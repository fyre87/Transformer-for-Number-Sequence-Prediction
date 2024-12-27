# Transformer-for-Number-Sequence-Prediction

[Fake college football](https://www.reddit.com/r/FakeCollegeFootball/) is a game where two teams, an offense and a defense, select numbers 1-1500. If those numbers are close together, the offense has a good play and if those numbers are far apart, the defense has a good play (note that 1 and 1500 are 1 apart, as the numbers are in a circle). The game takes around 100 numbers to complete.

Given the sequential nature of the game, I constructed a transformer to predict the probability that the next number submitted by a player is within each of the 15 100 number groups (1-100, 101-200, etc.).

The data stores information about the previous numbers submitted (what chunk of 100 numbers they fell into), what their opponent played, whether they are on offense or defense, etc. Rather than converting tokens to vectors like most LLM's, this vector of data about the previous numbers submitted is standardized and put into the transformer to predict the next number. 

While there is a lot of noise in the outcome, as this is human's predicting numbers and many factors influence the decision of humans, the transformer correctly learns the most common trends from the game (people most likely to submit numbers 1-100 generally, higher numbers slightly more common on defense). 
