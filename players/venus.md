# Venus

[[filthytide]][[catcher]][[runner]][[gcx]][[gcxi]][[legend]][[active]]

Venus was "discovered" in the Green Cup V Memorial tournament and is now the greatest hope the Tide have for winning a Green Cup. She once scored 8 TDs in her Round 9 GCX match against the Badger Claws, which is better than [[Yakup]] ever managed. She shares second place in the single match TD record list with Aeson and Donat.

* Birthdate 1262.121-274:700 #t2121 (Born during GCII)

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Venus  | [Filthy Tide](../teams/filthytide) | Catcher |   20 |    2 |   12 |   34 |  105 |    1 |    0 |    0 |    0 |    0 |    4 |  336 |


```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Venus" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Venus  | Filthy Tide | Green Cup V Memorial |    0 |    0 |    1 |    1 |    0 |    0 |    0 |    0 |    0 |    1 |    8 |
| Venus  | Filthy Tide | Green Cup X          |    7 |    0 |    7 |   35 |    0 |    0 |    0 |    0 |    0 |    3 |  120 |
| Venus  | Filthy Tide | Champions Circuit    |    0 |    0 |    2 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Venus  | Filthy Tide | Green Cup XI         |   13 |    2 |    3 |   69 |    1 |    0 |    0 |    0 |    0 |    1 |  213 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Venus" ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Rookie of the Year - Green Cup X [[rookieofyear#gcx]]
* All-Star - GCX [[allstars#gcx]]
* MVP - GCXI [[mvp#gcxi]]
* Sardines Crown - GCXI [[sardinecrown#gcxi]]
* Halfleg Award - GCXI [[halflegaward#gcxi]]
* All-Star - GCXI [[allstars#gcxi]]
* Green Cup XI Champion [[champ#gcxi]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Venus  | Filthy Tide | Green Cup V Memorial |  1 |    1 |    3 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    1 |    8 |
| Venus  | Filthy Tide | Green Cup X          | 14 |   35 |  489 |    0 |     0 |   33 |    0 |    0 |    2 |    0 |    3 |  **120** |
| Venus  | Filthy Tide | Green Cup XI         | 18 |   69 |  770 |    1 |     3 |   47 |    0 |    0 |    1 |    1 |    1 |  213 |
| Venus  | Filthy Tide | Champions Circuit    |  2 |    1 |   12 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Venus" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```