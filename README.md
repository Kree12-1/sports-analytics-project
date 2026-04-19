# sports-analytics-project
# Project overview:
This project introduces a Badminton Performnace impact Dashboard for tournaments organized by the Badminton World Federation(BWF). The idea goes beyond basic match results and develop support tool that evulates player performance.
# Decision making problem:
How can coaches and analysts can make better match strategy and player evulation decisions during tournament? like who performs better under pressure or who is more consistent across rounds.
# Propsed analytics approach:
Take the data from the Kaggle badminton match or BWF tournamnet match from that includes the key variables like player ranking, match scores and tournamnets round. These matrics are combined into a performance impact index which helps to comapre players and identify meaningful performance differences.
# Use by decision makers:
Coaches, Analysts or team managers can use a simple dashboard from where they can analyze opponent strengths before matches and adjust the strategies and evulate performace after matches.
# Connection to chapter 7:
This project is in creative phase in which idea are defined but has not yet been tested or implemented. The focus is on identifying a analtyics opprtunity before building or prototyping.
# Prototype enhancement
Adding a pressure performance score, a dashboard sub-metric that particularly monitors how a player's point-winning rate varies in pivotal games (game 3) in comparison to their previous games in the same competition, is one significant addition to the original concept.
What is being altered: Overall performance across rounds is tracked by the original dashboard. This improvement includes a specific metric that separates clutch performance, or a player's reaction when a game is at stake.
Why making better decisions could result from this: In order to prepare for elimination rounds, coaches must be aware of an opponent's tendency to improve or deteriorate under pressure. An opponent that continuously outperforms in game 3 is tactically distinct from one whose performance deteriorates under pressure.
Let the following variables be defined for a given player in a match that reaches game 3:
- $P_{g}$ = points won by the player in game $g$
- $T_{g}$ = total points played in game $g$
- $R_{g} = \dfrac{P_{g}}{T_{g}}$ = point-winning rate in game $g$
The baseline rate across games 1 and 2 is:
$$R_{\text{baseline}} = \frac{P_1 + P_2}{T_1 + T_2}$$
The Pressure Performance Score is then defined as the difference between the player's game 3 rate and their baseline rate:
$$\text{PPS} = R_3 - R_{\text{baseline}} = \frac{P_3}{T_3} - \frac{P_1 + P_2}{T_1 + T_2}$$
### Interpretation
| PPS Value | Meaning |
| PPS > 0 | Player performs **better** under pressure (raises level in game 3) |
| PPS ≈ 0 | Player performs **consistently** regardless of match situation |
| PPS < 0 | Player performs **worse** under pressure (drops level in game 3) |
A tournament-level average can then be computed across all game-3 matches a player has played:
$$\overline{\text{PPS}} = \frac{1}{N} \sum_{i=1}^{N} \text{PPS}_i$$
where $N$ is the total number of matches reaching game 3 for that player.

