# Marques

[[palaceorchids]][[catcher]][[ogiii]][[star]]



* Birthdate: 1261.986-574:681 #t1986
* Deathdate: 1262.

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Marques | Palace Orchids | Catcher  |    8 |    1 |    2 |   11 |   14 |    3 |    3 |    2 |    0 |    0 |    1 |   60 |

> Marques began her career in the Open Division, where these stats are from.


```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Marques" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Marques | Palace Orchids | Orange Goblet III |    8 |    1 |    2 |   14 |    3 |    3 |    2 |    0 |    0 |    1 |   60 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Marques" ORDER BY tours.tour_id ASC;
```

# Prize Stats

* MVP - Orange Goblet III [[prizes/mvp#orange goblet iii]]
* Rookie of the Year - Orange Goblet III [[rookieofyear#orange goblet iii]]
* Most TDs - Orange Goblet III [[sardinecrown#orange goblet iii]]
* Most Catches - Orange Goblet III [[softhands#orange goblet iii]]
* Most Rushing - Orange Goblet III [[halflegaward#orange goblet iii]]


| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP | oVP | dVP | tVP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|----:|----:|----:|
| Marques | Palace Orchids | Orange Goblet III | 11 |   14 |  226 |    3 |     5 |   20 |    3 |    2 |   22 |    3 |    1 |   60 | 60.1 | 15.4 | 75.5 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Marques" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Season | Round   | Touches       | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  | oVP  | dVP  | tVP  |
|--------|-------------|--------|---------|----------|-----|------|------|----------|---------|------|--------|-------|------|------|----|----|----|----|
| Marques | Palace Orchids | Orange Goblet III |     1 |       3 |    2 |   19 |    0 |     0 |    3 |    0 |    1 |    0 |    0 |    0 |    8 |  6.9 |  1.0 |  7.9 |
| Marques | Palace Orchids | Orange Goblet III |     2 |       4 |    3 |   36 |    0 |     0 |    4 |    0 |    0 |    0 |    0 |    0 |    9 | 10.6 |  0.0 | 10.6 |
| Marques | Palace Orchids | Orange Goblet III |     4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |  0.0 |  0.0 |  0.0 |
| Marques | Palace Orchids | Orange Goblet III |     5 |       2 |    1 |   21 |    0 |     0 |    2 |    0 |    1 |    1 |    0 |    0 |    5 |  5.1 |  1.2 |  6.3 |
| Marques | Palace Orchids | Orange Goblet III |     6 |       1 |    1 |   12 |    0 |     0 |    1 |    0 |    0 |    3 |    0 |    0 |    3 |  3.2 |  0.6 |  3.8 |
| Marques | Palace Orchids | Orange Goblet III |     7 |       3 |    2 |   16 |    0 |     0 |    2 |    0 |    0 |    1 |    0 |    0 |    6 |  5.6 |  0.2 |  5.8 |
| Marques | Palace Orchids | Orange Goblet III |     8 |       3 |    1 |   30 |    1 |    -1 |    2 |    1 |    0 |    4 |    0 |    0 |    6 |  6.9 |  2.8 |  9.7 |
| Marques | Palace Orchids | Orange Goblet III |     9 |       3 |    1 |   21 |    0 |     0 |    1 |    0 |    0 |    2 |    0 |    0 |    3 |  4.1 |  0.4 |  4.5 |
| Marques | Palace Orchids | Orange Goblet III |    10 |       3 |    1 |   29 |    0 |     0 |    3 |    0 |    0 |    2 |    1 |    1 |    8 |  6.9 |  1.4 |  8.3 |
| Marques | Palace Orchids | Orange Goblet III |    11 |       2 |    2 |   20 |    0 |     0 |    1 |    1 |    0 |    4 |    1 |    0 |    8 |  5.0 |  3.8 |  8.8 |
| Marques | Palace Orchids | Orange Goblet III |   252 |       2 |    0 |   22 |    2 |     6 |    1 |    1 |    0 |    5 |    1 |    0 |    4 |  5.8 |  4.0 |  9.8 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Marques" GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;
```


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Marques" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

