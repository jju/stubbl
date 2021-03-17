# team stats

## team passing ranks pro-level pre-GCXI

| Team              | Cp   | Attempts | Cp_Pct | CpDist | AvgDist |
|-------------------|------|----------|----------|----------|--------------|
| Old Wyrms         |  449 |      593 | 0.7572 |   1329 |  2.9599 |
| Glorious Hounds   |  349 |      452 | 0.7721 |   1455 |  4.1691 |
| Irregular Cogs    |  288 |      434 | 0.6636 |    659 |  2.2882 |
| Eldritch Fatality |  263 |      419 | 0.6277 |    837 |  3.1825 |
| Filthy Tide       |  271 |      407 | 0.6658 |    689 |  2.5424 |
| TC Sump Runners   |  205 |      338 | 0.6065 |    613 |  2.9902 |
| Zensun Vagabonds  |  220 |      327 | 0.6728 |    890 |  4.0455 |
| Cackling Furies   |  185 |      308 | 0.6006 |    598 |  3.2324 |
| Darkling Spectres |  146 |      292 | 0.5000 |    436 |  2.9863 |
| Gore Farmers      |  177 |      289 | 0.6125 |    562 |  3.1751 |
| Badger Claws      |  188 |      264 | 0.7121 |    460 |  2.4468 |
| Kaiju Dynamo      |   98 |      207 | 0.4734 |    177 |  1.8061 |
| Vanadium Hunters  |   93 |      169 | 0.5503 |    426 |  4.5806 |
| Orbital Machine   |   85 |      169 | 0.5030 |    268 |  3.1529 |
| Gargantuan Brutes |   86 |      159 | 0.5409 |    315 |  3.6628 |
| Carcosan Tatters  |   85 |      158 | 0.5380 |    246 |  2.8941 |
| Ravenous Eagles   |   79 |      153 | 0.5163 |    217 |  2.7468 |
| Arboreal Menace   |   56 |       76 | 0.7368 |    193 |  3.4464 |
| Gladiolas         |    4 |        5 | 0.8000 |      9 |  2.2500 |
| Thorns            |    3 |        4 | 0.7500 |     11 |  3.6667 |
| Mules             |    0 |        0 |   NULL |      0 |    NULL |


## team passing ranks pro-level pre-GCX

| Team              | Cp   | Attempts | Cp_Pct | CpDist | AvgDist |
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
SELECT pl.f_tname AS Team, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(mx.pass_distance) AS CpDist, sum(mx.pass_distance) / sum(md.cp) AS AvgDist FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY sum(mx.pass_attempts) DESC;
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
SELECT pl.f_tname AS Team, sum(md.cp) AS Cp, sum(mx.pass_attempts) AS Attempts, sum(md.cp) / sum(mx.pass_attempts) AS Cp_Pct, sum(md.td) AS TD, sum(md.td) / sum(md.cp) AS TD_Cp, sum(mx.interceptions_thrown) - sum(mx.safe_throws) AS Int_Thrown, (sum(mx.interceptions_thrown) - sum(mx.safe_throws)) / sum(mx.pass_attempts) AS Int_Rate, sum(mx.handoffs) AS Handoff, sum(mx.handoffs) / sum(md.cp) AS Hand_Cp FROM match_data_es AS mx 	JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY td_pass DESC;
```

Now this table shows us the Dynamo's real strength of play: the handoff. They hand off the ball almost twice as much as they pass (KD 1.82 Handoff/Pass) and score even more than they pass (KD 1.99 TD/Pass). This makes a lot of sense because remember that they also have a sub 50% completion rate. It's somewhat interesting to note the similarities with the Ravenous Eagles, who've parlayed similar, though less extreme, rates (RE 1.69 Handoff/Pass and RE 1.52 TD/Pass) into tournament wins. These teams do this and keep their interception rate way down (KD 4% RE 2%). They're making less-risky passes, and getting picked off at about the same rate as the really good passing teams (OW 5% GH 2%). 

It should be apparent, looking at this that the Darkling Spectres need to stop throwing the ball. They are picked off a lot and at the highest rate (DS 12%) while completing only half their attempts. The Cogs have a similar interceptions thrown rate, but their ccuracy is up at 65%.

| team              | cp   | attempts | comp_pct | td   | td_pass | intcpt_thrown | intcpt_rate | sum(mx.handoffs) | hand_pass |
|-------------------|------|----------|----------|------|---------|---------------|-------------|------------------|-----------|
| OE Gore Farmers | 44 | 84 | 0.5238 | 76 | 1.7955 | 6 | 0.0714 | 98 | 2.2273 |
| OE Carcosan Tatters | 49 | 83 | 0.5904 | 85 | 1.7551 | 6 | 0.0723 | 42 | 0.8571 |
| OE Kaiju Dynamo | 74 | 140 | 0.5286 | 118 | 1.6486 | 6 | 0.0429 | 140 | 1.8919 |
| OE Darkling Spectres | 49 | 95 | 0.5158 | 73 | 1.5510 | 6 | 0.0632 | 46 | 0.9388 |
| OE Cackling Furies | 70 | 117 | 0.5983 | 103 | 1.5143 | 9 | 0.0769 | 82 | 1.1714 |
| OE Filthy Tide | 154 | 217 | 0.7097 | 143 | 0.9610 | 21 | 0.0968 | 92 | 0.5974 |
| OE Zensun Vagabonds | 115 | 178 | 0.6461 | 89 | 0.7739 | 11 | 0.0618 | 74 | 0.6435 |
| OE Old Wyrms | 245 | 324 | 0.7562 | 172 | 0.7265 | 34 | 0.1049 | 81 | 0.3306 |
| OE Gargantuan Brutes | 62 | 106 | 0.5849 | 45 | 0.7258 | 9 | 0.0849 | 57 | 0.9194 |
| OE Glorious Hounds | 149 | 187 | 0.7968 | 105 | 0.7047 | 13 | 0.0695 | 64 | 0.4295 |
| OE Irregular Cogs | 230 | 331 | 0.6949 | 153 | 0.7000 | 19 | 0.0574 | 82 | 0.3565 |
| OE Vanadium Hunters | 165 | 242 | 0.6818 | 121 | 0.5515 | 17 | 0.0702 | 79 | 0.4788 |
| OE Poets | 60 | 98 | 0.6122 | 32 | 0.5333 | 2 | 0.0204 | 36 | 0.6000 |

We have some rough stats from the Old-Era to try and make some era comparisons. The big one that stands out is how the Gore Farmers remade their offence between eras. Their OE Handoff/Pass rate was 2.23 and their Modern rate is 0.72. They're getting intercepted a little less (ME 6% OE 7%) but are making completions at a much higher rate (from an among the worst 52% up to a middling 62%), but they're also completing longer passes (ME 3.36 vs OE 2.81).
