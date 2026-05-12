nba-win-prediction
job interview assignment 


we will be using 2021-2024 season data for training and 2026 season data for testing.
we will be using the following features for training our model:
 used ai to write the readme
 Date Conversion

Converted:

gameDateTimeEst
gameDate

into pandas datetime format for chronological analysis.

Reason:

rolling statistics require correct time ordering
prevents future data leakage
enables train/test splitting by season
2. Modern Era Filtering

Filtered dataset to:

2021–2026 seasons only

Reason:

focuses on modern NBA play style
improves relevance for current predictions
avoids outdated basketball trends from older eras
3. Duplicate Removal

Removed:

duplicated rows
duplicated gameId entries

Reason:

duplicated games distort rolling statistics
duplicated games create biased model training
4. Chronological Sorting

Sorted all games by:

gameDateTimeEst

Reason:

sports analytics depends on time ordering
rolling features require correct chronology
prevents future leakage
5. Removal of Broken/Incomplete Games

Removed games with:

missing scores
invalid scores

Reason:

incomplete games cannot be used for supervised learning
prevents corrupted rows from entering the model
6. Target Variable Creation

Created:

home_win

Encoding:

1 = home team wins
0 = away team wins

Reason:

machine learning models require numerical target variables
7. Team Name Standardization

Created:

home_team
away_team

by combining city + team name.

Example:

Boston Celtics
Miami Heat

Reason:

easier grouping for rolling statistics
simplifies feature engineering
improves readability
8. Playoff Feature Engineering

Created:

is_playoff

Encoding:

1 = playoff game
0 = regular season game

Reason:

playoff basketball behaves differently from regular season basketball
9. COVID Era Feature

Created:

covid_era

Reason:

COVID seasons had unusual scheduling and attendance effects
allows model to learn abnormal season behavior
10. Leakage Prevention

Removed leakage columns from the modeling dataset.

Examples:

final scores
winner labels

Reason:

the model should not see future information before prediction