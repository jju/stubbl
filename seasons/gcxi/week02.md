# week 02

[Previously](week01) 
#t2773

* business storyline IC-GH [[warreporter]] learn history of GryjHun, RE-DS [[aficionado]] give the Spectres' weirdass lineup one more shot
* player storyline CT-FT [[aficionado]] Venus doing her thing in adverse circumstances, BC-ZV [[writer]] Klim could be interesting, 
* team storyline RE-DS [[warreporter]] (knows BR Ossa from bad times), GF-OW [[writer]] Stacks division rivalry defending champion, SR-EF [[aficionado]] bad teams doing better
* AM-OM CF-KD


## matchups

* [Badger Claws](../../teams/badgerclaws) - [Zensun Vagabonds](../../teams/zensunvagabonds) (BC) #t2773.1
* [Cackling Furies](../../teams/cacklingfuries) - [Kaiju Dynamo](../../teams/kaijudynamo) (KD+) (or KD) #t2773.2
* [Arboreal Menace](../../teams/arborealmenace) - [Orbital Machine](../../teams/orbitalmachine) (AM+) (or Even) #t2773.3
* [Ravenous Eagles](../../teams/ravenouseagles) - [Darkling Spectres](../../teams/darklingspectres) (Even) (or RE) #t2773.4
* [TC Sump Runners](../../teams/sumprunners) - [Eldritch Fatality](../../teams/eldritchfatality) (EF) #t2773.5
* [Gore Farmers](../../teams/gorefarmers) - [Old Wyrms](../../teams/oldwyrms) (OW+) (lock of the week) #t2773.7
* [Irregular Cogs](../../teams/irregularcogs) - [Glorious Hounds](../../teams/glorioushounds) (IC) #t2773.8
* [Carcosan Tatters](../../teams/carcosantatters) - [Filthy Tide](../../teams/filthytide) (FT) (or CT) #t2773.9

[[gcxi-02-bczv]]

[[]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Old Wyrms | 1-1-0 | Irregular Cogs | 1-0-0 | Zensun Vagabonds | 1-0-1 | Eldritch Fatality | 1-0-0 |
| Gore Farmers | 1-0-1 | Carcosan Tatters | 0-1-0 | Orbital Machine | 0-1-0 | Ravenous Eagles | 1-0-1 |
| Filthy Tide | 1-0-0 | Arboreal Menace | 0-0-1 | Glorious Hounds | 0-1-0 | Cackling Furies | 0-1-1 |
| TC Sump Runners | 0-1-0 | Badger Claws | 0-0-2 | Kaiju Dynamo | 1-0-1 | Darkling Spectres | 1-0-1 |

## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 2 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
