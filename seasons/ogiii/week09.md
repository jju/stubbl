# week 09

#t2786

## matchups

 The Raptors broke the UBBL win streak record with their 13th straight win. The Thrillers and Umber Hulks have been eliminated from playoff contention, leaving the Geometers Hunters and Warthogs in the mix for two playoff spots.

## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 8-0-0 |
| Gladiolas | 6-1-1 |
| Mules | 6-1-1 |
| Magpies | 5-1-2 |
| Deep Dreamers | 4-1-3 |
| Hoods | 4-0-4 |
| Warthogs | 2-2-4 |
| Vanadium Hunters | 2-2-4 |
| Geometers | 1-2-5 |
| Thrillers | 1-1-7 |
| Umber Hulks | 0-1-8 |


## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Debbie   | Hoods            |    1 |   19 |    1 |      3 |    0 |    1 |    0 |    2 |    0 |    0 |    6 |
| Syeda    | Magpies          |    1 |   23 |    3 |      4 |    1 |    0 |    0 |    1 |    0 |    0 |    6 |
| Taymuraz | Raptors          |    2 |   20 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Borgisl  | Gladiolas        |    2 |   22 |    0 |      0 |    3 |    0 |    0 |    1 |    0 |    0 |    6 |
| Calfuray | Magpies          |    1 |    5 |    2 |      1 |    2 |    0 |    0 |    0 |    0 |    0 |    5 |
| Hursit   | Warthogs         |    1 |   29 |    2 |     12 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 9 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
