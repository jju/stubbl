# Carrion Pickers



## Playbook

The Carrion Pickers use the Wary Eagle playbook, which is very similar to the Scrying Avian technique, but with slightly higher skilled (and more expensive to replace) players. The lineup includes four catchers, two blitzers and throwers that have more of an option of holding back and letting fly once the catchers are in position.

## Records

### Open Level Record (W-D-L)

5-1-7

### UBBL Record (W-D-L)

9-1-8

### Prizes

* [[noprize]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Carrion Pickers | Rookie Rumble     |    4 |    0 |    1 |      5 |      80 |   11 |    6 |    1 |     -9 |    3 |
| Carrion Pickers | UBBL Challenge IV |    2 |    0 |    1 |      3 | 66.6667 |    6 |    5 |    3 |     -1 |    0 |
| Carrion Pickers | Orange Goblet II  |    3 |    1 |    6 |     10 |      35 |   21 |   29 |    6 |     -9 |    0 |

`
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Carrion Pickers" ORDER BY mr.win_pct DESC limit 15;
`

## History


### Seasons


#### Projection OGII

W-D-L ?


### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Leopoldo**  | Carrion Pickers | Catcher   |    4 |    1 |    5 |   10 |    7 |    7 |    0 |    0 |    0 |    1 |    0 |   30 |
| **Tlalli**    | Carrion Pickers | Wardancer |    5 |    1 |    7 |   13 |    4 |    1 |    0 |    2 |    0 |    0 |    1 |   22 |
| **Jet**       | Carrion Pickers | Lineman   |    5 |    1 |    7 |   13 |    1 |   19 |    0 |    0 |    0 |    0 |    0 |   22 |
| **Dinah**     | Carrion Pickers | Catcher   |    3 |    1 |    5 |    9 |    4 |    2 |    1 |    0 |    0 |    0 |    1 |   21 |
| **Atli**      | Carrion Pickers | Catcher   |    3 |    1 |    6 |   10 |    5 |    0 |    0 |    0 |    0 |    0 |    1 |   20 |
| Deborah  | Carrion Pickers | Lineman   |    5 |    1 |    7 |   13 |    0 |    1 |    0 |    2 |    0 |    0 |    2 |   15 |
| **Dietlinde** | Carrion Pickers | Lineman   |    4 |    1 |    5 |   10 |    0 |    0 |    0 |    0 |    0 |    0 |    3 |   15 |
| **Nace**      | Carrion Pickers | Wardancer |    4 |    1 |    6 |   11 |    1 |    0 |    0 |    0 |    0 |    0 |    2 |   13 |
| **Ermet**     | Carrion Pickers | Thrower   |    5 |    1 |    7 |   13 |    0 |   12 |    0 |    0 |    0 |    0 |    0 |   12 |
| **Paula**     | Carrion Pickers | Catcher   |    3 |    0 |    2 |    5 |    2 |    0 |    0 |    0 |    0 |    0 |    1 |   11 |
| **Inge**      | Carrion Pickers | Lineman   |    3 |    0 |    4 |    7 |    2 |    0 |    0 |    0 |    0 |    0 |    1 |   11 |


`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Carrion Pickers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
`

#unfinished 

### Management

### Fans


### Famous Games


