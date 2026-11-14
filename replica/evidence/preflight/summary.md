# Preflight observations
- Host is arm64 macOS 26.4; target is Zotero 10.0.6, universal x86_64+arm64, signed by Corporation for Digital Scholarship.
- Python 3.9.6 is pinned by the project. Swift 6.3.3 compiled the project AX tool to a native arm64 executable; AX reports `trusted`.
- Computer Use enumerated native apps successfully. No Zotero process was initially running.
- The build plugin's installation probe reported not installed, but the Build macOS Apps skill is readable in this session; only a minimal toolchain check was required for exploration.
- REA doctor could not start because rea-agents 6.9.0 requires Node 24.22.1+ and this host has 24.21.0. No client configuration was changed. Local archive inspection is the bounded fallback.
- Real Zotero data locations exist. They are excluded from runtime tests and storage captures.
