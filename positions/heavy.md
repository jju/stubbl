A team without a Heavy generally has a rougher time in the battles of attrition that can make up a BludBol match. Usually Heavies are the big strong anchor that smashes opponents and collects gaudy [[Cas]] totals.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Heavy     |      61 |  1569 |   19 |  427 |   12 |     27 |    3 |   21 |  795 | 9964 |  157 | 79.4 | 2986.8 | 1.95424 | 50.26557 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Ogre", "Troll", "Minotaur", "Chaos Troll", "Chaos Ogre", "Kroxigor", "Treeman", "Deathroller", "Yhetee", "Rat Ogre", "Beast of Nurgle");
```

## position hall of fame

| Player     | Team             | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVPG    | tVP   |
|------------|------------------|-------|------|------|------|--------|------|------|------|------|------|-------|------|---------|-------|
| [[Somfuhr]] | Filthy Tide       |    69 |    0 |    8 |    0 |      0 |    0 |    0 |   61 |  557 |   15 |  0.8 | 187.4 | 2.72754 | 188.2 |
| [[Marzhak]] | Gargantuan Brutes |    50 |    0 |    0 |    0 |      0 |    0 |    1 |   55 |  550 |   20 |  0.0 | 187.0 | 3.74000 | 187.0 |
| [[Jantine]] | Ravenous Eagles   |    51 |    0 |   16 |    0 |      0 |    0 |    1 |   63 |  518 |    6 |  1.6 | 174.6 | 3.45490 | 176.2 |
| **[[Percy]]**    | Ravenous Eagles   |    47 |    1 |    8 |    0 |      0 |    0 |    1 |   46 |  529 |    8 |  1.8 | 161.8 | 3.48085 | 163.6 |
| **[[Uli]]**      | Orbital Machine   |    48 |    0 |    0 |    0 |      0 |    0 |    0 |   47 |  522 |    8 |  0.0 | 159.4 | 3.32083 | 159.4 |
| **[[Katka]]**    | Hoods             |    34 |    0 |    0 |    0 |      0 |    0 |    0 |   40 |  340 |   10 |  0.0 | 118.0 | 3.47059 | 118.0 |
| **[[Pierre]]**   | Carcosan Tatters  |    67 |    0 |    7 |    0 |      0 |    0 |    0 |   32 |  376 |    2 |  0.7 | 109.2 | 1.64030 | 109.9 |
| [[Snow]]    | Cackling Furies   |    46 |    0 |    0 |    0 |      0 |    1 |    0 |   27 |  332 |    4 |  1.0 |  97.4 | 2.13913 |  98.4 |
| [[Lars]]    | Orbital Machine   |    29 |    1 |   11 |    0 |      0 |    0 |    2 |   18 |  284 |    3 |  2.1 |  81.8 | 2.89310 |  83.9 |
| **[[Pippin]]**   | Badger Claws      |    36 |    0 |    0 |    0 |      0 |    0 |    0 |   23 |  261 |    7 |  0.0 |  82.2 | 2.28333 |  82.2 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, round((sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)),1) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Ogre", "Troll", "Minotaur", "Chaos Troll", "Chaos Ogre", "Kroxigor", "Treeman", "Deathroller", "Yhetee", "Rat Ogre", "Beast of Nurgle") GROUP BY pl.name ORDER BY tVP DESC LIMIT 10;
```

[[somfuhr]]'s longevity made his efficiency as a Heavy somewhat lacking, but he's the most valuable player in the position.

Different playbooks can sometimes use different names for the position, which does make for a bit of variability.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|
| Minotaur        |      11 |   314 |    5 |   63 |    0 |      0 |    0 |    8 |  302 | 3322 |   60 | 11.3 | 1042.4 | 3.35573 |  95.79091 |
| Rat Ogre        |       5 |   154 |    0 |    4 |    0 |      0 |    0 |    1 |  104 | 1149 |   26 |  0.4 |  361.8 | 2.35195 |  72.44000 |
| Yhetee          |       4 |    85 |    0 |    1 |    0 |      0 |    1 |    0 |   41 |  585 |    8 |  1.1 |  166.0 | 1.96588 |  41.77500 |
| Ogre            |      20 |   451 |   14 |  347 |   12 |     27 |    1 |    9 |  158 | 2312 |   45 | 64.4 |  683.4 | 1.65809 |  37.39000 |
| Beast of Nurgle |       1 |    67 |    0 |    7 |    0 |      0 |    0 |    0 |   32 |  376 |    2 |  0.7 |  109.2 | 1.64030 | 109.90000 |
| Kroxigor        |       5 |   144 |    0 |    2 |    0 |      0 |    0 |    1 |   68 |  719 |    8 |  0.2 |  221.8 | 1.54167 |  44.40000 |
| Treeman         |       4 |   105 |    0 |    2 |    0 |      0 |    0 |    2 |   41 |  510 |    1 |  0.2 |  148.0 | 1.41143 |  37.05000 |
| Chaos Ogre      |       3 |    87 |    0 |    0 |    0 |      0 |    0 |    0 |   18 |  397 |    4 |  0.0 |  101.4 | 1.16552 |  33.80000 |
| Chaos Troll     |       2 |    50 |    0 |    1 |    0 |      0 |    0 |    0 |   11 |  211 |    1 |  0.1 |   54.2 | 1.08600 |  27.15000 |
| Deathroller     |       2 |    32 |    0 |    0 |    0 |      0 |    0 |    0 |    8 |  132 |    0 |  0.0 |   34.4 | 1.07500 |  17.20000 |
| Troll           |       4 |    80 |    0 |    0 |    0 |      0 |    1 |    0 |   12 |  251 |    2 |  1.0 |   64.2 | 0.81500 |  16.30000 |
| Total           |      61 |  1569 |   19 |  427 |   12 |     27 |    3 |   21 |  795 | 9964 |  157 | 79.4 | 2986.8 | 1.95424 | 50.26557 |


```
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Ogre", "Troll", "Minotaur", "Chaos Troll", "Chaos Ogre", "Kroxigor", "Treeman", "Deathroller", "Yhetee", "Rat Ogre", "Beast of Nurgle") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```
