# System Architecture & Design Specifications

This document outlines the architectural specifications, component boundaries, and data paths for the key systems within this developer portfolio.

---

## 1. macOS FaceUnlock Architecture

A secure, offline biometric authentication pipeline that integrates with the macOS kernel via a custom Pluggable Authentication Module (PAM) interface.

### Component Design

```
+------------------+             +-------------------------+
|                  |             |                         |
|   macOS Login    |             |  Custom C++ PAM Module  |
|   / sudo flow    |------------>|  - pam_sm_authenticate  |
|                  |             |  - Initiates IPC Socket |
+------------------+             +------------+------------+
                                              |
                                              | (UNIX Domain Socket: /var/run/faceunlock.sock)
                                              v
+------------------+             +------------+------------+
|  MediaPipe/dlib  |             |  FaceUnlock Python      |
|  Verification    |<----------->|  Daemon                 |
|  - Landmarks     |             |  - RAM Embedding Cache  |
|  - Liveness      |             |  - Local Camera Capture |
+------------------+             +-------------------------+
```

### IPC Protocol & Core Logic
- **PAM Client Wrapper**: Written in C++. It binds to `libpam` interfaces and writes request packets containing the username and challenge token to `/var/run/faceunlock.sock`.
- **Python Daemon (Server)**: Listens for socket connections. Upon receiving a challenge, it activates the camera stream, computes face landmarks, verifies eye-blink/liveness state changes, and calculates Euclidean distances against cached 128-D vectors.
- **Biometric Caching**: To achieve sub-second response times, user embedding vectors are cached in RAM on daemon initialization:
  ```python
  # Abstract representation of vector comparison logic
  def verify_identity(captured_vector, cached_vectors, threshold=0.6):
      for user, face_vectors in cached_vectors.items():
          distances = np.linalg.norm(face_vectors - captured_vector, axis=1)
          if np.min(distances) < threshold:
              return user, True
      return None, False
  ```

---

## 2. OrbitSync Vault Architecture

A cloud-native directory synchronization utility utilizing local file system events and semantic categorizations.

### Component Design

```
+----------------------+         +-----------------------+         +---------------------+
|   Local Filesystem   |         |    Watchdog Daemon    |         |   FastAPI Gateway   |
|   (Create/Edit/Del)  |-------->|   - FSEvents loop     |-------->|   - Sync controller |
|                      |         |   - Changes queue     |         |   - SQLite/Postgres |
+----------------------+         +-----------------------+         +----------+----------+
                                                                              |
                                                                              v
                                                                   +----------+----------+
                                                                   |  Groq Translation   |
                                                                   |  (Llama Semantic)   |
                                                                   |  - Metadata index   |
                                                                   +---------------------+
```

### Data Synchronization Flow
1. **Directory Watcher**: A python daemon hooks into the OS filesystem monitoring framework (`FSEvents` on macOS or `inotify` on Linux).
2. **Batch Processor**: Events are queued and batched to avoid duplicate writes on multi-file operations.
3. **API Layer**: FastAPI processes batch operations, updating PostgreSQL indices and updating local storage cache layers.
4. **Semantic Tagging**: Uploaded files trigger an asynchronous celery/background process that queries the Groq API (Llama-3.1-8b) to parse file content structures and index tags for enhanced retrieval queries.

---

## 3. Q-Commerce Logistics SLA Predictor

A decoupled MLOps workflow optimized for predicting logistics delivery delays and identifying root causes.

### System Diagram

```
[Raw Event Streams] -> [Preprocessing] -> [XGBoost Model]
                                                |
                                        (Breach Predicted?)
                                         /             \
                                       (No)           (Yes)
                                       /                 \
                                  [Record]          [Groq LLM Pipeline]
                                                     - Context Payload
                                                     - Cause Diagnosis
```

### Decoupling Logic
- **Predictive Core**: A localized XGBoost regressor/classifier evaluates features (distance, weather, rider payload, order rate) to compute breach probabilities.
- **Diagnostic Core**: If the prediction breaches the SLA constraint, the event is flagged and sent to Groq's Llama-3.1 API with the logs context. This extracts structured root-cause explanations (e.g., "High hub congestion coupled with adverse weather delays").

---

## 4. Devotee Mode

A native macOS distraction blocker that monitors application process states and forces deep work patterns.

### Blocker Engine Implementation
- **NSWorkspace Hook**: Swift monitors process lifecycles via `NSWorkspace.shared.notificationCenter` notifications for launched applications.
- **Lock-Free Checks**: Process metadata maps to a dictionary structure (`[String: BlockInfo]`) to resolve block evaluations in $O(1)$ lookup time:
  ```swift
  struct BlockInfo {
      let processName: String
      let priorityLevel: Int
      let blockReason: String
  }
  ```
- **Action**: Violating running applications are immediately sent termination signals:
  ```swift
  func enforceBlock(app: NSRunningApplication) {
      if blocklist[app.localizedName ?? ""] != nil {
          app.terminate()
      }
  }
  ```
