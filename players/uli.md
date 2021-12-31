# Uli

[[orbitalmachine]][[heavy]][[gcix]][[gcx]][[uciv]][[gcxi]][[active]][[superstar]]

Uli took over as the Orbital Machine's heavy muscle in the same season the team lost their lock on the team casualties award, so many fans blame him irrationally. His effectiveness started going up in GCXI.

* Birthdate: 1261.667-300:559 #t1667

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Uli    | [Orbital Machine](../teams/orbitalmachine) | Heavy |   14 |   12 |   20 |   46 |    0 |    0 |    0 |   30 |   14 |    1 |    4 |  110 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Uli" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Uli    | Orbital Machine | Green Cup IX      |    6 |    2 |    6 |    0 |    0 |    0 |    8 |    3 |    0 |    2 |   32 |
| Uli    | Orbital Machine | Green Cup X       |    7 |    4 |    5 |    0 |    0 |    0 |    9 |    2 |    1 |    2 |   34 |
| Uli    | Orbital Machine | UBBL Challenge IV |    0 |    0 |    2 |    0 |    0 |    0 |    2 |    0 |    0 |    0 |    4 |
| Uli    | Orbital Machine | Green Cup XI      |    1 |    6 |    9 |    0 |    0 |    0 |   13 |    9 |    0 |    0 |   44 |



```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Uli" ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Carmine Fist - Green Cup XI [[carminefist#gcxi]]
* Dervish Award - Green Cup XI [[dervishaward#gcxi]]

| Player | Team            | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|-----------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Uli    | Orbital Machine | Green Cup IX      | 14 |    0 |    0 |    0 |     0 |    0 |    0 |   11 |  149 |    2 |    2 |   32 |
| Uli    | Orbital Machine | Green Cup X       | 16 |    0 |    0 |    0 |     0 |    0 |    0 |   12 |  177 |    4 |    2 |   34 |
| Uli    | Orbital Machine | UBBL Challenge IV |  2 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   22 |    0 |    0 |    4 |
| Uli    | Orbital Machine | Green Cup XI      | 16 |    0 |    0 |    0 |     0 |    0 |    0 |   **22** |  **174** |    2 |    0 |   44 |



```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Uli" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Season | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|--------|-------|------|------|------|----------|---------|------|--------|-------|------|------|----|

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Uli" GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;
```


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Uli  | Orbital Machine | Green Cup IX      |          11 |          8 |          3 |          0 |    149 |     2 |     0.0134 |    0.0738 |     0 |    0 |    0 |    0 |         0 |
| Uli  | Orbital Machine | Green Cup X       |          12 |          9 |          2 |          1 |    177 |     4 |     0.0226 |    0.0678 |     0 |    0 |    0 |    0 |         0 |
| Uli  | Orbital Machine | UBBL Challenge IV |           2 |          2 |          0 |          0 |     22 |     0 |     0.0000 |    0.0909 |     0 |    0 |    0 |    0 |         0 |
| Uli  | Orbital Machine | Green Cup XI      |          22 |         13 |          9 |          0 |    174 |     2 |     0.0115 |    0.1264 |     0 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Uli" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

