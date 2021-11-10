# Orbital Machine

A dominant bashing Modern-Era team, the Orbital Machine embodies a team-oriented approach. They inflict a lot of casualties and have the best winning streak in the UBBL (12 wins spanning two seasons).

## Playbook

The Orbital Machine uses the Chariot playbook. This involves four massive players on the line with everyone else more lightly armoured but able to blitz like no one's business. Passing and ball-handling tend to be a secondary consideration and get focused into whichever players show an aptitude while the rest of the team assembles the cage to roll down the field.

## Official Lineup 

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Ruslan   | Blitzer      |   Star |       3 |
| Jarm     | Blitzer      |    Rookie |       3 |
| Kendrick | Blitzer      |   Emerging Star |       3 |
| Stino    | Blitzer      |   Veteran |       6 |
| Spinal   | Blitzer      |   Seasoned Veteran |       5 |
| Odalric  | Blocker |   Star |       3 |
| Mate     | Blocker |   Star |       4 |
| Jothi    | Blocker |   Star |       2 |
| Bolt     | Blocker |   Seasoned Veteran |       5 |
| Corinne  | Blitzer      |    Experienced |       3 |
| Praveena | Blitzer      |    Bench |       3 |
| Uli      | Heavy      |   Star |       3 |

### Bench

| Player    | Position  | SPP | Seasons |
|-----------|-----------|-----|---------|
| Leppard  | Blitzer      |  Superstar |       6 |
| Collar   | Blocker |   Seasoned Veteran |       4 |
| Anvil    | Blocker |   Seasoned Veteran |       4 |

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, pl.value AS Value, pl.extra_val FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Orbital Machine" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Pro Level Record (W-D-L)

39-11-25

### UBBL Record (W-D-L)

40-11-29

### Prizes

* Green Cup Classic 06 - Iron Fist [[teamcasualties#gcc06]]
* Green Cup Classic 06 - Green Cup Champions [[team1stplace#gcc06]]
* Green Cup Classic 06 - Pits Champions [[teamdivision#gcc06]]
* Green Cup VII - Iron Fist [[teamcasualties#gcvii]]
* Green Cup VIII - Iron Fist  [[teamcasualties#gcviii]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Orbital Machine | Green Cup VII        |   11 |    3 |    3 |     17 | 73.53 |   29 |   17 |   42 |     33 |   -1 |
| Orbital Machine | **Green Cup Classic 06** |    6 |    1 |    3 |     10 |      65.00 |   18 |   15 |   16 |      8 |    5 |
| Orbital Machine | Green Cup VIII       |    9 |    0 |    7 |     16 |   56.25 |   27 |   27 |   49 |     27 |    1 |
| Orbital Machine | Green Cup X          |    7 |    4 |    5 |     16 |   56.25 |   27 |   27 |   40 |     26 |   -1 |
| Orbital Machine | Green Cup IX         |    6 |    3 |    7 |     16 |  46.88 |   21 |   26 |   31 |     20 |   -1 |
| Orbital Machine | UBBL Challenge       |    1 |    0 |    2 |      3 | 33.33 |    5 |    6 |    4 |     -1 |   -1 |
| Orbital Machine | UBBL Challenge IV    |    0 |    0 |    2 |      2 |    0.00 |    1 |    3 |    6 |      1 |   -2 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "TEAM" ORDER BY mr.win_pct DESC limit 16;
```

## History

The Machine are entirely a Modern era institution.

### Seasons

With a timely 6-win streak the Pits champions hoisted the sixth (disputed) Green Cup. The Machine were sneaky in their physical dominance but inflicted 16 Casualties (10-3-3) in their 10-match championship run.

They continued to win throughout GCVII but lost in the Division Finals to the [Eldritch Fatality](eldritchfatality).

The GCIX season was their first in which they did not lead the league in Casualties inflicted.

In GCXI the Machine did not make the playoffs (but as former Green Cup winners they did not face relegation).

#### Projection GCXI

W-D-L 8-1-6

The Machine is due for another deep playoff run and this season could be the one where they take advantage of a tough-to-call division. The more interesting race might be to see if they can wrestle the [Iron Fist](../prizes/teamcasualties) from the [Ravenous Eagles](ravenouseagles).

#### GCXI Recap




### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Heep   | Orbital Machine | Blitzer      |   26 |    4 |   12 |   42 |   28 |    5 |    4 |    6 |    1 |    0 |    2 |  121 |
| **Leppard** | Orbital Machine | Blitzer      |   38 |   11 |   25 |   74 |   14 |   26 |    2 |    3 |    4 |    2 |    6 |  120 |
| Lars   | Orbital Machine | Heavy      |   18 |    4 |    7 |   29 |    1 |    0 |    2 |   11 |    6 |    1 |    6 |   73 |
| **Uli**     | Orbital Machine | Heavy      |   13 |    6 |   11 |   30 |    0 |    0 |    0 |   17 |    5 |    1 |    4 |   66 |
| **Ruslan**  | Orbital Machine | Blitzer      |   13 |    6 |   12 |   31 |    9 |    5 |    1 |    6 |    1 |    0 |    3 |   63 |
| Ioana  | Orbital Machine | Heavy      |    9 |    1 |    9 |   19 |    2 |    0 |    2 |    8 |    2 |    2 |    5 |   59 |
| **Odalric** | Orbital Machine | Blocker |   14 |    7 |   14 |   35 |    3 |    0 |    0 |    8 |    1 |    1 |    6 |   59 |
| **Jothi**   | Orbital Machine | Blocker |   13 |    6 |   12 |   31 |    3 |    2 |    2 |    7 |    1 |    0 |    5 |   56 |
| Priest | Orbital Machine | Blitzer      |   25 |    4 |   10 |   39 |    8 |   24 |    1 |    0 |    0 |    0 |    1 |   55 |
| Ozzy   | Orbital Machine | Blitzer      |   20 |    4 |    9 |   33 |   11 |   11 |    1 |    3 |    1 |    0 |    0 |   54 |
| Def    | Orbital Machine | Blitzer      |   28 |    5 |   13 |   46 |    3 |    2 |    2 |    5 |    3 |    1 |    4 |   53 |

### roster by season

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Orbital Machine" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

#### Cup Winners

| #    | Player   | GP | Touches | TD   | Rsh  | Cp   | CpDst | Ctch | Int  | Cas  | Blk  | Sck  | MVP  | Intercepted | Sacked | KOed | Hurt | Injured | Killed | SPP  |
|------|----------|----|---------|------|------|------|-------|------|------|------|------|------|------|-------------|--------|------|------|---------|--------|------|
|    5 | [[Stino]]    |  2 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    0 |
|    6 | [[Spinal]]   | 10 |       4 |    0 |    2 |    1 |     1 |    0 |    0 |    1 |   22 |    2 |    0 |           0 |      1 |    1 |    1 |       0 |      0 |    3 |
|    8 | [[Bolt]]     | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   61 |    0 |    1 |           0 |      0 |    1 |    1 |       0 |      0 |    7 |
|    9 | [[Collar]] | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   58 |    0 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   10 | [[Anvil]]    | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    1 |   52 |    1 |    0 |           0 |      0 |    0 |    0 |       0 |      0 |    2 |
|   17 | [[Rivet]]   | 10 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    3 |   67 |    1 |    0 |           0 |      1 |    0 |    0 |       0 |      0 |    6 |
|   25 | [[Def]]     | 10 |       1 |    0 |    0 |    1 |     4 |    0 |    0 |    2 |   40 |    2 |    2 |           0 |      0 |    0 |    1 |       0 |      0 |   15 |
|   26 | [[Lucio]]   |  2 |       2 |    0 |   17 |    0 |     0 |    0 |    0 |    0 |    1 |    0 |    1 |           0 |      1 |    0 |    0 |       0 |      0 |    5 |
|   81 | [[Priest]]  | 10 |      32 |    2 |  114 |    1 |     5 |    0 |    0 |    0 |    8 |    0 |    0 |           0 |      2 |    1 |    0 |       0 |      0 |    7 |
|   82 | [[Ozzy]]    | 10 |      14 |    5 |   75 |    1 |     4 |    0 |    1 |    2 |   28 |    1 |    0 |           0 |      5 |    0 |    0 |       0 |      0 |   22 |
|   82 | [[Leppard]] | 10 |       8 |    4 |   47 |    1 |     1 |    3 |    0 |    1 |   39 |    1 |    2 |           0 |      1 |    1 |    0 |       0 |      0 |   25 |
|   83 | [[Heep]]    | 10 |      16 |    7 |  100 |    2 |     5 |    4 |    0 |    1 |   21 |    0 |    2 |           0 |      6 |    0 |    1 |       0 |      0 |   35 |
|   84 | Crue.    |  8 |       3 |    0 |   10 |    0 |     0 |    0 |    0 |    0 |   18 |    0 |    0 |           0 |      2 |    0 |    0 |       0 |      1 |    0 |
|   86 | [[Judas]]   |  9 |       0 |    0 |    0 |    0 |     0 |    0 |    0 |    0 |   12 |    2 |    1 |           0 |      0 |    0 |    0 |       1 |      0 |    5 |
|   96 | [[Lars]]    | 10 |       2 |    0 |    0 |    0 |     0 |    0 |    2 |    3 |   97 |    1 |    1 |           0 |      0 |    0 |    2 |       0 |      0 |   15 |


##### No Ring

* Crue - dead

### Management

The Orbital Machine is owned by an industrial concern with long local ties to Stacksburg and especially the mass elevator.

### Fans

Fans of the Machine don't get on especially well with the other main bashing teams in the Pros (the [Carcosan Tatters](carcosantatters) and [Gore Farmers](gorefarmers)). Adding to the frisson with the Farmers is the disputed nature of the "true winner" of the sixth Green Cup.

### Famous Games

The betrayal at Dungardin vs the [Cogs](irregularcogs) in GCVII Week 8 was notable for historical reasons (also, it was a 2 interception match for the Machine).

