## top passing careers

| Player       | Team              | Cp   | Attempts | Cp_Pct | CpDist | AvgDist | intcpt_rate | total_touches | Sacked |
|--------|-----------------|-------------------|------|----------|--------|--------|---------|-------------|---------------|
| Elvis       | Old Wyrms         |  156 |      186 | 0.8387 |    716 |  4.5897 |      0.0215 |           211 |      5 |
| Yosif       | Glorious Hounds   |  152 |      169 | 0.8994 |    926 |  6.0921 |      0.0000 |           218 |     10 |
| **Filipa**       | Eldritch Fatality |  122 |      168 | 0.7262 |    400 |  3.2787 |      0.0595 |           192 |     19 |
| **Cleve**        | Badger Claws      |  112 |      145 | 0.7724 |    329 |  2.9375 |      0.0138 |           182 |      1 |
| Besz        | Irregular Cogs    |  101 |      154 | 0.6558 |    199 |  1.9703 |      0.0974 |           200 |     23 |
| Silas       | Filthy Tide       |   99 |      134 | 0.7388 |    290 |  2.9293 |      0.0224 |           192 |      3 |
| **Luanna**       | Cackling Furies   |   92 |      109 | 0.8440 |    336 |  3.6522 |      0.0275 |           146 |      5 |
| Subrahmanya | Zensun Vagabonds  |   91 |      120 | 0.7583 |    459 |  5.0440 |      0.0583 |           156 |      5 |
| **Jacquetta**    | TC Sump Runners   |   80 |      109 | 0.7339 |    251 |  3.1375 |      0.0917 |           142 |      9 |
| ToomsII.     | Darkling Spectres |   79 |      149 | 0.5302 |    225 |  2.8481 |      0.1007 |           207 |      9 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(mx.pass_distance) AS CpDist, sum(mx.pass_distance) / sum(md.cp) AS AvgDist, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS intcpt_rate,	sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(mx.sustained_sacks) AS Sacked FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE md.f_did = 1 GROUP BY pl.name, pl.f_tname ORDER BY sum(md.cp) DESC LIMIT 10;
```

## passing by season

| Player | Team            | Season            | Cp   | Attempts | Cp_Pct | CpDist | AvgDist | intcpt_rate | total_touches | Sacked |
|--------|-----------------|-------------------|------|----------|--------|--------|---------|-------------|---------------|--------|
| Yosif | Glorious Hounds | Green Cup VI      |   24 |       28 | 0.8571 |    129 |  5.3750 |      0.0000 |            41 |      5 |
| Yosif | Glorious Hounds | Green Cup VII     |   40 |       44 | 0.9091 |    249 |  6.2250 |      0.0000 |            60 |      1 |
| Yosif | Glorious Hounds | UBBL Challenge    |   10 |       12 | 0.8333 |     74 |  7.4000 |      0.0000 |            13 |      0 |
| Elvis | Old Wyrms       | UBBL Challenge    |    8 |       11 | 0.7273 |     52 |  6.5000 |      0.1818 |            12 |      0 |
| Yosif | Glorious Hounds | Green Cup VIII    |   43 |       48 | 0.8958 |    305 |  7.0930 |      0.0000 |            52 |      2 |
| Elvis | Old Wyrms       | Green Cup VIII    |   37 |       44 | 0.8409 |    164 |  4.4324 |      0.0227 |            53 |      1 |
| Yosif | Glorious Hounds | Green Cup IX      |   42 |       45 | 0.9333 |    232 |  5.5238 |      0.0000 |            58 |      2 |
| Elvis | Old Wyrms       | Green Cup IX      |   64 |       73 | 0.8767 |    302 |  4.7188 |      0.0137 |            74 |      1 |
| Elvis | Old Wyrms       | Green Cup X       |   37 |       47 | 0.7872 |    174 |  4.7027 |      0.0426 |            54 |      1 |
| Yosif | Glorious Hounds | Green Cup X       |    3 |        4 | 0.7500 |     11 |  3.6667 |      0.0000 |             7 |      0 |
| Elvis | Old Wyrms       | Champions Circuit |    0 |        0 |   NULL |      0 |    NULL |        NULL |             0 |      0 |
| Elvis | Old Wyrms       | Green Cup XI      |   18 |       22 | 0.8182 |     76 |  4.2222 |      0.0000 |            30 |      2 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(mx.pass_distance) AS CpDist, sum(mx.pass_distance) / sum(md.cp) AS AvgDist, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS intcpt_rate,	sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(mx.sustained_sacks) AS Sacked FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE (pl.name = "Yosif." OR pl.name = "Elvis.") AND md.f_did = 1 GROUP BY pl.name, pl.f_tname, tours.name ORDER BY tours.tour_id ASC;
```

### match by match

| Player | Team        | Season | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|--------|-------|------|------|------|----------|---------|------|--------|-------|------|------|
| Yosif. | Glorious Hounds | Green Cup VI      |     1 |    0 |    2 |    3 |    11 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VI      |     2 |    0 |   18 |    3 |    12 |    0 |    0 |    0 |    2 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VI      |     3 |    0 |    3 |    1 |     3 |    1 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VI      |     4 |    0 |    5 |    1 |     6 |    1 |    0 |    0 |    1 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VI      |     5 |    0 |    2 |    2 |     2 |    0 |    0 |    0 |    2 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VI      |     6 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Yosif. | Glorious Hounds | Green Cup VI      |     7 |    0 |   14 |    1 |     9 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VI      |     8 |    0 |   11 |    1 |     9 |    1 |    0 |    0 |    0 |    0 |    1 |    6 |
| Yosif. | Glorious Hounds | Green Cup VI      |     9 |    0 |   18 |    3 |    19 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VI      |    10 |    0 |   13 |    3 |    15 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VI      |    11 |    0 |    5 |    1 |     6 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VI      |    12 |    0 |   -2 |    1 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VI      |    13 |    0 |   11 |    3 |    25 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VI      |    14 |    0 |   -1 |    1 |    12 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VI      |   252 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Yosif. | Glorious Hounds | Green Cup VII     |     1 |    0 |   10 |    2 |    14 |    0 |    0 |    0 |    2 |    1 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VII     |     2 |    0 |    1 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Yosif. | Glorious Hounds | Green Cup VII     |     3 |    0 |   11 |    1 |     6 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VII     |     4 |    0 |   17 |    4 |    28 |    1 |    0 |    0 |    0 |    0 |    1 |    9 |
| Yosif. | Glorious Hounds | Green Cup VII     |     5 |    0 |    4 |    2 |     8 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VII     |     6 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Yosif. | Glorious Hounds | Green Cup VII     |     7 |    0 |    7 |    4 |    25 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Yosif. | Glorious Hounds | Green Cup VII     |     8 |    0 |   12 |    5 |    15 |    0 |    0 |    0 |    1 |    0 |    0 |    5 |
| Yosif. | Glorious Hounds | Green Cup VII     |     9 |    0 |    7 |    3 |    14 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VII     |    10 |    0 |    7 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Yosif. | Glorious Hounds | Green Cup VII     |    11 |    0 |    8 |    1 |    10 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VII     |    12 |    0 |    9 |    2 |    17 |    1 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VII     |    13 |    0 |    3 |    2 |    13 |    0 |    0 |    0 |    1 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VII     |    14 |    0 |    9 |    3 |    25 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VII     |    15 |    1 |   13 |    2 |    13 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Yosif. | Glorious Hounds | Green Cup VII     |   251 |    0 |   19 |    4 |    32 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Yosif. | Glorious Hounds | Green Cup VII     |   252 |    0 |   10 |    5 |    29 |    0 |    0 |    0 |    1 |    0 |    0 |    5 |
| Yosif. | Glorious Hounds | UBBL Challenge    |     2 |    0 |    7 |    2 |    17 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | UBBL Challenge    |     2 |    1 |   25 |    0 |     0 |    1 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | UBBL Challenge    |     3 |    0 |    5 |    3 |    15 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | UBBL Challenge    |     3 |    0 |    0 |    2 |    13 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | UBBL Challenge    |     4 |    0 |   11 |    2 |    19 |    1 |    0 |    0 |    1 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | UBBL Challenge    |   251 |    0 |    9 |    2 |    11 |    0 |    0 |    0 |    2 |    0 |    1 |    7 |
| Yosif. | Glorious Hounds | UBBL Challenge    |   251 |    0 |   22 |    4 |    25 |    1 |    1 |    0 |    0 |    0 |    0 |    6 |
| Elvis. | Old Wyrms       | UBBL Challenge    |   252 |    0 |   10 |    3 |    26 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     1 |    0 |    9 |    4 |    30 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     2 |    0 |    5 |    1 |     1 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     3 |    0 |    2 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     3 |    0 |   10 |    4 |    28 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     4 |    0 |    0 |    2 |    10 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     5 |    0 |   10 |    3 |    18 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     5 |    0 |   11 |    3 |    23 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     6 |    0 |    9 |    2 |    18 |    0 |    0 |    0 |    1 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     6 |    0 |    6 |    2 |     8 |    0 |    0 |    0 |    1 |    0 |    1 |    7 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     7 |    0 |    7 |    5 |    17 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     8 |    0 |   21 |    5 |    28 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     8 |    0 |    5 |    7 |    34 |    0 |    0 |    0 |    0 |    0 |    1 |   12 |
| Elvis. | Old Wyrms       | Green Cup VIII    |     9 |    0 |    7 |    3 |    18 |    1 |    0 |    0 |    1 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VIII    |     9 |    0 |    2 |    2 |    21 |    1 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup VIII    |    10 |    0 |    4 |    3 |     7 |    0 |    0 |    0 |    0 |    0 |    1 |    8 |
| Elvis. | Old Wyrms       | Green Cup VIII    |    11 |    0 |    9 |    1 |     3 |    1 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup VIII    |    11 |    0 |   14 |    3 |    19 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup VIII    |    12 |    0 |    5 |    2 |    12 |    0 |    0 |    0 |    3 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VIII    |    12 |    0 |   10 |    3 |    28 |    0 |    1 |    0 |    1 |    0 |    0 |    5 |
| Yosif. | Glorious Hounds | Green Cup VIII    |    13 |    0 |   26 |    8 |    56 |    0 |    0 |    0 |    0 |    0 |    0 |    8 |
| Elvis. | Old Wyrms       | Green Cup VIII    |    13 |    0 |    4 |    2 |     3 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VIII    |    14 |    0 |    7 |    5 |    32 |    0 |    0 |    0 |    1 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup VIII    |    14 |    0 |   13 |    3 |    11 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VIII    |    15 |    0 |    5 |    1 |     4 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup VIII    |    15 |    0 |   14 |    3 |    22 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup VIII    |   251 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Elvis. | Old Wyrms       | Green Cup VIII    |   251 |    0 |    7 |    2 |     5 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup VIII    |   252 |    0 |    5 |    1 |    13 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup IX      |     1 |    0 |   10 |    2 |    18 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup IX      |     1 |    0 |   13 |    3 |    10 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup IX      |     2 |    0 |    0 |    2 |     7 |    0 |    0 |    0 |    1 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup IX      |     2 |    0 |    4 |    1 |     1 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup IX      |     3 |    0 |    8 |    4 |    18 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Elvis. | Old Wyrms       | Green Cup IX      |     3 |    0 |   10 |    3 |    12 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup IX      |     4 |    0 |    4 |    5 |    20 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup IX      |     4 |    0 |   20 |    5 |    30 |    0 |    0 |    0 |    2 |    2 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup IX      |     5 |    0 |    2 |    1 |     5 |    0 |    0 |    0 |    3 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup IX      |     5 |    0 |    1 |    3 |    11 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup IX      |     6 |    0 |   14 |    3 |    26 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup IX      |     6 |    0 |    6 |    2 |    11 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup IX      |     7 |    0 |    9 |    4 |     3 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Yosif. | Glorious Hounds | Green Cup IX      |     7 |    0 |    4 |    1 |     3 |    0 |    0 |    0 |    2 |    1 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup IX      |     8 |    0 |    9 |    5 |    34 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup IX      |     8 |    0 |    2 |    4 |    17 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Yosif. | Glorious Hounds | Green Cup IX      |     9 |    0 |    7 |    2 |    23 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup IX      |     9 |    0 |   15 |    5 |    24 |    0 |    0 |    0 |    0 |    0 |    1 |   10 |
| Elvis. | Old Wyrms       | Green Cup IX      |    10 |    0 |    8 |    5 |    23 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup IX      |    11 |    0 |   14 |    4 |    30 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Yosif. | Glorious Hounds | Green Cup IX      |    11 |    0 |    1 |    3 |    10 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup IX      |    12 |    0 |   10 |    3 |    23 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup IX      |    12 |    0 |   14 |    3 |    13 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup IX      |    13 |    0 |   13 |    6 |    31 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Yosif. | Glorious Hounds | Green Cup IX      |    13 |    0 |    1 |    1 |     3 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup IX      |    14 |    0 |    8 |    2 |     8 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup IX      |    14 |    0 |    0 |    1 |     3 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup IX      |    15 |    0 |    9 |    2 |     9 |    0 |    0 |    0 |    1 |    0 |    0 |    2 |
| Yosif. | Glorious Hounds | Green Cup IX      |   251 |    0 |    8 |    3 |    22 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup IX      |   252 |    0 |    7 |    3 |    15 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Yosif. | Glorious Hounds | Green Cup IX      |   252 |    0 |    4 |    1 |     3 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup IX      |   253 |    0 |   17 |    7 |    30 |    0 |    0 |    0 |    1 |    0 |    0 |    7 |
| Yosif. | Glorious Hounds | Green Cup IX      |   253 |    0 |    9 |    3 |    20 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup IX      |   255 |    0 |    9 |    4 |    18 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Elvis. | Old Wyrms       | Green Cup X       |     1 |    0 |    3 |    3 |     3 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup X       |     2 |    0 |    6 |    1 |     0 |    1 |    0 |    0 |    2 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup X       |     3 |    0 |    4 |    2 |     7 |    0 |    0 |    0 |    2 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup X       |     4 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |
| Elvis. | Old Wyrms       | Green Cup X       |     5 |    0 |    8 |    4 |    19 |    0 |    0 |    0 |    3 |    0 |    0 |    4 |
| Elvis. | Old Wyrms       | Green Cup X       |     6 |    0 |    9 |    1 |     5 |    0 |    0 |    0 |    2 |    1 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup X       |     7 |    0 |    6 |    1 |     6 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup X       |     8 |    0 |    6 |    3 |    16 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup X       |     9 |    0 |    5 |    1 |     4 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup X       |    10 |    0 |   10 |    4 |    28 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Elvis. | Old Wyrms       | Green Cup X       |    11 |    0 |    7 |    1 |     4 |    0 |    0 |    0 |    1 |    1 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup X       |    12 |    0 |    6 |    1 |    10 |    0 |    0 |    0 |    2 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup X       |    13 |    0 |   13 |    3 |    11 |    0 |    0 |    0 |    2 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup X       |    13 |    0 |    9 |    3 |    21 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup X       |    14 |    0 |    2 |    1 |     2 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Yosif. | Glorious Hounds | Green Cup X       |    15 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |
| Elvis. | Old Wyrms       | Green Cup X       |    15 |    0 |    5 |    5 |    17 |    0 |    0 |    0 |    1 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup X       |   251 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    2 |   10 |
| Elvis. | Old Wyrms       | Green Cup X       |   252 |    0 |   16 |    3 |    22 |    0 |    0 |    1 |    1 |    0 |    0 |    5 |
| Elvis. | Old Wyrms       | Green Cup X       |   253 |    0 |    5 |    1 |     1 |    0 |    0 |    0 |    0 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup X       |   255 |    0 |    7 |    2 |     9 |    0 |    0 |    0 |    1 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Champions Circuit |     1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Elvis. | Old Wyrms       | Green Cup XI      |     1 |    0 |    7 |    2 |     8 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup XI      |     2 |    0 |   20 |    3 |     4 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Elvis. | Old Wyrms       | Green Cup XI      |     3 |    0 |    6 |    0 |     0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |
| Elvis. | Old Wyrms       | Green Cup XI      |     4 |    0 |    9 |    2 |     7 |    1 |    0 |    0 |    0 |    0 |    0 |    2 |
| Elvis. | Old Wyrms       | Green Cup XI      |     5 |    0 |   17 |    6 |    27 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Elvis. | Old Wyrms       | Green Cup XI      |     6 |    0 |    0 |    1 |     7 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |
| Elvis. | Old Wyrms       | Green Cup XI      |     7 |    0 |   18 |    4 |    23 |    0 |    0 |    0 |    1 |    0 |    0 |    4 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE (pl.name = "Yosif." OR pl.name = "Elvis.") GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY pl.name, mt.match_id ASC;
```
