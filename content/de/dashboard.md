# Dashboard & Events

```
koru serve          # http://127.0.0.1:8765/ (belegter Port → nächster freier)
```

- **Overview** — Projektwahl, IDE-Weg-Wahl (Editoren *und* erkannte Vendor-CLIs), Tabelle der LLM/IDE-Wege mit Verfügbarkeit.
- **Tickets** — Live-Queue-Zustand, Historie pro Ticket.
- **Events** — der event-sourced JSONL-Store (`.koru/event-store.jsonl`, Observability-Stream in `.koru/events/`): jeder Scan, Lauf, jede Entscheidung und jeder Skip mit Grund. Wiedergabe: `koru replay`.
