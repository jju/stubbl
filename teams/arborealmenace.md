# Arboreal Menace

The Arboreal Menace are the newest entries for the Green Cup competition, having won the third UBBL Challenge for their shot in GCX. They are passers and speedsters and are part of the slow wave of skillifying Pro-Level UBBL.

## Playbook

The Arboreal Menace use the Wary Eagle playbook, which is very similar to the Scrying Avian technique, but with slightly higher skilled (and more expensive to replace) players. The lineup includes four catchers, two blitzers and throwers that have more of an option of holding back and letting fly once the catchers are in position. The heavy on a Wary Eagle team is much less mobile than on a Scrying Avian but provides an anchor for the line.

## Playbook

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Ingeborg | Thrower   |   52 |       3 |   25 |         2 | 180000 |     0 |
|    3 | Laurel   | Catcher   |  178 |       4 |   43 |         3 | 260000 | 30000 |
|    4 | Attilla  | Catcher   |   90 |       7 |   50 |         3 | 200000 |     0 |
|    5 | Vusala   | Wardancer |   34 |       1 |   16 |         1 | 200000 | 10000 |
|    6 | Sanja    | Wardancer |   79 |       7 |   46 |         3 | 240000 |     0 |
|    7 | Bishop   | Lineman   |   19 |       4 |   21 |         1 | 110000 |     0 |
|    8 | Chantrea | Lineman   |   40 |       7 |   52 |         3 | 170000 |     0 |
|    9 | Iago     | Lineman   |   20 |       7 |   50 |         3 | 140000 | 30000 |
|   10 | Joona    | Lineman   |   22 |       7 |   53 |         4 | 110000 |     0 |
|   14 | Georgina | Catcher   |  180 |       7 |   49 |         3 | 280000 | 30000 |
|   15 | Dawa     | Catcher   |   17 |       1 |   13 |         1 | 130000 |     0 |
|   16 | Borarinn | Treeman   |   56 |       5 |   47 |         3 | 200000 |     0 |


### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Arboreal Menace" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division (W-D-L)

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Arboreal Menace | Pro    |   17 |    4 |   13 |   34 |  55.208 |  107 |  105 |            38 |            -20 |         -2 |
| Arboreal Menace | Open   |   12 |    1 |    6 |   19 |  56.964 |   59 |   33 |            20 |            -13 |          6 |
| Arboreal Menace | Street |    1 |    0 |    0 |    1 | 100.000 |    3 |    0 |             2 |              2 |          1 |


```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Arboreal Menace" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Arboreal Menace |          30 |            5 |           19 |             54 |                   62.611 |        169 |        138 |            60 |            -31 |          5 |
```
SELECT teams.name, sum(mr.won), sum(mr.draw), sum(mr.lost), sum(mr.played), round(avg(mr.win_pct),3), sum(mr.gf), sum(mr.ga), sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Arboreal Menace" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* UBBL Challenge III - UBBL Pennant [[team1stplace]]
* Green Cup XI - Outlands Division Champions [[teamdivision#gcxi]]

### Seasons

| Team      | Season             | W | D | L | GP | Win% | GF | GA | Cas | CDif | FF |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Arboreal Menace | StUBBL Scramble    |    1 |    0 |    0 |      1 |     100.00 |    3 |    0 |    1 |      2 |    1 |
| Arboreal Menace | UBBL Challenge III |    6 |    1 |    0 |      7 | 92.86 |   30 |   14 |   10 |      3 |    2 |
| Arboreal Menace | UBBL Challenge IV  |    3 |    0 |    1 |      4 |      75.00 |   12 |    5 |    2 |     -5 |    3 |
| Arboreal Menace | Green Cup XI       |   11 |    2 |    5 |     18 | 66.6667 |   66 |   54 |   16 |     -5 |    1 |
| Arboreal Menace | UBBL Challenge II  |    3 |    0 |    2 |      5 |      60.00 |   14 |    7 |    6 |     -5 |    1 |
| Arboreal Menace | Green Cup X        |    6 |    2 |    8 |     16 |   43.75 |   41 |   51 |   15 |    -15 |   -3 |
| Arboreal Menace | UBBL Challenge     |    0 |    0 |    3 |      3 |       0.00 |    3 |    7 |    0 |     -6 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Arboreal Menace" ORDER BY mr.win_pct DESC limit 16;
```

## History

### Seasons

The Arboreal Menace began their existence with three straight losses in the first UBBL Challenge (against the [Mules](kickingmules.md), [Machine](orbitalmachine) and [Eagles](ravenouseagles)).

In UBBL Challenge II they did much better against the bruising style of play, getting to the Quarter-finals which they lost to the eventual tournament winners the [Gargantuan Brutes](gargantuanbrutes). They lost again to the [Mules](kickingmules.md) this season.

The Third UBBL Challenge was the Arboreal Menace's clear crowning achievement thus far. They won the entire tournament in undefeated fashion with a 6-win run after an opening match draw against the [Gladiolas](palaceorchids.md).

Coming into GCX on a high, the Menace won early, but couldn't keep things under control through a long season. They ended up in last place in the Outlands division (and would have needed to beat the eventual GCX champions in week 15 to have made the playoffs).

The fourth UBBL Challenge saw a return to form where they easily made the quarterfinals against Open Division competition but couldn't advance further.

#### Projection GCXI

W-D-L 8-1-6

Current projections have them battling the [Tatters](carcosantatters) for third place in the Outlands. They are bringing a more experienced roster into GCXI and it's possible they can hang in there with a very tough division.

#### summary last season

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Arboreal Menace |     1 |      22 |    5 |  111 |    8 |       39 |      8 |          0 |    0 |     36 |     0 |    1 |   28 |           6 |           5 |
| Arboreal Menace |     2 |       8 |    4 |   54 |    3 |       23 |      3 |          0 |    1 |     18 |     1 |    1 |   22 |           4 |           2 |
| Arboreal Menace |     3 |      11 |    4 |   64 |    4 |       23 |      4 |          1 |    1 |     25 |     1 |    1 |   25 |           2 |           4 |
| Arboreal Menace |     4 |      19 |    4 |  101 |    5 |       13 |      5 |          0 |    0 |     25 |     1 |    1 |   22 |           4 |           7 |
| Arboreal Menace |     5 |      12 |    5 |   73 |    5 |       22 |      5 |          0 |    1 |     26 |     1 |    1 |   27 |           5 |           3 |
| Arboreal Menace |     6 |      18 |    6 |  115 |    6 |        9 |      6 |          1 |    1 |     33 |     2 |    1 |   33 |           5 |           6 |
| Arboreal Menace |     7 |       5 |    2 |   34 |    2 |        9 |      2 |          0 |    1 |     16 |     3 |    1 |   15 |           2 |           2 |
| Arboreal Menace |     8 |       9 |    4 |   68 |    3 |       10 |      3 |          0 |    0 |     23 |     1 |    1 |   20 |           6 |           4 |
| Arboreal Menace |     9 |      12 |    3 |   41 |    5 |       42 |      5 |          0 |    1 |     37 |     3 |    1 |   21 |           3 |           2 |
| Arboreal Menace |    10 |      11 |    4 |   53 |    4 |       16 |      4 |          2 |    2 |     38 |     1 |    1 |   29 |           2 |           4 |
| Arboreal Menace |    11 |      10 |    3 |   74 |    4 |       15 |      4 |          0 |    0 |     22 |     0 |    1 |   18 |           3 |           3 |
| Arboreal Menace |    12 |      15 |    6 |   90 |    5 |        4 |      5 |          1 |    2 |     24 |     1 |    1 |   34 |           0 |           6 |
| Arboreal Menace |    13 |      11 |    3 |   81 |    4 |       13 |      4 |          0 |    1 |     29 |     3 |    1 |   20 |           3 |           4 |
| Arboreal Menace |    14 |      10 |    3 |   43 |    4 |       29 |      4 |          0 |    1 |     25 |     1 |    1 |   20 |           1 |           3 |
| Arboreal Menace |    15 |      16 |    3 |   65 |    5 |       13 |      5 |          0 |    2 |     22 |     1 |    1 |   23 |           3 |           2 |
| Arboreal Menace |   BYE |       0 |    0 |    0 |    0 |        0 |      0 |          0 |    0 |      0 |     0 |    2 |   10 |           1 |           0 |
| Arboreal Menace |    QF |      11 |    3 |   64 |    3 |       10 |      3 |          1 |    1 |     22 |     0 |    1 |   21 |           3 |           2 |
| Arboreal Menace |    SF |      16 |    3 |   75 |    4 |        6 |      4 |          1 |    1 |     29 |     1 |    2 |   27 |           5 |           3 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Arboreal Menace" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster by season


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Ingeborg   | 17 |  **64** |    0 |  139 |   38 |   152 |    0 |    1 |    0 |    5 |    1 |    0 |           3 |      2 |    4 |    1 |       1 |      0 |   40 |
|    3 | Laurel     | 18 |      48 |   34 |  519 |    0 |     0 |   42 |    1 |    0 |    1 |    0 |    1 |           0 |      0 |    2 |    2 |       0 |      0 |  **109** |
|    4 | Attilla    | 15 |       7 |    5 |   78 |    4 |     8 |    3 |    0 |    0 |    1 |    0 |    2 |           0 |      0 |    0 |    0 |       1 |      0 |   29 |
|    5 | Vusala     | 16 |       5 |    4 |   20 |    0 |     0 |    1 |    0 |    1 |   56 |    1 |    4 |           0 |      0 |    5 |    1 |       1 |      0 |   34 |
|    6 | Sanja      | 13 |       7 |    2 |   22 |    0 |     0 |    0 |    1 |    1 |   70 |    4 |    1 |           1 |      1 |    7 |    1 |       1 |      0 |   15 |
|    7 | Bishop     | 16 |       2 |    0 |    4 |    0 |     0 |    0 |    0 |    2 |   40 |    2 |    3 |           0 |      0 |    3 |    1 |       1 |      0 |   19 |
|    8 | Chantrea   | 17 |       2 |    0 |    4 |    0 |     0 |    0 |    0 |    4 |   60 |    4 |    0 |           0 |      2 |    4 |    1 |       1 |      0 |    8 |
|    9 | Iago       | 17 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   21 |    1 |    0 |           0 |      0 |    4 |    1 |       1 |      0 |    0 |
|   10 | Joona      | 18 |       2 |    1 |   17 |    0 |     0 |    1 |    0 |    0 |   41 |    1 |    0 |           0 |      0 |    4 |    3 |       0 |      0 |    3 |
|   14 | Georgina   | 16 |      27 |   10 |  174 |    3 |    16 |   13 |    3 |    0 |    8 |    0 |    2 |           0 |      4 |    4 |    2 |       0 |      0 |   49 |
|   15 | Dawa       | 13 |      10 |    4 |   58 |    0 |     0 |    7 |    0 |    0 |   10 |    2 |    1 |           0 |      2 |    3 |    0 |       0 |      0 |   17 |
|   16 | Borarinn   | 18 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    6 |   69 |    0 |    2 |           0 |      0 |    1 |    1 |       0 |      0 |   22 |
|   71 | Priyanka.  | 18 |       3 |    0 |    3 |    2 |     3 |    1 |    1 |    0 |   12 |    2 |    1 |           0 |      0 |    2 |    1 |       0 |      R |    9 |
|   73 | Unnr.      | 12 |       2 |    0 |   13 |    1 |     1 |    1 |    0 |    0 |   16 |    1 |    0 |           0 |      1 |    3 |    1 |       0 |      R |    1 |
|   82 | Susila.    |  7 |      30 |    0 |   96 |   26 |   116 |    0 |    0 |    0 |    7 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      1 |   31 |
|   85 | Nitika.    |  5 |       7 |    4 |   51 |    0 |     0 |    5 |    0 |    0 |    9 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |   12 |
|   86 | Kropotkin. |  6 |       0 |    1 |    8 |    0 |     0 |    0 |    0 |    2 |   24 |    2 |    2 |           0 |      0 |    2 |    0 |       0 |      1 |   17 |


```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Arboreal Menace" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Georgina**   | Catcher   |   26 |    4 |   19 |   49 |   39 |   12 |   13 |    0 |    0 |    0 |    5 |  180 |
| **Laurel**     | Catcher   |   25 |    4 |   14 |   43 |   53 |    0 |    2 |    0 |    0 |    0 |    3 |  178 |
| **Attilla**    | Catcher   |   27 |    5 |   18 |   50 |   21 |   10 |    0 |    0 |    1 |    0 |    3 |   90 |
| Hartwin   | Thrower   |   13 |    3 |    9 |   25 |    0 |   65 |    2 |    0 |    1 |    0 |    2 |   81 |
| **Sanja**      | Wardancer |   25 |    3 |   18 |   46 |   15 |    2 |    1 |    1 |    4 |    0 |    4 |   79 |
| Kropotkin | Wardancer |   21 |    4 |   13 |   38 |    8 |    2 |    1 |    5 |    4 |    0 |    6 |   76 |
| Susila    | Thrower   |   11 |    3 |   11 |   25 |    0 |   53 |    0 |    1 |    0 |    0 |    3 |   70 |
| Nitika    | Catcher   |   13 |    2 |   11 |   26 |   20 |    2 |    1 |    0 |    0 |    0 |    1 |   69 |
| **Borarinn**   | Treeman   |   27 |    5 |   15 |   47 |    0 |    0 |    0 |   14 |    2 |    2 |    4 |   56 |
| **Ingeborg**   | Thrower   |   15 |    2 |    8 |   25 |    0 |   45 |    1 |    0 |    0 |    0 |    1 |   52 |
| **Chantrea**   | Lineman   |   29 |    4 |   19 |   52 |    1 |    0 |    0 |    5 |    1 |    0 |    5 |   40 |



```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Arboreal Menace" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

[[georgina]] won the StUBBL Jumper for UBBL Challenge III. They have amazingly soft hands and there are a few rumblings that they're gunning for the Pro Interception record.

[[Hartwin]] was primarily a backfield passer, though she had the arm for it, she didn't go the extreme long-passing route of a [[yosif]] or the deceased [[Adam]] (or [[Ozymandias]] for the old school). The anticipation that in the Green Cup she'd need a backup did come true, and [[susila]] is now working his way up the skill tree.

[[laurel]] and [[Attilla]] are both remarkably good catchers but neither has made themselves part of the larger superstar picture in their first Green Cup campaign.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|   14 | Georgina | Catcher  |       7 |      1 | 280000 | 30000 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Arboreal Menace" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

Criton Corp is an upspire entity.

### Fans

As the Arboreal Menace have only completed their first Pro-Level season they don't have a lot of long-standing rivalries. Among Open-Level teams they bumped heads most with [Thorns](thorns) fans. In the Green Cup their natural rivals are the [Badger Claws](badgerclaws), who not only share their division (and use a similar fragile speedster playbook), but are also upstarts who've been promoted from Open-Division play and are eager to be the first to win the coveted Cup.

### Famous Games

None yet.