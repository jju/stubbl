# Kicking Mules

The Kicking Mules were the first and third winners of the Orange Goblet, a championship for the Open Division of the UBBL. When expansion came to the Green Cup, the Mules were a shoo-in for inclusion.

## Playbook

The Mules use the Darvati Dorf playbook, which is built on a lineup slow tacklers to block off the centre, two attacking blitzers and two safety blitzers with a couple of ball handling runners. The emphasis is on toughness and defense rather than speed.

## Active Roster

Going into the GCXII season the Mules have a lot of flexibility with many players under contract and excited to play in the big leagues. If they do end up making the playoffs we'll see a major selection, but if they keep up with their basic reinvestment in development (and durability) there could be room for a division-spanning dynasty.

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Pilvi     | Runner     49 |       2 |   16 |         1 | 170000 |     0 |
|    2 | Bianka    | Runner  |   88 |       8 |   43 |         3 | 180000 |     0 |
|    3 | Mawunyo   | Blitzer |   38 |       2 |   21 |         1 | 140000 |     0 |
|    4 | Jade      | Blitzer |    9 |       2 |   15 |         1 | 100000 |     0 |
|    5 | Danilo    | Attacker |   14 |       2 |   16 |         1 | 110000 |     0 |
|    6 | Aygul     | Attacker |   25 |       1 |   13 |         1 | 130000 |     0 |
|    7 | Volker    | Blocker  |   22 |       4 |   23 |         2 | 120000 |     0 |
|    8 | Reshat    | Blocker  |   16 |       5 |   25 |         2 | 110000 |     0 |
|    9 | Yijun     | Blocker  |    6 |       1 |   10 |         1 |  90000 |     0 |
|   10 | Khloe     | Blocker  |   10 |       5 |   24 |         2 |  90000 |     0 |
|   11 | Thera     | Blocker  |   31 |       8 |   49 |         3 | 130000 |     0 |
|   12 | Lasse     | Blocker  |   23 |       8 |   54 |         4 | 110000 |     0 |
|   16 | Renatus   | Heavy  |   44 |       6 |   28 |         2 | 230000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Nkosana   | Runner       |   92 |       4 |   25 |         2 | 210000 |     0 |
|    2 | Umut      | Runner       |   31 |       1 |    8 |         1 | 140000 |     0 |
|    3 | Alida     | Blitzer      |   60 |       7 |   36 |         2 | 160000 |     0 |
|    4 | Lambert   | Blitzer      |   59 |       8 |   42 |         3 | 190000 |     0 |
|    5 | Amalie    | Attacker |   58 |       8 |   45 |         3 | 170000 |     0 |
|    6 | Gottfried | Attacker |   60 |       7 |   37 |         2 | 180000 |     0 |
|    7 | Ratna     | Blocker      |   11 |       1 |   10 |         1 |  90000 |     0 |
|    8 | Maral     | Blocker      |   17 |       1 |   13 |         1 | 120000 |     0 |
|    9 | Torborg   | Blocker      |   34 |       8 |   47 |         3 | 130000 |     0 |
|   10 | Halgurd   | Blocker      |   24 |       6 |   44 |         3 | 120000 |     0 |
|   12 | Juan      | Blocker      |    0 |       1 |    2 |         0 |  70000 |     0 |
|   16 | Yaxkin    | Heavy  |    2 |       2 |    3 |         0 | 160000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Kicking Mules" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Mules | Open     |   34 |    4 |   16 |   54 |  65.502 |   89 |   61 |  130 |      84 |    3 |
| Mules | Pro      |    3 |    0 |    0 |    3 | 100.000 |    6 |    2 |   10 |       9 |    2 |
| Mules | Street   |    0 |    1 |    0 |    1 |  50.000 |    1 |    1 |    4 |       4 |    1 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Kicking Mules" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Mules |   37 |    5 |   16 |   58 | 67.877 |   96 |   64 |  144 |      97 |    6 |

```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Kicking Mules" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* Orange Goblet I - Orange Goblet Champions [[team1stplace#orange goblet]]
* Orange Goblet II - Orange Goblet Runner-Up [[team2ndplace#orange goblet ii]]
* Orange Goblet II - Gorefield Honour [[teamcasualties#orange goblet ii]]
* UBBL Challenge III - Gorefield Honour [[teamcasualties#ubbl challenge ii]]
* Orange Goblet III - Orange Goblet Champions [[team1stplace#orange goblet iii]]
* Orange Goblet III - Gorefield Honour [[teamcasualties#orange goblet iii]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Mules | Champions Circuit  |    3 |    0 |    0 |      3 |     100 |    6 |    2 |   10 |      9 |    2 |
| Mules | **Orange Goblet III** |   11 |    1 |    1 |     13 | 88.4615 |   25 |    7 |   32 |     30 |    2 |
| Mules | UBBL Challenge III    |    4 |    0 |    2 |      6 | 66.67 |   10 |    8 |   13 |      8 |    2 |
| Mules | UBBL Challenge        |    2 |    1 |    1 |      4 |    62.50 |    6 |    4 |   10 |     10 |    1 |
| Mules | **Orange Goblet**     |    8 |    0 |    5 |     13 | 61.54 |   21 |   16 |   23 |     10 |    1 |
| Mules | UBBL Challenge II     |    3 |    0 |    2 |      5 |      60.00 |    7 |    8 |   11 |      4 |    1 |
| Mules | Orange Goblet II      |    6 |    2 |    5 |     13 | 53.8462 |   20 |   18 |   30 |     22 |   -4 |
| Mules | StUBBL Scramble       |    0 |    1 |    0 |      1 |      50.00 |    1 |    1 |    4 |      4 |    1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Kicking Mules" ORDER BY mr.win_pct DESC limit 16;
```


## History

The Mules were never a part of the original era UBBL, though after the interruption they were clamouring to get in. 

### Seasons

They were snakebit in direct elimination in the first three UBBL Challenge tournaments though they did not play badly. So when the Orange Goblet tournament was organized in an effort to give the not-quite Green Cup ready teams a venue for more regular play, the PicoCorp entity rushed at it (faster than most of their lineup can, went the joke). 

That the Mules managed to win the inaugural Orange Goblet season was impressive (especially since they played as the lesser team through all three playoff matches), but the legend of the Mules began with their beating of the [Old Wyrms](oldwyrms) in the first round of the Champions Circuit, a result no one expected, especially as the Mules' star runner [[Nkosana]] was injured.

#### projection Next Season

W-D-L 9-0-6

For their first season in the Green Cup, expectations are high. Based on their Orange Goblet performances, they're projected for 27 regular season points in GCXII. While that would give them a playoff berth in GCXI (they're being slotted into the Heaps which had a couple of team-best-records in GCXI), as a projection it is the best any team is slated for in GCXII.

#### summary last season (OGIII)

| Team  | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Mules |     1 |       2 |    2 |   25 |    0 |        0 |      1 |          1 |    5 |     51 |     0 |    1 |   23 |           0 |           2 |
| Mules |     2 |       4 |    2 |   21 |    0 |        0 |      0 |          0 |    1 |     57 |     0 |    1 |   13 |           2 |           0 |
| Mules |     3 |       9 |    2 |   45 |    1 |        2 |      1 |          0 |    1 |     41 |     0 |    1 |   14 |           1 |           2 |
| Mules |     4 |       2 |    1 |   21 |    0 |        0 |      0 |          0 |    3 |     54 |     1 |    1 |   14 |           1 |           1 |
| Mules |     5 |       3 |    2 |   29 |    0 |        0 |      0 |          0 |    1 |     53 |     1 |    1 |   13 |           2 |           1 |
| Mules |     6 |       6 |    1 |   27 |    2 |        7 |      2 |          0 |    1 |     49 |     1 |    1 |   12 |           2 |           1 |
| Mules |     7 |       4 |    3 |   34 |    0 |        0 |      0 |          0 |    4 |     54 |     0 |    1 |   22 |           0 |           3 |
| Mules |     8 |       5 |    2 |   20 |    0 |        0 |      0 |          0 |    2 |     45 |     0 |    1 |   15 |           0 |           2 |
| Mules |    10 |       3 |    2 |   33 |    0 |        0 |      0 |          0 |    0 |     48 |     1 |    1 |   11 |           0 |           2 |
| Mules |    11 |       4 |    2 |   45 |    0 |        0 |      0 |          0 |    4 |     46 |     0 |    1 |   19 |           2 |           0 |
| Mules |    QF |       4 |    2 |   36 |    0 |        0 |      0 |          0 |    1 |     57 |     0 |    1 |   13 |           2 |           0 |
| Mules |    SF |       5 |    2 |   36 |    0 |        0 |      0 |          0 |    5 |     58 |     0 |    1 |   21 |           2 |           1 |
| Mules |    OG |       6 |    2 |   35 |    0 |        0 |      0 |          0 |    4 |     44 |     0 |    1 |   19 |           2 |           1 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 30 AND pl.f_tname = "Kicking Mules" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

The Mules' Orange Goblet campaign was an historic defensive season. While it wasn't the fewest TDs allowed in an Open or Pro division play, keeping opponents below a 1 TD/match average had only happened in one comparable length season before.

| Team             | Season            | won  | draw | lost | played | win_pct | gf   | ga   | GF_avg | GA_avg | cas  | tcdiff | ff   |
|------------------|-------------------|------|------|------|--------|---------|------|------|--------|--------|------|--------|------|
| Mules            | Orange Goblet III |   11 |    1 |    1 |     13 | 88.4615 |   25 |    7 |  1.923 |  0.538 |   32 |     30 |    2 |
| Kaiju Dynamo     | UBBL Challenge IV |    2 |    0 |    1 |      3 | 66.6667 |    7 |    2 |  2.333 |  0.667 |    9 |      5 |    1 |
| Mules            | Champions Circuit |    3 |    0 |    0 |      3 |     100 |    6 |    2 |  2.000 |  0.667 |   10 |      9 |    2 |
| Geometers        | UBBL Challenge    |    2 |    0 |    2 |      4 |      50 |    5 |    3 |  1.250 |  0.750 |    9 |      6 |    2 |
| Carcosan Tatters | Green Cup VI      |   11 |    1 |    5 |     17 | 67.6471 |   20 |   15 |  1.176 |  0.882 |   23 |     10 |    5 |
| Ravenous Eagles  | UBBL Challenge    |    3 |    1 |    1 |      5 |      70 |    7 |    5 |  1.400 |  1.000 |    5 |     -2 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, round(mr.gf/mr.played,3) AS GF_avg, round(mr.ga/mr.played,3) AS GA_avg, mr.cas, mr.tcdiff, mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE tours.f_did <> 4 ORDER BY GA_avg ASC limit 10;
```


#### roster by season


| #    | Player  | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|---------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Pilvi   | 13 |      29 |    9 |  171 |    2 |     5 |    0 |    0 |    2 |   32 |    1 |    1 |           0 |      1 |    1 |    0 |       0 |      0 |   38 |
|    2 | Bianka  |  3 |       7 |    2 |   52 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    6 |
|    2 | Umut    |  8 |       9 |    6 |  108 |    1 |     4 |    2 |    0 |    1 |    9 |    1 |    2 |           0 |      2 |    0 |    0 |       0 |      0 |   31 |
|    3 | Mawunyo | 13 |       9 |    7 |   70 |    0 |     0 |    2 |    1 |    1 |   40 |    0 |    1 |           0 |      1 |    0 |    1 |       0 |      0 |   30 |
|    4 | Lambert |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    4 | Jade    | 10 |       3 |    1 |    6 |    0 |     0 |    0 |    0 |    0 |   42 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    3 |
|    5 | Danilo  |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   61 |    0 |    0 |           0 |      0 |    0 |    1 |       1 |      0 |    2 |
|    5 | Amalie  |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   30 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    7 |
|    6 | Aygul   | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    5 |   96 |    1 |    3 |           0 |      0 |    0 |    1 |       0 |      0 |   25 |
|    7 | Ratna   | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   50 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |   11 |
|    7 | Volker  |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   25 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    6 |
|    8 | Maral   | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    6 |   65 |    0 |    1 |           0 |      0 |    1 |    0 |       0 |      0 |   17 |
|    9 | Torborg |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   15 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    9 | Yijun   | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   38 |    0 |    0 |           0 |      0 |    1 |    1 |       0 |      0 |    6 |
|   10 | Khloe   |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   10 | Halgurd |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   30 |    0 |    0 |           0 |      0 |    1 |    1 |       0 |      0 |    2 |
|   11 | Thera   |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   13 |    0 |    1 |           0 |      1 |    0 |    0 |       0 |      0 |    7 |
|   12 | Juan    |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    8 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   12 | Lasse   | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   62 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |   11 |
|   16 | Renatus |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    5 |
|   16 | Yaxkin  |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   11 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Orange Goblet III" AND pl.f_tname = "Kicking Mules" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Nkosana**   | Runner       |   15 |    1 |    9 |   25 |   26 |    5 |    1 |    0 |    1 |    0 |    1 |   92 |
| **Bianka**    | Runner       |   27 |    3 |   13 |   43 |   12 |   30 |    2 |    3 |    0 |    1 |    2 |   88 |
| **Gottfried** | Attacker |   20 |    3 |   14 |   37 |    0 |    0 |    0 |   16 |    9 |    0 |    2 |   60 |
| **Alida**     | Blitzer      |   21 |    3 |   12 |   36 |    8 |    3 |    1 |    6 |    1 |    1 |    3 |   60 |
| **Lambert**   | Blitzer      |   25 |    3 |   14 |   42 |    6 |    3 |    1 |    5 |    1 |    2 |    4 |   59 |
| **Amalie**    | Attacker |   27 |    3 |   15 |   45 |    0 |    0 |    0 |   12 |    5 |    2 |    4 |   58 |
| **Pilvi**     | Runner       |   11 |    2 |    3 |   16 |   12 |    4 |    0 |    1 |    0 |    1 |    1 |   49 |
| **Renatus**   | Heavy  |   18 |    0 |   10 |   28 |    0 |    0 |    0 |    6 |    1 |    0 |    6 |   44 |
| **Mawunyo**   | Blitzer      |   15 |    2 |    4 |   21 |    8 |    1 |    1 |    2 |    1 |    0 |    1 |   38 |
| **Torborg**   | Blocker      |   28 |    4 |   15 |   47 |    0 |    0 |    0 |    5 |    2 |    0 |    4 |   34 |
| Halldor  | Runner       |    6 |    2 |    4 |   12 |    6 |    3 |    0 |    0 |    0 |    0 |    2 |   31 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Kicking Mules" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

[[Nkosana]] was the key to the Mules' offense, and could find a place in many even more generally skilled teams.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    1 | Nkosana   | Runner       |       4 |      1 | 210000 |     0 |
|    5 | Amalie    | Attacker |       8 |      2 | 170000 |     0 |
|    6 | Gottfried | Attacker |       7 |      1 | 180000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Kicking Mules" GROUP BY pl.name ORDER BY pl.nr ASC;
```

#### Goblet Winners

* Nkosana - OGI
* Bianka - OGI, OGIII
* Renatus - OGI
* Lambert - OGI, OGIII ?
* Gottfried - OGI
* Amalie - OGI, OGIII
* Torborg - OGI, OGIII
* Alida - OGI
* Reshat - OGI
* Lasse - OGI, OGIII
* Halgurd - OGI, OGIII
* Thera - OGI, OGIII
* Volker - OGI, OGIII
* Khloe - OGI, OGIII
* Janne - OGI
* Pilvi - OGIII
* Umut
* Mawunyo
* Jade
* Danilo
* Aygul
* Ratna
* Maral
* Yijun
* Juan ?
* Renatus
* Yaxkin ?



### Management

Pico Corp picked up the sponsorship of the mules who'd been a very effectively run community team.

### Fans

The Mules are steadily gaining fans as they win. They haven't had a really terrible season yet so there's a lot of interest.

### Famous Games

Champions Circuit victory over the [Old Wyrms](oldwyrms)
