# Beard Puller

[[gorefarmers]][[blitzer]][[gcvi]][[gcvii]][[uci]][[gcviii]][[gcix]][[seasonedveteran]][[retired]]

Beard Puller was a role playing veteran for the Gore Farmers' successful campaigns and was let go in favour of developing youthful blitzers in Green Cup IX.

* Birthdate: 1261.771-826:061 #t1771
* Retiredate: 1262.665-583:612 #t2665 

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| BeardPuller | [Gore Farmers](../teams/gorefarmers) | Blitzer  |   24 |    6 |   18 |   48 |    6 |    0 |    2 |    5 |    3 |    0 |    0 |   38 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "BeardPuller." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| BeardPuller | Gore Farmers | Green Cup VI   |   10 |    3 |    4 |    4 |    0 |    1 |    2 |    0 |    0 |    0 |   18 |
| BeardPuller | Gore Farmers | Green Cup VII  |    3 |    0 |    7 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| BeardPuller | Gore Farmers | UBBL Challenge |    1 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| BeardPuller | Gore Farmers | Green Cup VIII |   11 |    3 |    5 |    2 |    0 |    1 |    2 |    3 |    0 |    0 |   18 |
| BeardPuller | Gore Farmers | Green Cup IX   |    0 |    0 |    2 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |    2 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "BeardPuller." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Green Cup Champion - GCVI [[champ#vi]]
* Green Cup Champion - GCVIII [[champ#viii]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| BeardPuller | Gore Farmers | Green Cup VI   | 17 |    4 |   29 |    0 |     0 |    0 |    1 |    2 |   65 |    3 |    0 |   18 |
| BeardPuller | Gore Farmers | Green Cup VII  | 10 |    0 |   11 |    0 |     0 |    0 |    0 |    0 |   36 |    1 |    0 |    0 |
| BeardPuller | Gore Farmers | UBBL Challenge |  2 |    0 |    2 |    0 |     0 |    0 |    0 |    0 |   11 |    0 |    0 |    0 |
| BeardPuller | Gore Farmers | Green Cup VIII | 19 |    2 |   24 |    0 |     0 |    0 |    1 |    5 |   66 |    1 |    0 |   18 |
| BeardPuller | Gore Farmers | Green Cup IX   |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    6 |    0 |    0 |    2 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "BeardPuller." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Season | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|--------|-------|------|------|------|----------|---------|------|--------|-------|------|------|----|

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "BeardPuller." GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;
```


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| BeardPuller | Gore Farmers | Green Cup VI   |           2 |          2 |          0 |          0 |     65 |     3 |     0.0462 |    0.0308 |     0 |    0 |    0 |    0 |         0 |
| BeardPuller | Gore Farmers | Green Cup VII  |           0 |          0 |          0 |          0 |     36 |     1 |     0.0278 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| BeardPuller | Gore Farmers | UBBL Challenge |           0 |          0 |          0 |          0 |     11 |     0 |     0.0000 |    0.0000 |     1 |    0 |    0 |    0 |         0 |
| BeardPuller | Gore Farmers | Green Cup VIII |           5 |          2 |          3 |          0 |     66 |     1 |     0.0152 |    0.0758 |     1 |    1 |    0 |    0 |         1 |
| BeardPuller | Gore Farmers | Green Cup IX   |           1 |          1 |          0 |          0 |      6 |     0 |     0.0000 |    0.1667 |     0 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "BeardPuller." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

