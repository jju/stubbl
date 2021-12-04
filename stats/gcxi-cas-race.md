# GCXI Casualty Leaderboard

At the end of the regular season these were the GCXI Casualty stats.

| Player   | Team             | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|----------|------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Uli     | Orbital Machine  | Green Cup XI |   22 |   13 |    9 |    0 |    174 |     2 |     0.0115 |    0.1264 |         86 |     0.4943 |
| Jantine | Ravenous Eagles  | Green Cup XI |   11 |    9 |    2 |    0 |     94 |     1 |     0.0106 |    0.1170 |         50 |     0.5319 |
| Percy   | Ravenous Eagles  | Green Cup XI |   11 |    3 |    5 |    3 |     65 |     0 |     0.0000 |    0.1692 |         44 |     0.6769 |
| Pippin  | Badger Claws     | Green Cup XI |    7 |    4 |    2 |    1 |     39 |     2 |     0.0513 |    0.1795 |         20 |     0.5128 |
| Marley  | Carcosan Tatters | Green Cup XI |    7 |    5 |    1 |    1 |     89 |     0 |     0.0000 |    0.0787 |         39 |     0.4382 |
| Odalric | Orbital Machine  | Green Cup XI |    7 |    4 |    2 |    1 |    103 |     1 |     0.0097 |    0.0680 |         51 |     0.4951 |
| Zina    | Irregular Cogs   | Green Cup XI |    6 |    3 |    2 |    1 |     86 |     5 |     0.0581 |    0.0698 |         43 |     0.5000 |
| Tijmen  | Kaiju Dynamo     | Green Cup XI |    6 |    5 |    1 |    0 |     58 |     0 |     0.0000 |    0.1034 |         26 |     0.4483 |
| Danr.   | Cackling Furies  | Green Cup XI |    5 |    4 |    1 |    0 |     47 |     1 |     0.0213 |    0.1064 |         22 |     0.4681 |
| Beitris | Gore Farmers     | Green Cup XI |    5 |    2 |    2 |    1 |     67 |     2 |     0.0299 |    0.0746 |         36 |     0.5373 |


```
SELECT  pl.name AS Player,  pl.f_tname AS Team, tours.name AS Season, sum(mp.cas) As "Cas", sum(mp.bh) AS "BH", sum(mp.si) AS "SI", sum(mp.ki) AS "Ki", sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_knock_downs) AS knockdowns, sum(me.inflicted_knock_downs) / sum(me.inflicted_blocks) AS down_block FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE tours.name = 'Green Cup XI' GROUP BY pl.name, pl.f_tname, tours.name ORDER BY sum(mp.cas) DESC limit 10;
```

Jantine and Percy never played in the same match, so what if we combined their numbers?

| Player           | Team             | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|------------------|------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Uli              | Orbital Machine  | Green Cup XI |   22 |   13 |    9 |    0 |    174 |     2 |     0.0115 |    0.1264 |         86 |     0.4943 |
| Jantine / Percy  | Ravenous Eagles  | Green Cup XI |   21 |   12 |    7 |    2 |    150 |     1 |     0.0067 |    0.1400 |         86 |     0.5733 |

Combined, Jantine and Percy were slightly more efficient, but would be relying on playoff appearances to push their hybrid form over the top.

## Top Casualty Performances in a Season

| Player   | Team             | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|----------|------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Jantine  | Ravenous Eagles   | Green Cup IX   |   25 |   19 |    5 |    1 |    168 |     0 |     0.0000 |    0.1488 |         81 |     0.4821 |
| Rohit.   | Zensun Vagabonds  | Green Cup VII  |   25 |   20 |    5 |    0 |    125 |    10 |     0.0800 |    0.2000 |         69 |     0.5520 |
| Jantine  | Ravenous Eagles   | Green Cup X    |   24 |   17 |    7 |    0 |    191 |     4 |     0.0209 |    0.1257 |        110 |     0.5759 |
| Somfuhr. | Filthy Tide       | Green Cup VIII |   24 |   16 |    7 |    1 |    151 |     4 |     0.0265 |    0.1589 |         80 |     0.5298 |
| Uli      | Orbital Machine   | Green Cup XI   |   22 |   13 |    9 |    0 |    174 |     2 |     0.0115 |    0.1264 |         86 |     0.4943 |
| Jantine / Percy  | Ravenous Eagles  | Green Cup XI |   21 |   12 |    7 |    2 |    150 |     1 |     0.0067 |    0.1400 |         86 |     0.5733 |
| Percy    | Ravenous Eagles   | Green Cup VII  |   17 |   13 |    4 |    0 |    238 |     4 |     0.0168 |    0.0714 |        137 |     0.5756 |
| Marzhak. | Gargantuan Brutes | Green Cup VII  |   16 |   11 |    5 |    0 |    154 |     5 |     0.0325 |    0.1039 |         74 |     0.4805 |
| Edwin.   | TC Sump Runners   | Green Cup IX   |   16 |   11 |    3 |    2 |     67 |     2 |     0.0299 |    0.2388 |         42 |     0.6269 |
| Ekua     | Ravenous Eagles   | Green Cup X    |   15 |    8 |    5 |    2 |    142 |     5 |     0.0352 |    0.1056 |         86 |     0.6056 |
| Snow.    | Cackling Furies   | Green Cup VIII |   14 |    8 |    4 |    2 |    130 |     1 |     0.0077 |    0.1077 |         65 |     0.5000 |

```
SELECT  pl.name AS Player,  pl.f_tname AS Team, tours.name AS Season, sum(mp.cas) As "Cas", sum(mp.bh) AS "BH", sum(mp.si) AS "SI", sum(mp.ki) AS "Ki", sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_knock_downs) AS knockdowns, sum(me.inflicted_knock_downs) / sum(me.inflicted_blocks) AS down_block FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.name, pl.f_tname, tours.name ORDER BY sum(mp.cas) DESC limit 10;
```

When we compare the hybrid Jantine/Percy with all-time best seasons we see them slotted into 6th place (before playoff matches, which are included in the rest of the seasons listed).

| Player   | Team             | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|----------|------------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Jantine  | Ravenous Eagles   |   63 |   48 |   14 |    1 |    518 |     6 |     0.0116 |    0.1216 |        282 |     0.5444 |
| Somfuhr. | Filthy Tide       |   61 |   42 |   13 |    6 |    557 |    15 |     0.0269 |    0.1095 |        281 |     0.5045 |
| Marzhak. | Gargantuan Brutes |   55 |   35 |   18 |    2 |    550 |    20 |     0.0364 |    0.1000 |        286 |     0.5200 |
| Rohit.   | Zensun Vagabonds  |   52 |   39 |   12 |    1 |    417 |    17 |     0.0408 |    0.1247 |        217 |     0.5204 |
| Uli      | Orbital Machine   |   47 |   32 |   14 |    1 |    522 |     8 |     0.0153 |    0.0900 |        285 |     0.5460 |
| Percy    | Ravenous Eagles   |   45 |   29 |   12 |    4 |    520 |     8 |     0.0154 |    0.0865 |        295 |     0.5673 |
| Ekua     | Ravenous Eagles   |   43 |   27 |   13 |    3 |    681 |    30 |     0.0441 |    0.0631 |        399 |     0.5859 |
| Katka    | Hoods             |   39 |   29 |    8 |    2 |    313 |    10 |     0.0319 |    0.1246 |        190 |     0.6070 |
| Simon    | Darkling Spectres |   35 |   22 |    8 |    5 |    339 |     4 |     0.0118 |    0.1032 |        218 |     0.6431 |
| Pierre   | Carcosan Tatters  |   31 |   19 |   10 |    2 |    367 |     2 |     0.0054 |    0.0845 |        224 |     0.6104 |


```
SELECT  pl.name AS Player,  pl.f_tname AS Team, sum(mp.cas) As "Cas", sum(mp.bh) AS "BH", sum(mp.si) AS "SI", sum(mp.ki) AS "Ki", sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_knock_downs) AS knockdowns, sum(me.inflicted_knock_downs) / sum(me.inflicted_blocks) AS down_block FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.name, pl.f_tname ORDER BY sum(mp.cas) DESC limit 10;
```

So how much does that efficiency matter? More knockdowns/block are going to be better but the best Casualty inflicter the UBBL has isn't the most efficient. Make of that what you will.