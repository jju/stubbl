# Raptors



## Playbook

The Raptors use the Elizabeth Aardman playbook, with strong linemen and a big guy anchoring the centre, while the ball handling runners are chosen for speed (rather than skill, strength or durability). The basic idea of the playbook is to cage the fragile runner to a place where they can bolt for the endzone.

## Records

### Open Level Record (W-D-L)

10-2-6

### UBBL Record (W-D-L)

13-3-7

### Prizes

* Orange Goblet II Champions - [[team1stplace]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Raptors | Rookie Rumble     |    3 |    1 |    1 |      5 |      70 |   13 |    9 |    9 |     -1 |    2 |
| Raptors | Orange Goblet II  |    7 |    2 |    4 |     13 | 61.5385 |   26 |   25 |   21 |      1 |    4 |
| Raptors | UBBL Challenge IV |    3 |    0 |    2 |      5 |      60 |    9 |   10 |    5 |     -1 |    1 |


`
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Raptors" ORDER BY mr.win_pct DESC limit 15;
`

## History


### Seasons


#### Projection OGIII

W-D-L ?


### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Ella**      | Raptors | Runner    |    8 |    1 |    5 |   14 |   12 |    3 |    0 |    0 |    0 |    0 |    2 |   49 |
| Francine | Raptors | Runner    |    6 |    2 |    4 |   12 |    8 |    8 |    0 |    0 |    0 |    0 |    2 |   42 |
| **Tatiana**   | Raptors | Heavy |    8 |    1 |    4 |   13 |    0 |    0 |    0 |    4 |    0 |    0 |    3 |   23 |
| **Youko**     | Raptors | Blocker   |    8 |    2 |    4 |   14 |    0 |    0 |    0 |    3 |    1 |    1 |    2 |   20 |
| **Hiro**      | Raptors | Runner    |    8 |    0 |    3 |   11 |    2 |   13 |    0 |    0 |    0 |    0 |    0 |   19 |
| **Edme**      | Raptors | Runner    |    8 |    2 |    5 |   15 |    2 |    0 |    0 |    0 |    0 |    0 |    2 |   16 |
| **Thanatos**  | Raptors | Runner    |    9 |    2 |    6 |   17 |    3 |    2 |    0 |    0 |    0 |    0 |    1 |   16 |
| **Hercules**  | Raptors | Blocker   |   10 |    2 |    5 |   17 |    1 |    0 |    0 |    1 |    0 |    0 |    2 |   15 |
| **Conor**     | Raptors | Blocker   |   10 |    1 |    6 |   17 |    0 |    0 |    0 |    2 |    1 |    1 |    1 |   13 |
| **Greaves**   | Raptors | Runner    |    4 |    0 |    1 |    5 |    1 |    0 |    2 |    0 |    0 |    0 |    1 |   12 |
| **Viyan**     | Raptors | Runner    |   10 |    2 |    6 |   18 |    2 |    0 |    2 |    0 |    0 |    0 |    0 |   10 |


`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Raptors" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
`

#unfinished 

### Management

### Fans


### Famous Games


