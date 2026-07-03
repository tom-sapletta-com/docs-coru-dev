# Tory wykonania

Token `--ide` wybiera, kto wykonuje pracę. Jedna kolejka, jeden pipeline weryfikacji — tor to tylko ustawienie, a gdy wybrany jest naprawdę niedostępny, Koru **ratuje przejazd innym torem**.

## Zewnętrzne IDE

```
koru -a --ide windsurf     # albo: vscode, vscodium, cursor, antigravity, jetbrains, zed
```

- Daemon autopilota nasłuchuje na `$XDG_RUNTIME_DIR/koru-autopilot-<ide>.sock`; plugin IDE łączy się z nim.
- Wklejenie i wysłanie są *weryfikowane* (sondy pola, sentinel schowka, kontrola dymków) — niepotwierdzony submit jest raportowany, nie zakładany.
- Gdy plugin jest niedostępny, przejazd schodzi łańcuchem GUI: `vdisplay → imgl → gillm GuiDriver → nlp2uri focus → OS injector`.
- `--ide auto` wybiera tor po aktywnym/uruchomionym IDE, hoście terminala lub markerach projektu.

## CLI dostawcy (tillm)

```
koru -a --ide claude                      # headlessowe sterowanie Claude Code
koru -a --ide aider --llm gpt-5.2         # model per przebieg
```

- Na hoście bez edytora `--ide auto` **samo wybiera pierwszy CLI dostawcy z PATH** (wyłączenie: `KORU_AUTO_SHELL_CLIENT=0`).
- Jeśli zażądano klienta shellowego, a tillm nie ma — start **przerywa się głośno**, zamiast po cichu jechać torem edytora.
- Profil autonomii to domyślnie `automation` (klient może edytować pliki i uruchamiać testy); zmiana: `KORU_TILLM_EXECUTE_PROFILE`.
- Wspierani klienci: Claude Code, aider, codex, gemini-cli, cline, opencode, qwen-code, devin.

## Headless LLM

```
export OPENROUTER_API_KEY=sk-or-…
koru auto                                  # tickety z executor.kind=llm idą do API
```

Wybór modelu leży na tickecie (`inputs.llm_model`) albo w konfigu projektu — np. `openrouter/qwen/qwen3-coder-next`. Koszt każdego przebiegu jest śledzony (pakiet `costs`) i może renderować badge w README.
