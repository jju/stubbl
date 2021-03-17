# week XX

## matchups

## standings

## player of the week standings

```
SELECT pl.name AS Player, pl.f_tname AS Team, tours.name AS Season, sum(md.td) AS TDs, sum(mx.rushing_distance_move) AS Rush, sum(md.cp) AS Cp,	sum(mx.pass_distance) AS PassDist, sum(mx.catches) AS Caught, sum(md.intcpt) AS Picks, sum(md.bh) + sum(md.si) + sum(md.ki) AS Cas, sum(mx.inflicted_blocks) AS Blocks, sum(mx.inflicted_sacks) AS Sacks, sum(md.mvp) AS MVPs, (sum(md.td) * 3) + sum(md.cp) + (sum(md.intcpt) * 2) + (sum(md.bh) * 2) + (sum(md.si) * 2) + (sum(md.ki) * 2) + (sum(md.mvp) * 5) AS SPP FROM match_data AS md JOIN match_data_es AS mx ON md.f_player_id = mx.f_pid AND md.f_match_id = mx.f_mid JOIN players AS pl ON md.f_player_id = pl.player_id AND md.f_team_id = pl.owned_by_team_id JOIN matches AS mt ON mt.match_id = md.f_match_id JOIN tours ON mt.f_tour_id = tours.tour_id WHERE tours.name = "Green Cup Classic 06" AND mt.round = 1 GROUP BY pl.name, pl.f_tname ORDER BY SPP DESC LIMIT 10;
```

## season leaderboards

### mvp

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

Top 5

### TDs

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

Top 3

### passing

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

Top 3

### rushing

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

### catches

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

### casualties

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

### sacks

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

### blocks

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|

### mvps

| Player            | Team             | TDs  | Rush | Cp   | PassDist | Caughts | Cas  | Blocks | Sacks | MVPs | SPP  |
|-------------------|------------------|------|------|------|----------|---------|------|--------|-------|------|------|
