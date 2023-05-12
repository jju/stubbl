# ubbl challenge v

* [[prizes/mvp]] - [[Evgenia]] [^1] [[newcursed]]
* [[carminefist]] - [[Asketill]] [[umberhulks]]
* [[team1stplace]] - [[xenothrillers]]
* [[team2ndplace]] - [[arborealmenace]]
* [[team3rdplace]] - [[newcursed]]
* [[teamcasualties]] - [[orbitalmachine]]

## season leaderboards

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) AS oVP, (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS dVP, sum(md.td) + sum(md.cp) + sum(mx.catches) + (sum(mx.rushing_distance_move) * 0.1) + (sum(mx.pass_distance) * 0.1) + (sum(md.intcpt) * 2) + sum(md.bh) + sum(md.si) + sum(md.ki) + (sum(mx.inflicted_blocks) * 0.2) + sum(mx.inflicted_sacks) AS tVP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "UBBL Challenge V" GROUP BY pl.name, pl.f_tname ORDER BY tVP DESC LIMIT 5;
```


### mvp

| Player    | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP  | dVP  | tVP  |
|-----------|------------------|------|------|------|--------|------|------|------|------|------|------|------|------|
| [[Green]]     | Zensun Vagabonds |    8 |   84 |    1 |      0 |    6 |    0 |    1 |   19 |    1 | 23.4 |  5.8 | 29.2 |
| Ingeborg  | Arboreal Menace  |    0 |   56 |   14 |     63 |    0 |    0 |    2 |    4 |    0 | 25.9 |  2.8 | 28.7 |
| Laurel    | Arboreal Menace  |    6 |  126 |    0 |      0 |    8 |    0 |    0 |    1 |    1 | 26.6 |  1.2 | 27.8 |
| Ophelia   | Badger Claws     |    6 |  123 |    0 |      0 |    9 |    0 |    0 |    0 |    0 | 27.3 |  0.0 | 27.3 |
| Gianna    | Badger Claws     |    1 |   75 |   14 |     30 |    0 |    0 |    0 |    3 |    0 | 25.5 |  0.6 | 26.1 |

[^1]: [[Evgenia]] from the [[newcursed]] won the MVP award to great opprobrium from people who actually watched the games. Green did far more for her team on both sides of the ball as shown by her tVP score above, but the crowds loved [[Evgenia]] and she won the award.

### casualties

| Player    | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | oVP  | dVP  | tVP  |
|-----------|------------------|------|------|------|--------|------|------|------|------|------|------|------|------|
| Asketill | Umber Hulks     |    0 |    0 |    0 |      0 |    0 |    0 |    4 |   18 |    3 |  0.0 | 10.6 | 10.6 |
| Ioana.   | Orbital Machine |    0 |    0 |    0 |      0 |    0 |    0 |    3 |   35 |    1 |  0.0 | 11.0 | 11.0 |
| Odalric  | Orbital Machine |    0 |    0 |    0 |      0 |    0 |    0 |    3 |   20 |    1 |  0.0 |  8.0 |  8.0 |
| Friese.  | Badger Claws    |    0 |    0 |    0 |      0 |    0 |    0 |    3 |   32 |    0 |  0.0 |  9.4 |  9.4 |
| Teodora  | Particulates    |    0 |    0 |    0 |      0 |    0 |    0 |    3 |   14 |    0 |  0.0 |  5.8 |  5.8 |