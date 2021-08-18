# week 08

[Previously](week07)
[Concurrently](../ogiii/week03)

#t2780

~~After Week 6 the projections got all reshuffled. Apparently spreadZone has now decided the undefeated Fatality might not be a total fluke and could do well this season, and the Wyrms may have a harder row to hoe.

* business storyline EF-GF [[warreporter]] how does an undefeated team keep sharp and keep the money flowing, SR-CT [[aficionado]] defense and the art of weathering the bad game, [[writer]] 
* player storyline OM-DS [[warreporter]] Uli's surprising emergence over Jantine, RE-AM [[writer]] brute longevity vs Laurel's beauty, BC-IC [[aficionado]] Aeson's return and what his stats are looking like
* team storyline FT-OW [[aficionado]] playoff implications and seeing the defending champs falter a bit, GH-KD [[writer]] battle for the division and coming off Ziba's great week do the Dynamo have an answer?, ZV-CF [[warreporter]] 
* Playoffs: Intradivisional: BC-IC, FT-OW, GH-KD really imporant to get any separation in the divisional title hunt (or get the BC out of the basement)


## matchups

* [TC Sump Runners](../../teams/sumprunners) - [Carcosan Tatters](../../teams/carcosantatters) (SR) #t2779.1
* [Orbital Machine](../../teams/orbitalmachine) - [Darkling Spectres](../../teams/darklingspectres) (Even) #t2779.2
* [Zensun Vagabonds](../../teams/zensunvagabonds) - [Cackling Furies](../../teams/cacklingfuries) (ZV) #t2779.3
* [Badger Claws](../../teams/badgerclaws) - [Irregular Cogs](../../teams/irregularcogs) (BC) #t2779.4
* [Eldritch Fatality](../../teams/eldritchfatality) - [Gore Farmers](../../teams/gorefarmers) (EF+) #t2779.5
* [Filthy Tide](../../teams/filthytide) - [Old Wyrms](../../teams/oldwyrms) (Even) #t2779.7
* [Ravenous Eagles](../../teams/ravenouseagles) - [Arboreal Menace](../../teams/arborealmenace) (AM+) #t2779.8
* [Glorious Hounds](../../teams/glorioushounds) - [Kaiju Dynamo](../../teams/kaijudynamo) (Even) #t2779.9



## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 5-1-1 | Arboreal Menace | 4-1-2 | Glorious Hounds | 4-2-1 | Eldritch Fatality | 7-0-0 |
| Old Wyrms | 2-2-3 | Irregular Cogs | 3-1-3 | Kaiju Dynamo | 4-0-3 | Ravenous Eagles | 3-2-2 |
| Gore Farmers | 2-1-4 | Badger Claws | 3-0-4 | Orbital Machine | 1-3-3 | Cackling Furies | 2-2-3 |
| TC Sump Runners | 1-2-4 | Carcosan Tatters | 2-2-3 | Zensun Vagabonds | 1-1-5 | Darkling Spectres | 2-0-5 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 8 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
