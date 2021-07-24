# Ashtad

[[zensunvagabonds]][[line]][[gcvi]][[gcvii]][[gcviii]][[gcix]][[gcx]][[uci]][[uciii]][[seasonedveteran]][[dead]]

Because of a data entry mistake Ashtad is often listed as one of the top players for matches played, but he didn't actually play in the old-era as those records indicate which inflate his totals by 45. The stats below are correct. [[besz]] has similar discrepancies in her old-era stats though she did play a few matches in GCIV.

* Birthdate: 1261.
* Deathdate: 1262.732-964:354 #t2732

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ashtad | [Zensun Vagabonds](../teams/zensunvagabonds) | Line  |   26 |   13 |   19 |  58 |    0 |    0 |    0 |    3 |    2 |    0 |    5 |   35 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Ashtad." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ashtad | Zensun Vagabonds | Green Cup VI       |    5 |    4 |    6 |    0 |    0 |    0 |    1 |    2 |    0 |    2 |   16 |
| Ashtad | Zensun Vagabonds | Green Cup VII      |    6 |    6 |    3 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Ashtad | Zensun Vagabonds | UBBL Challenge     |    0 |    0 |    1 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |    2 |
| Ashtad | Zensun Vagabonds | Green Cup VIII     |    5 |    1 |    4 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |    2 |
| Ashtad | Zensun Vagabonds | Green Cup IX       |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Ashtad | Zensun Vagabonds | UBBL Challenge III |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Ashtad | Zensun Vagabonds | Green Cup X        |   10 |    2 |    5 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |   17 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Ashtad." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* [[noprize]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Ashtad | Zensun Vagabonds | Green Cup VI       | 15 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   43 |    0 |    2 |   16 |
| Ashtad | Zensun Vagabonds | Green Cup VII      | 15 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   41 |    0 |    0 |    0 |
| Ashtad | Zensun Vagabonds | UBBL Challenge     |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    5 |    0 |    0 |    2 |
| Ashtad | Zensun Vagabonds | Green Cup VIII     | 10 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   25 |    0 |    0 |    2 |
| Ashtad | Zensun Vagabonds | Green Cup IX       |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    6 |    0 |    0 |    0 |
| Ashtad | Zensun Vagabonds | UBBL Challenge III |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |    0 |
| Ashtad | Zensun Vagabonds | Green Cup X        | 16 |    0 |    2 |    0 |     0 |    0 |    0 |    1 |   62 |    1 |    3 |   17 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Ashtad." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Ashtad | Zensun Vagabonds | Green Cup VI       |           3 |          1 |          2 |          0 |     43 |     0 |     0.0000 |    0.0698 |     0 |    0 |    0 |    0 |         0 |
| Ashtad | Zensun Vagabonds | Green Cup VII      |           0 |          0 |          0 |          0 |     41 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Ashtad | Zensun Vagabonds | UBBL Challenge     |           1 |          1 |          0 |          0 |      5 |     0 |     0.0000 |    0.2000 |     0 |    0 |    0 |    0 |         0 |
| Ashtad | Zensun Vagabonds | Green Cup VIII     |           1 |          1 |          0 |          0 |     25 |     0 |     0.0000 |    0.0400 |     0 |    0 |    0 |    0 |         0 |
| Ashtad | Zensun Vagabonds | Green Cup IX       |           0 |          0 |          0 |          0 |      6 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Ashtad | Zensun Vagabonds | UBBL Challenge III |           0 |          0 |          0 |          0 |      5 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Ashtad | Zensun Vagabonds | Green Cup X        |           1 |          1 |          0 |          0 |     62 |     1 |     0.0161 |    0.0161 |     0 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Ashtad." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 20;
```

