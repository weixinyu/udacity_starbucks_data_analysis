Documentation
-------------
## Motivation for the project
> This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. 

> Not all users receive the same offer, and that is the challenge to solve with this data set.

> The task of this project is to combine transaction, demographic and offer data to predict whether or not someone will respond to an offer. This data set is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

> Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. You'll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement.

> The transactional data showing user purchases made on the app including the timestamp of purchase and the amount of money spent on a purchase. This transactional data also has a record for each offer that a user receives as well as a record for when a user actually views the offer. There are also records for when a user completes an offer. 

> Keep in mind as well that someone using the app might make a purchase through the app without having received an offer or seen an offer.

##  Libraries:
* numpy - The fundamental package for scientific computing with Python
* pandas - Pandas is a fast, powerful, flexible and easy to use open source data analysis and manipulation tool, and most of the data analysis in this project is based on the dataframe in Pandas.
* matplotlib - This is package used for generating statistics plot
* sklearn - This is a simple and efficient tools for predictive data analysis
seaborn - This is a powerful Python data visualization library based on matplotlib. It provides high level interface for drawing statistical graphics
* time - This package is used to transform datetime format
warnings - This package is used to filter warning info
* visuals - This is a package from the Udacity Program Introduction to Machine Learning with Pytorch, which supports to plot the classification result and features

## Project Repository files:
* Starbucks_Data_Exploration.ipynb	-	Code with appropriate comments, analysis, and documentation.
* visuals.py				-	Supplementary visualization code
* df_clean_20230208.pickle		-	The cleaned data
* README.md               		-	Documentation

## Result Summary:
*  Amoung the three classifiers experimented, Adaboost performs better than others with accuracy 0.748 and f1 score 0.690, which is also far better than the baseline score(accuracy 0.404, f1 score 0.576)
*  The Adaboost classifier optimized with Grid Search on three hyper parameters(learning_rate, n_estimators, algorithm) get scores(accuracy 0.748, f1 score 0.692). The f1 score is a little better. The best parameters are:algorithm='SAMME.R', learning_rate=0.1, n_estimators=250.
*  The top five important features are:(1.income, 2.social, 3.difficulty, 4.reward, 5.2016). The income is the most important feature for the prediction. Then all the second, third, forth are the properties of offer. It's quite interesting that Age and Gender are not important features for this prediction.
*  The detailed discussion about this project is posted to:https://blog.csdn.net/weixinyu2012/article/details/128946775

## Acknowledgements
My thanks would go to the Udacity Platform and mentors, because I have benifited the knowledge from Udacity programs Data Scientist and Intro to Machine Learning with Pytorch and use some demo codes from them. My thanks also goes to mentors, who give me valuable advice during my learning journey.

## References
> https://scikit-learn.org/stable/supervised_learning.html#supervised-learning
> https://blog.csdn.net/weixin_44838881/article/details/124836755
> https://stackoverflow.com/questions/30132282/datetime-to-string-with-series-in-pandas
> https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html#sklearn.metrics.f1_score
> https://learn.udacity.com/nanodegrees/nd229/parts/cd0025/lessons/
> http://scikit-learn.org/0.17/modules/generated/sklearn.grid_search.GridSearchCV.html
> http://scikit-learn.org/stable/modules/generated/sklearn.metrics.make_scorer.html
> https://scikit-learn.org/dev/modules/generated/sklearn.ensemble.AdaBoostClassifier.html#sklearn.ensemble.AdaBoostClassifier
> https://scikit-learn.org/dev/modules/generated/sklearn.ensemble.AdaBoostClassifier.html#sklearn.ensemble.AdaBoostClassifier.feature_importances_
