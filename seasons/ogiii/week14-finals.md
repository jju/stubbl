# orange goblet iii championship

#t2791

## matchups

The Mules faced the Deep Dreamers and won with another excellent defensive demonstration. Two of the Dreamers' biggest stars had their careers ended in the brutal match.

## standings

| Team | W-D-L |
|-------|-----|
| **Mules** | 11-1-1 |
| *Raptors* | 9-1-2 |
| *Gladiolas* | 8-1-2 |
| *Deep Dreamers* | 8-1-3 |
| *Magpies* | 5-2-4 |
| *Hoods* | 5-0-6 |
| *Warthogs* | 3-2-6 |
| *Vanadium Hunters* | 3-2-7 |
| *Geometers* | 1-2-7 |
| *Thrillers* | 1-1-8 |
| *Umber Hulks* | 1-1-8 |


## player of the week standings

| Player   | Team          | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|----------|---------------|------|------|------|--------|------|-----|---|--------|-------|------|------|
| Aygul    | Mules         |    0 |    0 |    0 |      0 |    0 |   0 |    1 |    5 |    0 |    1 |    7 |
| Gijsbert | Deep Dreamers |    0 |    0 |    0 |      0 |    0 |   0 |    0 |    1 |    0 |    1 |    5 |
| Pilvi    | Mules         |    1 |   24 |    0 |      0 |    0 |   0 |    1 |    0 |    0 |    0 |    5 |
| Marita   | Deep Dreamers |    1 |   13 |    0 |      0 |    1 |   0 |    0 |    0 |    0 |    0 |    3 |
| Mawunyo  | Mules         |    1 |    0 |    0 |      0 |    0 |   0 |    0 |    3 |    0 |    0 |    3 |
| Marylu   | Deep Dreamers |    0 |    8 |    2 |      7 |    0 |   0 |    0 |    0 |    0 |    0 |    2 |
| Volker   | Mules         |    0 |    0 |    0 |      0 |    0 |   0 |    1 |    3 |    0 |    0 |    2 |
| Halgurd  | Mules         |    0 |    0 |    0 |      0 |    0 |   0 |    1 |    3 |    0 |    0 |    2 |
| Krister  | Deep Dreamers |    0 |    0 |    0 |      0 |    0 |   0 |    0 |    1 |    0 |    0 |    0 |
| Clement  | Deep Dreamers |    0 |    0 |    0 |      0 |    0 |   0 |    0 |    3 |    0 |    0 |    0 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 255 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
