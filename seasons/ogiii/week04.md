# week 04

#t2781

## matchups

 The Raptors continued their winning streak now putting them in a tie for the second-longest in UBBL history.

## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 4-0-0 |
| Magpies | 3-1-0 |
| Mules | 3-1-0 |
| Gladiolas | 2-1-0 |
| Deep Dreamers | 1-1-2 |
| Geometers | 1-1-2 |
| Thrillers | 1-1-2 |
| Hoods | 1-0-2 |
| Umber Hulks | 0-1-3 |
| Vanadium Hunters | 0-1-2 |
| Warthogs | 0-0-3 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Eleonora | Warthogs      |    2 |   14 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    1 |   11 |
| Zena     | Deep Dreamers |    3 |    6 |    0 |      0 |    1 |    0 |    0 |    5 |    0 |    0 |    9 |
| Mallt    | Hoods         |    0 |    2 |    0 |      0 |    0 |    0 |    1 |    6 |    1 |    1 |    7 |
| Renat    | Umber Hulks   |    0 |    3 |    0 |      0 |    0 |    1 |    0 |    1 |    0 |    1 |    7 |
| Hiro     | Raptors       |    2 |   23 |    0 |      0 |    1 |    0 |    0 |    1 |    0 |    0 |    6 |
| Katka    | Hoods         |    0 |    0 |    0 |      0 |    0 |    0 |    3 |   13 |    1 |    0 |    6 |
| Jolanda  | Magpies       |    2 |   15 |    0 |      0 |    2 |    0 |    0 |    4 |    0 |    0 |    6 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 4 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
