# METHODOLOGY: Is wingspan or height a better predictor of NBA defense?

[Link to blog post.](https://dribbleanalytics.blogspot.com/2018/04/is-wingspan-or-height-better-predictor.html)

To test whether wingspan or height is a better predictor of NBA defense, first I created a database of every active NBA player's wingspan and height. The list of every active player was taken from [Basketball Reference](https://www.basketball-reference.com/leagues/NBA_2018_per_game.html)

## Data collection

Most of the data was taken from the [NBA's Combine Anthrometric page](https://stats.nba.com/draft/combine-anthro/). Height w/o shoes was used because height w/ shoes data was not recorded until the 2004-2005 season. All the NBA's Combine Anthrometric data is available on the "Combine Anthrometric" tab of the Excel master sheet.

Because not all players attend the combine, the Combine Anthrometric did not have all the data. So, I manually found data for over 200 players.

To complete the data manually, all height data was taken from each player's DraftExpress player profile. This may lead to some inconsistency, because DX sometimes uses height w/ shoes for the player profile. The only player whose height data was not taken from DX was Giannis Antetokounmpo, because he has grown since his draft measurements. His data was taken from this [ESPN TrueHoop article](http://www.espn.com/nba/story/_/id/14927328/milwaukee-bucks-f-giannis-antetokounmpo-nba-most-exceptional-body).

Most of the wingspan data was available on DX. For players whose wingspan was not available on DX, I used a variety of sources. The most credible source except for DX is NBAdraft.net. Team blogs, forums, etc. were used when I could not find data anywhere else. Finally, when there was no data on blogs or forums, I either estimated the wingspan to be a bit more than the player's height, or estimated the wingspan based on how DX described it (e.g. "average", "excellent").

All data not taken from the Combine Anthrometric is highlighted on the master Excel sheet. DX data is highlighted in yellow; data from other sources are highlighted in blue, and the source is specified next to the player's data; and players for whom I could not find data are highlighted in green.

## Player-by-player analysis

I compared each individual player's wingspan and height to his DWS (defensive win shares, downloaded from Basketball Reference). After doing a full-league regression, I divided the data into three groups: guards, forwards, and centers. This makes the analysis more accurate, given that bigmen are bigger and often have a larger DWS than guards.

## Team-by-team analysis

I downloaded each team's total year stats from Basketball Reference. This includes a list of their players and minutes played. I then weighted the wingspan and height data for each player according to their minutes, arriving at a weighted average for that team. Traded players or free agents count for every team they played (e.g. Blake Griffin has minutes on both the Clippers and Pistons).

The weighted average height and wingspan was then compared to DRTG (downloaded from [NBA.com/stats](https://stats.nba.com/teams/defense/?sort=W&dir=-1)). I then used a Pearson correlation test to determine whether wingspan or height is a better predictor of NBA defense. I used a p-value < .05 threshold to determine statistical significance (as is commonly accepted).

## Notes

Note that a higher DWS is better, so the factor with a greater r-value (correlation coefficient) is a better predictor of DWS. However, a lower DRTG is better, so the factor with a more negative r-value is a better predictor of DRTG.

All data and calculations are available in the master Excel sheet. The .csv files include only the final sheets used in the Python program. 
