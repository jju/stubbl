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

The Fatality are cash-poor right now, which might make their Green Cup quest a bust from the get-go, but they pulled off a draw in a blizzard against a Tatters team that had a 2-0 lead in the second half (that's probably a bit of a rarity). EF 2 - CT 2

Clydon was removed from the match before the ball hit the ground, but it's hard to say if he would have been able to help the Vagabonds to victory in a blizzard. The big development was that Aeson was held to a single TD. This might mean trouble for the Claws, or an opportunity to actually develop a more diverse squad. BC 4 - ZV 2

The Spectres are expected to do as little as possible this season, but bursting out the gate with a win against the Hounds seemed like it might happen until late in the second half of this match. A sack near the Hounds end, with a long stretch to Costache gave the Hounds a well-fought draw. GH 3 - DS 3

The Cogs got off to a good start and the Farmers didn't show any signs of their tankiness despite the loss. IC 3 - GF 1

The Wyrms didn't start the way they hope to end, but who is? OW 3 - CF 3

Sabah did his job, as far the Dynamo were concerned, but they just couldn't handle the offensive pressure from the Tide. That they spread the scoring around between 4 receivers (and a lineman) maybe signals a shift from the all-or-nothing approach the Claws have been using (and the Tide themselves pioneered in the Yakup era). FT 6 - KD 3

# players of the week

Sabah and Costache tied  with 9 SPP on 3 TDs in Week 1 of GCX, but Costache gets the edge as her points salvaged a draw while Sabah's were in an entirely losing cause. Of some note, in the first week of the inaugural Orange Goblet tournament Achille scored 4 TDs and got the MVP award for an SPP total of 17.


```
SELECT pl.name, pl.f_tname, mt.f_tour_id, tours.tour_id, mt.round, md.f_match_id, md.td, md.cp, md.intcpt, md.bh, md.si, md.ki, md.mvp, (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP 
FROM match_data AS md 
JOIN players AS pl ON md.f_player_id = pl.player_id
JOIN matches AS mt ON md.f_match_id = mt.match_id 
JOIN tours ON mt.f_tour_id = tours.tour_id
WHERE (mt.f_tour_id = 23 OR mt.f_tour_id = 22) AND mt.round = 1
ORDER BY SPP DESC 
limit 5;
```
