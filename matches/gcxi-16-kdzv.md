# Dynamo vs Vagabonds

#t2788.3

Pick: Dynamo

SpreadZone has the Dynamo (2920TV) favoured in this match against the Vagabonds (2410TV), and they've won 8/10 of their previous matchups (4/6 in the modern era). Let's check their actual GCXI records.

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Kaiju Dynamo      | Green Cup XI |   10 |    1 |    4 |     15 |      70 |   32 |   24 |   2.1333 |   1.6000 |   26 |    1.7333 |      9 |    2 |
| Zensun Vagabonds  | Green Cup XI |    4 |    2 |    9 |     15 | 33.3333 |   28 |   42 |   1.8667 |   2.8000 |   21 |    1.4000 |     -4 |   -3 |

The edge here is definitely for the Dynamo. They scored more, allowed fewer TDs, and inflicted more casualties. The question is what is the path the Vagabonds could take to get the win?

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Kaiju Dynamo      | Green Cup XI |   13 |       38 | 0.3421 |   32 | 2.4615 |          1 |   0.0263 |      27 |  2.0769 |
| Zensun Vagabonds  | Green Cup XI |   54 |       70 | 0.7714 |   28 | 0.5185 |          4 |   0.0571 |      10 |  0.1852 |

The Vagabonds are a much better passing team than the Dynamo, so this is how they're going to have a better chance to attack.

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Kaiju Dynamo      | Green Cup XI |     124 |     751 |   32 | 23.4688 |       3.88 |
| Zensun Vagabonds  | Green Cup XI |     167 |     677 |   28 | 24.1786 |       5.96 |

More Vagabonds touch the ball, which makes sense as they are a more passing-heavy team. More touches mean more chances for things to go wrong, so minimizing mistakes will be key.

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Kaiju Dynamo      | Green Cup XI |   26 |   23 |    2 |    1 |    702 |    17 |     0.0242 |    0.0370 |        391 |     0.5570 |
| Zensun Vagabonds  | Green Cup XI |   21 |   14 |    5 |    2 |    472 |    16 |     0.0339 |    0.0445 |        235 |     0.4979 |

The Dynamo inflict more casualties than the Vagabonds, but a lot of that is due to throwing a lot more blocks out there. If the Vagabonds can convert their sacks into possessions they've got a chance at the upset.

In their last match (last week) both teams didn't really have their hearts in it. [[Ion]] was the Dynamo's leading rusher and she did not make the playoff roster. In that match the Vagabonds completed only one pass, which is not how they want this one to go.

> Weather: Nice
> Toss: ??-Receive
> Kickoffs: 

[[zensunvagabonds]][[kaijudynamo]][[gcxi]]



| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1503" ORDER BY pl.f_tname, pl.nr;
```


Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

KD 8 Wins
ZV 1 Win (GC QF)
1 Draw

* Green Cup I - 6 - Zensun Vagabonds 1 **Kaiju Dynamo** 2
* Green Cup II - 6 - Zensun Vagabonds 3 **Kaiju Dynamo** 4
* Green Cup III - 1 - Zensun Vagabonds 2 **Kaiju Dynamo** 4
* Green Cup IV - 7 - Zensun Vagabonds 1 **Kaiju Dynamo** 3
* Green Cup VII - 15 - **Kaiju Dynamo** 2 Zensun Vagabonds 1
* Green Cup VIII - 11 - **Kaiju Dynamo** 4 Zensun Vagabonds 3
* Green Cup IX - 12 - Kaiju Dynamo 2 Zensun Vagabonds 2
* Green Cup X - 12 - Zensun Vagabonds 1 **Kaiju Dynamo** 2
* Green Cup X - QF - **Zensun Vagabonds** 5 Kaiju Dynamo 1
* Green Cup XI - 15 - Zensun Vagabonds 1 **Kaiju Dynamo** 2