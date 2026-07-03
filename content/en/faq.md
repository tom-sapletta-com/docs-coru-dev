# FAQ

## Does Koru commit unverified changes?

No. Verification (tests + gates) runs before commit; red blocks. Failures become tickets, not silent regressions.

## Can I run it fully offline?

Yes — pair it with a local OpenAI-compatible endpoint for the LLM lane, or a local CLI agent. No telemetry.

## Which models work?

Any model your executor can use: your IDE's built-in models, vendor CLIs' models (`--llm` to force one), or any OpenRouter/local model id for `executor.kind=llm` tickets.

## How do I stop the loop?

`Ctrl+C` in its terminal, or start a replacement with `koru auto` (it stops prior managed processes). State is checkpointed — the next start resumes the queue.
