# FAQ

## Committet Koru unverifizierte Änderungen?

Nein. Die Verifikation (Tests + Gates) läuft vor dem Commit; rot blockiert. Fehlschläge werden Tickets, keine stillen Regressionen.

## Geht das komplett offline?

Ja — kombinieren Sie die Schleife mit einem lokalen OpenAI-kompatiblen Endpunkt für den LLM-Weg oder einem lokalen CLI-Agenten. Keine Telemetrie.

## Welche Modelle funktionieren?

Jedes, das Ihr Executor nutzen kann: die eingebauten Modelle Ihrer IDE, die Modelle der Vendor-CLIs (`--llm` erzwingt eines) oder jede OpenRouter-/lokale Modell-Id für `executor.kind=llm`-Tickets.

## Wie stoppe ich die Schleife?

`Ctrl+C` in ihrem Terminal — oder ein Ersatzstart mit `koru auto` (stoppt vorherige verwaltete Prozesse). Der Zustand ist gecheckpointet — der nächste Start setzt die Queue fort.
