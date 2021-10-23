# Sophronia

[[cacklingfuries]][[blitzer]][[attacker]][[gcvii]][[uci]][[gcviii]][[ucii]][[gcix]][[gcx]][[uciv]][[gcxi]][[superstar]][[dead]]

Sophronia was a stalwart attacking blitzer. Fouled to death by [[Eulaylia]] in GCXI in the runup to the playoffs.

* Birthdate: 1261.765-621:809 #t1765
* Deathdate: 1262.784-380:288 #t2784 

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Sophronia | [Cackling Furies](../teams/cacklingfuries) | Attacker |   23 |   14 |   28 |   65 |    0 |    0 |    1 |   13 |    6 |    2 |    4 |   64 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Sophronia." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Sophronia | Cackling Furies | Green Cup VII     |    2 |    2 |    6 |    0 |    0 |    0 |    1 |    1 |    1 |    1 |   11 |
| Sophronia | Cackling Furies | UBBL Challenge    |    2 |    1 |    1 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |    7 |
| Sophronia | Cackling Furies | StUBBL Scramble   |    0 |    2 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Sophronia | Cackling Furies | Green Cup VIII    |    5 |    0 |   11 |    0 |    0 |    0 |    4 |    3 |    0 |    2 |   24 |
| Sophronia | Cackling Furies | UBBL Challenge II |    2 |    0 |    1 |    0 |    0 |    0 |    0 |    1 |    0 |    1 |    7 |
| Sophronia | Cackling Furies | Green Cup IX      |    7 |    7 |    3 |    0 |    0 |    0 |    3 |    1 |    0 |    1 |   13 |
| Sophronia | Cackling Furies | Green Cup X       |    6 |    4 |    6 |    0 |    0 |    1 |    5 |    1 |    1 |    0 |   16 |
| Sophronia | Cackling Furies | UBBL Challenge IV |    1 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Sophronia | Cackling Furies | Green Cup XI      |    3 |    1 |    2 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Sophronia." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* [[noprize]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Sophronia | Cackling Furies | Green Cup VII     | 10 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   80 |    3 |    1 |   11 |
| Sophronia | Cackling Furies | UBBL Challenge    |  4 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   31 |    0 |    1 |    7 |
| Sophronia | Cackling Furies | Green Cup VIII    | 16 |    0 |    0 |    0 |     0 |    0 |    0 |    7 |  150 |    1 |    2 |   24 |
| Sophronia | Cackling Furies | UBBL Challenge II |  3 |    0 |    6 |    0 |     0 |    0 |    0 |    1 |   24 |    0 |    1 |    7 |
| Sophronia | Cackling Furies | Green Cup IX      | 17 |    0 |    0 |    0 |     0 |    0 |    0 |    4 |  168 |    3 |    1 |   13 |
| Sophronia | Cackling Furies | Green Cup X       | 16 |    0 |    0 |    0 |     0 |    0 |    1 |    7 |  152 |    4 |    0 |   16 |
| Sophronia | Cackling Furies | UBBL Challenge IV |  2 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   25 |    0 |    0 |    0 |
| Sophronia | Cackling Furies | StUBBL Scramble   |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    3 |    1 |    0 |    0 |
| Sophronia | Cackling Furies | Green Cup XI      |  6 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   49 |    0 |    0 |    0 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Sophronia." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Season | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|--------|-------|------|------|------|----------|---------|------|--------|-------|------|------|----|

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Sophronia." GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;
```


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Sophronia | Cackling Furies | Green Cup VII     |           3 |          1 |          1 |          1 |     80 |     3 |     0.0375 |    0.0375 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | UBBL Challenge    |           1 |          1 |          0 |          0 |     31 |     0 |     0.0000 |    0.0323 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | StUBBL Scramble   |           0 |          0 |          0 |          0 |      3 |     1 |     0.3333 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | Green Cup VIII    |           7 |          4 |          3 |          0 |    150 |     1 |     0.0067 |    0.0467 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | UBBL Challenge II |           1 |          0 |          1 |          0 |     24 |     0 |     0.0000 |    0.0417 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | Green Cup IX      |           4 |          3 |          1 |          0 |    168 |     3 |     0.0179 |    0.0238 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | Green Cup X       |           7 |          5 |          1 |          1 |    152 |     4 |     0.0263 |    0.0461 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | UBBL Challenge IV |           0 |          0 |          0 |          0 |     25 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Sophronia | Cackling Furies | Green Cup XI      |           0 |          0 |          0 |          0 |     49 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Sophronia." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

