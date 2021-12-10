# Darkling Spectres

While of late the Darkling Spectres have been mired in mediocrity, they can be an effective defensive team. Their ownership sees the team as primarily a profit centre since on-field results have been hard to come by recently.

## Playbook

The Spectres use the traditional Unglewort playbook. They have nigh-unlimited cheap slow fodder for the line that funnel opposition towards the reliable massive blockers. Two blitzers attack opposing ball-carriers, and up to four runners supply all of the speed, though they are very fragile.


## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Ross          | Runner    |   32 |       1 |    8 |         1 | 140000 |     0 |
|    2 | Persis        | Line |   33 |       2 |   17 |         1 | 120000 |     0 |
|    3 | Sacnicte      | Runner    |   29 |       1 |    8 |         1 | 120000 |     0 |
|   14 | Xiomara       | Line |   17 |       2 |   15 |         1 | 100000 | 10000 |
|   16 | Blodeuwedd    | Line |    7 |       2 |   18 |         1 | 100000 | 10000 |
|   18 | Xochiquetzal  | Blitzer    |   20 |       3 |   25 |         2 | 130000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   20 | Sumit.       | Line |    6 |       3 |   18 |         1 |  70000 |     0 |
|   21 | Khurshid.    | Runner    |   33 |       1 |   11 |         1 | 130000 |     0 |
|   21 | Melite.      | Runner    |    2 |       1 |    7 |         0 |  70000 |     0 |
|   22 | Bambino.     | Runner    |   49 |       6 |   62 |         4 | 190000 | 40000 |
|   23 | RayII.       | Runner    |   42 |       2 |   24 |         2 | 150000 | 20000 |
|   24 | Ray.         | Runner    |   44 |       3 |   16 |         1 | 140000 | 10000 |
|   26 | Aldert.      | Blitzer    |   42 |       6 |   53 |         4 | 150000 |     0 |
|   27 | Mariann.     | Line   |    0 |       1 |    5 |         0 |  40000 |     0 |
|   29 | Kristina.    | Line   |    5 |       1 |    1 |         0 |  40000 |     0 |
|   30 | McGraw.      | Line   |    8 |       7 |   41 |         3 |  90000 | 30000 |
|   30 | Journee.     | Line   |    0 |       3 |   12 |         1 |  40000 |     0 |
|   31 | Willburg.    | Line   |    2 |       2 |   12 |         1 |  40000 |     0 |
|   31 | Antinanco.   | Line |    7 |       2 |   10 |         1 |  60000 |     0 |
|   32 | Vinter.      | Line   |    0 |       2 |    8 |         1 |  40000 |     0 |
|   32 | Kichiro.     | Line   |    0 |       1 |    6 |         0 |  40000 |     0 |
|   33 | Jeltsje.     | Line   |    0 |       1 |    1 |         0 |  40000 |     0 |
|   33 | Hyram.       | Line |    6 |       2 |   10 |         1 |  60000 |     0 |
|   34 | Marian.      | Line |   23 |       6 |   40 |         3 |  80000 |     0 |
|   34 | Amir.        | Line |    9 |       3 |   14 |         1 |  60000 |     0 |
|   34 | Klopas.      | Line   |    0 |       1 |    4 |         0 |  40000 |     0 |
|   35 | Niall.       | Line   |    5 |       2 |    7 |         0 |  40000 |     0 |
|   35 | Alexandros.  | Line   |    0 |       1 |    4 |         0 |  40000 |     0 |
|   35 | Kole.        | Line |    9 |       2 |    8 |         1 |  70000 |     0 |
|   36 | Uilliam.     | Line   |    0 |       2 |   19 |         1 |  40000 |     0 |
|   41 | Reinhold.    | Line |    5 |       1 |    2 |         0 |  40000 |     0 |
|   42 | Nnenna.      | Line |    0 |       1 |    4 |         0 |  40000 |     0 |
|   43 | Helga.       | Line |    0 |       1 |    2 |         0 |  40000 |     0 |
|   44 | Renate.      | Line |    0 |       1 |    2 |         0 |  40000 |     0 |
|   45 | Elise.       | Line |    0 |       1 |    6 |         0 |  40000 |     0 |
|   46 | Sheyna.      | Line |    0 |       1 |    1 |         0 |  40000 |     0 |
|   47 | Mahesh.      | Blocker    |   42 |       2 |   19 |         1 | 180000 |     0 |
|   48 | Daire.       | Blocker    |   27 |       2 |   17 |         1 | 160000 |     0 |
|   49 | Nisha.       | Line   |   12 |       1 |    7 |         0 |  60000 |     0 |
|   50 | Page.        | Line   |    0 |       1 |    2 |         0 |  40000 |     0 |
|   51 | Goddard.     | Line |    0 |       2 |   12 |         1 |  40000 |     0 |


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Darkling Spectres" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```


## Records

### Record by Division (W-D-L)

| Team              | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-------------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Darkling Spectres | Pro    |   47 |   15 |   55 |  117 | 47.423 |  228 |  278 |           214 |             58 |          4 |
| Darkling Spectres | Open   |    7 |    0 |    5 |   12 | 48.333 |   26 |   28 |            15 |             -2 |          0 |
| Darkling Spectres | Street |    2 |    1 |    7 |   10 | 25.000 |    9 |   19 |            21 |              6 |         -1 |

```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Darkling Spectres" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Darkling Spectres | 56 |   16 |   67 |  139 | 45.978 |  263 |  325 |  250 |      62 |    3 |

```
SELECT teams.name, sum(mr.won), sum(mr.draw), sum(mr.lost), sum(mr.played), round(avg(mr.win_pct),3), sum(mr.gf), sum(mr.ga), sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Darkling Spectres" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* Green Cup Classic 06 - Heaps Champion [[team2ndplace#gcc06]] & [[teamdivision#gcc06]]
* Green Cup VII - Classic Conference Champions [[team2ndplace#gcvii]]
* Green Cup VII - Heaps Division Champions [[teamdivision#gcvii]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Darkling Spectres | UBBL Challenge II    |    2 |    0 |    1 |      3 | 66.67 |    7 |    8 |    7 |      2 |   -1 |
| Darkling Spectres | UBBL Challenge IV    |    2 |    0 |    1 |      3 | 66.67 |    7 |    8 |    6 |     -1 |    1 |
| Darkling Spectres | Green Cup Classic 06 |    5 |    3 |    2 |     10 |      65.00 |   17 |   14 |   10 |     -2 |    3 |
| Darkling Spectres | UBBL Challenge       |    3 |    0 |    2 |      5 |      60.00 |   12 |    8 |    7 |      0 |    1 |
| Darkling Spectres | Green Cup IV         |    6 |    2 |    4 |     12 | 58.33 |   24 |   20 |   24 |      9 |    0 |
| Darkling Spectres | Green Cup VII        |   10 |    0 |    9 |     19 | 52.63 |   36 |   39 |   33 |     14 |    1 |
| Darkling Spectres | Green Cup XI         |    8 |    1 |    8 |     17 |      50 |   33 |   49 |   20 |      5 |    1 |
| Darkling Spectres | Green Cup IX         |    5 |    3 |    8 |     16 |  40.63 |   32 |   45 |   27 |     -3 |   -2 |
| Darkling Spectres | Green Cup III        |    3 |    2 |    5 |     10 |      40.00 |   21 |   24 |   25 |     13 |    2 |
| Darkling Spectres | Green Cup X          |    5 |    2 |    9 |     16 |    37.50 |   35 |   45 |   24 |     -1 |    0 |
| Darkling Spectres | Green Cup VIII       |    5 |    2 |   10 |     17 | 35.29 |   30 |   42 |   42 |     23 |   -1 |
| Darkling Spectres | Green Cup V Memorial |    2 |    1 |    7 |     10 |      25.00 |    9 |   19 |   17 |      6 |   -1 |
| Darkling Spectres | UBBL Challenge III   |    0 |    0 |    1 |      1 |       0.00 |    0 |    4 |    2 |     -3 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Darkling Spectres" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Spectres have been mired in mediocrity of late, but the rejuvenated UBBL has led them to their best tournament results. 

### Seasons

Their best pro season was the short GCC06 in which The Spectres handily won their division but injuries deprived them of their stars in the Green Cup final. They won the Heaps again in GCVII and then the Classic Conference, but lost to the [Eagles](ravenouseagles) in a battle of not that impressive win record teams (fans say they had a lot of heart).

There've been rumblings that ownership wanted to take their money and run, folding the team. Their lacklustre play in UBBL Challenge III lent weight to the idea, but they returned for the GCX. Everyone was watching them to see if they'd be tanking, but they ended up making the playoffs (on the backs of a surprisingly bad [Eldritch Fatality](eldritchfatality) team.

#### Projection GCXI

W-D-L 6-2-7 

The starting lineup being shown off in pre-GCXI training camps is surprising. While it does manage to stay above the 1700 Value Floor set for the season, it's hard to see how these scrubs are going to stay out of last place in the Heaps.

#### GCXI summary

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Darkling Spectres |     1 |       4 |    1 |   29 |    2 |        5 |      2 |          0 |    1 |     28 |     0 |    1 |   12 |           1 |           2 |
| Darkling Spectres |     2 |       4 |    2 |   24 |    1 |        3 |      1 |          0 |    1 |     25 |     1 |    1 |   14 |           1 |           2 |
| Darkling Spectres |     3 |       7 |    0 |   34 |    2 |       10 |      2 |          1 |    0 |     47 |     2 |    1 |    9 |           0 |           5 |
| Darkling Spectres |     4 |       7 |    0 |   41 |    1 |        1 |      1 |          0 |    1 |     32 |     0 |    1 |    8 |           5 |           0 |
| Darkling Spectres |     5 |       7 |    0 |   26 |    0 |        0 |      1 |          0 |    2 |     42 |     3 |    1 |    9 |           0 |           4 |
| Darkling Spectres |     6 |      16 |    4 |   81 |    6 |       15 |      6 |          0 |    1 |     50 |     1 |    1 |   25 |           8 |           4 |
| Darkling Spectres |     7 |       8 |    3 |   46 |    2 |        2 |      2 |          0 |    1 |     26 |     1 |    1 |   18 |           1 |           3 |
| Darkling Spectres |     8 |      16 |    6 |   78 |    4 |       12 |      4 |          0 |    1 |     38 |     1 |    1 |   29 |           6 |           4 |
| Darkling Spectres |     9 |       2 |    0 |   25 |    1 |        2 |      1 |          0 |    0 |     31 |     0 |    1 |    6 |           0 |           3 |
| Darkling Spectres |    10 |       9 |    4 |   53 |    3 |        8 |      3 |          1 |    1 |     50 |     1 |    1 |   24 |           2 |           4 |
| Darkling Spectres |    11 |      11 |    1 |   43 |    2 |        6 |      2 |          0 |    1 |     43 |     0 |    1 |   12 |           5 |           1 |
| Darkling Spectres |    12 |      14 |    3 |   33 |    3 |       10 |      3 |          0 |    5 |     35 |     1 |    1 |   27 |           3 |           0 |
| Darkling Spectres |    13 |       5 |    2 |   29 |    0 |        0 |      0 |          0 |    1 |     26 |     0 |    1 |   13 |           1 |           2 |
| Darkling Spectres |    14 |      12 |    3 |   51 |    4 |       12 |      4 |          1 |    1 |     37 |     0 |    1 |   22 |           3 |           3 |
| Darkling Spectres |    15 |      11 |    3 |   46 |    3 |       10 |      3 |          0 |    3 |     38 |     0 |    1 |   23 |           1 |           3 |
| Darkling Spectres |   R16 |      11 |    1 |   19 |    2 |       16 |      2 |          0 |    0 |     42 |     4 |    1 |   10 |           1 |           0 |
| Darkling Spectres |    QF |       4 |    0 |   20 |    1 |        5 |      1 |          0 |    0 |     45 |     2 |    1 |    6 |           4 |           0 |

```
SELECT pl.f_tname AS Team, mt.round, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Darkling Spectres" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Ross         |  8 |      14 |    3 |   39 |    3 |     9 |    1 |    0 |    0 |    4 |    0 |    4 |           0 |      2 |    1 |    1 |       0 |      0 |   32 |
|    2 | Persis       | 11 |      26 |    0 |   61 |   11 |    33 |    0 |    0 |    0 |   14 |    1 |    3 |           1 |      1 |    1 |    0 |       0 |      0 |   26 |
|    3 | Sacnicte     |  7 |      21 |    5 |  102 |    4 |    10 |    5 |    0 |    0 |    9 |    0 |    2 |           0 |      3 |    2 |    1 |       0 |      0 |   29 |
|   14 | Xiomara      | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   27 |    1 |    2 |           0 |      0 |    2 |    1 |       0 |      0 |   10 |
|   16 | Blodeuwedd   | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   50 |    1 |    0 |           0 |      0 |    1 |    0 |       1 |      0 |    0 |
|   18 | Xochiquetzal |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   31 |    1 |    1 |           0 |      0 |    3 |    0 |       0 |      0 |   11 |
|   20 | Sumit.       |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   22 |    0 |    0 |           0 |      0 |    1 |    0 |       1 |      0 |    0 |
|   21 | Melite.      |  7 |       4 |    0 |    6 |    2 |    -1 |    1 |    0 |    0 |   15 |    0 |    0 |           0 |      0 |    2 |    0 |       1 |      0 |    2 |
|   27 | Mariann.     |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    3 |    1 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|   30 | Journee.     |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   25 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   31 | Antinanco.   |  9 |       0 |    0 |   -1 |    0 |     0 |    0 |    0 |    0 |    5 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   32 | Kichiro.     |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   16 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      0 |    0 |
|   33 | Hyram.       |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   34 | Amir.        |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   20 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   34 | Marian.      |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |    8 |    1 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    9 |
|   35 | Kole.        |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    5 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   35 | Alexandros.  |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|   65 | Lamont.      |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   36 |    1 |    0 |           0 |      0 |    1 |    0 |       0 |      R |    4 |
|   66 | Grid.        | 10 |       1 |    0 |    0 |    1 |    12 |    0 |    0 |    1 |  105 |    3 |    0 |           0 |      0 |    4 |    0 |       1 |      R |    3 |
|   67 | Vayu.        |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   56 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      R |    2 |
|   68 | Simon.       |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    5 |   48 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      R |   10 |
|   69 | Nail.        |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   30 |    1 |    1 |           0 |      0 |    2 |    0 |       0 |      R |    7 |
|   71 | Florrie.     |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   19 |    0 |    0 |           0 |      1 |    0 |    1 |       0 |      R |    0 |
|   73 | Channing.    |  9 |      17 |    3 |   60 |    7 |    25 |    4 |    1 |    1 |   14 |    2 |    0 |           2 |      0 |    2 |    3 |       0 |      R |   20 |
|   81 | Gojko.       |  8 |      17 |    3 |  112 |    4 |    13 |    2 |    1 |    0 |    8 |    1 |    0 |           0 |      3 |    5 |    0 |       1 |      1 |   15 |
|   83 | Ragnar.      |  9 |      23 |    7 |  101 |    3 |    10 |    9 |    1 |    0 |   16 |    1 |    1 |           0 |      3 |    2 |    0 |       0 |      1 |   31 |
|   84 | Olufunmi.    |  4 |       9 |    7 |  107 |    1 |     3 |    8 |    0 |    0 |   11 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |   22 |
|   84 | Zdravko      | 10 |      16 |    5 |   91 |    1 |     3 |    8 |    0 |    1 |   18 |    0 |    1 |           1 |      3 |    2 |    1 |       0 |      1 |   23 |
|   90 | Henry.       |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   13 |    0 |    1 |           0 |      0 |    3 |    0 |       0 |      1 |    7 |
|   92 | Austeja.     |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Darkling Spectres" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```
### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Tooms II      | Runner    |   28 |    8 |   28 |   64 |   13 |   86 |    1 |    3 |    0 |    0 |    5 |  158 |
| *Qualls*      | Runner | ?? | ?? | ?? | 37 | 22 | 30 | 1 | 0 | 1 | 0 | 3 | 115 |
| Olufunmi      | Runner    |   16 |    1 |   20 |   37 |   29 |    4 |    2 |    2 |    0 |    0 |    1 |  104 |
| Gojko         | Runner    |   10 |    2 |   17 |   29 |   13 |   33 |    2 |    0 |    0 |    0 |    5 |  101 |
| Channing      | Runner    |   16 |    5 |   19 |   40 |   21 |   17 |    1 |    2 |    0 |    0 |    2 |   96 |
| Simon         | Blocker    |   23 |    6 |   24 |   53 |    0 |    0 |    0 |   22 |    8 |    5 |    5 |   95 |
| *Tutankhamun* | Blocker | ?? | ?? | ?? | 38 |  0 | 0 | 2 | 16 | 9 | 4 | 3 | 76 |
| Hortensius    | Runner    |    9 |    3 |   13 |   25 |   20 |    6 |    0 |    1 |    0 |    0 |    1 |   73 |
| Zdravko       | Runner    |   11 |    1 |   17 |   29 |   16 |    3 |    1 |    1 |    1 |    0 |    2 |   67 |
| Onesiphorus | Blocker    |   20 |    5 |   21 |   46 |    0 |    0 |    0 |   11 |   12 |    1 |    3 |   63 |
| Lamont       | Blitzer    |   27 |    5 |   26 |   58 |    3 |    0 |    0 |    6 |    5 |    1 |    6 |   63 |
| Ragnar       | Runner    |    9 |    2 |    7 |   18 |   11 |    4 |    2 |    1 |    0 |    0 |    3 |   58 |
| Federica     | Runner    |    8 |    2 |   11 |   21 |   12 |    3 |    0 |    1 |    0 |    0 |    3 |   56 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Darkling Spectres" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

For a very long time this team relied way too much on [[toomsii]] who was fragile as hell, but they didn't have anyone really special in the wings to replace him. Now [[Channing]] takes that role but with the support of [[gojko]] and [[Olufunmi]] they can spread some of the offensive work around a bit better. 

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|   81 | Tooms II | Runner   |       8 |      1 | 180000 |     0 |


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Darkling Spectres" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

### Management

The Lake ownership group makes a lot of money on this team and there isn't a lot of demand at the top for high-level play or competitiveness.

### Fans

The Spectres have come close to winning the Green Cup a couple of times, but have been thwarted by similarily bashing teams. Fans hate it when the schedule comes up against the [Orbital Machine](orbitalmachine) or the [Gore Farmers](gorefarmers).

### Famous Games

The Spectres' most impactful match came in the GCC06 semifinals.