# Irregular Cogs

The Cogs are the team of history that has never managed to re-live up to it. The Irregular Cogs won the inaugural Green Cup against their archrivals the [Old Wyrms](oldwyrms). The rest of their BludBol existence has been an attempt to hold that Green Cup again.

## Playbook

The Irregular Cogs use the Drop Eagle playbook. It's an adaptation of the Hermann playbook that again requires more skilled players to run it effectively. The strategy dispenses with the catcher position entirely, instead using four skilled blitzers and two runners to handle the ball, and two dedicated ball-hawks to attack the opposing ball-carriers. The Cogs have been known to score more of their TDs on defense because of their aggressive style of defending.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    3 | Frans     | Blitzer   |  133 |       4 |   42 |         3 | 250000 | 30000 |
|    4 | Mackenzie | Blitzer   |   92 |       5 |   39 |         3 | 230000 | 30000 |
|    5 | Zina      | Blitzer   |  101 |       7 |   67 |         4 | 270000 | 40000 |
|    6 | Hrolfr    | Blitzer   |   81 |       4 |   27 |         2 | 230000 | 20000 |
|    9 | Iniobong  | Line   |   20 |       5 |   37 |         2 | 110000 |     0 |
|   10 | Agata     | Line   |    0 |       2 |    9 |         1 |  70000 |     0 |
|   11 | Matheo    | Line   |   34 |       5 |   28 |         2 | 140000 |     0 |
|   13 | Grumman   | Line   |   27 |       4 |   35 |         2 | 130000 | 20000 |
|   15 | Pinja     | Attacker |   56 |       4 |   37 |         2 | 210000 | 20000 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   17 | Lazar     | Blitzer   |   41 |       1 |   10 |         1 | 160000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   23 | Dragos.      | Blitzer   |  140 |       9 |   62 |         4 | 260000 | 40000 |
|   25 | Adalberto.   | Blitzer   |   84 |       7 |   54 |         4 | 230000 |     0 |
|   28 | Abiel.       | Line   |   51 |       7 |   60 |         4 | 230000 | 40000 |
|   29 | Carsen.      | Line   |    7 |       2 |    2 |         0 |  90000 |     0 |
|   37 | Gyorgy.      | Line   |    5 |       2 |   22 |         1 |  70000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Irregular Cogs" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```



## Records

### Record by Division 

| Team           | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Irregular Cogs | Pro      |   79 |   15 |   54 |  148 | 61.461 |  397 |  323 |  176 |     -96 |    2 |
| Irregular Cogs | Street   |    8 |    3 |    2 |   13 | 73.077 |   27 |   14 |   30 |       9 |    0 |
| Irregular Cogs | Open     |    3 |    1 |    3 |    7 | 37.500 |   15 |   21 |   11 |       0 |   -1 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Irregular Cogs" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team           | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Irregular Cogs |   90 |   19 |   59 |  168 | 57.443 |  439 |  358 |  217 |     -87 |    1 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Irregular Cogs" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```
80-17-53

### Prizes

* Green Cup I - Green Cup Champions [[team1stplace#gci]]
* Green Cup VII - Tough Brake of Alsoran [[team3rdplace#gcvii]]
* Green Cup VII - Stacks Division Champions [[teamdivision#gcvii]]
* Green Cup V Memorial - Old-Era Champs [[team2ndplace]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Irregular Cogs | Green Cup V Memorial |    8 |    3 |    2 |     13 | 73.08 |   27 |   14 |   20 |      9 |    0 |
| Irregular Cogs | Green Cup VII        |   13 |    0 |    5 |     18 | 72.22 |   51 |   32 |   12 |    -19 |    2 |
| Irregular Cogs | **Green Cup I**          |    7 |    3 |    2 |     12 | 70.83 |   36 |   27 |   14 |    -10 |    2 |
| Irregular Cogs | Green Cup IX         |   11 |    1 |    5 |     17 | 67.65 |   49 |   36 |   15 |    -12 |    7 |
| Irregular Cogs | Green Cup X          |   10 |    2 |    5 |     17 | 64.71 |   49 |   35 |   18 |     -4 |    0 |
| Irregular Cogs | UBBL Challenge       |    2 |    1 |    1 |      4 |    62.50 |    9 |    8 |    5 |     -2 |   -1 |
| Irregular Cogs | Green Cup XI         |    9 |    2 |    6 |     17 | 58.8235 |   48 |   39 |   21 |      0 |   -1 |
| Irregular Cogs | Green Cup IV         |    5 |    2 |    4 |     11 | 54.55 |   29 |   26 |   11 |     -9 |    0 |
| Irregular Cogs | Green Cup II         |    6 |    1 |    5 |     12 | 54.17 |   32 |   28 |   17 |    -11 |   -3 |
| Irregular Cogs | UBBL Challenge IV    |    1 |    0 |    1 |      2 |      50.00 |    4 |    7 |    3 |      0 |    0 |
| Irregular Cogs | Green Cup VI         |    6 |    2 |    7 |     15 | 46.67 |   37 |   34 |   23 |     -1 |   -1 |
| Irregular Cogs | Green Cup III        |    5 |    1 |    6 |     12 | 45.83 |   31 |   29 |   11 |    -14 |   -2 |
| Irregular Cogs | Green Cup VIII       |    6 |    1 |    9 |     16 |  40.63 |   33 |   36 |   20 |    -16 |   -3 |
| Irregular Cogs | UBBL Challenge II    |    0 |    0 |    1 |      1 |       0.00 |    2 |    6 |    2 |      2 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Irregular Cogs" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Irregular Cogs have played a lot of BludBol, won the first Green Cup and have the second-most wins in the league. They want more.

### Seasons

The Irregular Cogs won the inaugural Green Cup against their archrivals the [Old Wyrms](oldwyrms) in a thrilling 3-2 game. Then a long period of good play but few results. 

In the first unified modern-era Green Cup (GCVII) the Irregular Cogs snuck through the season playing well, but without the gaudy win streak of the [Machine](orbitalmachine). They amassed the most tournament points through the regular season and when the Machine was knocked out of the playoffs they looked to be a Green Cup lock. But they were defeated in the Burger Conference final by the surprising [Ravenous Eagles](ravenouseagles) and came in third instead.

In the street-level GCV Memorial tournament the Cogs ended up with second place for the rookies and their best showing in many a season. Fans are well aware that it doesn't really count and was only a cash-grab but were mostly happy they did better than the [Wyrms](oldwyrms) in the end.

Both Green Cups IX and X ended in the Division Finals with losses to the [Badger Claws](badgerclaws) and underperforming expectations yet again. GCX even had the Cogs at the top of the standings by the end of the regular season, but a long playoff run just wasn't in the cards.

#### GCXI Projection

W-D-L 9-0-6 

There's no obvious reason the Cogs can't win the Green Cup this season. They have a big payroll and should be able to afford to develop some rookies as the season progresses. Playing for the division title is mostly about keeping the fragile [Badger Claws](badgerclaws) from getting a bye to rest up their scorers, so if things are going well early, expect them to ease up. But in GCX, the Outlands were the toughest division and they don't want to get stuck on the outside looking in.

#### GCXI summary

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Irregular Cogs |     1 |       5 |    2 |   58 |    2 |        5 |      2 |          0 |    3 |     30 |     1 |    1 |   19 |           1 |           2 |
| Irregular Cogs |     2 |       9 |    1 |   30 |    4 |        9 |      4 |          0 |    1 |     46 |     1 |    1 |   14 |           1 |           3 |
| Irregular Cogs |     3 |       9 |    2 |   35 |    3 |       15 |      3 |          1 |    1 |     46 |     3 |    1 |   18 |           2 |           2 |
| Irregular Cogs |     4 |       9 |    3 |   54 |    3 |       20 |      3 |          0 |    2 |     56 |     2 |    1 |   21 |           3 |           2 |
| Irregular Cogs |     5 |      17 |    5 |   74 |    6 |       11 |      6 |          2 |    2 |     44 |     1 |    1 |   34 |           5 |           1 |
| Irregular Cogs |     6 |       7 |    1 |   37 |    1 |        6 |      1 |          0 |    0 |     47 |     2 |    1 |    9 |           3 |           1 |
| Irregular Cogs |     7 |      22 |    4 |  107 |   12 |       23 |     12 |          0 |    0 |     53 |     2 |    1 |   29 |           5 |           4 |
| Irregular Cogs |     8 |      19 |    5 |   70 |    9 |       31 |      9 |          2 |    1 |     44 |     4 |    1 |   35 |           2 |           5 |
| Irregular Cogs |     9 |       9 |    3 |   34 |    2 |        4 |      2 |          1 |    1 |     36 |     6 |    1 |   20 |           3 |           1 |
| Irregular Cogs |    10 |      18 |    7 |  103 |    8 |       10 |      8 |          1 |    3 |     42 |     1 |    1 |   42 |           4 |           7 |
| Irregular Cogs |    11 |      10 |    3 |   76 |    3 |        9 |      3 |          0 |    1 |     34 |     0 |    1 |   19 |           3 |           3 |
| Irregular Cogs |    12 |       5 |    0 |   10 |    2 |        6 |      2 |          0 |    0 |     26 |     0 |    1 |    7 |           3 |           0 |
| Irregular Cogs |    13 |       9 |    3 |   37 |    2 |       14 |      2 |          0 |    0 |     37 |     0 |    1 |   16 |           3 |           1 |
| Irregular Cogs |    14 |       9 |    1 |   44 |    2 |        1 |      2 |          2 |    0 |     24 |     1 |    1 |   14 |           1 |           2 |
| Irregular Cogs |    15 |      10 |    2 |   50 |    4 |       17 |      4 |          0 |    3 |     35 |     0 |    1 |   21 |           1 |           2 |
| Irregular Cogs |   R16 |       9 |    4 |   69 |    2 |        5 |      2 |          0 |    1 |     42 |     2 |    1 |   21 |           4 |           2 |
| Irregular Cogs |    QF |       7 |    2 |   56 |    1 |        6 |      1 |          0 |    2 |     35 |     0 |    1 |   16 |           3 |           2 |

```
SELECT pl.f_tname AS Team, mt.round, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Irregular Cogs" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### GCXI roster


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    3 | Frans       | 17 |      43 |   19 |  241 |    4 |     9 |   24 |    5 |    1 |   36 |    0 |    1 |           0 |      2 |    3 |    1 |       0 |      0 |   78 |
|    4 | Mackenzie   |  7 |       5 |    2 |   13 |    0 |     0 |    2 |    1 |    2 |   22 |    1 |    0 |           1 |      0 |    0 |    0 |       0 |      0 |   12 |
|    5 | Zina        | 17 |       5 |    1 |   25 |    0 |     0 |    4 |    1 |    6 |   98 |    6 |    0 |           0 |      1 |    4 |    1 |       0 |      0 |   17 |
|    6 | Hrolfr      |  7 |      14 |    5 |  116 |    4 |    14 |    2 |    0 |    1 |   17 |    1 |    1 |           2 |      1 |    1 |    0 |       0 |      0 |   26 |
|    9 | Iniobong    | 15 |       2 |    0 |    9 |    1 |     3 |    0 |    0 |    1 |   43 |    0 |    0 |           0 |      0 |    5 |    0 |       2 |      0 |    3 |
|   10 | Agata       |  7 |       2 |    0 |    9 |    0 |     0 |    1 |    0 |    0 |   17 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|   11 | Matheo      | 16 |       7 |    1 |   16 |    3 |    14 |    1 |    0 |    0 |   24 |    0 |    4 |           0 |      0 |    3 |    1 |       1 |      0 |   26 |
|   13 | Grumman     |  8 |       2 |    0 |    2 |    1 |     1 |    0 |    0 |    1 |   32 |    0 |    1 |           0 |      0 |    1 |    0 |       1 |      0 |    8 |
|   15 | Pinja       | 16 |       2 |    0 |    7 |    0 |     0 |    0 |    1 |    2 |  114 |    7 |    3 |           1 |      0 |    1 |    2 |       0 |      0 |   21 |
|   17 | Lazar       | 10 |      17 |   11 |   77 |    3 |     2 |    8 |    0 |    0 |   15 |    1 |    1 |           0 |      1 |    1 |    0 |       0 |      0 |   41 |
|   29 | Carsen.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    5 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    7 |
|   64 | Saxa.       |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      R |    0 |
|   67 | Mirche.     |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   20 |    0 |    0 |           0 |      0 |    1 |    1 |       0 |      R |    0 |
|   68 | Loegaire.   |  7 |       2 |    0 |    5 |    1 |     4 |    0 |    0 |    2 |   31 |    0 |    0 |           0 |      1 |    0 |    0 |       0 |      R |    5 |
|   74 | Ignat.      | 10 |       2 |    0 |    7 |    1 |     3 |    2 |    0 |    0 |   77 |    3 |    0 |           0 |      0 |    1 |    0 |       0 |      R |    1 |
|   81 | Alexandros. | 12 |      38 |    1 |  184 |   29 |   118 |    1 |    0 |    0 |    6 |    0 |    0 |           2 |      5 |    3 |    0 |       0 |      R |   32 |
|   82 | Merlyn.     | 13 |      41 |    8 |  231 |   18 |    19 |   21 |    1 |    1 |   26 |    5 |    1 |           4 |      4 |    1 |    1 |       1 |      1 |   51 |
|   90 | Granlan.    | 12 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   32 |    0 |    1 |           0 |      0 |    4 |    1 |       0 |      1 |    5 |
|   90 | Tel.        |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   18 |    0 |    0 |           0 |      0 |    1 |    2 |       0 |      1 |    2 |
|   95 | Erazem.     |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   41 |    2 |    3 |           0 |      0 |    2 |    2 |       1 |      1 |   19 |
|   97 | Meryem.     |  1 |       1 |    0 |    2 |    1 |     5 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    1 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Irregular Cogs" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player      | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Besz       | Runner   |   33 |    4 |   23 |  64 |   23 |  110 |    0 |    0 |    1 |    0 |    5 |  206 |
| *Halfleg*  | Runner | ?? | ?? | ?? | 51 | 12 | 89 | 2 | 2 | 0 | 3 | 3 | 154 |
| *Crobuzon* | Attacker | ?? | ?? | ?? | 50 | 33 | 5 | 1 | 6 | 5 | 0 | 4 | 148 |
| Alexandros | Runner   |   26 |    5 |   18 |   49 |    9 |   86 |    1 |    0 |    0 |    0 |    5 |  140 |
| Dragos     | Blitzer  |   37 |    3 |   22 |   62 |   38 |    5 |    2 |    1 |    0 |    0 |    3 |  140 |
| **Frans**  | Blitzer  |   24 |    5 |   13 |   42 |   30 |    7 |    6 |    1 |    1 |    0 |    4 |  133 |
| Merlyn     | Runner   |   19 |    3 |   10 |   32 |   19 |   43 |    2 |    1 |    0 |    0 |    4 |  126 |
| Saxa       | Blitzer  |   24 |    2 |   19 |   45 |   23 |   11 |    4 |    2 |    1 |    0 |    2 |  104 |
| **Zina**   | Blitzer  |   36 |    6 |   25 |   67 |   17 |    2 |    1 |    8 |    4 |    1 |    4 |  101 |
| **Mackenzie** | Blitzer  |   23 |    3 |   13 |   39 |   20 |    4 |    1 |    2 |    1 |    0 |    4 |   92 |
| *BasLag*   | Attacker | ?? | ?? | ?? | 52 | 18 | 2 | 1 | 6 | 1 | 0 | 4 | 92 |
| Melisa     | Runner   |   16 |    2 |   14 |   32 |    8 |   42 |    2 |    0 |    0 |    0 |    3 |   85 |
| Adalberto  | Blitzer  |   27 |    4 |   23 |   54 |   11 |    4 |    1 |   10 |    4 |    1 |    3 |   84 |
| **Hrolfr** | Blitzer  |   16 |    3 |    8 |   27 |   19 |    6 |    0 |    4 |    0 |    0 |    2 |   81 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Irregular Cogs" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

[[besz]] played in the old-era. No one has any proof she didn't play in all the matches she says she did (as an underused backup to Halfleg), but no one quite believes her either. (Updated: Besz played 4 games in the old era. Her stats above now reflect this.) She was good for a long time, and the heart of the Cogs, though [[alexandros]] has now taken over the position.

The biggest problem with the Cogs' lineup is the value they have to give up to their opponents. Some say the team would be better if they kept a minimum of overpaid stars and went with a youth-focused approach. That's what worked in the GCV.


#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|   81 | Besz.    | Runner   |      12 |      1 | 270000 | 60000 |
|   82 | Solas.   | Runner   |       1 |      1 |  80000 |     0 |
|   92 | Iounia.  | Line     |       5 |      1 | 120000 |     0 |
|   95 | Arzu.    | Attacker |       2 |      1 | 170000 |     0 |
|   96 | Venkata. | Attacker |       5 |      1 | 180000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Irregular Cogs" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

Gryj the Hun was an upspirer back when they helped found the UBBL. Now they have blended right into the fabric and it's hard to imagine them anywhere else.

### Fans

The fans are bursting for another championship.

The Cogs and the [Old Wyrms](oldwyrms) are traditional rivals, and the fact the Cogs won the first Green Cup is pretty much *the* bright point for the Cogs in that history. More recently, the [Orbital Machine](orbitalmachine) made the Cogs' shit list in "the Betrayal at Dungardin" and they're always looking over their shoulders at the [Eldritch Fatality](eldritchfatality) who use the same playbook.

### Famous Games

The Battle of Dungardin [[gcvii-08-omic]] in GCVII Week 8



