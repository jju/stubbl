A touchdown (TD) is recorded when a BludBol player is in control of the ball in the opposing team's endzone. This can happen because the player caught it there, carried the ball in, or was pushed in as long as they maintain control of the ball.

In traditional [[SPP]] valuation, a TD counts for 3 SPP. Usually this leads to scorers dominating the most valuable player competitions. In the [[tVP]] valuation, scoring itself is only counted as one point (technically an [[oVP]]), but players are also credited with more of the components of scoring, namely the distance run with the ball and if it was caught (as opposed to recovered from the ground).

Green Cup tournaments reward the season leader in TDs with the [[sardinecrown]].

# UBBL TD Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.


| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| [[Aeson]]    | Badger Claws      |  174 | 2280 |    3 |      3 |  145 |    0 |    0 |    7 |    0 |   10 |  575 |
| **[[Veens]]**     | Filthy Tide       |  106 | 1274 |    1 |      3 |   80 |    0 |    0 |    3 |    1 |    5 |  344 |
| **[[Ziba]]**      | Glorious Hounds   |   90 | 1028 |    3 |      2 |   86 |    2 |    1 |   18 |    1 |    7 |  314 |
| [[Costache]] | Glorious Hounds   |   76 |  640 |    3 |     -2 |   73 |    2 |    4 |   95 |    6 |    3 |  258 |
| [[Yakup]]    | Filthy Tide       |   73 |  986 |    1 |      1 |   67 |    0 |    1 |   23 |    2 |    4 |  242 |
| [[Souta]]    | Old Wyrms         |   72 |  923 |   51 |      5 |  132 |    3 |    3 |  113 |    9 |    4 |  299 |
| [[Sabah]]    | Kaiju Dynamo      |   66 |  856 |    2 |      4 |   33 |    0 |    0 |    7 |    0 |    3 |  215 |
| **[[Laurel]]**    | Arboreal Menace   |   58 |  883 |    0 |      0 |   72 |    2 |    0 |   15 |    1 |    4 |  198 |
| [[Atte]]     | Eldritch Fatality |   48 |  569 |    4 |      8 |   61 |    1 |    1 |  100 |    4 |    6 |  182 |
| [[Rickon]]   | Cackling Furies   |   41 |  559 |    2 |      4 |   55 |    2 |    1 |   71 |    2 |    4 |  151 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY TDs DESC LIMIT 10;
```