# Changelog

All notable changes to Ledger Once are documented here.

---

## 0.1.4 — 2026-03-10

### Added
- `blocked_return` parameter on `wrap_tools()` — set a custom return value for blocked calls so dispatch loops need no `None` check
- `guard.on_success()` callback — fires on every successful execution, pairs with `on_block()` for full observability
- `guard.check()` — one-line self-test that verifies exactly-once semantics are working correctly
- Guarantees and fingerprint algorithm documented explicitly in module docstring

### Fixed
- `__version__` updated to match PyPI release

---

## 0.1.3 — 2026-03-10

### Fixed
- Dashboard title corrected from "LEDGER / CONTROL" to "LEDGER / ONCE"

---

## 0.1.2 — 2026-03-10

### Fixed
- `pyproject.toml` build backend corrected (`setuptools.build_meta`)
- All references updated from `ledger-guard` to `ledger-once`

---

## 0.1.1 — 2026-03-10

### Added
- Initial PyPI release
- `guard()` — protect a single call
- `guard.wrap_tools()` — protect an entire toolset in one line
- `guard.policy()` — per-tool execution rules (`unlimited`, `replay`, `max`, `ttl`)
- `guard.on_block()` — callback fired on every blocked duplicate
- `guard.workflow()` / `guard.as_caller()` — multi-agent scoping
- `guard.retry()` / `guard.force()` — escape hatches
- `guard.log()` / `guard.stats()` / `guard.history()` — observability
- SQLite backend with WAL mode — survives restarts, safe for concurrent workers
- In-memory backend (`_Mem`) for testing
- `ledger-dashboard` — live web UI at `http://localhost:4242`
- `ledger` CLI — `show`, `tail`, `stats`, `clear`
- `CLAUDE.md` and `llms.txt` for AI coding assistant integration
- Key-based fingerprinting for non-deterministic arguments
- Footgun detector — warns when same tool is called with different args in <10s
- Crash recovery — stale `RUNNING` records expire after configurable timeout
