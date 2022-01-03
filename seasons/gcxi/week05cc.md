# champions circuit round 2

[Previously](seasons/gcxi/week05.md) 
#t2777

The Champions Circuit was designed as a showcase for the top 3 teams in the Green Cup and Orange Goblet tournaments, but with ongoing negotiations over league amalgamations there was a decision to step up the excitement and offer a bit of cash for a 1/3 of the way through the Green Cup version before the third Orange Goblet tournament begins.


## matchups

* [Irregular Cogs](../../teams/irregularcogs) - [Gladiolas](../../teams/gladiolas) #t2777.5
* [Filthy Tide](../../teams/filthytide) - [Mules](kickingmules.md) #t2777.7
* [Raptors](virtuaraptors.md) - [Eldritch Fatality](../../teams/eldritchfatality) #t2777.9

The Cogs decided to give [[besz]] one last kick at the ball before her retirement in this exhibition match.


## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Filthy Tide | 3-1-1 | Irregular Cogs | 3-1-1 | Kaiju Dynamo | 3-0-2 | Eldritch Fatality | 5-0-0 |
| Old Wyrms | 1-2-1 | Arboreal Menace | 3-0-2 | Glorious Hounds | 2-2-1 | Ravenous Eagles | 2-1-2 |
| Gore Farmers | 2-1-2 | Badger Claws | 2-0-3 | Orbital Machine | 1-3-1 | Cackling Furies | 1-1-3 |
| TC Sump Runners | 0-2-3 | Carcosan Tatters | 1-2-2 | Zensun Vagabonds | 1-0-4 | Darkling Spectres | 1-0-4 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|



```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Champions Circuit" AND mt.round = 2 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
