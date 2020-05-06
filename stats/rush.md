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

When delving into these numbers I actually wouldn't have guessed ahead of time that the [Glorious Hounds](../teams/glorioushounds) are the TD leader in the Pro Circuit. Their low rushing/TD ratio (GH 14.27 squares/TD) is not at all surprising for a team built around the aerial attack. Again, seeing the [Old Wyrms](../teams/oldwyrms) second in the list (OW 15.81 squares/TD) isn't surprising, but the [Vagabonds](../teams/zensunvagabonds) hitting third (ZV 17.12 squares/TD) by more than a square was.

Otherwise, these rankings are pretty much as you'd expect with the teams who just hold onto the ball taking more than 20 squares to get a TD. Also of note: the meandering path the [Ravenous Eagles](../teams/ravenouseagles) take to the end zone is actually more than an entire BludBol pitch length (RE 26.01 squares/TD vs 26 squares)

```
SELECT pl.f_tname AS team, sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing) AS total_rushing, sum(md.td) AS td, (sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing)) / sum(md.td) AS rush_td FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY rush_td ASC;
```
