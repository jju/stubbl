# playoffs - divisional finals

[Previously](week16)
[Concurrently](../ogiii/week12-quarterfinals)

#t2789

[next week](week18-conffinals)

A change in the record-keeping means that the regular season divisional winners are awarded the divisional titles now, so the only thing up for grabs in this round is the ability to play more BludBol. In the previous week we had two upsets and two expected results.

* business storyline: [[warreporter]] [[aficionado]] [[writer]]
* player storyline: [[warreporter]] [[aficionado]] [[writer]]
* team storyline:[[warreporter]] [[aficionado]] [[writer]]
* Playoffs: see above


## matchups

* [Glorious Hounds](../../teams/glorioushounds) - [Zensun Vagabonds](../../teams/zensunvagabonds) (GH)
* [Filthy Tide](../../teams/filthytide) - [Old Wyrms](../../teams/oldwyrms) (OW)
* [Arboreal Menace](../../teams/arbrealmenace) - [Irregular Cogs](../../teams/irregularcogs) (AM)
* [Eldritch Fatality](../../teams/eldritchfatality) - [Darkling Spectres](../../teams/darklingspectres) (EF)

The score doesn't reflect how much the result was never in doubt for this one, and the Hounds are on their way to the Classic Conference Final. GH 3 - ZV 2 [[gcxi-17-ghzv]]

There will be no three-peat for the Wyrms as the Filthy Tide won their thrilling matchup to head for the Burger Conference Final. FT 3 - OW 2 [[gcxi-17-ftow]]

And now we know we'll have a new winner of the Green Cup, as the Cogs lost in a thrilling OT battle. AM 3 - IC 2 OT [[gcxi-17-amic]]

The Fatality made it a sweep for the Divisional Champions in the Quarterfinal round. The Spectres were hampered by the weather and never got anything going in a near-repeat of their week 3 matchup. EF 4 - DS 0 [[gcxi-17-efds]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| **Filthy Tide** | 10-2-3 | **Arboreal Menace** | 9-2-4 | **Glorious Hounds** | 9-4-2 | **Eldritch Fatality** | 11-0-4 |
| *Gore Farmers* | 5-2-8 | *Irregular Cogs* | 8-2-5 | *Kaiju Dynamo* | 10-1-4 | *Darkling Spectres* | 7-1-7 |
| *Old Wyrms* | 4-3-8 | *Carcosan Tatters* | 7-2-6 | *Zensun Vagabonds* | 4-2-9 | *Ravenous Eagles* | 5-3-7 |
| *TC Sump Runners* | 1-4-10 | *Badger Claws* | 5-4-6 | *Orbital Machine* | 1-6-8 | *Cackling Furies* | 5-2-8 |


## player of the week standings

| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Georgina | Arboreal Menace   |    1 |    8 |    0 |      0 |    0 |    1 |    0 |    0 |    0 |    1 |   10 |
| Hrolfr   | Irregular Cogs    |    2 |   43 |    1 |      6 |    0 |    0 |    1 |    0 |    0 |    0 |    9 |
| Venus    | Filthy Tide       |    3 |   32 |    0 |      0 |    4 |    0 |    0 |    0 |    0 |    0 |    9 |
| Amador   | Old Wyrms         |    1 |   10 |    0 |      0 |    2 |    0 |    0 |    2 |    0 |    1 |    8 |
| Grumman  | Irregular Cogs    |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    6 |    0 |    1 |    7 |
| Laurel   | Arboreal Menace   |    2 |   37 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |    6 |
| Clydon   | Zensun Vagabonds  |    0 |    6 |    1 |      4 |    0 |    0 |    0 |    0 |    0 |    1 |    6 |
| Beatrix  | Eldritch Fatality |    2 |   13 |    0 |      0 |    1 |    0 |    0 |    2 |    0 |    0 |    6 |
| Ziba     | Glorious Hounds   |    2 |   12 |    0 |      0 |    1 |    0 |    0 |    0 |    0 |    0 |    6 |
| Mia      | Zensun Vagabonds  |    1 |    0 |    0 |      0 |    1 |    0 |    1 |    5 |    0 |    0 |    5 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 252 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
