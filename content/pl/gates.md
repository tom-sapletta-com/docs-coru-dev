# Bramki jakości

| Bramka | Na co odpowiada | Narzędzie |
|---|---|---|
| **regix** | Czy metryka jakości się pogorszyła? Twarde progi: złożoność cyklomatyczna ≤ 15, indeks utrzymywalności ≥ 20 (cele: CC ≤ 10, MI ≥ 30, docstringi ≥ 80%). Naruszenia wskazują `plik::symbol`. | `regix gates` |
| **TestQL** | Czy zachowanie się zepsuło? Scenariuszowe sondy na żywych endpointach. | `testql run …` |
| **wup** | Czy watcher on-change działa i pokrywa przyrostowe edycje? | `wup status` |

Czerwona bramka robi dwie rzeczy: **blokuje commit** i **tworzy deduplikowany ticket** (przez `scripts/koru-gate-capture.py`) z dokładną failującą linią i komendą, która ją wyprodukowała — pętla naprawia znaleziska, zamiast je kolekcjonować.
