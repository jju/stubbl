# Badger Claws

The Badger Claws fought their way into Green Cup play from the Open Division through the UBBL Challenge and have never had a season below .500. They also have the greatest scorer in UBBL history -- [[Aeson]] -- playing for them.

## Playbook

The Badger Claws use the Scrying Avian playbook which emphasizes speed above all else, especially the health of your own players. The position slots only include 2 blitzers, but have 2 throwers, 4 catchers (sometimes more accurately labelled runners), and a heavy available. With proper training it's possible to have a super-fast scorer onside, which makes the lack of defensive ability easier to overcome.

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Consolo    | Thrower       |   86 |       4 |   34 |         2 | 200000 |     0 |
|    2 | Gianna     | Thrower       |   18 |       1 |    6 |         0 | 120000 |     0 |
|    3 | Klim       | Runner |   92 |       3 |   21 |         1 | 210000 |     0 |
|    4 | Ophelia    | Runner |   36 |       1 |    8 |         1 | 150000 |     0 |
|    6 | Rong       | Runner |   21 |       1 |   14 |         1 | 120000 |     0 |
|    7 | Anselmo    | Line       |    9 |       5 |   45 |         3 |  70000 |     0 |
|    8 | Felicienne | Line       |   11 |       4 |   36 |         2 |  90000 | 20000 |
|    9 | Marge      | Line       |   21 |       4 |   31 |         2 | 110000 | 20000 |
|   10 | Gerty      | Line       |   19 |       3 |   16 |         1 |  90000 |     0 |
|   11 | Simas      | Line       |    7 |       5 |   31 |         2 |  90000 | 20000 |
|   14 | Chroma     | Blitzer       |    0 |       1 |    4 |         0 |  90000 |     0 |
|   15 | Iris       | Blitzer       |   55 |       4 |   48 |         3 | 190000 |     0 |
|   16 | Pippin     | Heavy      |   61 |       3 |   36 |         2 | 260000 | 20000 |

### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|   25 | Comgan     | Blitzer       |   23 |       3 |   17 |         1 | 150000 |  10000 |
|   36 | Friese     | Heavy      |    4 |       2 |    3 |         0 | 150000 |      0 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Badger Claws" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records
```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, avg(mr.win_pct) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Badger Claws" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```
### Pro Level Record (W-D-L)

29-6-20

### UBBL Record (W-D-L)
```
SELECT teams.name, sum(mr.won), sum(mr.draw), sum(mr.lost), sum(mr.played), avg(mr.win_pct), sum(mr.gf), sum(mr.ga), sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Badger Claws" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```
34-8-21

### Prizes

* Green Cup VIII - Pits Division Champions [[teamdivision#gcviii]]
* Green Cup VIII - Classic Conference Champions [[team2ndplace#gcviii]] & [[teamconference#gcviii]]
* Green Cup IX - Outlands Division Champions [[teamdivision#gcix]]
* Green Cup IX - Tough Brake of Alsoran [[team3rdplace#gcix]]
* Green Cup X - Outlands Division Champions [[teamdivision#gcx]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Badger Claws | UBBL Challenge  |    4 |    1 |    1 |      6 |      75.00 |   25 |   19 |    5 |      2 |    1 |
| Badger Claws | StUBBL Scramble |    1 |    1 |    0 |      2 |      75.00 |    5 |    2 |    0 |     -4 |    0 |
| Badger Claws | Green Cup IX    |   11 |    3 |    4 |     18 | 69.44 |   75 |   56 |   20 |    -20 |    0 |
| Badger Claws | Green Cup X     |    9 |    1 |    8 |     18 | 52.78 |   64 |   58 |   21 |     -8 |    1 |
| Badger Claws | Green Cup VIII  |    9 |    2 |    8 |     19 | 52.63 |   61 |   57 |   15 |    -32 |    4 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Badger Claws" ORDER BY mr.win_pct DESC limit 16;
```

## History

While the Claws have never not had a winning season, they've also never won a championship.

### Seasons

The Badger Claws did not win the first UBBL Challenge (which was a bigger affair and much tougher for challenger teams who had to face two established Green Cup teams in Pool Play). But as the top-finishing challenger they won the right to play the last-place [Brutes](gargantuanbrutes) for their spot in the Green Cup.

After defeating the [Brutes](gargantuanbrutes) 5-2, the Badger Claws went off on a tear in the Green Cup VIII tournament. They slowed down around the midpoint but made it through the playoffs with upset after stunning upset until facing down the [Gore Farmers](gorefarmers) in the final. And losing, but still. What a run.

Green Cup IX went even better for the Claws as far as wins go, but they were knocked out of the Conference Finals by the [Old Wyrms](oldwyrms), so they had to be satisfied with third place.

The projections for GCX had the Claws as 10-game winners and at least conference champions. They didn't manage that because of the incredibly competitive Outlands division, but did squeak through to the conference finals where they lost to the [Old Wyrms](oldwyrms) again.

#### Projection GCXI

W-D-L 9-1-5

There is no doubt that the Badger Claws can score. The question is if their defense can manage to hold off enough key plays to make them Green Cup Champions. Anything less is going to feel like a failure in [[Aeson]]'s probable final season.

#### roster by season

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Badger Claws" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```


### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Aeson**      | Badger Claws | Catcher |   34 |    7 |   20 |   61 |  157 |    3 |    0 |    0 |    0 |    0 |   10 |  524 |
| **Cleve**      | Badger Claws | Thrower       |   30 |    6 |   15 |   51 |    0 |  121 |    1 |    0 |    0 |    0 |    3 |  138 |
| Donat     | Badger Claws | Catcher |   19 |    5 |   12 |   36 |   35 |    2 |    0 |    1 |    0 |    0 |    0 |  109 |
| **Consolo**    | Badger Claws | Thrower       |   10 |    1 |    8 |   19 |    0 |   33 |    1 |    0 |    0 |    0 |    4 |   55 |
| Avani     | Badger Claws | Catcher |   23 |    5 |   13 |   41 |    5 |    4 |    1 |    3 |    0 |    0 |    5 |   52 |
| **Pippin**     | Badger Claws | Heavy      |   18 |    4 |    9 |   31 |    0 |    0 |    0 |    9 |    4 |    3 |    3 |   47 |
| Barukh    | Badger Claws | Catcher |   14 |    5 |   12 |   31 |    5 |   12 |    1 |    0 |    0 |    0 |    3 |   44 |
| Haman     | Badger Claws | Thrower       |   15 |    3 |   11 |   29 |    1 |   20 |    1 |    2 |    0 |    1 |    2 |   41 |
| **Iris**       | Badger Claws | Blitzer       |   20 |    4 |   11 |   35 |    0 |    1 |    0 |    6 |    1 |    0 |    5 |   40 |
| **Olanrewaju** | Badger Claws | Catcher |   14 |    2 |    6 |   22 |    6 |    7 |    3 |    0 |    0 |    0 |    1 |   36 |
| **Sunny**      | Badger Claws | Catcher |   12 |    1 |    9 |   22 |    8 |    2 |    1 |    0 |    0 |    0 |    1 |   33 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Badger Claws" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

Obviously when we talk about the Badger Claws we have to talk about the best player the UBBL has ever seen, [Aeson](../players/aeson). Aeson's SPP total in GCIX alone eclipse hundreds of players.

Aeson and [[donat]] started out similarly but Donat got a serious concussion and development slowed. In the off-season after GCX, Donat was the first player in the UBBL to be sold under the new free agency rules. He ended up with the Open Division [Vanadium Hunters](vanadiumhunters) for Orange Goblet II, where he was crippled in his first match and withdrew from BludBol entirely.

[[cleve]] is one of the biggest stars in the UBBL who has never scored a touchdown (3rd in the all-UBBL list and 3rd in the Pro Division). What makes it even more remarkable is how many times he touches the ball without going for the endzone himself.

It will eventually be a problem that all their good players have peaked and are getting more expensive by the season and there's not a lot of skill waiting in the wings. 

#### Award Winners
| #    | Player | Position      | Seasons | Prizes | Value  | Bonus  |
|------|--------|---------------|---------|--------|--------|--------|
|    5 | Aeson  | Runner |       6 |      9 | 320000 | 110000 |
|   98 | Donat. | Runner |       4 |      1 | 240000 |  30000 |


```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val As Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Badger Claws" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

### Fans

The Badger Claws had a major fan surge (FF +4 over the 9-2-8 season) in their first Green Cup tournament. The team has a few rivalries going to sustain it. The [Arboreal Menace](arborealmenace) are a natural rival as the new upstart little sibling in the Green Cup world, while their use of the same playbook as the [Filthy Tide](filthytide) make for some natural "Who did it better?" kinds of comparisons. Then there's the [Old Wyrms](oldwyrms), the team that's stopped the Claws in the conference finals every time they've shared the Burger Conference.

### Famous Games

The Green Cup VIII Conference Final against the [Kaiju Dynamo](kaijudynamo) was an insanely intense score-fest right to the end, when an ill-timed stumble for the Dynamo cost them the match 8-7. That was the highest scoring match seen to that time.

The Badger Claws did break that high scoring record, albeit in a 10-8 loss to the underdog Filthy Tide in [Week 9](../seasons/gcx/week09) of the GCX season.

