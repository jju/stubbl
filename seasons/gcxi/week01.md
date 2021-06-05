# week 01

[Previously in the preseason](preseason) #t2760

* business storyline DS-GF [[aficionado]]
* player storyline FT-AR [[writer]] or RE-ZV [[aficionado]] or BC-EF (dud bc Aeson does sit it out) [[writer]] or OW-CF [[warreporter]]
* team GH-CT (how do the Hounds do coming off a tournament win?) [[writer]] OM-SR (no fans vs bad team) [[warreporter]] KD-IC [[aficionado]] (interesting tactical choices)


## matchups

* [Ravenous Eagles](../teams/ravenouseagles) - [Zensun Vagabonds](../teams/zensunvagabonds) (ZV)
* [Darkling Spectres](../teams/darklingspectres) - [Gore Farmers](../teams/gorefarmers) (DS?!)
* [Old Wyrms](../teams/oldwyrms) - [Cackling Furies](../teams/cacklingfuries) (OW)
* [Kaiju Dynamo](../teams/kaijudynamo) - [Irregular Cogs](../teams/irregularcogs) (Even)
* [Glorious Hounds](../teams/glorioushounds) - [Carcosan Tatters](../teams/carcosantatters) (CT)
* [Filthy Tide](../teams/filthytide) - [Arboreal Menace](../teams/arborealmenace) (AR)
* [Orbital Machine](../teams/orbitalmachine) - [TC Sump Runners](../teams/sumprunners) (Even)
* [Eldritch Fatality](../teams/eldritchfatality) - [Badger Claws](../teams/badgerclaws) (BC)

It is crazy that spreadZone were giving odds in favour of the Spectres winning this match. No seriously, what are you thinking? Give the Gore Farmers credit though, they fielded a strong lineup. The Farmers are never great for a quote but [Sky Tripper](../players/skytripper) [[skytripper]] said they were just trying to win and he wouldn't be baited into commentary on the team's tanky tendencies in the past. You could barely tell who was who in the Spectres' half of the field.

Farmers got a nice and easy TD and then pushed the rookie [[Melite]] out of bounds as ball carrier, effectively ending the drive. [[RockLobber]] got badly hurt by the freebooting chainsaw wielding maniac. [Gojko](../players/gojko) [[gojko]]'s botched pickup off the kick wasn't immediately harmful, but [Zdravko](../players/zdravko) [[zdravko]] botched the catch on the try-again pass. [Aemulus](../players/aemulus) [[aemulus]] smashed the rookie [[Melite]]'s hip closing the trap on the left-hand drive the Spectres had been trying, but then Gojko busted loose and Zdravko shovelled it back to him and they were down the right side and tying it up with only a quarter of the match remaining. [[Aethelraed]] got a gouged eye and will be sitting out against the Wyrms in Week 2. But the Farmers stayed cool and [[Ros]] got the ball to Aemulus who partnered up with [[Sylvester]] for protection (which they needed as Gojko made a last-ditch attack on the ball) as they ran down the clock. DS 1 - GF 2

> Weather: Nice
> Toss: GF
> Kickoffs: DS-Changing Weather, GF-Quick Snap, GF-High Kick, DS-Pitch Invasion


## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| Gore Farmers | 1-0-0 | Arboreal Menace | 0-0-0 | Glorious Hounds | 0-0-0 | Eldritch Fatality | 0-0-0 |
| Filthy Tide | 0-0-0 | Badger Claws | 0-0-0 | Orbital Machine | 0-0-0 | Ravenous Eagles | 0-0-0 |
| Old Wyrms | 0-0-0 | Irregular Cogs | 0-0-0 | Kaiju Dynamo | 0-0-0 | Cackling Furies | 0-0-0 |
| TC Sump Runners | 0-0-0 | Carcosan Tatters | 0-0-0 | Zensun Vagabonds | 0-0-0 | Darkling Spectres | 0-0-1 |

## player of the week standings

| Player            | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-------------------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 1 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
