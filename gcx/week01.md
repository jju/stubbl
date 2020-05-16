# schedule

* Filthy Tide - Kaiju Dynamo
* Badger Claws - Zensun Vagabonds
* Ravenous Eagles -	Orbital Machine
* TC Sump Runners -	Arborists
* Glorious Hounds -	Darkling Spectres
* Eldritch Fatality - Carcosan Tatters
* Old Wyrms -	Cackling Furies
* Irregular Cogs - Gore Farmers

## matches to watch

The Sump Runners vs the Arborists is an immediate rematch of the UBBL Challenge III title bout. The Arborists drubbed the Runners last time and the Runners don't have a good replacement lineup ready.

We'll also be interested in the Filthy Tide vs Kaiju Dynamo to see if Venus can be the player she was groomed for and if Sabah still has enough left in the tank to lead this Dynamo team.

Everyone else will just be trying to establish themselves and not wind up in too big of a hole.

# recap

The Sump Runners brought a chainsaw and a friggin' giant but couldn't manage to overturn the Arborist offensive juggernaut. SR 0 - AR 5

The Machine had a long layoff since GCIX but managed to pull out a respectable draw against the Eagles who are a bit more dangerous than people might assume this year. RE 2 - OM 2

The Fatality are cash-poor right now, which might make their Green Cup quest a bust from the get-go.

# player of the week



```
SELECT 
	pl.name, 
	pl.f_tname, 
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
WHERE (mt.f_tour_id = 23 OR mt.f_tour_id = 22) AND mt.round = 1
ORDER BY SPP DESC 
limit 5;
```
