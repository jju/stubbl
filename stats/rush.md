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
SELECT pl.f_tname AS team, sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing) AS total_rushing, sum(md.td) AS td, (sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing)) / sum(md.td) AS rush_td 
FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1 
GROUP BY pl.f_tname 
ORDER BY rush_td ASC;
```

## touches and TDs pre-GCX

| team              | total_touches | td   | touches_td |
|-------------------|---------------|------|------------|
| Mules             |             6 |    2 |       3.00 |
| Badger Claws      |           659 |  209 |       3.15 |
| Arboreal Menace   |           215 |   58 |       3.71 |
| Irregular Cogs    |           852 |  224 |       3.80 |
| Eldritch Fatality |           827 |  216 |       3.83 |
| Glorious Hounds   |           975 |  251 |       3.88 |
| Kaiju Dynamo      |           781 |  201 |       3.89 |
| Filthy Tide       |           983 |  251 |       3.92 |
| Old Wyrms         |          1058 |  262 |       4.04 |
| Zensun Vagabonds  |           829 |  201 |       4.12 |
| Thorns            |             9 |    2 |       4.50 |
| Darkling Spectres |           693 |  151 |       4.59 |
| Cackling Furies   |           716 |  152 |       4.71 |
| Orbital Machine   |           602 |  126 |       4.78 |
| Carcosan Tatters  |           545 |  113 |       4.82 |
| Gladiolas         |            10 |    2 |       5.00 |
| TC Sump Runners   |           768 |  148 |       5.19 |
| Ravenous Eagles   |           615 |  114 |       5.39 |
| Vanadium Hunters  |           389 |   72 |       5.40 |
| Gore Farmers      |           785 |  136 |       5.77 |
| Gargantuan Brutes |           354 |   56 |       6.32 |



```
SELECT pl.f_tname AS team, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td) AS td,round(((sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td)),2) AS touches_td  FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id  WHERE md.f_did = 1  GROUP BY pl.f_tname  ORDER BY touches_td ASC;
```

The Touches stat needs a bit of explanation. In BludBol we count a "touch" of the ball whenever a player picks up, catches, intercepts, or receives a handoff. If every kickoff was caught by a player who then ran it in for a TD then we would get a Touch/TD rate of 1. That's not usually how the game is played, of course.

It is entirely unsurprising that the [Badger Claws](../teams/badgerclaws) have the lowest Touch/TD rate in the Pro Circuit (BC 3.11 though this is up a bit from their 2.97 before GCX). Their entire modus operandi when receiving the kick has been for Cleve to get the ball, deliver it to Aeson, who scores. That's a 2.0 Touch/TD rate. When Yakup was operating at his peak for the [Filthy Tide](../teams/filthytide) in Green Cup VII and the first UBBL Challenge, the Tide was doing very similar numbers. (FT 3.11 in GCVII vs 2.80 in the UBBL Challenge, the only tournament thus far the Tide has won)

| team        | season               | total_touches | td   | touches_td |
|-------------|----------------------|---------------|------|------------|
| Filthy Tide | UBBL Challenge III   |             1 |    0 |       NULL |
| Filthy Tide | UBBL Challenge       |            84 |   30 |     2.8000 |
| Filthy Tide | Green Cup V Memorial |            62 |   21 |     2.9524 |
| Filthy Tide | Green Cup VII        |           171 |   55 |     3.1091 |
| Filthy Tide | Green Cup VI         |           173 |   46 |     3.7609 |
| Filthy Tide | Green Cup X          |           196 |   50 |     3.9200 |
| Filthy Tide | Green Cup IX         |           204 |   45 |     4.5333 |
| Filthy Tide | Green Cup VIII       |           191 |   39 |     4.8974 |

```
SELECT  pl.f_tname AS team, tours.name AS season, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches,  sum(md.td) AS td, (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td) AS touches_td 
FROM match_data_es AS mx  JOIN match_data AS md  ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id  JOIN players AS pl  ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id 
WHERE mx.f_did = 1  
GROUP BY pl.f_tname, mx.f_trid  
ORDER BY touches_td ASC;
```

Obviously, it's difficult to keep that sort of thing up over a team's history. The Badger Claws' GCIX season really skews things with its hyper-specialization. This is a phenomenon that seems to correlate with the scoring skill of the teams but not with their overall results (we aren't seeing the [Orbital Machine](../teams/orbitalmachine) or [Gore Farmers](../teams/gorefarmers) in the list below. Also of note is that you seem to need a certain number of veteran players to get this sort of ratio as you don't see either of the Season Sixes, when teams were finding their feet in this list.

| team              | season         | total_touches | td   | touches_td |
|-------------------|----------------|---------------|------|------------|
| Ravenous Eagles   | Champions Circuit |             2 |    1 |       2.00 |
| Badger Claws      | Green Cup IX      |           183 |   75 |       2.44 |
| Mules             | Champions Circuit |             6 |    2 |       3.00 |
| Filthy Tide       | Green Cup XI      |            48 |   16 |       3.00 |
| Old Wyrms         | Champions Circuit |             3 |    1 |       3.00 |
| Filthy Tide       | Green Cup VII     |           171 |   55 |       3.11 |
| Eldritch Fatality | Green Cup XI      |            51 |   16 |       3.19 |
| Kaiju Dynamo      | Green Cup VIII    |           178 |   55 |       3.24 |
| Irregular Cogs    | Green Cup X       |           161 |   48 |       3.35 |
| Old Wyrms         | Green Cup IX      |           241 |   71 |       3.39 |


```
SELECT  pl.f_tname AS team, tours.name AS season, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches,  sum(md.td) AS td, round(((sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td)),2) AS touches_td 
FROM match_data_es AS mx  JOIN match_data AS md  ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id  JOIN players AS pl  ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id 
WHERE mx.f_did = 1 
GROUP BY pl.f_tname, mx.f_trid  
ORDER BY touches_td ASC 
LIMIT 10;
```
# player stats

| name        | team          | gp | total_touches | sum(md.td) | tds_touch |
|-------------|------------------|----|---------------|------------|-----------|
| **Aeson**     | Badger Claws      | 56 |           159 |        141 |      0.89 |
| Costache | Glorious Hounds   | 46 |           101 |         74 |      0.73 |
| Souta    | Old Wyrms         | 60 |           157 |         65 |      0.41 |
| Sabah    | Kaiju Dynamo      | 48 |            81 |         61 |      0.75 |
| Yakup    | Filthy Tide       | 42 |            74 |         55 |      0.74 |
| **Veens**     | Filthy Tide       | 18 |            57 |         46 |      0.81 |
| **Atte**      | Eldritch Fatality | 37 |            80 |         44 |      0.55 |
| Dragos   | Irregular Cogs    | 53 |            67 |         35 |      0.52 |
| **Rickon**    | Cackling Furies   | 42 |            78 |         35 |      0.45 |
| Donat    | Badger Claws      | 33 |            54 |         35 |      0.65 |

```
SELECT pl.name, pl.f_tname, count(DISTINCT md.f_match_id) AS gp, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td), round(sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)),2) AS tds_touch FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE mx.f_did = 1 GROUP BY pl.name, pl.f_tname ORDER BY sum(md.td) DESC, gp DESC LIMIT 10;
```

These are the top scorers in the Pro Circuit, along with their reliability rating. How good is Aeson? 89% of the time he gets the ball, he scores. The only players more "reliable" are bashers who never ever touch the ball but for one spectacular moment.

| name       | team           | gp | total_touches | sum(md.td) | tds_touch |
|------------|-------------------|----|---------------|------------|-----------|
| **Florrie**    | Darkling Spectres | 78 |             1 |          1 |    1.0000 |
| TallHexer | Gore Farmers      | 51 |             1 |          1 |    1.0000 |
| Noir      | TC Sump Runners   | 49 |             1 |          1 |    1.0000 |
| Rivet     | Orbital Machine   | 42 |             1 |          1 |    1.0000 |
| **Percy**      | Ravenous Eagles   | 40 |             1 |          1 |    1.0000 |
| **Zaira**      | Zensun Vagabonds  | 33 |             1 |          1 |    1.0000 |
| **Hamza**      | Zensun Vagabonds  | 32 |             1 |          1 |    1.0000 |
| **Odalric**    | Orbital Machine   | 32 |             3 |          3 |    1.0000 |
| **Hadassah**   | Filthy Tide       | 25 |             1 |          1 |    1.0000 |
| Horymir   | Filthy Tide       | 19 |             1 |          1 |    1.0000 |
| Ioana     | Orbital Machine   | 16 |             2 |          2 |    1.0000 |
| Dian      | Filthy Tide       | 14 |             1 |          1 |    1.0000 |
| **Eimilios**   | Old Wyrms         | 14 |             3 |          3 |    1.0000 |
| **Corinne**    | Orbital Machine   |  8 |             2 |          2 |    1.0000 |
| Tatjana   | TC Sump Runners   |  7 |             1 |          1 |    1.0000 |
| **Hachiro**    | Gargantuan Brutes |  1 |             2 |          2 |    1.0000 |
| Phemie    | Glorious Hounds   |  1 |             2 |          2 |    1.0000 |
| **Sukhdeep**   | Thorns            |  1 |             1 |          1 |    1.0000 |
| **Chikondi**   | Ravenous Eagles   | 68 |            10 |          9 |    0.9000 |
| **Aeson**      | Badger Claws      | 54 |           155 |        138 |    0.8903 |


There are a few players in the Pros who've made a big impact in non-obvious ways. The top 15 players in the above chart are players who, the only times they touched the ball managed to score. Odalric and Eimilios have both done it 3 times.

```
SELECT pl.name, pl.f_tname, count(DISTINCT md.f_match_id) AS gp, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td), sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) AS tds_touch 
FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id 
WHERE mx.f_did = 1
GROUP BY pl.name, pl.f_tname 
ORDER BY tds_touch DESC, gp DESC 
LIMIT 20;
```

Conversely, let's look at the players who've touched the ball a whole lot in the Pros but never ever scored.

| player      | team              | gp | total_touches | sum(md.td) | tds_touch |
|-------------|-------------------|----|---------------|------------|-----------|
| **Elvis**       | Old Wyrms         | 52 |           181 |          0 |    0.0000 |
| **Cleve**       | Badger Claws      | 44 |           158 |          0 |    0.0000 |
| **Melchor**     | Vanadium Hunters  | 33 |            89 |          0 |    0.0000 |
| **Evander**     | Old Wyrms         | 32 |            72 |          0 |    0.0000 |
| Mutasim    | TC Sump Runners   | 18 |            64 |          0 |    0.0000 |
| **Consolo**     | Badger Claws      | 19 |            64 |          0 |    0.0000 |
| Vlad       | Gargantuan Brutes | 25 |            57 |          0 |    0.0000 |
| Garth      | TC Sump Runners   | 16 |            52 |          0 |    0.0000 |
| GutTwister | Gore Farmers      | 17 |            38 |          0 |    0.0000 |
| Hartwin    | Arboreal Menace   |  9 |            29 |          0 |    0.0000 |

Most of these could find the endzone at some point, but the fact that the [Gargantuan Brutes](../teams/gargantuanbrutes) have now folded makes Vlad's achievement of 25 matches over three seasons and 57 touches the saddest. Elvis has moved up in these ranks, which you would imagine he's going to want to keep going at least until he passes [[yosif]] on the all-time passing leaderboard.

```
SELECT pl.name AS player, pl.f_tname AS team, count(DISTINCT md.f_match_id) AS gp, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td), sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) AS tds_touch 
FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1
GROUP BY pl.name, pl.f_tname 
HAVING sum(md.td) = 0 AND total_touches >0 
ORDER BY total_touches DESC 
limit 10;
```
