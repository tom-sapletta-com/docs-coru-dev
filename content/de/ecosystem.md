# Ökosystem-Pakete

| Paket | Rolle |
|---|---|
| **koru** | Die Schleife: Queue, Zyklen, Lauf-Orchestrierung, Dashboard, Doctor. |
| **planfile** | Tickets, Sprints, Queue — das Audit-Rückgrat. |
| **tillm** | Registry & Treiber für Shell-LLM-Clients (null Abhängigkeiten; Kernabhängigkeit von koru). |
| **gillm** | GUI-Injektion: Tastatur-/Maus-Treiber, Fehlerklassifikation. |
| **koruide** | IDE-Identität & Control-Plane: Erkennung, Aliasse, Plugin-Daemon-Protokoll. |
| **vdisplay** | Bildschirm-Wahrheit: Captures, VQL-Element-Karten, verifizierte GUI-Aktuation. |
| **regix / testql / wup** | Qualitäts-, Verhaltens- und On-Change-Gates. |
| **goal** | Repo-Automatisierung: Deps → Diagnose → Tests → Commit/Publish. |
