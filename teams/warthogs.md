# Warthogs



## Playbook

The Orville-Crush approach to BludBol is traditional, simple, but also somewhat arcane. A team can use 4 strong slow and unskilled linemen, 4 faster attacking blitzers, 2 dedicated ball-handlers, 4 weak slow receivers and a nigh-unlimited supply of tough fodder. The basic idea is to get a ball handler into a cage and grind out a 2-1 win, but there are more options for the team that wishes to develop them.

## Records

### Open Level Record (W-D-L)

15-2-16

### UBBL Record (W-D-L)

15-2-17

### Prizes

*  UBBL Challenge IV - Alsoran Honour [[team3rdplace]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Warthogs | UBBL Challenge IV  |    3 |    0 |    2 |      5 |      60 |   11 |    6 |   12 |      8 |    3 |
| Warthogs | Orange Goblet II   |    6 |    1 |    4 |     11 | 59.0909 |   22 |   16 |   18 |      8 |   -2 |
| Warthogs | Orange Goblet      |    5 |    1 |    5 |     11 |      50 |   14 |   17 |   13 |      6 |    3 |
| Warthogs | UBBL Challenge     |    1 |    0 |    2 |      3 | 33.3333 |    3 |    7 |    2 |      3 |    0 |
| Warthogs | UBBL Challenge III |    0 |    0 |    3 |      3 |       0 |    1 |   10 |    4 |      2 |   -1 |
| Warthogs | StUBBL Scramble    |    0 |    0 |    1 |      1 |       0 |    0 |    1 |    1 |      0 |    0 |

`
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Warthogs" ORDER BY mr.win_pct DESC limit 15;
`

## History


### Seasons


#### Projection OGIII

W-D-L ?


### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Omiros**    | Warthogs | Blitzer           |   13 |    2 |   15 |   30 |   16 |    0 |    0 |    0 |    2 |    0 |    2 |   62 |
| **Ragu**      | Warthogs | Catcher            |   15 |    2 |   16 |   33 |   18 |    1 |    0 |    0 |    0 |    0 |    1 |   60 |
| **Hursit**    | Warthogs | Thrower           |   15 |    2 |   16 |   33 |    0 |   34 |    0 |    1 |    0 |    1 |    4 |   58 |
| Jimena   | Warthogs | Thrower           |   10 |    2 |   15 |   27 |    2 |   25 |    2 |    0 |    1 |    0 |    2 |   47 |
| **Borislav**  | Warthogs | Blitzer           |   10 |    1 |   13 |   24 |    3 |    0 |    2 |    6 |    3 |    0 |    2 |   41 |
| **Sita**      | Warthogs | Blocker |   15 |    2 |   15 |   32 |    0 |    0 |    1 |    1 |    1 |    0 |    6 |   36 |
| **Emmet**     | Warthogs | Blocker |   15 |    2 |   16 |   33 |    0 |    0 |    0 |    4 |    0 |    0 |    5 |   33 |
| **Devereux**  | Warthogs | Blocker |    9 |    1 |   13 |   23 |    0 |    0 |    0 |    3 |    1 |    0 |    5 |   33 |
| **Bethari**   | Warthogs | Blitzer           |   11 |    2 |   16 |   29 |    4 |    2 |    1 |    1 |    1 |    1 |    0 |   22 |
| **Svjetlana** | Warthogs | Blitzer           |    6 |    1 |    4 |   11 |    2 |    1 |    1 |    2 |    2 |    2 |    0 |   21 |
| **Heinrich**  | Warthogs | Blocker |   12 |    1 |    9 |   22 |    0 |    0 |    0 |    6 |    2 |    0 |    1 |   21 |

`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Warthogs" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC 
limit 11;
`

#unfinished 

### Management

### Fans


### Famous Games


