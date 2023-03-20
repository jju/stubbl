# week 04

[Previously](seasons/gcxi/week03.md) 
#t2775
[next week](week05)

* business storyline CF-DS [[aficionado]] the logic of the tank, RE-GF [[writer]] those new players just sitting there waiting, BC-OM [[warreporter]] the rivalry behind the ownership groups and how it plays out on the field,  
* player storyline BC-OM [[writer]] Aeson's continued return and how the partnership with Klim plays out', FT-SR [[aficionado]] Veens trying to pull the team along in an intradivisional match, RE-GF [[warreporter]] injuries from Jantine
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

Now that the Spectres have been decisively knocked back down to last place in the division, perhaps they'll pull a Badger Claws move and bust out their good players once again. CF 5 - DS 0 [[gcxi-04-cfds]]

The Tide did what was necessary despite the Sump Runners never really giving up the ghost. SR 3 - FT 5 [[gcxi-04-srft]]

CT 1 - KD 0 [[gcxi-04-ctkd]]

Not the results the Claws were looking for, plus serious injuries to four of their skilled position players. BC 0 - OM 2 [[gcxi-04-bcom]]

ZV 2 - EF 3 [[gcxi-04-zvef]]

IC 3 - OW 2 [[gcxi-04-icow]]

RE 1 - GF 0 [[gcxi-04-regf]]

AM 4 - GH 7 [[gcxi-04-amgh]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 2-1-1 | Irregular Cogs | 2-1-1 | Glorious Hounds | 2-2-0 | Eldritch Fatality | 4-0-0 |
| Gore Farmers | 2-0-2 | Arboreal Menace | 2-0-2 | Kaiju Dynamo | 2-0-2 | Ravenous Eagles | 2-1-1 |
| Old Wyrms | 1-2-1 | Carcosan Tatters | 1-2-1 | Orbital Machine | 1-2-1 | Cackling Furies | 1-1-2 |
| TC Sump Runners | 0-2-2 | Badger Claws | 1-0-3 | Zensun Vagabonds | 1-0-3 | Darkling Spectres | 1-0-3 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Ziba     | Glorious Hounds   |    6 |   64 |    0 |      0 |    4 |    0 |    0 |    1 |    0 |    0 |   18 |
| Laurel   | Arboreal Menace   |    4 |   40 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |   12 |
| Rickon   | Cackling Furies   |    3 |   23 |    0 |      0 |    3 |    1 |    0 |    1 |    0 |    0 |   11 |
| Koralo   | Eldritch Fatality |    2 |   24 |    4 |     10 |    3 |    0 |    0 |    1 |    0 |    0 |   10 |
| Corinne  | Orbital Machine   |    1 |   16 |    1 |      0 |    3 |    0 |    0 |    2 |    0 |    1 |    9 |
| Betuel   | Zensun Vagabonds  |    0 |   17 |    3 |      5 |    1 |    0 |    0 |    0 |    0 |    1 |    8 |
| Briseida | Filthy Tide       |    2 |   18 |    0 |      0 |    0 |    1 |    0 |    8 |    1 |    0 |    8 |
| Thiemo   | Cackling Furies   |    1 |    0 |    0 |      0 |    0 |    0 |    0 |    3 |    0 |    1 |    8 |
| Uli      | Orbital Machine   |    0 |    0 |    0 |      0 |    0 |    0 |    4 |   15 |    0 |    0 |    8 |
| Veens    | Filthy Tide       |    2 |   26 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    6 |



```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 4 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
