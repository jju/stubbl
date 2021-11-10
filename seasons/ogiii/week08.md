# week 08

#t2785

## matchups

 The Raptors got to try for the UBBL win streak record and after a shaky first half they managed a suppressive defense and got their record-tying 12th win in a row.

## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 7-0-0 |
| Mules | 6-1-1 |
| Gladiolas | 5-1-1 |
| Deep Dreamers | 4-1-2 |
| Magpies | 4-1-2 |
| Hoods | 3-0-4 |
| Warthogs | 2-1-4 |
| Vanadium Hunters | 2-1-4 |
| Geometers | 1-2-4 |
| Thrillers | 1-1-6 |
| Umber Hulks | 0-1-7 |


## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Kassandros     | Magpies          |    1 |   24 |    0 |      0 |    2 |    0 |    0 |    0 |    0 |    1 |    8 |
| Leifur         | Vanadium Hunters |    0 |    2 |    0 |      0 |    0 |    0 |    1 |    5 |    0 |    1 |    7 |
| Samuhel        | Geometers        |    0 |    0 |    0 |      0 |    0 |    0 |    1 |   11 |    0 |    1 |    7 |
| Kaneonuskateuw | Umber Hulks      |    0 |    6 |    1 |      0 |    0 |    0 |    0 |    1 |    0 |    1 |    6 |
| Marques        | Gladiolas        |    1 |   30 |    1 |     -1 |    2 |    1 |    0 |    4 |    0 |    0 |    6 |
| Zahida         | Vanadium Hunters |    0 |    7 |    3 |      1 |    0 |    0 |    1 |    2 |    1 |    0 |    5 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 8 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
