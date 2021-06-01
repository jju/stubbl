# week 01

[Previously in the preseason](preseason) #t2760



## matchups

* [Ravenous Eagles](../teams/ravenouseagles) - [Zensun Vagabonds](../teams/zensunvagabonds)
* [Darkling Spectres](../teams/darklingspectres) - [Gore Farmers](../teams/gorefarmers)
* [Old Wyrms](../teams/oldwyrms) - [Cackling Furies](../teams/cacklingfuries)
* [Kaiju Dynamo](../teams/kaijudynamo) - [Irregular Cogs](../teams/irregularcogs)
* [Glorious Hounds](../teams/glorioushounds) - [Carcosan Tatters](../teams/carcosantatters)
* [Filthy Tide](../teams/filthytide) - [Arboreal Menace](../teams/arborealmenace)
* [Orbital Machine](../teams/orbitalmachine) - [TC Sump Runners](../teams/sumprunners)
* [Eldritch Fatality](../teams/eldritchfatality) - [Badger Claws](../teams/badgerclaws)

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Old Wyrms | 0-0-0 | Arboreal Menace | 0-0-0 | Glorious Hounds | 0-0-0 | Eldritch Fatality | 0-0-0 |
| Filthy Tide | 0-0-0 | Badger Claws | 0-0-0 | Orbital Machine | 0-0-0 | Ravenous Eagles | 0-0-0 |
| Gore Farmers | 0-0-0 | Irregular Cogs | 0-0-0 | Kaiju Dynamo | 0-0-0 | Cackling Furies | 0-0-0 |
| TC Sump Runners | 0-0-0 | Carcosan Tatters | 0-0-0 | Zensun Vagabonds | 0-0-0 | Darkling Spectres | 0-0-0 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 1 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
