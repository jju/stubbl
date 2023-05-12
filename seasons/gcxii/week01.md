# week 01

[Previously in the preseason](seasons/gcxii/preseason.md) #t2814
[next week](week02)

* business storyline DS-GF [[aficionado]]
* player storyline FT-AR [[aficionado]] or RE-ZV [[aficionado]] or BC-EF (dud bc Aeson does sit it out) [[writer]] or OW-CF [[warreporter]]
* team GH-CT (how do the Hounds do coming off a tournament win?) [[writer]] OM-SR (no fans vs bad team) [[warreporter]] KD-IC [[aficionado]] (interesting tactical choices)


## matchups

* Kicking Mules - Arboreal Menace #t2815.1
* Ravenous Eagles - Virtua Raptors #t2815.2
* Palace Orchids - Gore Farmers  #t2815.3
* Xeno Thrillers - Glorious Hounds #t2815.4
* Eldritch Fatality - Old Wyrms #t2815.7
* Vanadium Hunters - Kaiju Dynamo #t2815.8
* Irregular Cogs - Zensun Vagabonds #t2815.9


## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 0-0-0 | Irregular Cogs | 0-0-0 | Orbital Machine | 0-0-0 | Eldritch Fatality | 0-0-0 |
| Gore Farmers | 0-0-0 | Carcosan Tatters | 0-0-0 | Glorious Hounds | 0-0-0 | Ravenous Eagles | 0-0-0 |
| Old Wyrms | 0-0-0 | Arboreal Menace | 0-0-0 | Kaiju Dynamo | 0-0-0 | Cackling Furies | 0-0-0 |
| Vanadium Hunters | 0-0-0 | Badger Claws | 0-0-0 | Zensun Vagabonds | 0-0-0 | Darkling Spectres | 0-0-0 |
| Virtua Raptors | 0-0-0 | Xeno Thrillers | 0-0-0 | Kicking Mules | 0-0-0 | Palace Orchids | 0-0-0 |

## player of the week standings

| Player  | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP  | dVP  | tVP  | MVPs | SPP  |
|---------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS tVP, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XII" AND mt.round = 1 GROUP BY pl.name, pl.f_tname ORDER BY tVP DESC LIMIT 5;
```