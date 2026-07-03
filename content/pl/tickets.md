# Tickety i planfile

Koru nigdy nie edytuje "bo tak" — każda zmiana prowadzi do ticketu w `.planfile/` (zarządzanym przez pakiet [planfile](https://pypi.org/project/planfile/)).

```
planfile ticket list --status open
planfile ticket show PLF-001
planfile ticket create "Reduce CC in parser.py" -d "…" --priority high
planfile ticket done PLF-001
```

- **Wykonawcy**: `human` (czeka na Ciebie), `shell` (uruchamia komendę), `llm` (woła API modelu), drive IDE (domyślny dla promptów refaktoryzacyjnych).
- **Deduplikacja**: znaleziska bramek niosą stabilny znacznik `[gate-finding:<key>]` — wciąż czerwona bramka dopisuje notatkę zamiast tworzyć duplikat.
- **Bezpieczeństwo**: `ticket create` odmawia niewypełnionych placeholderów szablonu jak `<finding_key>` (obejście: `--force`).
