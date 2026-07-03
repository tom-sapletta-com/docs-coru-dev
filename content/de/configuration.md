# Konfiguration & Umgebung

## koru.yaml (Projekt)

```
ide_integration:
  default_lane: windsurf
  lanes:
    windsurf: { backend: plugin_socket, ide: windsurf }
    cursor:   { backend: mcp_tool, mcp_server: koru }
autonomy:
  strategy: accordion_detail_to_general
```

## Wichtige Umgebungsvariablen

| Variable | Wirkung |
|---|---|
| `KORU_AUTOPILOT_INSTANCE` | Autopilot-Weg/-Instanz festnageln (z. B. `cursor-main`). Gewinnt gegen Autodetektion. |
| `KORU_TILLM_CLIENT` / `KORU_TILLM_MODEL` | Shell-Client-Id / Modell für den tillm-Weg. |
| `KORU_TILLM_EXECUTE_PROFILE` | `default` (nahezu read-only) oder `automation` (Änderungen + Checks; Autonomie-Standard). |
| `KORU_AUTO_SHELL_CLIENT=0` | Auto-Wahl eines Vendor-CLI auf editorlosen Hosts abschalten. |
| `KORU_ONBOARDING_MAX_QUESTIONS` | Fragenbudget des Assistenten beim ersten `koru auto` (Standard `1`; `0` keine, `all` volles Interview). |
| `KORU_AUTO_SKIP_WIZARD=1` | Onboarding komplett überspringen. |
| `KORU_PLANFILE_CMD` | Planfile-CLI festnageln. Fehlt das Modul in der gepinnten Umgebung, warnt Koru einmal und fällt auf Auto-Auflösung zurück. |
| `KORU_AUTOPILOT_REDRIVE_COOLDOWN_SECONDS` | Chat-Aktivitäts-Cooldown vor erneutem Lauf (Standard 300). |
| `KORU_OS_INJECTOR=1` | Tastatur-/OS-Injector-Fallback unter Wayland explizit aktivieren. |
| `KORU_STDIO_FORMAT` | Event-Ausgabe `human` oder `jsonl`. |
| `KORU_TILLM_PATH` | Pfad zum tillm-Checkout für Entwickler (PyPI-Installationen brauchen ihn nicht). |
