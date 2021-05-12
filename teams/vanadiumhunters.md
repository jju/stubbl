# Vanadium Hunters

The Hunters have been around a long time and in the Old-Era had one of the best players in the business. They've never been very good though, which led to relegation to the Open Division after GCVIII.

## Playbook

The Vanadium Hunters use the Hermann playbook, the original plan for playing BludBol, and the one that every other strategy is an adaptation of. The team has two thrower positions available, 4 catchers, 4 blitzers, a big guy and fills out the rest of the lineup with undistinguished concussion-fodder. Like most Hermann teams, the Hunters don't use all their specialist receivers, trusting more to a running game with the blitzers.

## Records

### Pro Level Record (W-D-L)

19-15-37

### UBBL Record (W-D-L)

36-24-58

### Prizes

* Green Cup IV - Doom Fist [[teamcasualties]]

### Seasons

| Team      | Season             | W  | D | L | GP | Win% | GF   | GA   | Cas  | CDif | FF   |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Vanadium Hunters | Orange Goblet        |    7 |    1 |    4 |     12 |    62.50 |   26 |   21 |   21 |      6 |    4 |
| Vanadium Hunters | Orange Goblet II     |    5 |    2 |    4 |     11 | 54.55 |   22 |   20 |   16 |      4 |    0 |
| Vanadium Hunters | UBBL Challenge       |    1 |    1 |    1 |      3 |      50.00 |    8 |    7 |    7 |      2 |    0 |
| Vanadium Hunters | Green Cup V Memorial |    4 |    3 |    5 |     12 | 45.83 |   18 |   21 |   14 |     -4 |    2 |
| Vanadium Hunters | Green Cup IV         |    4 |    2 |    5 |     11 | 45.45 |   31 |   25 |   40 |     30 |   -1 |
| Vanadium Hunters | Green Cup VII        |    3 |    7 |    6 |     16 |  40.63 |   30 |   37 |   27 |      7 |    2 |
| Vanadium Hunters | Green Cup Classic 06 |    2 |    2 |    4 |      8 |    37.50 |   15 |   19 |   10 |     -3 |    1 |
| Vanadium Hunters | Green Cup I          |    3 |    1 |    6 |     10 |      35.00 |   24 |   27 |   16 |     -6 |    1 |
| Vanadium Hunters | Green Cup III        |    3 |    1 |    6 |     10 |      35.00 |   20 |   23 |   19 |      3 |   -1 |
| Vanadium Hunters | Green Cup VIII       |    4 |    2 |   10 |     16 |   31.25 |   28 |   40 |   16 |    -13 |   -1 |
| Vanadium Hunters | UBBL Challenge II    |    0 |    1 |    2 |      3 | 16.67 |    4 |    8 |    2 |     -6 |   -1 |
| Vanadium Hunters | UBBL Challenge III   |    0 |    0 |    3 |      3 |       0.00 |    5 |   10 |    1 |     -1 |   -2 |
| Vanadium Hunters | UBBL Challenge IV    |    0 |    0 |    2 |      2 |       0.00 |    2 |    8 |    0 |     -2 |   -1 |

`
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Vanadium Hunters" ORDER BY mr.win_pct DESC limit 15;
`

## History

They are generally a bad team at the pro level, but they did achieve a Doom Fist in the old-era UBBL. 

### Seasons

The Hunters had never managed to achieve a winning season before the inaugural Open Division Orange Goblet.

### Stars & Scrubs

| Player           | Team        | Position      | W  | D | L | GP   | TD   | Cp | Int | BH   | SI   | Ki   | MVP  | SPP  |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| *HalfJack* | Vanadium Hunters | Thrower |  ?? | ?? | ?? | 51 | 5 | 84 | 0 | 1 | 1 | 0 | 5 | 128 |
| *Moseh* | Vanadium Hunters | Blitzer |  ?? | ?? | ?? | 51 | 25 | 9 | 2 | 6 | 1 | 0 | 4 | 122 |
| *Nyazi* | Vanadium Hunters | Blitzer | ?? | ?? | ?? | 51 | 28 | 5 | 1 | 7 | 3 | 0 | 2 | 121 |
| **Melchor**   | Vanadium Hunters | Thrower  |   16 |   10 |   30 |   56 |    0 |   68 |    0 |    2 |    0 |    0 |    8 |  112 |
| *Gabriel* | Vanadium Hunters | Thrower | ?? | ?? | ?? | 49 | 1 | 62 | 0 | 1 | 1 | 0 | 6 | 99 |
| *Kikin* | Vanadium Hunters | Catcher |  ?? | ?? | ?? | 46 | 22 | 5 | 0 | 0 | 0 | 5 | 98 |
| *Vrej* | Vanadium Hunters | Blitzer | ?? | ?? | ?? | 40 | 6 | 1 | 0 | 10 | 11 | 1 | 6 | 93 |
| **Gautstafr** | Vanadium Hunters | Catcher  |   10 |    4 |   11 |   25 |   21 |    4 |    4 |    0 |    0 |    0 |    3 |   90 |
| *Teague* | Vanadium Hunters | Blitzer |  ?? | ?? | ?? | 51 | 7 | 0 | 1 | 7 | 5 | 5 | 6 | 87 |
| **Marta**     | Vanadium Hunters | Blitzer  |   17 |   16 |   24 |   57 |    8 |    0 |    3 |   11 |    7 |    2 |    2 |   80 |
| **Amata**     | Vanadium Hunters | Catcher  |   11 |    5 |   13 |   29 |   20 |    7 |    1 |    0 |    1 |    0 |    1 |   76 |
| **Charles**   | Vanadium Hunters | Thrower  |   15 |   10 |   16 |   41 |    1 |   38 |    0 |    1 |    2 |    0 |    4 |   67 |
| **Mayflower** | Vanadium Hunters | Lineman  |   26 |   17 |   36 |   79 |    0 |    2 |    2 |    7 |    0 |    1 |    8 |   62 |
| Daley    | Vanadium Hunters | Blitzer  |    6 |    4 |   18 |   28 |   12 |    0 |    1 |    2 |    1 |    1 |    3 |   61 |
| **Boguslaw**  | Vanadium Hunters | Ogre     |   15 |   15 |   21 |   51 |    0 |    1 |    0 |   16 |    6 |    0 |    3 |   60 |
| Leibniz  | Vanadium Hunters | Blitzer  |   10 |   14 |   19 |   43 |    9 |    1 |    0 |    2 |    2 |    1 |    4 |   58 |
| Majken   | Vanadium Hunters | Catcher  |    8 |    9 |   18 |   35 |   10 |    3 |    0 |    0 |    0 |    0 |    5 |   58 |
| **Mohan**     | Vanadium Hunters | Blitzer  |   12 |   12 |   20 |   44 |    8 |    2 |    1 |    4 |    1 |    0 |    3 |   53 |


`
SELECT pl.name AS Player, pl.f_tname AS Team, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Vanadium Hunters" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
`

There's a lot of history in the list of star Hunters, but modern-era success has been minimal. [[Vrej]] came back from a fine retirement to play in the Green Cup V Memorial tournament and while that was enough to push him up the all-time Hunters hall of fame, it also cost him his career. [[Mayflower]] is sometimes credited with playing more in th old-era than is true. His real first season was GCIV.

### Management

The Noordennen family that runs the Hunters were the first to jump on the free agency model, using some of their Orange Goblet winnings to purchase [[Donat]] from the [Badger Claws](badgerclaws).

### Fans

Their fans love their traditional style and get really angry at teams like the [Kaiju Dynamo](kaijudynamo) who try new-fangled approaches to the game. That it hasn't been very successful, well maybe that will change in OGII.

### Famous Games

The Green Cup V Memorial tournament saw the Hunters knock off the first-seed [Old Wyrms](oldwyrms) in the opening round of the playoffs. Granted, this was a street-level match with no real implications.