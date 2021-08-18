# team ranks

## pro-level blocking ranks pre-GCXI

| Team              | BH   | SI   | Ki   | Blocks | Blitzes | Sacks | Sack_Block | Cas_Block |
|-------------------|------|------|------|--------|---------|-------|------------|-----------|
| Gargantuan Brutes |   42 |   27 |    3 |   1344 |     420 |    44 |     0.0327 |    0.0536 |
| Filthy Tide       |   86 |   27 |   16 |   2425 |     945 |    96 |     0.0396 |    0.0532 |
| Zensun Vagabonds  |   95 |   35 |   10 |   2701 |     871 |   102 |     0.0378 |    0.0518 |
| TC Sump Runners   |   73 |   41 |   12 |   2513 |     779 |    78 |     0.0310 |    0.0501 |
| Ravenous Eagles   |  135 |   55 |   13 |   4193 |    1050 |    82 |     0.0196 |    0.0484 |
| Orbital Machine   |  115 |   45 |   17 |   3913 |     909 |    69 |     0.0176 |    0.0452 |
| Mules             |    2 |    0 |    0 |     45 |      11 |     0 |     0.0000 |    0.0444 |
| Darkling Spectres |   82 |   42 |   12 |   3131 |     765 |    75 |     0.0240 |    0.0434 |
| Vanadium Hunters  |   36 |   14 |    3 |   1288 |     404 |    41 |     0.0318 |    0.0411 |
| Cackling Furies   |   85 |   39 |   15 |   3380 |     839 |    83 |     0.0246 |    0.0411 |
| Carcosan Tatters  |  107 |   44 |   14 |   4143 |     908 |    63 |     0.0152 |    0.0398 |
| Badger Claws      |   37 |   11 |    7 |   1424 |     648 |    52 |     0.0365 |    0.0386 |
| Gladiolas         |    1 |    0 |    0 |     26 |      10 |     2 |     0.0769 |    0.0385 |
| Gore Farmers      |   82 |   50 |   16 |   3947 |     861 |    80 |     0.0203 |    0.0375 |
| Kaiju Dynamo      |   76 |   28 |   13 |   3150 |     830 |    92 |     0.0292 |    0.0371 |
| Arboreal Menace   |    9 |    6 |    0 |    432 |     160 |    22 |     0.0509 |    0.0347 |
| Old Wyrms         |   59 |   19 |    3 |   2584 |     937 |    99 |     0.0383 |    0.0313 |
| Eldritch Fatality |   54 |   24 |    9 |   2928 |     856 |   105 |     0.0359 |    0.0297 |
| Irregular Cogs    |   57 |   20 |   11 |   3090 |     887 |   104 |     0.0337 |    0.0285 |
| Glorious Hounds   |   41 |   22 |    6 |   2493 |     868 |    99 |     0.0397 |    0.0277 |
| Thorns            |    0 |    0 |    0 |     21 |      12 |     0 |     0.0000 |    0.0000 |


```
SELECT 
	pl.f_tname AS Team, 
	sum(md.bh) AS BH,
	sum(md.si) AS SI,
	sum(md.ki) AS Ki,
	sum(mx.inflicted_blocks) AS Blocks, 
	sum(mx.blitz_actions) AS Blitzes, 
	sum(mx.inflicted_sacks) AS Sacks, 
	sum(mx.inflicted_sacks) / sum(mx.inflicted_blocks) AS Sack_Block, 
	(sum(md.bh) + sum(md.si) + sum(md.ki)) / sum(mx.inflicted_blocks) AS Cas_Block
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1
GROUP BY pl.f_tname 
ORDER BY Cas_Block DESC;
```

## blocking and fouling individual players by season

| Player | Team | Season | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Walton.  | Cackling Furies   | Green Cup VIII       |           0 |          0 |          0 |          0 |      8 |     0 |     0.0000 |    0.0000 |    23 |    2 |    0 |    0 |         6 |
| Ishii.   | Eldritch Fatality | Green Cup IX         |           0 |          0 |          0 |          0 |     50 |     0 |     0.0000 |    0.0000 |    22 |    0 |    0 |    0 |         1 |
| Eulaylia | Gore Farmers      | Green Cup X          |           0 |          0 |          0 |          0 |      8 |     0 |     0.0000 |    0.0000 |    22 |    0 |    0 |    0 |         3 |
| Leech.   | Ravenous Eagles   | Green Cup V Memorial |           0 |          0 |          0 |          0 |      3 |     0 |     0.0000 |    0.0000 |    21 |    1 |    0 |    0 |         4 |
| Lucius   | Old Wyrms         | Green Cup VII        |           1 |          0 |          1 |          0 |      2 |     1 |     0.5000 |    0.5000 |    19 |    0 |    0 |    0 |         2 |
| Walton.  | Cackling Furies   | Green Cup IX         |           2 |          1 |          1 |          0 |     17 |     0 |     0.0000 |    0.1176 |    17 |    1 |    1 |    2 |         2 |
| Ishii.   | Eldritch Fatality | Green Cup VIII       |           0 |          0 |          0 |          0 |     46 |     0 |     0.0000 |    0.0000 |    14 |    0 |    0 |    0 |         1 |
| Walton.  | Cackling Furies   | Green Cup VII        |           3 |          2 |          1 |          0 |     17 |     1 |     0.0588 |    0.1765 |    13 |    0 |    0 |    1 |         6 |
| Lucrece  | Carcosan Tatters  | Green Cup X          |           1 |          0 |          0 |          1 |     20 |     0 |     0.0000 |    0.0500 |    11 |    0 |    0 |    0 |         3 |
| Ondina   | Particulates      | Orange Goblet        |           0 |          0 |          0 |          0 |      6 |     1 |     0.1667 |    0.0000 |    11 |    0 |    0 |    0 |         0 |

```
SELECT  pl.name,  pl.f_tname, tours.name,  sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.name, pl.f_tname, tours.name ORDER BY sum(me.inflicted_fouls) DESC limit 10;
```

Above but totals
```
SELECT  pl.name,  pl.f_tname, sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.name, pl.f_tname ORDER BY sum(me.inflicted_foul_kills) DESC limit 10;
```