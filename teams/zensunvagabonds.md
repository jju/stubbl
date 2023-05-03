# Zensun Vagabonds

Usually credited along with the [Old Wyrms](oldwyrms) as the founders of the UBBL, the Vagabonds have a long history in fans' minds of not being great. Which is kind of funny as they did almost win the Green Cup once back in the Old-Era.

## Playbook

The Vagabonds use the Hermann playbook, the original plan for playing BludBol, and the one that every other strategy is an adaptation of. The team has two thrower positions available, 4 catchers, 4 blitzers, a big guy and fills out the rest of the lineup with undistinguished concussion-fodder. Like most Hermann teams, the Vagabonds don't use all their specialist receivers, trusting more to a running game with the blitzers.

## Active Roster

|  # | Player   | Position  | SPP | Seasons |   GP | Contracts | Value | Bonus |
|----|----------|-----------|-----|---------|------|-----------|-------|-------|
|  1 | Clydon   | Thrower  |   73 |       6 |   37 |         2 | 190000 |  20000 |
|  2 | Betuel   | Thrower  |  120 |       4 |   35 |         2 | 210000 |      0 |
|  4 | Padma    | Blitzer  |  156 |       5 |   36 |         2 | 230000 |      0 |
|  5 | Green    | Blitzer  |   16 |       1 |   10 |         1 | 210000 | -30000 |
|  6 | Dene     | Blitzer  |   42 |       6 |   44 |         3 | 150000 |      0 |
|  7 | Breann   | Line  |    7 |       4 |   24 |         2 |  70000 |      0 |
|  8 | Hamza    | Line  |   24 |       7 |   52 |         3 | 130000 |  30000 |
|  9 | Everette | Line  |   14 |       5 |   21 |         1 |  80000 |  10000 |
| 13 | Alphege  | Line  |   19 |       3 |   18 |         1 | 130000 |      0 |
| 15 | Mia      | Blitzer  |   89 |       5 |   37 |         2 | 240000 |  20000 |
| 16 | Zaira    | Heavy    |   66 |       7 |   45 |         3 | 240000 |      0 |

### Depth (on payroll)

|  # | Player    | Position | SPP | Seasons | GP | Contracts | Value | Bonus |
|----|-----------|----------|-----|---------|----|-----------|-------|-------|
| 17 | Voos      | Blitzer  |   20 |       4 |   20 |         1 | 140000 |  10000 |

### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   23 | Ormonde.     | Blitzer  |   61 |       2 |   30 |         2 | 210000 |     0 |
|   25 | Harinder.    | Blitzer  |   24 |       5 |   29 |         2 | 130000 |     0 |
|   31 | Eah.         | Line  |    2 |       1 |    4 |         0 |  50000 |     0 |
|   32 | Joscelin.    | Line  |    2 |       2 |    3 |         0 |  50000 |     0 |
|   33 | Sashka.      | Line  |    0 |       2 |    9 |         1 |  50000 |     0 |
|   39 | Siv.         | Catcher  |   80 |       7 |   43 |         3 | 170000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Zensun Vagabonds" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```



## Records

### Record by Division 

| Team             | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|------------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Zensun Vagabonds | Pro      |   55 |   27 |   62 |  144 | 50.714 |  317 |  353 |  252 |     -19 |    5 |
| Zensun Vagabonds | Open     |    1 |    1 |    3 |    5 | 25.000 |    8 |   10 |    8 |      -1 |   -2 |
| Zensun Vagabonds | Street   |    0 |    1 |    0 |    1 | 50.000 |    0 |    0 |    0 |       0 |    0 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Zensun Vagabonds" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team             | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|------------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Zensun Vagabonds |   56 |   29 |   65 |  150 | 45.523 |  325 |  363 |  260 |     -20 |    3 |

```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Zensun Vagabonds" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* Green Cup II - Runner-Up [[team2ndplace#gcii]]
* Green Cup X - Tough Brake of Alsoran [[team3rdplace#gcx]] 
* Green Cup X - Heaps Division Champions [[teamdivision#gcx]]

### Seasons

| Team      | Season             | W | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Zensun Vagabonds | Champions Circuit  |    1 |    0 |    0 |      1 |     100.00 |    3 |    2 |    3 |      2 |    0 |
| Zensun Vagabonds | Green Cup X        |   11 |    2 |    5 |     18 | 66.67 |   46 |   33 |   29 |      3 |    5 |
| Zensun Vagabonds | Green Cup VII      |    7 |    6 |    3 |     16 |    62.50 |   47 |   32 |   38 |     -1 |    1 |
| Zensun Vagabonds | Green Cup IX       |    7 |    3 |    6 |     16 |  53.13 |   32 |   40 |   19 |    -10 |    1 |
| Zensun Vagabonds | UBBL Challenge II  |    1 |    0 |    1 |      2 |      50.00 |    4 |    4 |    3 |     -3 |    0 |
| Zensun Vagabonds | Green Cup VI       |    5 |    4 |    6 |     15 | 46.67 |   31 |   36 |   31 |     -2 |    2 |
| Zensun Vagabonds | Green Cup II       |    5 |    2 |    6 |     13 | 46.15 |   27 |   32 |   31 |     12 |    1 |
| Zensun Vagabonds | Green Cup I        |    3 |    3 |    5 |     11 | 40.91 |   20 |   25 |   18 |      4 |    1 |
| Zensun Vagabonds | Green Cup III      |    4 |    1 |    6 |     11 | 40.91 |   22 |   28 |   22 |      5 |    0 |
| Zensun Vagabonds | Green Cup VIII     |    6 |    1 |    9 |     16 |  40.63 |   35 |   47 |   22 |    -21 |   -1 |
| Zensun Vagabonds | Green Cup IV       |    1 |    3 |    6 |     10 |      25.00 |   20 |   30 |    0 |     -8 |   -2 |
| Zensun Vagabonds | Green Cup XI       |    5 |    2 |   10 |     17 | 35.2941 |   34 |   48 |   25 |     -3 |   -3 |
| Zensun Vagabonds | UBBL Challenge     |    0 |    1 |    1 |      2 |      25.00 |    2 |    3 |    6 |      3 |   -1 |
| Zensun Vagabonds | UBBL Challenge III |    0 |    0 |    1 |      1 |       0.00 |    2 |    3 |    0 |     -1 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Zensun Vagabonds" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Vagabonds have been getting better as of late.

### Seasons

The Vagabonds have a long history in which they've been fine. They would have been relegated after GCIV if the interruption hadn't happened (which is why they weren't invited to the GCV Memorial Tournament), but since that did happen they were happy to pick things up again in GCVI and keep on being fine for a few cycles.

But then the Green Cup X season was a triumph for the Vagabonds, marred only by the playoff loss. If they can build on that success they could be hoisting the Green Cup. They couldn't live up to the expectations in GCXI but a good showing in UCV has them optimistic.

#### Projection GCXII

W-D-L 6-1-8

The projections are somewhat hard on the Vagabonds, because it's hard to ignore that long history. They'll need to play really well to make the playoffs, where they're going to have some really tough divisional rivals to get through.

#### summary last season

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Zensun Vagabonds |     1 |       6 |    0 |   13 |    2 |       17 |      2 |          0 |    2 |     31 |     1 |    1 |   11 |           2 |           0 |
| Zensun Vagabonds |     2 |      12 |    5 |   62 |    4 |       17 |      4 |          0 |    5 |     43 |     2 |    1 |   34 |           2 |           5 |
| Zensun Vagabonds |     3 |      12 |    1 |   51 |    5 |       14 |      5 |          0 |    0 |     24 |     2 |    1 |   13 |           2 |           1 |
| Zensun Vagabonds |     4 |       9 |    2 |   51 |    4 |        2 |      4 |          0 |    2 |     48 |     2 |    1 |   19 |           2 |           3 |
| Zensun Vagabonds |     5 |      12 |    1 |   31 |    3 |       22 |      2 |          2 |    1 |     31 |     1 |    1 |   17 |           5 |           1 |
| Zensun Vagabonds |     6 |       8 |    1 |   43 |    2 |        5 |      2 |          0 |    0 |     30 |     0 |    1 |   10 |           1 |           2 |
| Zensun Vagabonds |     7 |       9 |    2 |   32 |    3 |       20 |      3 |          0 |    1 |     34 |     1 |    1 |   16 |           2 |           2 |
| Zensun Vagabonds |     8 |      15 |    1 |   69 |    6 |       20 |      6 |          0 |    0 |     32 |     0 |    1 |   14 |           6 |           1 |
| Zensun Vagabonds |     9 |      10 |    2 |   40 |    3 |       26 |      3 |          1 |    1 |     29 |     1 |    1 |   18 |           3 |           2 |
| Zensun Vagabonds |    10 |      15 |    3 |   58 |    4 |        8 |      4 |          1 |    0 |     34 |     2 |    1 |   20 |           3 |           2 |
| Zensun Vagabonds |    11 |      16 |    5 |   61 |    4 |       25 |      4 |          0 |    3 |     38 |     1 |    1 |   30 |           5 |           1 |
| Zensun Vagabonds |    12 |      10 |    1 |   14 |    2 |        5 |      2 |          1 |    0 |     11 |     1 |    1 |   12 |           1 |           1 |
| Zensun Vagabonds |    13 |      16 |    0 |   64 |    7 |       25 |      7 |          0 |    1 |     24 |     0 |    1 |   14 |           0 |           7 |
| Zensun Vagabonds |    14 |      11 |    3 |   70 |    4 |       17 |      4 |          0 |    5 |     46 |     1 |    1 |   28 |           2 |           3 |
| Zensun Vagabonds |    15 |       6 |    1 |   16 |    1 |        4 |      1 |          0 |    0 |     17 |     1 |    1 |    9 |           1 |           2 |
| Zensun Vagabonds |   R16 |      13 |    4 |   57 |    6 |       31 |      6 |          0 |    1 |     27 |     1 |    1 |   25 |           3 |           4 |
| Zensun Vagabonds |    QF |      10 |    2 |   40 |    4 |       15 |      4 |          0 |    3 |     33 |     0 |    1 |   21 |           3 |           2 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Zensun Vagabonds" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Rohit       | Blitzer  |   20 |   12 |   19 |   51 |    7 |    1 |    1 |   39 |   12 |    1 |    6 |  158 |
| **Padma**        | Blitzer  |   17 |    5 |   14 |   36 |   41 |    1 |    0 |    3 |    2 |    1 |    4 |  156 |
| Subrahmanya | Thrower  |   21 |   11 |   22 |   54 |    1 |   96 |    0 |    1 |    0 |    0 |    5 |  126 |
| Lucrece     | Catcher  |   24 |   14 |   24 |   62 |   27 |    3 |    2 |    1 |    1 |    0 |    6 |  122 |
| **Betuel**       | Thrower  |   17 |    5 |   13 |   35 |    2 |   86 |    0 |    2 |    2 |    0 |    4 |  120 |
| Jonah       | Catcher  |   16 |    5 |   13 |   34 |   24 |   10 |    2 |    0 |    0 |    0 |    4 |  106 |
| Bahiyya     | Blitzer  |   16 |   12 |   14 |   42 |   29 |    1 |    3 |    2 |    2 |    0 |    0 |  102 |
| Shy Hulud    | Heavy    |   30 |   21 |   39 |   90 |    0 |    1 |    0 |   16 |    10 |    3 |    7 |   94 |
| *Mahdi*      | Thrower  | ?? | ?? | ?? | 45 | 4 | 65 | 0 | 0 | 0 | 0 | 3 | 92 |
| **Mia**          | Blitzer  |   16 |    5 |   16 |   37 |   14 |    6 |    5 |    6 |    1 |    1 |    3 |   89 |
| *Paul*       | Thrower  | ?? | ?? | ?? | 45 | 4 | 25 | 1 | 3 | 1 | 0 | 7 | 82 |
| *Korba*      | Catcher  | ?? | ?? | ?? | 44 | 15 | 4 | 0 | 0 | 1 | 0 | 6 | 81 |
| Siv        | Catcher  |   18 |    8 |   17 |   43 |   20 |    3 |    1 |    0 |    0 |    0 |    3 |   80 |
| **Clydon**       | Thrower  |   18 |    5 |   14 |   37 |    2 |   31 |    2 |    1 |    0 |    0 |    6 |   73 |
| **Zaira**        | Heavy     |   23 |    7 |   15 |   45 |    1 |    0 |    1 |   10 |    5 |    3 |    5 |   66 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Zensun Vagabonds" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

[[jonah]] and [[Clydon]] were being forced into the role of faces of the franchise before they were really ready. [[betuel]] is rapidly rising in the ranks, and has a plethora of talented players ready to make catches and get the ball into endzones.

The Vagabonds miss the days of having [[hulud]] anchoring their lineup, but [[Zaira]] is coming along as a more than competent replacement.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|   76 | Shy Hulud | Heavy   |       8 |      2 | 230000 |     0 |
|   85 | Rohit    | Blitzer  |       7 |      2 | 190000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Zensun Vagabonds" GROUP BY pl.name ORDER BY pl.nr ASC;
```

#### GCXI roster

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Clydon      |  7 |       7 |    0 |   13 |    4 |    18 |    1 |    0 |    0 |    9 |    1 |    2 |           1 |      1 |    2 |    0 |       0 |      0 |   14 |
|    2 | Betuel      | 16 |      73 |    0 |  197 |   51 |   231 |    2 |    0 |    3 |   10 |    1 |    1 |           5 |      1 |    6 |    1 |       0 |      0 |   62 |
|    4 | Padma       | 16 |      35 |   18 |  230 |    0 |     0 |   22 |    0 |    1 |   46 |    1 |    0 |           0 |      5 |    2 |    1 |       1 |      0 |   56 |
|    5 | Green       | 10 |      10 |    2 |   50 |    1 |     2 |    6 |    0 |    2 |   48 |    4 |    1 |           0 |      0 |    1 |    2 |       1 |      0 |   16 |
|    6 | Dene        |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   28 |    0 |    0 |           0 |      0 |    3 |    0 |       0 |      0 |    2 |
|    7 | Breann      | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   32 |    0 |    1 |           0 |      0 |    4 |    2 |       0 |      0 |    7 |
|    8 | Hamza       | 15 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   47 |    0 |    1 |           0 |      0 |    4 |    1 |       2 |      0 |    7 |
|    9 | Everette    | 12 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   31 |    0 |    2 |           0 |      0 |    1 |    0 |       1 |      0 |   14 |
|   13 | Alphege     | 12 |      14 |    0 |   40 |    3 |    12 |    6 |    1 |    2 |   29 |    1 |    2 |           0 |      7 |    4 |    0 |       0 |      0 |   19 |
|   15 | Mia         | 16 |      31 |    9 |  165 |    3 |     7 |   18 |    1 |    5 |   72 |    2 |    1 |           0 |      9 |    6 |    2 |       1 |      0 |   47 |
|   16 | Zaira       |  8 |       0 |    0 |    5 |    0 |     0 |    0 |    0 |    4 |   43 |    1 |    1 |           0 |      0 |    2 |    0 |       3 |      0 |   13 |
|   17 | Voos        |  9 |       1 |    1 |    7 |    0 |     0 |    1 |    0 |    1 |   33 |    2 |    1 |           0 |      0 |    2 |    0 |       1 |      0 |   10 |
|   32 | Joscelin.   |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    7 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   33 | Sashka.     |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      0 |    0 |
|   70 | Leone.      | 11 |       2 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   19 |    0 |    0 |           0 |      0 |    1 |    2 |       2 |      R |    2 |
|   71 | Yehochanan. | 16 |       1 |    0 |    1 |    0 |     0 |    0 |    1 |    0 |   22 |    0 |    1 |           0 |      0 |    3 |    0 |       1 |      R |    7 |
|   86 | Alizee.     |  5 |       4 |    0 |    3 |    2 |     3 |    0 |    0 |    0 |   22 |    2 |    1 |           0 |      0 |    0 |    1 |       0 |      1 |    7 |
|   89 | Eetu.       |  5 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   25 |    1 |    1 |           0 |      0 |    0 |    0 |       1 |      1 |    5 |
|   94 | Jonah.      |  4 |      11 |    4 |   61 |    0 |     0 |    7 |    2 |    0 |    4 |    1 |    1 |           1 |      0 |    2 |    0 |       2 |      1 |   21 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Zensun Vagabonds" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Management

Muddib is an old BludBol hand exiled from somewhere far upspire. He's ancient and grublike but knows the game. That he's been unable to create a championship force from his players rankles.

### Fans

The Vagabonds' primary rivalry is with the [Old Wyrms](oldwyrms) as the pair of UBBL Founders. They've never been nearly as good as the Wyrms, so a lot of fans see themselves as custodians of tradition instead of victory.

### Famous Games

The loss that ended the Vagabonds' GCVIII season was [[hulud]]'s final match, as well as [[yakup]]'s last one in the pros. It was a great game.

The first-round playoff upset against the [Kaiju Dynamo](kaijudynamo) in GCXI was a comeback for the ages. [[gcxi-16-kdzv]]