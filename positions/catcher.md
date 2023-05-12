The biggest scorers in BludBol tend to be Catchers. They are the players who get downfield and bring the ball into the endzone. The scoring emphasis means they can end up hogging a lot of the [[SPP]] on a team, so it's important not to focus to much on them since they can be fragile. Some teams use their catchers well on defence too, forcing [[Int | interceptions]] and [[sack | sacks]] galore.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Catcher    |     144 |  3320 | 2188 | 31224 |  716 |   1142 | 3025 |  143 |  121 | 4604 |  367 | 9165.6 | 1694.8 | 3.27120 | 75.41944 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Gutter Runner", "Catcher", "Skaven Renegade", "Goblin Renegade");
```

## position hall of fame

| Player     | Team             | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVPG    | tVP   |
|------------|------------------|-------|------|------|------|--------|------|------|------|------|------|-------|------|---------|-------|
| [[Aeson]]    | Badger Claws    |    69 |  174 | 2280 |    3 |      3 |  145 |    0 |    0 |    7 |    0 | 550.3 |  1.4 | 7.99565 | 551.7 |
| [[Souta]]    | Old Wyrms       |    67 |   72 |  923 |   51 |      5 |  132 |    3 |    3 |  113 |    9 | 347.8 | 40.6 | 5.79701 | 388.4 |
| **[[Veens]]**     | Filthy Tide     |    35 |  106 | 1274 |    1 |      3 |   80 |    0 |    0 |    3 |    1 | 314.7 |  1.6 | 9.03714 | 316.3 |
| **[[Ziba]]**      | Glorious Hounds |    38 |   90 | 1028 |    3 |      2 |   86 |    2 |    1 |   18 |    1 | 282.0 |  9.6 | 7.67368 | 291.6 |
| **[[Amador]]**    | Old Wyrms       |    55 |   32 |  607 |   44 |     10 |   84 |    2 |    2 |  137 |    9 | 221.7 | 42.4 | 4.80182 | 264.1 |
| **[[Aronne]]**    | Cackling Furies |    51 |   31 |  741 |   30 |    -11 |   91 |    2 |    0 |  106 |    5 | 225.0 | 30.2 | 5.00392 | 255.2 |
| [[Costache]] | Glorious Hounds |    50 |   76 |  640 |    3 |     -2 |   73 |    2 |    4 |   95 |    6 | 215.8 | 33.0 | 4.97600 | 248.8 |
| [[Yakup]]    | Filthy Tide     |    51 |   73 |  986 |    1 |      1 |   67 |    0 |    1 |   23 |    2 | 239.7 |  7.6 | 4.84902 | 247.3 |
| **[[Laurel]]**    | Arboreal Menace |    47 |   58 |  883 |    0 |      0 |   72 |    2 |    0 |   15 |    1 | 218.3 |  8.0 | 4.81489 | 226.3 |
| **[[Georgina]]**  | Arboreal Menace |    53 |   41 |  672 |   12 |     45 |   59 |   14 |    0 |   33 |    1 | 183.7 | 35.6 | 4.13774 | 219.3 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, round((sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)),1) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Gutter Runner", "Catcher", "Skaven Renegade", "Goblin Renegade") GROUP BY pl.name ORDER BY tVP DESC LIMIT 10;
```

The Catchers' hall of fame looks a lot like the UBBL hall of fame. If you look at the best defensive catchers the list changes, notably including [[Signe]] from the Open-level [[hoods]].

Different playbooks can sometimes use different names for the position, which does make for a bit of variability.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|------|
| Gutter Runner   |      30 |   726 |  624 |  9184 |  119 |    248 |  621 |   18 |   14 |  749 |   84 | 2307.2 |  283.8 | 3.56887 | 86.36667 |
| Catcher         |     103 |  2429 | 1505 | 21154 |  573 |    795 | 2341 |  122 |   95 | 3620 |  266 | 6613.9 | 1329.0 | 3.27003 | 77.11553 |
| Skaven Renegade |       7 |    80 |   26 |   373 |   23 |     96 |   20 |    1 |   12 |  230 |   17 |  115.9 |   77.0 | 2.41125 | 27.55714 |
| Goblin Renegade |       4 |    85 |   33 |   513 |    1 |      3 |   43 |    2 |    0 |    5 |    0 |  128.6 |    5.0 | 1.57176 | 33.40000 |
| Total           |     144 |  3320 | 2188 | 31224 |  716 |   1142 | 3025 |  143 |  121 | 4604 |  367 | 9165.6 | 1694.8 | 3.27120 | 75.41944 |


```
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Gutter Runner", "Catcher", "Skaven Renegade", "Goblin Renegade") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```
