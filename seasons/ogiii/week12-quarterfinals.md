# week 12

#t2789

## matchups

Playoffs are here! The Gladiolas take on the Hunters, the Mules duel the Warthogs, the Raptors face the Hoods and the Deep Dreamers square off against the Magpies.

The favourites took victory in each of the first three playoff matches making it look like the Orange Goblet really will be a battle of the best teams if the Gladiolas dispose of the Hunters as easily as expected.

But as seems to always happen come playoff time, the Gladiolas lost to an inferior team and will not be duking it out for the Goblet.

## standings

| Team | W-D-L |
|-------|-----|
| Mules | 9-1-1 |
| Raptors | 9-1-1 |
| *Gladiolas* | 8-1-2 |
| Deep Dreamers | 7-1-3 |
| *Magpies* | 5-2-4 |
| *Hoods* | 5-0-6 |
| *Warthogs* | 3-2-6 |
| Vanadium Hunters | 3-2-6 |
| *Geometers* | 1-2-7 |
| *Thrillers* | 1-1-8 |
| *Umber Hulks* | 1-1-8 |


## player of the week standings

| Player    | Team             | TDs  | Rush | Cp   | CpDist | Ctch | Int | Cas  | Blck | Sck | MVP | SPP  |
|-----------|------------------|------|------|------|----------|---------|---|---|--------|-------|------|------|
| Amata     | Vanadium Hunters |    2 |   23 |    1 |      3 |    4 |    0 |    1 |    1 |    1 |    1 |   14 |
| Marita    | Deep Dreamers    |    2 |   21 |    0 |      0 |    4 |    0 |    0 |    0 |    0 |    0 |    6 |
| Pilvi     | Mules            |    2 |   31 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    0 |    6 |
| Erastos   | Vanadium Hunters |    1 |    8 |    0 |      0 |    0 |    0 |    1 |    3 |    0 |    0 |    5 |
| Eufemia   | Gladiolas        |    0 |   13 |    5 |     12 |    0 |    0 |    0 |    0 |    0 |    0 |    5 |
| Renatus   | Mules            |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    5 |    0 |    1 |    5 |
| Brynja    | Deep Dreamers    |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    3 |    0 |    1 |    5 |
| Ella      | Raptors          |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    0 |    0 |    1 |    5 |
| Gaszi     | Magpies          |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    4 |    0 |    1 |    5 |
| Primitiva | Warthogs         |    0 |    0 |    0 |      0 |    0 |    0 |    0 |    2 |    0 |    1 |    5 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet III" AND mt.round = 252 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```
