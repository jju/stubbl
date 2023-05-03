In BludBol an interception (Int) is recorded when a player successfully grabs a ball being passed from one opposing teammate to another. It's very difficult to manage, but very valuable as it not only stops an opposing drive but starts a new one.

In traditional [[SPP]] valuation, an Int counts for 2 SPP. In the [[tVP]] valuation, completions are also worth 2 points (technically [[dVP]]s).

Usually there aren't enough interceptions in a season to justify an award, though the [[skylinepicker]] is an ad-hoc prize.

# UBBL Int Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.


| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| **[[Georgina]]**    | Arboreal Menace   |   41 |  672 |   12 |     45 |   59 |   14 |    0 |   33 |    1 |    5 |  188 |
| [[Babar]]      | Old Wyrms         |   29 |  368 |   15 |     30 |   36 |    9 |    5 |  135 |   17 |    3 |  145 |
| [[KneeMasher]] | Gore Farmers      |   31 |  422 |   10 |     28 |   33 |    8 |    5 |  162 |    8 |    2 |  139 |
| [[Oiva]]       | Glorious Hounds   |   30 |  463 |   29 |      8 |   63 |    8 |    3 |  112 |    8 |    3 |  156 |
| **[[Betul]]**       | Eldritch Fatality |   35 |  404 |    9 |     22 |   37 |    7 |    3 |   97 |    5 |    6 |  164 |
| **[[Shay]]**        | TC Sump Runners   |   15 |  651 |   70 |    134 |   50 |    7 |    1 |   50 |    0 |    4 |  151 |
| [[Gaenor]]     | TC Sump Runners   |    9 |  259 |   28 |     91 |    9 |    7 |    3 |   91 |    5 |    4 |   95 |
| [[Mihael]]     | Deep Dreamers     |   12 |  246 |    6 |     34 |   20 |    6 |    1 |    6 |    0 |    1 |   61 |
| **[[Frans]]**       | Irregular Cogs    |   30 |  350 |    7 |     22 |   35 |    6 |    2 |  102 |    1 |    4 |  133 |
| **[[Mia]]**         | Zensun Vagabonds  |   14 |  237 |    6 |     13 |   25 |    5 |    8 |  180 |    9 |    3 |   89 |

```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY "Int" DESC LIMIT 10;
```