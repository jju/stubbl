# Tide vs Claws

#t2784.5

Pick: Claws

Klim stumbled on his way in for the 3-2 TD. The 6-4 TD was a back and forth drive after Aleksy botched the pass to Venus. Eventually things settled down into trading TDs but the Tide had gotten their advantage in the first half and held it even as their defenders got injured.

> Weather: Nice
> Toss: BC-Receive
> Kickoffs: FT-BrilliantCoachingFT (BC 1), BC-ChangingWeatherNice (FT 1), FT-ChangingWeatherNice (BC 2), BC-BrilliantCoachingFT (FT 2), FT-BrilliantCoachingFT (FT 3), FT-PerfectDefense (FT 4), FT-QuickSnap (Half), BC-CheeringFansFT (BC 3), BC-Blitz (FT 5), FT-QuickSnap (BC 4), BC-RiotBack (FT 6), FT-CheeringFansFT (BC 5), BC-PitchInvasion (FT 7), FT-CheeringFansFT (BC 6), BC-CHangingWeatherNice (FT 8), FT-HighKick (BC 7), BC-RiotBack (FT 9), FT-QuickSnap (Final)

[[badgerclaws]][[filthytide]][[gcxi]]

[[aficionado]] offense offense offense do these games get a little unpredictable?

| Player    | Team            | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-----------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|

```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1480" ORDER BY pl.f_tname, pl.nr;
```

### playoff race



Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

IC 4 Wins
DS 1 Win
2 Draws

* UBBL Challenge - SF - Badger Claws 6 **Filthy Tide** 7
* Green Cup VIII - 11 - Filthy Tide 5 **Badger Claws** 6
* Green Cup IX - 15 - Filthy Tide 1 **Badger Claws** 6
* Green Cup X - 9 - **Filthy Tide** 10 Badger Claws 8