# week 11

[Previously](seasons/gcxi/week10.md)
[Concurrently](../ogiii/week06)

#t2783

[next week](week12)

* business storyline: SR-CF [[warreporter]] bottom dwellers battling it out again, ZV-DS [[aficionado]] Surprisingness of the Spectres resurgence, RE-CT [[writer]] slow teams with success how do they do it?
* player storyline  OM-KD [[warreporter]] Uli leading the Carmine Fist, [[writer]], FT-GH [[aficionado]] battle of the best, can the Tide get back from the big defeat in Week 10
* team storyline EF-OW [[writer]] desperation for the Wyrms, IC-AM [[aficionado]] AM just put down the league leading EF last week who also use a Drop Eagle, BC-GF [[warreporter]] the Claws are sucking and need to pick it up horse with broken leg.
* Playoffs: Intradivisional: IC-AM Tied for first in the Outlands, this determines the edge, OM-KD worst v first in Heaps 


## matchups

* [Orbital Machine](../../teams/orbitalmachine) - [Kaiju Dynamo](../../teams/kaijudynamo) (KD+) #t2783.1
* [Zensun Vagabonds](../../teams/zensunvagabonds) - [Darkling Spectres](../../teams/darklingspectres) (ZV) #t2783.2
* [TC Sump Runners](../../teams/sumprunners) - [Cackling Furies](../../teams/cacklingfuries) (CF) #t2783.3
* [Badger Claws](../../teams/badgerclaws) - [Gore Farmers](../../teams/gorefarmers) (BC+) #t2783.4
* [Ravenous Eagles](../../teams/ravenouseagles) - [Carcosan Tatters](../../teams/carcosantatters) (RE) #t2783.5
* [Eldritch Fatality](../../teams/eldritchfatality) - [Old Wyrms](../../teams/oldwyrms) (Even) #t2783.7
* [Arboreal Menace](../../teams/arborealmenace) - [Irregular Cogs](../../teams/irregularcogs) (AM) #t2783.8
* [Filthy Tide](../../teams/filthytide) - [Glorious Hounds](../../teams/glorioushounds) (GH) #t2783.9

The draw helped the Machine in the standings but they lost two players and [[Uli]] didn't gain any ground in the Carmine Fist competition. OM 1 - KD 1 [[gcxi-11-omkd]]

The Vagabonds looked like the playoff team from last season in their dominating win over the Spectres. ZV 5 - DS 1 [[gcxi-11-zvds]]

The Furies got the win they needed to keep pace with the Spectres, while the Sump Runners are dependent on the Wyrms continuing to slide. SR 1 - CF 2 [[gcxi-11-srcf]]

The Claws couldn't get the win they needed. Again. BC 2 - GF 2 [[gcxi-11-bcgf]]

The Tatters played out of character allowing Sparrow to have a flashy first half, but they locked down the second and got the win the Claws were hoping they wouldn't. RE 1 - CT 2 [[gcxi-11-rect]]

The Wyrms could never get anything going in this match. EF 4 - OW 1 [[gcxi-11-efow]]

The battle for the Outlands wasn't won today.  AM 3 - IC 3 [[gcxi-11-amic]]

This high-scoring match solved absolutely nothing in the standings, but Veens did edge away from Ziba in the Sardines crown race. FT 8 - GH 8 [[gcxi-11-ftgh]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 7-2-2 | Irregular Cogs | 6-2-3 | Kaiju Dynamo | 7-1-3 | Eldritch Fatality | 9-0-2 |
| Gore Farmers | 4-2-5 | Arboreal Menace | 6-2-3 | Glorious Hounds | 6-2-2 | Ravenous Eagles | 4-3-4 |
| Old Wyrms | 3-3-5 | Carcosan Tatters | 4-2-5 | Zensun Vagabonds | 3-1-7 | Darkling Spectres | 4-0-7 |
| TC Sump Runners | 1-4-6 | Badger Claws | 3-3-5 | Orbital Machine | 1-4-6 | Cackling Furies | 3-2-6 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Veens   | Filthy Tide       |    8 |  100 |    0 |      0 |    6 |    0 |    0 |    0 |    0 |    1 |   29 |
| Ziba    | Glorious Hounds   |    7 |   90 |    0 |      0 |    4 |    0 |    0 |    0 |    0 |    0 |   21 |
| Luanna  | Cackling Furies   |    0 |   18 |    4 |     11 |    0 |    1 |    0 |    2 |    0 |    1 |   11 |
| Oxana   | Glorious Hounds   |    0 |   22 |    6 |     23 |    0 |    0 |    0 |    0 |    0 |    1 |   11 |
| Padma   | Zensun Vagabonds  |    3 |   21 |    0 |      0 |    3 |    0 |    0 |    4 |    0 |    0 |    9 |
| Koralo  | Eldritch Fatality |    2 |   28 |    1 |     -2 |    0 |    0 |    1 |    0 |    0 |    0 |    9 |
| Nuru  | Gore Farmers      |    1 |   44 |    0 |      0 |    4 |    0 |    0 |    0 |    0 |    1 |    8 |
| Ross  | Darkling Spectres |    1 |   15 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    1 |    8 |
| Mia     | Zensun Vagabonds  |    2 |   30 |    0 |      0 |    1 |    0 |    1 |    4 |    0 |    0 |    8 |
| Percy | Ravenous Eagles   |    0 |    0 |    0 |      0 |    0 |    0 |    4 |    7 |    0 |    0 |    8 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 11 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
