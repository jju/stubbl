Offence Value Points (oVP) are a newer way to assign "value" to players based on what they have done on the BludBol pitch. Combined with Defence Value Points [[dVP]] they make Total Value Points [[tVP]]. 

* [[TD]] = 1 oVP
* [[Cp]] = 1 oVP
* Catch = 1 oVP
* Rush/10 = 1 oVP
* PassDist/10 = 1 oVP

# UBBL tVP Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player  | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVP   |
|---------|-------------------|------|------|------|--------|------|------|------|------|------|-------|------|-------|
| [[Ekua]]      | Ravenous Eagles   |    9 |   75 |    0 |      0 |    2 |    1 |   43 |  687 |   30 | 18.5 | 212.4 | 230.9 |
| [[Somfuhr]]   | Filthy Tide       |    0 |    8 |    0 |      0 |    0 |    0 |   61 |  557 |   15 |  0.8 | 187.4 | 188.2 |
| [[Marzhak]]   | Gargantuan Brutes |    0 |    0 |    0 |      0 |    0 |    1 |   55 |  550 |   20 |  0.0 | 187.0 | 187.0 |
| **[[Deepali]]**    | Kaiju Dynamo      |    1 |    5 |    0 |      0 |    0 |    1 |   21 |  686 |   19 |  1.5 | 179.2 | 180.7 |
| [[Jantine]]   | Ravenous Eagles   |    0 |   16 |    0 |      0 |    0 |    1 |   63 |  518 |    6 |  1.6 | 174.6 | 176.2 |
| [[Sophronia]] | Cackling Furies   |    0 |    6 |    0 |      0 |    0 |    1 |   23 |  682 |   12 |  0.6 | 173.4 | 174.0 |
| **[[Percy]]**      | Ravenous Eagles   |    1 |    8 |    0 |      0 |    0 |    1 |   46 |  529 |    8 |  1.8 | 161.8 | 163.6 |
| **[[Uli]]**        | Orbital Machine   |    0 |    0 |    0 |      0 |    0 |    0 |   47 |  522 |    8 |  0.0 | 159.4 | 159.4 |
| [[Rohit]]     | Zensun Vagabonds  |    7 |   69 |    1 |      5 |    5 |    1 |   52 |  417 |   17 | 20.4 | 154.4 | 174.8 |
| **[[Florinda]]**   | Glorious Hounds   |    4 |   46 |    4 |     24 |    6 |    3 |   17 |  499 |   17 | 21.0 | 139.8 | 160.8 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY dVP DESC LIMIT 10;
```