# Engineering Roadmap

This document outlines upcoming system enhancements, research projects, and architectural improvements planned for the featured systems in this workspace.

---

## Short-Term Objectives (Q3 2026)

### macOS FaceUnlock (Biometrics Core)
- [ ] **Rust Transition**: Port the UNIX domain socket server daemon and facial vector matching engine from Python/C++ to Rust for static memory safety guarantees.
- [ ] **Liveness Threshold Optimization**: Adjust MediaPipe landmark angles to improve detection consistency across high-contrast environments.

### OrbitSync Vault (Cloud Storage Sync)
- [ ] **Native macOS Sync Client**: Refactor Python Watchdog code to run directly on Swift's FSEvents framework to decrease daemon run-time CPU utilization.
- [ ] **pgvector Migration**: Replace PostgreSQL `ILIKE` tags search queries with vector embeddings stored using the `pgvector` extension.

---

## Mid-Term Objectives (Q4 2026)

### Q-Commerce Logistics Engine (MLOps)
- [ ] **On-Device LLM Pipeline**: Transition root-cause diagnosis queries from Groq API (Llama-3.1) to local, quantized Llama-3-3B/8B GGUF running inside llama.cpp.
- [ ] **Feature Store Integration**: Integrate Feast to store real-time transit telemetry metrics.

### System Blocker (Devotee Mode)
- [ ] **Advanced Sandbox Constraints**: Investigate using macOS App Sandbox or system configuration profiles (`.mobileconfig`) to restrict applications instead of active application sweeps.

---

## Long-Term Objectives (2027)

- [ ] **Unified Native CLI**: Build a central native executable (`agy-cli` or similar) in Swift or Rust that manages the installation, daemon lifecycle, socket binding, and local database sync of all sub-projects.
