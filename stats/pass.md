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

```
SELECT pl.f_tname AS team, sum(md.cp) AS cp, sum(mx.pass_attempts) AS attempts, sum(md.cp) / sum(mx.pass_attempts) AS comp_pct, sum(mx.pass_distance) AS distance, sum(mx.pass_distance) / sum(md.cp) AS pass_average FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY sum(mx.pass_attempts) DESC;
```

You can see the different passing strategies in the good passing teams pretty clearly in this table. The [Old Wyrms](../teams/oldwyrms) attempted (OW 462 vs GH 362) and completed (OW 350 vs GH 282) more passes than the [Glorious Hounds](../teams/glorioushounds), but the Hounds get more distance out of each one (GH 4.32 vs OW 3.00).

While the Wyrms and Glorious Hounds are by far the most prolific passers it's a little bit interesting to note that the [Badger Claws](../teams/badgerclaws) come close for their completion percentages (GH 77% OW 76% BC 74%). Also somewhat interesting is that the [Vanadium Hunters](../teams/vanadiumhunters) were even more of a deep threat than the Hounds when they made their passes (VH 4.58 squares/completion vs GH 4.32), but because they only completed 55% of them we don't think of the Hunters as a passing team. Is it strange that the Vagabonds are the only other team with an average pass distance over 4?

The shortest passers in the Pros are the [Kaiju Dynamo](../teams/kaijudynamo) (KD 1.99 squares/completion), surprising no one, especially since they also have the lowest completion rate at 46%. (The other <50% teams are the [Darkling Spectres](../teams/darklingspectres) 49% and the [Ravenous Eagles](../teams/ravenouseagles) 47%). It is a little surprising that the [Irregular Cogs](../teams/irregularcogs) are the second shortest passers (IC 2.28 squares/completion), especially when the [Eldritch Fatality](../teams/eldritchfatality) who use almost the exact same playbook average 0.8 more squares/completion.

| team              | cp   | attempts | comp_pct | td   | td_pass | intcpt_thrown | intcpt_rate | sum(mx.handoffs) | hand_pass |
|-------------------|------|----------|----------|------|---------|---------------|-------------|------------------|-----------|
| Kaiju Dynamo      |   79 |      172 |   0.4593 |  157 |  1.9873 |             7 |      0.0407 |              144 |    1.8228 |
| Ravenous Eagles   |   52 |      111 |   0.4685 |   79 |  1.5192 |             2 |      0.0180 |               88 |    1.6923 |
| Orbital Machine   |   69 |      136 |   0.5074 |   93 |  1.3478 |             7 |      0.0515 |               65 |    0.9420 |
| Carcosan Tatters  |   65 |      128 |   0.5078 |   81 |  1.2462 |             3 |      0.0234 |               70 |    1.0769 |
| Badger Claws      |  128 |      173 |   0.7399 |  136 |  1.0625 |             5 |      0.0289 |               39 |    0.3047 |
| Darkling Spectres |  112 |      228 |   0.4912 |  113 |  1.0089 |            27 |      0.1184 |               60 |    0.5357 |
| Zensun Vagabonds  |  163 |      248 |   0.6573 |  145 |  0.8896 |            17 |      0.0685 |               55 |    0.3374 |
| Filthy Tide       |  215 |      321 |   0.6698 |  185 |  0.8605 |            12 |      0.0374 |               72 |    0.3349 |
| Cackling Furies   |  121 |      216 |   0.5602 |  100 |  0.8264 |            19 |      0.0880 |               51 |    0.4215 |
| Gore Farmers      |  125 |      201 |   0.6219 |  101 |  0.8080 |            12 |      0.0597 |               91 |    0.7280 |
| TC Sump Runners   |  145 |      246 |   0.5894 |  117 |  0.8069 |            15 |      0.0610 |               55 |    0.3793 |
| Vanadium Hunters  |   93 |      169 |   0.5503 |   72 |  0.7742 |             8 |      0.0473 |               39 |    0.4194 |
| Eldritch Fatality |  214 |      351 |   0.6097 |  162 |  0.7570 |            21 |      0.0598 |               61 |    0.2850 |
| Irregular Cogs    |  226 |      348 |   0.6494 |  168 |  0.7434 |            31 |      0.0891 |               72 |    0.3186 |
| Glorious Hounds   |  282 |      362 |   0.7790 |  198 |  0.7021 |             9 |      0.0249 |               52 |    0.1844 |
| Gargantuan Brutes |   86 |      159 |   0.5409 |   56 |  0.6512 |             8 |      0.0503 |               44 |    0.5116 |
| Old Wyrms         |  350 |      462 |   0.7576 |  191 |  0.5457 |            25 |      0.0541 |               44 |    0.1257 |

```
SELECT pl.f_tname AS team, sum(md.cp) AS cp, sum(mx.pass_attempts) AS attempts, sum(md.cp) / sum(mx.pass_attempts) AS comp_pct, sum(md.td) AS td, sum(md.td) / sum(md.cp) AS td_pass, sum(mx.interceptions_thrown) - sum(mx.safe_throws) AS intcpt_thrown, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS intcpt_rate, sum(mx.handoffs), sum(mx.handoffs) / sum(md.cp) AS hand_pass FROM match_data_es AS mx 	JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY td_pass DESC;
```

Now this table shows us the Dynamo's real strength of play: the handoff. They hand off the ball almost twice as much as they pass (KD 1.82 Handoff/Pass) and score even more than they pass (KD 1.99 TD/Pass). This makes a lot of sense because remember that they also have a sub 50% completion rate. It's somewhat interesting to note the similarities with the Ravenous Eagles, who've parlayed similar, though less extreme, rates (RE 1.69 Handoff/Pass and RE 1.52 TD/Pass) into tournament wins. These teams do this and keep their interception rate way down (KD 4% RE 2%). They're making less-risky passes, and getting picked off at about the same rate as the really good passing teams (OW 5% GH 2%). 

It should be apparent, looking at this that the Darkling Spectres need to stop throwing the ball. They are picked off a lot and at the highest rate (DS 12%) while completing only half their attempts. The Cogs have a similar interceptions thrown rate, but their ccuracy is up at 65%.
