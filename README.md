Premier League Match Results: What Drives Them, and How Good Are Bookmaker Odds?

Live dashboard: (https://public.tableau.com/app/profile/s.m.shawkat.jamil/viz/EPLMatchResultsandBookmakerCalibration/Overview)

Question
What drives Premier League results (home advantage, shots, fouls and cards, team strength), and how well do bookmaker odds reflect what actually happens?

Data
- Source: Football-Data.co.uk, English Premier League, seasons 2016/17 to 2025/26 (10 seasons, 3,800 matches).
- Fields used: results, shots, shots on target, fouls, cards, corners, referee, and Bet365 odds.
- Data is open and match-level; no personal data is involved. Credit to Football-Data.co.uk.

Tools and process
1. Power BI (Power Query): combined 10 CSVs, kept 22 columns, fixed dates (UK format), trimmed text, built calculated columns (TotalGoals, GoalDiff, points, home win), and converted bookmaker odds to probabilities (1/odds, normalised by the overround so they sum to 100%).
2. Power BI (DAX measures): validation checks (total rows, result vs goals mismatches, negative values, 380 matches per season).
3. Team-level table: each match reshaped to two rows (home and away team) for team analysis (7,600 rows).
4. Tableau Public: 4 dashboards (Overview, Teams, Discipline and shots, Bookmakers).

Key findings
1. Home Win = 44.6%, Draw = 23.2%, Away Win = 32.2%.
2. Season with highest Home Team Winrate was in the season 2016/17 with 49.2%, Season with lowest Home Team Winrate was in the season 2020/21 with 37.9%.
3. Top team by points per game was Man City(2.28), bottom team by points per game was Norwich(0.57).
4. Trend line's R-squared of Shots on Target vs Points = 0.88 
5. Fouls are similar across results, while yellow cards are slightly higher for drawing and losing teams. Home win probabilities track actual home win rates closely in most buckets. The biggest visible gap is at 0.7 (299 matches), where home teams won slightly less often than the odds implied.
6. Overall Bookmakers' favourite win percentage = 56%

Limitations
- One league and one bookmaker (Bet365), so findings may not generalise.
- Team averages across 10 seasons are noisier for clubs with fewer seasons in the data.
- Calibration buckets at the extremes have few matches.
- Associations shown are descriptive, not causal.
- Odds are used only as a benchmark for how well probabilities match results, not as betting advice.

Files
- `epl_clean.csv`: one row per match
- `team_matches.csv`: one row per team per match
- `EPL_Analysis.pbix`: Power BI file with the cleaning steps
