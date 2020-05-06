# team stats

## passing ranks pre-GCX

| team              | cp   | attempts | comp_pct | distance | pass_average |
|-------------------|------|----------|----------|----------|--------------|
| Old Wyrms         |  350 |      462 |   0.7576 |     1050 |       3.0000 |
| Glorious Hounds   |  282 |      362 |   0.7790 |     1219 |       4.3227 |
| Eldritch Fatality |  214 |      351 |   0.6097 |      666 |       3.1121 |
| Irregular Cogs    |  226 |      348 |   0.6494 |      515 |       2.2788 |
| Filthy Tide       |  215 |      321 |   0.6698 |      547 |       2.5442 |
| Zensun Vagabonds  |  163 |      248 |   0.6573 |      671 |       4.1166 |
| TC Sump Runners   |  145 |      246 |   0.5894 |      507 |       3.4966 |
| Darkling Spectres |  112 |      228 |   0.4912 |      342 |       3.0536 |
| Cackling Furies   |  121 |      216 |   0.5602 |      413 |       3.4132 |
| Gore Farmers      |  125 |      201 |   0.6219 |      420 |       3.3600 |
| Badger Claws      |  128 |      173 |   0.7399 |      316 |       2.4688 |
| Kaiju Dynamo      |   79 |      172 |   0.4593 |      157 |       1.9873 |
| Vanadium Hunters  |   93 |      169 |   0.5503 |      426 |       4.5806 |
| Gargantuan Brutes |   86 |      159 |   0.5409 |      315 |       3.6628 |
| Orbital Machine   |   69 |      136 |   0.5074 |      221 |       3.2029 |
| Carcosan Tatters  |   65 |      128 |   0.5078 |      205 |       3.1538 |
| Ravenous Eagles   |   52 |      111 |   0.4685 |      141 |       2.7115 |

You can see the different passing strategies in the good passing teams pretty clearly in this table. The [Old Wyrms](../teams/oldwyrms) attempted (OW 462 vs GH 362) and completed (OW 350 vs GH 282) more passes than the [Glorious Hounds](../teams/glorioushounds), but the Hounds get more distance out of each one (GH 4.32 vs OW 3.00).

While the Wyrms and Glorious Hounds are by far the most prolific passers it's a little bit interesting to note that the [Badger Claws](../teams/badgerclaws) come close for their completion percentages (GH 77% OW 76% BC 74%). Also somewhat interesting is that the [Vanadium Hunters](../teams/vanadiumhunters) were even more of a deep threat than the Hounds when they made their passes (VH 4.58 squares/completion vs GH 4.32), but because they only completed 55% of them we don't think of the Hunters as a passing team. Is it strange that the Vagabonds are the only other team with an average pass distance over 4?

The shortest passers in the Pros are the [Kaiju Dynamo](../teams/kaijudynamo) (KD 1.99 squares/completion), surprising no one, especially since they also have the lowest completion rate at 46%. (The other <50% teams are the [Darkling Spectres](../teams/darklingspectres) 49% and the [Ravenous Eagles](../teams/ravenouseagles) 47%). It is a little surprising that the [Irregular Cogs](../teams/irregularcogs) are the second shortest passers (IC 2.28 squares/completion), especially when the [Eldritch Fatality](../teams/eldritchfatality) who use almost the exact same playbook average 0.8 more squares/completion.

```
SELECT pl.f_tname AS team, sum(md.cp) AS cp, sum(mx.pass_attempts) AS attempts, sum(md.cp) / sum(mx.pass_attempts) AS comp_pct, sum(mx.pass_distance) AS distance, sum(mx.pass_distance) / sum(md.cp) AS pass_average FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY sum(mx.pass_attempts) DESC;
```
