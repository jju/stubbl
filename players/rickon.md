# Rickon

[[cacklingfuries]][[catcher]][[players/oe-veteran]][[gcc06]][[gcvii]][[uci]][[gcviii]][[gcxi]][[active]][[superstar]]

Rickon played a couple of seasons in the old-era and remains on the active roster in GCXI, mostly as a backup if part of the fragile developing stars get hurt. He appreciates his role as the grizzled old vet and tells stories of [[snow]] whom he was buddies with back in the day.

* Birthdate: 1261.545-188:570 #t1545
* Deathdate: 1262.

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Rickon | [Cackling Furies](../teams/cacklingfuries) | Catcher  |   23 |   11 |   31 |   76 |   35 |    2 |    2 |    1 |    0 |    0 |    3 |  128 |

```
SELECT  pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Rickon" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

> this requires checking against the old era records -> -4 -2 -5 in W-D-L compared to db numbers

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Rickon | Cackling Furies | Old-Era GCIII-IV  |    12 |    3 |    8 |   10 |    2 |    0 |    3 |    1 |    0 |    1 |   45 |
| Rickon | Cackling Furies | Green Cup Classic 06 |    1 |    4 |    3 |    6 |    0 |    0 |    0 |    0 |    0 |    1 |   23 |
| Rickon | Cackling Furies | Green Cup VII        |    4 |    3 |    8 |    8 |    0 |    1 |    0 |    0 |    0 |    1 |   31 |
| Rickon | Cackling Furies | UBBL Challenge       |    2 |    1 |    1 |    4 |    0 |    0 |    0 |    0 |    0 |    0 |   12 |
| Rickon | Cackling Furies | Green Cup VIII       |    5 |    0 |   10 |   13 |    1 |    0 |    1 |    0 |    0 |    1 |   47 |
| Rickon | Cackling Furies | Green Cup XI         |    1 |    1 |    2 |    8 |    1 |    1 |    0 |    0 |    0 |    0 |   27 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Rickon" ORDER BY tours.tour_id ASC;
```

> this has been checked against the OE numbers for GC !!! & IV

# Prize Stats

* [[noprize]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Rickon | Cackling Furies | Green Cup Classic 06 |  8 |    6 |  110 |    0 |     0 |   12 |    0 |    0 |    6 |    1 |    1 |   23 |
| Rickon | Cackling Furies | Green Cup VII        | 15 |    8 |  144 |    0 |     0 |   14 |    1 |    0 |   30 |    0 |    1 |   31 |
| Rickon | Cackling Furies | UBBL Challenge       |  4 |    4 |   50 |    0 |     0 |    7 |    0 |    0 |    3 |    0 |    0 |   12 |
| Rickon | Cackling Furies | StUBBL Scramble      |  1 |    0 |    1 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |
| Rickon | Cackling Furies | Green Cup VIII       | 15 |   13 |  173 |    1 |     3 |    9 |    0 |    1 |   19 |    1 |    1 |   47 |
| Rickon | Cackling Furies | Green Cup XI         |  4 |    8 |   65 |    1 |     1 |   10 |    1 |    0 |    6 |    0 |    0 |   27 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Rickon" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Rickon" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

