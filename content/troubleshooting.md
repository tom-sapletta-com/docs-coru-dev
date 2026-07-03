# Troubleshooting

Start with the doctor:

```
koru doctor
planfile_binary → pass
lane_dependencies → pass | tillm=yes; gillm=yes
```

- **`--ide claude` says tillm is unavailable** — `pip install tillm` in the same environment as koru (it's a core dependency of recent versions; older installs may miss it).
- **Queue errors "No module named planfile"** — your `KORU_PLANFILE_CMD` points at an env without planfile; recent koru falls back automatically and warns. Install planfile there or unset the pin.
- **Loop pastes into the wrong window / nothing happens on Wayland** — run `koru autopilot prepare-vdisplay --ide <ide>` and calibrate; blind OS-injector clicks are refused unless `KORU_ALLOW_BLIND_KEYBOARD_FALLBACK=1`.
- **`koru -a: unrecognized arguments`** — an old koru on PATH (check `koru --version`, then `pip install -U koru` in *that* environment). Multiple Pythons (conda/pyenv/venv) are the usual cause.
- **Daemon version mismatch** — the loop restarts stale daemons automatically; persistent mismatches mean two different koru installs are fighting — align them.
- **Ticket stuck in `waiting_input`** — it's an `executor=human` ticket: answer it in the IDE, or `koru replay 'ticket input PLF-…'`, or close it.

## Keep the toolchain fresh in loop environments

```
# pyproject.toml of the project running the loop (uv default group):
[dependency-groups]
dev = ["koru>=0.1.366", "goal>=2.1.264", "planfile>=0.1.104", "tillm>=0.1.37"]
```

Then every `goal -au` run (`uv sync --upgrade`) upgrades the tools; a running loop picks new versions up on its next restart.
