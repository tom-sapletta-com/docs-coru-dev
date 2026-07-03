# Komendy CLI (najczęstsze)

| Komenda | Działanie |
|---|---|
| `koru auto` / `koru -a` | Zatrzymaj wcześniejsze pętle, przeprowadź onboarding (jeśli trzeba), uruchom cykl autonomiczny. |
| `koru -a --ide <token>` | Wybór toru: id edytora, id klienta shellowego albo `auto`. |
| `koru -a --llm <model>` | Wymuś model dla torów klientów shellowych. |
| `koru doctor` | Diagnostyka: binarka/pin planfile, **zależności torów**, sockety, paczka pluginu, runtime IDE. |
| `koru scan --apply` | Jeden przebieg discovery; znaleziska stają się ticketami. |
| `koru wizard` | Pełny wywiad strategiczny (wiele pytań). |
| `koru serve` / `koru dashboard` | Dashboard + REST API. |
| `koru autopilot drive --ide X 'tekst'` | Pojedynczy ręczny przejazd (test toru). |
| `koru autopilot env --ide X` | Wypisz exporty env toru dla Twojego shella. |
