# Leppard

[[orbitalmachine]][[blitzer]][[gcc6]][[gcvii]][[gcviii]][[gcix]][[gcx]][[uciv]][[gcxi]][[superstar]][[dead]]

Leppard was a stalwart part of the Orbital Machine's greatest successes, but finally succumbed to injury in GCXI against the [Kaiju Dynamo](../teams/kaijudynamo).

* Birthdate: 1261.876-535:886 #t1876 
* Deathdate: 1262.783.161:398 #t2783

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Leppard  | [Orbital Machine](../teams/orbitalmachine) | Blitzer |   39 |   14 |   31 |   84 |   17 |   26 |    2 |    3 |    4 |    2 |    6 |  129 |


```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Leppard." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Leppard | Orbital Machine | Green Cup Classic 06 |    6 |    1 |    3 |    4 |    1 |    0 |    0 |    0 |    1 |    2 |   25 |
| Leppard | Orbital Machine | Green Cup VII        |   10 |    3 |    3 |    1 |    2 |    1 |    1 |    0 |    0 |    2 |   19 |
| Leppard | Orbital Machine | Green Cup VIII       |    9 |    0 |    7 |    3 |    0 |    1 |    2 |    1 |    1 |    2 |   29 |
| Leppard | Orbital Machine | Green Cup IX         |    6 |    3 |    7 |    3 |   13 |    0 |    0 |    1 |    0 |    0 |   24 |
| Leppard | Orbital Machine | Green Cup X          |    7 |    4 |    5 |    3 |   10 |    0 |    0 |    2 |    0 |    0 |   23 |
| Leppard | Orbital Machine | UBBL Challenge IV    |    0 |    0 |    2 |    1 |    0 |    0 |    1 |    0 |    0 |    0 |    5 |
| Leppard | Orbital Machine | Green Cup XI         |    1 |    3 |    6 |    3 |    0 |    0 |    0 |    0 |    0 |    0 |    9 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Leppard." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Green Cup Champion - GCC06 [[champ#06]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Leppard | Orbital Machine | Green Cup Classic 06 | 10 |    4 |   47 |    1 |     1 |    3 |    0 |    1 |   39 |    1 |    2 |   25 |
| Leppard | Orbital Machine | Green Cup VII        | 16 |    1 |   19 |    2 |     9 |    1 |    1 |    1 |   47 |    2 |    2 |   19 |
| Leppard | Orbital Machine | Green Cup VIII       | 16 |    3 |   74 |    0 |     0 |    2 |    1 |    4 |   40 |    1 |    2 |   29 |
| Leppard | Orbital Machine | Green Cup IX         | 16 |    3 |  242 |   13 |    58 |    0 |    0 |    1 |   23 |    3 |    0 |   24 |
| Leppard | Orbital Machine | Green Cup X          | 16 |    3 |  219 |   10 |    29 |    0 |    0 |    2 |   37 |    0 |    0 |   23 |
| Leppard | Orbital Machine | UBBL Challenge IV    |  2 |    1 |    3 |    0 |     0 |    0 |    0 |    1 |    6 |    0 |    0 |    5 |
| Leppard | Orbital Machine | Green Cup XI         | 10 |    3 |   40 |    0 |     0 |    2 |    0 |    0 |   34 |    2 |    0 |    9 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Leppard." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```