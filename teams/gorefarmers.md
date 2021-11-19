# Gore Farmers

When the Gore Farmers are good they can be very good, as evidenced by their two Green Cup wins in the modern era. But they can also be really bad, which has led to relegation and terrible seasons and an overall record below .500.

## Playbook

The Orville-Crush approach to BludBol is traditional, simple, but also somewhat arcane. A team can use 4 strong slow and unskilled linemen, 4 faster attacking blitzers, 2 dedicated ball-handlers, 4 weak slow receivers and a nigh-unlimited supply of tough fodder. The basic idea is to get a ball handler into a cage and grind out a 2-1 win, but there are more options for the team that wishes to develop them. The Gore Farmers, for instance, *mostly* eschew the Big Guy approach.

## Active Roster GCXI Playoffs

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Ros        | Thrower |   66 |       3 |   29 |         2 | 160000 | 10000 |
|    2 | SkyTripper | Thrower |   97 |       5 |   60 |         4 | 170000 |     0 |
|    3 | Aemulus    | Blitzer |  104 |       3 |   35 |         2 | 230000 | 20000 |
|    4 | Nuru       | Catcher |   80 |       5 |   38 |         3 | 170000 | 20000 |
|    5 | Elric      | Blitzer |   52 |       3 |   31 |         2 | 170000 |     0 |
|    6 | Beitris    | Blitzer |   52 |       4 |   38 |         3 | 160000 |     0 |
|    7 | Eloi       | Blocker |   52 |       3 |   40 |         3 | 170000 |     0 |
|    8 | Pasquale   | Blocker |   31 |       3 |   38 |         3 | 140000 |     0 |
|    9 | RockLobber | Blocker |   69 |       6 |   64 |         4 | 200000 | 40000 |
|   10 | Emil       | Blocker |   51 |       5 |   40 |         3 | 170000 |     0 |
|   11 | Helmuth    | Line    |   27 |       6 |   62 |         4 | 120000 | 30000 |
|   12 | Johann     | Line    |   31 |       2 |    9 |         1 | 140000 |     0 |
|   13 | Mashee     | Catcher |   85 |       7 |   61 |         4 | 170000 |     0 |
|   15 | Sylvester  | Blitzer |   33 |       4 |   34 |         2 | 140000 |     0 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   16 | Aethelraed | Blitzer |   32 |       4 |   38 |         3 | 140000 |     0 |
|   17 | Sanel      | Blocker |   14 |       3 |   11 |         1 | 100000 |     0 |


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Gore Farmers" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division (W-D-L)

```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, avg(mr.win_pct) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gore Farmers" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

47-17-53

### UBBL Record (W-D-L)
```
SELECT teams.name, sum(mr.won), sum(mr.draw), sum(mr.lost), sum(mr.played), avg(mr.win_pct), sum(mr.gf), sum(mr.ga), sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gore Farmers" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```
52-22-60

### Prizes

* Green Cup VI - Green Cup Champions [[team1stplace#gcvi]]
* Green Cup VI - Stacks Champions [[teamdivision#gcvi]]
* Green Cup VIII - Green Cup Champions [[team1stplace#gcviii]]
* Green Cup VIII - Burger Conference Champions [[teamconference#gcviii]]
* Green Cup VIII - Stacks Division Champions [[teamdivision#gcviii]]
* Green Cup IV - Tough Brake of Alsoran [[team3rdplace#gciv]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Gore Farmers | Green Cup IV         |    7 |    2 |    2 |     11 | 72.7273 |   22 |   13 |   28 |     21 |    3 |
| Gore Farmers | **Green Cup VI**         |   10 |    3 |    4 |     17 | 67.6471 |   27 |   25 |   25 |     14 |    3 |
| Gore Farmers | **Green Cup VIII**       |   11 |    3 |    5 |     19 | 65.7895 |   36 |   23 |   42 |     24 |    1 |
| Gore Farmers | UBBL Challenge       |    2 |    0 |    2 |      4 |      50 |    7 |    8 |    7 |     -2 |    2 |
| Gore Farmers | Green Cup III        |    5 |    1 |    5 |     11 |      50 |   16 |   17 |   32 |     20 |   -1 |
| Gore Farmers | Green Cup V Memorial |    3 |    5 |    3 |     11 |      50 |   11 |   14 |   15 |      5 |    1 |
| Gore Farmers | Green Cup X          |    6 |    2 |    9 |     17 | 41.1765 |   30 |   35 |   32 |     15 |    2 |
| Gore Farmers | Green Cup VII        |    5 |    0 |   11 |     16 |   31.25 |   22 |   40 |   24 |     -9 |   -2 |
| Gore Farmers | Green Cup I          |    2 |    2 |    6 |     10 |      30 |   12 |   22 |   18 |     10 |   -1 |
| Gore Farmers | Green Cup IX         |    1 |    4 |   11 |     16 |   18.75 |   17 |   34 |   28 |     14 |   -6 |
| Gore Farmers | UBBL Challenge IV    |    0 |    0 |    2 |      2 |       0 |    2 |    6 |    3 |      0 |   -1 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gore Farmers" ORDER BY mr.win_pct DESC limit 16;
```

## History

### Seasons

The Gore Farmers were the first team to be relegated in the old-era UBBL after a terrible inaugural season. When they came back they were better, and in GCIV they only had 2 losses. It was a shame the second came in the quarterfinals. [[Spleen Hucker]] was a thrower in that Old-Era incarnation and was the person tagged to lead the team's name to glory, which only came in the new era, winning the first modern (somewhat disputed) Green Cup in GCVI.

They followed up their first championship with a lousy GCVII, but then in GCVIII the Gore Farmers played solid defensive caging BludBol to win: the Stacks Division facing [a mad-scoring threat](filthytide) in the first round, the Burger Conference against [a defensive powerhouse](carcosantatters) and the Green Cup itself against [a very young and healthy mad-scoring threat](badgerclaws). They're the first renaissance era multiple champions and did it by playing their game.

Sadly for lovers of pure competition, Spleen Hucker was also one of the first to really jump on the "tanking in a lost season" strategy, making their bad seasons (like GCIX) really bad and leaving them as a .500 team overall despite being multiple champions.

In GCX they played for the Stacks championship but lost to the [Old Wyrms](oldwyrms). They did avoid the charge of tanking and played competitive BludBol throughout the season.

#### GCXI Projection

W-D-L 7-0-8 

The Gore Farmers have a decent payroll going into the GCXI season, bringing back as many veterans as they had relatively healthy. Their fortunes are a crapshoot but they don't have any obvious deficiencies that need plugging. The biggest problem may be in finding the funds to develop rookies, but so far they don't seem too worried.

#### roster by season

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| KneeMasher   | Gore Farmers | Blitzer           |   26 |    7 |   19 |   52 |   31 |   10 |    8 |    5 |    0 |    0 |    2 |  139 |
| *AxeEater* | Gore Farmers | Blitzer | ?? | ?? | ?? | 50 | 24 | 2 | 0 | 12 | 3 | 0 | 2 | 114 |
| **SkyTripper**    | Gore Farmers | Thrower           |   23 |    5 |   26 |   54 |    4 |   56 |    1 |    0 |    0 |    0 |    4 |   90 |
| *GutTwister* | Gore Farmers | Thrower | ?? | ?? | ?? | 53 | 13 | 18 | 0 | 4 | 0 | 0 | 4 | 85 |
| **Mashee**        | Gore Farmers | Catcher            |   27 |    5 |   28 |   60 |   20 |    1 |    3 |    0 |    0 |    0 |    3 |   82 |
| *SpleenHucker* | Gore Farmers | Thrower | ?? | ?? | ?? | 45 | 11 | 23 | 0 | 1 | 1 | 0 | 4 | 80 |
| **Aemulus**       | Gore Farmers | Blitzer           |    7 |    6 |   13 |   26 |   16 |    6 |    2 |    2 |    0 |    0 |    3 |   77 |
| KnuckleBiter | Gore Farmers | Thrower           |   15 |    5 |   15 |   35 |    5 |   45 |    1 |    1 |    0 |    0 |    1 |   69 |
| **Nuru**          | Gore Farmers | Catcher            |   13 |    4 |   16 |   33 |   15 |    1 |    0 |    0 |    0 |    0 |    4 |   66 |
| **RockLobber**    | Gore Farmers | Blocker |   23 |    5 |   30 |   58 |    0 |    0 |    1 |   12 |    5 |    1 |    5 |   63 |
| GrimThrasher | Gore Farmers | Blocker |   28 |    6 |   25 |   59 |    0 |    0 |    0 |    5 |    9 |    3 |    5 |   59 |
| **Ros**           | Gore Farmers | Thrower           |    7 |    3 |   11 |   21 |    2 |   33 |    0 |    1 |    0 |    1 |    2 |   53 |
| TallHexer    | Gore Farmers | Blocker |   27 |    6 |   22 |   55 |    1 |    0 |    0 |    5 |    0 |    0 |    8 |   53 |
| StoneLicker  | Gore Farmers | Blitzer           |   17 |    4 |   16 |   37 |    6 |    0 |    0 |   12 |    5 |    0 |    0 |   52 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

That the Gore Farmers have won two modern-era Green Cups with only one legitimate superstar (who is now retired - [[kneemasher]]) is an impressive testament to the power of a solid line and the traditional caging methods of play. [[guttwister]] retired after GCVI as a veteran of the old-era UBBL. He says he was glad to get a ring, but felt sidelined despite his abilities.

The current star is [[aemulus]] who provides a fine alternative to [[Mashee]] as a scoring threat from outside the cage.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Gore Farmers" GROUP BY pl.name ORDER BY pl.nr ASC;
```

#### Cup Winners

* [[kneemasher]] VI, VIII
* [[beardpuller]] VI, VIII
* [[GrimThrasher]] VI, VIII
* [[ToothGrinder]] VI, VIII
* [[TallHexer]] VI, VIII
* [[SpaceFiller]] VI, VIII
* [[guttwister]] VI
* [[KnuckleBiter]] VI
* [[mashee]] VI
* [[stonelicker]] VI
* [[RibCracker]] VI
* [[TuskOfGruumsh]] VI
* [[CakeStomper]] VI
* [[HobNailer]] VI
* [[JunkKicker]] VI
* [[skytripper]] VIII
* [[RockLobber]] VIII
* [[Elric]] VIII
* [[Fang]] VIII
* [[belenus]] VIII
* [[Nuru]] VIII
* [[TinyDancer]] VIII
* [[Eulaylia]] VIII
* [[Helmuth]] VIII

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup VI" AND pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup VIII" AND pl.f_tname = "Gore Farmers" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Tactics

As noted above, the Gore Farmers play a traditional bashing, caging style of BludBol. What has made them a good team has been having options to deviate from that plan. When [[kneemasher]] was still active he was a terror to passing teams and had the raw abilities to power the ball to TD himself on the other side of the field from the cage. [[mashee]] has not been as prolific and usually only takes the field when her role is crystal clear, but that has included some of the Farmers' biggest games.

### Management

Spleen Hucker has proved to be a savvy leader of the team, but at the expense of entertaining BludBol. When things weren't going well for the Farmers in GCVII he dropped all the starters from the active roster, replacing them with journeymen anxious for a taste of Pro level BludBol. They proceeded to lose lots of matches, but the players gained skills. Then in GCVIII those skills meant he didn't need to overpay for past performance and they won another championship. GCIX meant a time to tear everything down again to prep for some even-year magic.

### Fans

The current fanbase hates the tanking that went on in GCIX and the Farmers were going to be under the microscope for violations of the spirit of the new rules in GCX. They got through the season having regained some trust.

The Gore Farmers and the [Orbital Machine](orbitalmachine) both won the sixth Green Cup (one Classic and one not) and that dispute over which one should really count fuelled their rivalry. The [Darkling Spectres](darklingspectres) at this point are the team the Farmers try their best to fend off, as successfully as they have thus far.

### Famous Games

The GCVI Final is a match to watch. It wasn't the most pretty, but it's a pretty excellent example of how good BludBol can be even without constant arcing passes.