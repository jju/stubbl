# week 04

[Previously](week03) 
#t2775

* business storyline CF-DS [[aficionado]] the logic of the tank, RE-GF [[writer]] those new players just sitting there waiting, BC-OM [[warreporter]] the rivalry behind the ownership groups and how it plays out on the field,  
* player storyline BC-OM [[writer]] Aeson's continued return and how the partnership with Klim plays out', FT-SR [[aficionado]] Venus trying to pull the team along in an intradivisional match, RE-GF [[warreporter]] injuries from Jantine
* team storyline ZV-EF [[writer]] the rise of the Fatality especially against a team that's trying to mak a bit of money, CT-KD [[warreporter]] will the Tatters be able to bounce back and actually get a win, IC-OW [[aficionado]] the classic rivalry
* Champions Circuit: AM-GH KD-CT and GF-RE need wins to get in, an AM win puts a nail in the hopes of the Hounds. The Cogs have an outside chance if they beat the Wyrms and the KD and GF both lose. Could also note that the Hounds have the toughest schedule to make the CC.


## matchups

* [Cackling Furies](../../teams/cacklingfuries) - [Darkling Spectres](../../teams/darklingspectres) (CF) #t2775.1
* [TC Sump Runners](../../teams/sumprunners)  - [Filthy Tide](../../teams/filthytide) (FT+) (or FT) #t2775.2
* [Carcosan Tatters](../../teams/carcosantatters) - [Kaiju Dynamo](../../teams/kaijudynamo) (KD) #t2775.3
* [Badger Claws](../../teams/badgerclaws) - [Orbital Machine](../../teams/orbitalmachine) (BC) #t2775.4
* [Zensun Vagabonds](../../teams/zensunvagabonds)  - [Eldritch Fatality](../../teams/eldritchfatality) (ZV?) (or Even) #t2775.5
* [Irregular Cogs](../../teams/irregularcogs) - [Old Wyrms](../../teams/oldwyrms) (OW) (or Even) #t2775.7
* [Ravenous Eagles](../../teams/ravenouseagles) - [Gore Farmers](../../teams/gorefarmers) (Even) (RE) #t2775.8
* [Arboreal Menace](../../teams/arborealmenace) - [Glorious Hounds](../../teams/glorioushounds) (AM) (or GH) #t2775.9



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



```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 3 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
