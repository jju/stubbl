# green cup all-stars

A Green Cup All-Star is a player who is in the top 16 players ranked by SPP in a given season.

```
SELECT pl.name AS Player, pl.f_tname AS Team, count(md.f_match_id) AS GP, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 16;
```

## gcxi

| Player | Team         | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|

 

## gcx

| Player | Team         | GP | TD | Rsh | Cp | CpDst | Ctch | Int | Cas | Blk | Sck | MVP | SPP |
|--------|--------------|---:|---:|----:|---:|------:|-----:|----:|----:|----:|----:|----:|----:|
| [[Aeson]]     | Badger Claws      | 17 |   52 |  645 |    0 |     0 |   40 |    0 |    0 |    0 |    0 |    3 |  171 |
| [[Venus]]     | Filthy Tide       | 14 |   35 |  489 |    0 |     0 |   33 |    0 |    0 |    2 |    0 |    3 |  120 |
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

1.  [[aeson]]
2.  [[souta]]
3.  [[costache]]
4.  [[sabah]]
5.  [[alexandros]]
6.  [[Elvis]]
7.  [[atte]]
8.  [[shay]]
9.  [[amador]]
10.  [[besz]]
11.  [[Filipa]]
12.  [[jantine]]
13.  [[Aronne]]
14.  [[Betul]]
15.  [[Udo]]
16.  [[Sparrow]]

## gcviii

1. [[costache]]
2. [[aeson]]
3. [[donat]]
4. [[sabah]]
5. [[nakayama]]
6. [[somfuhr]]
7. [[Filipa]]
8. [[Gention]]
9. [[Lucrece]]
10. [[cleve]]
11. [[roni]]
12. [[kneemasher]]
13. [[elvis]]
14. [[Ioana]]
15. [[toomsii]]
16. [[Tomer]]

## gcvii

1. [[Yakup]]
2. [[Oiva]]
3. [[Rohit]]
4. [[Saxa]]
5. [[Souta]]
6. [[Bill]]
7. [[Besz]]
8. [[Mako]]
9. [[Kota]]
10. [[Dragos]]
11. [[ToomsII]]
12. [[Mandawuy]]
13. [[Bahiyya]]
14. [[Yosif]]
15. [[Heep]]
16. [[Olufunmi]]