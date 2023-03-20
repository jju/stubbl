# week 10

[Previously](seasons/gcxi/week09.md)
[Concurrently](../ogiii/week05)

#t2782

[next week](week11)

* business storyline: OM-CT [[warreporter]] Bruiser matchup that they both need for the long stretch, ZV-SR [[aficionado]]two last place teams just marking time in the season, KD-GF [[writer]] player development vs win now
* player storyline  EF-AM [[warreporter]] should be a classic even though these teams have very little history, [[writer]], FT-IC [[aficionado]] an OG match that is too close to call  
* team storyline RE-BC [[writer]] Another chance for the Claws to underperform, OW-DS [[aficionado]] If the DS win this puts the OW season in jeopardy, GH-CF [[warreporter]] The Furies are trying to play spoiler and basically just fuck up the Hounds.
* Playoffs: Intradivisional: none


## matchups

* [Zensun Vagabonds](../../teams/zensunvagabonds) - [TC Sump Runners](../../teams/sumprunners) (Even) #t2782.1 
* [Orbital Machine](../../teams/orbitalmachine) - [Carcosan Tatters](../../teams/carcosantatters) (OM) #t2782.2 
* [Glorious Hounds](../../teams/glorioushounds) - [Cackling Furies](../../teams/cacklingfuries) (GH+) #t2782.3
* [Old Wyrms](../../teams/oldwyrms) - [Darkling Spectres](../../teams/darklingspectres) (OW+) #t2782.4 
* [Ravenous Eagles](../../teams/ravenouseagles) - [Badger Claws](../../teams/badgerclaws) (BC+) #t2782.5 
* [Kaiju Dynamo](../../teams/kaijudynamo) - [Gore Farmers](../../teams/gorefarmers) (KD+) #t2782.7 
* [Eldritch Fatality](../../teams/eldritchfatality) - [Arboreal Menace](../../teams/arborealmenace) (AM) #t2782.8
* [Filthy Tide](../../teams/filthytide) - [Irregular Cogs](../../teams/irregularcogs) (Even) #t2782.9

The Vagabonds showed signs of their GCX prowess in this battle of the last placers. ZV 3 - SR 2 [[gcxi-10-zvsr]]

The Tatters kept the pressure on the Claws and Uli got a couple more casualties. OM 0 - CT 2 [[gcxi-10-omct]]

The Furies did their best to hack and slash at the Hounds' stars, but skill (on the pitch and in the medical bay) got the Hounds back to their winning ways. GH 5 - CF 2 [[gcxi-10-ghcf]]

In the end though the Spectres managed to clog up the lanes the Wyrms needed and got a pretty convincing win, which doesn't make the Wyrms title defense look any less shaky. OW 2 - DS 4 [[gcxi-10-owds]]

The Dynamo were just better in this match and got some good work out of [[Erika]] to claim the win and stay on top of the Heaps. KD 3 - GF 0 [[gcxi-10-kdgf]]

The Fatality lost to a team that just seemed better prepared even after losing their fastest scoring threat before she had the chance to touch the ball. EF 2 - AM 4 [[gcxi-10-efam]]

The Tide got hit with the one-two punch to end the first half against the trademark attacking defense of the Cogs and then got walloped again in the second half. FT 4 - IC 7 [[gcxi-10-ftic]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 7-1-2 | Irregular Cogs | 6-1-3 | Kaiju Dynamo | 7-0-3 | Eldritch Fatality | 8-0-2 |
| Gore Farmers | 4-1-5 | Arboreal Menace | 6-1-3 | Glorious Hounds | 6-2-2 | Ravenous Eagles | 4-3-3 |
| Old Wyrms | 3-3-4 | Badger Claws | 3-2-5 | Zensun Vagabonds | 2-1-7 | Darkling Spectres | 4-0-6 |
| TC Sump Runners | 1-4-5 | Carcosan Tatters | 3-2-5 | Orbital Machine | 1-3-6 | Cackling Furies | 2-2-6 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| [[Jonah]]      | Zensun Vagabonds  |    2 |   24 |    0 |      0 |    3 |    1 |    0 |    0 |    0 |    1 |   13 |
| Lazar      | Irregular Cogs    |    4 |   28 |    1 |     -2 |    1 |    0 |    0 |    1 |    0 |    0 |   13 |
| Veens      | Filthy Tide       |    4 |   44 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |   12 |
| Ziba       | Glorious Hounds   |    4 |   41 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |   12 |
| Sacnicte   | Darkling Spectres |    2 |   27 |    1 |      2 |    1 |    0 |    0 |    1 |    0 |    1 |   12 |
| Georgina   | Arboreal Menace   |    2 |   15 |    0 |      0 |    2 |    1 |    0 |    1 |    0 |    0 |    8 |
| Priyanka   | Arboreal Menace   |    0 |    0 |    1 |      3 |    1 |    1 |    0 |    0 |    0 |    1 |    8 |
| Danae      | TC Sump Runners   |    1 |    5 |    0 |      0 |    1 |    0 |    0 |   13 |    0 |    1 |    8 |
| Ophelia    | Badger Claws      |    1 |   19 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    1 |    8 |
| Koralo     | Eldritch Fatality |    2 |   25 |    1 |     -1 |    4 |    0 |    0 |    1 |    0 |    0 |    7 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 10 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
