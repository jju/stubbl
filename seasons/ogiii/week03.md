# week 03

#t2780

## matchups

 


## standings

| Team | W-D-L |
|-------|-----|
| Gladiolas | 2-0-0 |
| Mules | 2-0-0 |
| Raptors | 2-0-0 |
| Magpies | 1-1-0 |
| Thrillers | 1-0-1 |
| Deep Dreamers | 0-1-1 |
| Umber Hulks | 0-1-1 |
| Vanadium Hunters | 0-1-1 |
| Warthogs | 0-0-1 |
| Geometers | 0-0-2 |
| Hoods | 0-0-1 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 3 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
