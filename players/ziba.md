# Ziba

[[glorioushounds]][[catcher]][[gcx]][[uciv]][[gcxi]][[legend]][[active]]

Ziba hit the ground flying in GCXI after becoming a star in her rookie season and then getting polished up in the Hounds' successful UBBL Challenge IV campaign. Halfway through GCXI she'd already put together a more impressive statline than in GCX, including an absolutely massive performance in Week 6 against the Spectres [[gcxi-06-ghds]]

* Birthdate: 1261.975-089:983 #t1975

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ziba   | [Glorious Hounds](../teams/glorioushounds) | Catcher  |   17 |    7 |    9 |   33 |   81 |    3 |    2 |    1 |    0 |    0 |    6 |  282 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Ziba" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ziba   | Glorious Hounds | Green Cup X       |    4 |    3 |    6 |   15 |    1 |    0 |    1 |    0 |    0 |    3 |   63 |
| Ziba   | Glorious Hounds | UBBL Challenge IV |    4 |    0 |    1 |    9 |    0 |    0 |    0 |    0 |    0 |    1 |   32 |
| Ziba   | Glorious Hounds | Green Cup XI      |   12 |    4 |    3 |   63 |    2 |    2 |    0 |    0 |    0 |    3 |  210 |
| Ziba   | Glorious Hounds | Champions Circuit |    1 |    0 |    0 |    3 |    0 |    0 |    0 |    0 |    0 |    0 |    9 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Ziba" ORDER BY tours.tour_id ASC;
```

# Prize Stats

* StUBBL Jumper - UBBL Challenge IV [[prizes/mvp#ubbl challenge iv]]
* All-Star - GCX [[allstars#gcx]]
* Player of the Week - GCXI [[seasons/gcxi/week04]]
* Soft Hands Award - GCXI [[softhands#gcxi]]
* All-Star - GCXI [[allstars#gcxi]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Ziba   | Glorious Hounds | Green Cup X       | 13 |   15 |  189 |    1 |     2 |   17 |    0 |    1 |    8 |    0 |    3 |   63 |
| Ziba   | Glorious Hounds | UBBL Challenge IV |  5 |    9 |   79 |    0 |     0 |    8 |    0 |    0 |    1 |    0 |    1 |   **32** |
| Ziba   | Glorious Hounds | Green Cup XI      | 19 |   63 |  739 |    2 |     0 |   58 |    2 |    0 |    9 |    1 |    3 |  210 |
| Ziba   | Glorious Hounds | Champions Circuit |  1 |    3 |   21 |    0 |     0 |    3 |    0 |    0 |    0 |    0 |    0 |    9 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Ziba" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```