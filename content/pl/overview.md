# Przegląd

**Koru** to otwartoźródłowa (Apache-2.0), w pełni autonomiczna pętla refaktoryzacji: wykrywa dług techniczny, zamienia znaleziska w tickety, zleca naprawę wykonawcy AI, weryfikuje każdą zmianę testami i bramkami jakości — i powtarza cykl. Bez Twojego udziału.

```
Detect → Plan → Execute → Verify → Heal → Learn → Repeat
```

- **Detect** — skanery i bramki jakości (regix, TestQL, wup, smelle kodu) produkują znaleziska.
- **Plan** — znaleziska stają się precyzyjnie zakreślonymi, deduplikowanymi *ticketami planfile* w kolejce.
- **Execute** — wykonawca pracuje nad ticketem: czat Twojego IDE, CLI dostawcy (Claude Code, aider, codex…) albo API modelu.
- **Verify** — testy + progi złożoności/utrzymywalności; czerwone = brak commita.
- **Heal** — niedostępne tory przełączają się na kolejne (plugin → sterownik GUI → wejście OS), a zepsute środowiska same się naprawiają.
- **Learn** — każdy krok trafia do event-sourcowanego logu JSONL, który można odtworzyć i audytować.
