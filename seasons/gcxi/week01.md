# week 01

[Previously in the preseason](preseason) #t2772

* business storyline DS-GF [[aficionado]]
* player storyline FT-AR [[writer]] or RE-ZV [[aficionado]] or BC-EF (dud bc Aeson does sit it out) [[writer]] or OW-CF [[warreporter]]
* team GH-CT (how do the Hounds do coming off a tournament win?) [[writer]] OM-SR (no fans vs bad team) [[warreporter]] KD-IC [[aficionado]] (interesting tactical choices)


## matchups

* [Darkling Spectres](../../teams/darklingspectres) - [Gore Farmers](../../teams/gorefarmers) (DS?!) #t2772.1 
* [Eldritch Fatality](../../teams/eldritchfatality) - [Badger Claws](../../teams/badgerclaws) (BC) #t2772.2 
* [Ravenous Eagles](../../teams/ravenouseagles) - [Zensun Vagabonds](../../teams/zensunvagabonds) (ZV)
* [Old Wyrms](../../teams/oldwyrms) - [Cackling Furies](../../teams/cacklingfuries) (OW)
* [Kaiju Dynamo](../../teams/kaijudynamo) - [Irregular Cogs](../../teams/irregularcogs) (Even)
* [Glorious Hounds](../../teams/glorioushounds) - [Carcosan Tatters](../../teams/carcosantatters) (CT)
* [Filthy Tide](../../teams/filthytide) - [Arboreal Menace](../../teams/arborealmenace) (AR)
* [Orbital Machine](../../teams/orbitalmachine) - [TC Sump Runners](../../teams/sumprunners) (Even)

It is crazy that spreadZone were giving odds in favour of the Spectres winning this match. No seriously, what are you thinking? Give the Gore Farmers credit though, they fielded a strong lineup. You could barely tell who was who in the Spectres' half of the field. DS 1 - GF 2 [[gcxi-01-dsgf]]

The Claws had the edge going in against a Fatality team that was terrible last season and has no resources to build up something much better this season unless they win a lot of games. [[Rong]] got badly hurt on the opening drive which can't be good for their development plans. At the half Rong had been joined by a chunk of the line fodder on the sidelines and the Fatality were up 2-1. They never released that lead. EF 4 - BC 2 [[gcxi-01-efbc]] 

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Gore Farmers | 1-0-0 | Arboreal Menace | 0-0-0 | Glorious Hounds | 0-0-0 | Eldritch Fatality | 1-0-0 |
| Filthy Tide | 0-0-0 | Carcosan Tatters | 0-0-0 | Orbital Machine | 0-0-0 | Ravenous Eagles | 0-0-0 |
| Old Wyrms | 0-0-0 | Irregular Cogs | 0-0-0 | Kaiju Dynamo | 0-0-0 | Cackling Furies | 0-0-0 |
| TC Sump Runners | 0-0-0 | Badger Claws | 0-0-1 | Zensun Vagabonds | 0-0-0 | Darkling Spectres | 0-0-1 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 1 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
