# green cup all-stars

A Green Cup All-Star is a player who is in the top 16 players ranked by SPP in a given season.

```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 16;
```

## gcxi


| Player    | Team              | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|-----------|-------------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| [[Veens]] | Filthy Tide       | 18 |   69 |  770 |    1 |     3 |   47 |    0 |    0 |    1 |    1 |    1 |  213 |
| Ziba    | Glorious Hounds   | 19 |   63 |  739 |    2 |     0 |   58 |    2 |    0 |    9 |    1 |    3 |  210 |
| Laurel  | Arboreal Menace   | 18 |   34 |  519 |    0 |     0 |   42 |    1 |    0 |    1 |    0 |    1 |  109 |
| Frans   | Irregular Cogs    | 17 |   19 |  241 |    4 |     9 |   24 |    5 |    1 |   36 |    0 |    1 |   78 |
| Koralo  | Eldritch Fatality | 15 |   12 |  223 |   19 |    11 |   22 |    0 |    2 |   14 |    0 |    2 |   69 |
| Klim    | Badger Claws      | 12 |   19 |  267 |    0 |     0 |   19 |    0 |    0 |    2 |    2 |    2 |   67 |
| Luanna. | Cackling Furies   | 16 |    1 |  204 |   54 |   221 |    0 |    1 |    0 |   15 |    0 |    1 |   64 |
| Betuel  | Zensun Vagabonds  | 16 |    0 |  197 |   51 |   231 |    2 |    0 |    3 |   10 |    1 |    1 |   62 |
| Oxana   | Glorious Hounds   | 18 |    0 |  234 |   54 |   195 |    3 |    1 |    0 |   19 |    0 |    1 |   61 |
| Filipa  | Eldritch Fatality | 18 |    1 |  247 |   47 |   134 |    2 |    2 |    0 |   12 |    1 |    1 |   59 |
| Padma   | Zensun Vagabonds  | 16 |   18 |  230 |    0 |     0 |   22 |    0 |    1 |   46 |    1 |    0 |   56 |
| Ravil   | Glorious Hounds   | 13 |    6 |   71 |    4 |     4 |    9 |    0 |    0 |   20 |    4 |    6 |   52 |
| Ayane   | Eldritch Fatality | 14 |   14 |   91 |    1 |     3 |   10 |    0 |    2 |   55 |    6 |    1 |   52 |
| Arya    | Carcosan Tatters  | 16 |   12 |  165 |    3 |     4 |   14 |    0 |    1 |   54 |    2 |    2 |   51 |
| Merlyn. | Irregular Cogs    | 13 |    8 |  231 |   18 |    19 |   21 |    1 |    1 |   26 |    5 |    1 |   51 |
| Aeson.  | Badger Claws      |  8 |   17 |  231 |    0 |     0 |   15 |    0 |    0 |    3 |    0 |    0 |   51 |

 

## gcx

| Player | Team         | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| [[Aeson]]     | Badger Claws      | 17 |   52 |  645 |    0 |     0 |   40 |    0 |    0 |    0 |    0 |    3 |  171 |
| [[Veens]]     | Filthy Tide       | 14 |   35 |  489 |    0 |     0 |   33 |    0 |    0 |    2 |    0 |    3 |  120 |
| [[Atte]]      | Eldritch Fatality | 15 |   26 |  307 |    2 |     5 |   32 |    0 |    1 |   30 |    0 |    1 |   87 |
| [[Padma]]     | Zensun Vagabonds  | 17 |   22 |  237 |    1 |     0 |   21 |    0 |    5 |   49 |    2 |    2 |   87 |
| [[Shashi]]    | Cackling Furies   | 17 |   21 |  188 |    0 |     0 |   23 |    0 |    1 |   41 |    0 |    3 |   80 |
| [[Seosamh]]   | Old Wyrms         | 19 |   18 |  203 |    2 |    12 |   24 |    1 |    2 |   43 |    1 |    3 |   77 |
| [[Merlyn]]    | Irregular Cogs    | 17 |    9 |  256 |   24 |    50 |   14 |    1 |    0 |    9 |    1 |    3 |   68 |
| [[Luanna]]    | Cackling Furies   | 16 |    1 |  115 |   41 |   167 |    3 |    0 |    2 |   18 |    0 |    3 |   63 |
| [[Ziba]]      | Glorious Hounds   | 13 |   15 |  189 |    1 |     2 |   17 |    0 |    1 |    8 |    0 |    3 |   63 |
| [[Aemulus]]   | Gore Farmers      | 17 |   13 |  192 |    4 |     9 |   25 |    1 |    2 |   46 |    3 |    2 |   59 |
| [[Modest]]    | Old Wyrms         | 18 |   15 |  129 |    4 |     7 |   20 |    0 |    0 |   53 |    0 |    2 |   59 |
| [[Costache]] | Glorious Hounds   | 15 |   14 |  183 |    0 |     0 |   20 |    2 |    3 |   41 |    4 |    1 |   57 |
| [[Gojko]]    | Darkling Spectres | 14 |    5 |  242 |   23 |    54 |    2 |    1 |    0 |   19 |    3 |    3 |   55 |
| [[Betuel]]    | Zensun Vagabonds  | 17 |    2 |  186 |   32 |   125 |    0 |    0 |    1 |   11 |    1 |    3 |   55 |
| [[Ruslan]]    | Orbital Machine   | 16 |    8 |  211 |    4 |    11 |    6 |    0 |    6 |   32 |    3 |    3 |   55 |
| [[Consolo]]   | Badger Claws      | 17 |    0 |  200 |   33 |    74 |    2 |    1 |    0 |   17 |    1 |    4 |   55 |



## gcix

| Player | Team         | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Aeson.      | Badger Claws      | 18 |   59 |  795 |    1 |     1 |   48 |    0 |    0 |    1 |    0 |    5 |  203 |
| Souta.      | Old Wyrms         | 14 |   30 |  396 |   16 |     1 |   49 |    2 |    0 |   21 |    1 |    3 |  125 |
| Sabah.      | Kaiju Dynamo      | 15 |   27 |  369 |    0 |     0 |   14 |    0 |    0 |    1 |    0 |    0 |   81 |
| Costache.   | Glorious Hounds   | 15 |   25 |  204 |    1 |     1 |   21 |    0 |    0 |   20 |    0 |    1 |   81 |
| Alexandros. | Irregular Cogs    | 15 |    8 |  265 |   30 |    65 |   19 |    0 |    0 |    2 |    0 |    4 |   74 |
| Elvis.      | Old Wyrms         | 17 |    0 |  175 |   64 |   302 |    0 |    0 |    0 |   10 |    2 |    1 |   69 |
| Atte.       | Eldritch Fatality | 19 |   14 |  161 |    1 |     2 |   16 |    0 |    0 |   47 |    3 |    5 |   68 |
| Shay        | TC Sump Runners   | 15 |   11 |  222 |   16 |    44 |   10 |    0 |    1 |   24 |    0 |    3 |   66 |
| Amador      | Old Wyrms         | 17 |   12 |  221 |   15 |     0 |   32 |    0 |    2 |   39 |    4 |    2 |   65 |
| Besz.       | Irregular Cogs    | 16 |    7 |  296 |   36 |    70 |   11 |    0 |    1 |    9 |    0 |    0 |   59 |
| Filipa      | Eldritch Fatality | 18 |    2 |  287 |   44 |   141 |    4 |    1 |    0 |    6 |    1 |    1 |   57 |
| Jantine.    | Ravenous Eagles   | 16 |    0 |    5 |    0 |     0 |    0 |    0 |   25 |  168 |    0 |    1 |   55 |
| Udo         | Glorious Hounds   | 18 |    8 |  195 |   14 |    19 |   25 |    0 |    1 |   36 |    3 |    3 |   55 |
| Aronne      | Cackling Furies   | 16 |   12 |  219 |    7 |     4 |   22 |    1 |    0 |   36 |    1 |    2 |   55 |
| Betul       | Eldritch Fatality | 12 |   11 |   96 |    3 |     6 |    9 |    2 |    0 |   27 |    3 |    3 |   55 |
| Sparrow     | Carcosan Tatters  | 16 |   13 |  149 |    1 |     0 |   13 |    1 |    1 |   30 |    0 |    2 |   54 |



## gcviii

| Player | Team         | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Costache.   | Glorious Hounds   | 16 |   35 |  215 |    2 |    -3 |   31 |    0 |    0 |   26 |    2 |    1 |  112 |
| Aeson.      | Badger Claws      | 19 |   27 |  358 |    1 |     0 |   28 |    0 |    0 |    2 |    0 |    1 |   87 |
| Donat.      | Badger Claws      | 19 |   26 |  330 |    1 |     6 |   22 |    0 |    1 |    7 |    0 |    0 |   81 |
| Sabah.      | Kaiju Dynamo      | 18 |   25 |  308 |    0 |     0 |   12 |    0 |    0 |    5 |    0 |    0 |   75 |
| Nakayama.   | Kaiju Dynamo      | 18 |   12 |  367 |   16 |    47 |    0 |    1 |    1 |    6 |    0 |    2 |   66 |
| Somfuhr.    | Filthy Tide       | 17 |    0 |    0 |    0 |     0 |    0 |    0 |   24 |  151 |    4 |    2 |   58 |
| Filipa      | Eldritch Fatality | 15 |    5 |  190 |   25 |    92 |    4 |    0 |    1 |    8 |    0 |    3 |   57 |
| Gention.    | Carcosan Tatters  | 18 |    8 |   73 |    0 |     0 |    3 |    0 |    4 |   47 |    1 |    5 |   57 |
| Lucrece.    | Zensun Vagabonds  | 14 |   10 |  124 |    2 |     8 |    9 |    2 |    0 |   17 |    0 |    4 |   56 |
| Cleve.      | Badger Claws      | 18 |    0 |  205 |   45 |   127 |    1 |    0 |    0 |   21 |    0 |    2 |   55 |
| Roni        | Old Wyrms         | 16 |    9 |  166 |   11 |    14 |   23 |    3 |    0 |   49 |    4 |    2 |   54 |
| KneeMasher. | Gore Farmers      | 18 |    9 |  157 |    5 |    21 |   11 |    6 |    4 |   68 |    2 |    0 |   52 |
| Elvis.      | Old Wyrms         | 15 |    0 |   99 |   37 |   164 |    2 |    0 |    0 |    5 |    0 |    3 |   52 |
| ToomsII.    | Darkling Spectres | 15 |    5 |  264 |   21 |    70 |    1 |    0 |    1 |   18 |    2 |    2 |   48 |
| Tomer       | Filthy Tide       | 17 |   11 |  166 |    0 |     0 |   12 |    0 |    0 |   14 |    1 |    3 |   48 |
| Ioana.      | Orbital Machine   | 14 |    2 |   16 |    0 |     0 |    0 |    2 |    9 |  144 |    0 |    4 |   48 |


## gcvii
| Player | Team         | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Yakup.    | Filthy Tide       | 17 |   26 |  349 |    0 |     0 |   25 |    0 |    0 |    2 |    0 |    1 |   83 |
| Oiva.     | Glorious Hounds   | 16 |   15 |  267 |   11 |     1 |   25 |    6 |    0 |   29 |    3 |    2 |   78 |
| Rohit.    | Zensun Vagabonds  | 16 |    3 |   31 |    1 |     5 |    2 |    1 |   25 |  125 |   10 |    3 |   77 |
| Saxa.     | Irregular Cogs    | 17 |   13 |  130 |    6 |    15 |    9 |    3 |    0 |   33 |    1 |    2 |   61 |
| Souta.    | Old Wyrms         | 15 |   16 |  172 |   11 |    -5 |   28 |    1 |    0 |   25 |    1 |    0 |   61 |
| Bill.     | Eldritch Fatality | 17 |    1 |  199 |   36 |   137 |    5 |    0 |    1 |   10 |    0 |    4 |   61 |
| Besz.     | Irregular Cogs    | 18 |    7 |  279 |   24 |    81 |   10 |    0 |    0 |    9 |    0 |    3 |   60 |
| Mako.     | Kaiju Dynamo      | 17 |   11 |  271 |   20 |    33 |    0 |    2 |    0 |    4 |    0 |    0 |   57 |
| Kota.     | Cackling Furies   | 16 |   12 |  123 |    1 |    -1 |    9 |    0 |    1 |   20 |    0 |    3 |   54 |
| Dragos.   | Irregular Cogs    | 17 |   14 |  114 |    3 |     0 |   12 |    1 |    0 |   40 |    1 |    1 |   52 |
| Mandawuy. | Glorious Hounds   | 15 |   13 |   93 |    3 |     2 |   10 |    1 |    1 |   50 |    3 |    1 |   51 |
| ToomsII.  | Darkling Spectres | 19 |    4 |  288 |   29 |    87 |    1 |    0 |    0 |   10 |    0 |    2 |   51 |
| Yosif.    | Glorious Hounds   | 17 |    1 |  147 |   40 |   249 |    2 |    0 |    0 |    5 |    1 |    1 |   48 |
| Heep.     | Orbital Machine   | 17 |   11 |  221 |    3 |    -3 |   18 |    3 |    3 |   34 |    1 |    0 |   48 |
| Bahiyya.  | Zensun Vagabonds  | 16 |   14 |  123 |    0 |     0 |   11 |    0 |    3 |   33 |    3 |    0 |   48 |
| Olufunmi. | Darkling Spectres | 19 |   14 |  149 |    2 |     1 |   18 |    1 |    1 |   37 |    1 |    0 |   48 |




# orange goblet all-stars

## ogiii

| Player  | Team              | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|---------|-------------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Marques    | Palace Orchids   | 11 |   14 |  226 |    3 |     5 |   20 |    3 |    2 |   22 |    3 |    1 |   60 |
| Marita     | Deep Dreamers    | 13 |   13 |  164 |    3 |     7 |   13 |    3 |    0 |    2 |    0 |    1 |   53 |
| Kassandros | Magpies          | 11 |   10 |  145 |    0 |     0 |   14 |    0 |    1 |   15 |    1 |    4 |   52 |
| Krister    | Deep Dreamers    | 13 |    7 |  122 |   13 |    36 |    6 |    3 |    0 |    3 |    1 |    2 |   50 |
| Pilvi      | Mules            | 13 |    9 |  171 |    2 |     5 |    0 |    0 |    2 |   32 |    1 |    1 |   38 |
| Amata      | Vanadium Hunters | 11 |    4 |  124 |    8 |    -2 |   17 |    1 |    1 |    9 |    1 |    2 |   34 |
| Eufemia    | Palace Orchids   | 11 |    1 |  105 |   31 |   106 |    1 |    0 |    0 |   12 |    2 |    0 |   34 |
| Karpos     | Palace Orchids   | 11 |    3 |   25 |    0 |     0 |    1 |    1 |    1 |   52 |    0 |    4 |   33 |
| Zahida     | Vanadium Hunters | 11 |    0 |  116 |   25 |    93 |    0 |    0 |    1 |    7 |    2 |    1 |   32 |
| Debbie     | Hoods            | 11 |    6 |  186 |    9 |    24 |    8 |    2 |    0 |   18 |    0 |    0 |   31 |
| Umut       | Mules            |  8 |    6 |  108 |    1 |     4 |    2 |    0 |    1 |    9 |    1 |    2 |   31 |
| Mawunyo    | Mules            | 13 |    7 |   70 |    0 |     0 |    2 |    1 |    1 |   40 |    0 |    1 |   30 |
| Jolanda.   | Magpies          |  9 |    9 |   99 |    1 |    10 |    9 |    0 |    1 |   27 |    0 |    0 |   30 |
| Waltraut   | Raptors          | 12 |    6 |  115 |    1 |    -1 |    0 |    0 |    0 |    5 |    0 |    2 |   29 |
| Hursit     | Warthogs         | 10 |    4 |  162 |   16 |    62 |    0 |    0 |    0 |    8 |    0 |    0 |   28 |
| Borgisl    | Palace Orchids        |  7 |    7 |   75 |    2 |     2 |    9 |    0 |    0 |    9 |    0 |    1 |   28 |

## ogii

| Player  | Team              | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|---------|-------------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Mihael.   | Deep Dreamers    | 12 |   10 |  178 |    5 |    25 |   12 |    5 |    1 |    4 |    0 |    1 |   52 |
| Euri      | Palace Orchids   |  8 |   14 |  141 |    2 |     0 |   11 |    0 |    1 |   11 |    0 |    1 |   51 |
| Francine. | Raptors          | 12 |    8 |  178 |    8 |    16 |    0 |    0 |    0 |    4 |    1 |    2 |   42 |
| Ella      | Raptors          | 10 |   12 |  165 |    1 |     0 |    5 |    0 |    0 |    2 |    0 |    1 |   42 |
| Barbro    | Palace Orchids   |  7 |   12 |  129 |    0 |     0 |   13 |    1 |    0 |   16 |    2 |    0 |   38 |
| Nor       | Geometers        |  9 |   10 |  153 |    0 |     0 |    9 |    0 |    1 |   13 |    2 |    1 |   37 |
| Juozas    | Palace Orchids   | 10 |    9 |   67 |    2 |     3 |    8 |    0 |    0 |   16 |    2 |    1 |   34 |
| Nahor     | Thrillers        | 10 |    8 |   77 |    1 |     3 |    4 |    1 |    0 |   50 |    0 |    1 |   32 |
| Marita    | Deep Dreamers    | 11 |    4 |   66 |    1 |     3 |    6 |    2 |    0 |    5 |    0 |    3 |   32 |
| Gautstafr | Vanadium Hunters |  6 |    6 |   88 |    2 |     5 |    8 |    1 |    0 |    2 |    1 |    2 |   32 |
| Amata     | Vanadium Hunters |  9 |    8 |  129 |    5 |     0 |   16 |    0 |    1 |    7 |    0 |    0 |   31 |
| Ragu.     | Warthogs         | 11 |   10 |  159 |    1 |     4 |   18 |    0 |    0 |    4 |    1 |    0 |   31 |
| Eufemia   | Palace Orchids   | 12 |    1 |  124 |   25 |   123 |    4 |    0 |    1 |    9 |    2 |    0 |   30 |
| Tamara    | Thorns           |  8 |    7 |  103 |    2 |     5 |   11 |    0 |    0 |   15 |    2 |    1 |   28 |
| Omiros    | Warthogs         |  8 |    7 |   60 |    0 |     0 |    2 |    0 |    1 |   30 |    2 |    1 |   28 |
| Mariyka.  | Thrillers        |  7 |    6 |  142 |    3 |    11 |    6 |    0 |    0 |    4 |    0 |    1 |   26 |

## ogi

| Player  | Team              | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|---------|-------------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| Achille.    | Thorns           | 13 |   13 |  173 |    8 |   -11 |   22 |    0 |    1 |   37 |    4 |    2 |   59 |
| Eufemia     | Palace Orchids   | 12 |    1 |  139 |   34 |   160 |    2 |    0 |    0 |    7 |    1 |    3 |   52 |
| Nkosana     | Mules            | 13 |   12 |  219 |    3 |    12 |   13 |    1 |    1 |   20 |    2 |    0 |   43 |
| Joukahainen | Palace Orchids   | 11 |   13 |  127 |    1 |     1 |   16 |    0 |    1 |   23 |    3 |    0 |   42 |
| Nanna.      | Thrillers        | 11 |    5 |  203 |   15 |    34 |    1 |    2 |    0 |   11 |    0 |    1 |   39 |
| Signe       | Hoods            | 10 |    0 |   17 |    2 |     1 |    0 |    0 |    7 |   71 |    6 |    4 |   36 |
| Amata       | Vanadium Hunters | 11 |    9 |  122 |    2 |     8 |   10 |    1 |    0 |   18 |    2 |    1 |   36 |
| Barbro      | Palace Orchids   | 11 |    9 |  132 |    1 |     2 |   13 |    0 |    1 |   18 |    0 |    1 |   35 |
| Bianka      | Mules            | 12 |    5 |  180 |   13 |    28 |    1 |    0 |    1 |   15 |    0 |    1 |   35 |
| Gautstafr   | Vanadium Hunters | 11 |   10 |  122 |    1 |    -2 |   14 |    2 |    0 |    6 |    1 |    0 |   35 |
| Balwinder   | Thorns           | 13 |    1 |  117 |   26 |    84 |    0 |    0 |    0 |    8 |    1 |    1 |   34 |
| Daphnee     | Thorns           | 13 |    0 |    4 |    2 |    14 |    1 |    0 |    1 |   32 |    2 |    5 |   29 |
| Hildefons.  | Thorns           | 10 |    5 |   53 |    1 |     0 |    8 |    1 |    2 |   27 |    0 |    1 |   27 |
| Katka       | Hoods            | 10 |    0 |    0 |    0 |     0 |    0 |    0 |   13 |  104 |    1 |    0 |   26 |
| Shantanu    | Thrillers        | 11 |    6 |   50 |    0 |     0 |    4 |    1 |    3 |   88 |    1 |    0 |   26 |
| Nagendra    | Thrillers        | 10 |    5 |  141 |    1 |     1 |    8 |    0 |    0 |    4 |    1 |    2 |   26 |
