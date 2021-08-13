# Kropotkin

[[arborealmenace]][[blitzer]][[ucii]][[uciii]][[gcx]][[uciv]][[gcxi]][[superstar]][[dead]]

One of the OG Arborists, Kropotkin was a steadying influence as they made their way into Green Cup play. Though their first season in the pros wasn't successful, Special K was sure they'd make their way to the top like they did in the third UBBL Challenge. He was killed by [[Rajendra]] in GCXI.

* Birthdate: 1261.736-881:229 #t1736
* Deathdate: 1262.779-818:894 #t2779 

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Kropotkin | [Arboreal Menace](../teams/arborealmenace) | Blitzer |    9 |    3 |   10 |   22 |    1 |    0 |    0 |    3 |    1 |    0 |    3 |   26 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Kropotkin." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Kropotkin | Arboreal Menace | UBBL Challenge II  |    3 |    0 |    2 |    5 |    0 |    0 |    0 |    0 |    0 |    0 |   15 |
| Kropotkin | Arboreal Menace | UBBL Challenge III |    6 |    1 |    0 |    1 |    0 |    0 |    1 |    3 |    0 |    2 |   21 |
| Kropotkin | Arboreal Menace | Green Cup X        |    6 |    2 |    8 |    0 |    0 |    0 |    1 |    1 |    0 |    1 |    9 |
| Kropotkin | Arboreal Menace | UBBL Challenge IV  |    3 |    0 |    1 |    1 |    2 |    1 |    1 |    0 |    0 |    1 |   14 |
| Kropotkin | Arboreal Menace | Green Cup XI       |    3 |    1 |    2 |    1 |    0 |    0 |    2 |    0 |    0 |    2 |   17 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Kropotkin." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* [[noprize]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Kropotkin | Arboreal Menace | UBBL Challenge II  |  5 |    5 |   35 |    0 |     0 |    6 |    0 |    0 |   15 |    0 |    0 |   15 |
| Kropotkin | Arboreal Menace | UBBL Challenge III |  7 |    1 |   11 |    0 |     0 |    0 |    0 |    4 |   34 |    2 |    2 |   21 |
| Kropotkin | Arboreal Menace | Green Cup X        | 16 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   56 |    7 |    1 |    9 |
| Kropotkin | Arboreal Menace | UBBL Challenge IV  |  4 |    1 |   13 |    2 |     2 |    0 |    1 |    1 |   21 |    4 |    1 |   14 |
| Kropotkin | Arboreal Menace | Green Cup XI       |  6 |    1 |    8 |    0 |     0 |    0 |    0 |    2 |   24 |    2 |    2 |   17 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Kropotkin." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```

### match by match

| Player | Team        | Season | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|--------|-------|------|------|------|----------|---------|------|--------|-------|------|------|----|

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Kropotkin." GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;
```


