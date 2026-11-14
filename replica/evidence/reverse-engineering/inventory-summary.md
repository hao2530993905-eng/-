# Zotero 10.0.6 package inventory (static observations)

## Identity and architecture
- Bundle: `/Applications/Zotero.app`, bundle ID `org.zotero.zotero`, version/build `10.0.6`.
- Main executable SHA-256: `7daa49fec5d27bdafcf49d2f425b21cba684e59718c8e5399679f6353025b116`.
- Main executable and XUL are universal x86_64+arm64 Mach-O. The application is a Firefox/XUL-based desktop app, not Electron.

## Components and declared entry points
- Nested plugin-container, media-plugin-helper and updater apps; Safari extension and Safari web extension; XUL and media/security dynamic libraries.
- Document declarations: RIS, ISI, MODS, RDF, BibTeX, MARC, CSL, XML and text.
- URL scheme: `zotero://`; AppleScript is enabled in Info.plist.
- `Contents/Resources/app/omni.ja` SHA-256: `85a70f000e932ad76d96cf9e883b2f1b78193f8e9a8cacd206f18c301e9cf87d`.

## Relevant code observations
- `modules/BrowserContentHandler.sys.mjs` parses `-datadir`; `dataDirectory.js` requires an absolute path or `profile`.
- A fresh profile without `-datadir` may use the real `~/Zotero`; isolation therefore requires both a dedicated profile and an explicit project-local data directory.
- Defaults include automatic sync and scraper updates, plus a local HTTP server on port 23119. The isolated test profile disables these before first launch.

## Limits and unknowns
- Package declarations and static code do not establish runtime reachability or behavior. They are candidates for UI verification.
- REA MCP tools are unavailable in this session and its CLI doctor is blocked by the installed Node patch version; no native decompilation was needed for initial entry-point discovery.
- Account sync, third-party word processors, browser connector round trips and paid/storage-service effects are not exercised without separate conditions/authorization.
