# Pętla autonomiczna

Każdy cykl `koru auto` / `koru autonomous up`:

1. **Scan** (gdy kolejka jest pusta) — discovery tworzy nowe tickety.
2. **Queue** — kolejka planfile wybiera następny wykonywalny ticket wg priorytetu.
3. **Drive** — prompt ticketu trafia do wybranego toru wykonawczego.
4. **Verify** — kontrole po przejeździe (zmiany w gicie, testy, bramki, ocena wyniku przez LLM).
5. **Decide** — ślad decyzji zapisuje, co zaobserwowano, zdecydowano, zrobiono i co dalej.

Pętla jest z założenia ostrożna: raczej *poczeka*, niż wklei tekst na aktywny czat IDE (cooldown aktywności czatu, strojenie: `KORU_AUTOPILOT_REDRIVE_COOLDOWN_SECONDS`), pomija ponowne przejazdy bez zmian, a każde pominięcie podaje w logu swój powód.
