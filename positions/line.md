Playing on the line is not the glamorous part of BludBol. The job is to get hit and to hit. If the opportunity arises a Line player can do more, but generally this is the job.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Line      |     713 | 11627 |  587 | 16906 | 1098 |   3353 |  735 |  116 |  797 | 23351 |  613 | 4445.9 | 6312.2 | 0.92527 | 15.08850 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Lineman", "Rotter", "Zombie", "Skeleton", "Linewoman", "Marauder", "Beastman", "Hobgoblin", "Thrall", "Halfling") ;
```

Different playbooks can sometimes use different names for the position, which does make for a bit of variability.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|
| Beastman  |      24 |   688 |  127 | 3456 |  106 |    303 |  104 |   16 |   63 |  1710 |   73 |  712.9 |  510.0 | 1.77747 |
| Hobgoblin |      55 |   723 |  140 | 4124 |  130 |    352 |  127 |    6 |   38 |   668 |   32 |  844.6 |  215.6 | 1.46639 |
| Marauder  |      26 |   685 |   52 | 1534 |  148 |    538 |   96 |   17 |   57 |  1662 |   51 |  503.2 |  474.4 | 1.42715 |
| Rotter    |      44 |   489 |   18 | 1400 |  111 |    383 |   29 |    4 |   28 |   571 |   17 |  336.3 |  167.2 | 1.02965 |
| Linewoman |       8 |    99 |   10 |  157 |    6 |     19 |   10 |    2 |    5 |   188 |    5 |   43.6 |   51.6 | 0.96162 |
| Lineman   |     451 |  7192 |  209 | 5486 |  552 |   1635 |  335 |   61 |  525 | 15693 |  356 | 1808.1 | 4141.6 | 0.82727 |
| Thrall    |      11 |   116 |    6 |  132 |    8 |     26 |   10 |    1 |    4 |   204 |    2 |   39.8 |   48.8 | 0.76379 |
| Skeleton  |      31 |   726 |   11 |  274 |   18 |     56 |    7 |    4 |   40 |  1412 |   48 |   69.0 |  378.4 | 0.61625 |
| Halfling  |      17 |   213 |   13 |  302 |   18 |     38 |   17 |    1 |    4 |   125 |   12 |   82.0 |   43.0 | 0.58685 |
| Zombie    |      46 |   696 |    1 |   41 |    1 |      3 |    0 |    4 |   33 |  1118 |   17 |    6.4 |  281.6 | 0.41379 |
| Total     |     713 | 11627 |  587 | 16906 | 1098 |   3353 |  735 |  116 |  797 | 23351 |  613 | 4445.9 | 6312.2 | 0.92527 | 15.08850 |


```
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Lineman", "Rotter", "Zombie", "Skeleton", "Linewoman", "Marauder", "Beastman", "Hobgoblin", "Thrall", "Halfling") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```

