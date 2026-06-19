# Contributing to L9G9N0 Portfolio Workspace

Thank you for your interest in contributing to this developer architecture blueprint. To maintain a production-grade codebase, please adhere to the following workflow guidelines.

---

## Code of Conduct

All contributors are expected to uphold our [Code of Conduct](CODE_OF_CONDUCT.md).

---

## How to Contribute

### 1. Reporting Bugs
- Search the issue tracker to ensure the bug has not been reported.
- If it is new, open an issue using the **Bug Report** template.
- Include OS version, environment details, and steps to reproduce.

### 2. Feature Requests
- Feature requests are tracked via the **Feature Request** template.
- Explain the problem statement, the proposed solution, and how the changes affect low-level architectures.

### 3. Pull Requests (PRs)
- Fork the repository and create a branch from `main`.
- Branch name format: `feature/short-desc` or `bugfix/short-desc`.
- Ensure all code changes are fully documented in the matching architecture guides.
- Keep commits descriptive and follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
- Open a PR against `main` using the PR template.

---

## Development Standards

- **C++**: Compile using `std=c++17` or `std=c++20`. Avoid dynamic heap allocation inside tight liveness loops.
- **Python**: Format code using `black` and run static checking with `flake8`. Include type annotations for all public endpoints.
- **Swift**: Use standard SwiftLint guidelines for UI structures. Ensure Combine pipelines dispose of stream bindings correctly to avoid memory leaks.

---

## Contact channels

For any questions, open an issue using the **Question** template or email the maintainer at `hariom24229@iiitd.ac.in`.
