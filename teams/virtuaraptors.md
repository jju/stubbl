# Virtua Raptors



## Playbook

The Raptors use the Elizabeth Aardman playbook, with strong linemen and a big guy anchoring the centre, while the ball handling runners are chosen for speed (rather than skill, strength or durability). The basic idea of the playbook is to cage the fragile runner to a place where they can bolt for the endzone.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Ulviyye      | Runner    |   21 |       2 |   14 |         1 | 110000 |     0 |
|    2 | Hiro         | Runner    |   64 |       5 |   29 |         2 | 180000 |     0 |
|    3 | Thanatos     | Runner    |   22 |       4 |   23 |         2 | 100000 |     0 |
|    4 | Ella         | Runner    |   58 |       5 |   23 |         2 | 160000 |     0 |
|    5 | Miki         | Blocker   |   19 |       2 |   10 |         1 | 120000 |     0 |
|    6 | Uhtric       | Blocker   |   18 |       5 |   31 |         2 | 120000 |     0 |
|    7 | Hercules     | Blocker   |   26 |       5 |   30 |         2 | 120000 |     0 |
|    8 | Diocletianus | Blocker   |    8 |       3 |   19 |         1 | 100000 |     0 |
|    9 | Youko        | Blocker   |   24 |       5 |   23 |         2 | 130000 |     0 |
|   10 | Conor        | Blocker   |   20 |       5 |   30 |         2 | 120000 |     0 |
|   11 | Viyan        | Runner    |   24 |       5 |   26 |         2 | 100000 |     0 |
|   12 | Lachlan      | Runner    |   28 |       5 |   27 |         2 | 100000 |     0 |
|   13 | Greaves      | Runner    |   25 |       3 |   16 |         1 | 100000 |     0 |
|   14 | Waltraut     | Runner    |   41 |       3 |   19 |         1 | 120000 |     0 |
|   15 | Taymuraz     | Runner    |   17 |       1 |    3 |         0 | 100000 |     0 |
|   16 | Tatiana      | Heavy |   40 |       5 |   27 |         2 | 210000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    3 | Freja        | Runner    |   23 |       2 |   11 |         1 | 100000 |     0 |
|    8 | Milivoj      | Blocker   |    0 |       1 |    2 |         0 |  80000 |     0 |
|    9 | Madalin      | Blocker   |    9 |       1 |    4 |         0 | 110000 |     0 |
|    9 | Seher        | Blocker   |    0 |       1 |   10 |         1 |  80000 |     0 |
|   10 | Sampo        | Blocker   |    7 |       2 |   12 |         1 | 100000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   27 | Amardeep     | Blocker   |   11 |       5 |   24 |         2 | 100000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Virtua Raptors" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```



## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Virtua Raptors | Open     |   19 |    3 |    8 |   30 | 66.902 |   64 |   55 |   50 |      -1 |    3 |
| Virtua Raptors | Street   |    3 |    1 |    1 |    5 | 70.000 |   13 |    9 |   10 |      -1 |    2 |
| Virtua Raptors | Pro      |    1 |    0 |    1 |    2 | 50.000 |    5 |    5 |    7 |       7 |   -1 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Virtua Raptors" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record (W-D-L)

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Virtua Raptors |   23 |    4 |   10 |   37 | 64.141 |   82 |   69 |   67 |       5 |    4 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Virtua Raptors" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Orange Goblet II Champions - [[team1stplace]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Virtua Raptors | Orange Goblet III |    9 |    1 |    2 |     12 | 79.1667 |   29 |   20 |   14 |     -1 |   -2 |
| Virtua Raptors | OGII Qualifier    |    3 |    1 |    1 |      5 |      70 |   13 |    9 |    9 |     -1 |    2 |
| Virtua Raptors | **Orange Goblet II**  |    7 |    2 |    4 |     13 | 61.5385 |   26 |   25 |   21 |      1 |    4 |
| Virtua Raptors | UBBL Challenge IV |    3 |    0 |    2 |      5 |      60 |    9 |   10 |    5 |     -1 |    1 |
| Virtua Raptors | Champions Circuit |    1 |    0 |    1 |      2 |      50 |    5 |    5 |    3 |      7 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Virtua Raptors" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Raptors are relative upstarts in the UBBL

### Seasons


#### Projection OGIII

W-D-L ?

#### summary last season

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Virtua Raptors |     1 |       1 |    3 |   43 |    1 |        1 |      1 |          0 |    4 |     40 |     4 |    1 |   23 |           0 |           3 |
| Virtua Raptors |     2 |       2 |    2 |   35 |    2 |       -1 |      2 |          1 |    1 |     29 |     0 |    1 |   17 |           1 |           2 |
| Virtua Raptors |     3 |       2 |    5 |   94 |    2 |       -2 |      2 |          0 |    0 |     35 |     1 |    1 |   22 |           5 |           4 |
| Virtua Raptors |     4 |       3 |    3 |   51 |    1 |        1 |      1 |          0 |    0 |     33 |     1 |    1 |   15 |           3 |           1 |
| Virtua Raptors |     5 |       1 |    3 |   57 |    0 |        0 |      0 |          0 |    1 |     37 |     2 |    1 |   16 |           3 |           0 |
| Virtua Raptors |     6 |       2 |    2 |   50 |    2 |        3 |      2 |          0 |    1 |     38 |     0 |    1 |   15 |           2 |           1 |
| Virtua Raptors |     8 |       0 |    1 |   42 |    0 |        0 |      0 |          0 |    0 |     46 |     1 |    1 |    8 |           1 |           0 |
| Virtua Raptors |     9 |       4 |    4 |   47 |    0 |        0 |      0 |          0 |    1 |     43 |     1 |    1 |   19 |           0 |           4 |
| Virtua Raptors |    10 |       0 |    0 |   60 |    2 |        3 |      2 |          0 |    2 |     46 |     3 |    1 |   11 |           4 |           0 |
| Virtua Raptors |    11 |       3 |    3 |   68 |    1 |        2 |      1 |          0 |    2 |     43 |     0 |    1 |   19 |           3 |           3 |
| Virtua Raptors |    QF |       1 |    2 |   53 |    0 |        0 |      0 |          0 |    2 |     34 |     2 |    1 |   15 |           2 |           1 |
| Virtua Raptors |    SF |       1 |    1 |   54 |    1 |        1 |      1 |          0 |    0 |     32 |     2 |    1 |    9 |           1 |           5 |

```
SELECT pl.f_tname AS Team, mt.round, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 30 AND pl.f_tname = "Virtua Raptors" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Ulviyye      | 12 |      20 |    3 |   95 |    4 |     5 |    1 |    0 |    0 |    6 |    2 |    0 |           3 |      1 |    2 |    1 |       0 |      0 |   13 |
|    2 | Hiro         | 11 |      24 |    7 |  137 |    0 |     0 |    5 |    0 |    0 |    2 |    0 |    0 |           0 |      2 |    9 |    1 |       1 |      0 |   21 |
|    3 | Freja        | 10 |      25 |    5 |  100 |    3 |     3 |    2 |    1 |    0 |    2 |    0 |    0 |           1 |      2 |    3 |    1 |       2 |      0 |   20 |
|    4 | Ella         |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    1 |           0 |      0 |    1 |    1 |       0 |      0 |    5 |
|    5 | Miki         |  9 |       0 |    0 |    8 |    0 |     0 |    0 |    0 |    2 |   54 |    1 |    3 |           0 |      0 |    3 |    0 |       1 |      0 |   19 |
|    6 | Uhtric       |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   32 |    2 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    4 |
|    7 | Hercules     |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   39 |    1 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    4 |
|    8 | Milivoj      |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   13 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    8 | Diocletianus |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   23 |    1 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    2 |
|    9 | Madalin      |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   20 |    1 |    1 |           0 |      0 |    1 |    0 |       1 |      0 |    9 |
|    9 | Youko        |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    1 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|    9 | Seher        | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   43 |    0 |    0 |           0 |      0 |    1 |    2 |       0 |      0 |    0 |
|   10 | Conor        |  7 |       2 |    0 |    1 |    0 |     0 |    0 |    0 |    1 |   44 |    1 |    1 |           0 |      0 |    1 |    0 |       0 |      0 |    7 |
|   10 | Sampo        | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   62 |    4 |    1 |           0 |      0 |    3 |    0 |       1 |      0 |    7 |
|   11 | Viyan        |  2 |       1 |    1 |    6 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    3 |
|   12 | Lachlan      |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    5 |
|   13 | Greaves      |  9 |       2 |    1 |   24 |    0 |     0 |    0 |    0 |    0 |    3 |    0 |    1 |           0 |      1 |    1 |    1 |       0 |      0 |    8 |
|   14 | Waltraut     | 12 |      26 |    6 |  115 |    1 |    -1 |    0 |    0 |    0 |    5 |    0 |    2 |           1 |      1 |    0 |    0 |       0 |      0 |   29 |
|   15 | Taymuraz     |  3 |      11 |    5 |   87 |    2 |     3 |    1 |    0 |    0 |    1 |    0 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |   17 |
|   16 | Tatiana      |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   41 |    2 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    2 |
|   27 | Amardeep     |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   27 |    0 |    0 |           0 |      0 |    0 |    0 |       1 |      0 |    0 |
|   84 | Edme.        |  5 |       7 |    1 |   81 |    2 |    -2 |    3 |    0 |    0 |    2 |    0 |    0 |           0 |      2 |    0 |    0 |       0 |      1 |    5 |
|   86 | Jewel.       |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    4 |    1 |    1 |           0 |      0 |    0 |    0 |       0 |      1 |    7 |
|   96 | Rani.        |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   18 |    0 |    0 |           0 |      0 |    0 |    0 |       1 |      1 |    2 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Orange Goblet III" AND pl.f_tname = "Virtua Raptors" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Hiro**      | Runner    |   20 |    2 |    7 |   29 |   11 |   17 |    2 |    0 |    0 |    0 |    2 |   64 |
| **Ella**      | Runner    |   13 |    2 |    8 |   23 |   13 |    4 |    0 |    0 |    0 |    0 |    3 |   58 |
| Francine | Runner    |    6 |    2 |    4 |   12 |    8 |    8 |    0 |    0 |    0 |    0 |    2 |   42 |
| **Waltraut**  | Runner    |   14 |    2 |    3 |   19 |    8 |    2 |    0 |    0 |    0 |    0 |    3 |   41 |
| **Tatiana**   | Heavy |   16 |    3 |    8 |   27 |    0 |    0 |    0 |    8 |    1 |    1 |    4 |   40 |
| **Lachlan**   | Runner    |   15 |    3 |    9 |   27 |    7 |    2 |    0 |    0 |    0 |    0 |    1 |   28 |
| Edme     | Runner    |   17 |    3 |    6 |   26 |    5 |    2 |    0 |    0 |    0 |    0 |    2 |   27 |
| **Hercules**  | Blocker   |   19 |    3 |    8 |   30 |    1 |    0 |    0 |    2 |    1 |    1 |    3 |   26 |
| **Greaves**   | Runner    |   13 |    0 |    3 |   16 |    2 |    0 |    2 |    0 |    0 |    0 |    3 |   25 |
| **Viyan**     | Runner    |   14 |    3 |    9 |   26 |    5 |    0 |    2 |    0 |    0 |    0 |    1 |   24 |
| **Youko**     | Blocker   |   13 |    3 |    7 |   23 |    0 |    0 |    1 |    3 |    2 |    1 |    2 |   24 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Virtua Raptors" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Virtua Raptors" GROUP BY pl.name ORDER BY pl.nr ASC;
```


### Management

### Fans


### Famous Games


