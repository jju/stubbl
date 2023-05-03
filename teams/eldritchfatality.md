# Eldritch Fatality

A youngish team, they weren't active in the Green Cup before the interruption, but have come along as fierce competitors in the Modern Era.

## Playbook

The Eldritch Fatality use the Drop Eagle playbook. It's an adaptation of the Hermann playbook that again requires more skilled players to run it effectively. The strategy dispenses with the catcher position entirely, instead using four skilled blitzers and two runners to handle the ball, and two dedicated ball-hawks to attack the opposing ball-carriers. It's an aggressive defense that does as much work as their offense.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Filipa    | Runner    |  223 |       7 |   73 |         5 | 270000 |  50000 |
|    2 | Koralo    | Runner    |   70 |       2 |   16 |         1 | 180000 |      0 |
|    3 | Ilanit    | Blitzer   |   32 |       2 |   10 |         1 | 170000 |  10000 |
|    4 | Betul     | Blitzer   |  164 |       6 |   50 |         3 | 230000 |      0 |
|    5 | Beatrix   | Blitzer   |  143 |       9 |   83 |         6 | 270000 |  60000 |
|    6 | Ayane     | Blitzer   |   84 |       4 |   27 |         2 | 200000 |      0 |
|    7 | Eydis     | Lineman   |    0 |       1 |    1 |         0 |  70000 |      0 |
|    8 | Nimet     | Lineman   |    1 |       2 |    4 |         0 |  70000 |      0 |
|    9 | Danel     | Lineman   |   18 |       4 |   23 |         2 | 130000 |  10000 |
|   14 | Maritites | Witch Elf |    0 |       1 |    1 |         0 | 110000 |      0 |
|   15 | Huguo     | Witch Elf |   31 |       5 |   31 |         2 | 190000 |  20000 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    2 | Lavender  | Runner    |    6 |       1 |    1 |         0 |  80000 |      0 |
|    5 | Parveen   | Blitzer   |    0 |       1 |    1 |         0 | 100000 |      0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   24 | Lynwood.    | Blitzer   |   68 |       2 |   19 |         1 | 200000 |     0 |
|   46 | Ishii.      | Assassin  |   32 |       5 |   65 |         4 | 190000 | 40000 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Eldritch Fatality" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```


## Records

### Record by Division 

| Team              | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-------------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Eldritch Fatality | Pro      |   54 |   10 |   35 |   99 | 58.489 |  261 |  207 |  125 |     -32 |    2 |
| Eldritch Fatality | Open     |    5 |    0 |    3 |    8 | 62.500 |   28 |   19 |   13 |       0 |    3 |
| Eldritch Fatality | Street   |    0 |    1 |    1 |    2 | 25.000 |    0 |    2 |    0 |       0 |   -1 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Eldritch Fatality" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team              | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-------------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Eldritch Fatality |   59 |   11 |   39 |  109 | 55.942 |  289 |  228 |  138 |     -32 |    4 |

```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Eldritch Fatality" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup Classic 06 - Tough Brake of Alsoran [[team3rdplace#gcc06]]
* Green Cup VII - Pits Division Champions [[teamdivision#gcvii]]
* Green Cup IX - Pits Division Champions [[teamdivision#gcix]]
* Green Cup IX - Classic Conference Champions [[team2ndplace#gcix]] & [[teamconference#gcix]]
* Green Cup XI - Pits Division Champions [[teamdivision#gcxi]]
* Green Cup XI - Tough Brake of Alsoran [[team3rdplace#gcxi]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Eldritch Fatality | UBBL Challenge       |    3 |    0 |    1 |      4 |      75 |   16 |   10 |    7 |      1 |    1 |
| Eldritch Fatality | Green Cup XI         |   13 |    0 |    5 |     18 | 72.2222 |   53 |   35 |   20 |    -14 |    2 |
| Eldritch Fatality | Green Cup VIII       |   10 |    3 |    4 |     17 | 67.6471 |   37 |   27 |   23 |      5 |   -1 |
| Eldritch Fatality | Green Cup Classic 06 |    4 |    4 |    1 |      9 | 66.6667 |   24 |   17 |   10 |      1 |    2 |
| Eldritch Fatality | Green Cup VII        |   11 |    0 |    7 |     18 | 61.1111 |   47 |   40 |   15 |    -11 |    2 |
| Eldritch Fatality | Green Cup IX         |   11 |    1 |    7 |     19 | 60.5263 |   57 |   40 |   22 |      1 |   -1 |
| Eldritch Fatality | UBBL Challenge IV    |    2 |    0 |    2 |      4 |      50 |   12 |    9 |    8 |     -1 |    2 |
| Eldritch Fatality | Champions Circuit    |    1 |    0 |    1 |      2 |      50 |    5 |    5 |    0 |     -7 |    0 |
| Eldritch Fatality | Green Cup X          |    4 |    2 |   10 |     16 |   31.25 |   38 |   43 |   17 |     -7 |   -2 |
| Eldritch Fatality | StUBBL Scramble      |    0 |    1 |    1 |      2 |      25 |    0 |    2 |    0 |      0 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Eldritch Fatality" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Eldritch Fatality were acitve in the lower divisions of the old-era UBBL but those records weren't kept. The Iskander family jumped at the chance to legitimize the team in the Green Cup Classic and even more so once the leagues were consolidated for GCVII.

### Seasons

In Green Cup Classic 06 the Fatality were undefeated until the Orlock Machine handed them a loss in the semi-finals. They're now seen as perennial contenders with a second place (and tops of the Pits Division and Classic Conference) in Green Cup IX. That was the best the Fatality had ever done and was right in line with the pre-season expectations.

Sadly for Fatality fans they followed up GCIX with an abysmal last-in-the-Pits finish. None of the projection systems had guessed things would go so badly the Fatality would face relegation so quickly (11-2-6 and Green Cup Champion was our thought). They did fine in the UBBL Challenge IV and didn't have to face the ignominy of playing full time in the Open Division, but they had something to prove in GCXI.

In the end, the Fatality seriously outplayed expectations, handily becoming Pits Division Champion with 11 regular season wins. They ran into an exceptionally good Glorious Hounds team in the conference finals, and had to settle for a third place finish.

#### GCXII Projection

W-D-L 7-2-6 

The Fatality have a tougher task to defend their division championship with the very good expansion Palace Orchids also coming to the Pits. The Fatality are currently projected to come in second to the Orchids, but many think that's giving too much credit to the lower level of competition in the Open Division.

#### summary last season

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Eldritch Fatality |     1 |      11 |    4 |   67 |    4 |       11 |      4 |          0 |    3 |     56 |     1 |    1 |   27 |           4 |           2 |
| Eldritch Fatality |     2 |      13 |    4 |   50 |    4 |        6 |      4 |          1 |    2 |     46 |     2 |    1 |   27 |           1 |           4 |
| Eldritch Fatality |     3 |      12 |    5 |   63 |    3 |        8 |      3 |          0 |    3 |     39 |     2 |    1 |   29 |           0 |           5 |
| Eldritch Fatality |     4 |      15 |    3 |   38 |    7 |       17 |      7 |          0 |    1 |     29 |     0 |    1 |   23 |           2 |           3 |
| Eldritch Fatality |     5 |      12 |    2 |   37 |    5 |       11 |      5 |          0 |    0 |     31 |     1 |    1 |   16 |           1 |           2 |
| Eldritch Fatality |     6 |      15 |    3 |   60 |    5 |       10 |      5 |          0 |    1 |     42 |     2 |    1 |   21 |           3 |           1 |
| Eldritch Fatality |     7 |      12 |    3 |   36 |    5 |       21 |      5 |          0 |    0 |     38 |     2 |    1 |   19 |           3 |           1 |
| Eldritch Fatality |     8 |      16 |    4 |   93 |    8 |       14 |      8 |          1 |    2 |     47 |     0 |    1 |   31 |           6 |           4 |
| Eldritch Fatality |     9 |       4 |    2 |   26 |    0 |        0 |      0 |          0 |    1 |     33 |     4 |    1 |   13 |           1 |           2 |
| Eldritch Fatality |    10 |      14 |    2 |   54 |    5 |       21 |      5 |          1 |    1 |     29 |     1 |    1 |   20 |           2 |           4 |
| Eldritch Fatality |    11 |      12 |    4 |   57 |    2 |       -1 |      2 |          0 |    3 |     45 |     0 |    1 |   25 |           4 |           1 |
| Eldritch Fatality |    12 |      11 |    3 |   46 |    4 |        9 |      4 |          0 |    0 |     26 |     1 |    1 |   18 |           0 |           3 |
| Eldritch Fatality |    13 |       8 |    2 |   27 |    2 |        9 |      2 |          1 |    0 |     18 |     2 |    1 |   15 |           2 |           0 |
| Eldritch Fatality |    14 |       8 |    2 |   57 |    4 |       13 |      4 |          0 |    0 |     26 |     0 |    1 |   15 |           3 |           2 |
| Eldritch Fatality |    15 |      15 |    2 |   81 |    7 |       22 |      7 |          0 |    0 |     36 |     2 |    1 |   18 |           2 |           8 |
| Eldritch Fatality |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    1 |    5 |           1 |           0 |
| Eldritch Fatality |    QF |      15 |    4 |   76 |    6 |        1 |      6 |          0 |    2 |     28 |     3 |    1 |   27 |           4 |           0 |
| Eldritch Fatality |    SF |      14 |    3 |   52 |    7 |       16 |      7 |          2 |    1 |     52 |     3 |    1 |   27 |           3 |           4 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Eldritch Fatality" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Filipa      | 18 |      59 |    1 |  247 |   47 |   134 |    2 |    2 |    0 |   12 |    1 |    1 |           3 |      3 |    6 |    1 |       0 |      0 |   59 |
|    2 | Koralo      | 15 |      42 |   12 |  223 |   19 |    11 |   22 |    0 |    2 |   14 |    0 |    2 |           2 |     11 |    3 |    2 |       0 |      0 |   69 |
|    3 | Ilanit      |  9 |      15 |    3 |   55 |    1 |     1 |    6 |    1 |    0 |   13 |    1 |    4 |           0 |      4 |    3 |    0 |       0 |      0 |   32 |
|    4 | Betul       | 15 |      20 |   13 |  141 |    2 |     7 |   14 |    1 |    1 |   21 |    1 |    0 |           1 |      0 |    4 |    3 |       1 |      0 |   45 |
|    5 | Beatrix     | 13 |      13 |    3 |   43 |    3 |    18 |    6 |    1 |    2 |   32 |    2 |    2 |           1 |      0 |    2 |    0 |       1 |      0 |   28 |
|    6 | Ayane       | 14 |      19 |   14 |   91 |    1 |     3 |   10 |    0 |    2 |   55 |    6 |    1 |           0 |      5 |    4 |    2 |       0 |      0 |   52 |
|    9 | Danel       | 16 |       1 |    0 |    4 |    1 |     4 |    0 |    0 |    1 |   48 |    0 |    3 |           0 |      0 |    3 |    1 |       1 |      0 |   18 |
|   15 | Huguo       | 18 |       9 |    0 |   29 |    1 |     5 |    3 |    0 |    2 |  119 |    3 |    2 |           1 |      1 |    3 |    6 |       0 |      0 |   15 |
|   34 | Fosgood.    |  2 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    7 |    1 |    0 |           0 |      1 |    0 |    0 |       2 |      0 |    0 |
|   63 | Atte.       |  9 |      18 |    4 |   61 |    1 |     1 |    8 |    1 |    0 |   13 |    1 |    0 |           0 |      1 |    4 |    1 |       2 |      R |   15 |
|   67 | Yair.       | 17 |       5 |    1 |   17 |    0 |     0 |    4 |    0 |    1 |   49 |    1 |    0 |           0 |      0 |    5 |    2 |       1 |      R |    5 |
|   68 | Xaver.      | 18 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   51 |    2 |    2 |           0 |      0 |    6 |    2 |       0 |      R |   12 |
|   72 | Ermenrich.  |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   15 |    0 |    0 |           0 |      0 |    0 |    0 |       2 |      R |    2 |
|   85 | Seela       |  8 |       4 |    1 |    7 |    1 |    -1 |    2 |    0 |    0 |   22 |    0 |    1 |           0 |      0 |    3 |    0 |       1 |      1 |    9 |
|   87 | Gogo.       |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |
|   93 | Vihaio.     |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   20 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      1 |    4 |
|   94 | Dunstan.    | 12 |       0 |    0 |    2 |    1 |     5 |    0 |    0 |    5 |  122 |    7 |    0 |           0 |      0 |    1 |    0 |       0 |      1 |   11 |
|   97 | Mieczyslaw. |  4 |       1 |    0 |    0 |    0 |     0 |    1 |    0 |    0 |    8 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      1 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Eldritch Fatality" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* may have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Filipa**   | Runner    |   39 |    4 |   30 |   73 |    9 |  163 |    3 |    0 |    1 |    0 |    5 |  223 |
| Atte    | Blitzer   |   26 |    3 |   19 |   48 |   48 |    4 |    1 |    1 |    0 |    0 |    6 |  182 |
| **Betul**    | Blitzer   |   24 |    3 |   23 |   50 |   35 |    9 |    7 |    3 |    0 |    0 |    6 |  164 |
| **Beatrix**  | Blitzer   |   42 |   10 |   31 |   83 |   23 |   12 |    4 |    7 |    0 |    0 |    8 |  143 |
| Qtpi    | Runner    |   29 |    4 |   17 |   50 |   25 |   31 |    2 |    1 |    0 |    0 |    3 |  127 |
| *Bill*    | Runner    |   18 |    5 |    8 |   31 |    2 |   68 |    1 |    1 |    0 |    0 |    5 |  103 |
| Grimly  | Blitzer   |   35 |    4 |   19 |   58 |   21 |    8 |    1 |    5 |    2 |    1 |    2 |   99 |
| **Ayane**    | Blitzer   |   12 |    1 |   14 |   27 |   17 |    3 |    2 |    2 |    0 |    1 |    4 |   84 |
| Mo      | Blitzer   |   28 |    7 |   12 |   47 |   15 |    6 |    1 |    3 |    0 |    1 |    4 |   81 |
| **Koralo**   | Runner    |   11 |    0 |    5 |   16 |   12 |   20 |    0 |    0 |    2 |    0 |    2 |   70 |
| Fosgood | Attacker |   29 |    4 |   16 |   49 |    9 |    4 |    3 |    5 |    1 |    0 |    4 |   69 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Eldritch Fatality" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


The Fatality are just generally good at BludBol. They spread out their scoring better and with [[Filipa]] still not on the downswing there's no reason this team can't be what the [Irregular Cogs](irregularcogs) have been trying to be for their existence.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|   81 | Bill    | Runner    |       4 |      1 | 180000 |     0 |
|   82 | Qtpi    | Runner    |       7 |      1 | 230000 | 40000 |
|   94 | Dunstan | Attacker |       6 |      1 | 250000 | 30000 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Eldritch Fatality" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

The Iskander family is heavily invested in culture for Stacksburg. Where their actual funding and power came from is generally on the seedy side, but they've been here a long time, and were apparently upset they'd missed the boat in the old-era UBBL. 

### Fans

The Fatality have a bit of a chip on their shoulder. They are a really good team that wins wins wins, but then they can't quite get the championship into their house. The [Orbital Machine](orbitalmachine) and [Old Wyrms](oldwyrms) have both beaten them on their paths to a Green Cup, and the mere fact that such an "objectively lousy" team like the [Ravenous Eagles](ravenouseagles) has won a Cup before them rankles badly. But the lack of Cup success is only a part of using the same playbook as the [Irregular Cogs](irregularcogs) which they are perpetually overshadowed by even though they were the better team (at least before the shitshow that was GCX).

### Famous Games
 
 