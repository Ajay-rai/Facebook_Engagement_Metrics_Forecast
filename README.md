# Facebook Engagement Metrics Forecast
* Predicted the engagement metric (number of reactions, comments, and shares) of future posts from the given dataset (Facebook page data) consisting of temporal information and the type of post(video, photo, link and status).
* Explained correlation between variables and trends using temporal dimensions of engagement metric.

## Code and Resources Used
* **Python Version:** 3.8.5
* **Packages:** pandas, numpy, scikit-learn, matplotlib, seaborn
* **Deployment Ref:** https://github.com/jacobod/Facebook-Metrics-Prediction

## EDA
![alt text](https://github.com/Ajay-rai/Facebook_Engagement_Metrics_Forecast/blob/main/Images/dist.png)
![alt text](https://github.com/Ajay-rai/Facebook_Engagement_Metrics_Forecast/blob/main/Images/bar_status.png)
![alt text](https://github.com/Ajay-rai/Facebook_Engagement_Metrics_Forecast/blob/main/Images/correlation.png)

## Modeling
* Multilinear model : MAE = 548
* Random Forest : MAE = 517
* Both model didn't perform well and gave high MAE value for overall engagement prediction. This could be due to dataset not containing enough useful information.

### Feature Importance
![alt text](https://github.com/Ajay-rai/Facebook_Engagement_Metrics_Forecast/blob/main/Images/shap.png)

## Result and Conclusion
* The 'number of reaction' column was the sum of reactions: likes,loves,sad etc. For analysis the reaction columns (likes,loves,sad etc.) were removed. By doing this, we are able to reduce dimension and remove correlation between variable. 
* Extracted year, month, weekday, and hour from status_published(datetime) column. Used them to visualize the behavior of user engagement over temporal dimensions.
* We see a higher correlation of reactions, comments, and shares column. This is obvious as the more a post engages users, the more will they comment and share along with reaction on the post.
* Created a new target variable which accounted for total reactions, comments, and shares of a post.
* Random forest gave a better prediction, which is due to presence of outliers/extreme values in our dataset. Decision tree models are not affected by outliers.
* For a post: the best type of post is video, best month is 5th, best time of the day is 7am to 11am, and best day is Wednesday.
* More data such as geographical location can help us make a better strategy for a post. We can also do an analysis of the sentiment of a user by looking at the type of reaction.
* Comments can be extracted and we can extract the common topic of discussion using NLP. We can also extract the length of the video, it can help us in engaging a user more.
