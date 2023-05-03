In BludBol the most valuable player (MVP) stat is recorded at the end of the match and is decided entirely by the fans. This means it has very very little relation to the actual play of anyone on the field.

In traditional [[SPP]] valuation, an MVP counts for 5 SPP. In the [[tVP]] valuation, they are ignored.

Green Cup tournaments reward the season leader in MVPs with the [[fanfavourite]] award.

# UBBL MVP Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.


| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| Aeson     | Badger Claws      |  174 | 2280 |    3 |      3 |  145 |    0 |    0 |    7 |    0 |   10 |  575 |
| **Anvil**      | Orbital Machine   |    0 |    2 |    0 |      0 |    0 |    0 |   10 |  264 |    1 |   10 |   70 |
| **Tacita**     | Thrillers         |    0 |    0 |    0 |      0 |    0 |    0 |    1 |   41 |    1 |   10 |   52 |
| Jacquetta | TC Sump Runners   |    4 |  466 |  107 |    368 |   13 |    2 |    6 |   96 |    6 |    9 |  180 |
| **Florinda**   | Glorious Hounds   |    4 |   46 |    4 |     24 |    6 |    3 |   17 |  499 |   17 |    9 |  101 |
| Erazem    | Irregular Cogs    |    4 |   29 |    2 |      0 |    0 |    1 |   11 |  355 |   18 |    8 |   78 |
| Hoss      | TC Sump Runners   |    3 |   25 |    0 |      0 |    3 |    1 |   10 |  277 |    4 |    8 |   71 |
| **Melchor**    | Vanadium Hunters  |    0 |  255 |   68 |    384 |    1 |    0 |    2 |   32 |    3 |    8 |  112 |
| **Beatrix**    | Eldritch Fatality |   23 |  248 |   12 |     75 |   24 |    4 |    7 |  236 |   15 |    8 |  143 |
| **Herman**     | Geometers         |    0 |    8 |    2 |      7 |    0 |    0 |    2 |   57 |    0 |    8 |   46 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY MVPs DESC LIMIT 10;
```