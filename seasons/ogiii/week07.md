# week 07

#t2784

## matchups

 The Raptors get a rest in Week 7 before trying to tie the UBBL win streak record, but even so their position atop the standings is safe another week and they have clinched their playoff spot.

## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 6-0-0 |
| Mules | 5-1-1 |
| Gladiolas | 4-1-1 |
| Deep Dreamers | 4-1-2 |
| Magpies | 4-1-1 |
| Hoods | 3-0-3 |
| Geometers | 1-2-3 |
| Warthogs | 1-1-4 |
| Thrillers | 1-1-5 |
| Vanadium Hunters | 1-1-4 |
| Umber Hulks | 0-1-6 |


## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Krister      | Deep Dreamers |    2 |   35 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    1 |   11 |
| Marita       | Deep Dreamers |    2 |   14 |    1 |     -3 |    1 |    1 |    0 |    0 |    0 |    0 |    9 |
| Aygul        | Mules         |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    5 |    0 |    1 |    7 |
| Kassandros   | Magpies       |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    4 |    0 |    1 |    7 |
| Mawunyo      | Mules         |    2 |   17 |    0 |      0 |    0 |    0 |    0 |    4 |    0 |    0 |    6 |
| Jolanda      | Magpies       |    2 |   28 |    0 |      0 |    2 |    0 |    0 |    3 |    0 |    0 |    6 |
| Mathghamhain | Geometers     |    0 |   23 |    1 |      1 |    1 |    0 |    0 |    0 |    0 |    1 |    6 |
| Hursit       | Warthogs      |    2 |   31 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Marques      | Gladiolas     |    2 |   16 |    0 |      0 |    2 |    0 |    0 |    1 |    0 |    0 |    6 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 7 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
