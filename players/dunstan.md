# Dunstan

[[eldritchfatality]][[attacker]][[gcix]][[gcx]][[uciv]][[gcxi]][[star]][[gcxi]][[dead]]

Dunstan was the powerhouse attacker for the Fatality in their great GCIX, terrible GCX and amazing GCXI. He was taken out in the leadup to the playoffs in GCXI, which exposed the team's lack of a real backup as far as muscle goes.

* Birthdate: 1261.946-635:262 #t1946 
* Deathdate: 1262.784-652:898 #t2784 

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Dunstan | [Eldritch Fatality](../teams/eldritchfatality) | Attacker  |   24 |    3 |   19 |   46 |    3 |    3 |    1 |    8 |    5 |    1 |    2 |   52 |

```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Dunstan." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W | D | L | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|--------|--------------|-----------------|--:|--:|--:|---:|---:|----:|---:|---:|---:|----:|----:|
| Dunstan | Eldritch Fatality | StUBBL Scramble   |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Dunstan | Eldritch Fatality | Green Cup IX      |   10 |    1 |    6 |    3 |    2 |    0 |    2 |    2 |    1 |    1 |   26 |
| Dunstan | Eldritch Fatality | Green Cup X       |    4 |    2 |   10 |    0 |    0 |    1 |    2 |    2 |    0 |    1 |   15 |
| Dunstan | Eldritch Fatality | UBBL Challenge IV |    2 |    0 |    2 |    0 |    0 |    0 |    2 |    0 |    0 |    1 |    9 |
| Dunstan | Eldritch Fatality | Champions Circuit |    0 |    0 |    1 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
| Dunstan | Eldritch Fatality | Green Cup XI      |   10 |    0 |    2 |    0 |    1 |    0 |    4 |    1 |    0 |    0 |   11 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Dunstan." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* Hunter Award - Green Cup IX [[hunteraward#gcix]]

| Player | Team         | Season          | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|-----------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Dunstan | Eldritch Fatality | Green Cup IX      | 17 |    3 |   30 |    2 |    14 |    4 |    0 |    5 |  123 |   **10** |    1 |   26 |
| Dunstan | Eldritch Fatality | Green Cup X       | 16 |    0 |    7 |    0 |     0 |    0 |    1 |    4 |  150 |    5 |    1 |   15 |
| Dunstan | Eldritch Fatality | UBBL Challenge IV |  4 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   54 |    1 |    1 |    9 |
| Dunstan | Eldritch Fatality | Champions Circuit |  1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   11 |    0 |    0 |    0 |
| Dunstan | Eldritch Fatality | Green Cup XI      | 12 |    0 |    2 |    1 |     5 |    0 |    0 |    5 |  122 |    7 |    0 |   11 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Dunstan." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```