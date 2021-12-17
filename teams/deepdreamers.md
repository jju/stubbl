# Deep Dreamers

The Deep Dreamers have been


## Playbook



## Records

### Open Level Record (W-D-L)

17-1-19

### UBBL Record (W-D-L)

17-1-20

### Prizes



### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Deep Dreamers | UBBL Challenge III |    3 |    0 |    2 |      5 |      60 |   14 |   13 |    4 |      3 |    1 |
| Deep Dreamers | Orange Goblet II   |    6 |    1 |    5 |     12 | 54.1667 |   26 |   27 |    6 |    -11 |    1 |
| Deep Dreamers | Orange Goblet      |    5 |    0 |    6 |     11 | 45.4545 |   20 |   21 |    6 |      1 |    2 |
| Deep Dreamers | UBBL Challenge IV  |    1 |    0 |    2 |      3 | 33.3333 |    7 |   11 |    4 |      1 |   -1 |
| Deep Dreamers | UBBL Challenge     |    1 |    0 |    2 |      3 | 33.3333 |    5 |    6 |    1 |     -4 |    1 |
| Deep Dreamers | UBBL Challenge II  |    1 |    0 |    2 |      3 | 33.3333 |    4 |    6 |    0 |     -6 |    0 |
| Deep Dreamers | StUBBL Scramble    |    0 |    0 |    1 |      1 |       0 |    0 |    3 |    0 |     -3 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Deep Dreamers" ORDER BY mr.win_pct DESC limit 15;
```

## History


### Seasons


#### Projection OGII

W-D-L ?


### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Medb**        | Deep Dreamers | Thrower  |   17 |    1 |   18 |   36 |    0 |   37 |    1 |    1 |    1 |    0 |    5 |   68 |
| Giovanna        | Deep Dreamers | Catcher  |   16 |    1 |   16 |   33 |   14 |    9 |    3 |    1 |    0 |    0 |    0 |   59 |
| **Mihael**      | Deep Dreamers | Catcher  |    6 |    1 |    6 |   13 |   10 |    5 |    5 |    1 |    0 |    0 |    1 |   52 |
| **Brynja**      | Deep Dreamers | Blitzer  |   11 |    0 |   15 |   26 |    8 |    2 |    1 |    2 |    0 |    0 |    4 |   52 |
| **Maja**        | Deep Dreamers | Blitzer  |   12 |    0 |   15 |   27 |    8 |    0 |    2 |    3 |    1 |    0 |    3 |   51 |
| **Tenskwatawa** | Deep Dreamers | Blitzer  |   10 |    0 |   13 |   23 |   11 |    2 |    3 |    1 |    0 |    0 |    1 |   48 |
| **Arthmael**    | Deep Dreamers | Blitzer  |    6 |    0 |    7 |   13 |    6 |    0 |    0 |    1 |    1 |    0 |    3 |   37 |
| **Marita**      | Deep Dreamers | Catcher  |    6 |    1 |    6 |   13 |    4 |    1 |    2 |    0 |    0 |    0 |    3 |   32 |
| **Noirin**      | Deep Dreamers | Line  |   17 |    1 |   19 |   37 |    2 |    1 |    2 |    1 |    0 |    0 |    3 |   28 |
| **Clement**     | Deep Dreamers | Line  |   16 |    1 |   18 |   35 |    0 |    0 |    1 |    0 |    0 |    0 |    4 |   22 |
| **Krister**     | Deep Dreamers | Catcher  |    6 |    1 |    6 |   13 |    2 |   10 |    0 |    0 |    0 |    0 |    1 |   21 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Deep Dreamers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

#unfinished 

### Management

### Fans


### Famous Games


