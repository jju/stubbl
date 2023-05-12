# Gore Farmers

When the Gore Farmers are good they can be very good, as evidenced by their two Green Cup wins in the modern era. But they can also be really bad, which has led to relegation and terrible seasons and an overall record below .500.

## Playbook

The Orville-Crush approach to BludBol is traditional, simple, but also somewhat arcane. A team can use 4 strong slow and unskilled linemen, 4 faster attacking blitzers, 2 dedicated ball-handlers, 4 weak slow receivers and a nigh-unlimited supply of tough fodder. The basic idea is to get a ball handler into a cage and grind out a 2-1 win, but there are more options for the team that wishes to develop them. The Gore Farmers, for instance, *mostly* eschew the Big Guy approach.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Ros        | Thrower |  Star |       3 |   30 |         2 | 170000 | 20000 |
|    3 | Aemulus    | Blitzer |  Superstar |       3 |   36 |         2 | 230000 | 20000 |
|    4 | Nuru       | Catcher |  Superstar |       5 |   39 |         3 | 180000 | 30000 |
|    5 | Elric      | Blitzer |   Star |       3 |   32 |         2 | 170000 |     0 |
|    6 | Beitris    | Blitzer |   Star |       4 |   39 |         3 | 160000 |     0 |
|    7 | Eloi       | Blocker |   Star |       3 |   41 |         3 | 170000 |     0 |
|    8 | Pasquale   | Blocker |   Seasoned Veteran|       3 |   39 |         3 | 140000 |     0 |
|    9 | RockLobber | Blocker |  Superstar |       6 |   65 |         4 | 220000 | 40000 |
|   10 | Emil       | Blocker |   Star |       5 |   41 |         3 | 170000 |     0 |
|   12 | Johann     | Line    |  Emerging Star |       2 |   10 |         1 | 140000 |     0 |
|   13 | Mashee     | Catcher |  Superstar |       8 |   62 |         4 | 170000 |     0 |
|   15 | Sylvester  | Blitzer |  Seasoned Veteran |       4 |   35 |         2 | 140000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   16 | Aethelraed | Blitzer | Seasoned Veteran |       4 |   38 |         3 | 140000 |     0 |
|   17 | Sanel      | Blocker | Experienced |       3 |   11 |         1 | 100000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   18 | GrimThrasher.  | Blocker |   59 |       5 |   59 |         4 | 160000 |     0 |
|   19 | Belenus.       | Blocker |   47 |       3 |   24 |         2 | 160000 | 20000 |
|   20 | Regulo.        | Blocker |   19 |       2 |   21 |         1 | 120000 |     0 |
|   25 | BeardPuller.   | Blitzer           |   38 |       5 |   50 |         3 | 170000 | 30000 |
|   27 | TallHexer.     | Blocker |   53 |       4 |   55 |         4 | 200000 | 40000 |
|   28 | Reagan.        | Line           |   16 |       3 |   12 |         1 | 130000 |     0 |
|   29 | Sloane.        | Blocker |    0 |       1 |    1 |         0 |  80000 |     0 |
|   29 | Vaso.          | Blocker |   19 |       3 |   16 |         1 | 130000 |     0 |
|   30 | Roze.          | Line    |    7 |       1 |    2 |         0 |  70000 |     0 |
|   31 | Casimiro.      | Line    |    7 |       2 |    3 |         0 |  70000 |     0 |
|   31 | Nikola.        | Line    |    0 |       2 |   13 |         1 |  50000 |     0 |
|   32 | Nimrod.        | Line    |    7 |       2 |    8 |         1 | 100000 |     0 |
|   32 | Bent.          | Catcher |   32 |       4 |   27 |         2 | 120000 |     0 |
|   33 | Aelfgifu.      | Catcher |   10 |       4 |   17 |         1 |  60000 |     0 |
|   34 | Londyn.        | Catcher |   15 |       2 |    7 |         0 |  60000 |     0 |
|   34 | Eulaylia.      | Line    |   16 |       6 |   35 |         2 | 100000 |     0 |
|   34 | Otieno.        | Line    |    8 |       2 |    7 |         0 |  70000 |     0 |
|   35 | HobNailer.     | Line    |   16 |       3 |   21 |         1 |  90000 |     0 |
|   35 | StoneLicker.   | Blitzer |   52 |       4 |   37 |         2 | 160000 |     0 |
|   41 | Gotthold.      | Line    |    6 |       1 |    2 |         0 |  70000 |     0 |
|   42 | Rayner.        | Line    |    7 |       1 |    3 |         0 |  70000 |     0 |
|   44 | Kamakshi.      | Line    |    6 |       1 |    1 |         0 |  70000 |     0 |
|   45 | Yasar.         | Line    |    6 |       1 |    1 |         0 | 100000 |     0 |
|   46 | Honza.         | Line    |   10 |       2 |    8 |         1 |  80000 |     0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Gore Farmers" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division

| Team            | Division | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|----------|------|------|------|------|--------|------|------|------|---------|------|
| Gore Farmers    | Pro      |   52 |   19 |   62 |  133 | 46.093 |  206 |  244 |           262 |            128 |         -2 |
| Gore Farmers    | Street   |    3 |    5 |    3 |   11 | 50.000 |   11 |   14 |            20 |              5 |          1 |
| Gore Farmers    | Open     |    2 |    0 |    4 |    6 | 25.000 |    9 |   14 |             8 |             -2 |          1 |

```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, Round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gore Farmers" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

### UBBL Record (W-D-L)

| Team            | W    | D    | L    | GP   | Win%   | GF   | GA   | Cas  | CasDiff | Fans |
|-----------------|-----:|-----:|-----:|-----:|-------:|-----:|-----:|-----:|--------:|-----:|
| Gore Farmers |      57 |   24 |   69 |  150 | 42.903 |  226 |  272 |  290 |     131 |    0 |


```
SELECT teams.name, sum(mr.won), sum(mr.draw), sum(mr.lost), sum(mr.played), Round(avg(mr.win_pct),3) AS "Win%", sum(mr.gf), sum(mr.ga), sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gore Farmers" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```

### Prizes

* Green Cup IV - Tough Brake of Alsoran [[team3rdplace#gciv]]
* Green Cup VI - Green Cup Champions [[team1stplace#gcvi]]
* Green Cup VI - Stacks Champions [[teamdivision#gcvi]]
* Green Cup VIII - Green Cup Champions [[team1stplace#gcviii]]
* Green Cup VIII - Burger Conference Champions [[teamconference#gcviii]]
* Green Cup VIII - Stacks Division Champions [[teamdivision#gcviii]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Gore Farmers | Green Cup IV         |    7 |    2 |    2 |     11 | 72.7273 |   22 |   13 |   28 |     21 |    3 |
| Gore Farmers | **Green Cup VI**     |   10 |    3 |    4 |     17 | 67.6471 |   27 |   25 |   25 |     14 |    3 |
| Gore Farmers | **Green Cup VIII**   |   11 |    3 |    5 |     19 | 65.7895 |   36 |   23 |   42 |     24 |    1 |
| Gore Farmers | UBBL Challenge       |    2 |    0 |    2 |      4 |      50 |    7 |    8 |    7 |     -2 |    2 |
| Gore Farmers | Green Cup III        |    5 |    1 |    5 |     11 |      50 |   16 |   17 |   32 |     20 |   -1 |
| Gore Farmers | Green Cup V Memorial |    3 |    5 |    3 |     11 |      50 |   11 |   14 |   15 |      5 |    1 |
| Gore Farmers | Green Cup X          |    6 |    2 |    9 |     17 | 41.1765 |   30 |   35 |   32 |     15 |    2 |
| Gore Farmers | Green Cup XI         |    5 |    2 |    9 |     16 |    37.5 |   24 |   35 |   28 |     19 |   -1 |
| Gore Farmers | Green Cup VII        |    5 |    0 |   11 |     16 |   31.25 |   22 |   40 |   24 |     -9 |   -2 |
| Gore Farmers | Green Cup I          |    2 |    2 |    6 |     10 |      30 |   12 |   22 |   18 |     10 |   -1 |
| Gore Farmers | Green Cup IX         |    1 |    4 |   11 |     16 |   18.75 |   17 |   34 |   28 |     14 |   -6 |
| Gore Farmers | UBBL Challenge IV    |    0 |    0 |    2 |      2 |       0 |    2 |    6 |    3 |      0 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gore Farmers" ORDER BY mr.win_pct DESC limit 16;
```

## History

### Seasons

The Gore Farmers were the first team to be relegated in the old-era UBBL after a terrible inaugural season. When they came back they were better, and in GCIV they only had 2 losses. It was a shame the second came in the quarterfinals. [[Spleen Hucker]] was a thrower in that Old-Era incarnation and was the person tagged to lead the team's name to glory, which only came in the new era, winning the first modern (somewhat disputed) Green Cup in GCVI.

They followed up their first championship with a lousy GCVII, but then in GCVIII the Gore Farmers played solid defensive caging BludBol to win: the Stacks Division facing [a mad-scoring threat](filthytide) in the first round, the Burger Conference against [a defensive powerhouse](carcosantatters) and the Green Cup itself against [a very young and healthy mad-scoring threat](badgerclaws). They're the first renaissance era multiple champions and did it by playing their game.

Sadly for lovers of pure competition, Spleen Hucker was also one of the first to really jump on the "tanking in a lost season" strategy, making their bad seasons (like GCIX) really bad and leaving them as a .500 team overall despite being multiple champions.

In GCX they played for the Stacks championship but lost to the [Old Wyrms](oldwyrms). They did avoid the charge of tanking and played competitive BludBol throughout the season.

#### GCXI Projection

W-D-L 7-0-8 

The Gore Farmers have a decent payroll going into the GCXI season, bringing back as many veterans as they had relatively healthy. Their fortunes are a crapshoot but they don't have any obvious deficiencies that need plugging. The biggest problem may be in finding the funds to develop rookies, but so far they don't seem too worried.

#### summary GCXI

The Gore Farmers had an okay season, coming in second in the Stacks during the regular season and hosting a playoff game. They didn't have a good day against the Wyrms in the round of 16 and were sent home, not to win another championship.

| Team         | round | Touches | TDs  | Rush | Cp   | PassDist | Caught | Intercepts | Cas  | Blocks | Sacks | MVPs | SPP  |  Location | WDL |
|--------------|-------|---------|------|------|------|----------|--------|------------|------|--------|-------|------|------|-------------|-------------|
| Gore Farmers |     1 |       6 |    2 |   35 |    1 |        5 |      1 |          0 |    2 |     47 |     1 |    1 |   16 |           1 |           2 |
| Gore Farmers |     2 |      13 |    1 |   51 |    4 |       11 |      4 |          0 |    0 |     54 |     0 |    1 |   12 |           1 |           5 |
| Gore Farmers |     3 |      13 |    2 |   61 |    3 |        4 |      3 |          0 |    1 |     59 |     2 |    1 |   16 |           2 |           1 |
| Gore Farmers |     4 |      11 |    0 |   22 |    0 |        0 |      0 |          1 |    0 |     36 |     0 |    1 |    7 |           1 |           0 |
| Gore Farmers |     5 |      11 |    2 |   41 |    4 |        2 |      4 |          0 |    3 |     38 |     1 |    1 |   21 |           2 |           2 |
| Gore Farmers |     6 |      13 |    3 |   53 |    4 |        9 |      4 |          0 |    5 |     50 |     0 |    1 |   28 |           4 |           3 |
| Gore Farmers |     7 |      10 |    1 |   31 |    2 |       11 |      2 |          0 |    2 |     50 |     1 |    1 |   14 |           3 |           1 |
| Gore Farmers |     8 |       8 |    1 |   30 |    1 |        6 |      1 |          0 |    1 |     36 |     1 |    1 |   11 |           1 |           0 |
| Gore Farmers |     9 |       5 |    3 |   40 |    1 |        0 |      1 |          0 |    3 |     55 |     0 |    1 |   21 |           3 |           0 |
| Gore Farmers |    10 |       3 |    0 |   14 |    0 |        0 |      0 |          0 |    0 |     34 |     0 |    1 |    5 |           3 |           0 |
| Gore Farmers |    11 |      15 |    2 |   61 |    4 |       16 |      4 |          1 |    2 |     46 |     0 |    1 |   21 |           2 |           2 |
| Gore Farmers |    12 |       7 |    1 |   17 |    1 |        2 |      1 |          0 |    5 |     45 |     3 |    1 |   19 |           1 |           3 |
| Gore Farmers |    13 |       3 |    1 |   25 |    1 |        3 |      1 |          0 |    0 |     47 |     0 |    1 |    9 |           3 |           1 |
| Gore Farmers |    14 |       3 |    2 |   37 |    0 |        0 |      0 |          0 |    0 |     24 |     1 |    1 |   11 |           2 |           1 |
| Gore Farmers |    15 |       9 |    2 |   42 |    3 |        7 |      3 |          0 |    2 |     28 |     2 |    1 |   18 |           3 |           2 |
| Gore Farmers |   R16 |       7 |    1 |   25 |    3 |        9 |      3 |          1 |    2 |     63 |     1 |    1 |   17 |           1 |           3 |

```
SELECT pl.f_tname AS Team, mt.round, CASE WHEN mt.team1_id = md.f_team_id THEN "Home" ELSE "Away" END AS Location, CASE WHEN mt.team1_score - mt.team2_score > 0 AND mt.team1_id = md.f_team_id THEN "Win" WHEN mt.team2_score - mt.team1_score > 0 AND mt.team2_id = md.f_team_id THEN "Win" WHEN mt.team1_score = mt.team2_score THEN "Draw" ELSE "Loss" END AS Result, mt.team1_score AS Home, mt.team2_score AS Away, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 29 AND pl.f_tname = "Gore Farmers" GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;
```

#### roster GCXI

The Gore Farmers ran out a **lot** of rookies (who were subsequently released from their contracts) after they clinched a playoff spot. 

Mashee played illegally in the first round of the playoffs, not having played in 5 regular season matches.

| #    | Player     | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|------------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    1 | Ros         |  9 |      22 |    0 |   54 |   13 |    20 |    2 |    0 |    0 |   11 |    0 |    0 |           4 |      3 |    1 |    0 |       1 |      0 |   13 |
|    3 | Aemulus     | 10 |      16 |    8 |   86 |    2 |    15 |   10 |    0 |    2 |   31 |    1 |    0 |           0 |      3 |    0 |    0 |       0 |      0 |   30 |
|    4 | Nuru        |  6 |      13 |    3 |   61 |    0 |     0 |    5 |    0 |    0 |    2 |    1 |    1 |           0 |      0 |    1 |    0 |       0 |      0 |   14 |
|    5 | Elric       |  9 |       4 |    2 |   14 |    1 |     1 |    4 |    0 |    4 |   51 |    0 |    1 |           0 |      1 |    0 |    1 |       1 |      0 |   20 |
|    6 | Beitris     | 10 |       2 |    0 |   12 |    0 |     0 |    1 |    0 |    5 |   67 |    2 |    1 |           0 |      2 |    2 |    0 |       0 |      0 |   15 |
|    7 | Eloi        | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   70 |    0 |    2 |           0 |      0 |    1 |    1 |       0 |      0 |   16 |
|    8 | Pasquale    | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   71 |    0 |    0 |           0 |      0 |    0 |    1 |       1 |      0 |    0 |
|    9 | RockLobber  |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    4 |   52 |    1 |    1 |           0 |      0 |    0 |    1 |       0 |      0 |   13 |
|   10 | Emil        |  7 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   50 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    5 |
|   12 | Johann      |  8 |      22 |    4 |   87 |    6 |    21 |    3 |    1 |    0 |    5 |    0 |    1 |           2 |      6 |    3 |    0 |       0 |      0 |   25 |
|   13 | Mashee      |  1 |       2 |    0 |   11 |    1 |     5 |    2 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    1 |
|   15 | Sylvester   |  7 |       3 |    1 |   14 |    0 |     0 |    1 |    0 |    1 |   36 |    0 |    0 |           0 |      0 |    3 |    0 |       0 |      0 |    5 |
|   16 | Aethelraed  |  5 |       1 |    1 |    7 |    0 |     0 |    0 |    1 |    3 |   19 |    3 |    1 |           0 |      0 |    1 |    0 |       1 |      0 |   16 |
|   17 | Sanel       |  6 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   35 |    1 |    2 |           0 |      0 |    1 |    0 |       0 |      0 |   12 |
|   28 | Reagan.     |  6 |       6 |    1 |   28 |    0 |     0 |    1 |    0 |    0 |   13 |    0 |    1 |           1 |      2 |    1 |    1 |       0 |      0 |    8 |
|   29 | Vaso.       | 12 |       0 |    1 |   14 |    0 |     0 |    0 |    0 |    1 |   68 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |   10 |
|   30 | Roze.       |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |    4 |    0 |    1 |           0 |      0 |    0 |    0 |       1 |      0 |    7 |
|   31 | Nikola.     |  6 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    0 |    0 |           0 |      0 |    3 |    1 |       0 |      0 |    0 |
|   31 | Casimiro.   |  1 |       2 |    0 |    6 |    1 |     3 |    0 |    0 |    0 |    1 |    0 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    6 |
|   32 | Nimrod.     |  4 |       6 |    1 |   34 |    2 |     4 |    0 |    0 |    1 |    8 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    7 |
|   34 | Eulaylia.   |  5 |       1 |    0 |    3 |    0 |     0 |    0 |    0 |    0 |    3 |    0 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    0 |
|   34 | Otieno.     |  5 |       5 |    2 |   26 |    0 |     0 |    1 |    0 |    1 |    8 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    8 |
|   62 | SkyTripper. |  7 |      26 |    0 |  104 |    5 |    12 |    0 |    1 |    1 |   12 |    0 |    0 |           0 |      2 |    1 |    1 |       0 |      0 |    9 |
|   71 | Helmuth.    | 10 |       4 |    0 |   19 |    1 |     4 |    2 |    0 |    0 |   26 |    2 |    1 |           0 |      0 |    0 |    0 |       0 |      0 |    6 |
|   85 | Fang.       |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   11 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   97 | Micha.      |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   98 | Reenie.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|   98 | Erato.      |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   98 | Gabriela.   |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   98 | Paulius.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    1 |    0 |           0 |      0 |    0 |    1 |       0 |      0 |    0 |
|   99 | Karinna.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Marcelino.  |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    0 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      1 |    0 |
|   99 | Ignacy.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Baptist.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    5 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Yuliya.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    7 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Sunta.      |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Kamaria.    |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Charlotte.  |  1 |       1 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Richa.      |  1 |       0 |    0 |    5 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Walter.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    3 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Vibiana.    |  3 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    6 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Viktor.     |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    6 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|   99 | Aquilina.   |  1 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    2 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |


```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| KneeMasher   | Blitzer           |   26 |    7 |   19 |   52 |   31 |   10 |    8 |    5 |    0 |    0 |    2 |  139 |
| *AxeEater*    | Blitzer | ?? | ?? | ?? | 50 | 24 | 2 | 0 | 12 | 3 | 0 | 2 | 114 |
| **Aemulus**       | Blitzer           |   11 |    7 |   18 |   36 |   24 |    8 |    2 |    2 |    1 |    1 |    3 |  107 |
| SkyTripper   | Thrower           |   25 |    6 |   30 |   61 |    4 |   61 |    2 |    1 |    0 |    0 |    4 |   99 |
| **Mashee**        | Catcher            |   27 |    5 |   30 |   62 |   21 |    2 |    3 |    0 |    0 |    0 |    3 |   86 |
| *GutTwister*  | Thrower | ?? | ?? | ?? | 53 | 13 | 18 | 0 | 4 | 0 | 0 | 4 | 85 |
| *SpleenHucker* | Thrower | ?? | ?? | ?? | 45 | 11 | 23 | 0 | 1 | 1 | 0 | 4 | 80 |
| **Nuru**          | Catcher            |   14 |    5 |   20 |   39 |   18 |    1 |    0 |    0 |    0 |    0 |    5 |   80 |
| **RockLobber**    | Blocker |   25 |    6 |   34 |   65 |    0 |    0 |    1 |   15 |    6 |    1 |    6 |   76 |
| KnuckleBiter | Thrower           |   15 |    5 |   15 |   35 |    5 |   45 |    1 |    1 |    0 |    0 |    1 |   69 |
| **Ros**           | Thrower           |   11 |    4 |   15 |   30 |    2 |   46 |    0 |    1 |    0 |    1 |    2 |   66 |
| GrimThrasher | Blocker |   28 |    6 |   25 |   59 |    0 |    0 |    0 |    5 |    9 |    3 |    5 |   59 |
| **Beitris**       | Blitzer           |   11 |    5 |   23 |   39 |    3 |    1 |    0 |    6 |    4 |    2 |    4 |   54 |
| TallHexer    | Blocker |   27 |    6 |   22 |   55 |    1 |    0 |    0 |    5 |    0 |    0 |    8 |   53 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

That the Gore Farmers have won two modern-era Green Cups with so few legitimate superstars is an impressive testament to the power of a solid line and the traditional caging methods of play. [[guttwister]] retired after GCVI as a veteran of the old-era UBBL. He says he was glad to get a ring, but felt sidelined despite his abilities.

The current star is [[aemulus]] who provides a fine alternative to [[Mashee]] as a scoring threat from outside the cage.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|
|   19 | Belenus  | Blocker  |       3 |      1 | 160000 | 20000 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Gore Farmers" GROUP BY pl.name ORDER BY pl.nr ASC;
```

#### Cup Winners

* [[kneemasher]] VI, VIII
* [[beardpuller]] VI, VIII
* [[GrimThrasher]] VI, VIII
* [[ToothGrinder]] VI, VIII
* [[TallHexer]] VI, VIII
* [[SpaceFiller]] VI, VIII
* [[guttwister]] VI
* [[KnuckleBiter]] VI
* [[mashee]] VI
* [[stonelicker]] VI
* [[RibCracker]] VI
* [[TuskOfGruumsh]] VI
* [[CakeStomper]] VI
* [[HobNailer]] VI
* [[JunkKicker]] VI
* [[skytripper]] VIII
* [[RockLobber]] VIII
* [[Elric]] VIII
* [[Fang]] VIII
* [[belenus]] VIII
* [[Nuru]] VIII
* [[TinyDancer]] VIII
* [[Eulaylia]] VIII
* [[Helmuth]] VIII

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup VI" AND pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup VIII" AND pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Tactics

As noted above, the Gore Farmers play a traditional bashing, caging style of BludBol. What has made them a good team has been having options to deviate from that plan. When [[kneemasher]] was still active he was a terror to passing teams and had the raw abilities to power the ball to TD himself on the other side of the field from the cage. [[mashee]] has not been as prolific and usually only takes the field when her role is crystal clear, but that has included some of the Farmers' biggest games.

### Management

Spleen Hucker has proved to be a savvy leader of the team, but at the expense of entertaining BludBol. When things weren't going well for the Farmers in GCVII he dropped all the starters from the active roster, replacing them with journeymen anxious for a taste of Pro level BludBol. They proceeded to lose lots of matches, but the players gained skills. Then in GCVIII those skills meant he didn't need to overpay for past performance and they won another championship. GCIX meant a time to tear everything down again to prep for some even-year magic.

### Fans

The current fanbase hates the tanking that went on in GCIX and the Farmers were going to be under the microscope for violations of the spirit of the new rules in GCX. They got through the season having regained some trust.

The Gore Farmers and the [Orbital Machine](orbitalmachine) both won the sixth Green Cup (one Classic and one not) and that dispute over which one should really count fuelled their rivalry. The [Darkling Spectres](darklingspectres) at this point are the team the Farmers try their best to fend off, as successfully as they have thus far.

### Famous Games

The GCVI Final is a match to watch. It wasn't the most pretty, but it's a pretty excellent example of how good BludBol can be even without constant arcing passes.