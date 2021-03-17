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
