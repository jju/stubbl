| name                 | sum(mr.won) | sum(mr.draw) | sum(mr.played) | draw_rate | sum(mr.gf) | td_rate | sum(mr.cas) | cas_rate | sum(mr.spp) | spp_rate |
|----------------------|-------------|--------------|----------------|-----------|------------|---------|-------------|----------|-------------|----------|
| Green Cup IX         |         112 |           46 |            270 |    0.1704 |        647 |  2.3963 |         405 |   1.5000 |        5020 |  18.5926 |
| Green Cup I          |          38 |           14 |             90 |    0.1556 |        212 |  2.3556 |         130 |   1.4444 |           0 |   0.0000 |
| Green Cup II         |          38 |           14 |             90 |    0.1556 |        211 |  2.3444 |         181 |   2.0111 |           0 |   0.0000 |
| Green Cup IV         |          52 |           20 |            124 |    0.1613 |        289 |  2.3306 |           0 |   0.0000 |           0 |   0.0000 |
| UBBL Challenge III   |          37 |            4 |             78 |    0.0513 |        176 |  2.2564 |         106 |   1.3590 |        1378 |  17.6667 |
| Green Cup III        |          54 |           16 |            124 |    0.1290 |        271 |  2.1855 |         227 |   0.8407 |           0 |   0.0000 |
| Green Cup VII        |         116 |           38 |            270 |    0.1407 |        585 |  2.1667 |         436 |   1.6148 |        4789 |  17.7370 |
| UBBL Challenge       |          57 |            8 |            122 |    0.0656 |        258 |  2.1148 |         173 |   1.4180 |        2106 |  17.2623 |
| Green Cup VIII       |         124 |           22 |            270 |    0.0815 |        562 |  2.0815 |         467 |   1.7296 |        4753 |  17.6037 |
| UBBL Challenge II    |          35 |            8 |             78 |    0.1026 |        160 |  2.0513 |         138 |   1.7692 |        1375 |  17.6282 |
| Green Cup VI         |          53 |           20 |            126 |    0.1587 |        246 |  1.9524 |         188 |   1.4921 |        2057 |  16.3254 |
| Green Cup Classic 06 |          23 |           24 |             70 |    0.3429 |        132 |  1.8857 |          92 |   1.3143 |        1064 |  15.2000 |
| StUBBL Scramble      |           7 |            4 |             18 |    0.2222 |         33 |  1.8333 |          26 |   1.4444 |         289 |  16.0556 |
| Green Cup V Memorial |          51 |           22 |            124 |    0.1774 |        183 |  1.4758 |         163 |   1.3145 |        1685 |  13.5887 |

```
SELECT tours.name,  sum(mr.won),  sum(mr.draw), sum(mr.played), sum(mr.draw) / sum(mr.played) as draw_rate, sum(mr.gf), sum(mr.gf) / sum(mr.played) AS td_rate,  sum(mr.ca
s),  sum(mr.cas) / sum(mr.played) AS cas_rate, sum(mr.spp), sum(mr.spp) / sum(mr.played) AS spp_rate FROM mv_teams AS mr  JOIN tours  ON mr.f_trid = tours.tour_id AND mr.f_did = tours.f_did  JOIN teams  ON teams.team_id = mr.f_tid  WHERE mr.f_lid = 1 GROUP BY tours.name ORDER BY cas_rate DESC;
```
