# Ravenous Eagles

The Ravenous Eagles are often referred to as the Worst Green Cup Champions, which is all right with the Ossa ownership group as they flaunt their rings. 

## Playbook

The Eagles use the Charles Dorf playbook, which is built on a very rigid division of smash and grab labour. They use slow tacklers on the line to block off the centre, three strong blitzers and a fragile ball-handling corps (which is a faster group than the blockers, but comparatively slow across the league) to score just as much as is necessary.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Humbert  | Hobgoblin           |   93 |       7 |   45 |         3 | 170000 |     0 |
|    2 | Wanjiku  | Hobgoblin           |   33 |       5 |   32 |         2 | 110000 |     0 |
|    3 | Calixta  | Hobgoblin           |   44 |       5 |   30 |         2 | 110000 |     0 |
|    4 | Bates    | Hobgoblin           |   69 |       5 |   30 |         2 | 140000 |     0 |
|    5 | Chibueze | Chaos Dwarf Blocker |   25 |       3 |   17 |         1 | 120000 |     0 |
|    6 | Jonquil  | Chaos Dwarf Blocker |   46 |       5 |   53 |         4 | 140000 |     0 |
|    7 | Nedyalko | Chaos Dwarf Blocker |   31 |       5 |   20 |         1 | 150000 |     0 |
|    8 | Toma     | Chaos Dwarf Blocker |   37 |       7 |   75 |         5 | 140000 |     0 |
|    9 | Desponia | Chaos Dwarf Blocker |   24 |       5 |   36 |         2 | 140000 |     0 |
|   10 | Sanjana  | Chaos Dwarf Blocker |   43 |       7 |   66 |         4 | 130000 |     0 |
|   11 | Donato   | Hobgoblin           |   45 |       4 |   15 |         1 | 100000 |     0 |
|   14 | Chikondi | Bull Centaur        |   68 |       8 |   78 |         5 | 260000 | 50000 |
|   15 | Ekua     | Bull Centaur        |  140 |       9 |  102 |         7 | 320000 | 60000 |
|   16 | Percy    | Minotaur            |  117 |       5 |   47 |         3 | 310000 | 50000 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   17 | Rajendra | Bull Centaur        |   38 |       2 |   22 |         1 | 200000 |     0 |
|   18 | Jantine  | Minotaur            |  138 |       6 |   53 |         4 | 300000 | 50000 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   42 |          | Hobgoblin           |    7 |       1 |    3 |         0 |  60000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Ravenous Eagles" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```


| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Bates      | Line           |   Star |       4 |
| Leckerslie | Line           |    Experienced |       3 |
| Desponia   | Blocker |   Veteran |       4 |
| Jonquil    | Blocker |   Seasoned Veteran |       4 |
| Nedyalko   | Blocker |   Experienced |       4 |
| Petrona    | Blocker |    Rookie |       2 |
| Gemma      | Blocker |    Rookie |       2 |
| Sanjana    | Blocker |   Seasoned Veteran |       6 |
| Donato     | Kicker           |    Experienced |       3 |
| Niko       | Line           |   Star |       5 |
| Imaan      | Line           |   Experienced |       2 |
| Chikondi   | Blitzer        |   Star |       7 |
| Ekua       | Blitzer        |  Superstar |       8 |
| Jantine    | Heavy            |  Superstar |       5 |

### Bench

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Wanjiku    | Line           |   Veteran |       4 |
| Humbert    | Line           |   Superstar |       6 |
| Calixta    | Line           |   Seasoned Veteran |       4 |
| Toma       | Blocker |   Seasoned Veteran |       6 |
| Bahij      | Blocker |   Seasoned Veteran |       7 |
| Rajendra   | Blitzer        |   Veteran |       1 |
| Percy      | Heavy            |   Superstar |       4 |

## Records

### Record by Division 

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|

```
SELECT teams.name AS Team, divisions.name AS Division, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Ravenous Eagles" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

33-11-42

### UBBL Record (W-D-L)

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|


```
SELECT teams.name AS Team, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf) AS Cas, sum(mr.tcdiff) AS CasDiff, sum(mr.ff) AS Fans FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Ravenous Eagles" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```
45-12-47

### Prizes

* Green Cup VII - Green Cup Champions [[team1stplace#gcvii]] 
* Green Cup VII - Burger Conference Champions [[teamconference#gcvii]]
* Green Cup VII - Outlands Division Champions [[teamdivision#gcvii]]
* Green Cup IX - Iron Fist [[teamcasualties#gcix]]
* Green Cup V Memorial - Chartreuse Pop Bottle [[team1stplace]]
* Green Cup V Memorial - Crimson Soles [[teamcasualties]]
* Green Cup X - Classic Conference Champions [[team2ndplace#gcx]] & [[teamconference#gcx]]
* Green Cup X - Pits Division Champions [[teamdivision#gcx]]
* Green Cup X - Iron Fist [[teamcasualties#gcx]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Ravenous Eagles | UBBL Challenge       |    3 |    1 |    1 |      5 |      70.00 |    7 |    5 |    5 |     -2 |    0 |
| Ravenous Eagles | Green Cup V Memorial |    9 |    0 |    4 |     13 | 69.23 |   19 |   13 |   20 |     14 |    4 |
| Ravenous Eagles | **Green Cup VII**        |   11 |    2 |    6 |     19 | 63.16 |   31 |   25 |   40 |     27 |    4 |
| Ravenous Eagles | Green Cup X          |    8 |    4 |    7 |     19 | 52.63 |   29 |   26 |   61 |     34 |    1 |
| Ravenous Eagles | Green Cup VI         |    5 |    2 |    8 |     15 |      40.00 |   18 |   26 |   23 |     10 |    3 |
| Ravenous Eagles | Green Cup VIII       |    6 |    0 |   10 |     16 |    37.50 |   16 |   24 |   34 |     14 |   -4 |
| Ravenous Eagles | Green Cup IX         |    3 |    3 |   10 |     16 |  28.13 |   14 |   28 |   43 |     27 |   -4 |
| Ravenous Eagles | Champions Circuit    |    0 |    0 |    1 |      1 |       0.00 |    1 |    2 |    2 |      0 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Ravenous Eagles" ORDER BY mr.win_pct DESC limit 16;
```

## History

In the old-era B.R. Ossa was a player for another Charles Dorf team, the Black Pearl Pirates, that couldn't quite get enough wins together to break into the UBBL (that the [[Poets]] did get a crack at the Green Cup and did horribly was even more upsetting to Pirates fans). They were actually poised to enter the Green Cup V tournament, but the interruption happened and they were shut out.

After the interruption, B.R. Ossa didn't have enough clout to get his old players back together but their closeness to Green Cup glory was seen as a good storyline for the new-era Green Cup VI. He gathered a bunch of rookies and poised them to become the perfect mix of smash and grab. The only returning player he brought with him was [[twig]], but that gave them a more than competent QB to get them through the initial weeks with an eye towards renewal and balance. 

### Seasons

Green Cup VI didn't go exceedingly well for them as they were last-place in the Outlands division (not the entire 8-team league), but they only missed the playoffs by a win. The Eagles bashed the way they were supposed to with a third-place Casualty differential (10). But they could not score this season: last-place in TDs, both raw (18) and differential (-8). Ossa would need to see about adding some speed and dexterity to the team for next season.

In GCVII, the Eagles fought from third place in the Outlands division to win it (defeating the [Vagabonds](zensunvagabonds) and the [Filthy Tide](filthytide)). From there they became Burger Conference Champions by defeating the first-place overall [Irregular Cogs](irregularcogs) and eventually hoisted the Green Cup after a nasty match against the [Darkling Spectres](darklingspectres). 

Green Cup VIII was another last-place finish in the Outlands division (though their points total would have put them in second place if they were in the Heaps). 

With the new divisions in place in GCIX there was some thought teams bashy teams like the Eagles would be at a disadvantage. That seemed to be somewhat the case, but fans had a blast watching [[jantine]] mow through opposing teams. Their GCVII Championship meant that even being last in the Pits they weren't subject to relegation. Led by Jantine, they inflicted the most casualties 43 (28-12-3) en route to a last place finish in their division (after realignment this was now the Pits, feeding an intradivisional rivalry with the [Spectres](darklingspectres)) but they also stole the first Iron Fist from the [Orbital Machine](orbitalmachine) in the new era.

Outside the Pro Division the Eagles put together a wonderful GCV Memorial season with their retirees and rookies, then got it all together for an exciting final match. Sure this didn't mean anything but it's fun to win. The Eagles actually tied with the [Irregular Cogs](irregularcogs) for Casualties inflicted (20), but their casualty composition (11-5-4) meant they ended more careers and had a better differential (14) so they won the prize.

The Eagles then made some huge strides and in GCX their veterans got them within a whisker of another championship and secured their second Iron Fist in a row.

#### Projection GCXI

W-D-L 7-1-7

We've seen the Eagles make a dashing playoff run before, and with the Spectres seemingly rolling over for the season, the regular season might give the Eagles time to develop some support for their big 3 bashers.

#### summary GCXI

| Team            | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|-----------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Ravenous Eagles |     1 |       4 |    2 |   44 |    0 |        0 |      0 |          0 |    3 |     56 |     2 |    1 |   17 |           2 |           0 |
| Ravenous Eagles |     2 |       5 |    1 |   14 |    0 |        0 |      0 |          0 |    6 |     51 |     1 |    1 |   20 |           1 |           2 |
| Ravenous Eagles |     3 |       6 |    1 |   43 |    1 |        6 |      1 |          1 |    5 |     54 |     3 |    1 |   21 |           1 |           1 |
| Ravenous Eagles |     4 |       8 |    1 |   19 |    0 |        0 |      0 |          0 |    3 |     51 |     2 |    1 |   14 |           1 |           0 |
| Ravenous Eagles |     5 |       9 |    0 |   16 |    0 |        0 |      0 |          0 |    0 |     33 |     2 |    1 |    5 |           0 |           4 |
| Ravenous Eagles |     6 |       7 |    2 |   36 |    0 |        0 |      0 |          0 |    1 |     58 |     2 |    1 |   13 |           2 |           0 |
| Ravenous Eagles |     7 |       7 |    2 |   33 |    2 |       10 |      2 |          0 |    2 |     41 |     2 |    1 |   17 |           2 |           2 |
| Ravenous Eagles |     8 |       3 |    1 |   23 |    0 |        0 |      0 |          0 |    4 |     49 |     3 |    1 |   16 |           1 |           0 |
| Ravenous Eagles |     9 |       6 |    1 |   30 |    1 |        1 |      1 |          0 |    1 |     49 |     2 |    1 |   11 |           1 |           2 |
| Ravenous Eagles |    10 |       6 |    1 |   13 |    1 |        6 |      1 |          0 |    3 |     54 |     2 |    1 |   15 |           1 |           1 |
| Ravenous Eagles |    11 |       9 |    1 |   26 |    1 |        5 |      1 |          1 |    4 |     40 |     1 |    1 |   19 |           1 |           2 |
| Ravenous Eagles |    12 |       5 |    0 |   45 |    1 |        0 |      1 |          1 |    5 |     43 |     2 |    1 |   18 |           0 |           3 |
| Ravenous Eagles |    13 |       4 |    0 |   17 |    1 |        2 |      1 |          0 |    2 |     64 |     0 |    1 |   10 |           3 |           0 |
| Ravenous Eagles |    14 |       6 |    2 |   43 |    2 |        2 |      2 |          0 |    1 |     41 |     0 |    1 |   15 |           2 |           1 |
| Ravenous Eagles |    15 |      12 |    1 |   48 |    5 |       13 |      5 |          0 |    2 |     50 |     1 |    1 |   17 |           1 |           2 |
| Ravenous Eagles |   R16 |       9 |    0 |   26 |    2 |        5 |      2 |          1 |    3 |     58 |     3 |    1 |   15 |           1 |           0 |

```
SELECT pl.f_tname AS Team, mt.round, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP, mt.team1_score, mt.team2_score FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Ravenous Eagles" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster GCXI


| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    2 | Wanjiku     |  6 |      13 |    1 |   38 |    5 |     8 |    2 |    0 |    0 |    4 |    1 |    1 |           0 |      1 |    2 |    0 |       1 |      0 |   13 |
|    3 | Calixta.    |  6 |      12 |    2 |   37 |    1 |     0 |    8 |    0 |    0 |    5 |    2 |    1 |           0 |      1 |    0 |    0 |       1 |      0 |   12 |
|    4 | Bates.      |  6 |      14 |    2 |   88 |    5 |    11 |    1 |    0 |    0 |    5 |    0 |    0 |           0 |      4 |    2 |    0 |       0 |      0 |   11 |
|    5 | Chibueze    | 10 |       1 |    0 |    0 |    0 |     0 |    0 |    1 |    3 |   46 |    1 |    3 |           0 |      0 |    1 |    0 |       0 |      0 |   23 |
|    7 | Nedyalko.   | 11 |       1 |    0 |    2 |    0 |     0 |    0 |    1 |    2 |   44 |    1 |    3 |           0 |      0 |    0 |    1 |       0 |      0 |   21 |
|   11 | Donato.     | 10 |      20 |    6 |  105 |    2 |    10 |    2 |    0 |    1 |    6 |    1 |    3 |           1 |      3 |    2 |    2 |       0 |      0 |   37 |
|   14 | Chikondi    |  7 |       2 |    1 |   17 |    0 |     0 |    0 |    0 |    0 |   39 |    3 |    0 |           0 |      0 |    1 |    1 |       0 |      0 |    3 |
|   15 | Ekua.       | 16 |       3 |    1 |    2 |    0 |     0 |    1 |    0 |    5 |  105 |    8 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |   18 |
|   16 | Percy.      |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |   11 |   65 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |   22 |
|   17 | Rajendra    |  8 |       2 |    1 |   19 |    0 |     0 |    0 |    0 |    3 |   35 |    5 |    1 |           0 |      1 |    0 |    0 |       0 |      0 |   14 |
|   18 | Jantine.    | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |   11 |   94 |    1 |    0 |           0 |      0 |    2 |    0 |       0 |      0 |   22 |
|   22 | Leckerslie. |  9 |      23 |    2 |  101 |    2 |     7 |    2 |    0 |    1 |    3 |    0 |    0 |           1 |      8 |    5 |    1 |       0 |      0 |   10 |
|   27 | Petrona.    | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   41 |    0 |    2 |           0 |      0 |    2 |    1 |       1 |      0 |   12 |
|   29 | Gemma.      | 13 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   58 |    2 |    1 |           0 |      0 |    0 |    1 |       0 |      0 |    7 |
|   30 | Bahij.      |  5 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   21 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   31 | Imaan.      | 10 |       5 |    0 |   21 |    0 |     0 |    1 |    0 |    0 |   12 |    0 |    0 |           0 |      0 |    0 |    0 |       2 |      0 |    0 |
|   32 | Niko.       |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    3 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   61 | Humbert.    |  6 |       9 |    0 |   44 |    2 |    14 |    0 |    1 |    0 |    0 |    0 |    0 |           0 |      2 |    1 |    1 |       1 |      R |    4 |
|   66 | Jonquil.    | 16 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   70 |    3 |    0 |           0 |      0 |    1 |    1 |       0 |      R |    6 |
|   68 | Toma.       |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   26 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      R |    0 |
|   69 | Desponia.   | 12 |       1 |    0 |    2 |    0 |     0 |    0 |    1 |    1 |   66 |    0 |    0 |           0 |      0 |    0 |    0 |       1 |      R |    4 |
|   70 | Sanjana.    | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   44 |    0 |    0 |           0 |      0 |    0 |    1 |       1 |      R |    2 |



```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Ravenous Eagles" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Ekua     | Bull Centaur        |   38 |   16 |   48 |  102 |    9 |    0 |    1 |   27 |   13 |    3 |    5 |  140 |
| Jantine  | Minotaur            |   18 |   13 |   23 |   54 |    0 |    0 |    1 |   48 |   14 |    1 |    2 |  138 |
| Percy    | Minotaur            |   21 |    3 |   23 |   47 |    1 |    0 |    1 |   29 |   12 |    5 |    4 |  117 |
| Humbert  | Hobgoblin           |   15 |    9 |   21 |   45 |   12 |   36 |    2 |    1 |    0 |    0 |    3 |   93 |
| Frediano | Hobgoblin           |   17 |    4 |   17 |   38 |   13 |   20 |    1 |    1 |    0 |    0 |    3 |   78 |
| Bates    | Hobgoblin           |   10 |    6 |   14 |   30 |   16 |    9 |    0 |    1 |    0 |    0 |    2 |   69 |
| **Chikondi**  | Bull Centaur        |   31 |   11 |   36 |   78 |   10 |    0 |    2 |    4 |    2 |    1 |    4 |   68 |
| Niko     | Hobgoblin           |   12 |    9 |   17 |   38 |   12 |    1 |    0 |    3 |    0 |    0 |    5 |   68 |
| Viltaute | Hobgoblin           |   19 |    5 |   23 |   47 |   10 |   10 |    0 |    0 |    1 |    0 |    2 |   52 |
| Lumusi   | Chaos Dwarf Blocker |   34 |   10 |   38 |   82 |    0 |    1 |    1 |    6 |    3 |    1 |    5 |   48 |
| Jonquil  | Chaos Dwarf Blocker |   15 |   12 |   26 |   53 |    0 |    0 |    0 |    4 |    2 |    2 |    6 |   46 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Ravenous Eagles" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

[[jantine]] and [[percy]] have been the biggest stars of the Eagles, who haven't been trying to dominate as much as get into position to put a little run together like they did in GCVII. 

The Eagles have developed a lot of journeymen, especially in GCV, but their style of play doesn't leave a lot of room for the Line players to really develop into flashy stars.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|    9 | Desponia   | Chaos Dwarf Blocker |       5 |      1 | 140000 |     0 |
|   16 | Percy      | Minotaur            |       5 |      1 | 310000 | 50000 |
|   18 | Jantine    | Minotaur            |       6 |      3 | 300000 | 50000 |


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Ravenous Eagles" GROUP BY pl.name ORDER BY pl.nr ASC;
```

#### Cup Winners

* [[ekua]] VII
* [[chikondi]] VII
* [[Frediano]] VII
* [[Mahendra]] VII
* [[Percy]] VII
* [[Toma]] VII
* [[Bahij]] VII
* [[Dijana]] VII
* [[Lumusi]] VII
* [[Viltaute]] VII
* [[Shalev]] VII
* [[Warren]] VII
* [[Sigfrido]] VII
* [[Eliott]] VII
* [[twig]] VII
* [[Birgitta]] VII

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|

```
SELECT pl.nr AS "#", pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup VII" AND pl.f_tname = "Ravenous Eagles" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Management

While the B.R. Ossa ownership group has a former player as its face, the resources for the (increasingly well-funded) team are more nebulous in origin.

### Fans

Fans of the Ravenous Eagles glory in their championship titles and especially love getting in the faces of fans of the [Glorious Hounds](glorioushounds). Their loyalty has been fleeting since the GCVII championship though.

### Famous Games

Even in their Green Cup winning season the Ravenous Eagles haven't put up a lot of amazing matches. Their games tend to be built on hits hits and hits. Their winning GCVII season was built on inflicting 53.58 Blocks/match which was 6 more than their Pro division average (47.53). 

#### GCVII Conference Final

Their best match was probably the (GCVII Conference Final) where they pulled off the huge upset against the [Irregular Cogs](irregularcogs) [[gcvii-18-icre]].