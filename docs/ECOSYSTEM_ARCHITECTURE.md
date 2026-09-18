# ECOSYSTEM_ARCHITECTURE.md (V4)

Status: observed + decided from evidence. No monorepo. No god-library.

## Reality (discovered)

28 repos: 20 single-file Python tools (`requests` + stdlib only, argparse CLI,
`--json` file output), 1 bash installer, 3 learning/docs, 3 legacy, 1 profile.
Duplication is real but shallow: HTTP-fetch+timeout+UA (~5 lines) and finding-print
patterns repeat in every tool. No shared imports anywhere (verified by grep).

## Decision

- Repos stay **separate** (CORE=none needed). Rationale: each tool is 60–150 lines,
  Termux-friendly, zero-install friction. A shared `tbh-core` package would add
  install/versioning cost exceeding the ~5 duplicated lines.
- Integration layer = `toolkit` package in **TBH-Toolkit** (PR #1 OPEN): full
  finding model, safety allowlist, reporting, tests. Standalone tools keep working.

```
TBH-Toolkit/toolkit (integrates) ──uses ideas from──▶ 20 standalone tools
        │                                                  │ (unchanged UX)
   safety/config/reporting/tests                     each: fetch→probe→print
```

## Data flow (every detector)

INPUT (CLI -u/--url, no validation) → PROCESSING (GET + safe payload, timeout 3–5s)
→ MATCH (substring/regex on response) → OUTPUT (terminal + optional JSON file)

V4 fix: hostname extraction (`netloc`→`hostname`) so `host:port` targets resolve.
