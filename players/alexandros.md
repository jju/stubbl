# Alexandros

[[irregularcogs]][[darklingspectres]][[runner]][[line]][[thrower]][[gcviii]][[ucii]][[gcix]][[gcx]][[uciv]][[gcxi]][[superstar]][[active]]

Alexandros played a few games before the ninth Green Cup season, but GCIX was the career-defining one. He won the rookie of the year competition and made himself a superstar. Injuries kept him from being a rough and tumble Runner and he migrated to the deep passing threat. At the end of his career with the Irregular Cogs, Alexandros was the 10th most prolific Pro passer of all time. His SPP total sat just below the [[centurion]] threshold at 21st.

* Birthdate: 1261.908-877:377 #t1908
* Deathdate: 1262.784-496:523 #t2784 

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Alexandros | [Irregular Cogs](../teams/irregularcogs) / [Darkling Spectres](../teams/darklingspectres)   | Runner / Line   |   26 |    5 |   15 |   46 |    9 |   82 |    1 |    0 |    0 |    0 |    4 |  131 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Alexandros." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Alexandros | Irregular Cogs    | Green Cup VIII       |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Alexandros | Irregular Cogs    | UBBL Challenge II    |    0 |    0 |    1 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    1 |
| Alexandros | Irregular Cogs    | Green Cup IX         |    9 |    1 |    5 |    8 |   30 |    0 |    0 |    0 |    0 |    4 |   74 |
| Alexandros | Irregular Cogs    | Green Cup V Memorial |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Alexandros | Irregular Cogs    | Green Cup X          |   10 |    2 |    5 |    0 |   23 |    1 |    0 |    0 |    0 |    0 |   25 |
| Alexandros | Irregular Cogs    | UBBL Challenge IV    |    1 |    0 |    1 |    0 |    3 |    0 |    0 |    0 |    0 |    1 |    8 |
| Alexandros | Irregular Cogs    | Green Cup XI         |    6 |    2 |    4 |    1 |   29 |    0 |    0 |    0 |    0 |    0 |   32 |
| Alexandros | Darkling Spectres | Green Cup XI         |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Alexandros." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Rookie of the Year - GCIX [[rookieofyear#gcix]]
* All-Star - GCIX [[allstars#gcix]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Alexandros | Irregular Cogs    | Green Cup VIII    |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Alexandros | Irregular Cogs    | UBBL Challenge II |  1 |    0 |   14 |    1 |    -1 |    3 |    0 |    0 |    0 |    0 |    0 |    1 |
| Alexandros | Irregular Cogs    | Green Cup IX      | 15 |    8 |  265 |   30 |    65 |   19 |    0 |    0 |    2 |    0 |    4 |   74 |
| Alexandros | Irregular Cogs    | Green Cup X       | 17 |    0 |  163 |   23 |    57 |    6 |    1 |    0 |    2 |    0 |    0 |   25 |
| Alexandros | Irregular Cogs    | UBBL Challenge IV |  2 |    0 |   14 |    3 |    13 |    0 |    0 |    0 |    0 |    0 |    1 |    8 |
| Alexandros | Irregular Cogs    | Green Cup XI      | 12 |    1 |  184 |   29 |   118 |    1 |    0 |    0 |    6 |    0 |    0 |   32 |
| Alexandros | Darkling Spectres | Green Cup XI      |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Alexandros." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Season | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|--------|-------|------|------|------|----------|---------|------|--------|-------|------|------|----|

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Alexandros." GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;
```


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Alexandros." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

