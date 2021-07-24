# week 02

#t2779

## matchups

 


## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 1-0-0 |
| Mules | 1-0-0 |
| Magpies | 1-0-0 |
| Thrillers | 1-0-0 |
| Gladiolas | 1-0-0 |
| Deep Dreamers | 0-0-1 |
| Umber Hulks | 0-0-1 |
| Geometers | 0-0-1 |
| Warthogs | 0-0-1 |
| Vanadium Hunters | 0-0-1 |
| Hoods | 0-0-0 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Karpos  | Gladiolas     |    1 |   12 |    0 |      0 |    0 |    1 |    0 |    8 |    0 |    1 |   10 |
| Lasse   | Mules         |    0 |    0 |    0 |      0 |    0 |    0 |    2 |    7 |    0 |    1 |    9 |
| Hiro    | Raptors       |    3 |   26 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    0 |    9 |
| Marques | Gladiolas     |    2 |   19 |    0 |      0 |    3 |    0 |    1 |    0 |    0 |    0 |    8 |
| Mawunyo | Mules         |    2 |   25 |    0 |      0 |    1 |    1 |    0 |    1 |    0 |    0 |    8 |
| Jewel   | Raptors       |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    2 |    1 |    1 |    7 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 2 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
