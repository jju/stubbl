Attackers go after the ball-carrier. They're really just a specialized form of [[positions/blitzer]] but they tend to be more mobile and throw a lot more blocks making them more defensively valuable. Usually teams are more limited in how many attacker roles they have in a lineup.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Attacker  |      26 |   784 |   50 |  660 |   31 |    101 |   59 |   14 |  179 | 5599 |  183 | 216.1 | 1509.8 | 2.20140 | 66.38077 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Troll Slayer", "Witch Elf", "Assassin", "Norse Werewolf", "Werewolf");
```

## position hall of fame

| Player     | Team             | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP   | dVP  | tVPG    | tVP   |
|------------|------------------|-------|------|------|------|--------|------|------|------|------|------|-------|------|---------|-------|
| [[Sophronia]] | Cackling Furies   |    75 |    0 |    6 |    0 |      0 |    0 |    1 |   23 |  682 |   12 |  0.6 | 173.4 | 2.32000 | 174.0 |
| [[Dunstan]]   | Eldritch Fatality |    50 |    3 |   39 |    3 |     19 |    4 |    1 |   16 |  460 |   23 | 15.8 | 133.0 | 2.97600 | 148.8 |
| [[Ignat]]     | Irregular Cogs    |    59 |    8 |   85 |    2 |      5 |   12 |    1 |    7 |  430 |   19 | 31.0 | 114.0 | 2.45763 | 145.0 |
| [[Fosgood]]   | Eldritch Fatality |    49 |    9 |   92 |    4 |      9 |    8 |    3 |    6 |  283 |   18 | 31.1 |  86.6 | 2.40204 | 117.7 |
| [[Erazem]]    | Irregular Cogs    |    39 |    4 |   29 |    2 |      0 |    0 |    1 |   11 |  355 |   18 |  8.9 | 102.0 | 2.84359 | 110.9 |
| [[Hin]]       | Cackling Furies   |    55 |    2 |   12 |    0 |      0 |    1 |    1 |   11 |  406 |   12 |  4.2 | 106.2 | 2.00727 | 110.4 |
| **[[Amalie]]**     | Kicking Mules     |    46 |    0 |    9 |    0 |      0 |    0 |    0 |   19 |  412 |    5 |  0.9 | 106.4 | 2.33261 | 107.3 |
| [[Hermes]]    | Eldritch Fatality |    46 |   10 |  134 |    4 |     14 |   10 |    1 |    5 |  229 |   12 | 38.8 |  64.8 | 2.25217 | 103.6 |
| [[Ife]]       | Cackling Furies   |    50 |    0 |    5 |    0 |      0 |    0 |    0 |   18 |  393 |    5 |  0.5 | 101.6 | 2.04200 | 102.1 |
| **[[Gottfried]]**  | Kicking Mules     |    37 |    0 |    0 |    0 |      0 |    0 |    0 |   25 |  320 |    4 |  0.0 |  93.0 | 2.51351 |  93.0 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, round((sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)),1) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Troll Slayer", "Witch Elf", "Assassin", "Norse Werewolf", "Werewolf") GROUP BY pl.name ORDER BY tVP DESC LIMIT 10;
```

Different playbooks can sometimes use different names for the position, which does make for a bit of variability.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|
| Witch Elf      |      13 |   373 |   48 |  590 |   28 |     88 |   57 |   10 |   66 | 2595 |  134 | 200.8 | 739.0 | 2.51957 | 72.29231 |
| Troll Slayer   |       4 |   113 |    0 |    9 |    0 |      0 |    0 |    0 |   51 |  971 |   11 |   0.9 | 256.2 | 2.27522 | 64.27500 |
| Norse Werewolf |       8 |   233 |    2 |   23 |    0 |      0 |    1 |    2 |   62 | 1849 |   38 |   5.3 | 473.8 | 2.05622 | 59.88750 |
| Assassin       |       1 |    65 |    0 |   38 |    3 |     13 |    1 |    2 |    0 |  184 |    0 |   9.1 |  40.8 | 0.76769 | 49.90000 |
| Total     |      26 |   784 |   50 |  660 |   31 |    101 |   59 |   14 |  179 | 5599 |  183 | 216.1 | 1509.8 | 2.20140 | 66.38077 |


```
SELECT pl.f_pos_name AS Position, count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Troll Slayer", "Witch Elf", "Assassin", "Norse Werewolf", "Werewolf") GROUP BY pl.f_pos_name ORDER BY tVPG DESC LIMIT 50;
```

