# playoffs first round

[Previously](week15)
[Concurrently](../ogiii/week11)

#t2788

So we begin the playoffs for the Eleventh Green Cup. The Cackling Furies have some legitimate grievances against the current playoff structure as their regular season record was better than *three* teams which did get to move on. There is talk that along with a four-team expansion for GCXII, there will be wild-card seeding within each conference.



The Dynamo are favoured to beat the lowly Vagabonds

* business storyline: [[warreporter]] [[aficionado]] [[writer]]
* player storyline: [[warreporter]] [[aficionado]] [[writer]]
* team storyline:[[warreporter]] [[aficionado]] [[writer]]
* Playoffs: see above


## matchups


* [Kaiju Dynamo](../../teams/kaijudynamo) - [Zensun Vagabonds](../../teams/zensunvagabonds) (KD)
* [Gore Farmers](../../teams/gorefarmers) - [Old Wyrms](../../teams/oldwyrms) (OW)
* [Darkling Spectres](../../teams/darklingspectres) - [Ravenous Eagles](../../teams/ravenouseagles) (Even)
* [Irregular Cogs](../../teams/irregularcogs) - [Carcosan Tatters](../../teams/carcosantatters) (IC)

The Vagabonds got a huge upset, but will be without their Heavy [[Zaira]] when they face the Hounds in the Quarterfinals. The Dynamo have to be disappointed at the way their so-promising season fizzled. KD 3 - ZV 4 [[gcxi-16-kdzv]]

The Wyrms played like defending champions and seem to have their hearts set on the three-peat despite a poor regular season showing. The Tide can't be happy about having to deal with this team on the upswing. GF 1 - OW 3 [[gcxi-16-gfow]]

The Spectres defeated the Eagles in a tense nail-biting match that almost seemed destined for overtime, but was won on a drive where it felt like everyone touched the ball, and Ragnar was martyred out of it. [[gcxi-16-dsre]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| **Filthy Tide** | 10-2-3 | **Arboreal Menace** | 9-2-4 | **Glorious Hounds** | 9-4-2 | **Eldritch Fatality** | 11-0-4 |
| *Gore Farmers* | 5-2-8 | Irregular Cogs | 8-2-5 | *Kaiju Dynamo* | 10-1-4 | Darkling Spectres | 7-1-7 |
| Old Wyrms | 4-3-8 | *Carcosan Tatters* | 7-2-6 | Zensun Vagabonds | 4-2-9 | *Ravenous Eagles* | 5-3-7 |
| *TC Sump Runners* | 1-4-10 | *Badger Claws* | 5-4-6 | *Orbital Machine* | 1-6-8 | *Cackling Furies* | 5-2-8 |


## player of the week standings

| Player    | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|-----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Arya       | Carcosan Tatters |    2 |   30 |    1 |      1 |    3 |    0 |    0 |    1 |    0 |    1 |   12 |
| Vusala     | Arboreal Menace  |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    2 |   10 |
| Othniel    | Filthy Tide      |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    2 |   10 |
| Hrolfr     | Irregular Cogs   |    1 |   35 |    1 |      4 |    0 |    0 |    0 |    2 |    0 |    1 |    9 |
| Mia        | Zensun Vagabonds |    2 |    7 |    0 |      0 |    2 |    0 |    1 |    6 |    0 |    0 |    8 |
| Chibueze   | Ravenous Eagles  |    0 |    0 |    0 |      0 |    0 |    1 |    0 |    5 |    1 |    1 |    7 |
| RockLobber | Gore Farmers     |    0 |    0 |    0 |      0 |    0 |    0 |    1 |   10 |    0 |    1 |    7 |
| Jia        | Old Wyrms        |    0 |    3 |    1 |      7 |    0 |    0 |    0 |    0 |    0 |    1 |    6 |
| Frans      | Irregular Cogs   |    1 |   20 |    1 |      1 |    1 |    0 |    1 |    3 |    0 |    0 |    6 |
| Fidolio    | Kaiju Dynamo     |    2 |   27 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    6 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 251 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
