# Thorns


## Playbook

The Thorns use what's known as the Excelsior playbook, where a fast fragile receiving corps works together downfield making catches in traffic and getting out of trouble. It's a shorter-passing game than the High Extension playbook used by the [Gladiolas](gladiolas) but when you can avoid injury it's very effective, as the Pro-Level [Old Wyrms](oldwyrms) have shown.

## History


## Records

### Open Level Record (W-D-L)

15-2-9

### UBBL Record (W-D-L)

17-2-9

### Prizes

* Orange Goblet I - Runner Up [[team2ndplace]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Thorns | StUBBL Scramble    |    1 |    0 |    0 |      1 |     100.00 |    4 |    1 |    3 |      3 |    1 |
| Thorns | Champions Circuit  |    1 |    0 |    0 |      1 |     100.00 |    2 |    1 |    0 |      0 |    1 |
| Thorns | UBBL Challenge II  |    3 |    0 |    1 |      4 |      75.00 |   12 |    4 |    5 |     -2 |    1 |
| Thorns | UBBL Challenge III |    4 |    0 |    2 |      6 | 66.67 |   19 |   12 |    5 |     -1 |    1 |
| Thorns | Orange Goblet      |    7 |    1 |    5 |     13 | 57.69 |   31 |   26 |   15 |     -5 |    0 |
| Thorns | UBBL Challenge     |    1 |    1 |    1 |      3 |      50.00 |   10 |    8 |    5 |      0 |    1 |
| Thorns | Orange Goblet II |    4 |    0 |    6 |     10 |      40 |   22 |   22 |    6 |    -13 |   -2 |

## History

The Thorns were a good Open level team and are waiting to prove themselves even better in Pro-Level play, but they had a piss-poor Orange Goblet II season which means they are missing out on OGIII.

### Stars & Scrubs

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| Achille   | Thorns | Catcher  |   15 |    1 |    9 |   25 |   26 |   14 |    1 |    1 |    1 |    0 |    3 |  113 |
| **Balwinder**  | Thorns | Thrower  |   15 |    2 |   10 |   27 |    1 |   65 |    0 |    0 |    0 |    0 |    3 |   83 |
| **Sukhdeep**   | Thorns | Catcher  |   15 |    2 |   13 |   30 |   12 |    5 |    2 |    4 |    0 |    1 |    3 |   70 |
| **Horsa**      | Thorns | Blitzer  |   17 |    2 |   14 |   33 |    8 |    3 |    0 |    6 |    2 |    0 |    3 |   58 |
| **Norma**      | Thorns | Catcher  |   14 |    2 |   11 |   27 |   11 |   16 |    0 |    0 |    0 |    0 |    1 |   54 |
| Hildefons | Thorns | Catcher  |   10 |    1 |    7 |   18 |   10 |    5 |    1 |    1 |    1 |    1 |    2 |   53 |
| **Daphnee**    | Thorns | Lineman  |   18 |    2 |   13 |   33 |    3 |    3 |    0 |    0 |    1 |    0 |    6 |   44 |
| **Roelof**     | Thorns | Lineman  |   19 |    2 |   13 |   34 |    1 |    2 |    0 |    1 |    2 |    0 |    5 |   36 |
| **Tamara**     | Thorns | Catcher  |    4 |    0 |    6 |   10 |    9 |    2 |    0 |    0 |    0 |    0 |    1 |   34 |
| **Sakiko**     | Thorns | Lineman  |   19 |    2 |   14 |   35 |    2 |   15 |    0 |    1 |    0 |    1 |    1 |   30 |
| Christen  | Thorns | Blitzer  |    8 |    1 |    4 |   13 |    2 |    1 |    2 |    1 |    2 |    0 |    2 |   27 |

`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_did = 3 AND pl.f_tname = "Thorns" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC 
limit 11;
`


### Management


### Fans


### Famous Games

#unfinished