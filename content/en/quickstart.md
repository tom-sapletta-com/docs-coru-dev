# Quickstart

```
pip install koru
koru auto
```

On a fresh project (no `.planfile/`) the onboarding wizard asks **one question** about your priority, seeds the first ticket, and starts the loop. Control the interview length with `KORU_ONBOARDING_MAX_QUESTIONS` (`0` = no questions, `all` = full interview) or skip it entirely with `KORU_AUTO_SKIP_WIZARD=1`.

> `koru auto` stops prior loops for the project and starts with `--replace-existing`. A live dashboard opens at `http://127.0.0.1:8765/`.

Useful first commands:

```
koru doctor        # health checks: planfile, lane dependencies, sockets, plugins
koru serve         # dashboard only (tickets, lanes, event stream)
koru wizard        # full interactive strategy interview
```
