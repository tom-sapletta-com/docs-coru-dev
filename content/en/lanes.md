# Execution lanes

The `--ide` token selects who does the work. One queue, one verification pipeline — the lane is just a setting, and Koru **rescues a failing drive through another lane** when the chosen one is genuinely unavailable.

## External IDE

```
koru -a --ide windsurf     # or: vscode, vscodium, cursor, antigravity, jetbrains, zed
```

- The autopilot daemon listens on `$XDG_RUNTIME_DIR/koru-autopilot-<ide>.sock`; the IDE plugin connects to it.
- Paste and submit are *verified* (input probes, sentinel clipboard, bubble checks) — a submit that cannot be confirmed is reported, not assumed.
- When the plugin is unavailable the drive falls back down the GUI chain: `vdisplay → imgl → gillm GuiDriver → nlp2uri focus → OS injector`.
- `--ide auto` picks the lane from the focused/running IDE, terminal host, or project markers.

## Vendor CLI (tillm)

```
koru -a --ide claude                      # drive Claude Code headlessly
koru -a --ide aider --llm gpt-5.2         # pick the model per run
```

- On an editor-less host, `--ide auto` **auto-selects the first vendor CLI found on PATH** (opt out: `KORU_AUTO_SHELL_CLIENT=0`).
- If a shell-client token is requested but tillm is missing, startup **aborts loudly** instead of silently driving an editor lane.
- The autonomy profile defaults to `automation` (the client may edit files and run checks); override with `KORU_TILLM_EXECUTE_PROFILE`.
- Supported clients: Claude Code, aider, codex, gemini-cli, cline, opencode, qwen-code, devin.

## Headless LLM

```
export OPENROUTER_API_KEY=sk-or-…
koru auto                                  # tickets with executor.kind=llm use the API
```

Model selection lives on the ticket (`inputs.llm_model`) or in project config — e.g. `openrouter/qwen/qwen3-coder-next`. Cost per run is tracked (the `costs` package) and can render a badge in your README.
