# week 03

#t2780

## matchups

 The matches this week ensured a little bit of separation. The Magpies are following the Raptors' example of being very good in their first taste of big(ger) league play.


## standings

| Team | W-D-L |
|-------|-----|
| Mules | 3-0-0 |
| Raptors | 3-0-0 |
| Magpies | 2-1-0 |
| Gladiolas | 2-0-0 |
| Geometers | 1-0-2 |
| Thrillers | 1-0-2 |
| Hoods | 1-0-1 |
| Deep Dreamers | 0-1-2 |
| Umber Hulks | 0-1-2 |
| Vanadium Hunters | 0-1-2 |
| Warthogs | 0-0-2 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Freja    | Raptors          |    3 |   39 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    9 |
| Syeda    | Magpies          |    1 |   13 |    0 |      0 |    1 |    0 |    0 |    1 |    0 |    1 |    8 |
| Waltraut | Raptors          |    1 |    6 |    0 |      0 |    0 |    0 |    0 |    1 |    0 |    1 |    8 |
| Emmet    | Warthogs         |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    6 |    0 |    1 |    7 |
| Zahida   | Vanadium Hunters |    0 |   13 |    2 |      5 |    0 |    0 |    0 |    0 |    0 |    1 |    7 |
| Ahmad    | Umber Hulks      |    0 |    1 |    0 |      0 |    0 |    1 |    0 |    3 |    0 |    1 |    7 |
| Adedayo  | Hoods            |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    4 |    1 |    1 |    7 |
| Shankte  | Geometers        |    2 |   19 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    6 |
| Umut     | Mules            |    2 |   23 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    6 |
| Ragu     | Warthogs         |    2 |   25 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    6 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 3 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
