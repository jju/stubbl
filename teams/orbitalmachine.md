# Orbital Machine

A dominant bashing Modern-Era team, the Orbital Machine embodies a team-oriented approach. They inflict a lot of casualties and have the best winning streak in the UBBL (12 wins spanning two seasons).

## Playbook

The Orbital Machine uses the Chariot playbook. This involves four massive players on the line with everyone else more lightly armoured but able to blitz like no one's business. Passing and ball-handling tend to be a secondary consideration and get focused into whichever players show an aptitude while the rest of the team assembles the cage to roll down the field.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Jarm      | Blitzer      |   33 |       4 |   17 |         1 | 130000 |     0 |
|    2 | Rodie     | Blitzer      |    7 |       1 |    2 |         0 |  80000 |     0 |
|    3 | Ruslan    | Blitzer      |   87 |       4 |   43 |         3 | 170000 |     0 |
|    4 | Akhenaton | Blitzer      |    6 |       1 |    9 |         1 |  90000 |     0 |
|    5 | Stino     | Blitzer      |   23 |       7 |   34 |         2 | 100000 |     0 |
|    6 | Spinal    | Blitzer      |   53 |       6 |   71 |         5 | 200000 | 50000 |
|    7 | Odalric   | Blocker |   80 |       4 |   50 |         3 | 200000 |     0 |
|    8 | Collar    | Blocker |   45 |       5 |   52 |         3 | 160000 |     0 |
|    9 | Jothi     | Blocker |   56 |       3 |   36 |         2 | 210000 |     0 |
|   10 | Anvil     | Blocker |   55 |       5 |   44 |         3 | 180000 |     0 |
|   11 | Kris      | Blitzer      |    1 |       1 |    4 |         0 |  60000 |     0 |
|   12 | Katiuscia | Blitzer      |    0 |       1 |    4 |         0 |  60000 |     0 |
|   13 | Ekkebert  | Blitzer      |    0 |       1 |    4 |         0 |  60000 |     0 |
|   16 | Uli       | Heavy      |  114 |       4 |   48 |         3 | 260000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Orbital Machine" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Orbital Machine | Pro      |   40 |   17 |   34 |   91 | 53.817 |  138 |  142 |  228 |     136 |    1 |
| Orbital Machine | Open     |    1 |    0 |    4 |    5 | 16.667 |    6 |    9 |    8 |       0 |   -3 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Orbital Machine" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Orbital Machine |   41 |   17 |   38 |   96 | 44.530 |  144 |  151 |  236 |     136 |   -2 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Orbital Machine" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```


### Prizes

* Green Cup Classic 06 - Iron Fist [[teamcasualties#gcc06]]
* Green Cup Classic 06 - Green Cup Champions [[team1stplace#gcc06]]
* Green Cup Classic 06 - Pits Champions [[teamdivision#gcc06]]
* Green Cup VII - Iron Fist [[teamcasualties#gcvii]]
* Green Cup VIII - Iron Fist  [[teamcasualties#gcviii]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Orbital Machine | Green Cup VII        |   11 |    3 |    3 |     17 | 73.53 |   29 |   17 |   42 |     33 |   -1 |
| Orbital Machine | **Green Cup Classic 06** |    6 |    1 |    3 |     10 |      65.00 |   18 |   15 |   16 |      8 |    5 |
| Orbital Machine | Green Cup VIII       |    9 |    0 |    7 |     16 |   56.25 |   27 |   27 |   49 |     27 |    1 |
| Orbital Machine | Green Cup X          |    7 |    4 |    5 |     16 |   56.25 |   27 |   27 |   40 |     26 |   -1 |
| Orbital Machine | Green Cup IX         |    6 |    3 |    7 |     16 |  46.88 |   21 |   26 |   31 |     20 |   -1 |
| Orbital Machine | UBBL Challenge       |    1 |    0 |    2 |      3 | 33.33 |    5 |    6 |    4 |     -1 |   -1 |
| Orbital Machine | Green Cup XI         |    1 |    6 |    9 |     16 |      25 |   16 |   30 |   40 |     22 |   -2 |
| Orbital Machine | UBBL Challenge IV    |    0 |    0 |    2 |      2 |    0.00 |    1 |    3 |    6 |      1 |   -2 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Orbital Machine" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Machine are entirely a Modern era institution.

### Seasons

With a timely 6-win streak the Pits champions hoisted the sixth (disputed) Green Cup. The Machine were sneaky in their physical dominance but inflicted 16 Casualties (10-3-3) in their 10-match championship run.

They continued to win throughout GCVII but lost in the Division Finals to the [Eldritch Fatality](eldritchfatality).

The GCIX season was their first in which they did not lead the league in Casualties inflicted.

In GCXI the Machine did not make the playoffs (but as former Green Cup winners they did not face relegation).

#### Projection GCXI

W-D-L 8-1-6

The Machine is due for another deep playoff run and this season could be the one where they take advantage of a tough-to-call division. The more interesting race might be to see if they can wrestle the [Iron Fist](../prizes/teamcasualties) from the [Ravenous Eagles](ravenouseagles).

#### GCXI Recap

The Machine didn't have that deep playoff run they were expecting. They didn't score more than 2 TDs even once, and their best team effort in bashing was a 6 casualty outing against the Fatality [[gcxi-13-efom]]. [[Uli]] handily coasted to a Carmine Fist award (but may not have if the Eagles hadn't been spreading their damage around; see [[gcxi-cas-race]]). The biggest impact they are likely to have on the season as a whole is that Uli seriously injured [[Venus]] in week 15 [[gcxi-15-omft]], causing a necessary shift in the Tide's playoff strategy.

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Orbital Machine |     1 |       7 |    2 |   41 |    1 |        4 |      1 |          0 |    3 |     56 |     0 |    1 |   18 |  Home | D |
| Orbital Machine |     2 |      10 |    2 |   59 |    2 |        4 |      2 |          0 |    1 |     49 |     0 |    1 |   15 |  Away | L |
| Orbital Machine |     3 |       6 |    1 |   42 |    0 |        0 |      0 |          1 |    3 |     72 |     1 |    1 |   16 |  Away | D |
| Orbital Machine |     4 |      10 |    2 |   44 |    4 |        3 |      4 |          0 |    4 |     37 |     0 |    1 |   23 |  Away | W |
| Orbital Machine |     5 |       6 |    2 |   24 |    1 |        6 |      1 |          0 |    3 |     71 |     3 |    1 |   18 |  Away | D |
| Orbital Machine |     6 |       7 |    0 |   30 |    0 |        0 |      0 |          0 |    3 |     52 |     1 |    1 |   11 |  Home | L |
| Orbital Machine |     7 |       4 |    1 |   35 |    0 |        0 |      0 |          0 |    1 |     71 |     0 |    1 |   10 |  Home | L |
| Orbital Machine |     8 |       7 |    0 |   18 |    0 |        0 |      0 |          0 |    2 |     40 |     2 |    1 |    9 |  Away | L |
| Orbital Machine |     9 |      11 |    1 |   32 |    2 |        1 |      2 |          1 |    2 |     60 |     1 |    1 |   16 |  Away | L |
| Orbital Machine |    10 |       2 |    0 |   23 |    1 |        2 |      1 |          0 |    3 |     57 |     1 |    1 |   12 |  Home | L |
| Orbital Machine |    11 |      11 |    1 |   43 |    0 |        0 |      0 |          0 |    1 |     49 |     3 |    1 |   10 |  Home | D |
| Orbital Machine |    12 |       7 |    1 |   35 |    2 |        4 |      2 |          0 |    1 |     47 |     0 |    1 |   12 |  Home | D |
| Orbital Machine |    13 |       9 |    0 |   20 |    1 |        4 |      2 |          0 |    6 |     47 |     2 |    1 |   18 |  Away | L |
| Orbital Machine |    14 |       7 |    1 |   36 |    0 |        0 |      0 |          0 |    1 |     36 |     0 |    1 |   10 |  Away | D |
| Orbital Machine |    15 |      10 |    2 |   50 |    3 |        8 |      3 |          0 |    5 |     43 |     0 |    1 |   24 |  Home | L |
| Orbital Machine |   251 |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    0 |    0 |   BYE | L |

```
SELECT pl.f_tname AS Team, mt.round, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Orbital Machine" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### GCXI

| #    | Player   | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|----------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Jarm      | 12 |      33 |    3 |  170 |    7 |    18 |    0 |    1 |    0 |   12 |    1 |    2 |           1 |      8 |    1 |    2 |       1 |      0 |   28 |
|    2 | Rodie     |  1 |       4 |    0 |   16 |    2 |     4 |    0 |    0 |    0 |    1 |    0 |    1 |           1 |      0 |    0 |    0 |       0 |      0 |    7 |
|    3 | Ruslan    | 10 |      21 |    3 |  128 |    5 |     9 |    4 |    0 |    0 |   37 |    0 |    2 |           0 |      5 |    0 |    0 |       0 |      0 |   24 |
|    4 | Akhenaton |  8 |      11 |    2 |   72 |    0 |     0 |    4 |    0 |    0 |   12 |    0 |    0 |           0 |      2 |    2 |    1 |       0 |      0 |    6 |
|    5 | Stino     |  8 |       3 |    0 |   15 |    0 |     0 |    0 |    0 |    0 |   19 |    1 |    0 |           0 |      1 |    0 |    1 |       2 |      0 |    0 |
|    6 | Spinal    | 13 |       5 |    1 |   11 |    0 |     0 |    0 |    0 |    4 |   33 |    4 |    1 |           1 |      2 |    2 |    2 |       2 |      0 |   16 |
|    7 | Odalric   | 15 |       3 |    0 |    7 |    0 |     0 |    0 |    1 |    7 |  103 |    1 |    1 |           0 |      0 |    2 |    1 |       0 |      0 |   21 |
|    9 | Jothi     |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   28 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|    9 | Collar    |  6 |       1 |    1 |    1 |    0 |     0 |    1 |    0 |    0 |   43 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    3 |
|   10 | Anvil     | 11 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   71 |    0 |    4 |           0 |      1 |    1 |    1 |       0 |      0 |   22 |
|   11 | Kris      |  4 |       3 |    0 |    4 |    1 |     1 |    0 |    0 |    0 |    9 |    0 |    0 |           0 |      1 |    1 |    0 |       0 |      0 |    1 |
|   16 | [[Uli]]   | 15 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |   22 |  174 |    2 |    0 |           0 |      0 |    1 |    1 |       0 |      0 |   **44** |
|   22 | Katiuscia |  4 |       2 |    0 |    5 |    0 |     0 |    0 |    0 |    0 |    7 |    0 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    0 |
|   24 | Ekkebert  |  4 |       1 |    0 |    6 |    0 |     0 |    1 |    0 |    0 |   11 |    0 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    0 |
|   82 | Leppard.  | 10 |      14 |    3 |   40 |    0 |     0 |    2 |    0 |    0 |   34 |    2 |    0 |           0 |      2 |    3 |    2 |       0 |      1 |    9 |
|   84 | Kendrick. |  9 |       3 |    0 |   14 |    0 |     0 |    1 |    0 |    0 |   22 |    1 |    2 |           0 |      2 |    2 |    2 |       2 |      1 |   10 |
|   85 | Gratien.  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      R |    0 |
|   86 | Judas.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      R |    0 |
|   87 | Bolt.     | 12 |       3 |    0 |    1 |    1 |     4 |    1 |    0 |    2 |   71 |    0 |    1 |           0 |      0 |    1 |    0 |       2 |      R |   10 |
|   88 | Mate      | 10 |       1 |    1 |    5 |    0 |     0 |    0 |    0 |    2 |   64 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    7 |
|   91 | Corinne.  |  8 |       6 |    2 |   37 |    1 |     0 |    4 |    0 |    1 |   31 |    1 |    1 |           0 |      0 |    2 |    0 |       0 |      1 |   14 |
|   95 | Praveena. |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    3 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |


```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Orbital Machine" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Heep   | Orbital Machine | Blitzer      |   26 |    4 |   12 |   42 |   28 |    5 |    4 |    6 |    1 |    0 |    2 |  121 |
| **Leppard** | Orbital Machine | Blitzer      |   38 |   11 |   25 |   74 |   14 |   26 |    2 |    3 |    4 |    2 |    6 |  120 |
| Lars   | Orbital Machine | Heavy      |   18 |    4 |    7 |   29 |    1 |    0 |    2 |   11 |    6 |    1 |    6 |   73 |
| **Uli**     | Orbital Machine | Heavy      |   13 |    6 |   11 |   30 |    0 |    0 |    0 |   17 |    5 |    1 |    4 |   66 |
| **Ruslan**  | Orbital Machine | Blitzer      |   13 |    6 |   12 |   31 |    9 |    5 |    1 |    6 |    1 |    0 |    3 |   63 |
| Ioana  | Orbital Machine | Heavy      |    9 |    1 |    9 |   19 |    2 |    0 |    2 |    8 |    2 |    2 |    5 |   59 |
| **Odalric** | Orbital Machine | Blocker |   14 |    7 |   14 |   35 |    3 |    0 |    0 |    8 |    1 |    1 |    6 |   59 |
| **Jothi**   | Orbital Machine | Blocker |   13 |    6 |   12 |   31 |    3 |    2 |    2 |    7 |    1 |    0 |    5 |   56 |
| Priest | Orbital Machine | Blitzer      |   25 |    4 |   10 |   39 |    8 |   24 |    1 |    0 |    0 |    0 |    1 |   55 |
| Ozzy   | Orbital Machine | Blitzer      |   20 |    4 |    9 |   33 |   11 |   11 |    1 |    3 |    1 |    0 |    0 |   54 |
| Def    | Orbital Machine | Blitzer      |   28 |    5 |   13 |   46 |    3 |    2 |    2 |    5 |    3 |    1 |    4 |   53 |

### roster by season


#### Cup Winners

| #    | Player   | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|----------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    5 | [[Stino]]    |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    6 | [[Spinal]]   | 10 |       4 |    0 |    2 |    1 |     1 |    0 |    0 |    1 |   22 |    2 |    0 |           0 |      1 |    1 |    1 |       0 |      0 |    3 |
|    8 | [[Bolt]]     | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   61 |    0 |    1 |           0 |      0 |    1 |    1 |       0 |      0 |    7 |
|    9 | [[Collar]] | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   58 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   10 | [[Anvil]]    | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   52 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   17 | [[Rivet]]   | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   67 |    1 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    6 |
|   25 | [[Def]]     | 10 |       1 |    0 |    0 |    1 |     4 |    0 |    0 |    2 |   40 |    2 |    2 |           0 |      0 |    0 |    1 |       0 |      0 |   15 |
|   26 | [[Lucio]]   |  2 |       2 |    0 |   17 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    1 |           0 |      1 |    0 |    0 |       0 |      0 |    5 |
|   81 | [[Priest]]  | 10 |      32 |    2 |  114 |    1 |     5 |    0 |    0 |    0 |    8 |    0 |    0 |           0 |      2 |    1 |    0 |       0 |      0 |    7 |
|   82 | [[Ozzy]]    | 10 |      14 |    5 |   75 |    1 |     4 |    0 |    1 |    2 |   28 |    1 |    0 |           0 |      5 |    0 |    0 |       0 |      0 |   22 |
|   82 | [[Leppard]] | 10 |       8 |    4 |   47 |    1 |     1 |    3 |    0 |    1 |   39 |    1 |    2 |           0 |      1 |    1 |    0 |       0 |      0 |   25 |
|   83 | [[Heep]]    | 10 |      16 |    7 |  100 |    2 |     5 |    4 |    0 |    1 |   21 |    0 |    2 |           0 |      6 |    0 |    1 |       0 |      0 |   **35** |
|   84 | Crue    |  8 |       3 |    0 |   10 |    0 |     0 |    0 |    0 |    0 |   18 |    0 |    0 |           0 |      2 |    0 |    0 |       0 |      1 |    0 |
|   86 | [[Judas]]   |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    2 |    1 |           0 |      0 |    0 |    0 |       1 |      0 |    5 |
|   96 | [[Lars]]    | 10 |       2 |    0 |    0 |    0 |     0 |    0 |    2 |    3 |   97 |    1 |    1 |           0 |      0 |    0 |    2 |       0 |      0 |   15 |

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup Classic 06" AND pl.f_tname = "Orbital Machine" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

##### No Ring

* Crue - dead

### Management

The Orbital Machine is owned by Orolk, an industrial concern with long local ties to Stacksburg and especially the mass elevator.

### Fans

Fans of the Machine don't get on especially well with the other main bashing teams in the Pros (the [Carcosan Tatters](carcosantatters) and [Gore Farmers](gorefarmers)). Adding to the frisson with the Farmers is the disputed nature of the "true winner" of the sixth Green Cup.

### Famous Games

The betrayal at Dungardin vs the [Cogs](irregularcogs) in GCVII Week 8 was notable for historical reasons (also, it was a 2 interception match for the Machine).

