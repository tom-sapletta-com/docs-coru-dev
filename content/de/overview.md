# Überblick

**Koru** ist eine quelloffene (Apache-2.0), vollständig autonome Refactoring-Schleife: Sie erkennt technische Schulden, macht Befunde zu Tickets, lässt einen KI-Executor sie beheben, verifiziert jede Änderung mit Tests und Quality Gates — und wiederholt den Zyklus. Ohne Ihr Zutun.

```
Detect → Plan → Execute → Verify → Heal → Learn → Repeat
```

- **Detect** — Scanner und Quality Gates (regix, TestQL, wup, Code-Smells) erzeugen Befunde.
- **Plan** — Befunde werden zu klar umrissenen, deduplizierten *Planfile-Tickets* in einer Queue.
- **Execute** — ein Executor bearbeitet das Ticket: der Chat Ihrer IDE, ein Vendor-CLI (Claude Code, aider, codex…) oder eine Modell-API.
- **Verify** — Tests + Komplexitäts-/Wartbarkeitsschwellen; rot heißt kein Commit.
- **Heal** — nicht verfügbare Wege fallen zurück (Plugin → GUI-Treiber → OS-Eingabe), defekte Umgebungen reparieren sich selbst.
- **Learn** — jeder Schritt landet in einem event-sourced JSONL-Log, das Sie abspielen und auditieren können.
