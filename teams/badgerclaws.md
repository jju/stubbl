# Badger Claws

The Badger Claws fought their way into Green Cup play from the Open Division through the UBBL Challenge and have had only one losing season. They also had the greatest scorer in UBBL history -- [[Aeson]] -- playing for them.

## Playbook

The Badger Claws use the Scrying Avian playbook which emphasizes speed above all else, especially the health of your own players. The position slots only include 2 blitzers, but have 2 throwers, 4 catchers (sometimes more accurately labelled runners), and a heavy available. With proper training it's possible to have a super-fast scorer onside, which makes the lack of defensive ability easier to overcome.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Consolo    | Thrower       |   86 |       4 |   34 |         2 | 200000 |     0 |
|    2 | Gianna     | Thrower       |   18 |       1 |    6 |         0 | 120000 |     0 |
|    3 | Klim       | Catcher |   92 |       3 |   21 |         1 | 210000 |     0 |
|    4 | Ophelia    | Catcher |   36 |       1 |    8 |         1 | 150000 |     0 |
|    6 | Rong       | Runner |   21 |       1 |   14 |         1 | 120000 |     0 |
|    7 | Anselmo    | Line       |    9 |       5 |   45 |         3 |  70000 |     0 |
|    8 | Felicienne | Line       |   11 |       4 |   36 |         2 |  90000 | 20000 |
|    9 | Marge      | Line       |   21 |       4 |   31 |         2 | 110000 | 20000 |
|   10 | Gerty      | Line       |   19 |       3 |   16 |         1 |  90000 |     0 |
|   11 | Simas      | Line       |    7 |       5 |   31 |         2 |  90000 | 20000 |
|   14 | Chroma     | Blitzer       |    0 |       1 |    4 |         0 |  90000 |     0 |
|   15 | Iris       | Blitzer       |   55 |       4 |   48 |         3 | 190000 |     0 |
|   16 | Pippin     | Heavy      |   61 |       3 |   36 |         2 | 260000 | 20000 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   25 | Comgan     | Blitzer       |   23 |       3 |   17 |         1 | 150000 |  10000 |
|   36 | Friese     | Heavy      |    4 |       2 |    3 |         0 | 150000 |      0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Badger Claws" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Badger Claws | Pro    |   33 |   10 |   28 |   71 | 53.088 |  253 |  230 |            88 |            -78 |          1 |
| Badger Claws | Open   |    4 |    1 |    1 |    6 | 75.000 |   25 |   19 |             8 |              2 |          1 |
| Badger Claws | Street |    1 |    1 |    0 |    2 | 75.000 |    5 |    2 |             1 |             -4 |          0 |

```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, Round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Badger Claws" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Badger Claws |   38 |   12 |   29 |   79 | 60.392 |  283 |  251 |            97 |            -80 |          2 |


```
SELECT teams.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, Round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Badger Claws" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* Green Cup VIII - Pits Division Champions [[teamdivision#gcviii]]
* Green Cup VIII - Classic Conference Champions [[team2ndplace#gcviii]] & [[teamconference#gcviii]]
* Green Cup IX - Outlands Division Champions [[teamdivision#gcix]]
* Green Cup IX - Tough Brake of Alsoran [[team3rdplace#gcix]]
* Green Cup X - Outlands Division Champions [[teamdivision#gcx]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Badger Claws | UBBL Challenge  |    4 |    1 |    1 |      6 |      75.00 |   25 |   19 |    5 |      2 |    1 |
| Badger Claws | StUBBL Scramble |    1 |    1 |    0 |      2 |      75.00 |    5 |    2 |    0 |     -4 |    0 |
| Badger Claws | Green Cup IX    |   11 |    3 |    4 |     18 | 69.44 |   75 |   56 |   20 |    -20 |    0 |
| Badger Claws | Green Cup X     |    9 |    1 |    8 |     18 | 52.78 |   64 |   58 |   21 |     -8 |    1 |
| Badger Claws | Green Cup VIII  |    9 |    2 |    8 |     19 | 52.63 |   61 |   57 |   15 |    -32 |    4 |
| Badger Claws | Green Cup XI    |    4 |    4 |    8 |     16 |    37.5 |   53 |   59 |   22 |    -18 |   -4 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Badger Claws" ORDER BY mr.win_pct DESC limit 16;
```

## History

Before GCXI the Claws had never not had a winning season, they've also never won a championship.

### Seasons

The Badger Claws did not win the first UBBL Challenge (which was a bigger affair and much tougher for challenger teams who had to face two established Green Cup teams in Pool Play). But as the top-finishing challenger they won the right to play the last-place [Brutes](gargantuanbrutes) for their spot in the Green Cup.

After defeating the [Brutes](gargantuanbrutes) 5-2, the Badger Claws went off on a tear in the Green Cup VIII tournament. They slowed down around the midpoint but made it through the playoffs with upset after stunning upset until facing down the [Gore Farmers](gorefarmers) in the final. And losing, but still. What a run.

Green Cup IX went even better for the Claws as far as wins go, but they were knocked out of the Conference Finals by the [Old Wyrms](oldwyrms), so they had to be satisfied with third place.

The projections for GCX had the Claws as 10-game winners and at least conference champions. They didn't manage that because of the incredibly competitive Outlands division, but did squeak through to the conference finals where they lost to the [Old Wyrms](oldwyrms) again.

#### Projection GCXI

W-D-L 9-1-5

There is no doubt that the Badger Claws can score. The question is if their defense can manage to hold off enough key plays to make them Green Cup Champions. Anything less is going to feel like a failure in [[Aeson]]'s probable final season.

#### summary GCXI

How to dissect the failure that was this season? The Badger Claws never climbed above 8th place in the overall standings despite an initial projection of an Outlands Division title. Even then there was still hope they could turn things around, but an ugly string of draws and losses weren't enough for what is usually described as the toughest most competitive GC division.

[[aeson]] and [[klim]] weren't as seamless a pairing as management would have preferred and there wasn't much else going on for the team. Aeson did hang up his cleats as the all-time MVP after the final regular season match.

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  | Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|----------|-----|
| Badger Claws |     1 |       9 |    2 |   42 |    4 |       26 |      4 |          0 |    1 |     25 |     1 |    1 |   17 |           4 |           2 |
| Badger Claws |     2 |       9 |    2 |   36 |    2 |        6 |      2 |          0 |    0 |     38 |     1 |    1 |   13 |           2 |           5 |
| Badger Claws |     3 |      15 |    5 |   87 |    7 |       12 |      7 |          0 |    3 |     33 |     1 |    1 |   33 |           4 |           5 |
| Badger Claws |     4 |       4 |    0 |   16 |    1 |        6 |      1 |          0 |    0 |     12 |     0 |    1 |    6 |           0 |           2 |
| Badger Claws |     5 |      11 |    3 |   51 |    0 |        0 |      0 |          0 |    2 |     20 |     0 |    1 |   18 |           2 |           3 |
| Badger Claws |     6 |      20 |    5 |   90 |    6 |       12 |      6 |          0 |    0 |     29 |     1 |    1 |   26 |           5 |           6 |
| Badger Claws |     7 |      18 |    5 |   94 |    6 |       34 |      6 |          2 |    3 |     43 |     1 |    1 |   36 |           5 |           4 |
| Badger Claws |     8 |       8 |    2 |   55 |    3 |        7 |      3 |          0 |    1 |     22 |     3 |    1 |   16 |           3 |           2 |
| Badger Claws |     9 |      11 |    2 |   54 |    3 |       14 |      3 |          1 |    4 |     32 |     1 |    1 |   24 |           2 |           2 |
| Badger Claws |    10 |       8 |    1 |   44 |    2 |        4 |      2 |          0 |    1 |     20 |     1 |    1 |   12 |           1 |           1 |
| Badger Claws |    11 |      12 |    2 |   40 |    3 |        5 |      3 |          0 |    0 |     16 |     1 |    1 |   14 |           2 |           2 |
| Badger Claws |    12 |      21 |    7 |  189 |    7 |       18 |      8 |          0 |    1 |     31 |     1 |    1 |   35 |           9 |           7 |
| Badger Claws |    13 |      20 |    7 |  123 |    5 |       13 |      5 |          0 |    1 |     47 |     2 |    1 |   33 |           7 |           8 |
| Badger Claws |    14 |       6 |    3 |   37 |    0 |        0 |      0 |          1 |    1 |     20 |     1 |    1 |   18 |           3 |           3 |
| Badger Claws |    15 |      24 |    7 |  125 |    8 |       15 |      8 |          0 |    2 |     36 |     2 |    1 |   38 |           7 |           3 |
| Badger Claws |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    0 |    0 |         BYE |           L |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Badger Claws" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster GCXI

| #    | Player      | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|-------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Consolo     | 14 |      43 |    0 |  168 | **22** |  55 |    3 |    0 |    2 |   29 |    1 |    1 |           3 |      1 |    3 |    2 |       1 |      0 |   31 |
|    2 | Gianna      |  7 |      13 |    2 |   54 |    7 |     8 |    1 |    0 |    0 |    7 |    0 |    1 |           0 |      0 |    1 |    0 |       0 |      0 |   18 |
|    3 | Klim        | 12 |      27 | **19** | **267** | 0 |   0 | **19** |  0 |    0 |    2 |    2 |    2 |           1 |      3 |    4 |    1 |       1 |      0 | **67** |
|    4 | Ophelia     |  9 |      25 |    6 |  125 |    6 |    18 |    7 |    1 |    0 |    2 |    1 |    2 |           0 |      4 |    1 |    0 |       0 |      0 |   36 |
|    6 | Rong        | 15 |      17 |    4 |   90 |    5 |    11 |    6 |    2 |    0 |   12 |    2 |    0 |           0 |      4 |    6 |    1 |       1 |      0 |   21 |
|    7 | Anselmo     | 15 |       1 |    0 |    5 |    0 |     0 |    1 |    0 |    1 |   25 |    0 |    0 |           0 |      0 |    5 |    4 |       1 |      0 |    2 |
|    8 | Felicienne  | 16 |       1 |    0 |    0 |    0 |     0 |    0 |    1 |    1 |   32 |    1 |    0 |           0 |      1 |    5 |    2 |       0 |      0 |    4 |
|    9 | Marge       | 16 |       1 |    1 |    7 |    0 |     0 |    1 |    0 |    1 |   32 |    1 |    1 |           0 |      0 |    6 |    5 |       0 |      0 |   10 |
|   10 | Gerty       | 13 |       3 |    1 |    6 |    0 |     0 |    1 |    0 |    3 |   20 |    1 |    2 |           0 |      0 |    3 |    1 |       2 |      0 |   19 |
|   11 | Simas       | 14 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    9 |    0 |    0 |           0 |      0 |    4 |    0 |       0 |      0 |    0 |
|   14 | Chroma      |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    6 |    1 |    0 |           0 |      0 |    1 |    1 |       1 |      0 |    0 |
|   15 | Iris        | 13 |       1 |    0 |    8 |    0 |     0 |    1 |    0 |    5 |  117 |    2 |    1 |           0 |      0 |    3 |    0 |       1 |      0 |   15 |
|   16 | Pippin      |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 | **7** |  39 |    2 |    0 |           0 |      0 |    0 |    2 |       0 |      0 |   14 |
|   81 | Cleve.      |  7 |      24 |    0 |   39 |   15 |    76 |    0 |    0 |    0 |    9 |    0 |    0 |           1 |      0 |    3 |    0 |       1 |      R |   15 |
|   84 | Aeson.      |  8 |      23 |   17 |  231 |    0 |     0 |   15 |    0 |    0 |    3 |    0 |    0 |           0 |      2 |    3 |    0 |       0 |      R |   51 |
|   85 | Sunny.      |  9 |       7 |    3 |   34 |    0 |     0 |    1 |    0 |    0 |   17 |    1 |    0 |           0 |      1 |    6 |    0 |       1 |      R |    9 |
|   85 | Barukh.     |  8 |       9 |    0 |   49 |    2 |     4 |    2 |    0 |    0 |   22 |    0 |    2 |           0 |      3 |    4 |    1 |       1 |      R |   12 |
|   86 | Olanrewaju. |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    3 |    1 |    0 |           0 |      0 |    1 |    0 |       0 |      1 |    0 |
|   92 | Ejiroghene. |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      1 |    0 |
|   94 | Ishkur.     |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   37 |    1 |    3 |           0 |      0 |    1 |    1 |       2 |      1 |   15 |

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Badger Claws" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Aeson  | Catcher |   38 |    8 |   23 |   69 |  174 |    3 |    0 |    0 |    0 |    0 |   10 |  575 |
| Cleve  | Thrower       |   32 |    6 |   20 |   58 |    0 |  136 |    1 |    0 |    0 |    0 |    3 |  153 |
| Donat  | Catcher |   19 |    6 |   12 |   37 |   35 |    2 |    0 |    1 |    0 |    0 |    0 |  109 |
| **Klim**    | Catcher |    8 |    4 |    9 |   21 |   21 |    7 |    1 |    0 |    0 |    0 |    4 |   92 |
| **Consolo** | Thrower       |   14 |    6 |   14 |   34 |    0 |   55 |    1 |    1 |    1 |    0 |    5 |   86 |
| **Pippin**  | Heavy      |   21 |    4 |   11 |   36 |    0 |    0 |    0 |   13 |    6 |    4 |    3 |   61 |
| Barukh | Attacker |   17 |    8 |   15 |   40 |    5 |   14 |    1 |    0 |    0 |    0 |    5 |   56 |
| **Iris**    | Blitzer       |   23 |    9 |   17 |   49 |    0 |    1 |    0 |    9 |    3 |    0 |    6 |   55 |
| Avani  | Attacker |   23 |    5 |   13 |   41 |    5 |    4 |    1 |    3 |    0 |    0 |    5 |   52 |
| Sunny  | Attacker |   13 |    5 |   15 |   33 |   11 |    2 |    1 |    0 |    0 |    0 |    1 |   42 |
| Haman  | Thrower       |   15 |    3 |   11 |   29 |    1 |   20 |    1 |    2 |    0 |    1 |    2 |   41 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Badger Claws" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

Obviously when we talk about the Badger Claws we have to talk about the best player the UBBL has ever seen, [Aeson](../players/aeson). Aeson's SPP total in GCIX alone eclipse hundreds of players.

Aeson and [[donat]] started out similarly but Donat got a serious concussion and development slowed. In the off-season after GCX, Donat was the first player in the UBBL to be sold under the new free agency rules. He ended up with the Open Division [Vanadium Hunters](vanadiumhunters) for Orange Goblet II, where he was crippled in his first match and withdrew from BludBol entirely.

[[cleve]] is one of the biggest stars in the UBBL who has never scored a touchdown (3rd in the all-UBBL list and 3rd in the Pro Division). What makes it even more remarkable is how many times he touches the ball without going for the endzone himself.

It will eventually be a problem that all their good players have peaked and are getting more expensive by the season and there's not a lot of skill waiting in the wings. 

#### Award Winners
| #    | Player | Position      | Seasons | Prizes | Value  | Bonus  |
|------|--------|---------------|---------|--------|--------|--------|
|    5 |  Aeson | Catcher |       6 |      9 | 320000 | 110000 |
|   98 |  Donat | Catcher |       4 |      1 | 240000 |  30000 |


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val As Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Badger Claws" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

### Fans

The Badger Claws had a major fan surge (FF +4 over the 9-2-8 season) in their first Green Cup tournament. The team has a few rivalries going to sustain it. The [Arboreal Menace](arborealmenace) are a natural rival as the new upstart little sibling in the Green Cup world, while their use of the same playbook as the [Filthy Tide](filthytide) make for some natural "Who did it better?" kinds of comparisons. Then there's the [Old Wyrms](oldwyrms), the team that's stopped the Claws in the conference finals every time they've shared the Burger Conference.

### Famous Games

The Green Cup VIII Conference Final against the [Kaiju Dynamo](kaijudynamo) was an insanely intense score-fest right to the end, when an ill-timed stumble for the Dynamo cost them the match 8-7. That was the highest scoring match seen to that time.

The Badger Claws did break that high scoring record, albeit in a 10-8 loss to the underdog Filthy Tide in [Week 9](../seasons/gcx/week09) of the GCX season.

