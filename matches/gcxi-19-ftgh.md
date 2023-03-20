# Tide vs Hounds

#t2791.9

Pick: Hounds

The Glorious Hounds (2330TV) and the Filthy Tide (2290TV) square off in a Green Cup both have been longing to see for a long time. Both of these teams have won an UBBL Challenge, but the big trophy hasn't made it to either of them yet.

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Filthy Tide       | Green Cup XI |   13 |    2 |    3 |     18 | 77.7778 |   80 |   58 |   4.4444 |   3.2222 |   11 |    0.6111 |    -24 |    2 |
| Glorious Hounds   | Green Cup XI |   12 |    4 |    2 |     18 | 77.7778 |   80 |   49 |   4.4444 |   2.7222 |   17 |    0.9444 |    -14 |    0 |

Again we see the Hounds take on a team with an identical win%. Throughout the season they scored the exact same number of TDs, but the Hounds had a better defense and inflicted more casualties. Both teams have a 12-player roster, so exactly one sub if things go poorly.

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Glorious Hounds   | Green Cup XI |   91 |      120 | 0.7583 |   79 | 0.8681 |          3 |   0.0250 |      17 |  0.1868 |
| Filthy Tide       | Green Cup XI |   66 |       96 | 0.6875 |   79 | 1.1970 |          4 |   0.0417 |      33 |  0.5000 |

| Team            | Player       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-----------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Glorious Hounds | Oxana        |   51 |   58 | 0.8793 |    0 | 0.0000 |          1 |   0.0172 |       3 |  0.0588 |
| Filthy Tide     | Aleksy       |   38 |   47 | 0.8085 |    0 |  0.0000 |          1 |   0.0213 |       3 |  0.0789 |
| Glorious Hounds | Cecile       |   22 |   28 | 0.7857 |    0 | 0.0000 |          0 |   0.0000 |       6 |  0.2727 |
| Filthy Tide     | Geir         |   14 |   21 | 0.6667 |    1 |  0.0714 |          1 |   0.0476 |       9 |  0.6429 |
| Glorious Hounds | Branson      |    8 |   13 | 0.6154 |    4 | 0.5000 |          0 |   0.0000 |       0 |  0.0000 |
| Filthy Tide     | Milica       |    6 |   12 | 0.5000 |    2 |  0.3333 |          1 |   0.0833 |       3 |  0.5000 |

```
SELECT pl.f_tname AS Team, pl.name AS Player, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(md.td) AS TD, sum(md.td) / sum(md.cp) AS TD_Cp, sum(mx.interceptions_thrown) - sum(mx.safe_throws) AS Int_Thrown, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS Int_Rate, sum(mx.handoffs) AS Handoff, sum(mx.handoffs) / sum(md.cp) AS Hand_Cp FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id and mx.f_did = tours.f_did WHERE tours.name = 'Green Cup XI' AND pl.f_tname = 'Glorious Hounds' GROUP BY pl.name ORDER BY Cp DESC LIMIT 4;
```

The Hounds are great passers, even though [[Oxana]] and [[Cecile]] aren't quite the cannons that [[Yosif]] used to be.

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Filthy Tide       | Green Cup XI |     246 |    1390 |   79 | 17.5949 |       3.11 |
| Glorious Hounds   | Green Cup XI |     225 |    1221 |   79 | 15.4557 |       2.85 |

Numbers 1 and 3 in rushing on the season (and the Tide have the best rushing record across all Green cups)

| Team            | Player  | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-----------------|---------|---------|---------|------|---------|------------|
| Filthy Tide     | Veens   |      75 |     769 |   66 |  11.6515 |       1.14 |
| Glorious Hounds | Ziba    |      71 |     725 |   62 | 11.6935 |       1.15 |
| Glorious Hounds | Oxana   |      58 |     218 |    0 |    NULL |       NULL |
| Filthy Tide     | Aleksy  |      62 |     168 |    0 |     NULL |       NULL |
| Filthy Tide     | Milica  |      22 |     118 |    2 |  59.0000 |      11.00 |
| Filthy Tide     | Geir    |      34 |     117 |    1 | 117.0000 |      34.00 |
| Filthy Tide     | Othniel |      22 |      68 |    3 |  22.6667 |       7.33 |
| Glorious Hounds | Cecile  |      34 |      68 |    0 |    NULL |       NULL |
| Glorious Hounds | Ravil   |      16 |      63 |    6 | 10.5000 |       2.67 |
| Glorious Hounds | Branson |      17 |      61 |    4 | 15.2500 |       4.25 |

```
SELECT pl.f_tname AS Team, pl.name AS Player, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(mx.rushing_distance_leap) + sum(mx.rushing_distance_push) + sum(mx.rushing_distance_move) + sum(mx.rushing_distance_block) + sum(mx.rushing_distance_shadowing) AS Rushing, sum(md.td) AS TDs, (sum(mx.rushing_distance_leap) + sum(mx.rushing_distance_push) + sum(mx.rushing_distance_move) + sum(mx.rushing_distance_block) + sum(mx.rushing_distance_shadowing)) / sum(md.td) AS Rush_TD, round(((sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td)),2) AS Touches_TD FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id and mx.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = 'Glorious Hounds' GROUP BY pl.name ORDER BY Rushing DESC LIMIT 5;
```

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Glorious Hounds   | Green Cup XI |   17 |   11 |    6 |    0 |    488 |    28 |     0.0574 |    0.0348 |        248 |     0.5082 |
| Filthy Tide       | Green Cup XI |   11 |    7 |    4 |    0 |    437 |    19 |     0.0435 |    0.0252 |        183 |     0.4188 |


The Tide were the absolute worst at infliciting casualties this season, but the Hounds were only a couple of spots above them. 

| Team            | Player   | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-----------------|----------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Glorious Hounds | Florinda |    8 |    7 |    1 |    0 |    161 |     6 |     0.0373 |    0.0497 |         84 |     0.5217 |
| Filthy Tide     | Briseida |    3 |    2 |    1 |    0 |    106 |     3 |     0.0283 |    0.0283 |         42 |     0.3962 |
| Filthy Tide     | Slawomir |    1 |    0 |    1 |    0 |     62 |     2 |     0.0323 |    0.0161 |         30 |     0.4839 |
| Filthy Tide     | Drita    |    2 |    0 |    2 |    0 |     45 |     2 |     0.0444 |    0.0444 |         28 |     0.6222 |
| Glorious Hounds | Branson  |    4 |    3 |    1 |    0 |     39 |     4 |     0.1026 |    0.1026 |         23 |     0.5897 |
| Filthy Tide     | Tomer    |    2 |    2 |    0 |    0 |     39 |     4 |     0.1026 |    0.0513 |          7 |     0.1795 |
| Glorious Hounds | August   |    2 |    1 |    1 |    0 |     36 |     4 |     0.1111 |    0.0556 |         17 |     0.4722 |
| Glorious Hounds | Udo      |    1 |    0 |    1 |    0 |     35 |     3 |     0.0857 |    0.0286 |         12 |     0.3429 |


[[briseida]] is back in the lineup for the Tide to play can-opener, the way [[florinda]] does for the Hounds

The last time these teams met in Week 11 was a barn-burner of an offensive slugfest that ended in an 8-8 draw [[gcxi-11-ftgh]]

> Weather: Very Sunny
> Toss: FT-Receive
> Kickoffs: GH-PitchInvasion (FT 1), FT-PitchInvasion (GH 1), GH-PefectDefense (FT 2), FT-PitchInvasion (Half), FT-ChangingWeatherNice (GH 2), GH-CHeeringFansFT ()

Green Cup play began in the bright lights and the fans couldn't wait to celebrate till things were over. As a bunch of Hounds hit the deck Milica and Veens streaked up the sideline for their patented dumpoff play. Ziba was wise to the plan and got between them, making the pick as August went for the sack. Briseida and Milica got the ball back to Veens before it could get too far and the Tide took the lead. FT 1 - GH 0

The Tide's crowd handlers again couldn't keep the people back which opened up new holes in the lines for attack, which weren't strictly necessary as Oxana made a clean connection to Ziba who scored. FT 1 - GH 1

The Hounds adapted their defense on the next kick, but Veens leapt through. Udo did catch up and stripped the ball from her but when Oxana picked it up she couldn't make an accurate pass back up to Ziba. Aleksy zipped up the middle to pass to an open Othniel but he messed that up too. A bit more back and forth and the Tide managed to keep the ball in Aleksy's hands long enough for Veens to get in position for the TD. FT 2 - GH 1

If the Hounds could tie it up here, the game would still be under their control. They would still have the speed advantage in the second half. The fans invaded the pitch meaning Ziba would have a straight run for the endzone. And then Cecile botched the quick pass and the Tide entered the second with a lead instead of being poised to surrender one. FT 2 - GH 1

The second half kicked off with Oxana messing up another pass, giving the Tide a chance to expand their lead instead of let it all get tied up. They couldn't corral the ball and Irenaeus scored instead. FT 2 - GH 2

The Tide tried their Milica Veens dumpoff run and again, Ziba made the interception! The Hounds got the ball downfield but Tomer was playing safety and got the ball out to Aleksy who couldn't complete the pass to Veens. Oxana tried to get the ball out and make the pass to Udo, but couldn't handle it in all the traffic Drita was making. Geir got in and grabbed the ball and made the slightly shaky handoff to Veens, who scored the winning TD. The Tide are finally Green Cup Champions! FT 3 - GH 2


[[filthytide]][[glorioushounds]][[gcxi]]

#playoff 


| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1588" ORDER BY pl.f_tname, pl.nr;
```


Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

GH 5 Wins
FT 1 Win
4 Draws

* Green Cup IV - 3 - **Glorious Hounds** 4 Filthy Tide 2
* Green Cup IV - SF - **Glorious Hounds** 4 Filthy Tide 3
* Green Cup VI - 2 - Glorious Hounds 2 **Filthy Tide** 3
* Green Cup VI - 12 - Filthy Tide 3 Glorious Hounds 3
* Green Cup VII - 4 - Filthy Tide 4 Glorious Hounds 4
* Green Cup VIII - 10 - Filthy Tide 1 **Glorious Hounds** 3
* Green Cup IX - 8 - **Glorious Hounds** 5 Filthy Tide 3
* Green Cup V Memorial - 4 - Filthy Tide 3 Glorious Hounds 3
* Green Cup X - 12 - Filthy Tide 2 **Glorious Hounds** 4
* Green Cup XI - 11 - Filthy Tide 8 Glorious Hounds 8