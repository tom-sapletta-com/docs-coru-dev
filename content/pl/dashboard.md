# Dashboard i zdarzenia

```
koru serve          # http://127.0.0.1:8765/ (zajęty port → następny wolny)
```

- **Overview** — wybór projektu, wybór toru IDE (edytory *i* wykryte CLI dostawców), tabela torów LLM/IDE z dostępnością.
- **Tickets** — stan kolejki na żywo, historia per ticket.
- **Events** — event-sourcowany magazyn JSONL (`.koru/event-store.jsonl`, strumień obserwowalności w `.koru/events/`): każdy skan, przejazd, decyzja i pominięcie z powodem. Odtwarzanie: `koru replay`.
