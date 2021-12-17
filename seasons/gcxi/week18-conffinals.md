# playoffs - conference finals

[Previously](week17-divfinals)
[Concurrently](../ogiii/week13-semifinals)

#t2790

[next week](week19-greencup)

The division winners swept the quarterfinal round and the winner of the Green Cup will be from among the season's four winningest teams.  
  
Fighting to represent the Burger Conference we have an Original 8 team vs the newest Green Cup competitor in the Filthy Tide vs Arboreal Menace. SpreadZone gives the edge to the Menace.  
  
In the Classic Conference we have the team with the most wins taking on the team with the fewest losses in the Eldritch Fatality vs the Glorious Hounds. SpreadZone is picking  the Hounds.

This season is the first since GCVI where we have all the regular season division champs in the conference finals (and if you count GCVI and GCC06 as being two halves of one season, then that didn't even happen then). GCX had the Eagles and Claws in as upsets; GCIX had the Hounds and Claws; GCVIII (pre-divisional reshuffle) had the Farmers (eventual champs) and Claws; GCVII had the Fatality and Eagles (Cup champions) and GCC06 had the Orbital Machine (who won it all).

* business storyline: [[warreporter]] [[aficionado]] [[writer]]
* player storyline: [[warreporter]] [[aficionado]] [[writer]]
* team storyline:[[warreporter]] [[aficionado]] [[writer]]
* Playoffs: see above


## matchups

* [Filthy Tide](../../teams/filthytide) - [Arboreal Menace](../../teams/arbrealmenace) (AM)
* [Eldritch Fatality](../../teams/eldritchfatality) - [Glorious Hounds](../../teams/glorioushounds) (GH)

The Hounds got their win in a much more thrilling match than in Week 15 and are bound for the Green Cup. EF 3 - GH 4 (OT) [[gcxi-18-efgh]]

The Tide have finally made it to the big dance in a gutsy tense 3/4 of a match, they didn't let up and beat the favoured Menace. FT 5 - AM 3 [[gcxi-18-ftam]]

## standings

| Stacks | W-D-L | Outlands | W-D-L | Heaps | W-D-L | Pits | W-D-L |
|-------|-----|--|--|------|------|--|--|
| **Filthy Tide** | 13-2-3 | *Arboreal Menace* | 11-2-5 | **Glorious Hounds** | 12-4-2 | *Eldritch Fatality* | 13-0-5 |
| *Old Wyrms* | 5-3-9 | *Irregular Cogs* | 9-2-6 | *Kaiju Dynamo* | 10-1-5 | *Darkling Spectres* | 8-1-8 |
| *Gore Farmers* | 5-2-9 | *Carcosan Tatters* | 7-2-7 | *Zensun Vagabonds* | 5-2-10 | *Ravenous Eagles* | 5-3-7 |
| *TC Sump Runners* | 1-4-11 | *Badger Claws* | 4-4-8 | *Orbital Machine* | 1-6-9 | *Cackling Furies* | 5-2-9 |


## player of the week standings

| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Venus    | Filthy Tide       |    4 |   22 |    0 |      0 |    3 |    0 |    0 |    0 |    0 |    0 |   12 |
| Ziba     | Glorious Hounds   |    4 |   38 |    0 |      0 |    4 |    0 |    0 |    0 |    0 |    0 |   12 |
| Beatrix  | Eldritch Fatality |    0 |   10 |    2 |      9 |    1 |    0 |    1 |    5 |    1 |    1 |    9 |
| Georgina | Arboreal Menace   |    1 |   32 |    0 |      0 |    3 |    0 |    0 |    1 |    0 |    1 |    8 |
| Betul    | Eldritch Fatality |    2 |   25 |    0 |      0 |    2 |    1 |    0 |    0 |    0 |    0 |    8 |
| Laurel   | Arboreal Menace   |    2 |   27 |    0 |      0 |    1 |    1 |    0 |    0 |    0 |    0 |    8 |
| Milica   | Filthy Tide       |    0 |   22 |    2 |      1 |    0 |    0 |    0 |    1 |    0 |    1 |    7 |
| Borarinn | Arboreal Menace   |    0 |    0 |    0 |      0 |    0 |    0 |    1 |    3 |    0 |    1 |    7 |
| Filipa   | Eldritch Fatality |    0 |    7 |    4 |      8 |    1 |    1 |    0 |    0 |    0 |    0 |    6 |
| Florinda | Glorious Hounds   |    0 |    0 |    0 |      0 |    0 |    0 |    3 |   10 |    0 |    0 |    6 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup XI" AND mt.round = 253 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
