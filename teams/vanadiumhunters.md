# Vanadium Hunters

The Hunters have been around a long time and in the Old-Era had one of the best players in the business. They've never been very good though, which led to relegation to the Open Division after GCVIII.

## Playbook

The Vanadium Hunters use the Hermann playbook, the original plan for playing BludBol, and the one that every other strategy is an adaptation of. The team has two thrower positions available, 4 catchers, 4 blitzers, a big guy and fills out the rest of the lineup with undistinguished concussion-fodder. Like most Hermann teams, the Hunters don't use all their specialist receivers, trusting more to a running game with the blitzers.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Charles     | Thrower  |   67 |       7 |   41 |         3 | 160000 |     0 |
|    2 | Melchor     | Thrower  |  112 |       8 |   56 |         4 | 180000 |     0 |
|    3 | NicodemusII | Catcher  |    6 |       1 |    3 |         0 | 200000 |     0 |
|    4 | Amata       | Catcher  |  119 |       8 |   43 |         3 | 190000 |     0 |
|    5 | Mahmud      | Blitzer  |   31 |       5 |   22 |         1 | 150000 |     0 |
|    6 | Mohan       | Blitzer  |   55 |      10 |   50 |         3 | 170000 |     0 |
|    7 | Kondwani    | Lineman  |   47 |      11 |   69 |         5 | 110000 |     0 |
|    8 | Mayflower   | Lineman  |   69 |      14 |  113 |         8 | 130000 |     0 |
|    9 | Mor         | Lineman  |   19 |       5 |   20 |         1 |  90000 |     0 |
|   10 | Kalyani     | Lineman  |   12 |       3 |   19 |         1 | 100000 |     0 |
|   11 | Horea       | Lineman  |   35 |      10 |   68 |         5 | 120000 |     0 |
|   12 | Tammi       | Lineman  |    0 |       2 |   16 |         1 |  50000 |     0 |
|   13 | Bozena      | Lineman  |   18 |       4 |   19 |         1 |  90000 |     0 |
|   14 | Nanuli      | Blitzer  |   25 |       3 |   11 |         1 | 140000 |     0 |
|   15 | Erastos     | Catcher  |   42 |       5 |   45 |         3 | 130000 |     0 |
|   16 | Boguslaw    | Ogre     |   60 |      10 |   51 |         3 | 250000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Zahida      | Thrower  |   39 |       2 |   14 |         1 | 150000 |     0 |
|    2 | Baz         | Thrower  |   81 |       9 |   40 |         3 | 240000 |     0 |
|    3 | Gautstafr   | Catcher  |   90 |       6 |   25 |         2 | 210000 |     0 |
|    6 | Bjorg       | Blitzer  |   10 |       1 |    9 |         1 | 110000 |     0 |
|    9 | Venceslao   | Lineman  |   19 |       6 |   33 |         2 |  90000 |     0 |
|   10 | Raquel      | Lineman  |   10 |       2 |   13 |         1 |  70000 |     0 |
|   11 | Anastazija  | Lineman  |   18 |       3 |   15 |         1 |  90000 |     0 |
|   12 | Leifur      | Lineman  |   12 |       4 |   15 |         1 | 100000 |     0 |
|   14 | Kamal       | Blitzer  |    7 |       3 |    3 |         0 | 110000 |     0 |
|   15 | Farhan      | Catcher  |   17 |       2 |   14 |         1 | 130000 |     0 |
|   16 | Leutgard    | Ogre     |   22 |       3 |   22 |         1 | 180000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   43 | Aibinn      | Lineman  |    0 |       1 |    1 |         0 |  50000 |     0 |
|   44 | Asih        | Lineman  |    0 |       1 |    2 |         0 |  50000 |     0 |
|   45 | Sargon      | Lineman  |    0 |       3 |   16 |         1 |  50000 |     0 |
|   46 | Estine      | Lineman  |    0 |       1 |    2 |         0 |  50000 |     0 |


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Vanadium Hunters" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```



### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Vanadium Hunters | Pro      |   19 |   15 |   37 |   71 | 37.472 |  148 |  171 |  126 |      18 |    1 |
| Vanadium Hunters | Open     |   17 |    7 |   25 |   49 | 31.297 |   87 |  109 |   72 |     -14 |   -2 |
| Vanadium Hunters | Street   |    4 |    4 |    5 |   13 | 47.917 |   18 |   21 |   16 |      -4 |    2 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Vanadium Hunters" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Vanadium Hunters |   40 |   26 |   67 |  133 | 35.690 |  253 |  301 |  214 |       0 |    1 |

```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Vanadium Hunters" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* Green Cup IV - Doom Fist [[teamcasualties]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Vanadium Hunters | Orange Goblet        |    7 |    1 |    4 |     12 |    62.5 |   26 |   21 |   21 |      6 |    4 |
| Vanadium Hunters | Orange Goblet II     |    5 |    2 |    4 |     11 | 54.5455 |   22 |   20 |   16 |      4 |    0 |
| Vanadium Hunters | UBBL Challenge       |    1 |    1 |    1 |      3 |      50 |    8 |    7 |    7 |      2 |    0 |
| Vanadium Hunters | Green Cup V Memorial |    4 |    3 |    5 |     12 | 45.8333 |   18 |   21 |   14 |     -4 |    2 |
| Vanadium Hunters | Green Cup IV         |    4 |    2 |    5 |     11 | 45.4545 |   31 |   25 |    0 |     30 |   -1 |
| Vanadium Hunters | Green Cup VII        |    3 |    7 |    6 |     16 |  40.625 |   30 |   37 |   27 |      7 |    2 |
| Vanadium Hunters | Green Cup Classic 06 |    2 |    2 |    4 |      8 |    37.5 |   15 |   19 |   10 |     -3 |    1 |
| Vanadium Hunters | Green Cup III        |    3 |    1 |    6 |     10 |      35 |   20 |   23 |    0 |      3 |   -1 |
| Vanadium Hunters | Green Cup I          |    3 |    1 |    6 |     10 |      35 |   24 |   27 |    0 |     -6 |    1 |
| Vanadium Hunters | Orange Goblet III    |    3 |    2 |    7 |     12 | 33.3333 |   15 |   28 |   18 |    -15 |   -1 |
| Vanadium Hunters | UBBL Challenge V     |    1 |    0 |    2 |      3 | 33.3333 |    5 |    7 |    1 |     -2 |   -1 |
| Vanadium Hunters | Green Cup VIII       |    4 |    2 |   10 |     16 |   31.25 |   28 |   40 |   16 |    -13 |   -1 |
| Vanadium Hunters | UBBL Challenge II    |    0 |    1 |    2 |      3 | 16.6667 |    4 |    8 |    2 |     -6 |   -1 |
| Vanadium Hunters | UBBL Challenge IV    |    0 |    0 |    2 |      2 |       0 |    2 |    8 |    0 |     -2 |   -1 |
| Vanadium Hunters | UBBL Challenge III   |    0 |    0 |    3 |      3 |       0 |    5 |   10 |    1 |     -1 |   -2 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff, mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Vanadium Hunters" ORDER BY mr.win_pct DESC limit 16;
```


## History

They are generally a bad team at the pro level, but they did achieve a Doom Fist in the old-era UBBL. 

### Seasons

The Hunters had never managed to achieve a winning season before the inaugural Open Division Orange Goblet.

#### summary Orange Goblet III

| Team            | round | Location | Result | Home | Away | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|----------|--------|--------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Vanadium Hunters |     1 | Home     | Loss   |    0 |    3 |       9 |    0 |   27 |    2 |        4 |      2 |          0 |    0 |     20 |     0 |    1 |    7 |
| Vanadium Hunters |     2 | Away     | Draw   |    1 |    1 |       7 |    1 |   27 |    2 |        8 |      3 |          0 |    1 |     19 |     1 |    1 |   12 |
| Vanadium Hunters |     3 | Away     | Loss   |    4 |    1 |       8 |    1 |   39 |    2 |        5 |      2 |          0 |    2 |     34 |     0 |    1 |   14 |
| Vanadium Hunters |     5 | Away     | Win    |    1 |    3 |      15 |    3 |   46 |    3 |        4 |      3 |          2 |    2 |     28 |     1 |    1 |   25 |
| Vanadium Hunters |     6 | Home     | Loss   |    0 |    5 |       8 |    0 |   53 |    3 |       10 |      3 |          0 |    2 |     47 |     0 |    1 |   12 |
| Vanadium Hunters |     7 | Home     | Loss   |    2 |    4 |      11 |    2 |   41 |    4 |       17 |      4 |          0 |    0 |     27 |     2 |    1 |   15 |
| Vanadium Hunters |     8 | Home     | Win    |    2 |    0 |      18 |    2 |   31 |    5 |       10 |      6 |          0 |    3 |     23 |     4 |    1 |   22 |
| Vanadium Hunters |     9 | Away     | Draw   |    2 |    2 |      11 |    2 |   54 |    6 |       10 |      6 |          0 |    2 |     24 |     2 |    1 |   21 |
| Vanadium Hunters |    10 | Home     | Loss   |    0 |    2 |       7 |    0 |   16 |    2 |       12 |      2 |          1 |    2 |     23 |     0 |    1 |   13 |
| Vanadium Hunters |    11 | Away     | Loss   |    2 |    0 |       3 |    0 |   17 |    2 |        1 |      2 |          0 |    1 |     16 |     0 |    1 |    9 |
| Vanadium Hunters |    QF | Away     | Win    |    2 |    3 |      17 |    3 |   62 |    5 |       25 |      5 |          0 |    3 |     52 |     2 |    1 |   25 |
| Vanadium Hunters |    SF | Away     | Loss   |    2 |    1 |       8 |    1 |   26 |    3 |       16 |      3 |          0 |    0 |     22 |     0 |    1 |   11 |


```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 30 AND pl.f_tname = "Vanadium Hunters" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Zahida     | 11 |      43 |    0 |  116 |   25 |    93 |    0 |    0 |    1 |    7 |    2 |    1 |           3 |      2 |    4 |    1 |       1 |      0 |   32 |
|    2 | Baz        | 11 |      18 |    4 |   86 |    6 |    31 |    8 |    0 |    2 |   31 |    2 |    1 |           0 |      2 |    3 |    0 |       1 |      0 |   27 |
|    4 | Amata      | 11 |      27 |    4 |  124 |    8 |    -2 |   17 |    1 |    1 |    9 |    1 |    2 |           1 |      4 |    2 |    1 |       0 |      0 |   34 |
|    5 | Mahmud     |  2 |       1 |    0 |    0 |    0 |     0 |    1 |    0 |    0 |    9 |    0 |    0 |           0 |      1 |    0 |    1 |       0 |      0 |    0 |
|    6 | Mohan      |  3 |       1 |    0 |    5 |    0 |     0 |    1 |    0 |    0 |    9 |    1 |    0 |           0 |      0 |    1 |    1 |       0 |      0 |    0 |
|    7 | Kondwani   |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|    8 | Mayflower  | 11 |       1 |    1 |    9 |    0 |     0 |    1 |    0 |    2 |   50 |    1 |    0 |           0 |      0 |    4 |    0 |       1 |      0 |    7 |
|    9 | Mor        | 12 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   38 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    7 |
|   10 | Kalyani    | 12 |       3 |    1 |    0 |    0 |     0 |    0 |    0 |    1 |   46 |    2 |    0 |           0 |      0 |    1 |    1 |       1 |      0 |    5 |
|   11 | Anastazija | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    0 |    2 |           0 |      0 |    0 |    0 |       1 |      0 |   10 |
|   12 | Leifur     | 10 |       5 |    0 |    9 |    0 |     0 |    1 |    0 |    1 |   13 |    0 |    1 |           0 |      1 |    1 |    2 |       1 |      0 |    7 |
|   13 | Bozena     |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    5 |
|   14 | Nanuli     |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    5 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   15 | Farhan     | 11 |      14 |    4 |   64 |    0 |     0 |    8 |    1 |    0 |    1 |    0 |    0 |           0 |      1 |    2 |    2 |       1 |      0 |   14 |
|   15 | Erastos    | 12 |       5 |    1 |   21 |    0 |     0 |    4 |    0 |    4 |   28 |    3 |    0 |           0 |      1 |    3 |    3 |       0 |      0 |   11 |
|   16 | Leutgard   | 10 |       1 |    0 |    5 |    0 |     0 |    0 |    1 |    3 |   43 |    0 |    1 |           0 |      0 |    0 |    2 |       0 |      0 |   13 |
|   86 | Shufen.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |
|   87 | Zhen.      |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   17 |    0 |    2 |           0 |      0 |    5 |    0 |       1 |      1 |   12 |
|   90 | Yaling.    |  9 |       2 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   11 |    0 |    0 |           1 |      0 |    3 |    2 |       1 |      1 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Orange Goblet III" AND pl.f_tname = "Vanadium Hunters" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

#### projection Next Season

W-D-L ?-?-?

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| *HalfJack* | Thrower |  ?? | ?? | ?? | 51 | 5 | 84 | 0 | 1 | 1 | 0 | 5 | 128 |
| *Moseh* | Blitzer |  ?? | ?? | ?? | 51 | 25 | 9 | 2 | 6 | 1 | 0 | 4 | 122 |
| *Nyazi* | Blitzer | ?? | ?? | ?? | 51 | 28 | 5 | 1 | 7 | 3 | 0 | 2 | 121 |
| **[[Amata]]**     | Catcher  |   15 |    7 |   21 |   43 |   25 |   16 |    2 |    0 |    1 |    1 |    4 |  119 |
| *Gabriel* | Thrower | ?? | ?? | ?? | 49 | 1 | 62 | 0 | 1 | 1 | 0 | 6 | 99 |
| **[[Melchor]]**   | Thrower  |   16 |   10 |   30 |   56 |    0 |   68 |    0 |    2 |    0 |    0 |    8 |  112 |
| *Kikin* | Catcher |  ?? | ?? | ?? | 46 | 22 | 5 | 0 | 0 | 0 | 5 | 98 |
| *Vrej* | Blitzer | ?? | ?? | ?? | 40 | 6 | 1 | 0 | 10 | 11 | 1 | 6 | 93 |
| **[[Gautstafr]]** | Catcher  |   10 |    4 |   11 |   25 |   21 |    4 |    4 |    0 |    0 |    0 |    3 |   90 |
| *Teague* | Blitzer |  ?? | ?? | ?? | 51 | 7 | 0 | 1 | 7 | 5 | 5 | 6 | 87 |
| **[[Baz]]**       | Thrower  |   10 |    9 |   21 |   40 |    6 |   38 |    1 |    3 |    0 |    1 |    3 |   81 |
| Marta    | Blitzer  |   17 |   16 |   24 |   57 |    8 |    0 |    3 |   11 |    7 |    2 |    2 |   80 |
| **[[Mayflower]]** | Lineman  |   30 |   19 |   44 |  93 |    1 |    2 |    2 |    8 |    0 |    2 |    8 |   69 |
| **[[Charles]]**   | Thrower  |   15 |   10 |   16 |   41 |    1 |   38 |    0 |    1 |    2 |    0 |    4 |   67 |
| Daley    | Blitzer  |    6 |    4 |   18 |   28 |   12 |    0 |    1 |    2 |    1 |    1 |    3 |   61 |
| **[[Boguslaw]]**  | Heavy     |   15 |   15 |   21 |   51 |    0 |    1 |    0 |   16 |    6 |    0 |    3 |   60 |
| Majken   | Catcher  |    8 |    9 |   18 |   35 |   10 |    3 |    0 |    0 |    0 |    0 |    5 |   58 |
| Leibniz  | Blitzer  |   10 |   14 |   19 |   43 |    9 |    1 |    0 |    2 |    2 |    1 |    4 |   58 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int", sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Vanadium Hunters" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

There's a lot of history in the list of star Hunters, but modern-era success has been minimal. [[Vrej]] came back from a fine retirement to play in the Green Cup V Memorial tournament and while that was enough to push him up the all-time Hunters hall of fame, it also cost him his career. [[Mayflower]] is sometimes credited with playing more in th old-era than is true. His real first season was GCIV.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    5 | [[Mahmud]]   | Blitzer  |       5 |      1 | 150000 |     0 |
|   24 | [[Leibniz]] | Blitzer  |       6 |      1 | 170000 |     0 |
|   81 | [[Kobe]]    | Thrower  |       2 |      1 | 110000 |     0 |
|   85 | [[Vrej]]    | Blitzer  |       3 |      1 | 150000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Vanadium Hunters" GROUP BY pl.name ORDER BY pl.nr ASC;
```


### Management

The Noordennen family that runs the Hunters were the first to jump on the free agency model, using some of their Orange Goblet winnings to purchase [[donat]] from the [Badger Claws](badgerclaws).

### Fans

Their fans love their traditional style and get really angry at teams like the [Kaiju Dynamo](kaijudynamo) who try new-fangled approaches to the game. That it hasn't been very successful, well maybe that will change in OGII.

### Famous Games

The Green Cup V Memorial tournament saw the Hunters knock off the first-seed [Old Wyrms](oldwyrms) in the opening round of the playoffs. Granted, this was a street-level match with no real implications.