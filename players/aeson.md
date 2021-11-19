# Aeson

[[badgerclaws]][[catcher]][[uci]][[gcviii]][[gcix]][[gcx]][[gcxi]][[active]][[legend]]

Aeson was 0.58GSec old when he made his debut for the Badger Claws.

Aeson holds all sorts of records, including the best single match performance (of 8 TDs and MVP for 29 SPP, which is more than all but 14 players achieved in the first half of the GCX season). He then followed that up in the same season with a 9 TD match (plus MVP) for 32 SPP, eclipsing his own record.

Aeson came up in the UBBL Challenge with [[donat]]. In their first pro season the two had really similar records and both and the main difference between the two players has been one of durability. Aeson has peaked as a legendary player but remains healthy. It remained a weirdness of the business side of BludBol that Aeson was only just barely in the top 50 best paid players in the Pro Circuit until the massive financial readjustment happened in the post GCX off-season.

Aeson didn't play a huge amount in GCXI, being saved for a playoff run and letting youngster [[Klim]] develop the scoring touch instead. It was hugely devastating that the Badger Claws missed the playoffs and Aeson blamed some of that on himself. In this "down" season he only achieved stats that would make a star of a rookie (which isn't quite the legendary performances we've been getting used to). He felt it was time to retire and left on a high note in a very nice passing the torch match in which he and Klim and [[Gianna]] put the torch to the Old Wyrms.

* Birthdate 1262.043-040:245 #t2043
* Retiredate 1262.787-264:548 #t2787 

# Basic Stats

## Pro Totals (pre-GCXI)

| Player           | Team        | Position      | W  | D | L | GP   | TD   | Cp | Int | BH   | SI   | Ki   | MVP  | SPP  |
|------------------|-------------|---------------|----|---|---|------|------|----|-----|------|------|------|------|------|
| Aeson  | [Badger Claws](../teams/badgerclaws) | Catcher |   33 |    7 |   22 |   62 |  155 |    2 |    0 |    0 |    0 |    0 |    9 |  512 |


```
SELECT pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS W, sum(mp.draw) AS D, sum(mp.lost) AS L, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "Aeson." GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

## By Season

| Player | Team         | Season          | W  | D | L | TD   | Cp   | Int | BH   | SI   | Ki   | MVP  | SPP  |
|--------|--------------|-----------------|----|---|---|------|------|-----|------|------|------|------|------|
| Aeson  | Badger Claws | UBBL Challenge  |    4 |    1 |    1 |   16 |    1 |      0 |    0 |    0 |    0 |    1 |   54 |
| Aeson  | Badger Claws | StUBBL Scramble |    1 |    0 |    0 |    3 |    0 |      0 |    0 |    0 |    0 |    0 |    9 |
| Aeson  | Badger Claws | Green Cup VIII  |    9 |    2 |    8 |   27 |    1 |      0 |    0 |    0 |    0 |    1 |   87 |
| Aeson  | Badger Claws | Green Cup IX    |   11 |    3 |    4 |   59 |    1 |      0 |    0 |    0 |    0 |    5 |  203 |
| Aeson  | Badger Claws | Green Cup X     |    9 |    1 |    7 |   52 |    0 |      0 |    0 |    0 |    0 |    3 |  171 |
| Aeson  | Badger Claws | Green Cup XI    |    4 |    1 |    3 |   17 |    0 |    0 |    0 |    0 |    0 |    0 |   51 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mp.won AS W, mp.draw AS D, mp.lost AS L, mp.td as TD, mp.cp AS Cp, mp.intcpt as "Int", mp.bh AS BH, mp.si AS SI, mp.ki AS Ki, mp.mvp AS MVP, mp.spp AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "Aeson." ORDER BY tours.tour_id ASC;
```

# Prize Stats

* StUBBL Jumper - UBBL Challenge I [[mvp#ubbl challenge]]
* MVP - GCIX [[mvp#gcix]]
* Sardine Crown - GCIX [[sardinecrown#gcix]]
* Halfleg Award - GCIX [[halflegaward#gcix]]
* MVP - GCX [[mvp#gcx]]
* Sardine Crown - GCX [[sardinecrown#gcx]]
* Halfleg Award - GCX [[halflegaward#gcx]]
* Soft Hands Award - GCX [[softhands#gcx]]
* Best Single Match Performance - GCX [[bestmatch]]
* MVP - All-Time [[mvp#all-time]]
* Quintuple Centurion [[centurion]]
* All-Star - GCX, GCIX, GCVIII [[allstars]]

| Player | Team         | Season          | GP | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|--------------|-----------------|----|-----|-----|------|-------|------|-----|------|-----|-----|-----|------|
| Aeson  | Badger Claws | UBBL Challenge  |     6 |   16 |  213 |  1 |     2 |   12 |     0 |    0 |      1 |     0 |    1 |   **54** |
| Aeson  | Badger Claws | StUBBL Scramble |     1 |    3 |   38 |  0 |     0 |    2 |     0 |    0 |      0 |     0 |    0 |    9 |
| Aeson  | Badger Claws | Green Cup VIII  |    19 |   27 |  358 |  1 |     0 |   28 |     0 |    0 |      2 |     0 |    1 |   87 |
| Aeson  | Badger Claws | Green Cup IX    |    18 | **59** | **795** |    1 |    1 |    48 |    0 |    0 |      1 |     0 |    5 |  **203** |
| Aeson  | Badger Claws | Green Cup X     |    17 | **52** | **645** |    0 |    0 |**40** |    0 |    0 |      0 |     0 |    3 |  **171** |
| Aeson  | Badger Claws | Green Cup XI    |     8 |   17 |  231 |  0 |     0 |   15 |     0 |    0 |    3 |    0 |    0 |   51 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Aeson." GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
```