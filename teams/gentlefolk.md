# Gentlefolk

The Gentlefolk have folded as they could not maintain an overall 33% winning percentage in the UBBL.

## Playbook



## Records

### Open Level Record (W-D-L)

8-4-21

### UBBL Record (W-D-L)

9-4-21

### Prizes

* [[noprize]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Gentlefolk | StUBBL Scramble    |    1 |    0 |    0 |      1 |     100 |    1 |    0 |    1 |      0 |    0 |
| Gentlefolk | UBBL Challenge IV  |    1 |    0 |    1 |      2 |      50 |    3 |    9 |    7 |      5 |    1 |
| Gentlefolk | Orange Goblet      |    3 |    3 |    5 |     11 | 40.91 |   11 |   16 |   19 |     -1 |    0 |
| Gentlefolk | UBBL Challenge II  |    1 |    1 |    2 |      4 |    37.5 |    3 |    5 |   14 |      3 |    0 |
| Gentlefolk | UBBL Challenge     |    1 |    0 |    2 |      3 | 33.33 |    4 |    8 |    8 |      2 |    1 |
| Gentlefolk | Orange Goblet II   |    2 |    0 |    8 |     10 |      20 |   10 |   29 |   13 |     -9 |   -2 |
| Gentlefolk | UBBL Challenge III |    0 |    0 |    3 |      3 |       0 |    4 |    7 |    9 |      4 |    0 |

`
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Gentlefolk" ORDER BY mr.win_pct DESC limit 15;
`

## History


### Seasons


#### Projection OGII

W-D-L ?


### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Kibwe     | Gentlefolk | Heavy     |    8 |    4 |   21 |   33 |    3 |    0 |    0 |    8 |    5 |    4 |    2 |   53 |
| Aelfsige | Gentlefolk | Heavy     |    6 |    4 |   16 |   26 |    7 |   10 |    0 |    4 |    1 |    1 |    2 |   53 |
| Deepti   | Gentlefolk | Runner |    8 |    4 |   21 |   33 |    7 |    1 |    2 |    0 |    0 |    0 |    3 |   41 |
| Aslan     | Gentlefolk | Heavy     |    8 |    4 |   21 |   33 |    1 |    0 |    2 |    4 |    2 |    0 |    4 |   39 |
| Tom       | Gentlefolk | Heavy     |    7 |    4 |   14 |   25 |    0 |    0 |    2 |    5 |    3 |    0 |    3 |   35 |
| Barbel    | Gentlefolk | Heavy     |    6 |    3 |   14 |   23 |    0 |    0 |    1 |    7 |    4 |    0 |    2 |   34 |
| Shona     | Gentlefolk | Runner |    8 |    4 |   20 |   32 |    3 |    1 |    0 |    0 |    0 |    0 |    4 |   30 |
| Doroteja | Gentlefolk | Runner |    7 |    3 |   19 |   29 |    5 |    2 |    0 |    0 |    0 |    0 |    2 |   27 |
| Nevan    | Gentlefolk | Runner |    5 |    4 |   13 |   22 |    2 |    2 |    0 |    1 |    0 |    0 |    3 |   25 |
| Nina      | Gentlefolk | Heavy     |    6 |    4 |   12 |   22 |    1 |    0 |    0 |    6 |    3 |    2 |    0 |   25 |
| Bjorn     | Gentlefolk | Heavy     |    5 |    2 |   10 |   17 |    0 |    0 |    0 |    3 |    1 |    0 |    3 |   23 |


`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Gentlefolk" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
`

#unfinished 

### Management

### Fans


### Famous Games


