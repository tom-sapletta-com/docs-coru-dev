# CLI-Referenz (meistgenutzt)

| Befehl | Wirkung |
|---|---|
| `koru auto` / `koru -a` | Vorherige Schleifen stoppen, bei Bedarf onboarden, autonomen Zyklus starten. |
| `koru -a --ide <token>` | Weg wählen: Editor-Id, Shell-Client-Id oder `auto`. |
| `koru -a --llm <model>` | Modell für Shell-Client-Wege erzwingen. |
| `koru doctor` | Diagnose: planfile-Binary/Pin, **Weg-Abhängigkeiten**, Sockets, Plugin-Bundle, IDE-Runtime. |
| `koru scan --apply` | Ein Discovery-Durchlauf; Befunde werden zu Tickets. |
| `koru wizard` | Volles Strategie-Interview (mehrere Fragen). |
| `koru serve` / `koru dashboard` | Dashboard + REST-API. |
| `koru autopilot drive --ide X 'text'` | Ein manueller Lauf (zum Testen eines Wegs). |
| `koru autopilot env --ide X` | Weg-Umgebungsvariablen für Ihre Shell ausgeben. |
