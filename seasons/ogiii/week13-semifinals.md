# week 13

#t2790

## matchups

The Mules took on the lowly Hunters hoping not to suffer the same ignominous fate as the Gladiolas.

The Raptors lost to the Deep Dreamers, a tough end to a long season, but with their Green Cup expansion berth secured they aren't too down on a third place finish.

## standings

| Team | W-D-L |
|-------|-----|
| Mules | 10-1-1 |
| *Raptors* | 9-1-2 |
| *Gladiolas* | 8-1-2 |
| Deep Dreamers | 8-1-3 |
| *Magpies* | 5-2-4 |
| *Hoods* | 5-0-6 |
| *Warthogs* | 3-2-6 |
| *Vanadium Hunters* | 3-2-7 |
| *Geometers* | 1-2-7 |
| *Thrillers* | 1-1-8 |
| *Umber Hulks* | 1-1-8 |


## player of the week standings

| Player    | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-----------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Krister     | Deep Dreamers    |    2 |   23 |    2 |      8 |    1 |    1 |    0 |    0 |    0 |    0 |   10 |
| Brynja      | Deep Dreamers    |    1 |   20 |    0 |      0 |    2 |    0 |    0 |    1 |    0 |    1 |    8 |
| Amalie      | Mules            |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    6 |    0 |    1 |    7 |
| Bianka      | Mules            |    2 |   36 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Bozena      | Vanadium Hunters |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    1 |    5 |
| Tenskwatawa | Deep Dreamers    |    1 |    2 |    0 |      0 |    0 |    0 |    1 |    4 |    0 |    0 |    5 |
| Lachlan     | Raptors          |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    1 |    0 |    1 |    5 |
| Zena        | Deep Dreamers    |    1 |    0 |    0 |      0 |    1 |    0 |    0 |    1 |    1 |    0 |    3 |
| Waltraut    | Raptors          |    1 |   16 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Farhan      | Vanadium Hunters |    1 |   17 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |    3 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 253 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
