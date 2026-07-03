# Rozwiązywanie problemów

Zacznij od doctora:

```
koru doctor
planfile_binary → pass
lane_dependencies → pass | tillm=yes; gillm=yes
```

- **`--ide claude` zgłasza brak tillm** — `pip install tillm` w tym samym środowisku co koru (w nowych wersjach to twarda zależność; starsze instalacje mogą jej nie mieć).
- **Kolejka sypie "No module named planfile"** — `KORU_PLANFILE_CMD` wskazuje środowisko bez planfile; nowe koru samo przechodzi na fallback i ostrzega. Zainstaluj tam planfile albo usuń pin.
- **Pętla wkleja w złe okno / nic się nie dzieje na Waylandzie** — uruchom `koru autopilot prepare-vdisplay --ide <ide>` i skalibruj; ślepe kliknięcia OS-injectora są odrzucane, chyba że `KORU_ALLOW_BLIND_KEYBOARD_FALLBACK=1`.
- **`koru -a: unrecognized arguments`** — stare koru na PATH (sprawdź `koru --version`, potem `pip install -U koru` w *tamtym* środowisku). Zwykle winne jest kilka Pythonów (conda/pyenv/venv).
- **Niezgodność wersji daemona** — pętla sama restartuje przestarzałe daemony; uporczywa niezgodność = dwie różne instalacje koru walczą ze sobą — wyrównaj je.
- **Ticket utknął w `waiting_input`** — to ticket `executor=human`: odpowiedz w IDE, albo `koru replay 'ticket input PLF-…'`, albo zamknij go.

## Świeży toolchain w środowiskach pętli

```
# pyproject.toml projektu z pętlą (domyślna grupa uv):
[dependency-groups]
dev = ["koru>=0.1.366", "goal>=2.1.264", "planfile>=0.1.104", "tillm>=0.1.37"]
```

Wtedy każdy przebieg `goal -au` (`uv sync --upgrade`) podbija narzędzia; działająca pętla podchwyci nowe wersje przy następnym restarcie.
