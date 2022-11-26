# SpotifySkippingBehavior

## Executive Summary

Spotify is a media services provider, founded in 2006 by Daniel Elk and Martin Lorentzon. It provides DRM-protected music, videos and podcasts from record labels and media companies. Spotify gives you access to millions of songs, podcasts and videos from artists all over the world.Spotify is simple because you can just access content for free by signing up using an email address. 
Being Spotify a “freemium” service, you can find differences between Spotify Free and Premium: Free version is ad-supported, like radio stations, it can be accessed from computer and mobile phone, but if you want a full service you need to get and pay for a Premium subscription. One of the most relevant differences is that in the free version you have limited features and you are allowed to skip up to six times per hour, every hour. on the other hand Premium users have access to everything, they can play any song  (on demand), as well as find and hear playlists, create playlists, listen offline, hear high - quality music and, above all, they can skip as many songs as they like, without ads.
The goal for our models is to predict the behavior user for skipping or not a song, using as our Y the variable ‘Not_skipped’, understanding if and how much our output variable is dependent on the features included in our dataset. While there is a large related body of work on recommender systems, there is very little work, or data, describing how users sequentially interact with the streamed content they are presented with. In particular within music, the question of if, and when, a user skips a track is an important implicit feedback signal. In order to get this feedback we developed our analysis and prediction based on supervised machine learning models: we used Logistic Regression, which we concluded applying Ridge and Lasso regression, and the Regression Tree model, together with the Random Forest. 


## Dataset

We found the dataset for our project on AIC (Artificial Intelligence crowd), where it has been presented for challenge in 2019 (https://www.aicrowd.com/challenges/spotify-sequential-skip-prediction-challenge.) Our initial dataset is composed of 99999 observations for 21 variables. In this dataset we do not have any missing values. We decided to drop ‘hour_of_day’ and ‘date’ because during data visualization we discovered that they didn’t influence our output. We also got dummies for every variable which presented different classes. As asked from the challenge organizers we cite the following paper: @inproceedings{brost2019music, title={The Music Streaming Sessions Dataset}, author={Brost, Brian and Mehrotra, Rishabh and Jehan, Tristan}, booktitle={Proceedings of the 2019 Web Conference}, year={2019}, organization={ACM} }


## Analysis

### Logistic Regression
Since our variables are represented in the cleaned dataset as binary, the first model we decided to apply is Logistic Regression. We used the built-in feature importance method and then the Variance Inflation Factors to understand which variables were to be kept or discarded. We performed Ridge Regression and Lasso as well, and we found out that our accuracy underwent non relevant changes switching from no penalty, to l1 and l2. As our results for this model we got: Accuracy on train and test for Logistic: 0.99  Ridge and Lasso:  0.98.

### Regression Tree
A decision tree is a managerial tool that presents all the decision alternatives and outcomes in a flowchart type of diagram. Each branch of the tree represents a decision option, its cost and the probability that it is likely to occur. A decision tree illustrates graphically all the possible alternatives, probabilities and outcomes and identifies the benefits of using decision analysis. As our results for this model we got:
Root Mean Squared Error on train set: 0.09882687922411729
Root Mean Squared Error on test set: 0.10529649555232867
Mean of y_train: 0.3387333873338733

### Random Forest
The "forest" it builds is an ensemble of decision trees. Random forest builds multiple decision trees and merges them together to get a more accurate and stable prediction. These are the results we got for this model:
Root Mean Squared Error on train set: 0.08721280950953403
Root Mean Squared Error on test set: 0.1051392623351552
Mean of y_train: 0.3387333873338733
Accuracy of RF classifier on training set: 0.99
Accuracy of RF classifier on test set: 0.99


## Conclusions
First when we were exploring the data we saw that for our dependent variable had as percentage of song skipped about 66% and fully played 34%.  Comparing all the models that we use we got the same or similar accuracy = 0,99, for all of them. With the decision tree we can visualize better our results, and understand which variables affect on the result.

