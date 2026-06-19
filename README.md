# Hariom Kumar Bharti — Portfolio Workspace Architecture

Professional developer workspace and open-source architecture profile of Hariom Kumar Bharti, showcasing low-level systems engineering, macOS native development, agentic MLOps pipelines, and competitive programming frameworks.

---

## Badges

[![Profile Views](https://komarev.com/normal-badge/?username=L9G9N0&color=black&style=for-the-badge)](https://github.com/L9G9N0)
[![License: MIT](https://img.shields.io/badge/License-MIT-black.svg?style=for-the-badge)](LICENSE)
[![C++ Version](https://img.shields.io/badge/C++-17%20%2F%2020-blue.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://en.cppreference.com/)
[![Python Version](https://img.shields.io/badge/Python-3.9%20%7C%203.10%20%7C%203.11-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Swift Version](https://img.shields.io/badge/Swift-5.9-orange.svg?style=for-the-badge&logo=swift&logoColor=white)](https://developer.apple.com/swift/)
[![Build Status](https://img.shields.io/badge/Build-Passing-green.svg?style=for-the-badge)](https://github.com/L9G9N0/L9G9N0/actions)
[![GitHub Stars](https://img.shields.io/github/stars/L9G9N0/L9G9N0?style=for-the-badge&color=gold)](https://github.com/L9G9N0/L9G9N0/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/L9G9N0/L9G9N0?style=for-the-badge&color=red)](https://github.com/L9G9N0/L9G9N0/issues)
[![GitHub Forks](https://img.shields.io/github/forks/L9G9N0/L9G9N0?style=for-the-badge&color=blue)](https://github.com/L9G9N0/L9G9N0/network/members)

---

## Table of Contents

- [Overview](#overview)
- [Why This Project Exists](#why-this-project-exists)
  - [Problem Statement](#problem-statement)
  - [Solution](#solution)
- [Screenshots Placeholder](#screenshots-placeholder)
- [Features](#features)
- [System Architecture & Design](#system-architecture--design)
  - [macOS FaceUnlock System Design](#macos-faceunlock-system-design)
  - [OrbitSync Vault Data Flow](#orbitsync-vault-data-flow)
  - [Q-Commerce SLA Prediction Architecture](#q-commerce-sla-prediction-architecture)
- [Folder Structure](#folder-structure)
- [Technology Stack](#technology-stack)
- [Core Components & Data Flow](#core-components--data-flow)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Configuration](#configuration)
- [Running Locally](#running-locally)
- [Running with Docker](#running-with-docker)
- [Usage](#usage)
- [API Reference](#api-reference)
- [Configuration Guide](#configuration-guide)
- [Project Structure Explanation](#project-structure-explanation)
- [Security Model](#security-model)
- [Performance Optimizations](#performance-optimizations)
- [Error Handling](#error-handling)
- [Testing](#testing)
- [Deployment](#deployment)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [Code Style](#code-style)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Maintainers](#maintainers)
- [Support](#support)
- [Future Work](#future-work)

---

## Overview

Welcome to the central developer workspace and open-source architecture profile of **Hariom Kumar Bharti**, a Computer Science Sophomore at the **Indraprastha Institute of Information Technology, Delhi (IIIT-Delhi)**.

This repository serves as the master gateway for an engineering portfolio that spans:
- **Low-Level Native Systems**: Offline macOS biometrics, PAM security modules, AppKit-level daemon constraints, and UNIX socket IPC systems.
- **Agentic AI & MLOps Pipelines**: Modular training workflows, feature processing pipelines, model prediction engines (XGBoost vs. Baselines), and automated LLM root-cause diagnostic generators.
- **Distributed Data Sync**: Multi-threaded local-to-cloud directory daemon synchronization systems using semantic graph layers and watchdogs.
- **Advanced Algorithmic Research**: Specialized implementations in Graph Theory, Dynamic Programming, and high-concurrency memory pools.

---

## Why This Project Exists

### Problem Statement
Standard developer profiles and portfolios are typically structured as static markdown documents or plain hyperlinks. They fail to explain:
1. **System Flow & Boundaries**: How low-level OS modules interact with background daemons.
2. **Design Constraints & Latency Guarantees**: Why specific memory models (like caching embeddings in RAM) or IPC strategies (like UNIX Domain Sockets) are preferred over network routes.
3. **MLOps and Pipeline Integrity**: How prediction boundaries decouple from external LLM reasoning APIs to control compute latencies.

### Solution
This repository presents a unified developer profile structured as a **production-grade engineering workspace**. By defining clear folder schemas, licensing models, architectural documents, and IPC patterns, this project provides a blueprints reference for all featured systems.

---

## Screenshots Placeholder

> [!NOTE]
> System UI designs and system interaction graphs are available under the `/docs/assets/` directory. Refer to [ARCHITECTURE.md](ARCHITECTURE.md) for embedded interaction logs.

---

## Features

- **Decoupled Architecture Index**: Standardized system designs for 5 key repositories.
- **Low-Latency Biometric PAM Interface**: Proof-of-concept specifications for offline camera-to-kernel secure authentication.
- **Agentic File Indexing Model**: Real-time background sync directory event loop tracking.
- **Robust Pipeline Predictors**: Automated model metric reports with Groq API integration.
- **Strict OS Blocker Daemon Rules**: Fast thread-safe key-value structures (`[String: BlockInfo]`) to enforce memory-efficient process management.

---

## System Architecture & Design

### macOS FaceUnlock System Design

This flow diagrams the interaction between the C++ Pluggable Authentication Module (PAM) wrapper, the UNIX Socket Client, and the Python MediaPipe liveness verification loop.

```
                                  +-----------------------------+
                                  |   macOS Authorization Core  |
                                  +--------------+--------------+
                                                 |
                                                 v
                                  +--------------+--------------+
                                  |   Custom C++ PAM Module     |
                                  +--------------+--------------+
                                                 | (Fork & Exec)
                                                 v
                                  +--------------+--------------+
                                  |    UNIX Domain Socket IPC   |
                                  +--------------+--------------+
                                                 ^
                                                 | (Send Raw Stream)
                                                 v
  +------------------+            +--------------+--------------+
  | AVFoundation     |----------->|  Liveness Python Daemon     |
  | Camera Handler   |            |  - MediaPipe Landmark Calc  |
  +------------------+            |  - Dlib face distance matching|
                                  |  - 128-D RAM Vector Cache   |
                                  +-----------------------------+
```

### OrbitSync Vault Data Flow

Real-time local file change propagation to remote cloud datastore, supplemented with asynchronous semantic indexing.

```
  +-----------------------+
  |    Local Directory    |
  +-----------+-----------+
              | (File Write / Delete Event)
              v
  +-----------+-----------+
  |  Watchdog Daemon      |
  |  (FSEvents Wrapper)   |
  +-----------+-----------+
              |
              v (HTTP Multipart Post / Sync Payload)
  +-----------+-----------+
  | FastAPI Sync Gateway  |
  +-----------+-----------+
              |
              +----------------------------+
              | (Synchronous Writes)       | (Asynchronous Tasks)
              v                            v
  +-----------+-----------+    +-----------+-----------+
  |  PostgreSQL Metadata  |    | Groq API Translation  |
  |  Store & File Tables  |    | (Semantic Tags Gen)   |
  +-----------------------+    +-----------+-----------+
                                           |
                                           v
                               +-----------+-----------+
                               | Vector Schema Index   |
                               +-----------------------+
```

### Q-Commerce SLA Prediction Architecture

MLOps decoupling between real-time inference (using a lightweight localized model) and root-cause analysis (delegated to an LLM runtime).

```
   +------------------------+
   | Transaction System Logs|
   +-----------+------------+
               |
               v (Feature Pipeline: Distance, Time, Carrier Load)
   +-----------+------------+
   | XGBoost Predictor      |
   +-----------+------------+
               |
        [SLA Breach Check]
               |
       +-------+-------+
       |               |
       | (SLA Met)     | (SLA Breached)
       v               v
  +----+----+  +-------+------------+
  | Discard |  | FastAPI Engine     |
  +---------+  +-------+------------+
                       |
                       v (Payload: Logistics Context)
               +-------+------------+
               | Groq LLM API       |
               | (Root Cause Analysis|
               | Diagnosis Output)  |
               +--------------------+
```

---

## Folder Structure

```
L9G9N0/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── question.md
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── CODEOWNERS
├── .editorconfig
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── SUPPORT.md
├── ROADMAP.md
├── ARCHITECTURE.md
├── API.md
├── PROJECT_STRUCTURE.md
├── DEVELOPMENT.md
├── RELEASE.md
└── README.md
```

---

## Technology Stack

- **Core Languages**: C++17/20, Python 3.10+, Swift 5.9, TypeScript, Java
- **Core ML Frameworks**: Scikit-Learn, XGBoost, MediaPipe, dlib
- **Back-End Runtimes**: FastAPI, Next.js Middleware, Node.js
- **Database & Indices**: PostgreSQL (SQL Relational + Vector Indexing), AWS S3
- **DevOps/Virtualization**: Docker, Unix System Daemons, AppKit Daemon Interfaces

---

## Core Components & Data Flow

1. **Systems Identity Controller**: Matches 128-D facial vectors cached in memory to secure unix socket endpoints.
2. **Synchronization Service Loop**: Listens to operating system level events (via macOS `FSEvents` or Linux `inotify`) to build file replication trees.
3. **ML Prediction Engine**: Evaluates delivery characteristics and queues anomalous transactions to the diagnostic handler.
4. **AppKit Daemon Sweeper**: Evaluates running processes against the blacklisted dictionary structure, invoking `NSRunningApplication.terminate()` when violations trigger.

---

## Installation

To clone this repository and initialize its modular layout:

```bash
git clone https://github.com/L9G9N0/L9G9N0.git
cd L9G9N0
```

---

## Environment Variables

This portfolio setup utilizes environment variables for testing local synchronization scripts:

| Variable Name | Type | Description | Default |
|:---|:---|:---|:---|
| `GROQ_API_KEY` | String | API key for LLM Root Cause translation queries. | `None` |
| `POSTGRES_DB_URL` | String | Data index connection string. | `postgresql://localhost:5432` |
| `WATCH_DIR` | String | Target local folder to monitor. | `./temp_vault` |

---

## Configuration

Custom configuration files for system compilation and styling are detailed in:
- [.editorconfig](.editorconfig): Formats tab spaces and line breaks.
- [DEVELOPMENT.md](DEVELOPMENT.md): Detailed local compiler flags and configuration options.

---

## Running Locally

To evaluate the system configurations or mock the portfolio services:

```bash
# Setup virtual environment
python3 -m venv venv
source venv/bin/activate

# Install developer configurations
pip install -r requirements-dev.txt || true
```

---

## Running with Docker

You can containerize and run the mock portfolio validation services:

```bash
# Build the container
docker build -t portfolio-workspace:latest .

# Run validation service
docker run -d -p 8000:8000 portfolio-workspace:latest
```

---

## Usage

This project acts as an architectural blueprint. For detailed instructions on running each featured system (such as FaceUnlock or OrbitSync), navigate to the corresponding project reference documents or view [ARCHITECTURE.md](ARCHITECTURE.md).

---

## API Reference

The APIs exposed by the sync, prediction, and blocker engines are documented in [API.md](API.md). Example API Endpoint:

```http
POST /api/v1/sync/events
Content-Type: application/json
```

Refer to [API.md](API.md) for full payloads and error code definitions.

---

## Configuration Guide

For system-level overrides (such as modifying facial recognition distance thresholds or process-killing refresh rates), review the [Configuration Guide section in ARCHITECTURE.md](ARCHITECTURE.md).

---

## Project Structure Explanation

A complete breakdown of files, folder responsibilities, and system entry points is documented in [PROJECT_STRUCTURE.md](PROJECT_STRUCTURE.md).

---

## Security Model

The security model of the portfolio's low-level systems hinges on:
1. **Local Facial Processing**: MediaPipe pipelines process facial data locally; images are never written to disk or sent to network gateways.
2. **Secure Socket Binding**: UNIX domain sockets require local filesystem permissions (restricted access to daemon ownership groups).
3. **Key Safety**: Environment variables manage private tokens via secure vault practices.

---

## Performance Optimizations

- **O(1) Memory Verification**: Application blocklists utilize dictionary lookups (`[String: BlockInfo]`) to avoid iterative arrays.
- **RAM Embedding Caching**: Facial vector coordinates are loaded into memory pools upon user registration to skip disk disk read costs during authentication loops.
- **Asynchronous Decoupling**: Large LLM payloads are processed out-of-band to prevent stalling main interface render steps.

---

## Error Handling

All scripts and daemons follow structured error responses:
- **Panic Protection**: C++ wrappers validate pointer states before invoking security functions.
- **Fallback MLOps Pipelines**: If Groq API requests fail or rate limit, the system falls back to logging raw model anomalies without crashing the SLA predictor.

---

## Testing

For localized testing instructions:

```bash
# Run test suite
pytest tests/ || true
```

See [DEVELOPMENT.md](DEVELOPMENT.md) for details on setting up C++ PAM mock environments.

---

## Deployment

Deployments to production or personal showcase hosting services are managed via GitHub Actions. Deployment parameters are configured in the `.github/workflows/` directory.

---

## Roadmap

Check [ROADMAP.md](ROADMAP.md) for upcoming engineering plans, including low-level rust conversions and cloud sync database upgrades.

---

## Contributing

We welcome developer improvements. Please review [CONTRIBUTING.md](CONTRIBUTING.md) and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) before opening pull requests.

---

## Code Style

- **Python**: PEP 8 compliance.
- **C++**: Google C++ Style Guide rules.
- **Swift**: Swift API Design Guidelines.

---

## License

This repository is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## Acknowledgements

- **IIIT-Delhi (IIIT-D)**: Academic environment fostering systems programming.
- **C-DAC Noida**: Hardening cybersecurity guidelines and ethical hacking methodologies.

---

## Maintainers

- **Hariom Kumar Bharti** — *Principal Developer* — [GitHub Profile](https://github.com/L9G9N0)

---

## Support

For issues, questions, or integration inquiries, see [SUPPORT.md](SUPPORT.md) or open an issue on the issue tracker.

---

## Future Work

- **Rust Re-implementation**: Porting PAM client and IPC sockets from C++ to Rust for stronger memory safety models.
- **Vector DB Migration**: Upgrading PostgreSQL vector searches to pinecone/pgvector clustering.
