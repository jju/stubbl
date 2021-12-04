# Cogs vs Eagles

Conference finals with the Cogs heavily favoured.

> Weather: Nice
> Toss: RE-Receive
> Kickoffs: IC-?? (RE 1), RE-?? (Half), RE-PerfectDefence (IC 1), IC-?? (RE 2), RE-PitchInvasion (Final)

The Eagles' [[Frediano]] received the kick and immediately moved into a cage while [[Sigfrido]] headed downfield. The Cogs withdrew from the cage, leaving Frediano to reform the cage to his left while Sigfrido headed further towards the endzone. The Cogs attempted to get in the faces of both ends of the potential scoring battery, which was neutralized, but then Frediano darted towards the sideline. [[venkata]] wrestled Sigfrido to the ground in the endzone, but he got up and out of the way for Frediano to be freed from a swarm to make the pass and catch. IC 0 - RE 1

The second quarter began with a short kick by Sigfrido. [[dragos]] got the ball to [[besz]] after Venkata opened up a hole on their right. After the Eagles swarmed back on the Cogs, Besz stumbled trying to get away from [[ekua]], and wound up knocked out. [[Birgitta]] recovered the fumbled ball, but was then sacked by [[Anant]], who stumbled and lost the ball trying to get clear (this whole time Saxa was waiting patiently downfield). Ekua cleared a path to the ball for Eliott, who picked it up but was immediately pushed into the crowd by Dragos. The ball ended up at midfield where Sigfrido grabbed it, tossed it to Birgitta who made a run for the endzone, but tripped as she pushed herself too fast! Dragos couldn't get the ball downfield far enough and the half ended. IC 0 - RE 1

The second half kicked off with a perfect defence by the Eagles. The Cogs headed to their left into the slightly less-threatening jaws of Ekua and Chikondi. Besz dumped off to Saxa, who darted through the center to make a just good enough pass to Dragos in the endzone. IC 1 - RE 1

On the kickoff, Frediano headed directly into a cage, knowing that drawing out a long scoring drive was the best way for the Eagles to win. Unlike the first half, the Cogs immediately began to pressure the cage while Dragos headed downfield. The cage ruptured and Frediano started running to his left with Ekua. Venkata came directly after him and got the sack, but Ekua remarkably didn't fumble the ball. The Cogs swarmed him, but he burst out of the cage and headed straight for the endzone for a TD. So much for the long scoring drive. IC 1 - RE 2

On the kickoff, there was a pitch invasion so with Besz down Karsten moved back to get the ball, but he mucked up the pass. Rather than trying to recover the dropped ball, the Eagles mobbed up on the Cogs who were still frozen at the line. Saxa headed downfield, followed by Besz and Karsten. Chikondi tried to sack Besz but she dumped the ball out to Dragos, who was then sacked by Lumusi. The ball went into the crowd, ending up at midfield where Eagles guarded it on the ground, not daring to try pick it up. The Cogs still had loads of time to score and force an overtime. Saxa moved downfield, but Dragos stumbled on his way to get the ball. The Eagles again protected the ball on the ground until the Cogs only had one last shot to grab and tie the match. Adalberto tried to grab it but was tackled going in and the ball made it out to Birgitta, who took a victorious trot downfield knowing the win was the Eagles'! IC 1 - RE 2





[[irregularcogs]][[ravenouseagles]][[gcvii]]

#playoff #close #upset 

| Player    | Team              | Touches | TDs  | Rush | Cp   | PassDist | Caught | Picks | Cas  | Blocks | Sacks | MVPs | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|-----------|-------------------|---------|------|------|------|----------|--------|-------|------|--------|-------|------|-------------|--------|------|------|---------|--------|------|


```
SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1571" ORDER BY pl.f_tname, pl.nr;
```


