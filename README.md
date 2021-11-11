# Python-Football-Betting-from-Scratch
I believe asking myself questions and responding to them might help you understand my project's goals and methodology in creation. Here are some QnA's below, enjoy!

Q1) Why did you make this model, what was your ultimate goal?
Can I outsmart my friends and create my own set of fairly accurate homemade odds using xG that adjusts for the factors I deem as important, to ultimately go beyond breaking even, win some money and my friends' respect? (the latter not so much, but still true)

*I have loved football (The European one not the aussie version, although go Demons!) ever since, and for a few years I've been casually having a competition with my friends in who can predict the most games correct, and get a few bucks with it via bets! 
My bets have not even been breaking even as of yet, so I was very curious on how I could increase my chances in betting successfully through the use of the famous xG model (expected goals), and adjusting the average xG per team with self-deemed 'important factors', using the popular Poisson Distribution for implied probabilities too. 
The final creation of homemade odds will then be compared to bookie odds to find some potential value bets. As always though, gamble responsibly!*

Q2) What mathemathical tools / equations or logical constructs did I use to represent the relationships between the variables depicted by the conceptual model? 
Note: I have detailed the external and internal variables, and the boundaries of my fairly simplistic project and what type of eventual model it is (i.e. stochastic or deterministic, etc). 

This type of model is Static (no time variable), Deterministic (final odds calculated do not vary), Discrete (xG values are from last 'n' games so can be counted in intervals and averaged).

Although the model itself does not consider space, xG (expected goals) is a more complex model which accounts for the shot selection and 'space' respect to the goal. I am only using the data provided, not making the complex xG model, thankfully!

1. Expected Goals (xG) ~ Mathematical Tools/Data Used
In football, a “shot on target” can't be treated equally as you could take a shot from anywhere with little chance of it going in, or you could score a tap in! xG instead considers the quality of each shot taken by looking at where it was taken, what foot it was taken with and the “style of play”. Thankfully I will not be creating the xG model myself (that would be a pain), but I will be using the data available for each PL team and make some adjustment to increase my chances of winning bets!

2. Boundaries: Only Premier League statistics and fixtures, not for the other "big leagues" as I am not too interested in them and devoutly follow only the PL. Assumes team does not have drastic injuries,deaths or significant changes to the team.

NOTE: Not all variables possible are considered, only those I assume and deem as very important and influential in the results of the teams. This simplifies the model down.

3. Internal variables include: xG values (of each team), 
Home/Away fixture, team form (no. of wins vs matches played), 'Balance Factor' in Attack and Defence of Team (G vs GA)

4. External variables are: Popular bookies' odds 

Equations used: The 'Poisson Distribution', a discrete probability distribution and a popular betting tool used (popular for good reason too!) 

 (Lambda = average value xG over given time, k = number of events e.g. goals scored)

M = matches played so far
W = wins so far
L = losses so far, D = draws so far
G = goals scored by team
GA = goals conceded by team (scored against)

Note that in this case, I have only explored 'over and under' bets as I have not tested this model's wits in calculating the probability of a fixture's outcome. That requires more variables and a more complex model which I may potentially work on in the future. So far the model is working wonders for me!



Q3) Can you summarise what your model does?
What does the model do exactly in a step-by-step process?
1. I first obtain the average expected goals of every team from the website 'Understat', which has arguably the best xG model freely available
2. The model then adjusts this value when accounting for the variables of the team's form, if it is a home/away fixture and the balance between attack and defence. These are variables/factors I have deemed over my lifetime as a football fan as very influential in a team's ability to score goals. (An assumption, but an important one to simplify the model) 
3. This adjusted average value for expected goals is then converted into implied probabilities via Poisson Distribution and inverted into homemade odds for 'over/under 'k' goals' bets (and potentially wins if you compare two teams' implied probabilities, although not addressed)
4. (additionally) Compare with bookies odds and find 'Value' bets [i.e. if the bookie odd offered is greater than the homemade odd for a specific event]

In terms of results, the implied probabilities produced are still useful in assessing which bets are more likely to happen, but converting them into the format of odds later on in the model makes it easier to compare with standard betting formats. 
Most of the homemade bets aligned fairly closely with the odds offered by Sportsbet and Bet365, but there were some 'value' bets which I did attempt. So far I have done more than break even (although a relatively small 6 bet sample size) and most have been successful bets to my pleasure.
A slight annoyance about the model is that only calculating up to 5 does miss out on ~0.1% of the other events, which could affect the values calculated by a specific marginal error. 
But What I find helpful about this model is that I can change the extent at which each of the three variables/factors affect the average xG, as my experience and knowledge gets better. 
It was really fun (and stressful too) making this model and I hope you understand it even with some football jargon and terminologies. Take care!
