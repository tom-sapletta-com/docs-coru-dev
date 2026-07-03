# Szybki start

```
pip install koru
koru auto
```

Na świeżym projekcie (bez `.planfile/`) kreator zadaje **jedno pytanie** o Twój priorytet, tworzy pierwszy ticket i uruchamia pętlę. Długość wywiadu kontroluje `KORU_ONBOARDING_MAX_QUESTIONS` (`0` = bez pytań, `all` = pełny wywiad); całość pominiesz przez `KORU_AUTO_SKIP_WIZARD=1`.

> `koru auto` zatrzymuje wcześniejsze pętle projektu i startuje z `--replace-existing`. Żywy dashboard otwiera się pod `http://127.0.0.1:8765/`.

Przydatne pierwsze komendy:

```
koru doctor        # diagnostyka: planfile, zależności torów, sockety, pluginy
koru serve         # sam dashboard (tickety, tory, strumień zdarzeń)
koru wizard        # pełny interaktywny wywiad strategiczny
```
