# Zomato Restaurant Clustering And Sentiment Analysis

## Introduction
In today’s digitized modern world, the popularity of food apps is increasing due to their functionality to view, book, and order food with a few clicks on the phone for their favorite restaurant or cafes, by surveying the user ratings and reviews of the previously visited customers. Food app like Zomato provides a secular part where user can rate their experience of the visited restaurant or café. Zomato is a site where someone can give a review of a restaurant, how the restaurant is, and someone's opinion about the restaurant. Restaurant customer satisfaction can be analyzed by their review on Zomato. Sometimes, restaurants see the reviews in Zomato, but they don't get if the reviews are positive or negative to their restaurants. Reviews on Zomato are still in the form of text and can be classified with positive, negative, or neutral ratings.

Starting with EDA we found the most and least expensive restaurants and also found out the critics which have rated more than 100 restaurants and have more than 10000 followers on which restaurant staff should focus.

For clustering, we have decided on 3 clusters after the Silhouette score plot and elbow plot where we used KMeans clustering and Hierarchical clustering algorithms. During clustering, we created a superset of cuisine and cost as features for the clusters.

For sentiment analysis, we used both supervised and unsupervised techniques where we used Linear Discriminant Analysis & Non-negative Matrix Factorization for unsupervised and Multinomial NB, Logistic regression, Decision trees, and its ensembles for supervised learning. In Sentiment Analysis, we converted the ratings above 3.5 as positive and the rating below 3.5 as negative. After tuning the hyperparameters and using the cross-validation technique, the optimum hyperparameters were chosen for the models and the best model was chosen as logistic regression and Lightgbm classifier for supervised learning technique.

## Problem Statement
Your task is to cluster the zomato restaurants into different segments. Also the data has valuable information around cuisine and costing which can be used in cost vs. benefit analysis
Perform sentiment analysis. Also use metadata of reviewers to identifying the critics in the industry.

## About the data
There are two data files
* "Zomato restaurant reviews" has Name of the Restaurant, Name of the customer, their review, rating, follower details, Time of Review and number of photos uploaded along with the review. This data has been mainly used for Sentiment analysis.
* "Zomato Restaurant names and Metadata" has the details of Name of the Restaurant, Link to order on their restaurant on zomato, Average cost, Tags for the restaurants, Cuisines and timings. This data has been mainly used for clustering.

## Models used 
### For clustring 
* K-means Clustering
* Hierarchical Clustering

### For sentiment Analysis( Unsupervised )
* Linear Discriminant Analysis 
* Non-negative Matrix Factorization

### For sentiment Analysis( Supervised )
* Logistic Regression
* Decision Trees
* Random Forest
* Multinomial NB
* XGBoost
* LightGBM

## Deployment of Streamlit WebApp in Heroku and Streamlit

We have created front-end using Streamlit for the webapp. whose deployments and github link are as follows 

| Website | Link |
| ------ | ------ |
| Github | https://github.com/Ali-Asgar-Lakdawala/my-ml-deployment-2 |
| Heroku | https://my-ml-deployment-2.herokuapp.com/ |
| Streamlit | https://share.streamlit.io/ali-asgar-lakdawala/my-ml-deployment-2/main/app.py|
## Conclusion

* We got best cluster as 3 in k means and in hierarchical
* Best model we found for sentiment analysis(Supervised) are Lightgbm and logistic regression 
* We were successfull in deploying the strealit app on heruko .
