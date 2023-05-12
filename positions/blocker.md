Blockers are not the stars of BludBol. They bash, they take massive numbers of hits and provide almost all of their value in defense. Basically they're [[line]] players who are tougher and stronger and harder to move. Don't count on them to score or provide any offensive value whatsoever.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Blocker   |     107 |  3368 |   31 |  494 |    6 |     29 |   13 |   38 |  640 | 17630 |  202 | 102.3 | 4444.0 | 1.34985 | 42.48879 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blocker", "Nurgle Warrior", "Chaos Warrior", "Saurus", "Flesh Golem", "Chaos Dwarf Blocker", "Mummy", "Tomb Guardian");
```
## position hall of fame

| Player     | Team             | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVPG    | tVP   |
|------------|------------------|-------|------|------|------|--------|------|------|------|------|------|-------|------|---------|-------|
| **[[Deepali]]**  | Kaiju Dynamo      |    75 |    1 |    5 |    0 |      0 |    0 |    1 |   21 |  686 |   19 |  1.5 | 179.2 | 2.40933 | 180.7 |
| **[[Haruna]]**           | Kaiju Dynamo      |    74 |    0 |    4 |    0 |      0 |    0 |    1 |   11 |  421 |   16 |  0.4 | 113.2 | 1.53514 | 113.6 |
| [[Simon]]           | Darkling Spectres |    52 |    0 |    0 |    0 |      0 |    0 |    0 |   35 |  350 |    4 |  0.0 | 109.0 | 2.09615 | 109.0 |
| [[Bolt]]            | Orbital Machine   |    73 |    1 |   13 |    2 |      7 |    2 |    0 |   15 |  409 |    0 |  7.0 |  96.8 | 1.42192 | 103.8 |
| **[[Mate]]**             | Orbital Machine   |    60 |    2 |   28 |    0 |      0 |    1 |    1 |   10 |  387 |    3 |  5.8 |  92.4 | 1.63667 |  98.2 |
| **[[OreSmitingMaster]]** | Carcosan Tatters  |    67 |    0 |    1 |    0 |      0 |    0 |    1 |   13 |  397 |    2 |  0.1 |  96.4 | 1.44030 |  96.5 |
| **[[Odalric]]**          | Orbital Machine   |    53 |    3 |   33 |    0 |      0 |    1 |    1 |   20 |  316 |    3 |  7.3 |  88.2 | 1.80189 |  95.5 |
| **[[Collar]]**           | Orbital Machine   |    55 |    2 |   16 |    1 |      8 |    2 |    0 |   13 |  353 |    1 |  7.4 |  84.6 | 1.67273 |  92.0 |
| **[[Brown]]**           | Kaiju Dynamo      |    71 |    0 |    0 |    0 |      0 |    0 |    0 |    9 |  390 |    4 |  0.0 |  91.0 | 1.28169 |  91.0 |
| [[Lumusi]]          | Ravenous Eagles   |    82 |    0 |    4 |    1 |      5 |    0 |    1 |   10 |  359 |    3 |  1.9 |  86.8 | 1.08171 |  88.7 |
| **[[Jothi]]**      | Orbital Machine |    36 |    3 |   72 |    2 |      9 |    1 |    2 |    8 |  223 |    1 | 14.1 | 57.6 | 1.99167 |  71.7 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, round((sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)),1) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blocker", "Nurgle Warrior", "Chaos Warrior", "Saurus", "Flesh Golem", "Chaos Dwarf Blocker", "Mummy", "Tomb Guardian") GROUP BY pl.name ORDER BY tVP DESC LIMIT 10;
```

[[Jothi]] is included at the bottom of this list as the blocker with the best [[oVP]] rating. In general, the [[orbitalmachine | Orbital Machine]] is the team that uses its blockers more offensively than  others.

Different playbooks can sometimes use different names for the position, which does make for a bit of variability.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|------|
| Mummy               |       8 |   233 |    0 |    0 |    0 |      0 |    0 |    2 |  116 | 1491 |    6 |  0.0 |  424.2 | 1.82060 | 53.02500 |
| Tomb Guardian       |       7 |   202 |    0 |   18 |    0 |      0 |    1 |    2 |   49 | 1404 |    9 |  2.8 |  342.8 | 1.71089 | 49.37143 |
| Chaos Warrior       |       9 |   391 |   15 |  196 |    5 |     24 |    8 |    4 |   92 | 2346 |   11 | 50.0 |  580.2 | 1.61176 | 70.02222 |
| Saurus              |      30 |   870 |    5 |   77 |    0 |      0 |    0 |    7 |  151 | 4937 |  127 | 12.7 | 1279.4 | 1.48517 | 43.07000 |
| Nurgle Warrior      |      12 |   424 |    1 |   35 |    0 |      0 |    0 |    6 |   84 | 2525 |   12 |  4.5 |  613.0 | 1.45637 | 51.45833 |
| Flesh Golem         |       4 |   112 |    0 |    9 |    0 |      0 |    1 |    3 |   13 |  544 |    3 |  1.9 |  130.8 | 1.18482 | 33.17500 |
| Chaos Dwarf Blocker |      23 |   792 |    9 |  132 |    1 |      5 |    1 |   13 |   89 | 3055 |   27 | 24.7 |  753.0 | 0.98194 | 33.81304 |
| Blocker             |      14 |   344 |    1 |   27 |    0 |      0 |    2 |    1 |   46 | 1328 |    7 |  5.7 |  320.6 | 0.94855 | 23.30714 |
| Total   |     107 |  3368 |   31 |  494 |    6 |     29 |   13 |   38 |  640 | 17630 |  202 | 102.3 | 4444.0 | 1.34985 | 42.48879 |


```
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blocker", "Nurgle Warrior", "Chaos Warrior", "Saurus", "Flesh Golem", "Chaos Dwarf Blocker", "Mummy", "Tomb Guardian") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```

