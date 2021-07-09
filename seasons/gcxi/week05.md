# week 05

[Previously](week04) 
#t2776

* business storyline FT-DS [[aficionado]] the logic of the tank vs a team really trying to win, RE-KD [[writer]] those new players just sitting there waiting (with the prize money from the CC at stake the Eagles really would like to get in), GF-OM [[warreporter]] the rivalry behind the ownership groups (aficionados vs pragmatist gangsetrs) and how it plays out on the field,  
* player storyline CT-BC [[writer]] Aeson's continued return and how the partnership with Klim plays out especially after a lacklustre performance in Week 4, CF-EF [[aficionado]] new rookie Koralo, RE-KD [[warreporter]] injuries from Jantine
* team storyline OW-GH [[writer]] can the Hounds swagger match up with their results, GF-OM [[warreporter]] Farmers had a bad match against a bashing team maybe they can turn it around? [[aficionado]] Tatters bouncing back and can they stop the intense run again? [[aficionado]] IC-ZV another throwback rivalry O8 matchup
* Champions Circuit: The Fatality have a lock on facing the Raptors in the Champions Circuit and the team they are facing is merely trying to stay out of the division's basement so CF-EF has no standings interest. The Hounds can clinch second place with a win against the Wyrms regardless of the rest of the matches (they can also sneak in with a loss if there are a flurry of ties. KD AM and GF could possibly get into the CC with a win (the AM are playing the SR so this should almost be a guarantee), but they would require losses from the RE FT and IC. KD has the best shot at this since they are playing the Eagles, and the IC have the toughest opponents in the ZV, but if the AM win the KD are mostly out of luck.


## matchups

* [Arboreal Menace](../../teams/arborealmenace) - [TC Sump Runners](../../teams/sumprunners) (AR+) #t2776.1
* [Darkling Spectres](../../teams/darklingspectres) - [Filthy Tide](../../teams/filthytide) (FT+) #t2776.2
* [Carcosan Tatters](../../teams/carcosantatters) - [Badger Claws](../../teams/badgerclaws) (BC) #t2776.3
* [Cackling Furies](../../teams/cacklingfuries) - [Eldritch Fatality](../../teams/eldritchfatality) (EF) #t2776.4
* [Gore Farmers](../../teams/gorefarmers)  - [Orbital Machine](../../teams/orbitalmachine) (GF) #t2776.5
* [Irregular Cogs](../../teams/irregularcogs) - [Zensun Vagabonds](../../teams/zensunvagabonds) (IC) #t2776.7
* [Old Wyrms](../../teams/oldwyrms) - [Glorious Hounds](../../teams/glorioushounds) (OW) #t2776.8
* [Ravenous Eagles](../../teams/ravenouseagles) - [Kaiju Dynamo](../../teams/kaijudynamo) (KD) #t2776.9

[[]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 3-1-1 | Irregular Cogs | 2-1-1 | Glorious Hounds | 2-2-0 | Eldritch Fatality | 4-0-0 |
| Gore Farmers | 2-0-2 | Arboreal Menace | 3-0-2 | Kaiju Dynamo | 2-0-2 | Ravenous Eagles | 2-1-1 |
| Old Wyrms | 1-2-1 | Badger Claws | 2-0-3 | Orbital Machine | 1-2-1 | Cackling Furies | 1-1-2 |
| TC Sump Runners | 0-2-3 | Carcosan Tatters | 1-2-2 | Zensun Vagabonds | 1-0-3 | Darkling Spectres | 1-0-4 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|



```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 5 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
