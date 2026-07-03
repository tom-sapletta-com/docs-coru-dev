# Overview

**Koru** is an open-source (Apache-2.0), fully autonomous refactor loop: it detects technical debt, turns findings into tickets, drives an AI executor to fix them, verifies every change with tests and quality gates, and repeats — hands-off.

```
Detect → Plan → Execute → Verify → Heal → Learn → Repeat
```

- **Detect** — scanners and quality gates (regix, TestQL, wup, code smells) produce findings.
- **Plan** — findings become scoped, deduplicated *planfile tickets* in a queue.
- **Execute** — an executor works the ticket: your IDE's chat, a vendor CLI (Claude Code, aider, codex…), or a model API.
- **Verify** — tests + complexity/maintainability thresholds; red means no commit.
- **Heal** — unavailable lanes fall back (plugin → GUI driver → OS input), broken environments self-repair.
- **Learn** — every step lands in an event-sourced JSONL log you can replay and audit.
