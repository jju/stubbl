# Thrillers



## Playbook

Nova-Unglewort takes a similar approach to the traditional Unglewort playbook, but generally skews a little faster and more fragile. Instead of 4 generalist runners, two are specialized as attacking blitzers. The blockers are generally used more as roadblocks

## Records

### Open Level Record (W-D-L)

15-4-21

### UBBL Record (W-D-L)

1-1-0

### Prizes

*  UBBL Challenge IV - Runner-Up [[team2ndplace]]


### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Thrillers | UBBL Challenge IV  |    5 |    0 |    1 |      6 | 83.3333 |   14 |   10 |   11 |      3 |    4 |
| Thrillers | StUBBL Scramble    |    1 |    1 |    0 |      2 |      75 |    6 |    4 |    4 |      4 |    2 |
| Thrillers | Orange Goblet II   |    4 |    1 |    6 |     11 | 40.9091 |   21 |   21 |   13 |      3 |   -1 |
| Thrillers | UBBL Challenge III |    2 |    0 |    3 |      5 |      40 |   12 |   10 |   10 |      3 |   -1 |
| Thrillers | UBBL Challenge II  |    1 |    1 |    2 |      4 |    37.5 |    5 |    9 |    4 |     -1 |    2 |
| Thrillers | Orange Goblet      |    3 |    2 |    6 |     11 | 36.3636 |   19 |   20 |    9 |      3 |   -2 |
| Thrillers | UBBL Challenge     |    0 |    0 |    3 |      3 |       0 |    5 |   12 |    3 |      0 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Thrillers" ORDER BY mr.win_pct DESC limit 15;
```

## History


### Seasons


#### Projection OGII

W-D-L ?


### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Nanna   | Thrillers | Runner                |    6 |    3 |   13 |   22 |   10 |   29 |    2 |    0 |    0 |    0 |    3 |   78 |
| **Nagendra** | Thrillers | Runner                |   11 |    2 |   12 |   25 |   11 |   11 |    1 |    1 |    0 |    0 |    3 |   63 |
| **Olga**     | Thrillers | Attacker |   11 |    3 |   16 |   30 |   11 |    1 |    0 |    3 |    2 |    0 |    3 |   59 |
| **Shantanu** | Thrillers | Attacker |   13 |    4 |   15 |   32 |   14 |    0 |    1 |    5 |    1 |    1 |    0 |   58 |
| **Aljaz**    | Thrillers | Blitzer                |   15 |    4 |   21 |   40 |    3 |    2 |    1 |    7 |    1 |    0 |    2 |   39 |
| Aslaug  | Thrillers | Runner                |    3 |    2 |    7 |   12 |    8 |    7 |    0 |    0 |    1 |    0 |    0 |   33 |
| **Tacita**   | Thrillers | Line               |   12 |    1 |   12 |   25 |    0 |    0 |    0 |    1 |    0 |    0 |    6 |   32 |
| **Nahor**    | Thrillers | Attacker |    4 |    1 |    5 |   10 |    8 |    1 |    1 |    0 |    0 |    0 |    1 |   32 |
| **Mariyka**  | Thrillers | Runner                |    3 |    1 |    3 |    7 |    6 |    3 |    0 |    0 |    0 |    0 |    1 |   26 |
| Carole  | Thrillers | Blitzer                |   13 |    4 |   19 |   36 |    0 |    3 |    1 |    1 |    3 |    0 |    2 |   23 |
| **Virginia** | Thrillers | Line               |   11 |    3 |   16 |   30 |    0 |    0 |    0 |    2 |    1 |    1 |    3 |   23 |

`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Thrillers" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC 
limit 11;
`

#unfinished 

### Management

### Fans


### Famous Games


