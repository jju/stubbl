[if $research === 'none']
All right. With no knowledge of anything regarding bludbol you can pull up a list of teams playing for the Green Cup. They've even played a game so you have their current records at hand. 
[else]
All right. Bludbol is about scoring touchdowns and bashing the snot out of other teams. 
[continue]
[if $research === 'basic']
You pull up the list of teams that currently battling it out (along with their current W-D-L records). There are a bunch of excited people on your terminal arguing about who will obviously be the best this season, but really it's a bit of a wash.
[continue]
[if $research === 'tactics']
After spending some time researching, you've got some notes on team playbooks (and styles of play those playbooks recommend) to go with their current W-D-L records.
[continue]
[if $research === ('history' || 'statistics')]
After spending some time researching, you've got some notes on what these teams did the last time there was bludbol down in the Stacks along with their current W-D-L records.
[continue]
The teams are arranged in a couple of divisions: the Stacks and the Outlands.

## Stacks
[if $research === ('basic' || 'none')]
* Carcosan Tatters 1-0-0
* Filthy Tide 1-0-0
* Ravenous Eagles 0-0-1
* Zensun Vagabonds 0-0-1
[continue]
[if $research === 'tactics']
* Carcosan Tatters 1-0-0 - Nergal (Defensive Bashing)
* Filthy Tide 1-0-0 - Scrying Avian (Fragile Running)
* Ravenous Eagles 0-0-1 - Charles Dorf (Slow Bashing)
* Zensun Vagabonds - Hermann (All-rounder)
[continue]
[if $research === 'history']
* Carcosan Tatters 1-0-0 - Won Green Cup II
* Filthy Tide 1-0-0 - Had an amazing scorer named Sardines
* Ravenous Eagles 0-0-1 - New to Green Cup play
* Zensun Vagabonds 0-0-1 - Founding team of old-era UBBL
[continue]
[if $research === 'statistics']
* Carcosan Tatters 1-0-0 - 71% Wins, 1.81 TD/game, 2.21 Casualties/Game, 1 Championship
* Filthy Tide 1-0-0 - 49% Wins, 2.55 TD/game, 0.73 Casualties/Game
* Ravenous Eagles 0-0-1 - 71% Wins (non-Pro), 1.47 TD/game, 2.53 Casualties/Game
* Zensun Vagabonds 0-0-1 - 39% Wins, 1.98 TD/game, 1.53 Casualties/Game
[continue]
[if $research === 'business']
* Carcosan Tatters 1-0-0 - Big budget. Die-hard fans only.
* Filthy Tide 1-0-0 - Low budget. Interested fanbase.
* Ravenous Eagles 0-0-1 - Mid-range budget. Full bandwagon of fans.
* Zensun Vagabonds 0-0-1 - No budget. Die-hard fans only.
[continue]
## Outlands
[if $research === ('basic' || 'none')]
* Glorious Hounds 1-0-0
* Gore Farmers 1-0-0
* Irregular Cogs 0-0-1
* Old Wyrms 0-0-1
[continue]
[if $research === 'tactics']
* Glorious Hounds 1-0-0 - High Extension (Passing)
* Gore Farmers 1-0-0 - Orville-Crush (Bashing)
* Irregular Cogs  0-0-1 - Drop Eagle (Running)
* Old Wyrms  0-0-1 - Excelsior (Fragile Passing)
[continue]
[if $research === 'history']
* Glorious Hounds 1-0-0 - Only played in one Green Cup before, but came in second.
* Gore Farmers 1-0-0 - Were once relegated but made it back to Green Cup level play
* Irregular Cogs  0-0-1 - Won Green Cup I
* Old Wyrms  0-0-1 - Founding team and won Green Cups III and IV
[continue]
[if $research === 'statistics']
* Glorious Hounds 1-0-0 - 51% Wins, 2.56 TD/game, 0.73 Casualties/Game
* Gore Farmers 1-0-0 - 48% Wins, 1.46 TD/game, 1.69 Casualties/Game
* Irregular Cogs  0-0-1 - 60% Wins, 2.78 TD/game, 0.87 Casualties/Game, 1 Championship
* Old Wyrms  0-0-1 - 65% Wins, 3.25 TD/game, 0.43 Casualties/Game, 2 Championships
[continue]
[if $research === 'business']
* Glorious Hounds 1-0-0 - Mid-range budget. Engaged fanbase.
* Gore Farmers 1-0-0 - Big budget. Die-hard fans only.
* Irregular Cogs 0-0-1 - Low budget. Excited fanbase.
* Old Wyrms 0-0-1 - Mid-range budget. Engaged fanbase.
[continue]
[if $research !== 'basic']
So if you're going to be watching and following a team for, geez, 17 MSeconds, what kind of team do you want to spend time with?
[continue]
[if $research === ('basic' || 'business')]
The Ravenous Eagles' fans are pretty hyped up online, and the Gore Farmers' are pretty grouchy about who they're sharing a division with. But whatever.
[continue]
[if $research === 'tactics']
The Ravenous Eagles' fans are pretty hyped up online, and the Gore Farmers' are pretty grouchy about who they're sharing a division with (it sounds like being surrounded by teams that are good at scoring might make life difficult). But whatever.
[continue]
[if $research === ('history' || 'statistics')]
It's probably important to remember that the new teams bearing these names aren't coming back with old-school rosters, just whichever stars could be enticed.
[continue]
[if $research === 'business']
It's hard to say what influence the money question is going to have, but everything you know about the world says that the more money an organization has, the less luck they will need to deal with adversity, while less-flush organizations have a thinner margin.
[continue]
[if $research === 'none']
It's hard to care just based on a name so you might as well choose randomly. 
[continue]
One thing jumping out at you is the Carcosan Tatters team name. Back before the mass elevator there was a Tatters gang. There must be a connection there, right?

Other than that, assuming those divisions are vaguely spatial, the Outlands teams are probably closer to your cube. 

> Don't just follow one team. Watch all the games on EDS.->[[01-gcvi-02-burger]]
> Follow the Carcosan Tatters->[[01-gcvi-02-ct]]
> Follow the Filthy Tide->[[01-gcvi-02-ft]]
> Follow the Glorious Hounds->[[01-gcvi-02-gh]]
> Follow the Gore Farmers->[[01-gcvi-02-gf]]
> Follow the Irregular Cogs->[[01-gcvi-02-ic]]
> Follow the Old Wyrms->[[01-gcvi-02-ow]]
> Follow the Ravenous Eagles->[[01-gcvi-02-re]]
> Follow the Zensun Vagabonds->[[01-gcvi-02-zv]]

