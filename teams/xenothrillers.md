# Xeno Thrillers

The Thrillers have a lot of longevity as an Open Division team, actually playing the most games outside the Pros. Part of this is because they have been generally fine. Some good seasons and some bad. More bad. No one expected them to win the fifth UBBL Challenge [[team1stplace#ucv]] but they did and are now going to the big show.

## Playbook

Nova-Unglewort takes a similar approach to the traditional Unglewort playbook, but generally skews a little faster and more fragile. Instead of 4 generalist runners, two are specialized as attacking blitzers. The blockers are generally used more as roadblocks

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Herodotus  | Runner   |   23 |       2 |    7 |         0 | 120000 |     0 |
|    2 | Nagendra   | Runner   |   64 |       5 |   27 |         2 | 160000 |     0 |
|    3 | Olga       | Attacker |   62 |       8 |   33 |         2 | 200000 |     0 |
|    4 | Shantanu   | Attacker |   86 |       9 |   49 |         3 | 220000 |     0 |
|    5 | Geretrudis | Blitzer  |    7 |       3 |   20 |         1 | 120000 |     0 |
|    6 | Aljaz      | Blitzer  |   53 |       9 |   58 |         4 | 170000 |     0 |
|    7 | Nashwa     | Line     |   26 |       6 |   39 |         3 |  80000 |     0 |
|    8 | Methusaleh | Line     |   22 |       7 |   39 |         3 |  90000 |     0 |
|    9 | Apostol    | Blocker  |    2 |       2 |    9 |         1 | 110000 |     0 |
|   10 | Brittany   | Blocker  |   41 |       9 |   56 |         4 | 170000 |     0 |
|   11 | Tacita     | Line     |   52 |       5 |   41 |         3 | 120000 |     0 |
|   12 | Inga       | Line     |   37 |       9 |   49 |         3 | 100000 |     0 |
|   13 | Janice     | Line     |    0 |       1 |    1 |         0 |  40000 |     0 |
|   14 | Cnaeus     | Line     |   14 |       7 |   39 |         3 |  70000 |     0 |
|   15 | Federikka  | Line     |    5 |       2 |    4 |         0 |  40000 |     0 |
|   16 | Ingeborg   | Line     |    0 |       1 |    1 |         0 |  40000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Florentino | Runner   |   31 |       3 |   19 |         1 | 130000 |     0 |
|    3 | Tahti      | Attacker |   34 |       3 |   20 |         1 | 240000 |     0 |
|    4 | Nahor      | Attacker |   32 |       1 |   10 |         1 | 190000 |     0 |
|    8 | Virginia   | Line     |   23 |       9 |   47 |         3 |  80000 |     0 |
|    9 | Dolf       | Blocker  |   19 |       8 |   41 |         3 | 150000 |     0 |
|   16 | Rosa       | Line     |    0 |       2 |    2 |         0 |  40000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Xeno Thrillers" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```


## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Xeno Thrillers | Open     |   21 |    6 |   29 |   56 | 43.097 |   96 |  110 |   77 |      15 |    2 |
| Xeno Thrillers | Street   |    1 |    1 |    0 |    2 | 75.000 |    6 |    4 |    6 |       4 |    2 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Xeno Thrillers" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```


### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Xeno Thrillers |   22 |    7 |   29 |   58 | 46.641 |  102 |  114 |   83 |      19 |    4 |

```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Xeno Thrillers" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* UBBL Challenge V - Champion [[team1stplace#ucv]] 
* UBBL Challenge IV - Runner-Up [[team2ndplace#uciv]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Thrillers | **UBBL Challenge V** |  5 |    1 |    0 |      6 | 91.6667 |   14 |    6 |    7 |      4 |    3 |
| Thrillers | UBBL Challenge IV  |    5 |    0 |    1 |      6 | 83.3333 |   14 |   10 |   11 |      3 |    4 |
| Thrillers | StUBBL Scramble    |    1 |    1 |    0 |      2 |      75 |    6 |    4 |    4 |      4 |    2 |
| Thrillers | Orange Goblet II   |    4 |    1 |    6 |     11 | 40.9091 |   21 |   21 |   13 |      3 |   -1 |
| Thrillers | UBBL Challenge III |    2 |    0 |    3 |      5 |      40 |   12 |   10 |   10 |      3 |   -1 |
| Thrillers | UBBL Challenge II  |    1 |    1 |    2 |      4 |    37.5 |    5 |    9 |    4 |     -1 |    2 |
| Thrillers | Orange Goblet      |    3 |    2 |    6 |     11 | 36.3636 |   19 |   20 |    9 |      3 |   -2 |
| Thrillers | Orange Goblet III  |    1 |    1 |    8 |     10 |      15 |    6 |   22 |    8 |      0 |   -3 |
| Thrillers | UBBL Challenge     |    0 |    0 |    3 |      3 |       0 |    5 |   12 |    3 |      0 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Thrillers" ORDER BY mr.win_pct DESC limit 15;
```

## History


### Seasons


#### summary UBBL Challenge V

| Team            | round | Location | Result | Home | Away | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|----------|--------|--------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Xeno Thrillers |     2 | Home     | Draw   |    2 |    2 |      13 |    2 |   60 |    2 |       10 |      2 |          0 |    2 |     39 |     2 |    1 |   17 |
| Xeno Thrillers |     3 | Away     | Win    |    1 |    3 |       9 |    3 |   55 |    2 |        4 |      2 |          0 |    2 |     43 |     1 |    1 |   20 |
| Xeno Thrillers |   251 | Away     | Win    |    0 |    1 |       9 |    1 |   27 |    0 |        0 |      0 |          0 |    1 |     36 |     1 |    1 |   10 |
| Xeno Thrillers |   252 | Home     | Win    |    4 |    2 |      11 |    4 |   64 |    1 |        2 |      1 |          2 |    0 |     61 |     0 |    1 |   22 |
| Xeno Thrillers |   253 | Home     | Win    |    2 |    0 |       7 |    2 |   30 |    0 |        0 |      0 |          0 |    1 |     43 |     0 |    1 |   13 |
| Xeno Thrillers |   255 | Away     | Win    |    1 |    2 |       5 |    2 |   43 |    0 |        0 |      0 |          1 |    1 |     41 |     1 |    1 |   15 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 31 AND pl.f_tname = "Xeno Thrillers" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```


#### roster UBBL Challenge V

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Florentino |  5 |      24 |    3 |   42 |    3 |    12 |    1 |    0 |    0 |    2 |    0 |    0 |           0 |      1 |    0 |    1 |       0 |      0 |   12 |
|    1 | Herodotus  |  6 |      14 |    6 |  151 |    0 |     0 |    2 |    0 |    0 |    3 |    0 |    1 |           0 |      1 |    1 |    0 |       0 |      0 |   23 |
|    2 | Nagendra   |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    3 | Tahti      |  5 |       5 |    2 |   28 |    1 |     3 |    1 |    0 |    0 |   36 |    2 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    7 |
|    3 | Olga       |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   16 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    4 | Shantanu   |  6 |       3 |    1 |   25 |    1 |     1 |    0 |    0 |    1 |   46 |    1 |    1 |           0 |      0 |    0 |    0 |       1 |      0 |   11 |
|    5 | Geretrudis |  6 |       5 |    1 |   12 |    0 |     0 |    0 |    1 |    0 |   18 |    1 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    5 |
|    6 | Aljaz      |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   33 |    1 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    9 |
|    7 | Nashwa     |  6 |       1 |    1 |   12 |    0 |     0 |    0 |    1 |    1 |   15 |    0 |    1 |           0 |      0 |    1 |    0 |       0 |      0 |   12 |
|    8 | Virginia   |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   22 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|    9 | Apostol    |  4 |       1 |    0 |    4 |    0 |     0 |    1 |    0 |    1 |   17 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|    9 | Dolf       |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    8 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   10 | Brittany   |  6 |       1 |    0 |    5 |    0 |     0 |    0 |    1 |    1 |   32 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    4 |
|   11 | Tacita     |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    4 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|   12 | Inga       |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    9 |    0 |    2 |           0 |      0 |    0 |    0 |       0 |      0 |   10 |
|   15 | Federikka  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   16 | Ingeborg   |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "UBBL Challenge V" AND pl.f_tname = "Xeno Thrillers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

#### Projection GCXII

W-D-L 5-1-9

The Thrillers overachieved by winning the UCV tournament and getting an expansion slot in the Green Cup. Coming off of their 1-Win Orange Goblet campaign which would have seen them dropped from the next OG tournament, we can't expect a lot from these upstarts.


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Nanna        | Runner   |    7 |    4 |   13 |   24 |   11 |   32 |    2 |    1 |    0 |    0 |    3 |   86 |
| **Shantanu** | Attacker |   19 |    7 |   23 |   49 |   17 |    1 |    1 |    9 |    1 |    1 |    2 |   86 |
| **Nagendra** | Runner   |   12 |    2 |   13 |   27 |   11 |   12 |    1 |    1 |    0 |    0 |    3 |   64 |
| **Olga**     | Attacker |   13 |    4 |   16 |   33 |   12 |    1 |    0 |    3 |    2 |    0 |    3 |   62 |
| **Aljaz**    | Blitzer  |   22 |    7 |   29 |   58 |    4 |    2 |    1 |   10 |    1 |    0 |    3 |   53 |
| **Tacita**   | Line     |   18 |    3 |   20 |   41 |    0 |    0 |    0 |    1 |    0 |    0 |   10 |   52 |
| Aslaug       | Runner   |    4 |    3 |    7 |   14 |   10 |   11 |    0 |    0 |    1 |    0 |    0 |   43 |
| **Brittany** | Blocker  |   22 |    7 |   27 |   56 |    0 |    0 |    2 |    3 |    2 |    1 |    5 |   41 |
| **Inga**     | Line     |   17 |    7 |   25 |   49 |    0 |    0 |    0 |    0 |    0 |    1 |    7 |   37 |
| **Tahti**    | Attacker |    7 |    2 |   11 |   20 |    4 |    1 |    1 |    0 |    1 |    1 |    3 |   34 |
| **Nahor**    | Attacker |    4 |    1 |    5 |   10 |    8 |    1 |    1 |    0 |    0 |    0 |    1 |   32 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Xeno Thrillers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    3 | Olga   | Attacker |       8 |      1 | 200000 |     0 |
|   11 | Tacita | Line     |       5 |      1 | 120000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Xeno Thrillers" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

### Fans


### Famous Games

UBBL Challenge V championship game (mostly for the final play).


