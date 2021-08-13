# Ekua

[[ravenouseagles]][[blitzer]][[gcvi]][[gcvii]][[gcviii]][[gcix]][[gcx]][[gcxi]][[superstar]][[active]]

Ekua has had the longest pro-level UBBL career ever. They started GCXI 6 matches shy of [[hulud]]'s record (which included four seasons in the Old Era). They have put in solid seasons every year without getting any major in-season awards.

* Birthdate: 1261.908-741:886 #t1908
* Retiredate: 1262.???

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ekua   | [Ravenous Eagles](../teams/ravenouseagles) | Blitzer |   35 |   13 |   42 |   90 |    9 |    0 |    1 |   24 |   13 |    3 |    4 |  129 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Ekua" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ekua   | Ravenous Eagles | Green Cup VI         |    5 |    2 |    8 |    3 |    0 |    0 |    2 |    1 |    0 |    1 |   20 |
| Ekua   | Ravenous Eagles | Green Cup VII        |   11 |    2 |    6 |    3 |    0 |    1 |    4 |    2 |    0 |    0 |   23 |
| Ekua   | Ravenous Eagles | Green Cup VIII       |    5 |    0 |   10 |    0 |    0 |    0 |    7 |    2 |    1 |    1 |   25 |
| Ekua   | Ravenous Eagles | Green Cup IX         |    3 |    3 |    8 |    0 |    0 |    0 |    2 |    2 |    0 |    2 |   18 |
| Ekua   | Ravenous Eagles | Green Cup V Memorial |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Ekua   | Ravenous Eagles | Green Cup X          |    8 |    4 |    7 |    2 |    0 |    0 |    8 |    5 |    2 |    0 |   36 |
| Ekua   | Ravenous Eagles | Champions Circuit    |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Ekua   | Ravenous Eagles | Green Cup XI         |    3 |    2 |    2 |    1 |    0 |    0 |    1 |    1 |    0 |    0 |    7 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Ekua" ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Green Cup Champion - GCVII [[champ#vii]]
* Dervish Award - All-Time [[dervishaward#all-time]]
* Hunter Award - All-Time [[hunteraward#all-time]]
* Most Pro Matches

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Ekua   | Ravenous Eagles | Green Cup VI         | 15 |    3 |   12 |    0 |     0 |    0 |    0 |    3 |   76 |    4 |    1 |   20 |
| Ekua   | Ravenous Eagles | Green Cup VII        | 19 |    3 |   34 |    0 |     0 |    0 |    1 |    6 |  153 |    5 |    0 |   23 |
| Ekua   | Ravenous Eagles | Green Cup VIII       | 15 |    0 |    7 |    0 |     0 |    0 |    0 |   10 |  103 |    5 |    1 |   25 |
| Ekua   | Ravenous Eagles | Green Cup IX         | 14 |    0 |   15 |    0 |     0 |    1 |    0 |    4 |   90 |    3 |    2 |   18 |
| Ekua   | Ravenous Eagles | Green Cup V Memorial |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   11 |    0 |    0 |    0 |
| Ekua   | Ravenous Eagles | Green Cup X          | 19 |    2 |    5 |    0 |     0 |    0 |    0 |   15 |  142 |    5 |    0 |   36 |
| Ekua   | Ravenous Eagles | Champions Circuit    |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    7 |    0 |    0 |    0 |
| Ekua   | Ravenous Eagles | Green Cup XI         |  7 |    1 |    2 |    0 |     0 |    0 |    0 |    2 |   49 |    5 |    0 |    7 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Ekua" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

## blocks and fouls

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Ekua | Ravenous Eagles | Green Cup VI         |           3 |          2 |          1 |          0 |     76 |     4 |     0.0526 |    0.0395 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Green Cup VII        |           6 |          4 |          2 |          0 |    153 |     5 |     0.0327 |    0.0392 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Green Cup VIII       |          10 |          7 |          2 |          1 |    103 |     5 |     0.0485 |    0.0971 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Green Cup IX         |           4 |          2 |          2 |          0 |     90 |     3 |     0.0333 |    0.0444 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Green Cup V Memorial |           0 |          0 |          0 |          0 |     11 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Green Cup X          |          15 |          8 |          5 |          2 |    142 |     5 |     0.0352 |    0.1056 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Champions Circuit    |           0 |          0 |          0 |          0 |      7 |     0 |     0.0000 |    0.0000 |     0 |    0 |    0 |    0 |         0 |
| Ekua | Ravenous Eagles | Green Cup XI         |           2 |          1 |          1 |          0 |     49 |     5 |     0.1020 |    0.0408 |     0 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 AND pl.name = "Ekua" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mp.f_trid ASC limit 10;
```
