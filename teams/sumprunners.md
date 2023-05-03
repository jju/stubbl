# Sump Runners

They were once thought to be the future of BludBol in the old era UBBL, and were set to play in Green Cup V before the interruption. They've never lived up to that, though they tend to be better in Open Division play. They lean on the passing game which can make them more fun to watch than other teams with a similar playbook.

## Playbook

The Sump Runners use the Hermann playbook, the original plan for playing BludBol, and the one that every other strategy is an adaptation of. The team has two thrower positions available, 4 catchers, 4 blitzers, a big guy and fills out the rest of the lineup with undistinguished concussion-fodder. In actuality, most Hermann teams don't use all their specialist receivers, trusting more to a running game with the blitzers. The Sump Runners have some oddities in their lineup including using one of their thrower slots as a makeshift blitzer.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Shay    | Thrower  |  Superstar |       5 |   52 |         3 | 190000 |     0 |
|    2 | Ulvi    | Thrower  |  Experienced |       1 |    1 |         0 |  90000 |     0 |
|    3 | Xesus   | Blitzer  |  Veteran |       2 |   13 |         1 | 150000 |     0 |
|    4 | Metin   | Catcher  |  Superstar |       4 |   37 |         2 | 170000 |     0 |
|    5 | Danae   | Blitzer  |  Superstar |       6 |   56 |         4 | 240000 | 40000 |
|    6 | Pol     | Blitzer  |  Superstar |       4 |   38 |         3 | 230000 | 30000 |
|   10 | Grimnus | Line  |  Rookie |       1 |    6 |         0 |  50000 |     0 |
|   13 | Umar    | Line  |  Rookie |       1 |    2 |         0 |  50000 |     0 |
|   14 | Gulnar  | Line  |  Rookie |       1 |    1 |         0 |  50000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
| 21 | Ulvi     | Thrower   |    Experienced |       1 |    1 |         0 |  90000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    7 | Eylul     | Line  | Seasoned Veteran |       5 |   53 |         4 | 150000 | 40000 |
|    8 | Hoss      | Line  | Star |      10 |  103 |         7 | 220000 | 70000 |
|    9 | Edgar     | Line  | Star |       9 |   89 |         6 | 200000 | 60000 |
|   11 | Agus      | Line  | Veteran |       3 |   15 |         1 | 110000 | 10000 |
|   12 | Sille     | Line  | Experienced |       3 |   15 |         1 |  80000 | 10000 |
|   15 | Zdislava  | Blitzer  | Seasoned Veteran |       4 |   37 |         2 | 170000 | 20000 |
|   21 | Jacquetta | Line  |  Superstar |       6 |   60 |         4 | 260000 | 40000 |
|   34 | Tine      | Catcher  | Star |       7 |   61 |         4 | 160000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "TC Sump Runners" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

Yes, we foresee this 0 bench players situation will end up being a major problem if the Sump Runners want to win. Two superstars cannot carry a team in the UBBL.

## Records

### Record by Division

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|-------------------|------|------|---------------|----------------|------------|
| TC Sump Runners | Pro      |   20 |   18 |   50 |   88 | 34.375 |  166 |  224 |           155 |              3 |        -13 |
| TC Sump Runners | Open     |   11 |    0 |    7 |   18 | 60.416 |   45 |   36 |            28 |             -5 |          7 |


```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "TC Sump Runners" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record (W-D-L)

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| TC Sump Runners |   31 |   18 |   57 |  106 | 44.792 |  211 |  260 |  183 |      -2 |   -6 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "TC Sump Runners" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* UBBL Challenge II - Most Improved [[team3rdplace]]
* UBBL Challenge III - Runner-Up [[team2ndplace]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| TC Sump Runners | UBBL Challenge III   |    3 |    0 |    1 |      4 |      75.00 |   12 |    8 |    8 |     -2 |    3 |
| TC Sump Runners | UBBL Challenge II    |    4 |    0 |    2 |      6 | 66.67 |   15 |    9 |   11 |      2 |    3 |
| TC Sump Runners | Green Cup Classic 06 |    2 |    4 |    2 |      8 |      50.00 |   16 |   15 |   11 |      0 |   -3 |
| TC Sump Runners | UBBL Challenge IV    |    2 |    0 |    2 |      4 |      50.00 |   10 |    9 |    3 |     -5 |    2 |
| TC Sump Runners | UBBL Challenge       |    2 |    0 |    2 |      4 |      50.00 |    8 |   10 |    4 |      0 |   -1 |
| TC Sump Runners | Green Cup IX         |    5 |    4 |    7 |     16 |   43.75 |   37 |   38 |   33 |      7 |   -2 |
| TC Sump Runners | Green Cup VII        |    5 |    2 |    9 |     16 |    37.50 |   35 |   39 |   24 |      7 |    2 |
| TC Sump Runners | Green Cup VIII       |    4 |    2 |   10 |     16 |   31.25 |   29 |   40 |   31 |      5 |   -2 |
| TC Sump Runners | Green Cup X          |    3 |    2 |   11 |     16 |      25.00 |   23 |   46 |   28 |     -4 |   -4 |
| TC Sump Runners | Green Cup XI         |    1 |    4 |   11 |     16 |   18.75 |   26 |   46 |   19 |    -12 |   -4 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "TC Sump Runners" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Sump Runners have never had a winning Pro-Level season.

### Seasons

Before the interruption the Sump Runners were a fascinating glimpse of what a Hermann-based team could do. Sadly all the records of those matches were lost. When the Green Cup Classic organizers were looking for teams to fill out their divisions the Sump Runners name was important to bring in. That they were owned by the TyrolCorp entity made things a bit more difficult. The team has done its best to put entertaining BludBol out there, but their best pro season was their first one, and even then they only won half their matches.

After another dismal GCVIII the TC Sump Runners were facing relegation in the second UBBL Challenge tournament but fought their way to a third place prize. 

They were playing in UBBL Challenge III voluntarily and had their own undefeated run going mowing down challengers in the B-Side until the [Arborist](arborealmenace) scoring threat proved too much in the final.

Green Cup X saw the team play putridly and they again faced relegation in UBBL Challenge IV, where they managed to get a couple of wins and preserved their attempts for the Green Cup.

#### Projection GCXI

W-D-L 6-0-9

If the Sump Runners don't come in last place in the Stacks, practically the entire BludBol watching population will be surprised. They are starting out the season with a payroll just above the Value Floor instituted to prevent egregious tanking attempts and are in a division that has teams who've won 60% of the Green Cups between them.

#### summary GCXI

The TC Sump Runners were not projected to be good this season and the projections were wildly optimistic. They tied the Brutes for the third-worst Green Cup season in history with their 1-4-11 record. So yes, they hit last-place in the Stacks and the season. They didn't run afoul of the new playoff roster rules and so they didn't really bother rotating players through the lineup. By the end of the season many of the players launched contract renegotiations which management wasn't very eager to honour so we may be seeing a bunch of free agents available for the upcoming expansion.

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| TC Sump Runners |     1 |       6 |    2 |   20 |    4 |       12 |      3 |          0 |    3 |     30 |     1 |    1 |   21 |           2 |           2 |
| TC Sump Runners |     2 |       3 |    1 |   12 |    2 |       16 |      2 |          0 |    2 |     39 |     0 |    1 |   14 |           1 |           4 |
| TC Sump Runners |     3 |       9 |    2 |   58 |    5 |        8 |      5 |          0 |    1 |     56 |     2 |    1 |   18 |           2 |           2 |
| TC Sump Runners |     4 |       6 |    3 |   58 |    8 |       19 |      8 |          0 |    0 |     46 |     2 |    1 |   22 |           3 |           5 |
| TC Sump Runners |     5 |       6 |    3 |   61 |    5 |       17 |      5 |          0 |    4 |     40 |     0 |    1 |   27 |           5 |           3 |
| TC Sump Runners |     6 |       1 |    0 |   16 |    0 |        0 |      0 |          0 |    0 |     20 |     0 |    1 |    5 |           2 |           0 |
| TC Sump Runners |     7 |       1 |    3 |   27 |    5 |       11 |      5 |          0 |    1 |     29 |     0 |    1 |   21 |           3 |           2 |
| TC Sump Runners |     8 |       1 |    3 |   44 |    3 |        4 |      3 |          1 |    2 |     57 |     2 |    1 |   23 |           3 |           3 |
| TC Sump Runners |     9 |       5 |    2 |   40 |    1 |        1 |      1 |          1 |    1 |     56 |     2 |    1 |   16 |           2 |           2 |
| TC Sump Runners |    10 |       7 |    2 |   45 |    3 |       11 |      3 |          1 |    0 |     41 |     1 |    1 |   16 |           3 |           2 |
| TC Sump Runners |    11 |       3 |    1 |   42 |    2 |        6 |      2 |          1 |    2 |     43 |     4 |    1 |   16 |           1 |           2 |
| TC Sump Runners |    12 |       3 |    2 |   81 |    1 |        1 |      2 |          0 |    2 |     28 |     1 |    1 |   16 |           6 |           2 |
| TC Sump Runners |    13 |       2 |    0 |   22 |    2 |        6 |      2 |          0 |    1 |     17 |     0 |    1 |    9 |           0 |           2 |
| TC Sump Runners |    14 |       3 |    1 |   23 |    3 |        8 |      3 |          0 |    0 |     18 |     0 |    1 |   11 |           2 |           1 |
| TC Sump Runners |    15 |       6 |    1 |   24 |    3 |       11 |      3 |          0 |    0 |     31 |     1 |    1 |   11 |           1 |           3 |
| TC Sump Runners |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    0 |    0 |           1 |           0 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "TC Sump Runners" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster gcxi

| nr   | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Shay       | 14 |      41 |    0 | **139** |   20 |    51 |   11 |    2 |    0 |    6 |    0 |    0 |           6 |      6 |    2 |    1 |       1 |      0 |   24 |
|    2 | Jacquetta  | 14 |      40 |    1 |   75 | **21** | **62** |    4 |    0 |    4 |   20 |    0 |    1 |           1 |      3 |    3 |    0 |       1 |      0 |   37 |
|    3 | Xesus      | 11 |      11 |    7 |   63 |    1 |    -1 |    8 |    0 |    0 |   25 |    0 |    2 |           0 |      3 |    5 |    0 |       0 |      0 |   32 |
|    4 | Metin      | 15 |      22 | **10** |  112 |    1 |     1 | **14** |    1 |    0 |   25 |    1 |    3 |           0 |      5 |    2 |    1 |       1 |      0 | **48** |
|    5 | Danae      | 16 |       1 |    2 |   17 |    0 |     0 |    1 |    0 |    3 | **130** | **6** |    1 |           0 |      0 |    4 |    2 |       0 |      0 |   17 |
|    6 | Pol        | 14 |      27 |    5 |  137 |    1 |     7 |    7 |    1 |    1 |   34 |    3 |    1 |           0 |      6 |    2 |    1 |       0 |      0 |   25 |
|    7 | Eylul      | 15 |       2 |    0 |    4 |    0 |     0 |    1 |    0 |    2 |   72 |    2 |    0 |           1 |      0 |    3 |    4 |       1 |      0 |    4 |
|    8 | Hoss       | 16 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   52 |    0 |    1 |           0 |      0 |    3 |    3 |       0 |      0 |    9 |
|    9 | Edgar      | 11 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   41 |    2 |    1 |           0 |      0 |    1 |    0 |       2 |      0 |    7 |
|   10 | Grimnus    |  6 |       3 |    0 |    4 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    4 |    1 |       1 |      0 |    0 |
|   11 | Agus       | 12 |       1 |    0 |    1 |    0 |     0 |    0 |    0 |    1 |   28 |    0 |    3 |           0 |      0 |    1 |    2 |       3 |      0 |   17 |
|   12 | Sille      | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   44 |    1 |    1 |           0 |      0 |    2 |    0 |       0 |      0 |    7 |
|   13 | Umar       |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|   14 | Gulnar     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       1 |      0 |    0 |
|   15 | Zdislava   | 14 |       1 |    1 |    8 |    0 |     0 |    1 |    0 |    2 |   58 |    0 |    0 |           0 |      0 |    5 |    2 |       1 |      0 |    7 |
|   21 | Ulvi       |  1 |       6 |    0 |   13 |    3 |    11 |    0 |    0 |    0 |    0 |    0 |    1 |           0 |      0 |    0 |    0 |       1 |      0 |    8 |
|   83 | Gaenor     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    4 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      R |    2 |
|   86 | Prakash    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    4 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    2 |
|   99 | Berger     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |


```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "TC Sump Runners" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player    | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|-----------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Jacquetta | Line     |   18 |   10 |   32 |   60 |    4 |  107 |    2 |    2 |    2 |    2 |    9 |  180 |
| **Shay**  | Thrower  |   14 |   10 |   28 |   52 |   15 |   70 |    7 |    0 |    0 |    1 |    4 |  151 |
| Desmond   | Blitzer  |   17 |    8 |   26 |   51 |    9 |    1 |    2 |   16 |   10 |    1 |    2 |   96 |
| Gaenor    | Blitzer  |   12 |    6 |   19 |   37 |    9 |   28 |    7 |    2 |    1 |    0 |    4 |   95 |
| Persimmon | Thrower  |   17 |    8 |   21 |   46 |   16 |   27 |    0 |    2 |    0 |    0 |    3 |   94 |
| **Metin** | Catcher  |    8 |    6 |   23 |   37 |   20 |    1 |    1 |    0 |    0 |    0 |    6 |   93 |
| Edwin     | Blitzer  |   22 |   10 |   27 |   59 |   11 |    1 |    0 |   13 |    8 |    3 |    2 |   92 |
| **Pol**   | Blitzer  |    9 |    5 |   24 |   38 |   17 |    2 |    1 |    3 |    1 |    2 |    4 |   87 |
| Hoss      | Line     |   31 |   18 |   54 |  103 |    3 |    0 |    1 |    7 |    0 |    2 |    8 |   69 |
| Stultz    | Catcher  |   17 |    7 |   29 |   53 |   17 |    1 |    1 |    1 |    0 |    0 |    2 |   66 |
| Tine      | Catcher  |   21 |    9 |   31 |   61 |   13 |    3 |    0 |    1 |    0 |    0 |    4 |   64 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "TC Sump Runners" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

The Sump Runners play a slightly unorthodox version of the traditional allrounder Hermann strategy. [[jacquetta]] actually plays the role of a traditional Thrower, while [[shay]]'s positioning is more like a Blitzer.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "TC Sump Runners" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

One of the first UBBL teams owned by a corporate entity from upspire (TyrolCorp) instead of a more traditional bludbol concern, many fans are cynical about the commitment of the team.

### Fans

In the past the [Vanadium Hunters](vanadiumhunters) were the Sump Runners' chief rivals, but with them relegated to the Open Division it's slim pickings. They had a devastating loss to the [Arboreal Menace](arborealmenace) in the third UBBL Challenge tournament, which may spark something moving on. The absolute drubbing they took in GCX shed fans by the bandwagonload.

### Famous Games

The Sump Runners haven't had a lot of great moments in the UBBL.