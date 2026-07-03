# Tickets & Planfile

Koru ändert nie etwas "einfach so" — jede Änderung führt zu einem Ticket in `.planfile/` (verwaltet vom Paket [planfile](https://pypi.org/project/planfile/)).

```
planfile ticket list --status open
planfile ticket show PLF-001
planfile ticket create "Reduce CC in parser.py" -d "…" --priority high
planfile ticket done PLF-001
```

- **Executoren**: `human` (wartet auf Sie), `shell` (führt einen Befehl aus), `llm` (ruft eine Modell-API), IDE-Drive (Standard für Refactoring-Prompts).
- **Deduplizierung**: Gate-Befunde tragen einen stabilen Marker `[gate-finding:<key>]` — ein weiterhin rotes Gate hängt eine Notiz an, statt ein Duplikat zu erzeugen.
- **Sicherheit**: `ticket create` verweigert unausgefüllte Template-Platzhalter wie `<finding_key>` (Override: `--force`).
