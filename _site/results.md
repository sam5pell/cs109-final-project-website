## Project Trajectory
When we began our project we hypothesized that the outcome of the most recent elections in a given district would be important in predicting the upcoming election (or in this case the 2018 election). However, after completing our preliminary data exploration and analyzing the results of our baseline model, we realized that while previous election results can give a better than average prediction for the winner, much more information and different types of information would be necessary to improve our model.

## Results
### Final Model results
Below we have the Senate predictions made by our final model.
![Model Predictions](images/final_model_predictions.png)

From the table provided, we can see that our model correctly predicted 27 out of the 33 seats in the general election. We can see that the types of elections our model typically gets wrong are the - understandably - difficult to predict outcomes such as open seat elections and when an incumbent loses to a challenger. However, our model did correctly predict 3 challengers that defeated incumbents and 1 open seat election correctly, something that is impressive for a computer model with no human political intuition behind it.

It should also be noted that our model put all 33 actual winners within the top two of the contenders of each state. This shows that our model clearly has identified some type of trend, and either an even more sophisticated model or some added human intuition could help in predicting all of these outcomes correctly.

Taking a look at the coefficients, we found that our logistic regression model weighted incumbency positively and challenger/open seat status negatively, all heavily. It also weighted fundraising numbers very slightly. We were surprised to see, however, that it did not weight previous election voter polarization at all. We think this may be caused by the small differences in the numbers, and we think future data augmentation may help with this.

As a note, we put the 2018 election results in the dataframe to show how our model did, but never did we ever use the 2018 election results in any part of our model training.


## Further considerations

As shown above, our model performed quite respectably. If we were to make an even more sophisticated model in the future, we would consider a few more things. We would like to properly take into account voting trends over several previous election cycles, and we would also like to include the presidential election results per state to see how they influence future Senate elections.

Another main addition we would have liked to make is make a more concrete per-state model - meaning we would like for all candidates running within a state to “compete” with each other in the model. This would mean each candidate is not only evaluated from his/her own statistics, but also based on who they are matching up against as well. We would like the probabilities of all candidates running within a state to add up to 1 so we can have a proper percentage likelihood prediction of who is going to win the seat.
