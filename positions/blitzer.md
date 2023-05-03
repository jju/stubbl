Blitzers are the stars of BludBol. They can bash, they can score, they are who you want on your team.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Blitzer   |     204 |  5594 | 1337 | 17861 |  443 |   1237 | 1219 |  150 |  936 | 23118 |  842 | 4908.8 | 6701.6 | 2.07551 | 56.91373 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blitzer", "Wight", "Pestigor", "Beastman", "Blitz-Ra");
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
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Blitzer", "Wight", "Pestigor", "Beastman", "Blitz-Ra") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```

