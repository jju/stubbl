# Old Wyrms

Even when they're bad they aren't that bad. And when they're good they're dazzling. The Wyrms are the UBBL's only four-time champions and the only team to have defended a championship (twice).

## Playbook

The Old Wyrms (OW) use what's known as the Excelsior playbook, where a fast fragile receiving corps works together downfield making catches in traffic and getting out of trouble. It's a shorter-passing game than the High Extension playbook used by the [Glorious Hounds](glorioushounds) but when you can avoid injury it's very effective, as the Wyrms have shown.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Jia      | Thrower  |   66 |       4 |   33 |         2 | 180000 |     0 |
|    2 | Evander  | Thrower  |   98 |       5 |   42 |         3 | 240000 | 40000 |
|    3 | Amador   | Catcher  |  173 |       6 |   56 |         4 | 250000 | 40000 |
|    4 | Seosamh  | Catcher  |  124 |       4 |   33 |         2 | 220000 |     0 |
|    5 | Kelemann | Blitzer  |   87 |       4 |   42 |         3 | 250000 |     0 |
|    6 | Rati     | Blitzer  |   69 |       6 |   50 |         3 | 220000 | 30000 |
|    8 | Yasmani  | Line  |   12 |       2 |   16 |         1 |  80000 |     0 |
|   10 | Oeneios  | Line  |   20 |       2 |   13 |         1 | 110000 |     0 |
|   11 | Andela   | Line  |   38 |       4 |   37 |         2 | 120000 |     0 |
|   14 | Olaug    | Catcher  |   54 |       3 |   21 |         1 | 190000 |     0 |
|   15 | Modest   | Catcher  |   85 |       4 |   28 |         2 | 240000 |     0 |
|   16 | Belmont  | Line  |   35 |       4 |   30 |         2 | 150000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   17 | Roni     | Catcher  |   89 |       5 |   24 |         2 | 260000 | 30000 |
|   18 | Zalmon   | Catcher  |   32 |       1 |    7 |         0 | 170000 |     0 |
|   19 | Headley  | Blitzer  |   15 |       1 |    6 |         0 | 130000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Old Wyrms" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division 

| Team      | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Old Wyrms | Pro      |   77 |   27 |   49 |  153 | 54.190 |  454 |  377 |  138 |    -240 |    2 |
| Old Wyrms | Street   |    7 |    1 |    3 |   11 | 68.182 |   23 |   12 |   12 |      -9 |   -3 |
| Old Wyrms | Open     |    3 |    0 |    1 |    4 | 75.000 |   10 |    7 |    3 |     -10 |    2 |

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Old Wyrms" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team      | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Old Wyrms |   87 |   28 |   53 |  168 | 56.867 |  487 |  396 |  153 |    -259 |    1 |


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Old Wyrms" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup I - Runner-Up [[team2ndplace#gci]]
* Green Cup II - Tough Brake of Alsoran [[team3rdplace#gcii]]
* Green Cup III - Green Cup Champions [[team1stplace#gciii]]
* Green Cup IV - Green Cup Champions [[team1stplace#gciv]]
* Green Cup IX - Green Cup IX Champions [[team1stplace#gcix]]
* Green Cup IX - Burger Conference Champions [[teamconference#gcix]]
* Green Cup IX - Stacks Division Champions [[teamdivision#gcix]]
* Green Cup V Memorial - Picked-Off Primer [[team3rdplace]]
* Green Cup X - Green Cup X Champions [[team1stplace#gcx]]
* Green Cup X - Burger Conference Champions [[teamconference#gcx]]
* Green Cup X - Stacks Division Champions [[teamdivision#gcx]]

### Seasons

| Team      | Season               | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|----------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Old Wyrms | **Green Cup IX**     |   15 |    1 |    3 |     19 | 81.58 |   72 |   46 |   20 |    -17 |    2 |
| Old Wyrms | UBBL Challenge       |    3 |    0 |    1 |      4 |   75.00 |   10 |    7 |    4 |    -10 |    2 |
| Old Wyrms | **Green Cup III**    |    8 |    3 |    2 |     13 | 73.08 |   43 |   25 |   11 |    -17 |    2 |
| Old Wyrms | **Green Cup X**      |   11 |    5 |    3 |     19 | 71.05 |   61 |   49 |   14 |    -30 |    2 |
| Old Wyrms | Green Cup V Memorial |    7 |    1 |    3 |     11 | 68.18 |   23 |   12 |    9 |     -9 |   -3 |
| Old Wyrms | **Green Cup IV**     |    7 |    3 |    3 |     13 | 65.38 |   39 |   32 |   13 |    -27 |    2 |
| Old Wyrms | Green Cup II         |    6 |    2 |    3 |     11 | 63.64 |   37 |   21 |    2 |    -41 |    0 |
| Old Wyrms | Green Cup I          |    7 |    1 |    4 |     12 |    62.50 |   40 |   28 |    6 |    -12 |    0 |
| Old Wyrms | Green Cup VII        |    6 |    5 |    5 |     16 |  53.13 |   45 |   44 |   18 |    -39 |   -2 |
| Old Wyrms | Green Cup VIII       |    6 |    2 |    8 |     16 |   43.75 |   38 |   39 |   14 |    -21 |   -1 |
| Old Wyrms | Green Cup VI         |    6 |    2 |    8 |     16 |   43.75 |   37 |   42 |   15 |    -21 |    3 |
| Old Wyrms | Green Cup XI         |    5 |    3 |    9 |     17 | 38.2353 |   41 |   49 |   14 |    -13 |   -5 |
| Old Wyrms | Champions Circuit    |    0 |    0 |    1 |      1 |       0.00 |    1 |    2 |    1 |     -2 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Old Wyrms" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Old Wyrms are a founding team of the UBBL and are almost universally loathed because of their winning ways.

### Seasons

While they lost the inaugural Green Cup to the [Irregular Cogs](irregularcogs) they had a replacement player ([[Newb]]) pick up the season MVP. They would go on to have several more chances at championship glory but the rivalry had begun. The Old Wyrms were on their way to another Green Cup appearance in GCII when they got absolutely mauled by the Cogs in the last week of the regular season.

The Wyrms fought through a lot of injuries to win the GCIII title then became the first team to defend a Green Cup win in GCIV. Of course, their efforts at a three-peat were foiled by the interruption of the GCV season, but there was no chance they weren't coming back to the league when the modern era began.

After a lackluster few modern-era seasons (only 6 wins in each 16 game season) the Old Wyrms were undoubtedly the best team in the league in GCIX, with high expectations and impeccable execution through their aerial attacks as they emerged from the Stacks Division through the Burger Conference Championship to hoist the Green Cup. None of the players on this team were Old-Era veterans.

They followed that up in the street-level GCV Memorial tournament as the best team in the tournament until they entered the playoffs, losing to the 8th place [Vanadium Hunters](vanadiumhunters), which was embarassing, but those stats don't really count for anything but player development. The question was whether the real team could bounce back in GCX.

The Tenth Green Cup championship did end up in the Old Wyrms' hands, though it wasn't the same kind of dominating season as the year before. The early weeks were filled with draws and their final record shows their offense was 10 TDs worse than previously, but their defense limited the damage. By the end they didn't need to be perfect, just better than their opponents, which they were.

When it comes down to a winner-take-all match, the Old Wyrms are still beatable as they showed in the first round of the Champions Circuit where they lost to the Open Division Orange Goblet Champions the ponderous [Mules](mules).

#### Projection GCXI

W-D-L 9-1-5

The Wyrms are going into GCXI looking to win it all again. They have a big payroll, and the funds to absorb any financial losses. The general assumption is that they will win the Stacks division easily, but could be vulnerable in the Burger Conference Final depending on how aggressively bashy their rivals play.

#### GCXI summary

This was the worst season in the Old Wyrms' history and they still came within a whisker of a Conference Championship berth. Things never really gelled and despite having a great lineup they were snakebit in the wins department. The team MVP, [[Martti]], was left off the playoff roster, another strange decision by HemSon (though not on par with the vicious snubbing of [[souta]]).

| Team      | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Old Wyrms |     1 |       5 |    2 |   44 |    3 |        9 |      3 |          0 |    0 |     37 |     1 |    1 |   14 |           2 |           2 |
| Old Wyrms |     2 |      14 |    5 |   69 |    4 |        5 |      4 |          1 |    1 |     33 |     1 |    1 |   28 |           1 |           5 |
| Old Wyrms |     3 |       8 |    1 |   17 |    2 |       16 |      2 |          0 |    0 |     28 |     2 |    1 |   10 |           1 |           1 |
| Old Wyrms |     4 |       9 |    2 |   48 |    4 |        4 |      4 |          1 |    1 |     37 |     0 |    1 |   19 |           3 |           2 |
| Old Wyrms |     5 |      28 |    5 |   83 |   12 |       32 |     12 |          0 |    1 |     45 |     2 |    1 |   34 |           5 |           4 |
| Old Wyrms |     6 |       3 |    0 |   15 |    2 |        6 |      2 |          0 |    0 |     28 |     0 |    1 |    7 |           2 |           0 |
| Old Wyrms |     7 |      18 |    4 |  100 |    7 |       27 |      7 |          1 |    1 |     53 |     0 |    1 |   28 |           5 |           4 |
| Old Wyrms |     8 |      10 |    3 |   50 |    5 |       13 |      5 |          0 |    1 |     53 |     3 |    1 |   21 |           3 |           3 |
| Old Wyrms |     9 |      12 |    2 |   33 |    4 |       13 |      4 |          0 |    2 |     23 |     2 |    1 |   19 |           1 |           2 |
| Old Wyrms |    10 |      10 |    2 |   45 |    4 |        7 |      4 |          0 |    0 |     30 |     0 |    1 |   15 |           2 |           4 |
| Old Wyrms |    11 |       8 |    1 |   32 |    4 |       11 |      4 |          0 |    0 |     33 |     0 |    1 |   12 |           4 |           1 |
| Old Wyrms |    12 |       4 |    0 |   15 |    1 |        0 |      1 |          0 |    0 |     23 |     1 |    1 |    6 |           0 |           2 |
| Old Wyrms |    13 |      20 |    4 |   78 |    7 |       29 |      7 |          0 |    2 |     41 |     2 |    1 |   28 |           3 |           4 |
| Old Wyrms |    14 |       5 |    2 |   43 |    2 |       10 |      2 |          0 |    1 |     40 |     1 |    1 |   15 |           2 |           3 |
| Old Wyrms |    15 |      17 |    3 |   75 |    8 |       46 |      8 |          0 |    1 |     32 |     1 |    1 |   24 |           7 |           3 |
| Old Wyrms |   R16 |      12 |    3 |   36 |    3 |       18 |      3 |          1 |    1 |     37 |     1 |    1 |   21 |           1 |           3 |
| Old Wyrms |    QF |      15 |    2 |   64 |    5 |       11 |      5 |          0 |    2 |     41 |     2 |    1 |   20 |           3 |           2 |

```
SELECT pl.f_tname AS Team, mt.round, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Old Wyrms" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season

| #    | Player    | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|-----------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Jia       |  9 |      13 |    0 |   20 |    7 |    29 |    0 |    0 |    0 |    4 |    0 |    1 |           0 |      0 |    2 |    0 |       1 |      0 |   12 |
|    2 | Evander   |  9 |      13 |    0 |   24 |   10 |    48 |    1 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    2 |    1 |       0 |      0 |   10 |
|    3 | Amador    |  7 |      11 |    5 |   62 |    4 |    -4 |    7 |    1 |    0 |   12 |    0 |    1 |           0 |      1 |    3 |    2 |       0 |      0 |   26 |
|    4 | Seosamh   | 11 |      18 | **12** | 140 |   0 |     0 |   13 |    0 |    1 |   21 |    2 |    0 |           1 |      1 |    0 |    0 |       1 |      0 |   38 |
|    5 | Kelemann  |  7 |       6 |    0 |   14 |    2 |    14 |    0 |    0 |    2 |   27 |    3 |    0 |           0 |      0 |    3 |    0 |       0 |      0 |    6 |
|    6 | Rati      | 10 |       0 |    0 |    1 |    0 |     0 |    0 |   0 | **3** | **113** | 3 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    6 |
|    8 | Yasmani   | 15 |       3 |    0 |   15 |    2 |     8 |    0 |    0 |    0 |   30 |    0 |    2 |           0 |      0 |    8 | **4** |      0 |      0 |   12 |
|   10 | Oeneios   |  9 |       9 |    1 |    9 |    4 |    13 |    3 |    0 |    1 |   19 |    0 |    1 |           1 |      0 |    3 |    0 |       1 |      0 |   14 |
|   11 | Andela    | 11 |       1 |    0 |   -7 |    0 |     0 |    0 |    1 |    0 |   26 |    0 |    0 |           0 |      0 |    4 |    0 |       0 |      0 |    2 |
|   14 | Olaug     |  7 |      16 |    5 |  124 |   10 |    19 |    9 |    1 |    0 |   25 |    2 |    1 |           1 |      5 |    1 |    1 |       0 |      0 |   32 |
|   15 | Modest    |  7 |       5 |    1 |   11 |    0 |     0 |    2 |    0 |    1 |   26 |    2 |    2 |           0 |      1 |    3 |    1 |       0 |      0 |   15 |
|   16 | Belmont   | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   59 |    1 |    0 |           0 |      0 |    1 |    0 |       0 |      0 |    2 |
|   18 | Zalmon    |  7 |      17 |    4 |  125 |    5 |     5 |   15 |    0 |    0 |    8 |    1 |    3 |           2 |      4 |    2 |    0 |       0 |      0 |   32 |
|   19 | Headley   |  6 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   27 |    0 |    3 |           0 |      1 |    1 |    0 |       0 |      0 |   15 |
|   21 | Chandan.  |  7 |      18 |    0 |   32 |   10 |    41 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      1 |    3 |    1 |       0 |      0 |   10 |
|   23 | Martti.   | 10 |      27 |   11 | **154** | 3 |     2 | **20** |  1 |    1 |   26 |    0 |    1 |           0 |      5 |    3 |    1 |       0 |      0 | **45** |
|   26 | Eimilios. | 10 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   79 |    2 |    0 |           0 |      1 |    2 |    0 |       1 |      0 |    2 |
|   29 | Katina.   |  8 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    2 |   22 |    0 |    0 |           0 |      0 |    5 |    0 |       0 |      0 |    4 |
|   33 | Babar.    |  5 |       4 |    0 |   15 |    2 |     6 |    1 |    0 |    0 |    7 |    1 |    0 |           0 |      1 |    3 |    3 |       1 |      0 |    2 |
|   35 | Devika.   |  9 |       5 |    2 |   31 |    0 |     0 |    4 |    0 |    1 |   37 |    2 |    1 |           0 |      2 |    0 |    1 |       0 |      0 |   13 |
|   67 | Elisavet. |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   16 |    0 |    0 |           0 |      0 |    3 |    1 |   **2** |      R |    0 |
|   81 | Elvis.    |  7 |      30 |    0 |   77 |   18 | **76** |   2 |    0 |    0 |    2 |    0 |    0 |           2 |      2 |    2 |    0 |       0 |      1 |   18 |
|   88 | Leilani.  |  4 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    4 |    0 |    1 |           0 |      0 |    1 |    0 |       0 |      1 |    5 |
|   88 | Menachem. |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    1 |    0 |       0 |      1 |    0 |
|   89 | Alva.     |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   19 |    0 |    0 |           0 |      0 |    4 |    1 |       0 |      1 |    0 |
|   90 | Teresia.  |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      1 |    0 |

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Old Wyrms" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

**Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Souta   | Catcher  |   33 |    9 |   27 |   69 |   72 |   51 |    3 |    2 |    1 |    0 |    4 |  299 |
| Elvis   | Thrower  |   36 |    9 |   20 |   65 |    1 |  164 |    0 |    0 |    1 |    0 |    7 |  204 |
| **Amador**   | Catcher  |   32 |    8 |   16 |   56 |   32 |   44 |    2 |    2 |    0 |    0 |    5 |  173 |
| *Tony*   | Catcher | ?? | ?? | ?? | 33 | 39 | 9 | 2 | 2 | 0 | 0 | 4 | 154 |
| Babar   | Catcher  |   35 |    8 |   27 |   70 |   29 |   15 |    9 |    5 |    0 |    0 |    3 |  145 |
| **Seosamh**  | Catcher  |   16 |    7 |   10 |   33 |   32 |    3 |    2 |    2 |    1 |    0 |    3 |  124 |
| *Carl*   | Thrower | ?? | ?? | ?? | 54 | 2 | 97 | 0 | 1 | 0 | 0 | 3 | 120 |
| *Joey*   | Catcher | ?? | ?? | ?? | 31 | 23 | 21 | 3 | 2 | 1 | 0 | 2 | 112 |
| **Evander**  | Thrower  |   15 |    7 |   20 |   42 |    0 |   71 |    0 |    1 |    0 |    0 |    5 |   98 |
| *Ocho*   | Catcher | ?? | ?? | ?? | 22 | 17 | 9 | 5 | 1 | 0 | 0 | 4 | 94 |
| **Roni**     | Catcher  |   13 |    2 |    9 |   24 |   16 |   13 |    3 |    1 |    0 |    0 |    4 |   89 |
| *Hems*   | Thrower | ?? | ?? | ?? | 47 | 0 | 76 | 1 | 0 | 0 | 0 | 2 | 88 |
| **Kelemann** | Blitzer  |   25 |    8 |    9 |   42 |   12 |    5 |    2 |    5 |    1 |    0 |    6 |   87 |
| **Modest**   | Catcher  |   15 |    7 |    6 |   28 |   16 |    5 |    0 |    1 |    0 |    0 |    6 |   85 |
| *HoJu*   | Catcher | ?? | ?? | ?? | 29 | 18 | 15 | 3 | 0 | 0 | 0 | 2 | 85 |
| *Newb*   | Catcher | ?? | ?? | ?? | 22 | 22 | 6 | 0 | 0 | 0 | 0 | 2 | 82 |
| Moirin  | Catcher  |   13 |    6 |    6 |   25 |   14 |   11 |    2 |    0 |    0 |    0 |    4 |   77 |
| **Rati**     | Blitzer  |   28 |    6 |   16 |   50 |    9 |    4 |    0 |   10 |    3 |    1 |    2 |   69 |


```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Old Wyrms" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

Having the second-best player the UBBL has ever seen in [[souta]] has gone pretty well for the Wyrms. That she wasn't used in the GCIX final is one of the things BludBol fans will always have an opinion on. [[elvis]] has a long way to go to catch [[souta]]

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    2 | Evander | Thrower  |       5 |      1 | 240000 | 40000 |
|   17 | Roni    | Catcher  |       5 |      1 | 260000 | 30000 |
|   81 | Elvis.  | Thrower  |       8 |      2 | 210000 | 20000 |
|   83 | Joey.   | Catcher  |       5 |      1 | 250000 | 10000 |
|   83 | Newb.   | Catcher  |       2 |      1 | 190000 | 10000 |
|   84 | Souta.  | Catcher  |       8 |      3 | 260000 | 30000 |
|   84 | Tony.   | Catcher  |       5 |      1 | 250000 | 10000 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Old Wyrms" GROUP BY pl.name ORDER BY pl.nr ASC;
```

#### Cup Winners

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup X" AND pl.f_tname = "Old Wyrms" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup X" AND pl.f_tname = "Old Wyrms" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

* [[Kelemann]] - GCIX, GCX
* [[amador]] - GCIX, GCX
* [[Rati]] - GCIX, GCX
* [[elvis]] - GCIX, GCX
* [[Jia]] - GCIX, GCX
* [[Elisavet]] - GCIX, GCX
* [[moirin]] - GCIX (Final only), GCX
* [[babar]] - GCIX, GCX off playoff roster
* [[Andela]] - GCIX
* [[Martti]] - GCIX
* [[roni]] - GCIX
* [[Tereza]] - GCIX
* [[Lucius]] - GCIX
* [[Yasmani]] - GCIX (Final only)
* [[seosamh]] - GCIX off playoff roster, GCX
* [[Belmont]] - GCX
* [[Journee]] - GCX
* [[Katina]] - GCX
* [[Leilani]] - GCX
* [[Alva]] - GCX
* [[Menachem]] - GCX
* [[Teresia]] - GCX
* [[modest]] - GCIX off playoff roster, GCX

##### Team won but no rings

* Otakar - GCIX dead
* Lakshmana - GCIX dead
* Phette - GCIX dead
* Shelach - GCIX dead
* Maelys - GCIX off playoff roster
* Olaug - GCIX off playoff roster, GCX off playoff roster
* Eimilios - GCIX off playoff roster, GCX off playoff roster
* Zipfruder - GCIX off playoff roster, GCX off playoff roster
* Coluim - GCIX off playoff roster
* Ingolf - GCIX off playoff roster
* Manju - GCIX off playoff roster
* Vilma - GCIX off playoff roster
* Kasimir - GCX off playoff roster
* Souta - GCIX off Finals roster & did not receive ring

### Management

Hems is the son of an old-Era veteran thrower for the Wyrms. He has a ruthless approach to winning. His roster manipulation in the GCIX championship run made for new rules of only allowing 4 veterans in reserve in GCX, though those rules have since been relaxed again.

### Fans

As the winningest team in the UBBL, Wyrm fans can be among the most despised. From their end, however, the main rivalries are with the [Zensun Vagabonds](zensunvagabonds) as the two "Founders" of the UBBL, the [Irregular Cogs](irregularcogs) (mostly for historical grudges around the GCI and GCII seasons), and the [Gore Farmers](gorefarmers), who have won as many Green Cups in the modern era (and share the Stacks division with them).

### Famous Games

The match everyone would really like to see is the one at the end of the GCII regular season that made the Cogs/Wyrms rivalry so intense but the records have been lost.

The Green Cup X championship game against the [Ravenous Eagles](ravenouseagles) was pretty great.