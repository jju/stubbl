# Farmers vs Wyrms

#t2788.5

Pick: Wyrms

Though underdogs in the standings SpreadZone has the Wyrms (2590TV) favoured in this match against the Farmers (2750TV). These teams have been playing against each other for almost as long as we've had BludBol in the Stacks. Let's check their GCXI records.

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Gore Farmers      | Green Cup XI |    5 |    2 |    8 |     15 |      40 |   23 |   32 |   1.5333 |   2.1333 |   26 |    1.7333 |     19 |   -1 |
| Old Wyrms         | Green Cup XI |    4 |    3 |    8 |     15 | 36.6667 |   36 |   45 |   2.4000 |   3.0000 |   11 |    0.7333 |    -16 |   -5 |

Both of these teams didn't have great seasons in GCXI, but it's worth noting that once their playoff berth was secure the Farmers stopped fielding very competitive teams.

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Old Wyrms         | Green Cup XI |   69 |       92 | 0.7500 |   36 | 0.5217 |          4 |   0.0435 |       9 |  0.1304 |
| Gore Farmers      | Green Cup XI |   29 |       51 | 0.5686 |   23 | 0.7931 |          4 |   0.0784 |      16 |  0.5517 |

The Wyrms were second in the league in passing this season and one would assume this is how they will be attacking. 

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Old Wyrms         | Green Cup XI |     171 |     750 |   36 | 20.8333 |       4.75 |
| Gore Farmers      | Green Cup XI |     130 |     561 |   23 | 24.3913 |       5.65 |

More Farmers have to touch the ball to score so minimizing the number of drives will be key.

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Gore Farmers      | Green Cup XI |   26 |   14 |    9 |    3 |    649 |    12 |     0.0185 |    0.0401 |        353 |     0.5439 |
| Old Wyrms         | Green Cup XI |   11 |    5 |    5 |    1 |    536 |    16 |     0.0299 |    0.0205 |        213 |     0.3974 |

The Wyrms were last in the league in Casualties inflicted so one would assume the Farmers are going to pound and pound to try and make a bit of mulch.

In their last match (back in week 2 [[gcxi-02-gfow]]) the Wyrms blazed to a 5-1 win, so they're looking for a repeat of that. 

> Weather: Nice
> Toss: GF-Receive
> Kickoffs: OW-Blitz (OW 1), OW-PerfectDefense (Half), GF-QuickSnap (OW 2), OW-CheeringFansGF (GF 1), GF-ChangingWeatherNice (OW 3), OW-ChangingWeatherNice (Final)

The Gore Farmers didn't elect to go cute and try and rely on their defence to start the match. Facing down a pretty balanced defence, they slightly loaded their left side, notably using [[Mashee]] to start instead of [[Nuru]]. When the Wyrms burst out with a blitz Kelemann and Modest launched themselves at the ball the Farmers tried to respond calmly, but SkyTripper got flustered and lost the ball, which [[Modest]] took in for a quick TD. It was looking like week 2 all over again. GF 0 - OW 1

The second drive began much like the first, but the Farmersmanaged to get the ball to Mashee up the left side with protection for a slow roll. The march got bogged down with Wyrm bodies and Mashee had to bust out to the open field, vulnerable. As expected [[Amador]] tried for the sack but [[Ros]] was ready to pick up the slack. But Amador intercepted the pass and left the Farmers down a TD going into halftime. GF 0 - OW 1

The Gore Farmers were still waiting for Ros to be able to play when they lined up to kick off the second half. The Wyrms went with a left side overload. After a deep kick and a quick snap the Wyrms had opened up their centre but looked ready to extend their lead. Elric tried to interfere with the pass for [[Olaug]] but even in traffic the wily catcher made the snag and danced away. When the Farmers converged on Olaug, Johann was in the right position to intercept the dump-off, but he was sacked and Amador got the ball to Seosamh and we started looking towards the end of the match. GF 0 - OW 2

The Farmers' fans tried to get them back into it and despite a strong assault on the cage, Mashee connected with Aemulus for a quick TD to keep them in the match. GF 1 - OW 2

The Farmers lined up an agressive defense, and the Wyrms didn't make any changes on their offense. Helmuth kicked the ball a bit too deep and the touchback for Amador, but when Rati couldn't punch a hole they shifted back to the right side where Kelemann was heading downfield. When SkyTripper tried to intercept the new passing lane he got badly hurt and the pass went through. Helmuth got the ball free but couldn't fend off all the Wyrms, who got it to Seosamh for what would seal the match. GF 1 - OW 3

The final drive had the Farmers trying to inflict casualties, and only succeeded in seriously injuring Oeneios with a foul. GF 1 - OW 3

[[gorefarmers]][[oldwyrms]][[gcxi]]

#playoff #upset 

| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1567" ORDER BY pl.f_tname, pl.nr;
```


Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

OW 8 Wins (1 BYE 1 Playoff)
GF 7 Wins (2 Playoff)
1 Draw

* Green Cup I - 3 - Gore Farmers 0 **Old Wyrms** 3
* Green Cup I - 9 - Gore Farmers 2 **Old Wyrms** 5
* Green Cup III - 8 - Old Wyrms 1 **Gore Farmers** 2
* Green Cup IV - 9 - **Gore Farmers** 2 Old Wyrms 0
* Green Cup VI - 1 - **Gore Farmers** 2 Old Wyrms 1
* Green Cup VI - 10 - Old Wyrms 1 **Gore Farmers** 2
* Green Cup VI - SF - **Gore Farmers** 2 Old Wyrms 1
* Green Cup VII - 3 - Gore Farmers 1 **Old Wyrms** 4
* Green Cup VIII - 4 - Gore Farmers 2 Old Wyrms 2
* Green Cup VIII - R16 - **Gore Farmers** 3 Old Wyrms 0
* Green Cup IX - 3 - **Old Wyrms** 4 Gore Farmers 2
* Green Cup IX - BYE - **Old Wyrms** 1 Gore Farmers 0
* Green Cup V Memorial - 7 - Gore Farmers 1 **Old Wyrms** 3
* Green Cup X - 3 - **Gore Farmers** 4 Old Wyrms 1
* Green Cup X - QF - **Old Wyrms** 3 Gore Farmers 1
* Green Cup XI - 2 - Gore Farmers 1 **Old Wyrms** 5