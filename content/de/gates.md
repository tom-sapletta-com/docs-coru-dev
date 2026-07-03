# Quality Gates

| Gate | Beantwortet | Werkzeug |
|---|---|---|
| **regix** | Hat sich eine Qualitätsmetrik verschlechtert? Harte Schwellen: zyklomatische Komplexität ≤ 15, Wartbarkeitsindex ≥ 20 (Ziele: CC ≤ 10, MI ≥ 30, Docstrings ≥ 80%). Verstöße nennen `datei::symbol`. | `regix gates` |
| **TestQL** | Hat sich das Verhalten verschlechtert? Szenario-Sonden gegen laufende Endpunkte. | `testql run …` |
| **wup** | Läuft der On-Change-Watcher und deckt inkrementelle Änderungen ab? | `wup status` |

Ein rotes Gate tut zwei Dinge: Es **blockiert den Commit** und **erzeugt ein dedupliziertes Ticket** (via `scripts/koru-gate-capture.py`) mit der exakten Fehlerzeile und dem auslösenden Befehl — die Schleife behebt Befunde, statt sie zu sammeln.
