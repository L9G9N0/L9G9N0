# Developer Setup & Contribution Guide

This document details local setup, dependency tracking, compiler targets, and validation instructions.

---

## 1. Prerequisites

Ensure you have the following toolchains installed:
- **C++ Compiler**: `clang` (Xcode command line tools) or `g++` supporting standard `C++17` or `C++20`.
- **Python Runtime**: `Python 3.10` or higher.
- **Swift/Xcode**: `Xcode 15` or command-line developer tools supporting `Swift 5.9`.

---

## 2. Low-Level C++ PAM Compilation

To compile and link the PAM biometric module locally for verification:

```bash
# Compile client source code
g++ -O3 -std=c++17 -shared -fPIC -lpam -o pam_faceunlock.so src/pam_faceunlock.cpp
```

### Verification Flags
- `-O3`: Optimizes binary size and memory layout for microsecond run-time responses.
- `-shared`: Generates a shared library for macOS login module linkage.
- `-lpam`: Links against the host operating system pluggable authentication headers.

---

## 3. Python Virtual Environments

To construct isolated runtime packages for backend services (FastAPI/Predictors):

```bash
# Create sandbox
python3 -m venv venv
source venv/bin/activate

# Install required components
pip install --upgrade pip
pip install fastapi uvicorn xgboost scikit-learn pandas
```

---

## 4. Linting and Formatting

All commits must pass formatting standards prior to merging:
```bash
# Python styling
black --check src/

# Static checking
flake8 src/
```
