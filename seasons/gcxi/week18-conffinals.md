# playoffs - conference finals

[Previously](week17-divfinals)
[Concurrently](../ogiii/week13-semifinals)

#t2790


* business storyline: [[warreporter]] [[aficionado]] [[writer]]
* player storyline: [[warreporter]] [[aficionado]] [[writer]]
* team storyline:[[warreporter]] [[aficionado]] [[writer]]
* Playoffs: see above


## matchups

* [Filthy Tide](../../teams/filthytide) - [Arboreal Menace](../../teams/arbrealmenace) (AM)
* [Eldritch Fatality](../../teams/eldritchfatality) - [Glorious Hounds](../../teams/glorioushounds) (GH)


## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| **Filthy Tide** | 12-2-3 | **Arboreal Menace** | 11-2-4 | **Glorious Hounds** | 11-4-2 | **Eldritch Fatality** | 13-0-4 |
| *Old Wyrms* | 5-3-9 | *Irregular Cogs* | 9-2-6 | *Kaiju Dynamo* | 10-1-5 | *Darkling Spectres* | 8-1-8 |
| *Gore Farmers* | 5-2-9 | *Carcosan Tatters* | 7-2-7 | *Zensun Vagabonds* | 5-2-10 | *Ravenous Eagles* | 5-3-7 |
| *TC Sump Runners* | 1-4-11 | *Badger Claws* | 4-4-8 | *Orbital Machine* | 1-6-9 | *Cackling Furies* | 5-2-9 |


## player of the week standings

| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 253 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
