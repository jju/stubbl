# week 06

[Previously](week05) (and the interlude of [another round in the Champions Circuit](week05cc))

#t2778

* business storyline GH-DS [[writer]] playing for a tanking team vs a team really trying to win, ZV-CT [[aficionado]] playing more with less and how it doesn't work for the Tatters  
* player storyline RE-SR [[warreporter]] counting stats and Ekua's GP record (parallel with longevity in gangsterism), BC-AM [[writer]] Aeson vs Laurel in a battle of finesse and scoring and beauty, FT-GF [[aficionado]] Venus needs a rebound match after being stifled in the CC against the Mules
* team storyline EF-IC [[aficionado]] Drop Eagle matchup with two teams on top of their divisions, KD-OW [[writer]] the Wyrms need to start overachieving and they have the skills to do it, OM-CF [[warreporter]] rumours have it that this could be a bloodbath
* Playoffs: Now is the middle game where teams just need to hang in until the trade deadline when lineups have to be solidified. We can expect a bit of experimentation.


## matchups

* [Ravenous Eagles](../../teams/ravenouseagles) - [TC Sump Runners](../../teams/sumprunners) (Even) #t2778.1
* [Glorious Hounds](../../teams/glorioushounds) - [Darkling Spectres](../../teams/darklingspectres) (GH+) #t2778.2
* [Zensun Vagabonds](../../teams/zensunvagabonds) - [Carcosan Tatters](../../teams/carcosantatters) (Even)
* [Orbital Machine](../../teams/orbitalmachine) - [Cackling Furies](../../teams/cacklingfuries) (Even)
* [Badger Claws](../../teams/badgerclaws)  - [Arboreal Menace](../../teams/arborealmenace) (BC+) 
* [Filthy Tide](../../teams/filthytide) - [Gore Farmers](../../teams/gorefarmers) (FT+)
* [Kaiju Dynamo](../../teams/kaijudynamo) - [Old Wyrms](../../teams/oldwyrms) (OW)
* [Eldritch Fatality](../../teams/eldritchfatality) - [Irregular Cogs](../../teams/irregularcogs) (Even)



## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 3-1-1 | Irregular Cogs | 3-1-1 | Kaiju Dynamo | 3-0-2 | Eldritch Fatality | 5-0-0 |
| Old Wyrms | 1-2-1 | Arboreal Menace | 3-0-2 | Glorious Hounds | 2-2-1 | Ravenous Eagles | 3-1-2 |
| Gore Farmers | 2-1-2 | Badger Claws | 2-0-3 | Orbital Machine | 1-3-1 | Cackling Furies | 1-1-3 |
| TC Sump Runners | 0-2-4 | Carcosan Tatters | 1-2-2 | Zensun Vagabonds | 1-0-4 | Darkling Spectres | 1-0-4 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|



```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 6 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
