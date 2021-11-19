# Arboreal Menace

The Arboreal Menace are the newest entries for the Green Cup competition, having won the third UBBL Challenge for their shot in GCX. They are passers and speedsters and are part of the slow wave of skillifying Pro-Level UBBL.

## Playbook

The Arboreal Menace use the Wary Eagle playbook, which is very similar to the Scrying Avian technique, but with slightly higher skilled (and more expensive to replace) players. The lineup includes four catchers, two blitzers and throwers that have more of an option of holding back and letting fly once the catchers are in position. The heavy on a Wary Eagle team is much less mobile than on a Scrying Avian but provides an anchor for the line.

## Playbook

## Active Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|
|    1 | Ingeborg | Thrower   |   45 |       3 |   22 |         1 | 150000 |     0 |
|    3 | Laurel   | Catcher   |  164 |       4 |   40 |         3 | 210000 |     0 |
|    4 | Attilla  | Catcher   |   90 |       7 |   47 |         3 | 200000 |     0 |
|    5 | Vusala   | Blitzer |   22 |       1 |   13 |         1 | 160000 |     0 |
|    6 | Sanja    | Blitzer |   79 |       7 |   43 |         3 | 240000 |     0 |
|    7 | Bishop   | Line   |   19 |       4 |   18 |         1 | 110000 |     0 |
|    8 | Chantrea | Line   |   40 |       7 |   50 |         3 | 170000 |     0 |
|    9 | Iago     | Line   |   20 |       7 |   47 |         3 | 130000 | 20000 |
|   10 | Joona    | Line   |   22 |       7 |   50 |         3 | 110000 |     0 |
|   11 | Priyanka | Line   |   19 |       7 |   51 |         3 | 120000 |     0 |
|   13 | Unnr     | Line   |    9 |       7 |   42 |         3 | 110000 | 20000 |
|   14 | Georgina | Catcher   |  162 |       7 |   46 |         3 | 230000 |     0 |
|   15 | Dawa     | Catcher   |   17 |       1 |   10 |         1 | 130000 |     0 |
|   16 | Borarinn | Heavy   |   49 |       5 |   44 |         3 | 180000 |     0 |


### Depth (on payroll)

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|


### Non Roster

| # | Player    | Position  | SPP | Seasons | GP | Contracts | Value | Bonus |
|---|-----------|-----------|-----|---------|----|-----------|-------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, sum(mp.spp) AS 'SPP', count(DISTINCT mp.f_trid) AS Seasons, sum(mp.played) AS "GP", ROUND(sum(mp.played)/15) AS Contracts, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id WHERE pl.f_tname = "Arboreal Menace" GROUP BY pl.name HAVING pl.name NOT LIKE '%.' ORDER BY pl.nr ASC;
```

## Records

### Record by Division (W-D-L)

```
SELECT teams.name, divisions.name, sum(mr.won) AS W, sum(mr.draw) AS D, sum(mr.lost) AS L, sum(mr.played) AS GP, avg(mr.win_pct) AS "Win%", sum(mr.gf) AS GF, sum(mr.ga) AS GA, sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN divisions ON mr.f_did = divisions.did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Arboreal Menace" GROUP BY teams.name, mr.f_did ORDER BY sum(mr.won) DESC limit 3;
```

6-2-8

### UBBL Record (W-D-L)
```
SELECT teams.name, sum(mr.won), sum(mr.draw), sum(mr.lost), sum(mr.played), avg(mr.win_pct), sum(mr.gf), sum(mr.ga), sum(mr.tcasf), sum(mr.tcdiff), sum(mr.ff) FROM mv_teams AS mr JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Arboreal Menace" GROUP BY teams.name ORDER BY sum(mr.won) DESC limit 3;
```
19-3-14

### Prizes

* UBBL Challenge III - UBBL Pennant [[team1stplace]]
* Green Cup XI - Outlands Division Champions [[teamdivision#gcxi]]

### Seasons

| Team      | Season             | W | D | L | GP | Win% | GF | GA | Cas | CDif | FF |
|-----------|--------------------|--:|--:|--:|---:|-----:|---:|---:|----:|-----:|---:|
| Arboreal Menace | StUBBL Scramble    |    1 |    0 |    0 |      1 |     100.00 |    3 |    0 |    1 |      2 |    1 |
| Arboreal Menace | UBBL Challenge III |    6 |    1 |    0 |      7 | 92.86 |   30 |   14 |   10 |      3 |    2 |
| Arboreal Menace | UBBL Challenge IV  |    3 |    0 |    1 |      4 |      75.00 |   12 |    5 |    2 |     -5 |    3 |
| Arboreal Menace | UBBL Challenge II  |    3 |    0 |    2 |      5 |      60.00 |   14 |    7 |    6 |     -5 |    1 |
| Arboreal Menace | Green Cup X        |    6 |    2 |    8 |     16 |   43.75 |   41 |   51 |   15 |    -15 |   -3 |
| Arboreal Menace | UBBL Challenge     |    0 |    0 |    3 |      3 |       0.00 |    3 |    7 |    0 |     -6 |    0 |

```
SELECT teams.name AS Team, tours.name AS Season, mr.won, mr.draw, mr.lost, 	mr.played, mr.win_pct, mr.gf, mr.ga, mr.cas, mr.tcdiff,	mr.ff FROM mv_teams AS mr JOIN tours ON mr.f_trid = tours.tour_id and mr.f_did = tours.f_did JOIN teams ON teams.team_id = mr.f_tid WHERE teams.name = "Arboreal Menace" ORDER BY mr.win_pct DESC limit 16;
```

## History

### Seasons

The Arboreal Menace began their existence with three straight losses in the first UBBL Challenge (against the [Mules](mules), [Machine](orbitalmachine) and [Eagles](ravenouseagles)).

In UBBL Challenge II they did much better against the bruising style of play, getting to the Quarter-finals which they lost to the eventual tournament winners the [Gargantuan Brutes](gargantuanbrutes). They lost again to the [Mules](mules) this season.

The Third UBBL Challenge was the Arboreal Menace's clear crowning achievement thus far. They won the entire tournament in undefeated fashion with a 6-win run after an opening match draw against the [Gladiolas](gladiolas).

Coming into GCX on a high, the Menace won early, but couldn't keep things under control through a long season. They ended up in last place in the Outlands division (and would have needed to beat the eventual GCX champions in week 15 to have made the playoffs).

The fourth UBBL Challenge saw a return to form where they easily made the quarterfinals against Open Division competition but couldn't advance further.

#### Projection GCXI

W-D-L 8-1-6

Current projections have them battling the [Tatters](carcosantatters) for third place in the Outlands. They are bringing a more experienced roster into GCXI and it's possible they can hang in there with a very tough division.

#### roster by season

```
SELECT pl.nr, pl.name AS Player, count(md.f_match_id) AS GP, sum(mx.catches) + sum(mx.pickups) + sum(md.intcpt) + sum(mx.handoff_catches) AS Touches, sum(md.td) AS TD, sum(mx.rushing_distance_move) AS Rsh, sum(md.cp) AS Cp, sum(mx.pass_distance) AS CpDst, sum(mx.catches) AS Ctch, sum(md.intcpt) AS "Int", sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blk, sum(mx.inflicted_sacks) AS Sck, sum(md.mvp) AS MVP, sum(mx.interceptions_thrown) AS Intercepted, sum(mx.sustained_sacks) AS Sacked, sum(mx.sustained_kos) AS KOed, sum(mx.sustained_bhs) AS Hurt, sum(mx.sustained_sis) AS Injured, sum(mx.sustained_kill) AS Killed, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON md.f_tour_id = tours.tour_id AND md.f_did = tours.f_did WHERE tours.name = "Green Cup XI" AND pl.f_tname = "Arboreal Menace" GROUP BY pl.name, pl.nr ORDER BY pl.nr ASC;
```

### Stars

> **Currently active players** are highlighted and modern-era players whose careers are over are not marked.

| Player           | Team        | Position      | W | D | L | GP | TD | Cp | Int | BH | SI | Ki | MVP | SPP |
|------------------|-------------|---------------|--:|--:|--:|---:|---:|---:|----:|---:|---:|---:|----:|----:|
| **Georgina**  | Arboreal Menace | Catcher   |   15 |    2 |   13 |   30 |   24 |    8 |    8 |    0 |    0 |    0 |    3 |  111 |
| Hartwin  | Arboreal Menace | Thrower   |   13 |    3 |    9 |   25 |    0 |   65 |    2 |    0 |    1 |    0 |    2 |   81 |
| **Laurel**    | Arboreal Menace | Catcher   |   11 |    2 |    8 |   21 |   17 |    0 |    1 |    0 |    0 |    0 |    2 |   63 |
| **Attilla**   | Arboreal Menace | Catcher   |   15 |    3 |   13 |   31 |   16 |    6 |    0 |    0 |    1 |    0 |    1 |   61 |
| **Sanja**     | Arboreal Menace | Blitzer |   14 |    2 |   13 |   29 |   12 |    2 |    0 |    0 |    4 |    0 |    2 |   56 |
| **Kropotkin** | Arboreal Menace | Blitzer |   15 |    3 |   10 |   28 |    6 |    0 |    0 |    2 |    4 |    0 |    3 |   45 |
| **Nitika**    | Arboreal Menace | Catcher   |    7 |    2 |    8 |   17 |   13 |    2 |    1 |    0 |    0 |    0 |    0 |   43 |
| **Borarinn**  | Arboreal Menace | Heavy   |   14 |    3 |    9 |   26 |    0 |    0 |    0 |    9 |    2 |    1 |    2 |   34 |
| **Chantrea**  | Arboreal Menace | Line   |   16 |    2 |   13 |   31 |    1 |    0 |    0 |    1 |    1 |    0 |    5 |   32 |
| **Susila**    | Arboreal Menace | Thrower   |    4 |    2 |    8 |   14 |    0 |   21 |    0 |    0 |    0 |    0 |    1 |   26 |
| **Iago**      | Arboreal Menace | Line   |   14 |    3 |   13 |   30 |    2 |    4 |    0 |    0 |    0 |    0 |    2 |   20 |

```
SELECT pl.name AS Player, pl.f_pos_name AS Position, sum(mp.won) AS won, sum(mp.draw) AS draw, sum(mp.lost) AS lost, sum(mp.played) AS GP, sum(mp.td) AS TD, sum(mp.cp) AS Cp, sum(mp.intcpt) AS "Int",	sum(mp.bh) AS BH, sum(mp.si) AS SI,	sum(mp.ki) AS Ki, sum(mp.mvp) AS MVP, sum(mp.spp) AS SPP FROM mv_players AS mp JOIN players AS pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN tours ON mp.f_trid = tours.tour_id AND mp.f_did = tours.f_did WHERE pl.f_tname = "Arboreal Menace" GROUP BY pl.name, pl.f_tname, pl.f_pos_name ORDER BY SPP DESC limit 11;
```

[[georgina]] won the StUBBL Jumper for UBBL Challenge III. They have amazingly soft hands and there are a few rumblings that they're gunning for the Pro Interception record.

[[Hartwin]] was primarily a backfield passer, though she had the arm for it, she didn't go the extreme long-passing route of a [[yosif]] or the deceased [[Adam]] (or [[Ozymandias]] for the old school). The anticipation that in the Green Cup she'd need a backup did come true, and [[susila]] is now working his way up the skill tree.

[[laurel]] and [[Attilla]] are both remarkably good catchers but neither has made themselves part of the larger superstar picture in their first Green Cup campaign.

#### Award Winners

| #    | Player   | Position | Seasons | Prizes | Value  | Bonus |
|------|----------|----------|---------|--------|--------|-------|

```
SELECT pl.nr AS "#", pl.name AS Player, pl.f_pos_name AS Position, count(DISTINCT mp.f_trid) AS Seasons, count(DISTINCT hof.hof_id) AS Prizes, pl.value AS Value, pl.extra_val AS Bonus FROM mv_players as mp JOIN players as pl ON mp.f_pid = pl.player_id AND mp.f_tid = pl.owned_by_team_id JOIN hof ON pl.player_id = hof.pid WHERE pl.f_tname = "Arboreal Menace" GROUP BY pl.name ORDER BY pl.nr ASC;
```

### Management

Criton Corp is an upspire entity.

### Fans

As the Arboreal Menace have only completed their first Pro-Level season they don't have a lot of long-standing rivalries. Among Open-Level teams they bumped heads most with [Thorns](thorns) fans. In the Green Cup their natural rivals are the [Badger Claws](badgerclaws), who not only share their division (and use a similar fragile speedster playbook), but are also upstarts who've been promoted from Open-Division play and are eager to be the first to win the coveted Cup.

### Famous Games

None yet.