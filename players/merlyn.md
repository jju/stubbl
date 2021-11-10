# Merlyn

[[irregularcogs]][[runner]][[gcx]][[uciv]][[gcxi]][[superstar]][[dead]]

Merlyn takes a bit of an odd approach to BludBol, basically daring someone to try and take the ball from him. He's a bit of a bully and his teammates weren't big fans. 

His career ended in the penultimate regular season match in GCXI. With the loss of [[Alexandros]] the week earlier the Cogs were set up incredibly poorly for a playoff run.

* Birthdate: 1261.679-072:112 #t1679
* Deathdate: 1262.786-8 #t2786 

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Merlyn | [Irregular Cogs](../teams/irregularcogs) | Runner   |   18 |    3 |   10 |   31 |   17 |   43 |    2 |    1 |    0 |    0 |    4 |  120 |


```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Merlyn." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Merlyn | Irregular Cogs | Green Cup X       |   10 |    2 |    5 |    9 |   24 |    1 |    0 |    0 |    0 |    3 |   68 |
| Merlyn | Irregular Cogs | UBBL Challenge IV |    1 |    0 |    0 |    2 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Merlyn | Irregular Cogs | Champions Circuit |    1 |    0 |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    1 |
| Merlyn | Irregular Cogs | Green Cup XI      |    7 |    1 |    5 |    8 |   18 |    1 |    1 |    0 |    0 |    1 |   51 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Merlyn." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* All-Star - GCX [[allstars#gcx]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Merlyn | Irregular Cogs | Green Cup X       | 17 |    9 |  256 |   24 |    50 |   14 |    1 |    0 |    9 |    1 |    3 |   68 |
| Merlyn | Irregular Cogs | UBBL Challenge IV |  1 |    2 |   14 |    0 |     0 |    3 |    0 |    0 |    1 |    0 |    0 |    6 |
| Merlyn | Irregular Cogs | Champions Circuit |  1 |    0 |   14 |    1 |     0 |    1 |    0 |    0 |    5 |    1 |    0 |    1 |
| Merlyn | Irregular Cogs | Green Cup XI      | 13 |    8 |  231 |   18 |    19 |   21 |    1 |    1 |   26 |    5 |    1 |   51 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Merlyn." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```