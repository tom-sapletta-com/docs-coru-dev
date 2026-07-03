# Ausführungswege

Das `--ide`-Token wählt, wer die Arbeit macht. Eine Queue, eine Verifikations-Pipeline — der Weg ist nur eine Einstellung, und wenn der gewählte wirklich nicht verfügbar ist, **rettet Koru den Lauf über einen anderen Weg**.

## Externe IDE

```
koru -a --ide windsurf     # oder: vscode, vscodium, cursor, antigravity, jetbrains, zed
```

- Der Autopilot-Daemon lauscht auf `$XDG_RUNTIME_DIR/koru-autopilot-<ide>.sock`; das IDE-Plugin verbindet sich damit.
- Einfügen und Absenden werden *verifiziert* (Eingabe-Sonden, Zwischenablage-Sentinel, Bubble-Checks) — ein unbestätigter Submit wird gemeldet, nicht angenommen.
- Ist das Plugin nicht verfügbar, fällt der Lauf die GUI-Kette hinunter: `vdisplay → imgl → gillm GuiDriver → nlp2uri focus → OS-Injector`.
- `--ide auto` wählt den Weg anhand der fokussierten/laufenden IDE, des Terminal-Hosts oder der Projekt-Marker.

## Vendor-CLI (tillm)

```
koru -a --ide claude                      # Claude Code headless steuern
koru -a --ide aider --llm gpt-5.2         # Modell pro Lauf wählen
```

- Auf einem Host ohne Editor wählt `--ide auto` **automatisch das erste Vendor-CLI aus dem PATH** (Abschalten: `KORU_AUTO_SHELL_CLIENT=0`).
- Wird ein Shell-Client angefordert, aber tillm fehlt, bricht der Start **laut ab**, statt still einen Editor-Weg zu fahren.
- Das Autonomie-Profil ist standardmäßig `automation` (der Client darf Dateien ändern und Checks ausführen); Änderung: `KORU_TILLM_EXECUTE_PROFILE`.
- Unterstützte Clients: Claude Code, aider, codex, gemini-cli, cline, opencode, qwen-code, devin.

## Headless-LLM

```
export OPENROUTER_API_KEY=sk-or-…
koru auto                                  # Tickets mit executor.kind=llm nutzen die API
```

Die Modellwahl liegt am Ticket (`inputs.llm_model`) oder in der Projekt-Konfiguration — z. B. `openrouter/qwen/qwen3-coder-next`. Die Kosten pro Lauf werden verfolgt (Paket `costs`) und können ein Badge im README rendern.
