# Luanna

[[cacklingfuries]][[thrower]][[ucii]][[gcix]][[gcx]][[uciv]][[gcxi]][[superstar]][[retired]]

Luanna was a surprising winner of the GCX Relentless Cannon award, but not to her teammates. She retired after the eleventh Green Cup, having achieved a lot, and needing more money than the Furies were willing to spend.

* Birthdate: 1261.967-090:151 #t1967
* Retiredate: post GCXI

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Luanna | [Cackling Furies](../teams/cacklingfuries) | Thrower   |   18 |   12 |   18 |   48 |    5 |  120 |    1 |    3 |    0 |    0 |    4 |  163 |


```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Luanna." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Luanna | Cackling Furies | StUBBL Scramble   |    0 |    2 |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    1 |    6 |
| Luanna | Cackling Furies | UBBL Challenge II |    2 |    0 |    1 |    1 |    6 |    0 |    0 |    0 |    0 |    0 |    9 |
| Luanna | Cackling Furies | Green Cup IX      |    7 |    6 |    3 |    3 |   25 |    0 |    1 |    0 |    0 |    0 |   36 |
| Luanna | Cackling Furies | Green Cup X       |    6 |    4 |    6 |    1 |   41 |    0 |    2 |    0 |    0 |    3 |   63 |
| Luanna | Cackling Furies | UBBL Challenge IV |    1 |    0 |    2 |    2 |    2 |    0 |    0 |    0 |    0 |    0 |    8 |
| Luanna | Cackling Furies | Green Cup XI      |    5 |    2 |    9 |    1 |   54 |    1 |    0 |    0 |    0 |    1 |   64 |



```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Luanna." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Relentless Cannon - Green Cup X [[relentlesscannon#gcx]]
* All-Star - GCX [[allstars#gcx]]
* GCXI Team MVP 64 SPP
* Relentless Cannon - Green Cup XI [[relentlesscannon#gcxi]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Luanna | Cackling Furies | UBBL Challenge II |  3 |    1 |   36 |    6 |    13 |    0 |    0 |    0 |    3 |    0 |    0 |    9 |
| Luanna | Cackling Furies | Green Cup IX      | 16 |    3 |  135 |   25 |    66 |    4 |    0 |    1 |   10 |    0 |    0 |   36 |
| Luanna | Cackling Furies | Green Cup X       | 16 |    1 |  **115** |   41 |   167 |    3 |    0 |    2 |   18 |    0 |    3 |   63 |
| Luanna | Cackling Furies | UBBL Challenge IV |  3 |    2 |   26 |    2 |     7 |    1 |    0 |    0 |    3 |    0 |    0 |    8 |
| Luanna | Cackling Furies | StUBBL Scramble   |  1 |    0 |    5 |    1 |     1 |    0 |    0 |    0 |    0 |    0 |    1 |    6 |
| Luanna | Cackling Furies | Green Cup XI      | 16 |    1 |  204 | **54** |   221 |    0 |    1 |    0 |   15 |    0 |    1 |   64 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Luanna." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```