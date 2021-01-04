BludBol bludbol bludbol. This shouldn't be too hard to find. They've been doing this uphive distraction for years down here now. You're sure that even back before the Interruption and closing of Bugs' for good, he was showing games on screens in there. You remember the flicker. They didn't have very good resolution. But there was something about a bunch of people together. They were getting into it. Of course they were, it was a spectacle designed to distract them from the way their lives had been violated using as many resources as could be mustered. No one had a chance. But that can't be the only way it all shakes out. 

There must be games happening out there. Didn't they build stadiums down here? When is the last time you left your cubicle? And really, you don't need to leave. The feeds are all available on EDS.

So how would you like to play this?

> [[Watch BludBol by yourself (on the EDS).->gcx-watch-eds]]
> [[Find an equivalent dive to Bugs and watch there.->gcx-watch-fh]]
> [[Hit the streets.->gcx-watch-st]]

:: gcx-watch-fh

[unless passage.visits > 1]

As expected, Bugs' is no more. He used to move it but none of his old call-signs work. It's been a long time. You're going to have to try somewhere else.

You end up at Fazel and Hiver's. It makes your stomach turn to look at the grotesque faux grit plastered all over. A dive bar that is held together with money. But it has screens and people wearing coloured shirts and gear, a big bunch in green and yellow and another group in orange and blue ~~{reveal link: 'EDS', text: '(Old Wyrms and Filthy Tide colours, respectively.)'}~~.

[else]

Back at Fazel and Hiver's. It may be corporate and terrible, but the screens work and there are people.

[continue]

[unless fan]

There's space for you to settle in and watch a game alone. You don't know any of these people, so that's probably the best approach for now. Or you could try and *shudder* be social.

> [[Watch the games and the fans.->gcx-watch-fh-solo]
> [[Try joining in with the Filthy Tide fans.->gcx-watch-fh-tide]]
> [[Try watching with the Old Wyrms fans.->gcx-watch-fh-wyrm]]

[else]

The bar is big enough you can watch by yourself if you want, or you can join some of the factions.

> [[Watch the games by yourself.->gcx-watch-fh-solo]]
> [[Watch with the Filthy Tide fans.->gcx-watch-fh-tide]]
> [[Watch with the Old Wyrms fans.->gcx-watch-fh-wyrm]]

[continue]

> {back link}

:: gcx-watch-fh-solo

seasonTime: seasonTime + 1

--

[if seasonTime === 1]

The Filthy Tide beat the team in pink ~~{reveal link: 'EDS', text: 'Kaiju Dynamo'}~~ handily and the Wyrms got a draw with their opponents ~~{reveal link: 'EDS', text: 'Cackling Furies'}~~.

One of the Tide fans is buying rounds for the bar in celebration. She's big and thundering, "This is it! This is the year!" There are some smirks and disdain from the Wyrms fans at the other end.

[continue]

[if seasonTime === 2]

The Wyrms beat a green and blue team ~~{reveal link: 'EDS', text: 'Badger Claws'}~~ 4-3. The Tide fans and the Wyrms fans seemed happy about this one, but the Tide lost their match to a team in black and gold ~~{reveal link: 'EDS', text: 'Carcosan Tatters'}~~.

[continue]

[if seasonTime === 3]

The Tide got absolutely crushed by a team in blue and green ~~{reveal link: 'EDS', text: 'Zensun Vagabonds'}~~ and the fans are feeling pretty down. The Wyrms lost to the Gore Farmers ~~{reveal link: 'EDS', text: 'in orange and black'}~~ so there was some commiserating. It felt like there were a few Farmers fans hanging around in the bar too, but they didn't seem like they were gloating.

[continue]

[if seasonTime === 4]

The Tide lost to a team in red and blue ~~{reveal link: 'EDS', text: 'Irregular Cogs'}~~ and the fans are feeling pretty down. The Wyrms tied their match with the Kaiju Dynamo.

[continue]

[if seasonTime === 5]

The Tide lost to a team in red and white ~~{reveal link: 'EDS', text: 'TC Sump Runners'}~~ and the fans are feeling pretty down. The Wyrms tied their match with the Vagabonds, escaping without any terrible injuries.

[continue]

> [[Get a reaction from the Tide fans->gcx-react-fh-tide]]
> [[Talk to the Wyrm fans->gcx-react-fh-wyrm]]

:: gcx-react-fh-tide

[if seasonTime === 1]

The orange and blue-clad Filthy Tide fans are ebuillent. You get a few beers bought for you as they tell you all about their team. A lot of the time they're talking over each other and there are arguments bursting out as it goes, but generally these aren't horrible people. One glassy-eyed fan gets very serious about how important Sardines was to her personally as a kid and how sad she was when his career ended. You aren't learning a lot about the tactics used in BludBol, but you can see what the game is meaning to them.

[continue]

[if seasonTime === 2]

[continue]

> [[Come back and watch with the Tide fans next week->gcx-watch-fh-tide]]
> [[Keep to yourself at FH's next week->gcx-watch-fh-tide]]
> [[Stay home and watch on the EDS->gcx-watch-eds]]
:: gcx-watch-fh-tide

[if seasonTime === 2]

This week you joined up to watch with the Filthy Tide fans in Fazel and Hiver's. They played against the Carcosan Tatters and lost. A skinny young receiver named Venus was injured in the match and the rest of the conversation in the bar was about how worried they were for her. There was a lot of grouching about how the Tatters cheat. You also heard some cheering from the other end of the bar, where the Wyrms seem to have won their match.


:: gcx-react-fh-wyrm

[if seasonTime === 1]

The fans in green and yellow are arguing with each other. Most of the chatter is about who is to blame for not completely humiliating their opponents, the Furies. Trying to elbow your way into a conversation where everyone is a self-proclaimed expert ends up with you getting initially yelled at and subsequently ignored. It looks like they are not a super-welcoming if you are asking questions rather than listing the ways the Wyrms are actually the best.




At this point you've watched a third of the season and both the Filthy Tide and the Old Wyrms are not doing so hot overall. Though the Wyrms are second place in the Stacks division, they only have one win and three draws, while the Tide have 4 losses to go with their lone win.~~{reveal link: 'EDS', text: 'The Carcosan Tatters are the top of the league with W-D-L 3-1-1.'}~~ 

A little after the Wyrms match wraps up, a gaggle of hivers in orange and black pile in in a raucous mood. The Gore Farmers won their game against the Spectres and these ones at least seem in the mood for a fight to celebrate. You remember that sound from the beforetimes, when it meant violence was in the air. What's your play here?

> [Slip out before anything happens. These are just a bunch of idiots.]
> [Hang out and observe - craft]
> [Make sure your friends are all right - compassion]
> [Take charge of the situation - chutzpah]

> [Okay, I can see how this would be fun, but I am not a fan fan.]
> [This is all so pointless.]
> [Yes, I am ready to declare my allegiance to a team and everything.]

[continue]
What will you do next week?
> [Same as this week. Watch right here.->]
> [I've got the gist of this. I can just watch on the EDS]
> {back link, label: 'I'll find somewhere else to watch.'}
> 