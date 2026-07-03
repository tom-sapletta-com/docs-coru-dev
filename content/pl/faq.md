# FAQ

## Czy Koru commituje niezweryfikowane zmiany?

Nie. Weryfikacja (testy + bramki) biegnie przed commitem; czerwone blokuje. Porażki stają się ticketami, nie cichymi regresjami.

## Czy da się działać w pełni offline?

Tak — sparuj pętlę z lokalnym endpointem zgodnym z OpenAI dla toru LLM albo z lokalnym agentem CLI. Zero telemetrii.

## Które modele działają?

Każdy, którego użyje Twój wykonawca: modele wbudowane w IDE, modele CLI dostawców (`--llm` wymusza konkretny) albo dowolne id modelu OpenRouter/lokalnego dla ticketów `executor.kind=llm`.

## Jak zatrzymać pętlę?

`Ctrl+C` w jej terminalu — albo start zastępczy `koru auto` (zatrzymuje wcześniejsze zarządzane procesy). Stan jest checkpointowany — kolejny start wznawia kolejkę.
