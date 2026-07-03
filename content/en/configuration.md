# Configuration & environment

## koru.yaml (project)

```
ide_integration:
  default_lane: windsurf
  lanes:
    windsurf: { backend: plugin_socket, ide: windsurf }
    cursor:   { backend: mcp_tool, mcp_server: koru }
autonomy:
  strategy: accordion_detail_to_general
```

## Key environment variables

| Variable | Effect |
|---|---|
| `KORU_AUTOPILOT_INSTANCE` | Pin the autopilot lane/instance (e.g. `cursor-main`). Wins over autodetection. |
| `KORU_TILLM_CLIENT` / `KORU_TILLM_MODEL` | Shell client id / model for the tillm lane. |
| `KORU_TILLM_EXECUTE_PROFILE` | `default` (read-only-ish) or `automation` (edit + run checks; autonomy default). |
| `KORU_AUTO_SHELL_CLIENT=0` | Disable auto-picking a vendor CLI on editor-less hosts. |
| `KORU_ONBOARDING_MAX_QUESTIONS` | Wizard question budget on first `koru auto` (default `1`; `0` none, `all` full interview). |
| `KORU_AUTO_SKIP_WIZARD=1` | Skip onboarding entirely. |
| `KORU_PLANFILE_CMD` | Pin the planfile CLI. If the pinned env lacks the module, Koru warns once and falls back to auto-resolution. |
| `KORU_AUTOPILOT_REDRIVE_COOLDOWN_SECONDS` | Chat-activity cooldown before a redrive (default 300). |
| `KORU_OS_INJECTOR=1` | Explicitly enable the keyboard/OS-injector fallback on Wayland. |
| `KORU_STDIO_FORMAT` | `human` or `jsonl` event output. |
| `KORU_TILLM_PATH` | Dev-checkout path for tillm (installed setups don't need it). |
