Attackers go after the ball-carrier. They're really just a specialized form of [[positions/blitzer]] but they tend to be more mobile and throw a lot more blocks making them more defensively valuable. Usually teams are more limited in how many attacker roles they have in a lineup.

| Position  | Players | Games | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck  | Sck  | oVP    | dVP    | tVPG    | tVPP |
|-----------|---------|-------|------|------|------|--------|------|------|------|-------|------|--------|--------|---------|-----|
| Attacker  |      26 |   784 |   50 |  660 |   31 |    101 |   59 |   14 |  179 | 5599 |  183 | 216.1 | 1509.8 | 2.20140 | 66.38077 |

```
SELECT count(distinct(md.f_player_id)) AS Players, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(md.f_match_id) AS tVPG, (sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks))/count(distinct(md.f_player_id)) AS tVPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE pl.f_pos_name IN ("Troll Slayer", "Witch Elf", "Assassin", "Norse Werewolf", "Werewolf");
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

