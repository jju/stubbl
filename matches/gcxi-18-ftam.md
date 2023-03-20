# Tide vs Menace

#t2790.7

Pick: Menace

In a battle between an original 8 team and the newest Green Cup challenger, SpreadZone is picking the Arboreal Menace (2590TV) over the Filthy Tide (2100TV). With the injury to [[Veens]] in Week 15, we'd have to agree.

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Filthy Tide       | Green Cup XI |   12 |    2 |    3 |     17 | 76.4706 |   75 |   55 |   4.4118 |   3.2353 |   11 |    0.6471 |    -23 |    1 |
| Arboreal Menace   | Green Cup XI |   11 |    2 |    4 |     17 | 70.5882 |   63 |   49 |   3.7059 |   2.8824 |   15 |    0.8824 |     -6 |    2 |

These teams are very evenly matched, with the Tide having a slightly better offense and the Menace a slightly better defense. A lot hinges on how well the [[Veens]] [[Milica]] teamup continues to work.

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Arboreal Menace   | Green Cup XI |   70 |       89 | 0.7865 |   62 | 0.8857 |          2 |   0.0225 |      10 |  0.1429 |
| Filthy Tide       | Green Cup XI |   62 |       90 | 0.6889 |   74 | 1.1935 |          3 |   0.0333 |      30 |  0.4839 |

The Tide use the handoff more than the Menace, probably due to their lower completion percentage (which is still higher than a lot of teams who pass more).

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Filthy Tide       | Green Cup XI |     234 |    1312 |   74 | 17.7297 |       3.16 |
| Arboreal Menace   | Green Cup XI |     200 |    1145 |   62 | 18.4677 |       3.23 |

Numbers 1 and 3 in rushing (and the Tide are number 2 across all Green cups)

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Arboreal Menace   | Green Cup XI |   15 |   15 |    0 |    0 |    421 |    20 |     0.0475 |    0.0356 |        213 |     0.5059 |
| Filthy Tide       | Green Cup XI |   11 |    7 |    4 |    0 |    402 |    18 |     0.0448 |    0.0274 |        163 |     0.4055 |

The Tide were the absolute worst at infliciting casualties this season, but the Menace were only a couple of spots above them.

The last time these teams met was in the opening week of the season. [[gcxi-01-ftam]] The Tide won that one 6-5

> Weather: Nice
> Toss: AM-Receive
> Kickoffs: FT-CheeringFansAM (AM 1), AM-QuickSnap (FT 1), FT-HighKick (FT 2Half), AM-Blitz (FT 3), FT-Blitz (FT 4), FT-CheeringFansFT (AM 2), AM-CheeringFansBoth (FT 5), FT-HighKick (AM 3Final)

The opening kick went smoothly for the Menace, who did a two-step to get the ball to Laurel who scored. No drama. FT 0 - AM 1

The quick snap on the Tide's first kick reception made some question lining Milica up on the line. ThenMilica botched the dump-off to Veens and things looked even worse. Georgina got the ball on the Menace's left flank and went for it down the sideline despite being mobbed by the Tide. She was clear until tripping over the endzone line. The ball went into the stands but the Tide couldn't get it to a competent ball-handler. Enrique was killed by Borarinn and Ingeborg threw the ball into the stands. Aleksy recovered it and got it out to Tomer. Tomer kept his cool and scored. They'd eaten up a lot of time, but should have the chance to even things out again by halftime if the defense failed. FT 1 - AM 1

On the ensuing kick Ingeborg and Laurel didn't connect with their pass. Milica and Veens pounced and timed their dash for the endzone for halftime, and went into the second with a lead. FT 2 - AM 1

The Menace blitzed off the kick and things looked dire for the Tide, but the ball managed to hit the ground and after a bunch of scrambling Geir got it out to Veens who took her time to draw down the clock a bit more. Now they just needed to hold on. FT 3 - AM 1

Lining up to hold on and play defensively seemed to be the order of the day, but instead the Tide blitzed. Veens caught the kick and even though she had the ball stripped by Sanja, Slawomir backed her up and she recovered for the TD. FT 4 - AM 1

The stadium was rocking for the Tide. Ingeborg passed to Laurel who scored and nobody cared at all. FT 4 - AM 2

The Tide scored again and so did the Menace but the game was over and the Filthy Tide were heading to their first ever Green Cup. FT 5 - AM 3

[[filthytide]][[arborealmenace]][[gcxi]]

#playoff #upset 


| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1585" ORDER BY pl.f_tname, pl.nr;
```


Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

FT 2 Wins

* Green Cup X - 10 - **Filthy Tide** 6 Arboreal Menace 1
* Green Cup XI - 1 - **Filthy Tide** 6 Arboreal Menace 5