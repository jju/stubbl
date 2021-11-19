# week 10

#t2787

## matchups

The Raptors' long winning streak finally came to an end against the Gladiolas. There's at least a slight sense of relief among Raptor fans since perfection on the season has already been lost.

## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 8-0-1 |
| Gladiolas | 7-1-1 |
| Mules | 7-1-1 |
| Magpies | 5-1-3 |
| Deep Dreamers | 5-1-3 |
| Hoods | 5-0-4 |
| Warthogs | 3-2-4 |
| Vanadium Hunters | 2-2-5 |
| Geometers | 1-2-6 |
| Thrillers | 1-1-8 |
| Umber Hulks | 0-1-8 |


## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Marques  | Gladiolas     |    1 |   29 |    0 |      0 |    3 |    0 |    0 |    2 |    1 |    1 |    8 |
| Krister  | Deep Dreamers |    1 |    2 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    1 |    8 |
| Miki     | Raptors       |    0 |    8 |    0 |      0 |    0 |    0 |    1 |    9 |    0 |    1 |    7 |
| Hursit   | Warthogs      |    1 |   23 |    4 |     13 |    0 |    0 |    0 |    1 |    0 |    0 |    7 |
| Eufemia  | Gladiolas     |    0 |    9 |    5 |     11 |    0 |    0 |    0 |    1 |    0 |    0 |    5 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 10 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
