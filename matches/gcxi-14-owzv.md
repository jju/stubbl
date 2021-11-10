# Wyrms vs Vagabonds

#t2786.2

Pick: Wyrms+

The Wyrms don't need a win, but the Vagabonds kind of do in order to escape an embarassing situation where they could be caught out by the Machine in week 15. Even a draw is good for the Vagabonds and these teams have gotten a lot of those in their time.

The Vagabonds' Zaira's botched handoff to Green stalled an amazing looking first half, but the Wyrms couldn't connect downfield and Betuel brought it back with Padma to take a 1-0 lead into halftime. They bashed their way through the Wyrms' line while regaining the lead and ended up clinching their playoff spot.

> Weather: Nice
> Toss: ZV-Receive
> Kickoffs: OW-RiotLong (ZV 1), ZV-BrilliantCoachingZV (Half), ZV-BrilliantCoachingZV (OW 1), OW-CheeringFansZV (ZV 2), ZV-QuickSnap (ZV 3), ZV-ThrowaRockOW (OW 2), OW-CheeringFansZV (Final)

[[oldwyrms]][[zensunvagabonds]][[gcxi]]



| Player    | Team            | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-----------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1493" ORDER BY pl.f_tname, pl.nr;
```

### playoff race



Are you writing anything about this match?

> A report of what happened on the field.
> A piece on the tragedy of injury in the service of sport.
> Just notes for now.

### previous matchups

ZV 2 Wins (1 OE playoff)
OW 4 Wins
7 Draws

* Green Cup I - 1 - Old Wyrms 2 **Zensun Vagabonds** 4
* Green Cup I - 8 - Old Wyrms 4 Zensun Vagabonds 4
* Green Cup II - 3 - **Old Wyrms** 6 Zensun Vagabonds 1
* Green Cup II - 7 - Zensun Vagabonds 2 Old Wyrms 2
* Green Cup II - SF - Old Wyrms 1 **Zensun Vagabonds** 3
* Green Cup III - 7 - Zensun Vagabonds 1 **Old Wyrms** 5
* Green Cup IV - 4 - Old Wyrms 3 Zensun Vagabonds 3
* Green Cup VI - 6 - Old Wyrms 3 Zensun Vagabonds 3
* Green Cup VI - 11 - Zensun Vagabonds 2 **Old Wyrms** 4
* Green Cup VII - 12 - Old Wyrms 3 Zensun Vagabonds 3
* Green Cup VIII - 1 - Zensun Vagabonds 3 Old Wyrms 3
* Green Cup IX - 8 - **Old Wyrms** 4 Zensun Vagabonds 0
* Green Cup X - 5 - Zensun Vagabonds 3 Old Wyrms 3