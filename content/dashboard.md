# Dashboard & events

```
koru serve          # http://127.0.0.1:8765/ (falls back to the next free port)
```

- **Overview** — project picker, IDE-lane picker (editors *and* detected vendor CLIs), LLM/IDE lanes table with availability.
- **Tickets** — live queue state, per-ticket history.
- **Events** — the event-sourced JSONL store (`.koru/event-store.jsonl`, observability stream in `.koru/events/`): every scan, drive, decision, and skip with its reason. Replay with `koru replay`.
