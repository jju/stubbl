## rushing ranks pre-GCX

| team              | total_rushing | td   | rush_td |
|-------------------|---------------|------|---------|
| Glorious Hounds   |          2827 |  198 | 14.2778 |
| Old Wyrms         |          3019 |  191 | 15.8063 |
| Zensun Vagabonds  |          2482 |  145 | 17.1172 |
| Eldritch Fatality |          2946 |  162 | 18.1852 |
| Badger Claws      |          2499 |  136 | 18.3750 |
| Irregular Cogs    |          3115 |  168 | 18.5417 |
| Filthy Tide       |          3567 |  185 | 19.2811 |
| TC Sump Runners   |          2303 |  117 | 19.6838 |
| Kaiju Dynamo      |          3217 |  157 | 20.4904 |
| Vanadium Hunters  |          1489 |   72 | 20.6806 |
| Cackling Furies   |          2091 |  100 | 20.9100 |
| Gore Farmers      |          2259 |  101 | 22.3663 |
| Darkling Spectres |          2528 |  113 | 22.3717 |
| Orbital Machine   |          2155 |   93 | 23.1720 |
| Carcosan Tatters  |          1915 |   81 | 23.6420 |
| Gargantuan Brutes |          1370 |   56 | 24.4643 |
| Ravenous Eagles   |          2055 |   79 | 26.0127 |

When delving into these numbers I actually wouldn't have guessed ahead of time that the [Glorious Hounds](../teams/glorioushounds) are the TD leader in the Pro Circuit. Their low rushing/TD ratio (GH 14.27 squares/TD) is not at all surprising for a team built around the aerial attack. Again, seeing the Old Wyrms second in the list (OW 15.81 squares/TD) isn't surprising, but the Vagabonds hitting third (ZV 17.12 squares/TD) by more than a square was.

Otherwise, these rankings are pretty much as you'd expect with the teams who just hold onto the ball taking more than 20 squares to get a TD. Also of note: the meandering path the [Ravenous Eagles](../teams/ravenouseagles) take to the end zone is actually more than an entire BludBol pitch length (RE 26.01 squares/TD vs 26 squares)

```
SELECT pl.f_tname AS team, sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing) AS total_rushing, sum(md.td) AS td, (sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing)) / sum(md.td) AS rush_td FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY rush_td ASC;
```

## touches and TDs pre-GCX

| team              | total_touches | td   | touches_td |
|-------------------|---------------|------|------------|
| Badger Claws      |           404 |  136 |     2.9706 |
| Glorious Hounds   |           746 |  198 |     3.7677 |
| Kaiju Dynamo      |           605 |  157 |     3.8535 |
| Irregular Cogs    |           659 |  168 |     3.9226 |
| Eldritch Fatality |           640 |  162 |     3.9506 |
| Filthy Tide       |           739 |  185 |     3.9946 |
| Zensun Vagabonds  |           599 |  145 |     4.1310 |
| Old Wyrms         |           795 |  191 |     4.1623 |
| Darkling Spectres |           534 |  113 |     4.7257 |
| Orbital Machine   |           445 |   93 |     4.7849 |
| TC Sump Runners   |           562 |  117 |     4.8034 |
| Cackling Furies   |           498 |  100 |     4.9800 |
| Carcosan Tatters  |           414 |   81 |     5.1111 |
| Vanadium Hunters  |           389 |   72 |     5.4028 |
| Gore Farmers      |           558 |  101 |     5.5248 |
| Ravenous Eagles   |           456 |   79 |     5.7722 |
| Gargantuan Brutes |           354 |   56 |     6.3214 |

```
SELECT pl.f_tname AS team, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td) AS td,	(sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td) AS touches_td FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY touches_td ASC;
```

The Touches stat needs a bit of explanation. In BludBol we count a "touch" of the ball whenever a player picks up, catches, intercepts, or receives a handoff. If every kickoff was caught by a player who then ran it in for a TD then we would get a Touch/TD rate of 1. That's not usually how the game is played, of course.

It is entirely unsurprising that the [Badger Claws](../teams/badgerclaws) have the lowest Touch/TD rate in the Pro Circuit (BC 2.97). Their entire modus operandi when receiving the kick has been for Cleve to get the ball, deliver it to Aeson, who scores. That's a 2.0 Touch/TD rate. When Yakup was operating a t his peak for the [Filthy Tide](../teams/filthytide) in Green Cup VII and the first UBBL Challenge, the Tide was doing very similar numbers. (FT 3.11 in GCVII vs 2.80 in the UBBL Challenge, the only tournament thus far the Tide has won)

| team        | season               | total_touches | td   | touches_td |
|-------------|----------------------|---------------|------|------------|
| Filthy Tide | UBBL Challenge III   |             1 |    0 |       NULL |
| Filthy Tide | UBBL Challenge       |            84 |   30 |     2.8000 |
| Filthy Tide | Green Cup V Memorial |            62 |   21 |     2.9524 |
| Filthy Tide | Green Cup VII        |           171 |   55 |     3.1091 |
| Filthy Tide | Green Cup VI         |           173 |   46 |     3.7609 |
| Filthy Tide | Green Cup IX         |           204 |   45 |     4.5333 |
| Filthy Tide | Green Cup VIII       |           191 |   39 |     4.8974 |

```
SELECT  pl.f_tname AS team, tours.name AS season, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches,  sum(md.td) AS td, (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td) AS touches_td FROM match_data_es AS mx  JOIN match_data AS md  ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id  JOIN players AS pl  ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id WHERE mx.f_did = 1  GROUP BY pl.f_tname, mx.f_trid  ORDER BY touches_td ASC;
```

Obviously, it's difficult to keep that sort of thing up over a team's history. The Badger Claws' GCIX season really skews things with its hyper-specialization. This is a phenomenon that seems to correlate with the scoring skill of the teams but not with their overall results (we aren't seeing the [Orbital Machine](../teams/orbitalmachine) or [Gore Farmers](../teams/gorefarmers) in the list below. Also of note is that you seem to need a certain number of veteran players to get this sort of ratio as you don't see either of the Season Sixes, when teams were finding their feet in this list.

| team              | season         | total_touches | td   | touches_td |
|-------------------|----------------|---------------|------|------------|
| Badger Claws      | Green Cup IX   |           183 |   75 |     2.4400 |
| Filthy Tide       | Green Cup VII  |           171 |   55 |     3.1091 |
| Kaiju Dynamo      | Green Cup VIII |           178 |   55 |     3.2364 |
| Old Wyrms         | Green Cup IX   |           241 |   71 |     3.3944 |
| Glorious Hounds   | Green Cup VII  |           204 |   60 |     3.4000 |
| Zensun Vagabonds  | Green Cup VII  |           163 |   47 |     3.4681 |
| Kaiju Dynamo      | Green Cup IX   |           171 |   49 |     3.4898 |
| Glorious Hounds   | Green Cup IX   |           209 |   58 |     3.6034 |
| Badger Claws      | Green Cup VIII |           221 |   61 |     3.6230 |
| Eldritch Fatality | Green Cup IX   |           204 |   56 |     3.6429 |

```
SELECT  pl.f_tname AS team, tours.name AS season, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches,  sum(md.td) AS td, (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td) AS touches_td FROM match_data_es AS mx  JOIN match_data AS md  ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id  JOIN players AS pl  ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id WHERE mx.f_did = 1  GROUP BY pl.f_tname, mx.f_trid  ORDER BY touches_td ASC LIMIT 10;
```
