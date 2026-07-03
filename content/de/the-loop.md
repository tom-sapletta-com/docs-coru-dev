# Die autonome Schleife

Jeder Zyklus von `koru auto` / `koru autonomous up`:

1. **Scan** (bei leerer Queue) — Discovery erzeugt neue Tickets.
2. **Queue** — die Planfile-Queue wählt das nächste lauffähige Ticket nach Priorität.
3. **Drive** — der Ticket-Prompt wird an den gewählten Ausführungsweg geliefert.
4. **Verify** — Prüfungen nach dem Lauf (Git-Änderungen, Tests, Gates, LLM-Bewertung des Ergebnisses).
5. **Decide** — eine Entscheidungsspur protokolliert, was beobachtet, entschieden, getan wurde und was folgt.

Die Schleife ist bewusst konservativ: Sie *wartet* lieber, statt in einen aktiven IDE-Chat zu tippen (Chat-Aktivitäts-Cooldown, Tuning: `KORU_AUTOPILOT_REDRIVE_COOLDOWN_SECONDS`), überspringt erneute Läufe ohne Änderungen, und jeder Skip nennt seinen Grund im Log.
