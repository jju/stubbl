# week 06

[Previously](week05) (and the interlude of [another round in the Champions Circuit](week05cc))

#t2778

* business storyline GH-DS [[writer]] playing for a tanking team vs a team really trying to win, ZV-CT [[aficionado]] playing more with less and how it doesn't work for the Tatters  
* player storyline RE-SR [[warreporter]] counting stats and Ekua's GP record (parallel with longevity in gangsterism), BC-AM [[writer]] Aeson vs Laurel in a battle of finesse and scoring and beauty, FT-GF [[aficionado]] Venus needs a rebound match after being stifled in the CC against the Mules
* team storyline EF-IC [[aficionado]] Drop Eagle matchup with two teams on top of their divisions, KD-OW [[writer]] the Wyrms need to start overachieving and they have the skills to do it, OM-CF [[warreporter]] rumours have it that this could be a bloodbath
* Playoffs: Now is the middle game where teams just need to hang in until the trade deadline when lineups have to be solidified. We can expect a bit of experimentation.


## matchups

* [Ravenous Eagles](../../teams/ravenouseagles) - [TC Sump Runners](../../teams/sumprunners) (Even) #t2778.1
* [Glorious Hounds](../../teams/glorioushounds) - [Darkling Spectres](../../teams/darklingspectres) (GH+) #t2778.2
* [Zensun Vagabonds](../../teams/zensunvagabonds) - [Carcosan Tatters](../../teams/carcosantatters) (Even) #t2778.3
* [Orbital Machine](../../teams/orbitalmachine) - [Cackling Furies](../../teams/cacklingfuries) (Even) #t2778.4
* [Badger Claws](../../teams/badgerclaws)  - [Arboreal Menace](../../teams/arborealmenace) (BC+) #t2778.5
* [Filthy Tide](../../teams/filthytide) - [Gore Farmers](../../teams/gorefarmers) (FT+) #t2778.7
* [Kaiju Dynamo](../../teams/kaijudynamo) - [Old Wyrms](../../teams/oldwyrms) (OW) #t2778.8
* [Eldritch Fatality](../../teams/eldritchfatality) - [Irregular Cogs](../../teams/irregularcogs) (Even) #t2778.9

The Eagles cruised through the match never really needing to let up against the last place team. RE 2 - SR 0 [[gcxi-06-resr]]

The Hounds spent the first half keeping ahead on the scoreboard but not really threatening on defense, then when they got the chance to open up they played more loosely and proceeded to trample the Spectres (figuratively). GH 8 - DS 4 [[gcxi-06-ghds]]

The Tatters did exactly what they are always attempting, and managed with a depleted lineup. ZV 1 - CT 2 [[gcxi-06-zvct]]

Not as bloody as it could have been, but the Machine seemed to have no real interest in winning. OM 0 - CF 3 [[gcxi-06-omcf]]

The Claws were a comedy of errors to start and couldn't pull back a draw. BC 5 - AM6 [[gcxi-06-bcam]]

A nice comeback match for Venus after the disappointment that was the Champions Circuit.  FT 4 - GF 3 [[gcxi-06-ftgf]]

The Dynamo hung onto the ball the entire second half without even scoring, making for a bit of a boring match, but a safe win that the Dynamo have often been loathe to try for. KD 2 - OW 0 [[gcxi-06-kdow]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 4-1-1 | Irregular Cogs | 3-1-1 | Kaiju Dynamo | 4-0-2 | Eldritch Fatality | 5-0-0 |
| Old Wyrms | 2-2-2 | Arboreal Menace | 4-0-2 | Glorious Hounds | 3-2-1 | Ravenous Eagles | 3-1-2 |
| Gore Farmers | 2-1-3 | Badger Claws | 2-0-4 | Orbital Machine | 1-3-2 | Cackling Furies | 2-1-3 |
| TC Sump Runners | 0-2-4 | Carcosan Tatters | 2-2-2 | Zensun Vagabonds | 1-0-5 | Darkling Spectres | 1-0-5 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Ziba      | Glorious Hounds   |    6 |   81 |    1 |      2 |    6 |    0 |    0 |    1 |    0 |    0 |   19 |
| Aeson     | Badger Claws      |    4 |   52 |    0 |      0 |    4 |    0 |    0 |    1 |    0 |    0 |   12 |
| Aemulus   | Gore Farmers      |    3 |   22 |    1 |     10 |    3 |    0 |    0 |    3 |    0 |    0 |   10 |
| Marley    | Carcosan Tatters  |    0 |    0 |    0 |      0 |    0 |    0 |    2 |    6 |    0 |    1 |    9 |
| Venus     | Filthy Tide       |    3 |   38 |    0 |      0 |    2 |    0 |    0 |    0 |    0 |    0 |    9 |
| Faite     | Cackling Furies   |    2 |   27 |    0 |      0 |    1 |    0 |    1 |    4 |    0 |    0 |    8 |
| Kropotkin | Arboreal Menace   |    1 |    8 |    0 |      0 |    0 |    0 |    0 |    5 |    1 |    1 |    8 |
| Lazar     | Irregular Cogs    |    1 |    7 |    0 |      0 |    0 |    0 |    0 |    1 |    0 |    1 |    8 |
| Roze      | Gore Farmers      |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    2 |    0 |    1 |    7 |
| Olufunmi  | Darkling Spectres |    2 |   41 |    1 |      3 |    3 |    0 |    0 |    2 |    0 |    0 |    7 |

[[Ziba]] had a heckuva week.


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 6 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
