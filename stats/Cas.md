A Casualty (Cas) is recorded when a BludBol player blocks or is blocked by an opposing player and the opposing player ends up Badly Hurt (BH), Seriously Injured (SI) or Killed (Ki). Usually casualty numbers are recorded as a total followed by a (BH/SI/Ki) breakdown.

In traditional [[SPP]] valuation, a Cas counts for 2 SPP. This makes it the primary stat measuring defensive contributions. In the [[tVP]] valuation, scoring itself is only counted as one point (technically a [[dVP]]), but players are also credited with more of the components of defence, namely the number of blocks delivered and the number of drive-stopping blocks (sacks).

Green Cup tournaments reward the season leader in Cas with the [[carminefist]].

# UBBL Cas Leaders

Stats updated pre GCXII. Note that these include Open- and even Street-level matches.

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked. *Old-era players* have incomplete statistics.


| Player   | Team              | TDs  | Rush | Cp   | CpDist | Ctch | Int  | Cas  | Blck | Sck  | MVP  | SPP  |
|----------|-------------------|------|------|------|--------|------|------|------|------|------|------|------|
| [[Jantine]] | Ravenous Eagles   |    0 |   16 |    0 |      0 |    0 |    1 |   63 |  518 |    6 |    2 |  138 |
| [[Somfuhr]] | Filthy Tide       |    0 |    8 |    0 |      0 |    0 |    0 |   61 |  557 |   15 |    6 |  152 |
| [[Marzhak]] | Gargantuan Brutes |    0 |    0 |    0 |      0 |    0 |    1 |   55 |  550 |   20 |    6 |  142 |
| [[Rohit]]   | Zensun Vagabonds  |    7 |   69 |    1 |      5 |    5 |    1 |   52 |  417 |   17 |    6 |  158 |
| **[[Uli]]** | Orbital Machine   |    0 |    0 |    0 |      0 |    0 |    0 |   47 |  522 |    8 |    4 |  114 |
| **[[Percy]]** | Ravenous Eagles   |    1 |    8 |    0 |      0 |    0 |    1 |   46 |  529 |    8 |    4 |  117 |
| [[Ekua]]    | Ravenous Eagles   |    9 |   75 |    0 |      0 |    2 |    1 |   43 |  687 |   30 |    5 |  140 |
| **[[Katka]]** | Hoods             |    0 |    0 |    0 |      0 |    0 |    0 |   40 |  340 |   10 |    4 |  100 |
| [[Simon]]   | Darkling Spectres |    0 |    0 |    0 |      0 |    0 |    0 |   35 |  350 |    4 |    5 |   95 |
| **[[Pierre]]** | Carcosan Tatters  |    0 |    7 |    0 |      0 |    0 |    0 |   32 |  376 |    2 |    6 |   94 |


```
SELECT pl.name AS Player, pl.f_tname AS Team, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS CpDist, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blck, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id GROUP BY pl.name, pl.f_tname ORDER BY Cas DESC LIMIT 10;
```

## more detailed casualty tables

| Player | Team | Cas | BH | SI | Ki | Blk | Sck | SckBlkRate | CasBlkRate | Fouls | fBH | fSI | fKi | Ejections |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Jantine | Ravenous Eagles   |          63 |         48 |         14 |          1 |    518 |     6 |     0.0116 |    0.1216 |     0 |    0 |    0 |    0 |         0 |
| Somfuhr | Filthy Tide       |          61 |         42 |         13 |          6 |    557 |    15 |     0.0269 |    0.1095 |     0 |    0 |    0 |    0 |         0 |
| Marzhak | Gargantuan Brutes |          55 |         35 |         18 |          2 |    550 |    20 |     0.0364 |    0.1000 |     0 |    0 |    0 |    0 |         0 |
| Rohit   | Zensun Vagabonds  |          52 |         39 |         12 |          1 |    417 |    17 |     0.0408 |    0.1247 |     0 |    0 |    0 |    0 |         0 |
| **Uli** | Orbital Machine   |          47 |         32 |         14 |          1 |    522 |     8 |     0.0153 |    0.0900 |     0 |    0 |    0 |    0 |         0 |
| **Percy** | Ravenous Eagles   |          46 |         29 |         12 |          5 |    529 |     8 |     0.0151 |    0.0870 |     0 |    0 |    0 |    0 |         0 |
| Ekua    | Ravenous Eagles   |          43 |         27 |         13 |          3 |    687 |    30 |     0.0437 |    0.0626 |     1 |    1 |    0 |    0 |         0 |
| **Katka** | Hoods             |          40 |         30 |          8 |          2 |    340 |    10 |     0.0294 |    0.1176 |     0 |    0 |    0 |    0 |         0 |
| Simon   | Darkling Spectres |          35 |         22 |          8 |          5 |    350 |     4 |     0.0114 |    0.1000 |     0 |    0 |    0 |    0 |         0 |
| **Pierre** | Carcosan Tatters  |          32 |         20 |         10 |          2 |    376 |     2 |     0.0053 |    0.0851 |     1 |    0 |    0 |    0 |         0 |


```
SELECT  pl.name,  pl.f_tname, sum(mp.cas),  sum(mp.bh), sum(mp.si), sum(mp.ki), sum(me.inflicted_blocks) AS blocks,  sum(me.inflicted_sacks) AS sacks,  sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block,  sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block, sum(me.inflicted_fouls) AS fouls, sum(me.inflicted_foul_bhs) AS fBH, sum(me.inflicted_foul_sis) AS fSI, sum(me.inflicted_foul_kills) AS fKi, sum(me.sustained_ejections) AS ejections FROM mv_es_players AS me  JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.name, pl.f_tname ORDER BY sum(mp.cas) DESC limit 10;
```