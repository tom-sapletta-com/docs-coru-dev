# Schnellstart

```
pip install koru
koru auto
```

Bei einem frischen Projekt (ohne `.planfile/`) stellt der Assistent **eine Frage** zu Ihrer Priorität, legt das erste Ticket an und startet die Schleife. Die Länge des Interviews steuert `KORU_ONBOARDING_MAX_QUESTIONS` (`0` = keine Fragen, `all` = volles Interview); ganz überspringen mit `KORU_AUTO_SKIP_WIZARD=1`.

> `koru auto` stoppt vorherige Schleifen des Projekts und startet mit `--replace-existing`. Ein Live-Dashboard öffnet sich unter `http://127.0.0.1:8765/`.

Nützliche erste Befehle:

```
koru doctor        # Diagnose: planfile, Weg-Abhängigkeiten, Sockets, Plugins
koru serve         # nur Dashboard (Tickets, Wege, Event-Stream)
koru wizard        # volles interaktives Strategie-Interview
```
