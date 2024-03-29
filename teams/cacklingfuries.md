# Cackling Furies

The Cackling Furies are an Old-Era expansion team that can cause a lot of injuries, but will take a lot in exchange.

## Playbook

The Furies use the Norton playbook, which is mostly a way to get less skilled players to channel their energy into flinging themselves at the opposition in a terrible frenzy. The use a couple of strong attacking ball-hawks, some blitzers, even receivers, but all one sees when a team is going Norton is whirling masses of limbs and teeth. To do this they can't protect themselves very well, so there is a lot of roster turnover.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    2 | Thiemo     | Lineman  |   36 |       5 |   19 |         1 | 140000 |     0 |
|    3 | Aronne     | Catcher  |  147 |       6 |   52 |         3 | 260000 | 30000 |
|    4 | Shashi     | Catcher  |  100 |       3 |   26 |         2 | 240000 | 20000 |
|    6 | Faite      | Blitzer  |   20 |       2 |   15 |         1 | 140000 |     0 |
|    7 | Mahendra   | Lineman  |    2 |       3 |   11 |         1 | 180000 | 50000 |
|    8 | Puneeta    | Lineman  |   25 |       4 |   26 |         2 |  90000 |     0 |
|    9 | Aarthi     | Lineman  |    0 |       2 |    6 |         0 |  50000 |     0 |
|   10 | Orazio     | Lineman  |   25 |       6 |   19 |         1 |  90000 |     0 |
|   11 | Tofa       | Lineman  |    0 |       2 |    6 |         0 |  50000 |     0 |
|   12 | Matleena   | Lineman  |    7 |       6 |   16 |         1 |  70000 |     0 |
|   13 | Chizoba    | Lineman  |   13 |       4 |   17 |         1 |  70000 |     0 |
|   15 | Svyatopolk | Yhetee   |   32 |       5 |   19 |         1 | 220000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    7 | Aniketos   | Lineman  |    0 |       2 |    7 |         0 |  50000 |     0 |
|   10 | Mumina     | Lineman  |    0 |       2 |    6 |         0 |  50000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Luanna.    | Thrower        |  198 |       7 |   58 |         4 | 270000 | 50000 |
|    5 | Danr.      | Blitzer        |   84 |       4 |   43 |         3 | 240000 | 30000 |
|    6 | Ed.        | Blitzer        |   44 |       6 |   44 |         3 | 200000 | 30000 |
|   14 | Hin.       | Norse Werewolf |   55 |       6 |   56 |         4 | 230000 | 40000 |
|   16 | Hasan.     | Lineman        |   35 |       5 |   31 |         2 | 150000 | 10000 |
|   20 | Kota.      | Catcher        |  104 |       4 |   38 |         3 | 200000 |     0 |
|   26 | Bryce.     | Blitzer        |   56 |       6 |   43 |         3 | 230000 | 30000 |
|   27 | Boreal.    | Lineman        |   39 |       5 |   43 |         3 | 120000 |     0 |
|   28 | Shalev.    | Lineman        |    0 |       1 |    1 |         0 | 160000 | 60000 |
|   29 | Francizek. | Lineman        |   20 |       3 |   28 |         2 | 120000 | 20000 |
|   30 | Rafferty.  | Lineman        |    7 |       2 |    5 |         0 |  80000 |     0 |
|   31 | Garron.    | Lineman        |   10 |       6 |   60 |         4 | 110000 | 40000 |
|   32 | Walton.    | Lineman        |   31 |       8 |   83 |         6 | 160000 | 50000 |
|   34 | Ife.       | Norse Werewolf |   51 |       6 |   50 |         3 | 220000 | 30000 |
|   41 | Kalisha.   | Lineman        |    8 |       1 |    3 |         0 |  70000 |     0 |
|   42 | Sylvette.  | Lineman        |    6 |       1 |    2 |         0 |  70000 |     0 |
|   51 | Melpomeni. | Lineman        |    1 |       2 |    5 |         0 |  50000 |     0 |
|   52 | Shaul.     | Lineman        |    2 |       3 |    3 |         0 |  50000 |     0 |
|   52 | Masamba.   | Lineman        |    2 |       1 |    2 |         0 |  50000 |     0 |
|   52 | Fawn.      | Lineman        |    2 |       1 |    5 |         0 |  50000 |     0 |
|   53 | Svetlana.  | Lineman        |    3 |       2 |    3 |         0 |  50000 |     0 |
|   53 | Rosalia.   | Lineman        |    2 |       2 |    2 |         0 |  50000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Cackling Furies" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division (W-D-L)

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Cackling Furies | Pro      |   45 |   25 |   54 |  124 | 45.985 |  244 |  254 |  278 |      45 |    0 |
| Cackling Furies | Open     |    7 |    1 |    5 |   13 | 55.208 |   30 |   23 |   39 |      14 |    4 |
| Cackling Furies | Street   |    3 |    3 |    6 |   12 | 42.500 |   12 |   22 |   20 |       0 |   -2 |


```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Cackling Furies" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```



### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Cackling Furies |   55 |   29 |   65 |  149 | 47.980 |  286 |  299 |  337 |      59 |    2 |

```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Cackling Furies" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup III - Runner-Up [[team2ndplace#gciii]]
* Green Cup III - Doom Fist [[teamcasualties#gciii]]
* UBBL Challenge II - Runner-Up [[team2ndplace#ubbl challenge ii]]

### Seasons

| Team            | Season               | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------------|----------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Cackling Furies | UBBL Challenge II    |    3 |    0 |    1 |      4 |      75 |   11 |    5 |   16 |      5 |    3 |
| Cackling Furies | Green Cup III        |    9 |    1 |    3 |     13 | 73.0769 |   33 |   23 |    0 |     13 |    1 |
| Cackling Furies | UBBL Challenge       |    2 |    1 |    1 |      4 |    62.5 |   12 |    8 |    9 |     12 |    2 |
| Cackling Furies | Green Cup IX         |    7 |    7 |    3 |     17 | 61.7647 |   38 |   34 |   24 |     -3 |    4 |
| Cackling Furies | Green Cup X          |    7 |    4 |    6 |     17 | 52.9412 |   41 |   30 |   27 |     -1 |    0 |
| Cackling Furies | UBBL Challenge V     |    1 |    0 |    1 |      2 |      50 |    2 |    4 |    3 |     -4 |    0 |
| Cackling Furies | StUBBL Scramble      |    0 |    2 |    0 |      2 |      50 |    1 |    1 |    0 |      0 |    1 |
| Cackling Furies | Green Cup II         |    4 |    2 |    5 |     11 | 45.4545 |   20 |   19 |    0 |     10 |   -1 |
| Cackling Furies | Green Cup IV         |    3 |    2 |    5 |     10 |      40 |   18 |   25 |    0 |     16 |   -2 |
| Cackling Furies | Green Cup Classic 06 |    1 |    4 |    3 |      8 |    37.5 |   11 |   15 |   15 |      0 |    1 |
| Cackling Furies | Green Cup XI         |    5 |    2 |    9 |     16 |    37.5 |   32 |   36 |   25 |     -2 |    0 |
| Cackling Furies | Green Cup V Memorial |    3 |    1 |    6 |     10 |      35 |   11 |   21 |   19 |      0 |   -3 |
| Cackling Furies | Green Cup VII        |    4 |    3 |    9 |     16 |  34.375 |   28 |   34 |   31 |      4 |   -1 |
| Cackling Furies | UBBL Challenge IV    |    1 |    0 |    2 |      3 | 33.3333 |    5 |    6 |    5 |      1 |   -1 |
| Cackling Furies | Green Cup VIII       |    5 |    0 |   11 |     16 |   31.25 |   23 |   38 |   43 |      8 |   -2 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Cackling Furies" ORDER BY mr.win_pct DESC limit 16;
```

## History



### Seasons

The Cackling Furies aren't an original Green Cup team, but in their second season (GCIII) they laid a lot of smack down, winning the Doom Fist (with 38 Casualties) and placing second overall to a just more talented [Old Wyrms](oldwyrms) team.

Their next winning seasons only came in the Open Division in the first two UBBL Challenges. The Furies represented the Green Cup faithful in the final for the UBBL Pennant in UCII after stomping through the B-Side challengers, but fell to the [Brutes](gargantuanbrutes).

After that it took a long time to work back to a winning season in Green Cup play, but they managed it. Green Cups IX and X went better for the Furies. They made it to the division finals each time before being knocked out by the [Eldritch Fatality](eldritchfatality) and [Ravenous Eagles](ravenouseagles) respectively.

#### Summary GCXI

The Furies didn't miss their projected target by much, going 5-2-8 in the regular season. The problem was the resurgent [Darkling Spectres](darklingspectres) who wildly outperformed their expectations. This meant that despite the Furies having done everything right, including giving [[luanna]] another shot at a Relentless Cannon award, they were on the outside looking in, come playoff time. Losing [[sophronia]] and [[rickon]] was also tough for the future of the team. They didn't get the funding that would really lend to bringing all their veterans back (as of this writing [[luanna]] and [[Hin]] (team MVP and Block leader respectively) to name a couple aren't under contract for GCXII) so their window of real competitiveness may have closed for the time being.

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Cackling Furies |     1 |      10 |    2 |   42 |    5 |       22 |      5 |          0 |    1 |     58 |     1 |    1 |   18 |           2 |           2 |
| Cackling Furies |     2 |      13 |    1 |   40 |    5 |       27 |      5 |          0 |    1 |     26 |     3 |    1 |   15 |           1 |           2 |
| Cackling Furies |     3 |      18 |    4 |   84 |    8 |       17 |      8 |          0 |    3 |     60 |     1 |    1 |   31 |           4 |           5 |
| Cackling Furies |     4 |      12 |    5 |   57 |    5 |       13 |      5 |          1 |    1 |     65 |     0 |    1 |   29 |           5 |           0 |
| Cackling Furies |     5 |       8 |    1 |   27 |    2 |        3 |      2 |          0 |    2 |     46 |     3 |    1 |   14 |           1 |           2 |
| Cackling Furies |     6 |       8 |    3 |   40 |    3 |       14 |      3 |          0 |    2 |     41 |     2 |    1 |   21 |           0 |           3 |
| Cackling Furies |     7 |       9 |    2 |   54 |    3 |        5 |      3 |          0 |    1 |     58 |     0 |    1 |   16 |           2 |           2 |
| Cackling Furies |     8 |      18 |    2 |   70 |    6 |       23 |      6 |          0 |    1 |     49 |     3 |    1 |   19 |           2 |           5 |
| Cackling Furies |     9 |      16 |    1 |   44 |    6 |       12 |      6 |          0 |    0 |     49 |     0 |    1 |   14 |           1 |           4 |
| Cackling Furies |    10 |      15 |    2 |   61 |    5 |       34 |      5 |          0 |    1 |     56 |     0 |    1 |   18 |           5 |           2 |
| Cackling Furies |    11 |      13 |    2 |   64 |    4 |       11 |      4 |          1 |    3 |     62 |     2 |    1 |   23 |           1 |           2 |
| Cackling Furies |    12 |       9 |    3 |   32 |    3 |       21 |      3 |          2 |    0 |     22 |     0 |    1 |   21 |           1 |           3 |
| Cackling Furies |    13 |       7 |    3 |   25 |    1 |        4 |      1 |          0 |    5 |     41 |     3 |    1 |   25 |           3 |           0 |
| Cackling Furies |    14 |      11 |    1 |   41 |    3 |        9 |      3 |          0 |    2 |     43 |     0 |    1 |   15 |           1 |           3 |
| Cackling Furies |    15 |       3 |    0 |    9 |    1 |        1 |      1 |          0 |    2 |     42 |     0 |    1 |   10 |           3 |           0 |
| Cackling Furies |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    0 |    0 |         BYE |           L |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Cackling Furies" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster GCXI

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Luanna.    | 16 |      84 |    1 | **204** | **54** | 221 | 0 |    1 |    0 |   15 |    0 |    1 |           5 |      2 |    2 |    0 |       0 |    0 | **64** |
|    2 | Thiemo     |  7 |       9 |    2 |   25 |    0 |     0 |    2 |    0 |    1 |   15 |    0 |    2 |           0 |      2 |    3 |    1 |       0 |      0 |   18 |
|    3 | Aronne     | 10 |      30 |    7 |  202 |    5 |    -6 |   29 |    0 |    0 |   18 |    2 |    0 |           1 |      9 |    3 |    0 |       0 |      0 |   26 |
|    4 | Shashi     |  7 |      18 |    6 |  119 |    0 |     0 |   12 |    1 |    0 |    8 |    1 |    0 |           1 |      5 |    2 |    1 |       0 |      0 |   20 |
|    5 | Danr.      |  9 |       5 |    3 |   20 |    0 |     0 |    1 |    1 |  *5* |   47 |    1 |    1 |           0 |      1 |    3 |    1 |       0 |      0 |   26 |
|    6 | Faite      | 13 |       5 |    2 |   27 |    0 |     0 |    3 |    0 |    3 |   69 |    0 |    1 |           0 |      2 |    2 |    4 |       2 |      0 |   17 |
|    6 | Ed.        |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   38 |    2 |    0 |           0 |      0 |    2 |    0 |       1 |      0 |    0 |
|    7 | Mahendra   |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   27 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|    7 | Aniketos   |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    9 |    0 |    0 |           0 |      0 |    2 |    0 |       2 |      0 |    0 |
|    8 | Puneeta    |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   15 |    2 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    0 |
|    9 | Aarthi     |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   19 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|    9 | Rina.      |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   13 |    0 |    1 |           0 |      0 |    1 |    0 |       0 |      0 |    9 |
|   10 | Orazio     |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   26 |    3 |    1 |           0 |      0 |    1 |    1 |       0 |      0 |    9 |
|   10 | Mumina     |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   16 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   11 | Tofa       |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    6 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      0 |    0 |
|   12 | Matleena   |  6 |       0 |    0 |    6 |    0 |     0 |    0 |    0 |    0 |   13 |    0 |    0 |           0 |      0 |    2 |    0 |       0 |      0 |    0 |
|   13 | Chizoba    |  7 |       2 |    0 |    1 |    0 |     0 |    0 |    0 |    0 |   26 |    1 |    0 |           0 |      0 |    2 |    1 |       0 |      0 |    0 |
|   14 | Hin.       | 16 |       0 |    1 |    5 |    0 |     0 |    0 |    0 |    2 | **139** | 3 |    1 |           0 |      0 |    1 |    2 |       0 |      0 |   12 |
|   15 | Svyatopolk | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |  *5* |   87 |    2 |    3 |           0 |      0 |    1 |    0 |       0 |      0 |   25 |
|   16 | Hasan.     |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   31 |    0 |    2 |           0 |      0 |    0 |    0 |       2 |      0 |   14 |
|   30 | Rafferty.  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    7 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    7 |
|   54 | Sevinc.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    8 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   84 | Rickon.    | 10 |      17 | **10** | 81 |    1 |     1 |   13 |    1 |    0 |   12 |    0 |    1 |           0 |      3 |    0 |    1 |       0 |      1 |   38 |
|   95 | Sophronia. |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   49 |    0 |    0 |           0 |      0 |    1 |    0 |       1 |      1 |    0 |
|   97 | Kichiro    |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |


```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Cackling Furies" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

#### Projection GCXII

W-D-L 7-1-8

The Furies are hoping for a chance at the divisional title, but will have to work to make the playoffs first. With Luanna out of the picture at the season's start with a rookie instead, it's probably going to be a rough one for Furies fans.


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Luanna    | Thrower        |   22 |   14 |   22 |   58 |    8 |  134 |    1 |    3 |    1 |    0 |    6 |  198 || Rickon    | Catcher        |   32 |   16 |   40 |   88 |   41 |    2 |    2 |    1 |    0 |    0 |    4 |  151 |
| Rickon    | Catcher        |   32 |   16 |   40 |   88 |   41 |    2 |    2 |    1 |    0 |    0 |    4 |  151 |
| **Aronne**     | Catcher        |   20 |   14 |   18 |   52 |   31 |   30 |    2 |    0 |    0 |    0 |    4 |  147 |
| *Rodrik*   | Catcher | *23* | ?? | ?? | 44 | 39 | 2 | 2 | 0 | 0 | 0 | 3 | 138 |
| *Benjen*   | Blitzer | ?? | ?? | ?? | 44 | 6 | 1 | 0 | 19 | 13 | 6 | 2 | 105 |
| Kota      | Catcher        |   10 |    5 |   23 |   38 |   25 |    2 |    0 |    1 |    0 |    0 |    5 |  104 |
| **Shashi**     | Catcher        |   10 |    4 |   12 |   26 |   27 |    0 |    1 |    0 |    0 |    1 |    3 |  100 |
| Danr      | Blitzer        |   18 |   11 |   14 |   43 |   12 |    2 |    3 |    7 |    3 |    0 |    4 |   84 |
| Fawcett   | Thrower        |   21 |   15 |   25 |   61 |    1 |   71 |    3 |    1 |    1 |    0 |    0 |   84 |
| Mukabe    | Blitzer        |   15 |    7 |   24 |   46 |    6 |    1 |    0 |   13 |    5 |    1 |    5 |   82 |
| *Artos*    | Blitzer | ?? | ?? | ?? | 35 | 16 | 3 | 1 | 1 | 1 | 2 | 4 | 81 |
| Sophronia | Attacker |   28 |   17 |   31 |   76 |    0 |    0 |    1 |   14 |    7 |    2 |    6 |   78 |
| Snow      | Heavy         |   31 |   13 |   36 |   80 |    0 |    0 |    0 |   20 |    5 |    2 |    4 |   74 |
| Borghild  | Catcher        |    8 |    8 |    4 |   20 |   18 |    2 |    0 |    0 |    1 |    1 |    0 |   60 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Cackling Furies" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```


While the old-era superstar [[Rodrik]] was atop the Furies' leaderboard for ages, [[Aronne]] is the future for this team. [[luanna]]'s surprise passing performance in GCX got her the Relentless Cannon award for the season, and could be an indication of a more well-rounded approach to future BludBol.

#### Award Winners

| #    | Player | Position | Seasons | Prizes | Value  | Bonus |
|------|--------|----------|---------|--------|--------|-------|
|    1 | Luanna | Thrower  |       7 |      2 | 270000 | 50000 |
|   81 | Yusra  | Thrower  |       3 |      1 | 150000 |     0 |
|   85 | Benjen | Blitzer  |       3 |      1 | 110000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Cackling Furies" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

### Fans

Cackling Furies fans don't have a lot of rivalries, getting in everyone's faces about evenly. They do, however, dislike the [Old Wyrms](oldwyrms) quite vehemently. The Furies' style of play can make them quite dangerous to the (fragile) Wyrms as well.

### Famous Games

The match in Green Cup VIII (Week 1) against the [Kaiju Dynamo](kaijudynamo) where Yusra got 3 interceptions in one match and then died.

The UBBL Challenge II match against the [[gentlefolk]] with all the casualties.
