# CLI reference (most used)

| Command | What it does |
|---|---|
| `koru auto` / `koru -a` | Stop prior loops, onboard if needed, start the autonomous cycle. |
| `koru -a --ide <token>` | Pick the lane: editor id, shell client id, or `auto`. |
| `koru -a --llm <model>` | Force the model for shell-client lanes. |
| `koru doctor` | Diagnostics: planfile binary/pin, **lane dependencies**, sockets, plugin bundle, IDE runtime. |
| `koru scan --apply` | One discovery pass; findings become tickets. |
| `koru wizard` | Full strategy interview (multi-question). |
| `koru serve` / `koru dashboard` | Dashboard + REST API. |
| `koru autopilot drive --ide X 'text'` | One manual drive (for testing a lane). |
| `koru autopilot env --ide X` | Print lane env exports for your shell. |
