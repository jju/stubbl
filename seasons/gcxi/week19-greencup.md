# playoffs - green cup final

[Previously](week18-conffinals)
[Concurrently](../ogiii/week14-finals)

#t2791

Let's take a look at the previous Green Cups to see how this matchup fares:

* Green Cup I - Final - **Irregular Cogs** 3 Old Wyrms 2
* Green Cup II - Final - **Carcosan Tatters** 2 Zensun Vagabonds 1
* Green Cup III - Final - Cackling Furies 2 **Old Wyrms** 4
* Green Cup IV - Final - Glorious Hounds 3 **Old Wyrms** 5
* Green Cup VI - Final - Carcosan Tatters 0 **Gore Farmers** 1
* Green Cup Classic 06 - Final - Darkling Spectres 0 **Orbital Machine** 1
* Green Cup VII - Final - **Ravenous Eagles** 1 Darkling Spectres 0
* Green Cup VIII - Final - **Gore Farmers** 2 Badger Claws 1
* Green Cup IX - Final - **Old Wyrms** 4 Eldritch Fatality 3
* Green Cup X - Final - **Old Wyrms** 2 Ravenous Eagles 1

As we can see, the home team has won 6 out of 10. You have to go back to the Old-Era to find a match that was closer than one 1 TD (and it was one of the GCXI finalists who was on the losing end of one of those in GCIV). 

In the modern era we've only had one final between two offense-first teams (GCIX), while in the Old-Era half of them went that way. SpreadZone's Over/Under of 8.5 seems reasonable.

* business storyline: [[warreporter]] [[aficionado]] [[writer]]
* player storyline: [[warreporter]] [[aficionado]] [[writer]]
* team storyline:[[warreporter]] [[aficionado]] [[writer]]
* Playoffs: see above


## matchups

* [Filthy Tide](../../teams/filthytide) - [Glorious Hounds](../../teams/glorioushounds) (GH)

Congratulations to those who picked SpreadZone's Under 8.5 (and the Filthy Tide)! That was a messier final than we were expecting but the Filthy Tide played their guts out to get this title. FT 3 - GH 2 [[gcxi-19-ftgh]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| **Filthy Tide** | 13-2-3 | *Arboreal Menace* | 11-2-5 | *Glorious Hounds* | 12-4-2 | *Eldritch Fatality* | 13-0-5 |
| *Old Wyrms* | 5-3-9 | *Irregular Cogs* | 9-2-6 | *Kaiju Dynamo* | 10-1-5 | *Darkling Spectres* | 8-1-8 |
| *Gore Farmers* | 5-2-9 | *Carcosan Tatters* | 7-2-7 | *Zensun Vagabonds* | 5-2-10 | *Ravenous Eagles* | 5-3-7 |
| *TC Sump Runners* | 1-4-11 | *Badger Claws* | 4-4-8 | *Orbital Machine* | 1-6-9 | *Cackling Furies* | 5-2-9 |


## player of the week standings

| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Ziba     | Glorious Hounds |    1 |   18 |    0 |      0 |    1 |    2 |    0 |    1 |    0 |    1 |   12 |
| Veens    | Filthy Tide     |    3 |   22 |    0 |      0 |    1 |    0 |    0 |    1 |    1 |    0 |    9 |
| Briseida | Filthy Tide     |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    7 |    0 |    1 |    5 |
| Oxana    | Glorious Hounds |    0 |   16 |    3 |     13 |    0 |    0 |    0 |    1 |    0 |    0 |    3 |
| Irenaeus | Glorious Hounds |    1 |    7 |    0 |      0 |    1 |    0 |    0 |    4 |    1 |    0 |    3 |
| Udo      | Glorious Hounds |    0 |    8 |    1 |     -1 |    1 |    0 |    0 |    3 |    0 |    0 |    1 |
| Aleksy   | Filthy Tide     |    0 |   15 |    1 |      1 |    0 |    0 |    0 |    1 |    0 |    0 |    1 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 255 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```

## season leaderboards

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 5;
```

### mvp

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Veens  | Filthy Tide       |   69 |  770 |    1 |      3 |   47 |    0 |    0 |    1 |    1 |    1 |  213 |
| Ziba   | Glorious Hounds   |   63 |  739 |    2 |      0 |   58 |    2 |    0 |    9 |    1 |    3 |  210 |
| Laurel | Arboreal Menace   |   34 |  519 |    0 |      0 |   42 |    1 |    0 |    1 |    0 |    1 |  109 |
| Frans  | Irregular Cogs    |   19 |  241 |    4 |      9 |   24 |    5 |    1 |   36 |    0 |    1 |   78 |
| Koralo | Eldritch Fatality |   12 |  223 |   19 |     11 |   22 |    0 |    2 |   14 |    0 |    2 |   69 |

Top 5

### TDs

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Veens  | Filthy Tide     |   69 |  770 |    1 |      3 |   47 |    0 |    0 |    1 |    1 |    1 |  213 |
| Ziba   | Glorious Hounds |   63 |  739 |    2 |      0 |   58 |    2 |    0 |    9 |    1 |    3 |  210 |
| Laurel | Arboreal Menace |   34 |  519 |    0 |      0 |   42 |    1 |    0 |    1 |    0 |    1 |  109 |
| Frans  | Irregular Cogs  |   19 |  241 |    4 |      9 |   24 |    5 |    1 |   36 |    0 |    1 |   78 |
| Klim   | Badger Claws    |   19 |  267 |    0 |      0 |   19 |    0 |    0 |    2 |    2 |    2 |   67 |

Top 3

### passing

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Luanna. | Cackling Furies   |    1 |  204 |   54 |    221 |    0 |    1 |    0 |   15 |    0 |    1 |   64 |
| Oxana   | Glorious Hounds   |    0 |  234 |   54 |    195 |    3 |    1 |    0 |   19 |    0 |    1 |   61 |
| Betuel  | Zensun Vagabonds  |    0 |  197 |   51 |    231 |    2 |    0 |    3 |   10 |    1 |    1 |   62 |

Top 3

### rushing

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Veens  | Filthy Tide       |   69 |  770 |    1 |      3 |   47 |    0 |    0 |    1 |    1 |    1 |  213 |
| Ziba   | Glorious Hounds   |   63 |  739 |    2 |      0 |   58 |    2 |    0 |    9 |    1 |    3 |  210 |
| Laurel | Arboreal Menace   |   34 |  519 |    0 |      0 |   42 |    1 |    0 |    1 |    0 |    1 |  109 |
| Klim   | Badger Claws      |   19 |  267 |    0 |      0 |   19 |    0 |    0 |    2 |    2 |    2 |   67 |
| Filipa | Eldritch Fatality |    1 |  247 |   47 |    134 |    2 |    2 |    0 |   12 |    1 |    1 |   59 |

### catches

| Player | Team            | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|--------|-----------------|------|------|------|--------|------|---|---|--------|-------|------|------|
| Ziba   | Glorious Hounds |   63 |  739 |    2 |      0 |   58 |    2 |    0 |    9 |    1 |    3 |  210 |
| Veens  | Filthy Tide     |   69 |  770 |    1 |      3 |   47 |    0 |    0 |    1 |    1 |    1 |  213 |
| Laurel | Arboreal Menace |   34 |  519 |    0 |      0 |   42 |    1 |    0 |    1 |    0 |    1 |  109 |
| Aronne | Cackling Furies |    7 |  202 |    5 |     -6 |   29 |    0 |    0 |   18 |    2 |    0 |   26 |
| Frans  | Irregular Cogs  |   19 |  241 |    4 |      9 |   24 |    5 |    1 |   36 |    0 |    1 |   78 |

### casualties

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Uli      | Orbital Machine  |    0 |    0 |    0 |      0 |    0 |    0 |   22 |  174 |    2 |    0 |   44 |
| Jantine. | Ravenous Eagles  |    0 |    0 |    0 |      0 |    0 |    0 |   11 |   94 |    1 |    0 |   22 |
| Percy    | Ravenous Eagles  |    0 |    0 |    0 |      0 |    0 |    0 |   11 |   65 |    0 |    0 |   22 |
| Florinda | Glorious Hounds  |    2 |   15 |    0 |      0 |    3 |    1 |    8 |  167 |    6 |    0 |   24 |

### sacks

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Ekua.    | Ravenous Eagles   |    1 |    2 |    0 |      0 |    1 |    0 |    5 |  105 |    8 |    1 |   18 |
| Pinja    | Irregular Cogs    |    0 |    7 |    0 |      0 |    0 |    1 |    2 |  114 |    7 |    3 |   21 |
| Dunstan. | Eldritch Fatality |    0 |    2 |    1 |      5 |    0 |    0 |    5 |  122 |    7 |    0 |   11 |

### blocks

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Uli      | Orbital Machine |    0 |    0 |    0 |      0 |    0 |    0 |   22 |  174 |    2 |    0 |   44 |
| Florinda | Glorious Hounds |    2 |   15 |    0 |      0 |    3 |    1 |    8 |  167 |    6 |    0 |   24 |
| Deepali  | Kaiju Dynamo    |    0 |    0 |    0 |      0 |    0 |    1 |    5 |  166 |    2 |    1 |   17 |

### mvps

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Ravil  | Glorious Hounds   |    6 |   71 |    4 |      4 |    9 |    0 |    0 |   20 |    4 |    6 |   52 |
| Vusala | Arboreal Menace   |    4 |   20 |    0 |      0 |    1 |    0 |    1 |   56 |    1 |    4 |   34 |
| Ross   | Darkling Spectres |    3 |   39 |    3 |      9 |    1 |    0 |    0 |    4 |    0 |    4 |   32 |
