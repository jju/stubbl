# Carcosan Tatters

The Carcosan Tatters have always been a good team. They're defensive-minded without really flashy stars and can lock a game down to a muddy slog even in the middle of a drought.

## Playbook

The Tatters use the Nergal playbook, which some (especially fans of pretty BludBol) say is one of the oldest and most insidious ways to play. The lineup consists of four strong blockers, four blitzing ball handlers and whatever dregs of fodder can be pulled off the street or opposing teams. Their biggest strengths are making everything difficult for the opposition.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Liubou           | Line          |   31 |       2 |   10 |         1 | 110000 |     0 |
|    2 | Maryna           | Line          |   10 |       2 |    9 |         1 |  60000 |     0 |
|    3 | Sparrow          | Blitzer        |  131 |       4 |   46 |         3 | 210000 |     0 |
|    4 | Arya             | Blitzer        |  110 |       5 |   44 |         3 | 250000 | 30000 |
|    5 | Orna             | Blitzer        |  107 |       9 |   73 |         5 | 190000 |     0 |
|    6 | Marley           | Blitzer        |   86 |       6 |   48 |         3 | 220000 | 40000 |
|    7 | Dalitso          | Blocker  |   36 |       4 |   28 |         2 | 220000 | 20000 |
|    8 | FlamingLion      | Blocker  |   54 |       5 |   40 |         3 | 250000 | 50000 |
|    9 | OreSmitingMaster | Blocker  |   53 |       8 |   69 |         5 | 250000 | 50000 |
|   10 | Shunmyo          | Blocker  |   40 |       3 |   36 |         2 | 170000 |     0 |
|   12 | Seela            | Line          |    6 |       1 |    7 |         0 |  70000 |     0 |
|   13 | Uzmal            | Line          |   18 |       4 |   18 |         1 |  80000 |     0 |
|   16 | Pierre           | Heavy |   94 |       8 |   68 |         5 | 290000 | 50000 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
| 10 | Pluto | Blocker |
|   17 | MaskedPain       | Blitzer        |   66 |       5 |   43 |         3 | 190000 | 30000 |
|   18 | alFadl           | Blitzer        |   21 |       1 |   11 |         1 | 130000 | 10000 |

### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   11 | Cain.               | Line         |   10 |       6 |   43 |         3 |  90000 | 30000 |
|   19 | LastForsakenVenom.  | Blocker |   51 |       4 |   42 |         3 | 220000 | 30000 |
|   20 | SpearoftheDepths.   | Blocker |   31 |       3 |   20 |         1 | 190000 | 10000 |
|   21 | EbonMiseryDragon.   | Blocker |   34 |       4 |   35 |         2 | 170000 |     0 |
|   22 | Mate.               | Line         |    0 |       1 |    1 |         0 |  40000 |     0 |
|   27 | Bruno.              | Blocker |   25 |       4 |   23 |         2 | 150000 |     0 |
|   31 | Valeriy.            | Line         |    0 |       1 |    7 |         0 |  40000 |     0 |
|   32 | Frommik.            | Line         |    3 |       3 |   16 |         1 |  50000 | 10000 |
|   32 | Iapheth.            | Line         |    7 |       5 |   38 |         3 |  60000 |     0 |
|   33 | Alizee.             | Line         |    0 |       1 |    5 |         0 |  40000 |     0 |
|   33 | Hermes.             | Line         |    8 |       1 |    9 |         1 |  70000 |     0 |
|   34 | Swanahil.           | Line         |    2 |       6 |   25 |         2 |  40000 |     0 |
|   35 | Lucrece.            | Line         |   22 |       5 |   34 |         2 |  80000 |     0 |
|   43 | Yamilet.            | Line         |    6 |       1 |    3 |         0 |  70000 |     0 |
|   51 | Zhi.                | Line         |    8 |       1 |    6 |         0 |  60000 |     0 |
|   52 | Indiana.            | Line         |    8 |       1 |    1 |         0 |  60000 |     0 |
|   52 | Lazar.              | Line         |    7 |       1 |    6 |         0 |  60000 |     0 |
|   52 | Chijindum.          | Line         |    6 |       1 |    5 |         0 |  60000 |     0 |
|   52 | Libitina.           | Line         |    8 |       1 |    2 |         0 |  60000 |     0 |
|   54 | Steinunn.           | Line         |    0 |       2 |    3 |         0 |  40000 |     0 |
|   55 | Cahal.              | Line         |    0 |       2 |    5 |         0 |  40000 |     0 |
|   56 | Zeki.               | Line         |    0 |       2 |    2 |         0 |  40000 |     0 |
|   57 | Albina.             | Line         |    2 |       2 |    2 |         0 |  40000 |     0 |
|   58 | Anacletus.          | Line         |    6 |       2 |    5 |         0 |  60000 |     0 |
|   59 | Eveleen.            | Line         |    0 |       2 |    4 |         0 |  40000 |     0 |
```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Carcosan Tatters" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```


## Records

### Record by Division 

| Team             | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|------------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Carcosan Tatters | Pro      |   67 |   19 |   47 |  133 | 58.116 |  195 |  196 |  320 |     200 |    4 |
| Carcosan Tatters | Street   |    4 |    2 |    6 |   12 | 45.455 |    9 |   14 |   18 |       5 |   -3 |
| Carcosan Tatters | Open     |    3 |    0 |    3 |    6 | 50.000 |    7 |    7 |   13 |       5 |    1 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Carcosan Tatters" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team             | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|------------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Carcosan Tatters |   74 |   21 |   56 |  151 | 54.920 |  211 |  217 |  351 |     210 |    2 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Carcosan Tatters" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup II - Green Cup Champions [[team1stplace]]
* Green Cup II - Doom Fist [[teamcasualties]]
* Green Cup III - Tough Brake of Alsoran [[team3rdplace]]
* Green Cup VI - Outlands Champions [[team2ndplace#gcvi]] & [[teamdivision#gcvi]]
* Green Cup VIII - Outlands Division Champions [[teamdivision#gcviii]]

### Seasons

| Team             | Season               | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|------------------|----------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Carcosan Tatters | **Green Cup II**     |    7 |    3 |    2 |     12 | 70.83 |   24 |   19 |   36 |     27 |    0 |
| Carcosan Tatters | Green Cup III        |    6 |    3 |    2 |     11 | 68.18 |   18 |   17 |   29 |     22 |   -1 |
| Carcosan Tatters | Green Cup VI         |   11 |    1 |    5 |     17 | 67.65 |   20 |   15 |   23 |     10 |    5 |
| Carcosan Tatters | UBBL Challenge       |    2 |    0 |    1 |      3 | 66.67 |    4 |    3 |    7 |      3 |    1 |
| Carcosan Tatters | Green Cup VIII       |   12 |    0 |    6 |     18 | 66.67 |   23 |   21 |   39 |     22 |    1 |
| Carcosan Tatters | Green Cup X          |    8 |    3 |    5 |     16 |  59.38 |   25 |   21 |   39 |     29 |    0 |
| Carcosan Tatters | Green Cup IX         |    8 |    3 |    5 |     16 |  59.38 |   25 |   24 |   37 |     25 |    6 |
| Carcosan Tatters | Green Cup IV         |    5 |    3 |    3 |     11 | 59.09 |   17 |   17 |   35 |     28 |   -4 |
| Carcosan Tatters | Green Cup XI         |    7 |    2 |    7 |     16 | 50.00 |   28 |   26 |   41 |     24 |    0 |
| Carcosan Tatters | Green Cup V Memorial |    4 |    1 |    6 |     11 | 40.91 |    9 |   14 |   14 |      5 |   -3 |
| Carcosan Tatters | UBBL Challenge IV    |    1 |    0 |    2 |      3 | 33.33 |    3 |    4 |    5 |      2 |    0 |
| Carcosan Tatters | Green Cup VII        |    3 |    1 |   12 |     16 |  21.88 |   15 |   36 |   30 |     13 |   -3 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Carcosan Tatters" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Tatters have played ugly bludbol for a long time, and have only achieved ugly results in a couple of seasons.

### Seasons

The Tatters won the first Green Cup they entered as an expansion team. They didn't defend their title and lost in the quarterfinals of GCIII (but still accumulated more points than either of the semifinal losers, which got them the Tough Brake award). 

Under former player BSEncef's leadership the Tatters bashed their way to second place in the rejuvenated UBBL. While the GCVII campaign went terribly, it remains their only losing pro-level season on record.

#### GCXI summary

Their first exactly even season, which fell a touch short of the preseason expectations.

| Team            | round | Location | Result | Home | Away | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|----------|--------|--------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Carcosan Tatters |     1 | Away     | Draw   |    2 |    2 |       9 |    2 |   39 |    3 |       13 |      3 |          0 |    3 |     51 |     1 |    0 |   15 |
| Carcosan Tatters |     2 | Home     | Draw   |    2 |    2 |       8 |    2 |   40 |    1 |        6 |      1 |          0 |    4 |     53 |     0 |    1 |   20 |
| Carcosan Tatters |     3 | Home     | Loss   |    2 |    4 |       7 |    2 |   58 |    3 |        5 |      3 |          0 |    1 |     56 |     0 |    1 |   16 |
| Carcosan Tatters |     4 | Home     | Win    |    1 |    0 |       4 |    1 |   18 |    0 |        0 |      0 |          0 |    4 |     60 |     0 |    1 |   16 |
| Carcosan Tatters |     5 | Home     | Loss   |    2 |    3 |      12 |    2 |   44 |    5 |       14 |      5 |          0 |    3 |     54 |     1 |    1 |   22 |
| Carcosan Tatters |     6 | Away     | Win    |    1 |    2 |       8 |    2 |   52 |    2 |       13 |      2 |          0 |    4 |     73 |     1 |    1 |   21 |
| Carcosan Tatters |     7 | Away     | Loss   |    3 |    2 |       7 |    2 |   34 |    3 |       14 |      3 |          0 |    1 |     42 |     2 |    1 |   16 |
| Carcosan Tatters |     8 | Away     | Loss   |    1 |    0 |       5 |    0 |   10 |    1 |        4 |      1 |          1 |    1 |     49 |     3 |    1 |   10 |
| Carcosan Tatters |     9 | Home     | Loss   |    1 |    2 |       7 |    1 |   37 |    0 |        0 |      0 |          0 |    2 |     59 |     1 |    1 |   12 |
| Carcosan Tatters |    10 | Away     | Win    |    0 |    2 |       7 |    2 |   25 |    1 |        4 |      1 |          0 |    3 |     33 |     2 |    1 |   18 |
| Carcosan Tatters |    11 | Away     | Win    |    1 |    2 |       6 |    2 |   36 |    2 |       11 |      2 |          0 |    0 |     52 |     0 |    1 |   13 |
| Carcosan Tatters |    12 | Away     | Win    |    0 |    2 |       7 |    2 |   33 |    0 |        0 |      0 |          0 |    3 |     50 |     2 |    1 |   17 |
| Carcosan Tatters |    13 | Home     | Loss   |    1 |    2 |      13 |    1 |   38 |    3 |       16 |      3 |          1 |    2 |     46 |     0 |    1 |   17 |
| Carcosan Tatters |    14 | Away     | Win    |    1 |    2 |      16 |    2 |   46 |    4 |       12 |      4 |          0 |    1 |     33 |     0 |    1 |   17 |
| Carcosan Tatters |    15 | Home     | Win    |    3 |    0 |       9 |    3 |   46 |    4 |       11 |      4 |          0 |    3 |     50 |     1 |    1 |   24 |
| Carcosan Tatters |   R16 | Away     | Loss   |    4 |    2 |      13 |    2 |   52 |    4 |       15 |      5 |          1 |    5 |     79 |     1 |    1 |   27 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Carcosan Tatters" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster GCXI


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Liubou           |  8 |      31 |    1 |   87 |   12 |    40 |    0 |    0 |    0 |    9 |    1 |    2 |           0 |      1 |    1 |    0 |       0 |      0 |   25 |
|    2 | Maryna           |  8 |       4 |    0 |    4 |    1 |     5 |    0 |    1 |    1 |   24 |    0 |    1 |           0 |      1 |    1 |    0 |       0 |      0 |   10 |
|    3 | Sparrow          | 11 |      21 |    8 |  126 |    2 |    15 |   16 |    0 |    2 |   33 |    0 |    0 |           2 |      4 |    3 |    0 |       1 |      0 |   30 |
|    4 | Arya             | 16 |      28 |   12 |  165 |    3 |     4 |   14 |    0 |    1 |   54 |    2 |    2 |           0 |      3 |    2 |    0 |       0 |    0 | **51** |
|    5 | Orna             |  6 |       3 |    1 |    5 |    0 |     0 |    0 |    0 |    2 |   40 |    2 |    0 |           0 |      0 |    0 |    2 |       0 |      0 |    7 |
|    6 | Marley           | 11 |       2 |    0 |    8 |    0 |     0 |    1 |    0 |    8 |  102 |    0 |    1 |           1 |      0 |    5 |    0 |       1 |      0 |   21 |
|    7 | Dalitso          |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   45 |    0 |    2 |           0 |      0 |    0 |    0 |       0 |      0 |   14 |
|    8 | FlamingLion      | 15 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    5 |  124 |    0 |    2 |           0 |      0 |    0 |    0 |       0 |      0 |   20 |
|    9 | OreSmitingMaster | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   67 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |   11 |
|   10 | Shunmyo          | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   79 |    0 |    1 |           0 |      0 |    1 |    1 |       1 |      0 |    7 |
|   11 | Uzmal            |  6 |       1 |    0 |    0 |    0 |     0 |    0 |    1 |    0 |    8 |    0 |    1 |           0 |      0 |    2 |    1 |       0 |      0 |    7 |
|   12 | Seela            |  7 |       5 |    0 |   12 |    1 |     6 |    1 |    0 |    0 |   14 |    1 |    1 |           0 |      1 |    3 |    0 |       0 |      0 |    6 |
|   16 | Pierre           |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    5 |   30 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |   10 |
|   17 | MaskedPain       |  6 |       1 |    1 |   10 |    0 |     0 |    0 |    0 |    2 |   31 |    2 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    7 |
|   18 | alFadl           | 10 |       9 |    3 |   41 |    1 |     7 |    2 |    1 |    2 |   54 |    3 |    1 |           0 |      0 |    3 |    0 |       0 |      0 |   21 |
|   19 | Chaggai.3        |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   42 |    0 |    0 |           0 |      0 |    1 |    0 |       1 |      0 |    0 |
|   22 | Mate.            |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       1 |      0 |    0 |
|   31 | Valeriy.         |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   13 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   32 | Frommik.         |  5 |       3 |    0 |   19 |    0 |     0 |    1 |    0 |    1 |    8 |    0 |    0 |           0 |      3 |    0 |    0 |       0 |      0 |    2 |
|   33 | Alizee.          |  5 |       1 |    0 |    4 |    0 |     0 |    0 |    0 |    0 |    3 |    1 |    0 |           0 |      0 |    2 |    0 |       1 |      0 |    0 |
|   35 | Lucrece.         |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   20 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|   62 | Gebhard.         |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   13 |    1 |    0 |           0 |      0 |    0 |    0 |       1 |      0 |    2 |
|   82 | Petronela.       |  5 |      12 |    2 |   52 |    2 |     9 |    2 |    0 |    0 |    1 |    0 |    0 |           0 |      2 |    0 |    0 |       0 |      1 |    8 |
|   85 | Gention.         |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    5 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   89 | Elke.            |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |    7 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    4 |
|   91 | Tycho.           |  8 |      17 |    0 |   75 |   14 |    52 |    0 |    0 |    1 |   12 |    1 |    0 |           1 |      1 |    1 |    0 |       0 |      1 |   16 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Carcosan Tatters" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

#### Projection GCXII

W-D-L 7-1-7

The Tatters could be in position to upset for a Divisional title, but hopes are not tremendously high. The team's main goal is to get more wins than losses and to not be embarassed out there. Probably not a recipe for glory.


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Sparrow**         | Blitzer        |   23 |    7 |   16 |   46 |   32 |    4 |    1 |    4 |    2 |    1 |    3 |  131 |
| Gention           | Blitzer        |   33 |    6 |   19 |   58 |   10 |    4 |    0 |   17 |    8 |    2 |    7 |  123 |
| *BSEncef*          | Blitzer        |   ?? |   ?? |   ?? |   49 |   23 |           31 |             2 |    1 |    0 |    0 |    3 |   121 |
| **Arya**               | Blitzer        |   19 |    6 |   19 |   44 |   25 |    4 |    0 |    3 |    0 |    0 |    5 |  110 |
| *Scrapie*          | Blitzer | ?? | ?? | ?? | 49 | 18 | 0 | 1 | 10 | 4 | 3 | 4 | 110 |
| **Orna**               | Blitzer        |   36 |    9 |   28 |   73 |   21 |    4 |    0 |    6 |    3 |    1 |    4 |  107 |
| **Pierre**             | Heavy |   31 |    6 |   31 |   68 |    0 |    0 |    0 |   20 |   10 |    2 |    6 |   94 |
| Tycho             | Thrower          |   29 |    8 |   19 |   56 |    4 |   51 |    2 |    2 |    1 |    0 |    3 |   88 |
| **Marley**             | Blitzer        |   25 |    5 |   18 |   48 |    9 |    3 |    1 |   13 |    2 |    2 |    4 |   86 |
| **MaskedPain**         | Blitzer        |   19 |    3 |   20 |   42 |   12 |    3 |    0 |    6 |    0 |    0 |    3 |   66 |
| **FlamingLion**        | Blocker  |   23 |    2 |   15 |   40 |    0 |    0 |    1 |    7 |    3 |    1 |    6 |   54 |
| **OreSmitingMaster**   | Blocker  |   37 |    8 |   24 |   69 |    0 |    0 |    1 |   10 |    3 |    0 |    5 |   53 |
| LastForsakenVenom | Blocker  |   20 |    1 |   21 |   42 |    0 |    0 |    0 |    3 |    4 |    1 |    7 |   51 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Carcosan Tatters" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```



The Tatters thrive on teamwork and defense, neither of which lends itself well to big flashy stars taking over a match. Back in the Old-Era [[BSEncef]] (now the team's manager) was one of those big flashy stars, but he hasn't tried to develop that kind of mindset in the current players. [[Gention]] had been holding things down as the best player for the last couple of tournaments (since the awful GCVII campaign in which there was a major redevelopment), but [[Sparrow]] will soon be taking her place and may emerge as the next superstar.

Though [[pierre]] is third on the active list for SPP and healthy, it was in flux until quite late whether he would suit up for the GCXI season. Also of note, [[adeno]] was an old veteran who didn't do much in the revitalization but has played for the team by far the longest.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    6 | Marley            | Blitzer       |       6 |      1 | 210000 | 30000 |
|   89 | RavenousOblivion. | Blocker |       6 |      1 | 170000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Carcosan Tatters" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

BSEncef runs the team cheaply but humbly. He basically has a grind it out ethic that a lot of fans and other players respect.

### Fans

The GCV Memorial tournament was a bad move for the Tatters' fanbase, losing a lot of goodwill built up in GCIX.

The Tatters' main rivals are the [Orbital Machine](orbitalmachine). They have a similar defensive playbook, but that's the main basis for any animosity. Fans of the Tatters, like the players on the Tatters, don't really care much for what other teams do. Aesthetically, they are near diametric opposites of the [Glorious Hounds](glorioushounds) who prefer to make everything graceful and easy looking.

### Famous Games

