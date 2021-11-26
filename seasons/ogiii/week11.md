# week 11

#t2788

## matchups


## standings

| Team | W-D-L |
|-------|-----|
| Gladiolas | 8-1-1 |
| Mules | 8-1-1 |
| Raptors | 8-1-1 |
| Deep Dreamers | 6-1-3 |
| Magpies | 5-2-3 |
| Hoods | 5-0-5 |
| Warthogs | 3-2-5 |
| Vanadium Hunters | 2-2-6 |
| Geometers | 1-2-7 |
| Thrillers | 1-1-8 |
| Umber Hulks | 1-1-8 |


## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Marita     | Deep Dreamers    |    3 |   49 |    1 |      1 |    2 |    1 |    0 |    0 |    0 |    0 |   12 |
| Aygul      | Mules            |    0 |    0 |    0 |      0 |    0 |    0 |    2 |    9 |    0 |    1 |    9 |
| Taymuraz   | Raptors          |    3 |   42 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    9 |
| Kassandros | Magpies          |    3 |   24 |    0 |      0 |    3 |    0 |    0 |    1 |    0 |    0 |    9 |
| Marques    | Gladiolas        |    2 |   20 |    0 |      0 |    1 |    1 |    0 |    4 |    1 |    0 |    8 |
| Tonje      | Warthogs         |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    8 |    0 |    1 |    7 |
| Miki       | Raptors          |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    9 |    0 |    1 |    7 |
| Gijsbert   | Deep Dreamers    |    2 |    0 |    0 |      0 |    2 |    0 |    0 |    1 |    0 |    0 |    6 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 11 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
