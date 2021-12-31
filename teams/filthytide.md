# Filthy Tide

The Filthy Tide are often called the best team to never win the Green Cup. They're an Original 8 team that has had two hall-of-fame scorers in the UBBL but has never been able to convert the big win to get those stars a (pro-level) championship. They have been in rebuild mode, but are banking on their new star [[venus]] to be the difference-maker.

## Playbook

The Filthy Tide uses the Scrying Avian playbook which emphasizes speed above all else, especially the health of your own players. The position slots only include 2 blitzers, but have 2 throwers, 4 catchers (sometimes more accurately labelled runners), and a heavy available. With proper training it's possible to have a super-fast scorer onside, which makes the lack of defensive ability easier to overcome.


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
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Filthy Tide" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Lineup

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Geir        | Thrower       |   Emerging Star |       3 |
| Aleksy      | Thrower       |   Superstar |       2 |
| Venus       | Catcher |  Superstar |       2 |
| Septimus    | Catcher |   Superstar |       9 |
| Slawomir    | Blitzer       |   Emerging Star |       3 |
| Briseida    | Blitzer       |   Veteran |       5 |
| Angilberct  | Line       |    Experienced |       3 |
| Emilee      | Line       |    Experienced |       3 |
| Hadassah    | Line       |   Veteran |       4 |
| Kgosi       | Line       |    Rookie |       3 |
| Ellanher    | Line       |    Experienced |       2 |
| Milica      | Catcher |   Emerging Star |       3 |
| Othniel     | Catcher |   Veteran |       2 |
| Tomer       | Catcher |   Star |       3 |
| Uzma        | Heavy      |   Star |       4 |


### Bench

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Enrique     | Line       |    Rookie |       1 |
| Karthikeyan | Line       |    Rookie |       2 |
| Giselle     | Line       |    Rookie |       2 |
| Dora        | Line       |    Rookie |       1 |
| Daibhi      | Line       |    Rookie |       2 |
| Teofil      | Line       |    Rookie |       1 |
| Robin       | Line       |    Rookie |       1 |
| Hanne       | Line       |    Rookie |       1 |
| Idunn       | Line       |    Rookie |       1 |
| Elmer       | Line       |    Rookie |       2 |

## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Filthy Tide | Pro      |   70 |   14 |   65 |  149 | 46.785 |  449 |  407 |  183 |    -165 |    2 |
| Filthy Tide | Open     |    8 |    0 |    3 |   11 | 50.794 |   39 |   22 |   23 |       3 |    3 |
| Filthy Tide | Street   |    4 |    1 |    6 |   11 | 40.909 |   21 |   20 |   18 |      -3 |   -1 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Filthy Tide" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Filthy Tide |   82 |   15 |   74 |  171 | 47.195 |  509 |  449 |  224 |    -165 |    4 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Filthy Tide" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup VI - Doom Fist [[teamcasualties#gcvi]]
* Green Cup VI - Tough Brake of Alsoran [[team3rdplace#gcvi]]
* UBBL Challenge - UBBL Pennant [[team1stplace#ubbl challenge]]
* UBBL Challenge - Gorefield Honour [[teamcasualties#ubbl challenge]]
* Green Cup XI - Pits Division Champions [[teamdivision#gcxi]]
* Green Cup XI - Burger Conference Champions [[teamconference#gcxi]]
<<<<<<< HEAD
* Green Cup XI - Green Cup Champions [[team1stplace#gcxi]]
=======
* Green Cup XI Champions [[team1stplace#gcxi]]
>>>>>>> 5ba9819c70286f12bf025ebf0d84f75ded037197

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Filthy Tide | **UBBL Challenge**   |    6 |    0 |    1 |      7 | 85.71 |   30 |   15 |   16 |      7 |    2 |
| Filthy Tide | **Green Cup XI**     |   14 |    2 |    3 |     19 | 78.9474 |   83 |   60 |   11 |    -24 |    2 |
| Filthy Tide | UBBL Challenge IV    |    2 |    0 |    1 |      3 | 66.67 |    9 |    5 |    6 |      1 |    1 |
| Filthy Tide | Green Cup VII        |    9 |    3 |    5 |     17 | 61.76 |   56 |   37 |   21 |     -3 |    0 |
| Filthy Tide | Green Cup I          |    6 |    0 |    5 |     11 | 54.55 |   31 |   26 |   13 |     -9 |    0 |
| Filthy Tide | Green Cup II         |    5 |    2 |    4 |     11 | 54.55 |   36 |   32 |   11 |    -17 |    0 |
| Filthy Tide | Green Cup VI         |    7 |    2 |    7 |     16 |      50.00 |   46 |   35 |   33 |      3 |    2 |
| Filthy Tide | Green Cup III        |    6 |    0 |    6 |     12 |      50.00 |   30 |   29 |   12 |    -27 |    0 |
| Filthy Tide | Green Cup VIII       |    7 |    2 |    8 |     17 | 47.06 |   39 |   40 |   42 |     -4 |   -4 |
| Filthy Tide | Green Cup X          |    7 |    0 |    9 |     16 |   43.75 |   50 |   51 |   19 |    -25 |    3 |
| Filthy Tide | Green Cup IV         |    5 |    0 |    7 |     12 | 41.67 |   32 |   38 |   11 |    -32 |    1 |
| Filthy Tide | Green Cup V Memorial |    4 |    1 |    6 |     11 | 40.91 |   21 |   20 |   15 |     -3 |   -1 |
| Filthy Tide | Green Cup IX         |    4 |    3 |   10 |     17 | 32.35 |   45 |   57 |   16 |    -23 |   -1 |
| Filthy Tide | UBBL Challenge III   |    0 |    0 |    1 |      1 |       0.00 |    0 |    2 |    0 |     -5 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Filthy Tide" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Tide is an integral part of the UBBL and has been from the beginning. They never really broke through in the old-era though they've had big stars. They came into the modern era trying to forge a new identity, and claimed their first team prizes in GCVI.

The Tide had an excellent GCVII season going when they ran into the bizarrely successful [Eagles](ravenouseagles) team who took Yakup out early and deflated the team.

The UBBL pennant is no Green Cup, but the Filthy Tide were proud to be its first winners (and they played an amazing semi-final against the [Kaiju Dynamo](kaijudynamo) to do it). Perhaps merely by playing the most matches, the Filthy Tide inflicted the most casualties in this tournament, 16 (11-5-0).

Their 4-win GCIX campaign was devastating to a team of such history. To follow up they put their efforts in the GCV Memorial tournament to develop a replacement for Yakup. Rather than learning a more conservative style of play to match up with their GCIX team's abilities they decided to try pinning their entire GCX season's fortunes on [[venus]], a young player who scored a TD in street-level play and looked fast doing it.

This approach wasn't punished too harshly in GCX, until they hit the playoffs and were steamrolled by the [Gore Farmers](gorefarmers).

#### GCXI Projection

W-D-L 7-1-7 

The Tide should be able to make the playoffs since they share the Stacks with a soft [TC Sump Runner team](sumprunners). Of all the teams in this Green Cup they would benefit most from getting a first-round playoff bye to avoid a round of being smashed to bits, but that means getting more wins in 15 matches than the powerhouse, defending champion [Wyrms](oldwyrms). Our projection has another round of 16 exit in store for the Tide.

#### summary last season

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Filthy Tide |     1 |      16 |    6 |  106 |    7 |       18 |      7 |          0 |    0 |     23 |     0 |    1 |   30 |           6 |           5 |
| Filthy Tide |     2 |       6 |    2 |   49 |    1 |        1 |      1 |          0 |    1 |     28 |     1 |    1 |   14 |           2 |           2 |
| Filthy Tide |     3 |      15 |    3 |   72 |    3 |       11 |      3 |          0 |    0 |     22 |     1 |    1 |   17 |           5 |           3 |
| Filthy Tide |     4 |      11 |    5 |   87 |    3 |       15 |      3 |          2 |    0 |     39 |     2 |    1 |   27 |           3 |           5 |
| Filthy Tide |     5 |      12 |    4 |   65 |    3 |       15 |      3 |          0 |    0 |     17 |     1 |    1 |   20 |           0 |           4 |
| Filthy Tide |     6 |      13 |    4 |   68 |    3 |        8 |      3 |          0 |    0 |     21 |     1 |    1 |   20 |           4 |           3 |
| Filthy Tide |     7 |      24 |    5 |   84 |    5 |       21 |      5 |          0 |    1 |     36 |     2 |    1 |   27 |           5 |           4 |
| Filthy Tide |     8 |      15 |    6 |  104 |    5 |       11 |      5 |          1 |    2 |     26 |     1 |    1 |   34 |           6 |           4 |
| Filthy Tide |     9 |      12 |    4 |   53 |    2 |        6 |      2 |          0 |    0 |     16 |     1 |    1 |   19 |           1 |           4 |
| Filthy Tide |    10 |      13 |    4 |   83 |    3 |        6 |      3 |          2 |    1 |     31 |     1 |    1 |   26 |           4 |           7 |
| Filthy Tide |    11 |      19 |    8 |  140 |    7 |       26 |      7 |          0 |    0 |     33 |     1 |    1 |   36 |           8 |           8 |
| Filthy Tide |    12 |      28 |    9 |  151 |    6 |       11 |      6 |          0 |    3 |     28 |     2 |    1 |   44 |           9 |           7 |
| Filthy Tide |    13 |      20 |    7 |  106 |    6 |       15 |      6 |          0 |    3 |     25 |     2 |    1 |   38 |           0 |           7 |
| Filthy Tide |    14 |       6 |    1 |   20 |    1 |       -3 |      1 |          0 |    0 |     12 |     0 |    1 |    9 |           2 |           1 |
| Filthy Tide |    15 |       6 |    3 |   46 |    2 |        2 |      2 |          0 |    0 |     10 |     0 |    1 |   16 |           2 |           3 |
| Filthy Tide |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    2 |   10 |           1 |           0 |
| Filthy Tide |    QF |      18 |    3 |   53 |    5 |       10 |      5 |          0 |    0 |     35 |     2 |    1 |   19 |           3 |           2 |
| Filthy Tide |    SF |      12 |    5 |   76 |    4 |        8 |      4 |          0 |    0 |     35 |     1 |    1 |   24 |           5 |           3 |
| Filthy Tide |    GC |      17 |    3 |   67 |    1 |        1 |      1 |          0 |    0 |     51 |     3 |    1 |   15 |           3 |           2 |

```
SELECT pl.f_tname AS Team, mt.round, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Filthy Tide" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Geir.1      | 17 |      36 |    1 |  126 |   14 |    38 |    0 |    0 |    1 |   29 |    2 |    1 |           1 |      1 |    2 |    1 |       2 |      0 |   24 |
|    2 | Aleksy.3    | 19 |      69 |    0 |  183 |   39 |   116 |    0 |    0 |    0 |   20 |    1 |    1 |           1 |      1 |   11 |    0 |       0 |      0 |   44 |
|    3 | Venus.3     | 18 |      79 |   69 |  770 |    1 |     3 |   47 |    0 |    0 |    1 |    1 |    1 |           0 |      2 |    3 |    2 |       1 |      0 |  213 |
|    4 | Milica      | 16 |      24 |    2 |  136 |    6 |     2 |   10 |    0 |    0 |   15 |    1 |    2 |           3 |      4 |    5 |    1 |       1 |      0 |   22 |
|    5 | Slawomir.3  | 18 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   71 |    2 |    2 |           0 |      0 |    5 |    1 |       1 |      0 |   12 |
|    6 | Briseida.1  | 17 |       5 |    2 |   27 |    0 |     0 |    0 |    1 |    3 |  113 |    3 |    4 |           0 |      0 |    2 |    1 |       3 |      0 |   34 |
|    8 | Karthikeyan |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    9 |    0 |    0 |           0 |      0 |    2 |    0 |       2 |      0 |    0 |
|    9 | Ellanher    | 14 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   30 |    2 |    0 |           0 |      0 |    5 |    4 |       0 |      0 |    0 |
|   10 | Angilberct  | 12 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   21 |    0 |    0 |           0 |      0 |    6 |    0 |       3 |      0 |    2 |
|   14 | Tomer.4     | 17 |      17 |    4 |   66 |    3 |    14 |    2 |    1 |    2 |   42 |    5 |    3 |           0 |      0 |    7 |    1 |       0 |      0 |   36 |
|   15 | Othniel     | 18 |      22 |    3 |   67 |    2 |     7 |    5 |    2 |    0 |   27 |    3 |    3 |           1 |      1 |    7 |    3 |       1 |      0 |   30 |
|   16 | Drita       | 10 |       1 |    0 |    0 |    0 |     0 |    0 |    1 |    2 |   61 |    2 |    2 |           0 |      1 |    2 |    0 |       1 |      0 |   16 |
|   17 | Septimus.1  |  6 |      10 |    1 |   55 |    2 |     2 |    3 |    0 |    0 |    1 |    0 |    0 |           0 |      1 |    1 |    0 |       0 |      0 |    5 |
|   25 | Giselle.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|   26 | Dora.       |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   30 | Daibhi.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|   87 | Enrique     |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    0 |    0 |           0 |      0 |    4 |    0 |       1 |      1 |    0 |
|   87 | Wangi.      |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|   87 | Didac.      |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   88 | Emilee.     |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   16 |    0 |    1 |           0 |      0 |    2 |    0 |       1 |      1 |    7 |
|   88 | Sharif.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   89 | Hadassah.   |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   14 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      1 |    0 |
|   89 | Christina.  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   96 | Uzma.       |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      1 |    0 |
|   99 | Idunn       |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Filthy Tide" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Venus**      | Catcher |   20 |    2 |   12 |   34 |  106 |    1 |    0 |    0 |    0 |    0 |    5 |  344 |
| Yakup       | Catcher |   27 |    6 |   20 |   53 |   73 |    1 |    0 |    0 |    1 |    0 |    4 |  242 |
| Somfuhr     | Heavy      |   31 |    9 |   29 |   69 |    0 |    0 |    0 |   42 |   13 |    6 |    6 |  152 |
| Silas       | Thrower       |   35 |    9 |   31 |   75 |    2 |  125 |    2 |    1 |    0 |    0 |    2 |  147 |
| *Despereaux* | Catcher | ?? | ?? | ?? | 43 | 31 | 10 | 1 | 1 | 0 | 0 | 5 | 132 |
| Mayu        | Catcher |   28 |    6 |   21 |   55 |   35 |    3 |    2 |    1 |    0 |    0 |    3 |  129 |
| Aleksy     | Thrower       |   24 |    5 |   21 |   50 |    2 |   90 |    0 |    1 |    1 |    0 |    5 |  125 |
| *Sardines*   | Catcher | ?? | ?? | ?? | 27 | 39 | 2 | 0 | 0 | 0 | 0 | 1 | 124 |
| *Nadaz*      | Thrower | ?? | ?? | ?? | 55 | 1 | 86 | 1 | 1 | 0 | 0 | 3 | 119 |
| Tomer      | Catcher |   27 |    7 |   21 |   55 |   17 |    6 |    2 |    3 |    0 |    0 |    7 |  102 |
| Madhavi     | Blitzer       |   31 |    9 |   29 |   69 |    4 |    2 |    4 |    9 |    5 |    3 |    8 |   96 |
| *Asmodeus*   | Catcher | ?? | ?? | ?? | 55 | 19 | 7 | 3 | 1 | 0 | 0 | 3 | 87 |
| **Septimus**   | Catcher |   37 |    7 |   42 |   86 |   18 |    9 |    2 |    1 |    0 |    1 |    2 |   81 |
| Nicodemus II | Catcher |    8 |    2 |    9 |   19 |   21 |    2 |    0 |    0 |    0 |    0 |    3 |   80 |
| *Nicodemus*  | Catcher | ?? | ?? | ?? | 55 | 14 | 9 | 2 | 2 | 0 | 0 | 4 | 79 | 
| Fikri       | Thrower       |   21 |    5 |   13 |   39 |    4 |   47 |    0 |    2 |    0 |    0 |    2 |   73 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Filthy Tide" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```



As of the start of GCXI, [[Somfuhr]] is in the Hall of Fame for inflicting the most casualties of any player in the Pro Division. For a time [[yakup]] seemed untouchable in his scoring abilities. That the team couldn't convert this dynamic duo into more than a third place Green Cup finish is heartbreaking. The new hope is [[venus]], who after one pro season has more SPP than [[sardines]] did.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    3 | Venus    | Catcher |       4 |      4 | 270000 | 40000 |
|   79 | Somfuhr.  | Heavy      |       6 |      2 | 330000 | 70000 |
|   83 | Sardines. | Catcher |       1 |      1 |  80000 |     0 |
|   83 | Yakup.    | Catcher |       5 |      6 | 220000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Filthy Tide" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

Asmodeus, an ex-player, runs the team in a pretty hands-off manner. They're a sentimental fan of counting stats and wouldn't take out players past their prime when they needed to be.

### Fans

The Filthy Tide have long been in the shadow of the [Old Wyrms](oldwyrms). They have had great individual players but no team success. Tide fans see Wyrms supporters as arrogant blowhards, but they hate Wyrms management even more for their unsentimental business first approach to winning. Tide fans also see the [Badger Claws](badgerclaws) as an up and coming rival, and would love to see their star [[aeson]] retire, preferably without a Green Cup ring. Generally the GCX season was a good one for Tide fans after a rough start.

### Famous Games

The UBBL Challenge semifinal vs the [Kaiju Dynamo](kaijudynamo) with all the scoring. GCX Week 9 [[seasons/gcx/week09]] with even more scoring which didn't lead to a (sub-Pro) championship.
