# Konfiguracja i środowisko

## koru.yaml (projekt)

```
ide_integration:
  default_lane: windsurf
  lanes:
    windsurf: { backend: plugin_socket, ide: windsurf }
    cursor:   { backend: mcp_tool, mcp_server: koru }
autonomy:
  strategy: accordion_detail_to_general
```

## Kluczowe zmienne środowiskowe

| Zmienna | Efekt |
|---|---|
| `KORU_AUTOPILOT_INSTANCE` | Przypnij tor/instancję autopilota (np. `cursor-main`). Wygrywa z autodetekcją. |
| `KORU_TILLM_CLIENT` / `KORU_TILLM_MODEL` | Id klienta shellowego / model dla toru tillm. |
| `KORU_TILLM_EXECUTE_PROFILE` | `default` (zbliżony do read-only) lub `automation` (edycje + testy; domyślny w autonomii). |
| `KORU_AUTO_SHELL_CLIENT=0` | Wyłącz auto-wybór CLI dostawcy na hostach bez edytora. |
| `KORU_ONBOARDING_MAX_QUESTIONS` | Budżet pytań kreatora przy pierwszym `koru auto` (domyślnie `1`; `0` brak, `all` pełny wywiad). |
| `KORU_AUTO_SKIP_WIZARD=1` | Pomiń onboarding całkowicie. |
| `KORU_PLANFILE_CMD` | Przypnij CLI planfile. Gdy w przypiętym środowisku brakuje modułu, Koru raz ostrzega i przechodzi na auto-rozwiązywanie. |
| `KORU_AUTOPILOT_REDRIVE_COOLDOWN_SECONDS` | Cooldown aktywności czatu przed ponownym przejazdem (domyślnie 300). |
| `KORU_OS_INJECTOR=1` | Jawnie włącz fallback klawiatury/OS-injectora na Waylandzie. |
| `KORU_STDIO_FORMAT` | Wyjście zdarzeń `human` albo `jsonl`. |
| `KORU_TILLM_PATH` | Ścieżka do checkoutu tillm dla deweloperów (instalacje z PyPI jej nie potrzebują). |
