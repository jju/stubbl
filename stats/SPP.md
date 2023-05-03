Star Player Points (SPP) are the traditional "value" assigned to players based on what they have done on the BludBol pitch.

* [[TD]] = 3 SPP
* [[Cp]] = 1 SPP
* [[Int]] = 2 SPP
* [[Cas]] = 2 SPP
* [[stats/MVP]] = 5 SPP

Players who have achieved certain numbers of SPP are ranked (and get increased salaries).

* 00 SPP = [[rookie]]
* 06 SPP = [[experienced]]
* 16 SPP = [[veteran]]
* 31 SPP = [[emergingstar]] / [[seasonedveteran]]
* 51 SPP = [[star]]
* 76 SPP = [[superstar]]
* 176 SPP = [[legend]]

# UBBL SPP Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| [[Aeson]]    | Badger Claws      |  174 | 2280 |    3 |      3 |  145 |    0 |    0 |    7 |    0 |   10 |  575 |
| **[[Veens]]**     | Filthy Tide       |  106 | 1274 |    1 |      3 |   80 |    0 |    0 |    3 |    1 |    5 |  344 |
| **[[Ziba]]**      | Glorious Hounds   |   90 | 1028 |    3 |      2 |   86 |    2 |    1 |   18 |    1 |    7 |  314 |
| [[Souta]]    | Old Wyrms         |   72 |  923 |   51 |      5 |  132 |    3 |    3 |  113 |    9 |    4 |  299 |
| [[Costache]] | Glorious Hounds   |   76 |  640 |    3 |     -2 |   73 |    2 |    4 |   95 |    6 |    3 |  258 |
| [[Yakup]]    | Filthy Tide       |   73 |  986 |    1 |      1 |   67 |    0 |    1 |   23 |    2 |    4 |  242 |
| **[[Filipa]]**    | Eldritch Fatality |    9 |  939 |  163 |    544 |   11 |    3 |    1 |   39 |    2 |    5 |  223 |
| [[Sabah]]    | Kaiju Dynamo      |   66 |  856 |    2 |      4 |   33 |    0 |    0 |    7 |    0 |    3 |  215 |
| [[Besz]]     | Irregular Cogs    |   23 | 1257 |  110 |    204 |   44 |    0 |    1 |   57 |    0 |    5 |  206 |
| [[Elvis]]    | Old Wyrms         |    1 |  514 |  164 |    768 |    6 |    0 |    1 |   40 |    4 |    7 |  204 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```