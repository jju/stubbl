# Geometers



## Playbook



## Records

### Open Level Record (W-D-L)

15-5-18

### UBBL Record (W-D-L)

15-5-18

### Prizes

* [[noprize]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Geometers | UBBL Challenge III |    3 |    0 |    2 |      5 |      60 |    9 |   10 |    7 |      4 |    1 |
| Geometers | Orange Goblet II   |    4 |    3 |    4 |     11 |      50 |   15 |   19 |   25 |     23 |    1 |
| Geometers | UBBL Challenge     |    2 |    0 |    2 |      4 |      50 |    5 |    3 |    9 |      6 |    2 |
| Geometers | UBBL Challenge IV  |    2 |    0 |    2 |      4 |      50 |    5 |    8 |    6 |      3 |    0 |
| Geometers | UBBL Challenge II  |    1 |    1 |    2 |      4 |    37.5 |    4 |    8 |    8 |      4 |   -1 |
| Geometers | Orange Goblet      |    3 |    1 |    6 |     10 |      35 |   12 |   17 |   13 |      4 |    0 |


`
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Geometers" ORDER BY mr.win_pct DESC limit 15;
`

## History


### Seasons


#### Projection OGIII

W-D-L ?


### Stars

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Mathghamhain** | Geometers | Thrower       |   13 |    3 |   17 |   33 |    8 |   27 |    1 |    2 |    0 |    0 |    1 |   62 |
| **Anda**         | Geometers | Blocker |   13 |    4 |   16 |   33 |    0 |    0 |    1 |    7 |    5 |    0 |    6 |   56 |
| Scot        | Geometers | Thrower       |    6 |    2 |   11 |   19 |   10 |    1 |    0 |    2 |    0 |    0 |    3 |   50 |
| **Nor**          | Geometers | Thrower       |    3 |    2 |    4 |    9 |   10 |    0 |    0 |    0 |    0 |    1 |    1 |   37 |
| **Siva**         | Geometers | Blocker |   13 |    4 |   15 |   32 |    0 |    0 |    0 |    6 |    1 |    2 |    3 |   33 |
| **Danut**        | Geometers | Blocker |   13 |    4 |   17 |   34 |    0 |    0 |    0 |    7 |    3 |    1 |    2 |   32 |
| **Dario**        | Geometers | Blocker |   14 |    4 |   17 |   35 |    0 |    0 |    1 |    2 |    1 |    0 |    4 |   28 |
| **Ciela**        | Geometers | Blitzer      |    8 |    4 |    8 |   20 |    4 |    0 |    0 |    2 |    0 |    0 |    2 |   26 |
| **Herman**       | Geometers | Line      |   15 |    4 |   18 |   37 |    0 |    1 |    0 |    2 |    0 |    0 |    4 |   25 |
| **Samuhel**      | Geometers | Blitzer      |    9 |    4 |    8 |   21 |    3 |    2 |    0 |    3 |    0 |    2 |    0 |   21 |
| **Karin**        | Geometers | Line      |   15 |    5 |   18 |   38 |    0 |    0 |    0 |    1 |    2 |    0 |    3 |   21 |

`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 2 AND pl.f_tname = "Geometers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC 
limit 11;
`

#unfinished 

### Management

### Fans


### Famous Games


