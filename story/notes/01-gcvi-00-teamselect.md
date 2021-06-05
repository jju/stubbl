[if $bbrules < 1]
All right. You can pull up a list of teams that will be playing in a couple of weeks. 
[else]
All right. Bludbol is about scoring touchdowns and bashing the snot out of other teams. 
[continue]
[if $bbrules >= 1]
You pull up the list of teams that will begin playing in a couple of weeks. There are a bunch of excited people on your terminal arguing about who will obviously be the best this season, but you've never really been one to put a lot of faith in what people say in the aether. Without any first-hand knowledge these teams all look the same.
[continue]
[if $bbtactics > 0]
Your cursory research into how bludbol is played got you some notes on team playbooks (and styles of play natural to those playbooks). If everyone follows their plans, this could be useful information.
[continue]
[if ($bbhistory || $bbstats) > 0]
If anything you find on the EDS can be believed, you've got some notes on what these teams did the last time there was bludbol down in the Stacks. (The time after the Mass Elevator but before the Interruption is generally being called the old-era UBBL and they played four and a half Green Cups.)
[continue]
[if $bbbusiness]
The people behind these teams aren't being too forthcoming about how they are running things; all you're getting is hype and a few scraps of financials.
[continue]
The teams for this tournament are organized into a couple of divisions: the Stacks and the Outlands.

## Stacks

### Carcosan Tatters

[if $bbtactics]
- Nergal (Defensive Bashing)
[continue]
[if $bbhistory]
- Won Green Cup II
[continue]
[if $bbstats]
- 71% Wins, 1.81 TD/game, 2.21 Casualties/Game, 1 Championship
[continue]
[if $bbbusiness]
- BS Encef (a former player) runs the team.
- Big budget. Die-hard fans only.
[continue]
[if $time >= 570 && $time < 576.5]
- Current Record 1-0-0
[continue] 

### Filthy Tide

[if $bbtactics]
- Scrying Avian (Fragile Running)
[continue]
[if $bbhistory]
 - Had an amazing scorer named Sardines
[continue]
[if $bbstats]
- 49% Wins, 2.55 TD/game, 0.73 Casualties/Game
[continue]
[if $bbbusiness]
- Asmodeus (a former player) runs the team.
- Low budget. Interested fanbase.
[continue]
[if $time >= 570 && $time < 576.5]
- Current Record 1-0-0
[continue] 

### Ravenous Eagles

[if $bbtactics]
- Charles Dorf (Slow Bashing)
[continue]
[if $bbhistory]
 - New to Green Cup play
[continue]
[if $bbstats]
- 71% Wins (non-Pro), 1.47 TD/game, 2.53 Casualties/Game
[continue]
[if $bbbusiness]
- BR Ossa ownership group running the team. BR Ossa was a former player, but the "group" behind the team is much less obvious.
- Mid-range budget. Full bandwagon of fans.
[continue]
[if $time >= 570 && $time < 576.5]
- Current Record 0-0-1
[continue] 

### Zensun Vagabonds

[if $bbtactics]
- Hermann (All-rounder)
[continue]
[if $bbhistory]
 - Founding team of old-era UBBL
[continue]
[if $bbstats]
- 39% Wins, 1.98 TD/game, 1.53 Casualties/Game
[continue]
[if $bbbusiness]
- Mud Dib is the team's Old-Era coach, returned to lead again.
- No budget. Die-hard fans only.
[continue]

## Outlands

### Glorious Hounds

[if $bbtactics]
- High Extension (Passing)
[continue]
[if $bbhistory]
- Only played in one Green Cup before, but came in second.
[continue]
[if $bbstats]
- 51% Wins, 2.56 TD/game, 0.73 Casualties/Game
[continue]
[if $bbbusiness]
- Ozyman (former player) runs the team. A bit of a showboat.
- Mid-range budget. Engaged fanbase.
[continue]

### Gore Farmers

[if $bbtactics]
- Orville-Crush (Bashing)
[continue]
[if $bbhistory]
- Were once relegated but made it back to Green Cup level play
[continue]
[if $bbstats]
- 48% Wins, 1.46 TD/game, 1.69 Casualties/Game
[continue]
[if $bbbusiness]
- Spleen Hucker (former player) runs the team. 
- Big budget. Die-hard fans only.
[continue]

### Irregular Cogs

[if $bbtactics]
- Drop Eagle (Running)
[continue]
[if $bbhistory]
- Won Green Cup I
[continue]
[if $bbstats]
- 60% Wins, 2.78 TD/game, 0.87 Casualties/Game, 1 Championship
[continue]
[if $bbbusiness]
- Gryj the Hun is is the team's Old-Era coach, returned to lead again. One of the driving forces behind organizing the UBBL.
- Low budget. Excited fanbase.
[continue]

### Old Wyrms

[if $bbtactics]
- Excelsior (Fragile Passing)
[continue]
[if $bbhistory]
- Founding team and won Green Cups III and IV
[continue]
[if $bbstats]
- 65% Wins, 3.25 TD/game, 0.43 Casualties/Game, 2 Championships
[continue]
[if $bbbusiness]
- Hems is the son of the team's old-era star thrower and runs the team.
- Mid-range budget. Engaged fanbase.
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
The Ravenous Eagles' fans are pretty hyped up online, and the Gore Farmers' are pretty grouchy about who they're sharing a division with. But whatever.
[continue]
[if $bbhistory || $bbstats]
It's probably important to remember that the new teams bearing these names aren't coming back with old-school rosters, just whichever stars could be enticed.
[continue]
[if $bbbusiness]
It's hard to say what influence the question of resources is going to have. We're supposed to be past the savage times of shooting people over credits, right? However, everything you know about the world says that the more an organization has, the less luck they will need to deal with adversity, while less-flush organizations have a thinner margin.
[continue]
One thing jumping out at you is the Carcosan Tatters team name. Back before the mass elevator there was a scabby old gang lead by a Carcosan for a while. There must be a connection there, right?

Other than that, assuming those divisions are vaguely spatial, the Outlands teams are probably closer to your cube. It might be useful if you want to feel a bit more locally connected.

> Don't just follow one team. Watch all the games on EDS.->[[01-gcvi-01-burger]]
> Follow the Carcosan Tatters->[[01-gcvi-01-ct]]
> Follow the Filthy Tide->[[01-gcvi-01-ft]]
> Follow the Glorious Hounds->[[01-gcvi-01-gh]]
> Follow the Gore Farmers->[[01-gcvi-01-gf]]
> Follow the Irregular Cogs->[[01-gcvi-01-ic]]
> Follow the Old Wyrms->[[01-gcvi-01-ow]]
> Follow the Ravenous Eagles->[[01-gcvi-01-re]]
> Follow the Zensun Vagabonds->[[01-gcvi-01-zv]]
