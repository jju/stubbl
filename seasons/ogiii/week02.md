# week 02

#t2779

## matchups

 Not a lot of movement in the standings, but the good teams from OGII are still looking like good teams.


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
| Marques  | Gladiolas        |    3 |   36 |    0 |      0 |    4 |    0 |    0 |    0 |    0 |    0 |    9 |
| Krister  | Deep Dreamers    |    2 |   17 |    0 |      0 |    2 |    1 |    0 |    0 |    0 |    0 |    8 |
| Juozas   | Gladiolas        |    1 |   14 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    1 |    8 |
| Madalin  | Raptors          |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    4 |    0 |    1 |    7 |
| Baz      | Vanadium Hunters |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    5 |    1 |    1 |    7 |
| Pilvi    | Mules            |    2 |   21 |    0 |      0 |    0 |    0 |    0 |    3 |    0 |    0 |    6 |
| Jolanda  | Magpies          |    2 |   20 |    0 |      0 |    2 |    0 |    0 |    2 |    0 |    0 |    6 |
| Freja    | Raptors          |    1 |    5 |    0 |      0 |    0 |    1 |    0 |    1 |    0 |    0 |    5 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 2 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
