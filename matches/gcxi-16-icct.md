# Cogs vs Tatters

#t2788.9

Pick: Cogs

These two teams had a heck of a battle through their division over the season. SpreadZone is picking the Cogs (2330TV) over the Tatters (2630TV).

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Irregular Cogs    | Green Cup XI |    8 |    2 |    5 |     15 |      60 |   42 |   34 |   2.8000 |   2.2667 |   18 |    1.2000 |      2 |   -1 |
| Carcosan Tatters  | Green Cup XI |    7 |    2 |    6 |     15 | 53.3333 |   26 | **22** | 1.7333 |   1.4667 |   36 |    2.4000 |     22 |    0 |

The Tatters had a league-leading defence while the Cogs were top-5 in every offensive category.

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Irregular Cogs    | Green Cup XI |   63 |      102 | 0.6176 |   42 | 0.6667 |          8 |   0.0784 |      11 |  0.1746 |
| Carcosan Tatters  | Green Cup XI |   32 |       52 | 0.6154 |   26 | 0.8125 |          4 |   0.0769 |       9 |  0.2813 |

It's interesting how both of these teams have such a similar completions percentage, but the Tatters just pass less and more of their passes lead to TDs.

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Irregular Cogs    | Green Cup XI |     167 |     829 |   42 | 19.7381 |       3.98 |
| Carcosan Tatters  | Green Cup XI |     125 |     551 |   26 | 21.1923 |       4.81 |

More Tatters have to touch the ball to get a TD than Cogs do. How much does this change with the loss of the Cogs' dedicated ballhandlers for the playoff?

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Carcosan Tatters  | Green Cup XI |   35 |   22 |    7 |    6 |    761 |    14 |     0.0184 |    0.0460 |        396 |     0.5204 |
| Irregular Cogs    | Green Cup XI |   18 |   11 |    5 |    2 |    600 |    24 |     0.0400 |    0.0300 |        275 |     0.4583 |

Casualty-wise, it's no surprise the Tatters dominate. If they can get pounding on the Cogs early, they have a real chance at the win.

In their last match (a couple of weeks ago [[gcxi-14-icct]]) the Tatters got a win. Unlike the Vagabonds and Dynamo who played each other late in the regular season, these two teams are going to be running out practically the same lineups, apart from [[merlyn]] who the Tatters removed from the season.

The Cogs are going to need to play a bit differently, and it's going to be interesting to see how well they adapt.

> Weather: Very Sunny
> Toss: CT-Kick
> Kickoffs: CT-BrilliantCoachingBoth (IC 1), IC-QuickSnap (IC 2), IC-Blitz (IC 3), IC-QuickSnap (Half), IC-ChangingWeatherNice (CT 1), CT-QuickSnap (IC 4), IC-QuickSnap (Final)

The Tatters elected to kick, trusting their defence to hold things together and see what the Cogs' runner-free offense was going to try. The Cogs went with a left flank load, relying on a couple of strong blitzes to get a quickish score. [[Erazem]] failed to make that happen. The line couldn't open up anything either and when [[Mackenzie]] tried to make a leap [[FlamingLion]]'s tentacles pulled her down into the maw. [[Frans]] did get through but [[Hrolfr]] made his way to a cage instead of immediately putting the pressure downfield. After a bit of pounding it almost looked clear for Hrolfr to pass to Frans, but [[Uzmal]] made the interception. The COgs swarmed and swarmed and forced Uzmal off the pitch. The ball was thrown in to Mackenzie who couldn't make the grab with FlamingLion in her face. Frans got over to shovelpass to Mackenzie who managed to get away and take the lead. IC 1 - CT 0

The Tatters set up nicely to cage up for the remainder of the first half, but Frans managed to get in the way and snag Liubo's errant pass into the cage. He then made it down for another quick TD and the Tatters' gameplan was officially fallen apart. IC 2 - CT 0

On the ensuing kick, Frans was keyed up and led the Cogs in a Blitz, that took Arya out of the drive. Liubo fucked up another pass, and the ball was in the middle of the pitch for a perfectly positioned Mackenzie to snatch and grab. IC 3 - CT 0

The Tatters killed off Tel in the last drive before the half, but otherwise nothing happened. Liubo continued missing all his passes. IC 3 - CT 0

Down two lines, Mateo the kicker was pressed into blocking duty for the Cogs who now just needed to make it through the half without any more injuries. The Tatters weren't going to let that happen. In the scrumming [[Erazem]] got viciously trampled while [[Arya]] scampered in for a TD. IC 3 - CT 1

The Tatters went for a short kick despite their lack of skills. The touchback went to Hrolfr who ran up the left side with protection, knowing the best defense is a good offense. Hrolfr got the TD without difficulty and the clock was reset. IC 4 - CT 1

Arya got a TD but the crowd was restless and just wanting to cheer on their Cogs. IC 4 - CT 2

There was some more play, including another completed pass by Liubo now that it was meaningless.

[[irregularcogs]][[carcosantatters]][[gcxi]]

#playoff #phyrric 

| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1571" ORDER BY pl.f_tname, pl.nr;
```


Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

CT 6 Wins (1 GC Playoff)
IC 7 Wins (1 GC Playoff)
2 Draws

* Green Cup II - 1 - Irregular Cogs 2 Carcosan Tatters 2
* Green Cup II - 7 - **Carcosan Tatters** 2 Irregular Cogs 0
* Green Cup II - SF - **Carcosan Tatters** 3 Irregular Cogs 2
* Green Cup III - 7 - **Carcosan Tatters** 2 Irregular Cogs 1
* Green Cup III - QF - Carcosan Tatters 0 **Irregular Cogs** 5
* Green Cup IV - 8 - Irregular Cogs 1 **Carcosan Tatters** 2
* Green Cup VI - 5 - **Carcosan Tatters** 2 Irregular Cogs 1
* Green Cup VI - 8 - **Irregular Cogs** 3 Carcosan Tatters 0
* Green Cup VII - 1 - **Irregular Cogs** 4 Carcosan Tatters 1
* Green Cup VIII - 6 - **Irregular Cogs** 3 Carcosan Tatters 1
* Green Cup IX - 14 - Carcosan Tatters 1 **Irregular Cogs** 2
* Green Cup V Memorial - 7 - Carcosan Tatters 0 **Irregular Cogs** 2
* Green Cup V Memorial - QF - **Irregular Cogs** 2 Carcosan Tatters 0
* Green Cup X - 14 - Irregular Cogs 1 Carcosan Tatters 1
* Green Cup XI - 14 - Irregular Cogs 1 **Carcosan Tatters** 2