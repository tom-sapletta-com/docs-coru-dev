# Fehlerbehebung

Beginnen Sie mit dem Doctor:

```
koru doctor
planfile_binary → pass
lane_dependencies → pass | tillm=yes; gillm=yes
```

- **`--ide claude` meldet fehlendes tillm** — `pip install tillm` in derselben Umgebung wie koru (in neuen Versionen eine Kernabhängigkeit; ältere Installationen können sie vermissen).
- **Queue-Fehler "No module named planfile"** — `KORU_PLANFILE_CMD` zeigt auf eine Umgebung ohne planfile; neues koru fällt automatisch zurück und warnt. Installieren Sie planfile dort oder entfernen Sie den Pin.
- **Schleife tippt ins falsche Fenster / nichts passiert unter Wayland** — `koru autopilot prepare-vdisplay --ide <ide>` ausführen und kalibrieren; blinde OS-Injector-Klicks werden verweigert, außer `KORU_ALLOW_BLIND_KEYBOARD_FALLBACK=1`.
- **`koru -a: unrecognized arguments`** — ein altes koru im PATH (`koru --version` prüfen, dann `pip install -U koru` in *jener* Umgebung). Meist sind mehrere Pythons (conda/pyenv/venv) die Ursache.
- **Daemon-Versionskonflikt** — die Schleife startet veraltete Daemons automatisch neu; hartnäckige Konflikte bedeuten zwei kämpfende koru-Installationen — angleichen.
- **Ticket hängt in `waiting_input`** — es ist ein `executor=human`-Ticket: in der IDE antworten, oder `koru replay 'ticket input PLF-…'`, oder schließen.

## Toolchain in Schleifen-Umgebungen aktuell halten

```
# pyproject.toml des Projekts mit der Schleife (uv-Standardgruppe):
[dependency-groups]
dev = ["koru>=0.1.366", "goal>=2.1.264", "planfile>=0.1.104", "tillm>=0.1.37"]
```

Dann aktualisiert jeder `goal -au`-Lauf (`uv sync --upgrade`) die Werkzeuge; eine laufende Schleife übernimmt neue Versionen beim nächsten Neustart.
