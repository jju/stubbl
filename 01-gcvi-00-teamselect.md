[if $bbrules < 1]
All right. You can pull up a list of teams that will be playing in a couple of weeks. 
[else]
All right. Bludbol is about scoring touchdowns and bashing the snot out of other teams. 
[continue]
[if $bbrules >= 1]
You pull up the list of teams that will be playing in a couple of weeks. There are a bunch of excited people on your terminal arguing about who will obviously be the best this season, but really it's a bit of a wash.
[continue]
[if $bbtactics > 0]
After spending some time researching, you've got some notes on team playbooks (and styles of play those playbooks recommend).
[continue]
[if ($bbhistory || $bbstats) > 0]
After spending some time researching, you've got some notes on what these teams did the last time there was bludbol down in the Stacks. (The time after the Mass Elevator but before the Interruption is generally being called the old-era UBBL and they played four and a half Green Cups.)
[continue]
The teams are arranged in a couple of divisions: the Stacks and the Outlands.

## Stacks
[if $bbrules < 1]
* Carcosan Tatters
* Filthy Tide
* Ravenous Eagles
* Zensun Vagabonds
[continue]
[if $bbtactics > 0]
* Carcosan Tatters - Nergal (Defensive Bashing)
* Filthy Tide - Scrying Avian (Fragile Running)
* Ravenous Eagles - Charles Dorf (Slow Bashing)
* Zensun Vagabonds - Hermann (All-rounder)
[continue]
[if $bbhistory > 0]
* Carcosan Tatters - Won Green Cup II
* Filthy Tide - Had an amazing scorer named Sardines
* Ravenous Eagles - New to Green Cup play
* Zensun Vagabonds - Founding team of old-era UBBL
[continue]
[if $bbstats > 0]
* Carcosan Tatters - 71% Wins, 1.81 TD/game, 2.21 Casualties/Game, 1 Championship
* Filthy Tide - 49% Wins, 2.55 TD/game, 0.73 Casualties/Game
* Ravenous Eagles - 71% Wins (non-Pro), 1.47 TD/game, 2.53 Casualties/Game
* Zensun Vagabonds - 39% Wins, 1.98 TD/game, 1.53 Casualties/Game
[continue]
[if $bbbusiness > 0]
* Carcosan Tatters - Big budget. Die-hard fans only.
* Filthy Tide - Low budget. Interested fanbase.
* Ravenous Eagles - Mid-range budget. Full bandwagon of fans.
* Zensun Vagabonds - No budget. Die-hard fans only.
[continue]
## Outlands
[if $bbrules < 1]
* Glorious Hounds
* Gore Farmers
* Irregular Cogs
* Old Wyrms
[continue]
[if $bbtactics > 0]
* Glorious Hounds - High Extension (Passing)
* Gore Farmers - Orville-Crush (Bashing)
* Irregular Cogs - Drop Eagle (Running)
* Old Wyrms - Excelsior (Fragile Passing)
[continue]
[if $bbhistory > 0]
* Glorious Hounds - Only played in one Green Cup before, but came in second.
* Gore Farmers - Were once relegated but made it back to Green Cup level play
* Irregular Cogs - Won Green Cup I
* Old Wyrms - Founding team and won Green Cups III and IV
[continue]
[if $bbstats > 0]
* Glorious Hounds - 51% Wins, 2.56 TD/game, 0.73 Casualties/Game
* Gore Farmers - 48% Wins, 1.46 TD/game, 1.69 Casualties/Game
* Irregular Cogs - 60% Wins, 2.78 TD/game, 0.87 Casualties/Game, 1 Championship
* Old Wyrms - 65% Wins, 3.25 TD/game, 0.43 Casualties/Game, 2 Championships
[continue]
[if $bbbusiness > 0]
* Glorious Hounds - Mid-range budget. Engaged fanbase.
* Gore Farmers - Big budget. Die-hard fans only.
* Irregular Cogs - Low budget. Excited fanbase.
* Old Wyrms - Mid-range budget. Engaged fanbase.
[continue]
[if $bbrules]
So if you're going to be watching and following a team for, geez, 18 MSeconds, what kind of team do you want to spend time with?
[else]
It's hard to care just based on a name so you might as well choose randomly. 
[continue]
[if $bbtactics]
The Ravenous Eagles' fans are pretty hyped up online, and the Gore Farmers' are pretty grouchy about who they're sharing a division with (it sounds like being surrounded by teams that are good at scoring might make life difficult). But whatever.
[continue]
[if !$bbtactics && $bbrules]
[continue]
[if ($bbhistory || $bbstats) > 0]
It's probably important to remember that the new teams bearing these names aren't coming back with old-school rosters, just whichever stars could be enticed.
[continue]
[if $bbbusiness > 0]
It's hard to say what influence the money question is going to have, but everything you know about the world says that the more money an organization has, the less luck they will need to deal with adversity, while less-flush organizations have a thinner margin.
[continue]
One thing jumping out at you is the Carcosan Tatters team name. Back before the mass elevator there was a Tatters gang. There must be a connection there, right?

Other than that, assuming those divisions are vaguely spatial, the Outlands teams are probably closer to your cube. 

> Don't just follow one team. Watch all the games on EDS.->[[01-gcvi-01-burger]]
> Follow the Carcosan Tatters->[[01-gcvi-01-ct]]
> Follow the Filthy Tide->[[01-gcvi-01-ft]]
> Follow the Glorious Hounds->[[01-gcvi-01-gh]]
> Follow the Gore Farmers->[[01-gcvi-01-gf]]
> Follow the Irregular Cogs->[[01-gcvi-01-ic]]
> Follow the Old Wyrms->[[01-gcvi-01-ow]]
> Follow the Ravenous Eagles->[[01-gcvi-01-re]]
> Follow the Zensun Vagabonds->[[01-gcvi-01-zv]]
