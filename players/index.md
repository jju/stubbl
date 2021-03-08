In the individual player stat pages we keep the basic box scores under Basic Stats (both as a Pro-Level total and by Season). Prize Stats are the kinds of stats used to determine individual awards in a season. Prize winning totals are **highlighted** in the tables. We may also include further stats of interest on a player by player basis.

* [[aeson]]
* [[Baraz]]
* [[besz]]
* [[daividh]]
* [[evander]]
* [[hulud]]
* [[souta]]
* [[yakup]]

# Basic Stats

## Pro Totals

| Player           | Team        | Position      | W  | D | L | GP   | TD   | Cp | Int | BH   | SI   | Ki   | MVP  | SPP  |
|------------------|-------------|---------------|----|---|---|------|------|----|-----|------|------|------|------|------|

`
SELECT  pl.name AS Player,  pl.f_tname AS Team, pl.f_pos_name AS Position,  sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Comp, sum(mp.intcpt) AS Ints, sum(mp.bh) AS BH, sum(mp.si) AS SI, sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE mp.f_did = 1 AND pl.name = "NAME" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
`

## By Season

| Player | Team         | Season          | W  | D | L | TD   | Cp   | Int | BH   | SI   | Ki   | MVP  | SPP  |
|--------|--------------|-----------------|----|---|---|------|------|-----|------|------|------|------|------|


`
SELECT pl.name AS Player,  pl.f_tname AS Team, tours.name AS Season, mp.won, mp.draw, mp.lost, mp.td, mp.cp, mp.intcpt, mp.bh, mp.si, mp.ki, mp.mvp, mp.spp FROM mv_players AS mp  JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id  JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did  WHERE pl.name = "NAME" ORDER BY tours.tour_id ASC;
`

# Prize Stats

* Prize - Season [[prizes/index]]

| Player | Team         | Season          | GP | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|--------------|-----------------|----|-----|-----|------|-------|------|-----|------|-----|-----|-----|------|


`
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush,sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Caught,sum(md.intcpt) AS Picks, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "NAME" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;
`

### match by match

| Player | Team        | Round          | TD  | Rsh | Cp   | CpDst | Ctch | Int | Cas  | Blk | Sck | MVP | SPP  |
|--------|-------------|-------|------|------|------|----------|---------|------|--------|-------|------|------|

