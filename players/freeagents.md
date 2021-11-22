# Free Agents

There are loads of players in the free agent pool available for expansion.

## Strong

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', pl.ma, pl.st, pl.ag, pl.av, count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.st > 3 GROUP BY pl.name HAVING pl.name LIKE '%.' AND pl.nr < 80 ORDER BY Value DESC LIMIT 10;
```

## Agile

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', pl.ma, pl.st, pl.ag, pl.av, count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.ag > 3 GROUP BY pl.name HAVING pl.name LIKE '%.' AND pl.nr < 80 ORDER BY Value DESC LIMIT 10;
```

## Fast

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', pl.ma, pl.st, pl.ag, pl.av, count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.ma > 7 GROUP BY pl.name HAVING pl.name LIKE '%.' AND pl.nr < 80 ORDER BY Value DESC LIMIT 10;
```

## by team

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', pl.ma, pl.st, pl.ag, pl.av, count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE Team = "TEAM" GROUP BY pl.name HAVING pl.name LIKE '%.' AND pl.nr < 80 ORDER BY Value DESC LIMIT 10;
```