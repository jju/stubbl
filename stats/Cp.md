In BludBol a completion (Cp) is recorded when one player successfully throws the ball to another player, who successfully catches it in the field of play. This does not include handoffs. Completions are a weird stat because they are dependent on having a teammate who can actually catch the ball.

In traditional [[SPP]] valuation, a Cp counts for 1 SPP. In the [[tVP]] valuation, completions are also worth 1 point (technically an [[oVP]]), but players are also credited with the distance they threw the ball.

Green Cup tournaments reward the season leader in Cps with the [[relentlesscannon]] (the award uses completion distance as a tiebreak).

# UBBL Cp Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.


| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| [[Elvis]]       | Old Wyrms         |    1 |  514 |  164 |    768 |    6 |    0 |    1 |   40 |    4 |    7 |  204 |
| **[[Filipa]]**  | Eldritch Fatality |    9 |  939 |  163 |    544 |   11 |    3 |    1 |   39 |    2 |    5 |  223 |
| [[Yosif]]       | Glorious Hounds   |    1 |  522 |  162 |   1000 |    8 |    2 |    0 |   24 |    2 |    2 |  179 |
| [[Cleve]]       | Badger Claws      |    0 |  613 |  136 |    388 |    1 |    1 |    0 |   70 |    1 |    3 |  153 |
| [[Luanna]]      | Cackling Furies   |    8 |  546 |  134 |    497 |    8 |    1 |    4 |   54 |    1 |    6 |  198 |
| [[Silas]]       | Filthy Tide       |    2 |  710 |  125 |    389 |    4 |    2 |    1 |   59 |    4 |    2 |  147 |
| [[Besz]]        | Irregular Cogs    |   23 | 1257 |  110 |    204 |   44 |    0 |    1 |   57 |    0 |    5 |  206 |
| [[Jacquetta]]   | TC Sump Runners   |    4 |  466 |  107 |    368 |   13 |    2 |    6 |   96 |    6 |    9 |  180 |
| **[[Oxana]]**   | Glorious Hounds   |    1 |  414 |  104 |    379 |    6 |    1 |    0 |   33 |    0 |    4 |  129 |
| [[Subrahmanya]] | Zensun Vagabonds  |    1 |  524 |   96 |    485 |    5 |    0 |    1 |   24 |    3 |    5 |  126 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY Cp DESC LIMIT 10;
```