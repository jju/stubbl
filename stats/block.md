# team ranks

## blocking ranks pre-GCX

| team              | BH   | SI   | Ki   | blocks | blitzes | sacks | sack_block | cas_block |
|-------------------|------|------|------|--------|---------|-------|------------|-----------|
| Filthy Tide       |   75 |   22 |   13 |   2006 |     757 |    76 |     0.0379 |    0.0548 |
| Zensun Vagabonds  |   74 |   28 |    7 |   2028 |     675 |    79 |     0.0390 |    0.0537 |
| Gargantuan Brutes |   42 |   27 |    3 |   1344 |     420 |    44 |     0.0327 |    0.0536 |
| TC Sump Runners   |   55 |   35 |    9 |   1965 |     618 |    57 |     0.0290 |    0.0504 |
| Darkling Spectres |   70 |   34 |    8 |   2421 |     583 |    59 |     0.0244 |    0.0463 |
| Ravenous Eagles   |   94 |   36 |   10 |   3112 |     794 |    58 |     0.0186 |    0.0450 |
| Orbital Machine   |   84 |   38 |   15 |   3053 |     710 |    49 |     0.0160 |    0.0449 |
| Cackling Furies   |   69 |   31 |   12 |   2528 |     643 |    57 |     0.0225 |    0.0443 |
| Vanadium Hunters  |   36 |   14 |    3 |   1288 |     404 |    41 |     0.0318 |    0.0411 |
| Badger Claws      |   22 |    7 |    5 |    895 |     428 |    33 |     0.0369 |    0.0380 |
| Carcosan Tatters  |   85 |   30 |   11 |   3343 |     725 |    51 |     0.0153 |    0.0377 |
| Kaiju Dynamo      |   54 |   25 |   11 |   2388 |     643 |    72 |     0.0302 |    0.0377 |
| Gore Farmers      |   58 |   44 |   14 |   3085 |     665 |    58 |     0.0188 |    0.0376 |
| Old Wyrms         |   50 |   13 |    3 |   1952 |     708 |    86 |     0.0441 |    0.0338 |
| Eldritch Fatality |   44 |   19 |    7 |   2386 |     697 |    91 |     0.0381 |    0.0293 |
| Irregular Cogs    |   44 |   17 |    9 |   2409 |     693 |    80 |     0.0332 |    0.0291 |
| Glorious Hounds   |   29 |   21 |    6 |   2037 |     690 |    78 |     0.0383 |    0.0275 |


```
SELECT 
	pl.f_tname AS team, 
	sum(md.bh) AS BH,
	sum(md.si) AS SI,
	sum(md.ki) AS Ki,
	sum(mx.inflicted_blocks) AS blocks, 
	sum(mx.blitz_actions) AS blitzes, 
	sum(mx.inflicted_sacks) AS sacks, 
	sum(mx.inflicted_sacks) / sum(mx.inflicted_blocks) AS sack_block, 
	(sum(md.bh) + sum(md.si) + sum(md.ki)) / sum(mx.inflicted_blocks) AS cas_block
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1
GROUP BY pl.f_tname 
ORDER BY cas_block DESC;
```
