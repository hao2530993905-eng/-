# Live SQLite capture assessment
Observation: the initial exploration capture reached storage capture and timed out using SQLite online backup. Direct read-only SQLite access also returned `database is locked`.
Static cause: bundled `xpcom/db.js` sets `DB_LOCK_EXCLUSIVE = true` and executes `PRAGMA main.locking_mode=EXCLUSIVE`; its own comment states this prevents access while Zotero is open. The database is in WAL mode, but WAL does not remove the connection-lifetime exclusive lock.
Decision: do not modify the original app or database and do not copy raw SQLite/WAL files as a substitute for online backup. Continue UI-only exploration with storage explicitly `blocked`; after normal quit, perform a bounded read-only snapshot to establish persistence where possible.
Impact: live before/after database values, schema and full-table diffs are unavailable for this session. UI observations remain valid, but data-side-effect claims stay partially verified until post-quit checks.
