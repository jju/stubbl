# week 08

[Previously](week07)
[Concurrently](../ogiii/week03)

#t2780

Crossing the midseason point and the Sump Runners no longer occupy the basement spot.

* business storyline GF-CT [[aficionado]] the Tatters' traditional just do enough approach compared with the Farmers' boom and bust, 
* player storyline RE-OM [[warreporter]] Uli vs Jantine head to head, [[writer]] DS-AM, BC-KD [[aficionado]] letting Klim get some reps and how the Dynamo have been working in the post-Sabah era  
* team storyline OW-SR [[writer]] losing a star and what it does to a team, GH-ZV [[aficionado]] the injured players and underperforming Vagabonds, CF-IC [[warreporter]]  
* Playoffs: Intradivisional: OW-SR if the Sump Runners win they will be tied in the standings!?, GH-ZV first and fourth; GC preview FT-EF the top 2 teams facing off


## matchups

* [Glorious Hounds](../../teams/glorioushounds) - [Zensun Vagabonds](../../teams/zensunvagabonds) (GH+) #t2780.1
* [Old Wyrms](../../teams/oldwyrms) - [TC Sump Runners](../../teams/sumprunners) (OW+) #t2780.2
* [Darkling Spectres](../../teams/darklingspectres) - [Arboreal Menace](../../teams/arborealmenace) (AM+) #t2780.3
* [Ravenous Eagles](../../teams/ravenouseagles) - [Orbital Machine](../../teams/orbitalmachine) (OM) #t2780.4
* [Gore Farmers](../../teams/gorefarmers) - [Carcosan Tatters](../../teams/carcosantatters) (Even) #t2780.5
* [Cackling Furies](../../teams/cacklingfuries) - [Irregular Cogs](../../teams/irregularcogs) (IC+) #t2780.7
* [Kaiju Dynamo](../../teams/kaijudynamo) - [Badger Claws](../../teams/badgerclaws) (BC) #t2780.8
* [Filthy Tide](../../teams/filthytide) - [Eldritch Fatality](../../teams/eldritchfatality) (FT) #t2780.9

The Hounds showed that they should not be counted out any more than the Fatality this season by destroying the Vagabonds. GH 6 - ZV 1 [[gcxi-08-ghzv]]

The Wyrms got a draw that felt as bad as a loss against their divisional punching-bag Sump Runners. OW 3 - SR 3 [[gcxi-08-owsr]]

The Spectres scored a major upset that hinged on an early perfect defensive alignment to throw off the Menace's quick scoring gameplan. DS 6 - AM 4 [[gcxi-08-dsam]]

The Uli vs Jantine showdown went to Uli, who knocked out the Eagles' star (after a brief scare that Jantine may have died), but the Eagles got the win. RE 1 - OM 0 [[gcxi-08-reom]]

The Gore Farmers took advantage of sloppy play by the Tatters in the first half and pressed their advantage in the second. Long-term the effects of losing Tycho in this game will be the most deeply felt. GF 1 - CT 0 [[gcxi-08-gfct]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 5-1-1 | Arboreal Menace | 4-1-3 | Glorious Hounds | 5-2-1 | Eldritch Fatality | 7-0-0 |
| Old Wyrms | 2-3-3 | Irregular Cogs | 3-1-3 | Kaiju Dynamo | 4-0-3 | Ravenous Eagles | 4-2-2 |
| Gore Farmers | 2-1-4 | Badger Claws | 3-0-4 | Orbital Machine | 1-3-4 | Cackling Furies | 2-2-3 |
| TC Sump Runners | 1-3-4 | Carcosan Tatters | 2-2-3 | Zensun Vagabonds | 1-1-6 | Darkling Spectres | 3-0-5 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 8 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
