# Hounds vs Vagabonds

#t2789.3

Pick: Hounds

SpreadZone has the Hounds as the favourites against the Vagabonds (2410TV), and they've won 8/10 of their previous matchups (4/6 in the modern era). Let's check their actual GCXI records.

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Glorious Hounds   | Green Cup XI |   10 |    4 | **2** |    16 |      75 | **73** | 44 |   4.5625 |   2.7500 |   13 |    0.8125 |    -13 |   -1 |
| Zensun Vagabonds  | Green Cup XI |    5 |    2 |    9 |     16 |    37.5 |   32 |   45 |   2.0000 |   2.8125 |   22 |    1.3750 |     -4 |   -3 |

Victories go to the Hounds, who had the fewest losses on the season. They scored the most in the season and had a better defense than the Vagbonds. It's hard to see how the Zensunners can respond.

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Glorious Hounds   | Green Cup XI |   82 |      109 | 0.7523 |   72 | 0.8780 |          1 |   0.0092 |      16 |  0.1951 |
| Zensun Vagabonds  | Green Cup XI |   60 |       77 | 0.7792 |   32 | 0.5333 |          4 |   0.0519 |      10 |  0.1667 |

Unlike in their first round matchup the Vagabonds are a much worse passing team (though not by percentage).

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Glorious Hounds   | Green Cup XI |     207 |    1123 |   72 | 15.5972 |       2.88 |
| Zensun Vagabonds  | Green Cup XI |     180 |     736 |   32 | 23.0000 |       5.63 |

More Vagabonds touch the ball, which makes sense as they have less of a one and done philosophy than the direct touch of the Hounds. More touches mean more chances for things to go wrong, so minimizing mistakes will again be key.

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Zensun Vagabonds  | Green Cup XI |   22 |   15 |    5 |    2 |    499 |    17 |     0.0341 |    0.0441 |        248 |     0.4970 |
| Glorious Hounds   | Green Cup XI |   13 |    7 |    6 |    0 |    414 |    23 |     0.0556 |    0.0314 |        204 |     0.4928 |

The Vagabonds inflict more casualties than the Hounds, but the Hounds are pretty elite when it comes to sacks.

In their last match in week 8 [[gcxi-08-ghzv]] the Hounds absolutely destroyed the Vagabonds. Will they take that lesson to heart and fuel some revenge?

> Weather: Pouring Rain
> Toss: GH-Receive
> Kickoffs: ZV-QuickSnap (GH 1), GH-CheeringFansBoth (GH 2), GH-CheeringFansZV (Half), GH-QuickSnap (GH 3), GH-QuickSnap (ZV 1), ZV-ThrowaRockGH (ZV 2), ZV-HighKick (Final)

The Vagabonds were overjoyed to see a torrential mess as they took to the field. Anything that could slow down [[Ziba]]. The Hounds elected to receive, trusting their gameplan even in the face of this. It was a well-founded trust as [[Cecile]] did exactly what was needed after [[Florinda]] opened the hole, getting the ball to Ziba who streaked for the opening TD. GH 1 - ZV 0

The Hounds kickoff had them looking for a sack and turnover to start opening up the seams. After aquick attack and scrum, the Hounds did heap on the humiliation and from their fans' perspective the trouncing could really begin. GH 2 - ZV 0

The Vagabonds withstood a barrage of sack attempts (well, [[Padma]] did) but they were unable to score before halftime was called. GH 2 - ZV 0

And the rout began in earnest when Betuel couldn't pick up the ball, leaving a scrum in the middle to spit out [[Ziba]] for a rare catch in the endzone TD. GH 3 - ZV 0

The Vagabonds succeeded in their flank assault with Padma and Mia to finally get on the board, but with only a quarter of the match left, there just wasn't time for this to become a real comeback. GH 3 - ZV 1

The Hounds didn't need Branson to sacrifice himself to stop Clydon from getting out of his scrum, but he tried it anyway and got his collarbone smashed for the trouble, so he'll be missing out on the Conference Championship next week. Oh, the Vagabonds did score too. GH 3 - ZV 2



[[zensunvagabonds]][[glorioushounds]][[gcxi]]

#playoff


| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1573" ORDER BY pl.f_tname, pl.nr;
```


Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

GH 4 Wins
ZV 3 Wins +1 BYE
1 Draw

* Green Cup IV - 10 - **Glorious Hounds** 3 Zensun Vagabonds 2
* Green Cup VI - 1 - Zensun Vagabonds 0 **Glorious Hounds** 1
* Green Cup VI - 10 - Glorious Hounds 4 Zensun Vagabonds 4
* Green Cup VII - 9 - **Zensun Vagabonds** 3 Glorious Hounds 2
* Green Cup VIII - 14 - Zensun Vagabonds 1 **Glorious Hounds** 5
* Green Cup IX - 13 - **Zensun Vagabonds** 3 Glorious Hounds 1
* Green Cup IX - R16 - Zensun Vagabonds 2 **Glorious Hounds** 4
* Green Cup X - 15 - **Zensun Vagabonds** 4 Glorious Hounds 0
* Green Cup X - R16 - Zensun Vagabonds 1 Glorious Hounds 0 (BYE)
* Green Cup XI - 8 - **Glorious Hounds** 6 Zensun Vagabonds 1