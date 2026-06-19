# Security Policy

## Supported Versions

Only the latest release version on the `main` branch is actively supported with security updates.

| Version | Supported |
| :--- | :--- |
| 1.0.x | :white_check_mark: Yes |
| < 1.0.0 | :x: No |

## Reporting a Vulnerability

We take the security of low-level systems architectures, authentication modules, and cloud sync pipelines seriously. If you find a vulnerability, please report it via secure channels rather than opening a public issue.

### Process
1. Email your findings to `hariom24229@iiitd.ac.in`.
2. Do not disclose the issue publicly until we have aligned on verification and a fix.
3. We will acknowledge receipt of your report within 48 hours and work with you to analyze and patch the vulnerability.

## Security Architecture Principles

1. **Local Authentication Boundaries**: Low-level biometrics daemons process user landmarks inside memory loops; raw media formats must not persist to the local filesystem or make unauthorized network connections.
2. **IPC Access Controls**: UNIX sockets used for privilege escalation or communication with native macOS PAM modules must enforce strict file permissions (`0600` or `0660` restricted to the owner daemon).
3. **Secret Isolation**: Never commit API keys or private database links. Use environment variables managed via system keychain modules.
