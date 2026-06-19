# Release & Versioning Policy

We follow [Semantic Versioning (SemVer)](https://semver.org/spec/v2.0.0.html) for tagging releases across all systems and portfolios.

---

## 1. Versioning Schema

Versions are defined as `MAJOR.MINOR.PATCH`:
- **MAJOR**: Architectures undergo breaking shifts (e.g. converting a Python backend service to Rust, changing IPC protocol models).
- **MINOR**: Adding new features or projects without affecting backwards compatibility of other API integrations.
- **PATCH**: Bug fixes, performance optimizations, or updating README/documentation metrics.

---

## 2. Release Steps

1. **Verify Builds**: Run compiler targets and static style linters.
2. **Update Changelog**: Document modifications inside [CHANGELOG.md](CHANGELOG.md).
3. **Commit Version Change**: Commit updates with the version tag as the message prefix.
4. **Git Tagging**: Create an annotated git tag:
   ```bash
   git tag -a v1.0.0 -m "Release version 1.0.0 detailing portfolio system layout"
   ```
5. **Push Tag**: Push tags to the upstream remote repository:
   ```bash
   git push origin v1.0.0
   ```
