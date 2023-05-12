Blitzers are the stars of BludBol. They can bash, they can score, they are who you want on your team.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Blitzer   |     204 |  5594 | 1337 | 17861 |  443 |   1237 | 1219 |  150 |  936 | 23118 |  842 | 4908.8 | 6701.6 | 2.07551 | 56.91373 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blitzer", "Wight", "Pestigor", "Beastman", "Blitz-Ra", "Vampire", "Bull Centaur");
```

## position hall of fame

| Player     | Team             | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVPG    | tVP   |
|------------|------------------|-------|------|------|------|--------|------|------|------|------|------|-------|------|---------|-------|
| [[Atte]]       | Eldritch Fatality |    48 |   48 |  569 |    4 |      8 |   61 |    1 |    1 |  100 |    4 | 170.7 |  27.0 | 4.11875 | 197.7 |
| [[Leppard]]    | Orbital Machine   |    86 |   18 |  644 |   26 |     97 |    8 |    2 |   10 |  226 |    9 | 126.1 |  68.2 | 2.25930 | 194.3 |
| [[KneeMasher]] | Gore Farmers      |    52 |   31 |  422 |   10 |     28 |   33 |    8 |    5 |  162 |    8 | 119.0 |  61.4 | 3.46923 | 180.4 |
| [[Rohit]]      | Zensun Vagabonds  |    50 |    7 |   69 |    1 |      5 |    5 |    1 |   52 |  417 |   17 |  20.4 | 154.4 | 3.49600 | 174.8 |
| **[[Beatrix]]**     | Eldritch Fatality |    82 |   23 |  248 |   12 |     75 |   24 |    4 |    7 |  236 |   15 |  91.3 |  77.2 | 2.05488 | 168.5 |
| **[[Betul]]**       | Eldritch Fatality |    49 |   35 |  404 |    9 |     22 |   37 |    7 |    3 |   97 |    5 | 123.6 |  41.4 | 3.36735 | 165.0 |
| **[[Padma]]**       | Zensun Vagabonds  |    35 |   41 |  491 |    1 |      0 |   45 |    0 |    6 |   99 |    3 | 136.1 |  28.8 | 4.71143 | 164.9 |
| **[[Florinda]]**    | Glorious Hounds   |    70 |    4 |   46 |    4 |     24 |    6 |    3 |   17 |  499 |   17 |  21.0 | 139.8 | 2.29714 | 160.8 |
| [[Dragos]]     | Irregular Cogs    |    61 |   38 |  340 |    5 |      5 |   40 |    2 |    1 |  161 |    5 | 117.5 |  42.2 | 2.61803 | 159.7 |
| **[[Orna]]**        | Carcosan Tatters  |    71 |   21 |  236 |    4 |     10 |   12 |    0 |   10 |  357 |   16 |  61.6 |  97.4 | 2.23944 | 159.0 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, round((sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)),1) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blitzer", "Wight", "Pestigor", "Beastman", "Blitz-Ra", "Vampire", "Bull Centaur") GROUP BY pl.name ORDER BY tVP DESC LIMIT 10;
```


Different playbooks can sometimes use different names for the position, which does make for a bit of variability.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|
| Pestigor |      12 |   433 |  131 |  1972 |   27 |     62 |  115 |    6 |   87 |  2115 |   64 |  476.4 |  586.0 | 2.45358 | 88.53333 |
| Blitzer  |     150 |  4029 | 1044 | 11845 |  295 |    818 |  964 |  122 |  716 | 17189 |  650 | 3569.3 | 5047.8 | 2.13877 | 57.44733 |
| Beastman |      24 |   688 |  127 |  3456 |  106 |    303 |  104 |   16 |   63 |  1710 |   73 |  712.9 |  510.0 | 1.77747 | 50.95417 |
| Blitz-Ra |       6 |   100 |   17 |   227 |    4 |     12 |   11 |    1 |   12 |   455 |   14 |   55.9 |  119.0 | 1.74900 | 29.15000 |
| Wight    |      12 |   344 |   18 |   361 |   11 |     42 |   25 |    5 |   58 |  1649 |   41 |   94.3 |  438.8 | 1.54971 | 44.42500 |
| Total    |     204 |  5594 | 1337 | 17861 |  443 |   1237 | 1219 |  150 |  936 | 23118 |  842 | 4908.8 | 6701.6 | 2.07551 | 56.91373 |


```
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blitzer", "Wight", "Pestigor", "Beastman", "Blitz-Ra", "Vampire") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```

