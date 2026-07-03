# Quality gates

| Gate | Answers | Tool |
|---|---|---|
| **regix** | Did a quality metric regress? Hard thresholds: cyclomatic complexity ≤ 15, maintainability index ≥ 20 (targets: CC ≤ 10, MI ≥ 30, docstrings ≥ 80%). Violations name `file::symbol`. | `regix gates` |
| **TestQL** | Did behavior regress? Scenario probes against live endpoints. | `testql run …` |
| **wup** | Is the on-change watcher up, covering incremental edits? | `wup status` |

Red gates do two things: **block the commit** and **create a deduplicated ticket** (via `scripts/koru-gate-capture.py`) with the exact failing line and the command that produced it — so the loop fixes findings instead of accumulating them.
