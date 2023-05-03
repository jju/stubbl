Total Value Points (tVP) are a newer way to assign "value" to players based on what they have done on the BludBol pitch. They are made up of two parts: Offence Value Points [[oVP]] and Defence Value Points [[dVP]].

These points are meant to scale with [[SPP]].

# UBBL tVP Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player  | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVP   |
|---------|-------------------|------|------|------|--------|------|------|------|------|------|-------|------|-------|
| [[Aeson]]  | Badger Claws      |  174 | 2280 |    3 |      3 |  145 |    0 |    0 |    7 |    0 | 550.3 |  1.4 | 551.7 |
| [[Souta]]  | Old Wyrms         |   72 |  923 |   51 |      5 |  132 |    3 |    3 |  113 |    9 | 347.8 | 40.6 | 388.4 |
| **[[Filipa]]**  | Eldritch Fatality |    9 |  939 |  163 |    544 |   11 |    3 |    1 |   39 |    2 | 331.3 | 16.8 | 348.1 |
| [[Besz]]   | Irregular Cogs    |   23 | 1257 |  110 |    204 |   44 |    0 |    1 |   57 |    0 | 323.1 | 12.4 | 335.5 |
| [[Yosif]]  | Glorious Hounds   |    1 |  522 |  162 |   1000 |    8 |    2 |    0 |   24 |    2 | 323.2 | 10.8 | 334.0 |
| **[[Veens]]**   | Filthy Tide       |  106 | 1274 |    1 |      3 |   80 |    0 |    0 |    3 |    1 | 314.7 |  1.6 | 316.3 |
| [[Elvis]]  | Old Wyrms         |    1 |  514 |  164 |    768 |    6 |    0 |    1 |   40 |    4 | 299.2 | 13.0 | 312.2 |
| **[[Ziba]]**    | Glorious Hounds   |   90 | 1028 |    3 |      2 |   86 |    2 |    1 |   18 |    1 | 282.0 |  9.6 | 291.6 |
| [[Luanna]] | Cackling Furies   |    8 |  546 |  134 |    497 |    8 |    1 |    4 |   54 |    1 | 254.3 | 17.8 | 272.1 |
| **[[Amador]]**  | Old Wyrms         |   32 |  607 |   44 |     10 |   84 |    2 |    2 |  137 |    9 | 221.7 | 42.4 | 264.1 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY tVP DESC LIMIT 10;
```