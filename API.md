# API Documentation

This document describes the HTTP and IPC API specifications for the OrbitSync and Q-Commerce SLA systems.

---

## 1. OrbitSync API (Sync Gateway)

### Create Sync Session
Initialize a new local-to-cloud synchronization transaction session.

```http
POST /api/v1/sync/sessions
Content-Type: application/json
```

**Request Parameters:**
```json
{
  "client_id": "macos-desktop-client-001",
  "sync_directory": "/Users/user/documents",
  "file_count": 142
}
```

**Response Header:** `201 Created`
```json
{
  "session_id": "sess_982348572190",
  "status": "initialized",
  "created_at": "2026-06-19T10:00:00Z"
}
```

---

### Sync Directory Event
Push filesystem modification logs to update indices.

```http
POST /api/v1/sync/events
Content-Type: application/json
```

**Request Parameters:**
```json
{
  "session_id": "sess_982348572190",
  "event_type": "CREATE",
  "file_path": "research/notes.txt",
  "file_size": 2048,
  "checksum": "d3b07384d113edec49eaa6238ad5ff00"
}
```

**Response Header:** `200 OK`
```json
{
  "event_id": "ev_012839",
  "indexed": true,
  "semantic_tags": ["research", "notes", "academics"]
}
```

---

## 2. Q-Commerce Predictor API

### Predict Delivery SLA
Calculate probability of delivery violations.

```http
POST /api/v1/predictor/predict
Content-Type: application/json
```

**Request Parameters:**
```json
{
  "distance_km": 4.2,
  "carrier_load": 12,
  "weather_condition": "rainy",
  "hub_congestion_score": 0.82
}
```

**Response Header:** `200 OK`
```json
{
  "breach_probability": 0.91,
  "breach_predicted": true,
  "diagnostics": {
    "root_cause": "High hub congestion score (82%) coupled with rain-induced carrier delays.",
    "severity": "CRITICAL"
  }
}
```
