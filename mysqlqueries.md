mysql

mysql -u cmsh -p sbbdb -e 'SQLCOMMANDS;' > /var/www/html/stubbl/outfile.txt


~~ INTO OUTFILE '/var/www/html/stubbl/bbstats.csv' FIELDS ENCLOSED BY '"' TERMINATED BY ';' ESCAPED BY '"' LINES TERMINATED BY '\r\n'; ~~

# player statlines

## by season

### basic stats

p_name | t_name | won | draw | lost | TDs | Cp | Int | BH | SI | Ki | MVP | SPP

SELECT 
	pl.name AS Player, 
	pl.f_tname AS Team, 
	tours.name AS Season, 
	mp.won,
	mp.draw,
	mp.lost,
	mp.td,
	mp.cp,
	mp.intcpt,
	mp.bh,
	mp.si,
	mp.ki,
	mp.mvp,
	mp.spp 
FROM mv_players AS mp 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did 
WHERE mp.f_did = 1 
ORDER BY mp.spp DESC 
limit 10;

### offense stats

p_name | t_name | TDs | Rushing | Touches | Cp | Distance | InterceptedRate | Sacked | Catches | CatchRate

SELECT 
	pl.name AS Player, 
	pl.f_tname AS Team, 
	tours.name AS Season, 
	mp.td, 
	me.rushing_distance_leap + me.rushing_distance_push + me.rushing_distance_move + me.rushing_distance_block + me.rushing_distance_shadowing AS total_rushing, 
	me.pass_distance, me.catches + me.pickups + mp.intcpt + me.handoff_catches AS total_touches,
	mp.cp,
	me.pass_distance,
	(me.interceptions_thrown - me.safe_throws) / me.pass_attempts AS intcpt_rate,
	me.sustained_sacks AS sacked,
	me.catches,
	me.catches / me.catch_attempts AS catch_rate
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_lid = 1 
ORDER BY mp.spp DESC 
limit 10;

### blocking stats

p_name | t_name | Cas | BH | SI | Ki | Blocks | Sacks | SckBlockRate | CasBlockRate | Fouls | fBH | fSI | fKi | ejections

SELECT 
	pl.name AS Player, 
	pl.f_tname AS Team, 
	tours.name AS Season, 
	mp.cas, 
	mp.bh,
	mp.si,
	mp.ki,
	me.inflicted_blocks AS blocks, 
	me.inflicted_sacks AS sacks, 
	me.inflicted_sacks / me.inflicted_blocks AS sack_block, 
	mp.cas / me.inflicted_blocks AS cas_block,
	me.inflicted_fouls AS fouls,
	me.inflicted_foul_bhs AS fBH,
	me.inflicted_foul_sis AS fSI,
	me.inflicted_foul_kills AS fKi,
	me.sustained_ejections AS ejections
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_lid = 1 
ORDER BY mp.cas DESC 
limit 10;

### misc stats

p_name | t_name | dice_rolls | dice_roll_sum - dice_target_sum | apothecary_used

SELECT 
	pl.name, 
	pl.f_tname AS team, 
	tours.name AS season, 
	me.sustained_blocks,
	me.sustained_sacks,
	me.sustained_bhs,
	me.sustained_sis,
	me.sustained_fouls AS fouled,
	me.apothecary_used,
	me.dice_rolls,
	me.dice_roll_sum - me.dice_target_sum AS excess,
	(me.dice_roll_sum - me.dice_target_sum) / me.dice_rolls AS skill 
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_lid = 1 
ORDER BY me.dice_rolls DESC 
limit 10;

## total (USE ON TEAM PAGE)

p_name | t_name | won | draw | lost | played | TDs | Cp | Int | BH | SI | Ki | MVP | SPP

SELECT 
	pl.name AS Player, 
	pl.f_tname AS Team,
	pl.f_pos_name AS Position, 
	sum(mp.won) AS won,
	sum(mp.draw) AS draw,
	sum(mp.lost) AS lost,
	sum(mp.played) AS GP,
	sum(mp.td) AS TD,
	sum(mp.cp) AS Comp,
	sum(mp.intcpt) AS Ints,
	sum(mp.bh) AS BH,
	sum(mp.si) AS SI,
	sum(mp.ki) AS Ki,
	sum(mp.mvp) AS MVP,
	sum(mp.spp) AS SPP
FROM mv_players AS mp 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did 
WHERE mp.f_did = 1 AND pl.f_tname = "Badger Claws"
GROUP BY pl.name, pl.f_tname, pl.f_pos_name
ORDER BY SPP DESC 
limit 11;

p_name | t_name | TDs | Rushing | Touches | Cp | Distance | Intercepted Rate | Sacked | CatchRate

SELECT 
	pl.name, 
	pl.f_tname, 
	sum(mp.td), 
	sum(me.rushing_distance_leap + me.rushing_distance_push + me.rushing_distance_move + me.rushing_distance_block + me.rushing_distance_shadowing) AS total_rushing, 
	sum(me.pass_distance), 
	sum(me.catches) + sum(me.pickups) + sum(mp.intcpt) + sum(me.handoff_catches) AS total_touches,
	sum(mp.cp),
	sum(me.pass_distance) AS passing_dist,
	(sum(me.interceptions_thrown) - sum(me.safe_throws)) / sum(me.pass_attempts) AS intcpt_rate,
	sum(me.sustained_sacks) AS sacked,
	sum(me.catches) / sum(me.catch_attempts) AS catch_rate
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_lid = 1 
GROUP BY pl.name, pl.f_tname
ORDER BY mp.spp DESC 
limit 10;

p_name | t_name | Season | Cas | BH | SI | Ki | Blocks | Sacks | SckBlockRate | CasBlockRate | Fouls | fBH | fSI | fKi | ejections

SELECT 
	pl.name, 
	pl.f_tname,
	tours.name, 
	sum(mp.cas), 
	sum(mp.bh),
	sum(mp.si),
	sum(mp.ki),
	sum(me.inflicted_blocks) AS blocks, 
	sum(me.inflicted_sacks) AS sacks, 
	sum(me.inflicted_sacks) / sum(me.inflicted_blocks) AS sack_block, 
	sum(mp.cas) / sum(me.inflicted_blocks) AS cas_block,
	sum(me.inflicted_fouls) AS fouls,
	sum(me.inflicted_foul_bhs) AS fBH,
	sum(me.inflicted_foul_sis) AS fSI,
	sum(me.inflicted_foul_kills) AS fKi,
	sum(me.sustained_ejections) AS ejections
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_lid = 1 
GROUP BY pl.name, pl.f_tname
ORDER BY sum(mp.cas) DESC 
limit 10;

p_name | t_name | dice_rolls | dice_roll_sum - dice_target_sum | apothecary_used

SELECT 
	pl.name, 
	pl.f_tname, 
	sum(me.sustained_blocks) AS hit,
	sum(me.sustained_sacks) AS sacked,
	sum(me.sustained_bhs) AS BHed,
	sum(me.sustained_sis) AS SIed,
	sum(me.sustained_fouls) AS fouled,
	sum(me.apothecary_used) + sum(me.regenerations) AS doctored,
	sum(me.dice_rolls) AS rolls,
	sum(me.dice_roll_sum) - sum(me.dice_target_sum) AS excess,
	(sum(me.dice_roll_sum) - sum(me.dice_target_sum)) / sum(me.dice_rolls) AS skill 
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours 
		ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_lid = 1 
GROUP BY pl.name, pl.f_tname
ORDER BY rolls DESC 
limit 10;

# queries

## team records by season (USE ON TEAM PAGE)

SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Raptors" ORDER BY mr.win_pct DESC limit 15;

to correct for lack of mr.cas in GCI-IV

SELECT  teams.name,  tours.name,  mr.cas, mr.tcasf, mr.tcdiff FROM mv_teams AS mr  JOIN tours  ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams  ON teams.team_id = mr.f_tid  WHERE mr.f_tid = 36 ORDER BY mr.win_pct DESC limit 15;

## team records by division

SELECT 
	teams.name, 
	divisions.name, 
	sum(mr.won), 
	sum(mr.draw), 
	sum(mr.lost), 
	sum(mr.played), 
	avg(mr.win_pct),
	sum(mr.gf),
	sum(mr.ga),
	sum(mr.tcasf),
	sum(mr.tcdiff),
	sum(mr.ff)
FROM mv_teams AS mr 
	JOIN divisions 
		ON mr.f_did = divisions.did
	JOIN teams 
		ON teams.team_id = mr.f_tid 
WHERE teams.name = "Raptors"
GROUP BY teams.name, mr.f_did
ORDER BY sum(mr.won) DESC
limit 10;

## team prizes

SELECT tours.name AS Season, title AS Prize, txt from prizes join tours on tours.tour_id = prizes.tour_id where team_id = 36;

## top 10 SPP gains/team by season

SELECT teams.name, tours.name, mr.won, mr.draw, mr.lost, mr.played, mr.gf, mr.gf / mr.played AS gf_rate, mr.ga, mr.ga / mr.played AS ga_rate, mr.cas, mr.cas / mr.played AS cas_rate, mr.spp, mr.spp / mr.played AS spp_rate FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id AND mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE mr.f_lid = 1 ORDER BY mr.spp DESC LIMIT 10;

## average players by team by season

> not sure if this one works

SELECT pl.f_tname, tours.name, avg(mp.played) AS GP, avg(mp.td) AS TD, avg(mp.cp) AS Completions, avg(mp.intcpt) AS Interceptions, avg(mp.bh) AS BH,	avg(mp.si) AS SI, avg(mp.ki) AS Ki,	avg(mp.mvp) AS MVP,	avg(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE mp.f_lid = 1 GROUP BY pl.f_tname, tours.name ORDER BY SPP DESC limit 10;

## player stats for prizes

SELECT
	pl.name AS Player,
	pl.f_tname AS Team,
	tours.name AS Season,
	sum(md.td) AS TDs,
	sum(mx.rushing_distance_move) AS Rush,
	sum(md.cp) AS Cp,
	sum(mx.pass_distance) AS PassDist,
	sum(mx.catches) AS Caught,
	sum(md.intcpt) AS Picks,
	sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas,
	sum(mx.inflicted_blocks) AS Blocks,
	sum(mx.inflicted_sacks) AS Sacks,
	sum(md.mvp) AS MVPs,
	(sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP
FROM match_data AS md
	JOIN match_data_es AS mx
		ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid
	JOIN players AS pl
		ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id
	JOIN matches AS mt
		ON mt.match_id = md.f_match_id
	JOIN tours 
		ON mt.f_tour_id = tours.tour_id
WHERE md.f_tour_id = 3 AND mt.round = 8
GROUP BY pl.name, pl.f_tname
ORDER BY SPP DESC;

SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "NAME" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;

### Weekly Player of the Week stats leader USE THIS!

SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Picks, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Orange Goblet II" AND mt.round = 1 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC Limit 10;

### match report USE THIS!

SELECT pl.name AS Player, pl.f_tname AS Team, mx.catches + mx.pickups + md.intcpt + mx.handoff_catches AS Touches, md.td AS TDs, mx.rushing_distance_move AS Rush, md.cp AS Cp,	mx.pass_distance AS PassDist, mx.catches AS Caught, md.intcpt AS Picks, md.bh + md.si + md.ki AS Cas, mx.inflicted_blocks AS Blocks, mx.inflicted_sacks AS Sacks, md.mvp AS MVPs, mx.interceptions_thrown AS Intercepted, mx.sustained_sacks AS Sacked, mx.sustained_kos AS KOed, mx.sustained_bhs AS Hurt, mx.sustained_sis AS Injured, mx.sustained_kill AS Killed, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE mt.match_id = "1477" ORDER BY pl.f_tname, pl.nr;

### export player stats by season

#### all players in a season to csv

mysql -u cmsh -p sbbdb -e 'SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush,sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught,sum(md.intcpt) AS Picks, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.f_did = 3 GROUP BY pl.name, pl.f_tname, tours.name ORDER BY SPP DESC;' > /var/www/html/stubbl/open-players.csv

#### specific player seasons

SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, count(md.f_match_id) AS Games, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush,sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught,sum(md.intcpt) AS Picks, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE pl.name = "Aeson" GROUP BY pl.name, pl.f_tname, tours.name ORDER BY mt.match_id ASC;

#### specific players match by match

mysql -u cmsh -p sbbdb -e 'SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, mt.round AS Round, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE (pl.name = "Ziba" OR pl.name = "Venus" OR pl.name = "Laurel" OR pl.name = "Aeson" OR pl.name = "Sabah." OR pl.name = "Yakup." OR pl.name = "Donat.") GROUP BY pl.name, pl.f_tname, tours.name, mt.round ORDER BY mt.match_id ASC;'' > /var/www/html/stubbl/speedy-matches.csv

## comparing seasons

SELECT tours.name,  sum(mr.won),  sum(mr.draw), sum(mr.played), sum(mr.draw) / sum(mr.played) as draw_rate, sum(mr.gf), sum(mr.gf) / sum(mr.played) AS td_rate,  sum(mr.cas),  sum(mr.cas) / sum(mr.played) AS cas_rate, sum(mr.spp), sum(mr.spp) / sum(mr.played) AS spp_rate FROM mv_teams AS mr  JOIN tours  ON mr.f_trid = tours.tour_id AND mr.f_did = tours.f_did  JOIN teams  ON teams.team_id = mr.f_tid  WHERE mr.f_lid = 1 GROUP BY tours.name ORDER BY cas_rate DESC;

## basic team records by season

SELECT teams.name,  sum(mr.won),  sum(mr.draw), sum(mr.lost), sum(mr.played), sum(mr.draw) / sum(mr.played) as draw_rate, sum(mr.gf), sum(mr.gf) / sum(mr.played) AS td_rate,  sum(mr.cas),  sum(mr.cas) / sum(mr.played) AS cas_rate, sum(mr.spp), sum(mr.spp) / sum(mr.played) AS spp_rate FROM mv_teams AS mr  JOIN tours  ON mr.f_trid = tours.tour_id AND mr.f_did = tours.f_did  JOIN teams  ON teams.team_id = mr.f_tid  WHERE tours.tour_id = 3 GROUP BY teams.name ORDER BY cas_rate DESC;

## home match records by round

mysql -u cmsh -p sbbdb -e 'SELECT tours.name, mt.round, teams.name, mt.team1_score, mt.tcas1, mt.ffactor1, mt.income1, mt.team2_id, mt.team2_score, mt.tcas2, mt.ffactor2, mt.income2 FROM matches AS mt  JOIN tours ON mt.f_tour_id = tours.tour_id JOIN teams ON teams.team_id = mt.team1_id WHERE tours.name = "Orange Goblet II" ORDER BY round ASC;' > /var/www/html/stubbl/matches-home-ogii.csv

mysql -u cmsh -p sbbdb -e 'SELECT tours.name, mt.round, teams.name, mt.team2_score, mt.tcas2, mt.ffactor2, mt.income2, mt.team1_id, mt.team1_score, mt.tcas1, mt.ffactor1, mt.income1 FROM matches AS mt  JOIN tours ON mt.f_tour_id = tours.tour_id JOIN teams ON teams.team_id = mt.team2_id WHERE tours.name = "Orange Goblet II" ORDER BY tours.tour_id, round ASC;' > /var/www/html/stubbl/matches-away-ogii.csv


## Top matches for interceptions (single player)

> needs cleaning up

SELECT pl.name, pl.f_tname,	mt.f_tour_id, mt.round, md.f_player_id, md.f_match_id, md.intcpt, mt.team1_id, mt.team1_score, mt.team2_id,	mt.team2_score FROM match_data AS md JOIN players AS pl ON md.f_player_id = pl.player_id JOIN matches AS mt ON md.f_match_id = mt.match_id ORDER BY md.intcpt DESC limit 5;

## Top 5 matches for TDs (single player)

SELECT 
	pl.name, 
	pl.f_tname,
	mt.f_tour_id,
	mt.round, 
	md.f_player_id, 
	md.f_match_id, 
	md.td,
	mt.team1_id,
	mt.team1_score,
	mt.team2_id,
	mt.team2_score
FROM match_data AS md 
	JOIN players AS pl 
		ON md.f_player_id = pl.player_id 
	JOIN matches AS mt
		ON md.f_match_id = mt.match_id
ORDER BY md.td DESC 
limit 5;

## Top 5 Matches Passing Stats (single player)

SELECT 
	pl.name, 
	pl.f_tname, 
	mt.f_tour_id,
	mt.round, 
	mx.f_pid, 
	mx.f_mid, 
	md.cp, 
	mx.pass_attempts,
	md.cp / mx.pass_attempts AS comp_pct,
	mx.pass_distance,
	mx.pass_distance / md.cp AS average,
	mt.team1_id,
	mt.team1_score,
	mt.team2_id,
	mt.team2_score 
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
	JOIN matches AS mt
		ON mx.f_mid = mt.match_id
ORDER BY mx.pass_distance DESC 
limit 5;

## Biggest single match SPP gain (or any other general stat) individual player

SELECT 
	pl.name, 
	pl.f_tname, 
	tours.name,
	mt.f_tour_id,
	mt.round, 
	md.f_match_id, 
	md.td, 
	md.cp, 
	md.intcpt, 
	md.bh, 
	md.si, 
	md.ki, 
	md.mvp, 
	(md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP 
FROM match_data AS md 
	JOIN players AS pl 
		ON md.f_player_id = pl.player_id
	JOIN matches AS mt
		ON md.f_match_id = mt.match_id 
	JOIN tours ON tours.tour_id = mt.f_tour_id
WHERE md.f_did = 1
ORDER BY SPP DESC 
limit 5;

## Player total handoffs, completions and interceptions

SELECT 
	pl.name, 
	pl.f_tname, 
	sum(md.cp), 
	sum(mx.pass_attempts), 
	sum(mx.interceptions_thrown) - sum(safe_throws) AS intcpt_thrown, 
	(sum(mx.interceptions_thrown) - sum(safe_throws)) / sum(mx.pass_attempts) AS intcpt_rate, 
	sum(mx.handoffs), sum(mx.handoffs) / sum(md.cp) AS hand_pass 
FROM match_data AS md 
	JOIN players AS pl 
		ON md.f_player_id = pl.player_id 
	JOIN match_data_es AS mx 
		ON md.f_player_id = mx.f_pid AND mx.f_mid = md.f_match_id 
GROUP BY pl.name, pl.f_tname 
ORDER BY hand_pass DESC 
limit 10;

## Week by Week of a single player

SELECT pl.name AS Player, pl.f_tname AS Team, mt.round, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 3 AND pl.name = 'NAME' GROUP BY pl.name, pl.f_tname, mt.round ORDER BY mt.round ASC;

## Week by Week by team in a tournament

SELECT pl.f_tname AS Team, mt.round, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp, sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Intercepts, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id WHERE md.f_tour_id = 3 GROUP BY pl.f_tname, mt.round ORDER BY mt.round ASC;

## player spp by season

### simple (limited by division) open division

SELECT pl.name, pl.f_tname, tours.name, mp.spp FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_did = 3 ORDER BY mp.spp DESC limit 10;

### complex

#### SPP correlating with wins, passing distance, rushing distance, touches

SELECT pl.name, pl.f_tname, tours.name, mp.won, mp.td, mp.cas, mp.spp, me.rushing_distance_leap + me.rushing_distance_push + me.rushing_distance_move + me.rushing_distance_block + me.rushing_distance_shadowing AS total_rushing, me.pass_distance, me.catches + me.pickups + mp.intcpt + me.handoff_catches AS total_touches FROM mv_es_players AS me JOIN mv_players AS mp ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did WHERE mp.f_did = 1 ORDER BY mp.spp DESC limit 10;

## Player average Passing

SELECT pl.name, pl.f_tname, mx.f_pid, sum(mx.pass_distance), sum(md.cp), sum(mx.pass_attempts), sum(mx.pass_distance) / sum(md.cp) AS pass_average, sum(md.cp) / sum(mx.pass_attempts) AS comp_pct FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id GROUP BY pl.name, pl.f_tname, mx.f_pid ORDER BY sum(mx.pass_attempts) DESC limit 10;

## Team average passing

SELECT 
	pl.f_tname AS team, 
	sum(md.cp) AS cp, 
	sum(mx.pass_attempts) AS attempts, 
	sum(md.cp) / sum(mx.pass_attempts) AS comp_pct,
	sum(mx.pass_distance) AS distance, 
	sum(mx.pass_distance) / sum(md.cp) AS pass_average 
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1
GROUP BY pl.f_tname 
ORDER BY sum(mx.pass_attempts) DESC;

## team average rushing

SELECT 
	pl.f_tname AS team, 
	sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing) AS total_rushing, 
	sum(md.td) AS td, 
	(sum(rushing_distance_leap) + sum(rushing_distance_push) + sum(rushing_distance_move) + sum(rushing_distance_block) + sum(rushing_distance_shadowing)) / sum(md.td) AS rush_td
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1
GROUP BY pl.f_tname 
ORDER BY rush_td ASC;

## team average blocking

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

## Player SPP wins and Cas correlated with blocking by season

SELECT 
	pl.name, 
	pl.f_tname, 
	tours.name, 
	mp.won, 
	mp.cas, 
	mp.spp, 
	me.inflicted_blocks, 
	me.blitz_actions, 
	me.inflicted_sacks, 
	me.inflicted_sacks / me.inflicted_blocks AS sack_block, 
	mp.cas / me.inflicted_blocks AS cas_block, 
	me.rushing_distance_leap + me.rushing_distance_push + me.rushing_distance_move + me.rushing_distance_block + me.rushing_distance_shadowing AS total_rushing 
FROM mv_es_players AS me 
	JOIN mv_players AS mp 
		ON me.f_pid = mp.f_pid AND me.f_trid = mp.f_trid 
	JOIN players AS pl 
		ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id 
	JOIN tours ON mp.f_trid = tours.tour_id and mp.f_did = tours.f_did 
WHERE mp.f_did = 1 
ORDER BY mp.cas DESC 
limit 10;

## team total touches and TDs

SELECT pl.f_tname AS team, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td) AS td,	(sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) / sum(md.td) AS touches_td FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id WHERE md.f_did = 1 GROUP BY pl.f_tname ORDER BY touches_td ASC;

## top 10 tds/touch player

SELECT 
	pl.name AS player, 
	pl.f_tname AS team, 
	count(DISTINCT md.f_match_id) AS gp, 
	sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, 
	sum(md.td), 
	sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) AS tds_touch 
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
WHERE mx.f_did = 1
GROUP BY pl.name, pl.f_tname 
ORDER BY sum(md.td) DESC, gp DESC 
LIMIT 10;

### top 10 tds/touch among active players

```
SELECT pl.name, pl.f_tname, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, sum(md.td), sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) AS tds_touch FROM match_data_es AS mx JOIN match_data AS md ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id JOIN players AS pl ON mx.f_pid = pl.player_id GROUP BY pl.name, pl.f_tname HAVING pl.name NOT LIKE '%.' ORDER BY sum(md.td) DESC LIMIT 10;
```

### top 10 tds/touch among unpeaked players

SELECT 
	pl.name, 
	pl.f_tname, 
	sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, 
	sum(md.td), 
	sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) AS tds_touch 
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
GROUP BY pl.name, pl.f_tname 
HAVING (pl.name NOT LIKE '%#_' ESCAPE '#' AND pl.name NOT LIKE '%.') 
ORDER BY sum(md.td) DESC 
LIMIT 10;

## most touches without a td

SELECT 
	pl.name AS player, 
	pl.f_tname AS team,
	count(DISTINCT md.f_tour_id) AS ssn_count, 
	sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS total_touches, 
	sum(md.td), 
	sum(md.td) / (sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches)) AS tds_touch 
FROM match_data_es AS mx 
	JOIN match_data AS md 
		ON mx.f_pid = md.f_player_id AND mx.f_mid = md.f_match_id 
	JOIN players AS pl 
		ON mx.f_pid = pl.player_id 
WHERE md.f_did = 1
GROUP BY pl.name, pl.f_tname 
HAVING sum(md.td) = 0 AND total_touches >0 
ORDER BY total_touches DESC 
limit 5;

# current team lineup

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp), count(DISTINCT mp.f_trid) AS Seasons, pl.date_sold AS Benched FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Team" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY Benched, pl.nr ASC;
```


# tables

## mv_players AS mp (totals)

f_pid
f_tid
f_cid
f_rid
f_trid
f_did
f_lid
mvp
cp
td
intcpt
bh
ki
si
cas
tdcas
smp
spp
ff
won
lost
draw
played
win_pct
ga
gf
sdiff
tcasa
tcasf
tcdiff

## mv_es_players AS me (totals)

f_pid
f_tid
f_cid
f_rid
f_trid
f_did
f_lid

pass_attempts
interceptions_thrown
safe_throws
pass_distance
dumpoff_attempts
dumpoff_completions
catch_attempts
catches
handoffs
handoffs_received
handoff_catches
pickup_attempts
pickups
rushing_distance_leap
rushing_distance_push
rushing_distance_move
rushing_distance_block
rushing_distance_shadowing
leap_attempts
leaps
dodge_attempts
dodges
blitz_actions
gfi_attempts
gfis

inflicted_blocks
inflicted_defender_downs
inflicted_defender_stumbles
inflicted_pushes
inflicted_both_downs
inflicted_attacker_downs
inflicted_knock_downs
inflicted_strip_balls
inflicted_sacks
inflicted_crowd_surfs
inflicted_stuns
inflicted_kos
inflicted_bhs
inflicted_sis
inflicted_kills

sustained_blocks
sustained_knocked_downs
sustained_sacks
sustained_crowd_surfs
sustained_stuns
sustained_kos
sustained_bhs
sustained_sis
sustained_kill

inflicted_fouls
inflicted_foul_stuns
inflicted_foul_kos
inflicted_foul_bhs
inflicted_foul_sis
inflicted_foul_kills

sustained_fouls
sustained_ejections

apothecary_used
ko_recovery_attempts
ko_recoveries
thickskull_used
regeneration_attempts
regenerations

kickoffs
kick_distance
dice_rolls
dice_natural_ones
dice_natural_sixes
dice_target_sum
dice_roll_sum

big_guy_stupidity_attempts
big_guy_stupidity_successes
big_guy_stupidity_blitz_attempts
big_guy_stupidity_blitz_successes
throw_team_mate_attempts
throw_team_mate_successes
throw_team_mate_distance
throw_team_mate_to_safe_landing

times_thrown
landing_attempts
landings
distance_thrown
rushing_distance_thrown

bloodlust_rolls
bloodlust_successes
bloodfeeds
hypnoze_rolls
hypnoze_successes
tentacles_rolls
tentacles_successes
foul_appearance_rolls
foul_appearance_successes
dauntless_rolls
dauntless_successes
shadowing_rolls
shadowing_successes
bombs_throw_attempts
bombs_thrown
sustained_bomb_effect
sustained_bomb_stun
sustained_bomb_ko
sustained_bomb_bh
sustained_bomb_si
sustained_bomb_kill

## match_data AS md (single matches - can be aggregated with sum(md.%))

f_coach_id
f_team_id
f_player_id
f_race_id
f_match_id
f_tour_id
f_did
f_lid
mvp
cp
td
intcpt
bh
si
ki
inj

## match_data_es AS mx (single matches - can be aggregated with sum(mx.%))

f_pid
f_tid
f_cid
f_rid
f_mid
f_trid
f_did
f_lid

pass_attempts
interceptions_thrown
safe_throws
pass_distance
dumpoff_attempts
dumpoff_completions
catch_attempts
catches
handoffs
handoffs_received
handoff_catches
pickup_attempts
pickups
rushing_distance_leap
rushing_distance_push
rushing_distance_move
rushing_distance_block
rushing_distance_shadowing
leap_attempts
leaps
dodge_attempts
dodges
blitz_actions
gfi_attempts
gfis

inflicted_blocks
inflicted_defender_downs
inflicted_defender_stumbles
inflicted_pushes
inflicted_both_downs
inflicted_attacker_downs
inflicted_knock_downs
inflicted_strip_balls
inflicted_sacks
inflicted_crowd_surfs
inflicted_stuns
inflicted_kos
inflicted_bhs
inflicted_sis
inflicted_kills

sustained_blocks
sustained_knocked_downs
sustained_sacks
sustained_crowd_surfs
sustained_stuns
sustained_kos
sustained_bhs
sustained_sis
sustained_kill

inflicted_fouls
inflicted_foul_stuns
inflicted_foul_kos
inflicted_foul_bhs
inflicted_foul_sis
inflicted_foul_kills

sustained_fouls
sustained_ejections

apothecary_used
ko_recovery_attempts
ko_recoveries
thickskull_used
regeneration_attempts
regenerations

kickoffs
kick_distance
dice_rolls
dice_natural_ones
dice_natural_sixes
dice_target_sum
dice_roll_sum

big_guy_stupidity_attempts
big_guy_stupidity_successes
big_guy_stupidity_blitz_attempts
big_guy_stupidity_blitz_successes
throw_team_mate_attempts
throw_team_mate_successes
throw_team_mate_distance
throw_team_mate_to_safe_landing

times_thrown
landing_attempts
landings
distance_thrown
rushing_distance_thrown

bloodlust_rolls
bloodlust_successes
bloodfeeds
hypnoze_rolls
hypnoze_successes
tentacles_rolls
tentacles_successes
foul_appearance_rolls
foul_appearance_successes
dauntless_rolls
dauntless_successes
shadowing_rolls
shadowing_successes
bombs_throw_attempts
bombs_thrown
sustained_bomb_effect
sustained_bomb_stun
sustained_bomb_ko
sustained_bomb_bh
sustained_bomb_si
sustained_bomb_kill

## players AS pl

player_id
type
name
owned_by_team_id
nr
f_pos_id
date_bought
date_sold
ach_ma
ach_st
ach_ag
ach_av
extra_spp
extra_val
f_rid
f_cid
f_tname
f_rname
f_cname
f_pos_name
value
status
date_died
ma
st
ag
av
ma_ua
st_ua
ag_ua
av_ua
inj_ma
inj_st
inj_ag
inj_av
inj_ni
win_pct

## matches AS mt

match_id
round
f_tour_id
team1_id (home)
team2_id (away)
team1_score
team2_score
tcas1
tcas2
ffactor1
ffactor2
income1
income2

## mv_teams AS mr

f_tid
f_cid
f_rid
elo
swon
sdraw
slost
pts
f_trid
f_did
f_lid
mvp
cp
td
intcpt
bh
ki
si
cas
tdcas
smp
spp
ff
won
lost
draw
played
win_pct
ga
gf
sdiff
tcasa
tcasf
tcdiff

## tours

tour_id
f_did
name
winner

## game_data_skills AS sklnam

### list of players with a skill

SELECT pl.name AS Player, pl.f_tname AS Team, sklnam.name AS Skill FROM players AS pl JOIN players_skills AS pskl ON pl.player_id = pskl.f_pid JOIN game_data_skills AS sklnam ON sklnam.skill_id = pskl.f_skill_id WHERE sklnam.name = "Frenzy" ORDER BY pl.value DESC LIMIT 10;

| skill_id | name                | cat  |
|----------|---------------------|------|
|        1 | Block               | G    |
|        2 | Dauntless           | G    |
|        3 | Dirty Player        | G    |
|        4 | Fend                | G    |
|        5 | Frenzy              | G    |
|        6 | Kick                | G    |
|        7 | Kick-off Return     | G    |
|        8 | Pass Block          | G    |
|        9 | Pro                 | G    |
|       10 | Shadowing           | G    |
|       11 | Strip Ball          | G    |
|       12 | Sure Hands          | G    |
|       13 | Tackle              | G    |
|       14 | Wrestle             | G    |
|       20 | Catch               | A    |
|       21 | Diving Catch        | A    |
|       22 | Diving Tackle       | A    |
|       23 | Dodge               | A    |
|       24 | Jump Up             | A    |
|       25 | Leap                | A    |
|       26 | Side Step           | A    |
|       27 | Sneaky Git          | A    |
|       28 | Sprint              | A    |
|       29 | Sure Feet           | A    |
|       40 | Accurate            | P    |
|       41 | Dump-Off            | P    |
|       42 | Hail Mary Pass      | P    |
|       43 | Leader              | P    |
|       44 | Nerves of Steel     | P    |
|       45 | Pass                | P    |
|       46 | Safe Throw          | P    |
|       50 | Break Tackle        | S    |
|       51 | Grab                | S    |
|       52 | Guard               | S    |
|       53 | Juggernaut          | S    |
|       54 | Mighty Blow         | S    |
|       55 | Multiple Block      | S    |
|       56 | Piling On           | S    |
|       57 | Stand Firm          | S    |
|       58 | Strong Arm          | S    |
|       59 | Thick Skull         | S    |
|       70 | Big Hand            | M    |
|       71 | Claw                | M    |
|       72 | Disturbing Presence | M    |
|       73 | Extra Arms          | M    |
|       74 | Foul Appearance     | M    |
|       75 | Horns               | M    |
|       76 | Prehensile Tail     | M    |
|       77 | Tentacles           | M    |
|       78 | Two Heads           | M    |
|       79 | Very Long Legs      | M    |
|       90 | Always Hungry       | E    |
|       91 | Ball and Chain      | E    |
|       92 | Blood Lust          | E    |
|       93 | Bombardier          | E    |
|       94 | Bone Head           | E    |
|       95 | Chainsaw            | E    |
|       96 | Decay               | E    |
|       97 | Fan Favourite       | E    |
|       98 | Hypnotic Gaze       | E    |
|       99 | Loner               | E    |
|      100 | No Hands            | E    |
|      101 | Nurgle's Rot        | E    |
|      102 | Really Stupid       | E    |
|      103 | Regeneration        | E    |
|      104 | Right Stuff         | E    |
|      105 | Secret Weapon       | E    |
|      106 | Stab                | E    |
|      107 | Stakes              | E    |
|      108 | Stunty              | E    |
|      109 | Take Roots          | E    |
|      110 | Throw Team-Mate     | E    |
|      111 | Titchy              | E    |
|      112 | Wild Animal         | E    |
|      113 | Animosity           | E    |


## players_skills AS pskl

id
f_pid
f_skill_id
type