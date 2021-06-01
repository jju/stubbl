# top 10 spp

| Player    | Team            | Season         | Round | TD   | Cp   | Int    | BH   | SI   | Ki   | MVP  | SPP  |
|-----------|-----------------|----------------|-------|------|------|--------|------|------|------|------|------|
| Aeson     | Badger Claws    | Green Cup X    |    15 |    9 |    0 |      0 |    0 |    0 |    0 |    1 |   32 |
| Aeson     | Badger Claws    | Green Cup X    |     9 |    8 |    0 |      0 |    0 |    0 |    0 |    1 |   29 |
| Donat.    | Badger Claws    | Green Cup VIII |   253 |    8 |    0 |      0 |    1 |    0 |    0 |    0 |   26 |
| Venus     | Filthy Tide     | Green Cup X    |     9 |    8 |    0 |      0 |    0 |    0 |    0 |    0 |   24 |
| Aeson     | Badger Claws    | Green Cup IX   |     5 |    6 |    0 |      0 |    0 |    0 |    0 |    1 |   23 |
| Souta.    | Old Wyrms       | Green Cup IX   |    13 |    6 |    3 |      0 |    0 |    0 |    0 |    0 |   21 |
| Aeson     | Badger Claws    | Green Cup IX   |    12 |    7 |    0 |      0 |    0 |    0 |    0 |    0 |   21 |
| Costache. | Glorious Hounds | Green Cup VIII |    13 |    7 |    0 |      0 |    0 |    0 |    0 |    0 |   21 |
| Souta.    | Old Wyrms       | Green Cup IX   |    12 |    4 |    2 |      0 |    0 |    0 |    0 |    1 |   19 |
| Costache. | Glorious Hounds | Green Cup VIII |    11 |    6 |    1 |      0 |    0 |    0 |    0 |    0 |   19 |

[[aeson]][[donat]][[Venus]][[souta]][[costache]]

`
SELECT pl.name,  pl.f_tname,  tours.name, mt.round, md.td,  md.cp,  md.intcpt,  md.bh,  md.si,  md.ki,  md.mvp,  (md.td * 3) + md.cp + (md.intcpt * 2) + (md.bh * 2) + (md.si * 2) + (md.ki * 2) + (md.mvp * 5) AS SPP  FROM match_data AS md  JOIN players AS pl ON md.f_player_id = pl.player_id JOIN matches AS mt ON md.f_match_id = mt.match_id  JOIN tours ON tours.tour_id = mt.f_tour_id WHERE md.f_did = 1 ORDER BY SPP DESC limit 10;
`

# top 10 Cp

| Player    | Team            | Season         | Round | TD   | Cp   | Int    | BH   | SI   | Ki   | MVP  | SPP  |
|-----------|-----------------|----------------|-------|------|------|--------|------|------|------|------|------|
| Cleve     | Badger Claws      | Green Cup VIII |    11 |    0 |    8 |      0 |    0 |    0 |    0 |    1 |   13 |
| Yosif.    | Glorious Hounds   | Green Cup VIII |    13 |    0 |    8 |      0 |    0 |    0 |    0 |    0 |    8 |
| Cleve     | Badger Claws      | Green Cup VIII |    13 |    0 |    7 |      0 |    0 |    0 |    0 |    0 |    7 |
| Hartwin.  | Arboreal Menace   | Green Cup X    |     4 |    0 |    7 |      0 |    0 |    0 |    0 |    0 |    7 |
| Elvis     | Old Wyrms         | Green Cup VIII |     8 |    0 |    7 |      0 |    0 |    0 |    0 |    1 |   12 |
| Elvis     | Old Wyrms         | Green Cup IX   |   253 |    0 |    7 |      0 |    0 |    0 |    0 |    0 |    7 |
| Nakayama. | Kaiju Dynamo      | Green Cup VIII |   253 |    1 |    7 |      0 |    0 |    0 |    0 |    0 |   10 |
| Melisa.   | Irregular Cogs    | Green Cup VIII |    15 |    0 |    7 |      0 |    0 |    0 |    0 |    0 |    7 |
| Klik      | Gargantuan Brutes | Green Cup IX   |     5 |    0 |    6 |      0 |    0 |    0 |    0 |    0 |    6 |
| Elvis     | Old Wyrms         | Green Cup IX   |    13 |    0 |    6 |      0 |    0 |    0 |    0 |    0 |    6 |

[[cleve]][[yosif]][[Hartwin]][[elvis]][[Nakayama]][[melisa]][[klik]]

# top 10 Cas

| Player    | Team            | Season         | Round | TD   | Cp   | Int    | BH   | SI   | Ki   | MVP  | SPP  |
|-----------|-----------------|----------------|-------|------|------|--------|------|------|------|------|------|
| Somfuhr.    | Filthy Tide       | Green Cup VIII       |    13 |    0 |    0 |      0 |    4 |    0 |    0 |    0 |    8 |
| Rohit.      | Zensun Vagabonds  | Green Cup VII        |    14 |    1 |    0 |      0 |    3 |    1 |    0 |    0 |   11 |
| Marzhak.    | Gargantuan Brutes | Green Cup VII        |    15 |    0 |    0 |      0 |    3 |    1 |    0 |    0 |    8 |
| Jantine     | Ravenous Eagles   | Green Cup X          |   251 |    0 |    0 |      0 |    3 |    1 |    0 |    0 |    8 |
| Somfuhr.    | Filthy Tide       | Green Cup VIII       |    11 |    0 |    0 |      0 |    2 |    2 |    0 |    0 |    8 |
| Pippin      | Badger Claws      | Green Cup X          |     7 |    0 |    0 |      0 |    2 |    0 |    1 |    0 |    6 |
| Marzhak.    | Gargantuan Brutes | Green Cup Classic 06 |     7 |    0 |    0 |      0 |    1 |    2 |    0 |    0 |    6 |
| Onesiphorus | Darkling Spectres | Green Cup VII        |     7 |    0 |    0 |      0 |    0 |    3 |    0 |    0 |    6 |
| Rohit.      | Zensun Vagabonds  | Green Cup VII        |     2 |    0 |    1 |      0 |    1 |    2 |    0 |    1 |   12 |
| Gention.    | Carcosan Tatters  | Green Cup X          |     3 |    0 |    0 |      0 |    3 |    0 |    0 |    0 |    6 |

[[somfuhr]][[rohit]][[marzhak]][[jantine]][[Pippin]][[Onesiphorous]][[Gention]]

# top 10 Int

| Player    | Team            | Season         | Round | TD   | Cp   | Int    | BH   | SI   | Ki   | MVP  | SPP  |
|-----------|-----------------|----------------|-------|------|------|--------|------|------|------|------|------|
| Yusra.      | Cackling Furies   | Green Cup VIII       |     1 |    0 |    3 |      3 |    0 |    0 |    0 |    0 |    9 |
| Mia         | Zensun Vagabonds  | Green Cup X          |     6 |    3 |    0 |      2 |    0 |    0 |    0 |    0 |   13 |
| Lars.       | Orbital Machine   | Green Cup Classic 06 |     3 |    0 |    0 |      2 |    0 |    0 |    0 |    0 |    4 |
| Olanrewaju  | Badger Claws      | Green Cup X          |    15 |    0 |    0 |      2 |    0 |    0 |    0 |    0 |    4 |
| Clydon      | Zensun Vagabonds  | Green Cup IX         |     6 |    0 |    3 |      2 |    0 |    0 |    0 |    0 |    7 |
| Ormonde.    | Zensun Vagabonds  | Green Cup VII        |    11 |    0 |    0 |      2 |    0 |    0 |    0 |    0 |    4 |
| Lucrece.    | Zensun Vagabonds  | Green Cup VIII       |     1 |    1 |    0 |      2 |    0 |    0 |    0 |    0 |    7 |
| KneeMasher. | Gore Farmers      | Green Cup VIII       |     5 |    1 |    1 |      2 |    0 |    0 |    0 |    0 |    8 |
| Jothi       | Orbital Machine   | Green Cup IX         |    14 |    1 |    0 |      2 |    0 |    0 |    0 |    1 |   12 |
| Erich       | Gargantuan Brutes | Green Cup Classic 06 |     7 |    1 |    1 |      2 |    0 |    0 |    0 |    0 |    8 |

[[yusra]][[Mia]][[lars]][[Erich]][[Jothi]]