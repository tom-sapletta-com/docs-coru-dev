# Tickets & planfile

Koru never edits "because it felt like it" — every change traces to a ticket in `.planfile/` (managed by the [planfile](https://pypi.org/project/planfile/) package).

```
planfile ticket list --status open
planfile ticket show PLF-001
planfile ticket create "Reduce CC in parser.py" -d "…" --priority high
planfile ticket done PLF-001
```

- **Executors**: `human` (waits for you), `shell` (runs a command), `llm` (calls a model API), IDE drive (default for refactor prompts).
- **Deduplication**: gate findings carry a stable `[gate-finding:<key>]` marker — a still-failing gate appends a note instead of creating a duplicate.
- **Safety**: `ticket create` refuses unfilled template placeholders like `<finding_key>` (override: `--force`).
