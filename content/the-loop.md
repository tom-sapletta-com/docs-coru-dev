# The autonomous loop

Each cycle of `koru auto` / `koru autonomous up`:

1. **Scan** (when the queue is idle) — discovery produces new tickets.
2. **Queue** — the planfile queue picks the next runnable ticket by priority.
3. **Drive** — the ticket prompt is delivered to the selected executor lane.
4. **Verify** — post-drive checks (git changes, tests, gates, LLM evaluation of the outcome).
5. **Decide** — a decision trace records what was observed, decided, done, and what comes next.

The loop is conservative by design: it will *wait* instead of pasting over an active IDE chat (chat-activity cooldown, tune with `KORU_AUTOPILOT_REDRIVE_COOLDOWN_SECONDS`), it skips redrives when nothing changed, and every skip states its reason in the log.
