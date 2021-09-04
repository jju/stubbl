# Tycho

[[vanadiumhunters]][[carcosantatters]][[catcher]][[thrower]][[freeagent]][[gcc06]][[gcvii]][[uci]][[gcviii]][[gcix]][[gcx]][[uciv]][[gcxi]][[dead]][[superstar]]

Tycho was so much better as a Tatter than as a Hunter. 

## Pro Totals
| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Tycho  | [Vanadium Hunters](../teams/vanadiumhunters) / [Carcosan Tatters](../teams/carcosantatters) | Catcher / Thrower   |   32 |   16 |   28 |   76 |   15 |   49 |    2 |    2 |    1 |    0 |    3 |  119 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Tycho." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Tycho  | Vanadium Hunters | Green Cup Classic 06 |    0 |    0 |    3 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Tycho  | Vanadium Hunters | Green Cup VII        |    3 |    7 |    6 |   10 |    2 |    0 |    0 |    0 |    0 |    0 |   32 |
| Tycho  | Vanadium Hunters | UBBL Challenge       |    1 |    1 |    1 |    3 |    0 |    1 |    0 |    0 |    0 |    0 |   11 |
| Tycho  | Vanadium Hunters | Green Cup VIII       |    1 |    1 |    2 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |
| Tycho  | Carcosan Tatters | Green Cup VIII       |   10 |    0 |    3 |    1 |    5 |    0 |    0 |    0 |    0 |    1 |   13 |
| Tycho  | Carcosan Tatters | Green Cup IX         |    8 |    3 |    4 |    3 |   15 |    0 |    1 |    1 |    0 |    0 |   28 |
| Tycho  | Carcosan Tatters | Green Cup X          |    8 |    3 |    5 |    0 |   13 |    2 |    0 |    0 |    0 |    2 |   27 |
| Tycho  | Carcosan Tatters | UBBL Challenge IV    |    1 |    0 |    2 |    0 |    4 |    0 |    0 |    0 |    0 |    0 |    4 |
| Tycho  | Carcosan Tatters | Green Cup XI         |    2 |    2 |    4 |    0 |   14 |    0 |    1 |    0 |    0 |    0 |   16 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Tycho." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* [[noprize]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Tycho  | Vanadium Hunters | Green Cup Classic 06 |  3 |    0 |    1 |    0 |     0 |    3 |    0 |    0 |    0 |    0 |    0 |    0 |
| Tycho  | Vanadium Hunters | Green Cup VII        | 16 |   10 |  128 |    2 |     6 |   13 |    0 |    0 |    6 |    0 |    0 |   32 |
| Tycho  | Vanadium Hunters | UBBL Challenge       |  3 |    3 |   35 |    0 |     0 |    5 |    1 |    0 |    5 |    0 |    0 |   11 |
| Tycho  | Vanadium Hunters | Green Cup VIII       |  4 |    1 |    3 |    0 |     0 |    1 |    0 |    0 |    1 |    0 |    0 |    3 |
| Tycho  | Carcosan Tatters | Green Cup VIII       | 13 |    1 |   88 |    5 |    21 |    1 |    0 |    0 |   13 |    1 |    1 |   13 |
| Tycho  | Carcosan Tatters | Green Cup IX         | 15 |    3 |  208 |   15 |    54 |    1 |    0 |    2 |    7 |    0 |    0 |   28 |
| Tycho  | Carcosan Tatters | Green Cup X          | 16 |    0 |  163 |   13 |    40 |    0 |    2 |    0 |    5 |    0 |    2 |   27 |
| Tycho  | Carcosan Tatters | UBBL Challenge IV    |  3 |    0 |   25 |    4 |    28 |    0 |    0 |    0 |    0 |    0 |    0 |    4 |
| Tycho  | Carcosan Tatters | Green Cup XI         |  8 |    0 |   75 |   14 |    52 |    0 |    0 |    1 |   12 |    1 |    0 |   16 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Tycho." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```