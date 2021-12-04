# GCXI Team Matchups

## Basic Records

| Team              | Season       | won  | draw | lost | played | win_pct | gf   | ga   | GF_match | GA_match | cas  | Cas_match | tcdiff | ff   |
|-------------------|--------------|------|------|------|--------|---------|------|------|----------|----------|------|-----------|--------|------|
| Eldritch Fatality | Green Cup XI | **12** |  0 |    4 |     16 |      75 |   46 |   31 |   2.8750 |   1.9375 |   17 |    1.0625 |    -15 |    2 |
| Filthy Tide       | Green Cup XI |   11 |    2 |    3 |     16 |      75 |   72 |   53 |   4.5000 |   3.3125 |   11 |    0.6875 |    -20 |    1 |
| Arboreal Menace   | Green Cup XI |   10 |    2 |    4 |     16 |   68.75 |   60 |   47 |   3.7500 |   2.9375 |   14 |    0.8750 |     -6 |    2 |
| Glorious Hounds   | Green Cup XI |   10 |    4 | **2** |    16 |      75 | **73** | 44 |   4.5625 |   2.7500 |   13 |    0.8125 |    -13 |   -1 |
| Kaiju Dynamo      | Green Cup XI |   10 |    1 |    5 |     16 |  65.625 |   35 |   28 |   2.1875 |   1.7500 |   27 |    1.6875 |      9 |    2 |
| Irregular Cogs    | Green Cup XI |    9 |    2 |    5 |     16 |    62.5 |   46 |   36 |   2.8750 |   2.2500 |   19 |    1.1875 |      0 |    0 |
| Darkling Spectres | Green Cup XI |    8 |    1 |    7 |     16 |  53.125 |   33 |   45 |   2.0625 |   2.8125 |   20 |    1.2500 |      6 |    2 |
| Carcosan Tatters  | Green Cup XI |    7 |    2 |    7 |     16 |      50 |   28 |   26 |   1.7500 |   1.6250 |   41 |    2.5625 |     24 |    0 |
| Gore Farmers      | Green Cup XI |    5 |    2 |    9 |     16 |    37.5 |   24 |   35 |   1.5000 |   2.1875 |   28 |    1.7500 |     19 |   -1 |
| Ravenous Eagles   | Green Cup XI |    5 |    3 |    8 |     16 |  40.625 |   16 | **24** | 1.0000 |   1.5000 | **45** |    2.8125 |   26 |    0 |
| Zensun Vagabonds  | Green Cup XI |    5 |    2 |    9 |     16 |    37.5 |   32 |   45 |   2.0000 |   2.8125 |   22 |    1.3750 |     -4 |   -3 |
| Old Wyrms         | Green Cup XI |    5 |    3 |    8 |     16 |  40.625 |   39 |   46 |   2.4375 |   2.8750 |   12 |    0.7500 |    -16 |   -4 |
| Cackling Furies   | Green Cup XI |    5 |    2 |    9 |     16 |    37.5 |   32 |   36 |   2.0000 |   2.2500 |   25 |    1.5625 |     -2 |    0 |
| Badger Claws      | Green Cup XI |    4 |    4 |    8 |     16 |    37.5 |   53 |   59 |   3.3125 |   3.6875 |   22 |    1.3750 |    -18 |   -4 |
| TC Sump Runners   | Green Cup XI |    1 |    4 |   11 |     16 |   18.75 |   26 |   46 |   1.6250 |   2.8750 |   19 |    1.1875 |    -12 |   -4 |
| Orbital Machine   | Green Cup XI |    1 | **6** |   9 |     16 |      25 |   16 |   30 |   1.0000 |   1.8750 |   40 |    2.5000 |     22 |   -2 |


```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.gf/mr.played AS GF_match, mr.ga/mr.played AS GA_match, mr.cas, mr.cas/mr.played AS Cas_match, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE tours.name = "Green Cup XI" ORDER BY mr.won DESC limit 16;
```

## Passing Stats

| Team              | Season       | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|--------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Glorious Hounds   | Green Cup XI |   82 |      109 | 0.7523 |   72 | 0.8780 |          1 |   0.0092 |      16 |  0.1951 |
| Old Wyrms         | Green Cup XI |   72 |       96 | 0.7500 |   39 | 0.5417 |          5 |   0.0521 |      11 |  0.1528 |
| Arboreal Menace   | Green Cup XI |   67 |       83 | 0.8072 |   59 | 0.8806 |          2 |   0.0241 |      10 |  0.1493 |
| Irregular Cogs    | Green Cup XI |   65 |      106 | 0.6132 |   46 | 0.7077 |          9 |   0.0849 |      11 |  0.1692 |
| Eldritch Fatality | Green Cup XI |   65 |       87 | 0.7471 |   45 | 0.6923 |          5 |   0.0575 |      15 |  0.2308 |
| Zensun Vagabonds  | Green Cup XI |   60 |       77 | 0.7792 |   32 | 0.5333 |          4 |   0.0519 |      10 |  0.1667 |
| Cackling Furies   | Green Cup XI |   60 |       90 | 0.6667 |   32 | 0.5333 |          3 |   0.0333 |       7 |  0.1167 |
| Badger Claws      | Green Cup XI |   57 |       82 | 0.6951 |   53 | 0.9298 |          5 |   0.0610 |      24 |  0.4211 |
| Filthy Tide       | Green Cup XI |   57 |       83 | 0.6867 |   71 | 1.2456 |          3 |   0.0361 |      27 |  0.4737 |
| TC Sump Runners   | Green Cup XI |   47 |       82 | 0.5732 |   26 | 0.5532 |          8 |   0.0976 |      17 |  0.3617 |
| Darkling Spectres | Green Cup XI |   36 |       66 | 0.5455 |   33 | 0.9167 |          4 |   0.0606 |       9 |  0.2500 |
| Carcosan Tatters  | Green Cup XI |   36 |       59 | 0.6102 |   28 | 0.7778 |          4 |   0.0678 |      10 |  0.2778 |
| Gore Farmers      | Green Cup XI |   32 |       56 | 0.5714 |   24 | 0.7500 |          5 |   0.0893 |      16 |  0.5000 |
| Orbital Machine   | Green Cup XI |   17 |       33 | 0.5152 |   16 | 0.9412 |          3 |   0.0909 |      17 |  1.0000 |
| Ravenous Eagles   | Green Cup XI |   17 |       29 | 0.5862 |   16 | 0.9412 |          2 |   0.0690 |      10 |  0.5882 |
| Kaiju Dynamo      | Green Cup XI |   14 |       41 | 0.3415 |   35 | 2.5000 |          1 |   0.0244 |      31 |  2.2143 |


```
SELECT pl.f_tname AS Team, tours.name as Season, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(md.td) AS TD, sum(md.td) / sum(md.cp) AS TD_Cp, sum(mx.interceptions_thrown) - sum(mx.safe_throws) AS Int_Thrown, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS Int_Rate, sum(mx.handoffs) AS Handoff, sum(mx.handoffs) / sum(md.cp) AS Hand_Cp FROM match_data_es AS mx 	JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id and mx.f_did = tours.f_did WHERE tours.name = 'Green Cup XI' GROUP BY pl.f_tname ORDER BY Cp DESC;
```


### Top Passing Teams in a Season

| Team              | Season         | Cp   | Attempts | Cp_Pct | TD   | TD_Cp  | Int_Thrown | Int_Rate | Handoff | Hand_Cp |
|-------------------|----------------|------|----------|--------|------|--------|------------|----------|---------|---------|
| Old Wyrms         | Green Cup IX   |  122 |      146 | 0.8356 |   71 | 0.5820 |          4 |   0.0274 |       7 |  0.0574 |
| Old Wyrms         | Green Cup X    |   97 |      129 | 0.7519 |   60 | 0.6186 |          8 |   0.0620 |      11 |  0.1134 |
| Glorious Hounds   | Green Cup IX   |   89 |      108 | 0.8241 |   58 | 0.6517 |          5 |   0.0463 |      13 |  0.1461 |
| Old Wyrms         | Green Cup VIII |   83 |      112 | 0.7411 |   38 | 0.4578 |          6 |   0.0536 |      10 |  0.1205 |
| Old Wyrms         | Green Cup VII  |   83 |      120 | 0.6917 |   45 | 0.5422 |         10 |   0.0833 |      12 |  0.1446 |
| **Glorious Hounds**   | Green Cup XI   |   82 |      109 | 0.7523 |   72 | 0.8780 |          1 |   0.0092 |      16 |  0.1951 |
| Glorious Hounds   | Green Cup VIII |   78 |       98 | 0.7959 |   50 | 0.6410 |          0 |   0.0000 |       7 |  0.0897 |
| Irregular Cogs    | Green Cup IX   |   77 |      115 | 0.6696 |   48 | 0.6234 |          7 |   0.0609 |      11 |  0.1429 |
| Glorious Hounds   | Green Cup VII  |   73 |       99 | 0.7374 |   60 | 0.8219 |          2 |   0.0202 |      17 |  0.2329 |
| Eldritch Fatality | Green Cup IX   |   72 |      110 | 0.6545 |   56 | 0.7778 |          7 |   0.0636 |      11 |  0.1528 |

```
SELECT pl.f_tname AS Team, tours.name as Season, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(md.td) AS TD, sum(md.td) / sum(md.cp) AS TD_Cp, sum(mx.interceptions_thrown) - sum(mx.safe_throws) AS Int_Thrown, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS Int_Rate, sum(mx.handoffs) AS Handoff, sum(mx.handoffs) / sum(md.cp) AS Hand_Cp FROM match_data_es AS mx 	JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id and mx.f_did = tours.f_did WHERE md.f_did = 1 GROUP BY pl.f_tname, tours.name ORDER BY Cp DESC LIMIT 10;
```

## Rushing

| Team              | Season       | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-------------------|--------------|---------|---------|------|---------|------------|
| Filthy Tide       | Green Cup XI |     216 |    1254 |   71 | 17.6620 |       3.04 |
| Glorious Hounds   | Green Cup XI |     207 |    1123 |   72 | 15.5972 |       2.88 |
| Badger Claws      | Green Cup XI |     196 |    1083 |   53 | 20.4340 |       3.70 |
| Arboreal Menace   | Green Cup XI |     189 |    1081 |   59 | 18.3220 |       3.20 |
| Irregular Cogs    | Green Cup XI |     176 |     900 |   46 | 19.5652 |       3.83 |
| Kaiju Dynamo      | Green Cup XI |     136 |     827 |   35 | 23.6286 |       3.89 |
| Eldritch Fatality | Green Cup XI |     178 |     797 |   45 | 17.7111 |       3.96 |
| Old Wyrms         | Green Cup XI |     183 |     785 |   39 | 20.1282 |       4.69 |
| Zensun Vagabonds  | Green Cup XI |     180 |     736 |   32 | 23.0000 |       5.63 |
| Cackling Furies   | Green Cup XI |     170 |     720 |   32 | 22.5000 |       5.31 |
| Darkling Spectres | Green Cup XI |     144 |     662 |   33 | 20.0606 |       4.36 |
| Carcosan Tatters  | Green Cup XI |     138 |     604 |   28 | 21.5714 |       4.93 |
| Gore Farmers      | Green Cup XI |     137 |     586 |   24 | 24.4167 |       5.71 |
| TC Sump Runners   | Green Cup XI |     156 |     578 |   26 | 22.2308 |       6.00 |
| Orbital Machine   | Green Cup XI |     114 |     530 |   16 | 33.1250 |       7.13 |
| Ravenous Eagles   | Green Cup XI |     106 |     467 |   16 | 29.1875 |       6.63 |


```
SELECT pl.f_tname AS Team, tours.name AS Season, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(mx.rushing_distance_leap) + sum(mx.rushing_distance_push) + sum(mx.rushing_distance_move) + sum(mx.rushing_distance_block) + sum(mx.rushing_distance_shadowing) AS Rushing, sum(md.td) AS TDs, (sum(mx.rushing_distance_leap) + sum(mx.rushing_distance_push) + sum(mx.rushing_distance_move) + sum(mx.rushing_distance_block) + sum(mx.rushing_distance_shadowing)) / sum(md.td) AS Rush_TD, round(((sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td)),2) AS Touches_TD FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id and mx.f_did = tours.f_did WHERE tours.name = "Green Cup XI" GROUP BY pl.f_tname, tours.name ORDER BY Rushing DESC;
```

### Top Team Rushing Seasons

| Team            | Season         | Touches | Rushing | TDs  | Rush_TD | Touches_TD |
|-----------------|----------------|---------|---------|------|---------|------------|
| Badger Claws    | Green Cup IX   |     183 |    1371 |   75 | 18.2800 |       2.44 |
| Badger Claws    | Green Cup X    |     218 |    1262 |   64 | 19.7188 |       3.41 |
| **Filthy Tide**     | Green Cup XI   |     216 |    1254 |   71 | 17.6620 |       3.04 |
| Old Wyrms       | Green Cup IX   |     241 |    1172 |   71 | 16.5070 |       3.39 |
| Badger Claws    | Green Cup VIII |     221 |    1128 |   61 | 18.4918 |       3.62 |
| **Glorious Hounds** | Green Cup XI   |     207 |    1123 |   72 | 15.5972 |       2.88 |
| Filthy Tide     | Green Cup X    |     196 |    1085 |   50 | 21.7000 |       3.92 |
| **Badger Claws**    | Green Cup XI   |     196 |    1083 |   53 | 20.4340 |       3.70 |
| **Arboreal Menace** | Green Cup XI   |     189 |    1081 |   59 | 18.3220 |       3.20 |
| Filthy Tide     | Green Cup IX   |     204 |    1030 |   45 | 22.8889 |       4.53 |


```
SELECT pl.f_tname AS Team, tours.name AS Season, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(mx.rushing_distance_leap) + sum(mx.rushing_distance_push) + sum(mx.rushing_distance_move) + sum(mx.rushing_distance_block) + sum(mx.rushing_distance_shadowing) AS Rushing, sum(md.td) AS TDs, (sum(mx.rushing_distance_leap) + sum(mx.rushing_distance_push) + sum(mx.rushing_distance_move) + sum(mx.rushing_distance_block) + sum(mx.rushing_distance_shadowing)) / sum(md.td) AS Rush_TD, round(((sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td)),2) AS Touches_TD FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id JOIN tours ON mx.f_trid = tours.tour_id and mx.f_did = tours.f_did WHERE md.f_did = 1 GROUP BY pl.f_tname, tours.name ORDER BY Rushing DESC LIMIT 10;
```

## Casualty Blocking Stats

At the end of the regular season these were the GCXI Casualty stats.

| Team              | Season       | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|--------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Ravenous Eagles   | Green Cup XI |   45 |   23 |   13 |    9 |    792 |    28 |     0.0354 |    0.0568 |        445 |     0.5619 |
| Carcosan Tatters  | Green Cup XI |   40 |   25 |    7 |    8 |    840 |    15 |     0.0179 |    0.0476 |        419 |     0.4988 |
| Orbital Machine   | Green Cup XI |   39 |   22 |   15 |    2 |    787 |    14 |     0.0178 |    0.0496 |        420 |     0.5337 |
| Gore Farmers      | Green Cup XI |   28 |   16 |    9 |    3 |    712 |    13 |     0.0183 |    0.0393 |        384 |     0.5393 |
| Kaiju Dynamo      | Green Cup XI |   27 |   23 |    3 |    1 |    765 |    18 |     0.0235 |    0.0353 |        428 |     0.5595 |
| Cackling Furies   | Green Cup XI |   25 |   18 |    7 |    0 |    718 |    18 |     0.0251 |    0.0348 |        371 |     0.5167 |
| Zensun Vagabonds  | Green Cup XI |   22 |   15 |    5 |    2 |    499 |    17 |     0.0341 |    0.0441 |        248 |     0.4970 |
| Badger Claws      | Green Cup XI |   20 |   11 |    8 |    1 |    424 |    17 |     0.0401 |    0.0472 |        176 |     0.4151 |
| Darkling Spectres | Green Cup XI |   20 |   11 |    7 |    2 |    590 |    15 |     0.0254 |    0.0339 |        303 |     0.5136 |
| Irregular Cogs    | Green Cup XI |   19 |   12 |    5 |    2 |    642 |    26 |     0.0405 |    0.0296 |        294 |     0.4579 |
| TC Sump Runners   | Green Cup XI |   19 |    9 |    7 |    3 |    551 |    16 |     0.0290 |    0.0345 |        268 |     0.4864 |
| Eldritch Fatality | Green Cup XI |   17 |   13 |    4 |    0 |    541 |    20 |     0.0370 |    0.0314 |        251 |     0.4640 |
| Arboreal Menace   | Green Cup XI |   14 |   14 |    0 |    0 |    399 |    20 |     0.0501 |    0.0351 |        198 |     0.4962 |
| Glorious Hounds   | Green Cup XI |   13 |    7 |    6 |    0 |    414 |    23 |     0.0556 |    0.0314 |        204 |     0.4928 |
| Old Wyrms         | Green Cup XI |   12 |    6 |    5 |    1 |    573 |    17 |     0.0297 |    0.0209 |        228 |     0.3979 |
| Filthy Tide       | Green Cup XI |   11 |    7 |    4 |    0 |    367 |    16 |     0.0436 |    0.0300 |        149 |     0.4060 |


```
SELECT  pl.f_tname AS Team, tours.name AS Season, sum(mp.cas) As "Cas", sum(mp.bh) AS "BH", sum(mp.si) AS "SI", sum(mp.ki) AS "Ki", sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_knock_downs) AS knockdowns, sum(me.inflicted_knock_downs) / sum(me.inflicted_blocks) AS down_block FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE tours.name = 'Green Cup XI' GROUP BY pl.f_tname, tours.name ORDER BY sum(mp.cas) DESC limit 16;
```



### Top Casualty Teams in a Season

| Team              | Season         | Cas  | BH   | SI   | Ki   | blocks | sacks | sack_block | cas_block | knockdowns | down_block |
|-------------------|----------------|------|------|------|------|--------|-------|------------|-----------|------------|------------|
| Ravenous Eagles   | Green Cup X    |   61 |   40 |   18 |    3 |   1034 |    22 |     0.0213 |    0.0590 |        577 |     0.5580 |
| Orbital Machine   | Green Cup VIII |   49 |   28 |   12 |    9 |    929 |    13 |     0.0140 |    0.0527 |        521 |     0.5608 |
| **Ravenous Eagles**   | Green Cup XI   |   45 |   23 |   13 |    9 |    792 |    28 |     0.0354 |    0.0568 |        445 |     0.5619 |
| Cackling Furies   | Green Cup VIII |   43 |   24 |   13 |    6 |    762 |    17 |     0.0223 |    0.0564 |        376 |     0.4934 |
| Ravenous Eagles   | Green Cup IX   |   43 |   28 |   12 |    3 |    710 |     9 |     0.0127 |    0.0606 |        381 |     0.5366 |
| Filthy Tide       | Green Cup VIII |   42 |   25 |   11 |    6 |    532 |    24 |     0.0451 |    0.0789 |        265 |     0.4981 |
| Darkling Spectres | Green Cup VIII |   42 |   26 |   12 |    4 |    714 |    13 |     0.0182 |    0.0588 |        393 |     0.5504 |
| Gore Farmers      | Green Cup VIII |   42 |   18 |   18 |    6 |    939 |    21 |     0.0224 |    0.0447 |        507 |     0.5399 |
| Orbital Machine   | Green Cup VII  |   42 |   28 |   13 |    1 |    859 |    15 |     0.0175 |    0.0489 |        449 |     0.5227 |
| Ravenous Eagles   | Green Cup VII  |   40 |   24 |   15 |    1 |   1018 |    17 |     0.0167 |    0.0393 |        532 |     0.5226 |

```
SELECT  pl.f_tname AS Team, tours.name AS Season, sum(mp.cas) As "Cas", sum(mp.bh) AS "BH", sum(mp.si) AS "SI", sum(mp.ki) AS "Ki", sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_knock_downs) AS knockdowns, sum(me.inflicted_knock_downs) / sum(me.inflicted_blocks) AS down_block FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.f_tname, tours.name ORDER BY sum(mp.cas) DESC limit 10;
```

