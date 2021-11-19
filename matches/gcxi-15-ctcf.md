# Tatters vs Furies

#t2787.7

Pick: Furies

The Furies needed this win to make the playoffs, but they couldn't make anything stick against a determined Tatters squad. Now they face relegation (or not as we may be entering an expansion season).

> Weather: Nice
> Toss: CT-Receive
> Kickoffs: CF-BrilliantCoachingCT (CT 1), CT-HighKick (CT 2), CT-ChangingWeatherNice (Half), CT-HighKick (CT 3Final)

[[carcosantatters]][[cacklingfuries]][[gcxi]]



| Player    | Team            | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-----------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1500" ORDER BY pl.f_tname, pl.nr;
```

### playoff race



Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

CT 5 Wins
CF 2 Wins
1 Draw

* Green Cup II - 10 - Cackling Furies 0 **Carcosan Tatters** 1
* Green Cup III - 6 - Carcosan Tatters 1 **Cackling Furies** 3
* Green Cup IV - 2 - **Carcosan Tatters** 2 Cackling Furies 0
* Green Cup VII - 12 - **Carcosan Tatters** 1 Cackling Furies 0
* Green Cup VIII - 4 - Cackling Furies 0 **Carcosan Tatters** 1
* Green Cup IX - 11 - Carcosan Tatters 1 Cackling Furies 1
* Green Cup V Memorial - 11 - Cackling Furies 0 **Carcosan Tatters** 2
* Green Cup X - 5 - Carcosan Tatters 0 **Cackling Furies** 2