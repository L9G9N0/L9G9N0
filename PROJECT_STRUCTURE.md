# Project Directory Structure

This document provides a detailed breakdown of the file organization, configuration files, and layout of this portfolio workspace.

---

## Workspace Layout

```
L9G9N0/
├── .github/                     # GitHub operations configurations
│   ├── ISSUE_TEMPLATE/          # Issue template definitions
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── question.md
│   ├── PULL_REQUEST_TEMPLATE.md # PR baseline templates
│   └── CODEOWNERS               # Repository code review owners
├── .editorconfig                # Universal indentation and lint configuration
├── LICENSE                      # MIT Open Source License
├── CHANGELOG.md                 # Semantic versioning release log
├── CONTRIBUTING.md              # Open source contribution guidelines
├── CODE_OF_CONDUCT.md           # Professional participant rules
├── SECURITY.md                  # Security reporting policy
├── SUPPORT.md                   # Communication and assistance guides
├── ROADMAP.md                   # Feature development plan
├── ARCHITECTURE.md              # Systems design blueprints
├── API.md                       # Systems endpoint specifications
├── PROJECT_STRUCTURE.md         # Current file directory map
├── DEVELOPMENT.md               # Compiler instructions and run steps
├── RELEASE.md                   # Tagging and release policy
└── README.md                    # Main portfolio landing page
```

---

## Directory Responsibilities

### 1. `.github/`
Contains the configuration files for repository health, ticket automation, and issue workflow constraints:
- `ISSUE_TEMPLATE/`: Enforces structured bug, feature, and questions tickets to keep discussions focused.
- `CODEOWNERS`: Directs pull requests automatically to the appropriate maintainer based on file path ownership.

### 2. Base Documentation
- `ARCHITECTURE.md` and `API.md` act as the primary technical specification sheets, defining systems IPC boundaries, data formats, and memory caches.
- `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md` outline how developers can safely write extensions and run compilers locally.
