# week 06

#t2783

## matchups

 The Raptors got their 11th straight win in their OGII rematch against the Mules. They get a rest in Week 7 but even so their position atop the standings is safe.

## standings

| Team | W-D-L |
|-------|-----|
| Raptors | 6-0-0 |
| Magpies | 4-1-0 |
| Mules | 4-1-1 |
| Gladiolas | 3-1-1 |
| Deep Dreamers | 3-1-2 |
| Hoods | 2-0-3 |
| Geometers | 1-2-2 |
| Thrillers | 1-1-4 |
| Vanadium Hunters | 1-1-3 |
| Warthogs | 0-1-4 |
| Umber Hulks | 0-1-5 |


## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Marita     | Deep Dreamers    |    2 |   27 |    0 |      0 |    2 |    0 |    0 |    1 |    0 |    1 |   11 |
| Borgisl    | Gladiolas        |    2 |   21 |    0 |      0 |    2 |    0 |    0 |    2 |    0 |    1 |   11 |
| Umut       | Mules            |    1 |   18 |    1 |      4 |    1 |    0 |    0 |    2 |    0 |    1 |    9 |
| Kassandros | Magpies          |    1 |   14 |    0 |      0 |    2 |    0 |    0 |    2 |    0 |    1 |    8 |
| Sadhbh     | Hoods            |    0 |    7 |    2 |     21 |    0 |    0 |    0 |    0 |    0 |    1 |    7 |
| Heinrich   | Warthogs         |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    7 |    0 |    1 |    5 |
| Zhen       | Vanadium Hunters |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    6 |    0 |    1 |    5 |
| Brittany   | Thrillers        |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    5 |    0 |    1 |    5 |
| Ampner     | Umber Hulks      |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    2 |    0 |    1 |    5 |
| Sampo      | Raptors          |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    7 |    0 |    1 |    5 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 6 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
