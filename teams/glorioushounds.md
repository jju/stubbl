# Glorious Hounds

The Hounds are all about deep passes to wide open receivers and how that is "the only true way" to play BludBol. They have never quite lived up to their own hype, but it is impossible to deny the prettiness of their game.

## Playbook

The Glorious Hounds use the High Extension playbook, a venerable adaptation of the Hermann technique. Generally to play this style, you need a higher skill level. The playbook uses four receivers but only two blitzers and no big guy option. The idea is usually for the thrower to hang onto the ball longer than in the Excelsior or Drop Eagle playbooks giving the catchers time to get open downfield.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Glorious Hounds" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Lineup

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Oxana    | Thrower  |   Star |       3 |
| Cecile   | Thrower  |  Superstar |       6 |
| Udo      | Catcher  |   Superstar |       5 |
| Ziba     | Catcher  |   Superstar |       2 |
| Veles    | Blitzer  |   Emerging Star |       3 |
| Florinda | Blitzer  |   Superstar |       5 |
| Owain    | Line  |    Experienced |       3 |
| Tsutsiko | Line  |   Experienced |       3 |
| Valeriy  | Line  |   Veteran |       3 |
| August   | Kicker  |   Veteran |       3 |
| Wawatam  | Line  |    Experienced |       2 |
| Branson  | Catcher  |   Star |       3 |
| Irenaeus | Catcher  |   Star |       3 |

### Bench

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Lestari  | Line  |    Rookie |       1 |
| Zeenat   | Line  |    Rookie |       1 |
| Aiza     | Line  |    Rookie |       1 |

## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Glorious Hounds | Pro      |   55 |   17 |   43 |  115 | 54.365 |  360 |  279 |  103 |    -121 |    2 |
| Glorious Hounds | Open     |    7 |    0 |    3 |   10 | 66.667 |   33 |   19 |    8 |     -18 |    5 |
| Glorious Hounds | Street   |    5 |    3 |    4 |   12 | 54.167 |   23 |   16 |   18 |      -6 |   -2 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Glorious Hounds" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Glorious Hounds |   67 |   20 |   50 |  137 | 56.805 |  416 |  314 |  129 |    -145 |    5 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Glorious Hounds" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup IV - Runner-Up [[team2ndplace#gciv]]
* Green Cup IX - Heaps Division Champions [[teamdivision#gcix]]
* UBBL Challenge IV - UBBL Pennant [[team1stplace#uciv]]
* Green Cup XI - Heaps Division Champions [[teamdivision#gcxi]]
* Green Cup XI - Classic Conference Champions [[teamconference#gcxi]] [[team2ndplace#gcxi]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Glorious Hounds | **UBBL Challenge IV** |   5 |    0 |    1 |      6 | 83.33 |   22 |    7 |    6 |    -10 |    4 |
| Glorious Hounds | Green Cup XI         |   12 |    4 |    3 |     19 | 73.6842 |   82 |   52 |   17 |    -14 |    0 |
| Glorious Hounds | Green Cup VIII       |   11 |    1 |    5 |     17 | 67.65 |   51 |   27 |   11 |    -20 |    2 |
| Glorious Hounds | Green Cup VII        |   10 |    1 |    6 |     17 | 61.76 |   60 |   37 |   16 |    -18 |    3 |
| Glorious Hounds | Green Cup V Memorial |    5 |    3 |    4 |     12 | 54.17 |   23 |   16 |   14 |     -6 |   -2 |
| Glorious Hounds | Green Cup IV         |    7 |    0 |    6 |     13 | 53.85 |   39 |   35 |   14 |     -9 |    0 |
| Glorious Hounds | Green Cup IX         |    8 |    3 |    7 |     18 | 52.78 |   58 |   49 |   14 |    -22 |   -1 |
| Glorious Hounds | UBBL Challenge       |    2 |    0 |    2 |      4 |      50.00 |   11 |   12 |    2 |     -8 |    1 |
| Glorious Hounds | Green Cup X          |    4 |    4 |    8 |     16 |    37.50 |   40 |   46 |   13 |    -25 |   -3 |
| Glorious Hounds | Green Cup VI         |    3 |    4 |    8 |     15 | 33.33 |   30 |   33 |   15 |    -13 |    1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Glorious Hounds" ORDER BY mr.win_pct DESC limit 16;
```
## History

The Hounds fought and fought in the old-era to gain admission to the Green Cup circuit. When they finally did, they came in second place with a match that just didn't measure up to even average play. And then it was the last season to be played before the interruption.

The Hounds couldn't make their new lineup of rookies play worth a damn in Green Cup VI, but since then they've been generally much better. They were projected to be Heaps champions again in GCX, but ended up last place in the division. No one could really tell why things went so poorly, but they did.

Winning the fourth UBBL Challenge after that execrable season was the second best thing they could do for their team psyche.

#### Projection GCXI

W-D-L 8-0-7

This season there's no way they roll over and come in last place again. They have the taste of winning and will be able to take advantage of a division that has no clear favourite apart from them. If they can do better than conference champions remains to be seen.

#### summary last season

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Glorious Hounds |     1 |       9 |    2 |   28 |    1 |        8 |      1 |          0 |    0 |     30 |     1 |    1 |   12 |           2 |           2 |
| Glorious Hounds |     2 |      12 |    3 |   61 |    6 |       22 |      6 |          0 |    0 |     39 |     1 |    1 |   20 |           1 |           3 |
| Glorious Hounds |     3 |      10 |    1 |   25 |    4 |       16 |      4 |          0 |    0 |     24 |     0 |    1 |   12 |           1 |           1 |
| Glorious Hounds |     4 |      25 |    7 |  112 |    8 |       35 |      8 |          0 |    0 |     19 |     0 |    1 |   34 |           4 |           7 |
| Glorious Hounds |     5 |      13 |    4 |   74 |    4 |       11 |      4 |          1 |    0 |     33 |     3 |    1 |   23 |           5 |           4 |
| Glorious Hounds |     6 |      15 |    8 |  123 |    8 |       13 |      8 |          0 |    2 |     39 |     0 |    1 |   41 |           8 |           4 |
| Glorious Hounds |     7 |      20 |    5 |   67 |    8 |        8 |      8 |          0 |    1 |     23 |     1 |    1 |   30 |           5 |           1 |
| Glorious Hounds |     8 |      18 |    6 |  110 |    8 |       21 |      8 |          0 |    3 |     41 |     5 |    1 |   37 |           6 |           1 |
| Glorious Hounds |     9 |       1 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |     27 |     1 |    1 |    5 |           3 |           0 |
| Glorious Hounds |    10 |       8 |    5 |   55 |    3 |       16 |      3 |          0 |    2 |     31 |     3 |    1 |   27 |           5 |           2 |
| Glorious Hounds |    11 |      22 |    8 |  137 |    8 |       21 |      8 |          0 |    1 |     23 |     0 |    1 |   39 |           8 |           8 |
| Glorious Hounds |    12 |      13 |    6 |   89 |    6 |       25 |      6 |          1 |    0 |     23 |     1 |    1 |   31 |           6 |           2 |
| Glorious Hounds |    13 |      23 |    8 |  107 |    8 |       17 |      8 |          1 |    1 |     26 |     2 |    1 |   41 |           7 |           8 |
| Glorious Hounds |    14 |       2 |    1 |   18 |    0 |        0 |      0 |          0 |    0 |      4 |     2 |    1 |    8 |           1 |           1 |
| Glorious Hounds |    15 |      16 |    8 |  110 |   10 |       25 |     10 |          0 |    3 |     32 |     3 |    1 |   45 |           2 |           8 |
| Glorious Hounds |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    2 |   10 |           1 |           0 |
| Glorious Hounds |    QF |       5 |    3 |   26 |    2 |        9 |      2 |          0 |    1 |     41 |     2 |    1 |   18 |           3 |           2 |
| Glorious Hounds |    SF |      13 |    4 |   70 |    7 |       30 |      7 |          0 |    3 |     33 |     3 |    1 |   30 |           3 |           4 |
| Glorious Hounds |    GC |      17 |    2 |   66 |    4 |       12 |      4 |          2 |    0 |     26 |     1 |    1 |   19 |           3 |           2 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Glorious Hounds" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Oxana    | 18 |      64 |    0 |  234 |   54 |   195 |    3 |    1 |    0 |   19 |    0 |    1 |           3 |      2 |    3 |    0 |       1 |      0 |   61 |
|    2 | Cecile   | 18 |      35 |    0 |   72 |   22 |    84 |    4 |    1 |    0 |   13 |    1 |    0 |           3 |      0 |    2 |    1 |       1 |      0 |   24 |
|    3 | Udo      | 19 |      13 |    4 |   47 |    3 |    -5 |    6 |    0 |    1 |   38 |    3 |    0 |           1 |      3 |    6 |    6 |       0 |      0 |   17 |
|    4 | Ziba.1   | 19 |      76 |   63 |  739 |    2 |     0 |   58 |    2 |    0 |    9 |    1 |    3 |           0 |      5 |    5 |    1 |       0 |      0 |  210 |
|    5 | Veles    | 18 |       0 |    0 |   -1 |    0 |     0 |    0 |    0 |    1 |   68 |    2 |    1 |           0 |      0 |    3 |    0 |       1 |      0 |    7 |
|    6 | Florinda | 18 |       4 |    2 |   15 |    0 |     0 |    3 |    1 |    8 |  167 |    6 |    0 |           0 |      2 |    3 |    1 |       1 |      0 |   24 |
|    7 | Lestari  | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   18 |    1 |    2 |           0 |      0 |    1 |    1 |       0 |      0 |   10 |
|    8 | Tsutsiko | 17 |       4 |    0 |    3 |    0 |     0 |    1 |    0 |    0 |   28 |    0 |    1 |           0 |      1 |    2 |    2 |       2 |      0 |    5 |
|    9 | Aiza     | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   16 |    0 |    1 |           0 |      0 |    2 |    0 |       0 |      0 |    5 |
|   11 | August   | 19 |       5 |    0 |   17 |    2 |    15 |    1 |    0 |    2 |   38 |    4 |    1 |           0 |      2 |    3 |    1 |       0 |      0 |   11 |
|   14 | Irenaeus |  8 |       7 |    2 |   20 |    0 |     0 |    5 |    0 |    0 |   18 |    3 |    1 |           1 |      1 |    1 |    1 |       1 |      0 |   11 |
|   15 | Ravil    | 13 |      17 |    6 |   71 |    4 |     4 |    9 |    0 |    0 |   20 |    4 |    6 |           0 |      3 |    4 |    2 |       0 |      0 |   52 |
|   17 | Branson  | 13 |      17 |    4 |   61 |    8 |    -4 |    5 |    0 |    4 |   39 |    4 |    1 |           0 |      4 |    3 |    1 |       1 |      0 |   33 |
|   28 | Zeenat.  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    2 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      0 |    2 |
|   87 | Owain.   |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   16 |    0 |    2 |           0 |      0 |    2 |    1 |       1 |      1 |   10 |
|   89 | Valeriy  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |
|   92 | Wawatam. |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    4 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      1 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Glorious Hounds" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Ziba**    | Catcher  |   20 |    7 |   10 |   37 |   87 |    3 |    2 |    1 |    0 |    0 |    7 |  305 |
| Costache | Catcher  |   23 |    8 |   20 |   51 |   76 |    3 |    2 |    2 |    2 |    0 |    3 |  258 |
| Yosif    | Thrower  |   32 |    9 |   29 |   70 |    1 |  162 |    2 |    0 |    0 |    0 |    2 |  179 |
| Oiva     | Catcher  |   27 |    8 |   21 |   56 |   30 |   29 |    8 |    3 |    0 |    0 |    3 |  156 |
| **Cecile**    | Thrower  |   41 |   12 |   24 |   77 |    2 |   83 |    4 |    1 |    0 |    0 |    7 |  134 |
| **Oxana**     | Thrower  |   24 |    7 |   14 |   45 |    1 |  101 |    1 |    0 |    0 |    0 |    4 |  126 |
| *Ozymandias* | Thrower | ?? | ?? | ?? | 40 | 1 | 77 | 0 | 0 | 0 | 0 | 8 | 123 |
| **Udo**       | Catcher  |   30 |   11 |   20 |   61 |   20 |   28 |    0 |    3 |    1 |    0 |    4 |  116 |
| **Florinda**  | Blitzer  |   39 |   12 |   19 |   70 |    4 |    4 |    3 |   12 |    3 |    2 |    9 |  101 |
| **Branson**   | Catcher  |   19 |    6 |   14 |   39 |   17 |   15 |    1 |    5 |    1 |    0 |    3 |   95 |
| *Forbearance* | Catcher | ?? | ?? | ?? | 34 | 23 | 3 | 0 | 1 | 0 | 0 | 2 | 84 |
| *Wonder* | Catcher | ?? | ?? | ?? | 22 | 19 | 2 | 1 | 2 | 1 | 0 | 3 | 82 |
| *Honour* | Catcher | ?? | ?? | ?? | 30 | 21 | 1 | 2 | 0 | 2 | 0 | 2 | 82 | 
| Daividh  | Catcher  |   10 |    5 |   11 |   26 |   17 |    2 |    1 |    1 |    1 |    0 |    4 |   79 |
| Berry    | Blitzer  |   25 |    6 |   16 |   47 |   14 |    2 |    0 |    4 |    1 |    2 |    4 |   78 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Glorious Hounds" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


[[costache]] had an early injury that hampered her effectiveness, but a better all-round receiver we see only rarely.

[[yosif]] was the best pure passer the UBBL has seen, and that includes Ozymandias, who has actually (amazingly) seemed to be okay with the eclipsing of his talent.

[[oiva]] was an excellent ball-hawk, but not quite the Green Cup best.

[[ziba]] wasn't high up in the pantheon of Glorious Greats before GCXI, but she's the fastest catcher the team has ever had, and with proper support, could make a run at some of the individual prizes currently held on lockdown by [[aeson]].

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    4 | Ziba      | Catcher  |       3 |      2 | 260000 |     0 |
|   15 | Ravil     | Catcher  |       1 |      1 | 190000 |     0 |
|   35 | Costache. | Catcher  |       5 |      4 | 290000 | 70000 |
|   81 | Yosif.    | Thrower  |       7 |      2 | 300000 | 60000 |
|   84 | Daividh.  | Catcher  |       2 |      1 | 230000 |     0 |
|   85 | Baraz.    | Catcher  |       4 |      1 | 170000 |     0 |
|   86 | Phemie.   | Catcher  |       1 |      1 |  90000 |     0 |
|   86 | Mandawuy. | Catcher  |       3 |      1 | 170000 |     0 |
|   94 | Cedric.   | Lineman  |       3 |      1 | 110000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Glorious Hounds" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

Ozymandias runs the team, and like many of the other former players, he runs it with an eye towards a love of the game first. He wants his players to play beautifully and they practice with that in mind. 

### Fans

The team has been on a recent slide with its fanbase, which is kind of weird since they actually pulled off a gain in lovable losers type in GCVI where they only won 3 matches.

Hounds fans generally despise teams that aren't trying to play aesthetically beautiful BludBol, so the [[ravenouseagles]] and [[carcosantatters]] are the most common targets of their ire.

### Famous Games

The 8-0 drubbing of the [Gargantuan Brutes](gargantuanbrutes) in GCVII was basically a perfectly played match. The only way to really improve upon it would be to have a [[yakup]]-level scorer on the pitch, which the Hounds never had the luxury of fielding.

In UBBL Challenge IV they had that speedster against the [Gentlefolk](gentlefolk) but managed only(!) another 8-0 win . These textbook displays are amazing things to study, as all true fans of BludBol should do.
