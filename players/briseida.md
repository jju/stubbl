# Briseida

[[filthytide]][[blitzer]][[gcviii]][[gcix]][[uciii]][[gcx]][[uciv]][[gcxi]][[seasonedveteran]][[active]]

Briseida really came into her own in tandem with [[venus]]. "Big Bad B" provides the muscle to punch a hole for Little V to score through. This technique doesn't lend itself well to a lot of glory or star player potential, but has been the site of some of the most beautiful bits of BludBol we've been fortunate enough to witness.

* Birthdate: 1262.113-943:038 #t2113 
* Deathdate: 1262.

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Briseida | [Filthy Tide](../teams/filthytide) | Blitzer  |   14 |    1 |   14 |   29 |    2 |    0 |    1 |    2 |    1 |    0 |    4 |   34 |

```
SELECT  pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Briseida" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Briseida | Filthy Tide | Green Cup VIII     |    2 |    0 |    3 |    0 |    0 |    0 |    1 |    1 |    0 |    1 |    9 |
| Briseida | Filthy Tide | Green Cup IX       |    1 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Briseida | Filthy Tide | UBBL Challenge III |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Briseida | Filthy Tide | Green Cup X        |    6 |    0 |    9 |    0 |    0 |    0 |    0 |    0 |    0 |    2 |   10 |
| Briseida | Filthy Tide | UBBL Challenge IV  |    2 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Briseida | Filthy Tide | Green Cup XI       |    5 |    1 |    1 |    2 |    0 |    1 |    1 |    0 |    0 |    1 |   15 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Briseida" ORDER BY tours.tour_id ASC;
```

# Prize Stats

* [[noprize]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Briseida | Filthy Tide | Green Cup VIII     |  5 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |    7 |    1 |    1 |    9 |
| Briseida | Filthy Tide | Green Cup IX       |  2 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   11 |    0 |    0 |    0 |
| Briseida | Filthy Tide | UBBL Challenge III |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |
| Briseida | Filthy Tide | Green Cup X        | 15 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   31 |    1 |    2 |   10 |
| Briseida | Filthy Tide | UBBL Challenge IV  |  2 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    9 |    1 |    0 |    0 |
| Briseida | Filthy Tide | Green Cup XI       |  7 |    2 |   24 |    0 |     0 |    0 |    1 |    1 |   55 |    2 |    1 |   15 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Briseida" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|-------|------|------|------|----------|---------|------|--------|-------|------|------|


## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Briseida | Filthy Tide | Green Cup VIII     |           2 |          1 |          1 |          0 |      7 |     1 |     0.1429 |    0.2857 |     0 |    0 |    0 |    0 |         0 |
| Briseida | Filthy Tide | Green Cup IX       |           0 |          0 |          0 |          0 |     11 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Briseida | Filthy Tide | UBBL Challenge III |           0 |          0 |          0 |          0 |      1 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Briseida | Filthy Tide | Green Cup X        |           0 |          0 |          0 |          0 |     31 |     1 |     0.0323 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Briseida | Filthy Tide | UBBL Challenge IV  |           0 |          0 |          0 |          0 |      9 |     1 |     0.1111 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Briseida | Filthy Tide | Green Cup XI       |           1 |          1 |          0 |          0 |     55 |     2 |     0.0364 |    0.0182 |     0 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Briseida" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```

