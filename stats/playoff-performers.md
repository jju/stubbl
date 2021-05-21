

## Total UBBL performances

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| **Aeson**     | Badger Claws      |   42 |  513 |    0 |      0 |   28 |    0 |    0 |    0 |    0 |    2 |  136 |
| **Georgina**  | Arboreal Menace   |   15 |  181 |    5 |     14 |   11 |    7 |    0 |    5 |    0 |    1 |   69 |
| **Jacquetta** | TC Sump Runners   |    2 |   92 |   24 |    133 |    6 |    1 |    2 |   13 |    2 |    4 |   56 |
| Yakup    | Filthy Tide       |   11 |  157 |    1 |      1 |    6 |    0 |    0 |    0 |    0 |    3 |   49 |
| Souta    | Old Wyrms         |   13 |  157 |    6 |     -4 |   19 |    1 |    0 |   14 |    0 |    0 |   47 |
| **Elvis**     | Old Wyrms         |    0 |   87 |   27 |    137 |    0 |    0 |    1 |    6 |    0 |    3 |   44 |
| Moirin   | Old Wyrms         |    8 |   95 |    4 |      7 |   10 |    1 |    0 |   13 |    1 |    2 |   40 |
| Votyris  | Gargantuan Brutes |    9 |  190 |    4 |     16 |   12 |    0 |    2 |    7 |    1 |    1 |   40 |
| **Aronne**    | Cackling Furies   |    7 |  136 |    3 |     -5 |   16 |    2 |    0 |   12 |    0 |    2 |   38 |
| **Cleve**     | Badger Claws      |    0 |  194 |   37 |    118 |    0 |    0 |    0 |   15 |    1 |    0 |   37 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.round > 15 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```

## Top Green Cup playoff performers

| Player    | Team            | Season         | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVPs | SPP  |
|-----------|-----------------|----------------|------|------|------|--------|------|------|------|------|------|------|------|
| **Aeson**     | Badger Claws    | Green Cup IX   |   13 |  172 |    0 |      0 |    6 |    0 |    0 |    0 |    0 |    0 |   39 |
| **Aeson**     | Badger Claws    | Green Cup X    |   12 |  143 |    0 |      0 |    8 |    0 |    0 |    0 |    0 |    0 |   36 |
| Donat    | Badger Claws    | Green Cup VIII |   10 |  132 |    0 |      0 |    7 |    0 |    1 |    1 |    0 |    0 |   32 |
| Sabah    | Kaiju Dynamo    | Green Cup VIII |    8 |   96 |    0 |      0 |    6 |    0 |    0 |    1 |    0 |    0 |   24 |
| Souta    | Old Wyrms       | Green Cup IX   |    6 |   73 |    3 |     -3 |    7 |    1 |    0 |    3 |    0 |    0 |   23 |
| **Seosamh**   | Old Wyrms       | Green Cup X    |    6 |   35 |    0 |      0 |    5 |    0 |    0 |   11 |    1 |    1 |   23 |
| **Aronne**    | Cackling Furies | Green Cup IX   |    4 |   72 |    2 |     -4 |    5 |    1 |    0 |    2 |    0 |    1 |   21 |
| Costache | Glorious Hounds | Green Cup IX   |    7 |   50 |    0 |      0 |    6 |    0 |    0 |    5 |    0 |    0 |   21 |
| Iskra    | Glorious Hounds | Green Cup VII  |    5 |   31 |    0 |      0 |    4 |    0 |    0 |    3 |    0 |    1 |   20 |
| **Percy**     | Ravenous Eagles | Green Cup VII  |    0 |    0 |    0 |      0 |    0 |    0 |    7 |   55 |    0 |    1 |   19 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.round > 15 AND md.f_did = 1 GROUP BY pl.name, pl.f_tname, tours.name ORDER BY SPP DESC LIMIT 10;
```

## Top Open division Playoff performers

| Player    | Team            | Season         | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVPs | SPP  |
|-----------|-----------------|----------------|------|------|------|--------|------|------|------|------|------|------|------|
| **Aeson**     | Badger Claws      | UBBL Challenge     |   13 |  166 |    0 |      0 |   10 |    0 |    0 |    0 |    0 |    1 |   44 |
| Yakup    | Filthy Tide       | UBBL Challenge     |   10 |  126 |    0 |      0 |    5 |    0 |    0 |    0 |    0 |    2 |   40 |
| **Georgina**  | Arboreal Menace   | UBBL Challenge III |    7 |   95 |    3 |      7 |    6 |    5 |    0 |    0 |    0 |    1 |   39 |
| Votyris  | Gargantuan Brutes | UBBL Challenge II  |    7 |  136 |    4 |     16 |    6 |    0 |    2 |    5 |    1 |    1 |   34 |
| **Jacquetta** | TC Sump Runners   | UBBL Challenge III |    1 |   43 |   14 |     68 |    1 |    1 |    2 |    4 |    1 |    2 |   33 |
| Maura    | TC Sump Runners   | UBBL Challenge III |    9 |   92 |    1 |      9 |    9 |    0 |    0 |   17 |    2 |    0 |   28 |
| **Nkosana**   | Mules             | UBBL Challenge III |    6 |   79 |    0 |      0 |    2 |    0 |    0 |    3 |    0 |    1 |   23 |
| Hartwin  | Arboreal Menace   | UBBL Challenge III |    0 |   64 |   16 |     57 |    0 |    1 |    1 |    7 |    3 |    0 |   20 |
| **Georgina**  | Arboreal Menace   | UBBL Challenge IV  |    5 |   60 |    0 |      0 |    4 |    2 |    0 |    3 |    0 |    0 |   19 |
| Eberardo | Darkling Spectres | UBBL Challenge II  |    4 |   57 |    1 |      1 |    4 |    0 |    0 |    9 |    0 |    1 |   18 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.round > 15 AND md.f_did = 2 GROUP BY pl.name, pl.f_tname, tours.name ORDER BY SPP DESC LIMIT 10;
```

| Player    | Team            | Season         | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVPs | SPP  |
|-----------|-----------------|----------------|------|------|------|--------|------|------|------|------|------|------|------|
