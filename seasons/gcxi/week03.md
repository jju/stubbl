# week 03

[Previously](seasons/gcxi/week02.md) 
#t2774
[next week](week04)

* business storyline CF-BC [[warreporter]] bringing back Aeson for wins, DS-EF [[aficionado]] can the Fatality keep running on fumes?, RE-GH [[writer]] Hounds out of cash entirely while the Eagles are sitting on new player contracts they can't sign
* player storyline CF-BC [[writer]] bringing back Aeson morale on Klim, KD-FT [[aficionado]] Veens doing her thing in better circumstances, RE-GH [[warreporter]] injuries from Jantine
* team storyline DS-EF [[writer]] the rise of the Fatality, CT-AM [[aficionado]] The third week in a row of the Tatters facing teams that can punish a moments' weakness by scoring seemingly at will, OW-OM [[warreporter]] can the Machine sideline enough Wyrms to make things tough going forward?
* IC-SR, GF-ZV


## matchups

* [Cackling Furies](../../teams/cacklingfuries) - [Badger Claws](../../teams/badgerclaws) (BC) #t2774.1
* [Irregular Cogs](../../teams/irregularcogs) - [TC Sump Runners](../../teams/sumprunners) (IC+) #t2774.2
* [Old Wyrms](../../teams/oldwyrms) - [Orbital Machine](../../teams/orbitalmachine) (OW+) #t2774.3
* [Carcosan Tatters](../../teams/carcosantatters) - [Arboreal Menace](../../teams/arborealmenace) (AM) (or Even) #t2774.4
* [Gore Farmers](../../teams/gorefarmers) - [Zensun Vagabonds](../../teams/zensunvagabonds) (ZV) #t2774.5
* [Kaiju Dynamo](../../teams/kaijudynamo) - [Filthy Tide](../../teams/filthytide) (Even) (or KD) #t2774.7
* [Darkling Spectres](../../teams/darklingspectres) - [Eldritch Fatality](../../teams/eldritchfatality) (EF+) #t2774.8
* [Ravenous Eagles](../../teams/ravenouseagles)- [Glorious Hounds](../../teams/glorioushounds) (GH) #t2774.9

The Badger Claws needed to get their legend out of the workout room, but [[aeson]] delivered the win against the Furies. CF 4 - BC 5 [[gcxi-03-cfbc]]

The Cogs have something wrong with them when they can't put away the lowly Sump Runners IC 2 - SR 2 [[gcxi-03-icsr]]

Well that was not a dominant display of championship calibre BludBol. OW 1 - OM 1 [[gcxi-03-owom]]

The Tatters still don't have a win after facing three offensive powerhouses. CT 2 - AM 4 [[gcxi-03-ctam]]

The Gore Farmers dropped some of their overkill going in, leaving them a nice lean team capable of beating the Vagabonds. Nothing special, just a good little upset. GF 2 - ZV 1 [[gcxi-03-gfzv]]

Early blunders dug the Tide a hole they couldn't escape from in this match. KD 5 - FT 3 [[gcxi-03-kdft]]

Now that's what we'd expect these Spectres to look like. DS 0 - EF 5 [[gcxi-03-dsef]]

The Eagles beat the odds by crunching through an interminable match for a draw. The Hounds needed a win to solidify their chances to go to the Champions Circuit after week 5. RE 1 - GH 1 [[gcxi-03-regh]]


Only favourite wins: AM and EF

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Gore Farmers | 2-0-1 | Arboreal Menace | 2-0-1 | Kaiju Dynamo | 2-0-1 | Eldritch Fatality | 3-0-0 |
| Old Wyrms | 1-2-0 | Irregular Cogs | 1-1-1 | Glorious Hounds | 1-2-0 | Ravenous Eagles | 1-1-1 |
| Filthy Tide | 1-1-1 | Badger Claws | 1-0-2 | Zensun Vagabonds | 1-0-2 | Darkling Spectres | 1-0-2 |
| TC Sump Runners | 0-2-1 | Carcosan Tatters | 0-2-1 | Orbital Machine | 0-2-1 | Cackling Furies | 0-1-2 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Louis      | Kaiju Dynamo      |    4 |   56 |    0 |      0 |    2 |    0 |    0 |    1 |    0 |    1 |   17 |
| Aeson      | Badger Claws      |    3 |   39 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |    9 |
| Atte       | Eldritch Fatality |    3 |   47 |    0 |      0 |    3 |    0 |    0 |    1 |    0 |    0 |    9 |
| Veens      | Filthy Tide       |    3 |   51 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |    9 |
| Rickon     | Cackling Furies   |    3 |   25 |    0 |      0 |    4 |    0 |    0 |    1 |    0 |    0 |    9 |
| Matheo     | Irregular Cogs    |    1 |    7 |    0 |      0 |    1 |    0 |    0 |    2 |    0 |    1 |    8 |
| Gerty      | Badger Claws      |    1 |    6 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    1 |    8 |
| Metin      | TC Sump Runners   |    1 |    7 |    0 |      0 |    1 |    0 |    0 |    4 |    0 |    1 |    8 |
| Svyatopolk | Cackling Furies   |    0 |    0 |    0 |      0 |    0 |    0 |    1 |   11 |    0 |    1 |    7 |
| Filipa     | Eldritch Fatality |    0 |    9 |    2 |      3 |    0 |    0 |    0 |    1 |    0 |    1 |    7 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 3 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
