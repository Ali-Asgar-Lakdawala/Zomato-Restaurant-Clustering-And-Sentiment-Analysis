# Zomato Restaurant Clustering And Sentiment Analysis

## Introduction
In today’s digitized modern world, the popularity of food apps is increasing due to their functionality to view, book, and order food with a few clicks on the phone for their favorite restaurant or cafes, by surveying the user ratings and reviews of the previously visited customers. Food app like Zomato provides a secular part where user can rate their experience of the visited restaurant or café. Zomato is a site where someone can give a review of a restaurant, how the restaurant is, and someone's opinion about the restaurant. Restaurant customer satisfaction can be analyzed by their review on Zomato. Sometimes, restaurants see the reviews in Zomato, but they don't get if the reviews are positive or negative to their restaurants. Reviews on Zomato are still in the form of text and can be classified with positive, negative, or neutral ratings.

Starting with EDA we found the most and least expensive restaurants and also found out the critics which have rated more than 100 restaurants and have more than 10000 followers on which restaurant staff should focus.

For clustering, we have decided on 3 clusters after the Silhouette score plot and elbow plot where we used KMeans clustering and Hierarchical clustering algorithms. During clustering, we created a superset of cuisine and cost as features for the clusters.

For sentiment analysis, we used both supervised and unsupervised techniques where we used Linear Discriminant Analysis & Non-negative Matrix Factorization for unsupervised and Multinomial NB, Logistic regression, Decision trees, and its ensembles for supervised learning. In Sentiment Analysis, we converted the ratings above 3.5 as positive and the rating below 3.5 as negative. After tuning the hyperparameters and using the cross-validation technique, the optimum hyperparameters were chosen for the models and the best model was chosen as logistic regression and Lightgbm classifier for supervised learning technique.

## Problem Statement
Your task is to cluster the Zomato restaurants into different segments. Also, the data has valuable information around cuisine and costs which can be used in cost vs. benefit analysis
Perform sentiment analysis. Also, use the metadata of reviewers to identify the critics in the industry.

## About the data
There are two data files
* "Zomato restaurant reviews" has the Name of the Restaurant, Name of the customer, their review, rating, follower details, Time of Review, and the number of photos uploaded along with the review. This data has been mainly used for Sentiment analysis.
    * Restaurant: Name of the Restaurant
    * Reviewer: Name of the Reviewer
    * Review: Review Text
    * Rating: Rating Provided by Reviewer
    * MetaData: Reviewer Metadata - No. of Reviews and followers
    * Time: Date and Time of Review
    * Pictures: No. of pictures posted with the review


* "Zomato Restaurant names and Metadata" has the details of the Name of the Restaurant, Link to order on their restaurant on Zomato, Average cost, Tags for the restaurants, Cuisines, and timings. This data has been mainly used for clustering.
    * Name: Name of Restaurants
    * Links: URL Links of Restaurants
    * Cost: Per person estimated Cost of dining
    * Collection: Tagging of Restaurants w.r.t. Zomato categories
    * Cuisines: Cuisines served by Restaurants
    * Timings: Restaurant Timings


## Steps involved:

### Null values Treatment
The data set had null values out of which we replaced some with the mean of the feature some by zero and dropped some observations which were almost filled with null values.  
### Outliers treatment
Isolation Forests(IF), similar to Random Forests, are built based on decision trees. And since there are no predefined labels here, it is an unsupervised model.IsolationForests were built based on the fact that anomalies are the data points that are “few and different”.In an Isolation Forest, randomly sub-sampled data is processed in a tree structure based on randomly selected features. The samples that travel deeper into the tree are less likely to be anomalies as they require more cuts to isolate them. Similarly, the samples which end up in shorter branches indicate anomalies as it was easier for the tree to separate them from other observations.
### Exploratory Data Analysis
We performed univariate and bivariate analyses. This process helped us figure out various aspects and relationships among variables. It gave us a better idea of which feature behaves in which manner.
### Encoding of categorical columns
We used One Hot Encoding(converting to dummy variables) to produce binary integers of 0 and 1 to encode our categorical features because categorical features that are in string format cannot be understood by the machine and needs to be converted to the numerical format.
### Standardization of features
Our main motive through this step was to scale our data into a uniform format that would allow us to utilize the data in a better way while performing fitting and applying different algorithms to it.
The basic goal was to enforce a level of consistency or uniformity to certain practices or operations within the selected environment.

### Fitting different models
For modeling, we tried various algorithms like:
* Clustering 
* K means clustering
* Hierarchical clustering
* MultinomialNB
* Logistic Regression
* Decision Tree
* Random Forest Classification
* XGBoost Classification
* LightGBM Classification

### Tuning the hyperparameters for better recall
It is necessary to tune the hyperparameters of respective algorithms to improve accuracy and avoid overfitting when using tree-based models such as Random Forest Classifier and XGBoost classifier. The best set of hyperparameters was determined using a grid search algorithm.

### Features Explainability 
We have applied SHAP on the XGBoost and CatBoost model to determine the features that were most important while predicting an instance and also build a feature importance graph to find out which features were important and which were redundant in a model

### Deciding number of cluster
- Elbow Method
<img src="https://github.com/Ali-Asgar-Lakdawala/Zomato-Restaurant-Clustering-And-Sentiment-Analysis/blob/main/Images/Elbow%20plot.png" width="1000">

From the above graph we selected the number of cluster(k) should be between 3 and 5

### Performance Matrix

#### Clustering (Silhouette score plot)
<img src="https://github.com/Ali-Asgar-Lakdawala/Zomato-Restaurant-Clustering-And-Sentiment-Analysis/blob/main/Images/Silhouette%20score%20plot.png" width="1000">
It can be seen that the silhouette score for k=3 is the highest 

#### Sentiment Analysis

* Performance matrix table
<img src="https://github.com/Ali-Asgar-Lakdawala/Zomato-Restaurant-Clustering-And-Sentiment-Analysis/blob/main/Images/Performance%20matrix%20table.png" width="1000">

<img src="https://github.com/Ali-Asgar-Lakdawala/Zomato-Restaurant-Clustering-And-Sentiment-Analysis/blob/main/Images/roc_auc%20plot.png" width="1000">

## Deployment of Streamlit WebApp in Heroku and Streamlit

We have created a front-end using Streamlit for the web app. whose deployments and Github link are as follows 

| Website | Link |
| ------ | ------ |
| Github | https://github.com/Ali-Asgar-Lakdawala/my-ml-deployment-2 |
| Heroku | https://my-ml-deployment-2.herokuapp.com/ |
| Streamlit | https://share.streamlit.io/ali-asgar-lakdawala/my-ml-deployment-2/main/app.py|

## Conclusion

* Based on the silhouette score plot and elbow plot, we decided on 3 clusters that were grouped using KMeans clustering and Hierarchical clustering.
* Best models we found for sentiment analysis(Supervised) are Lightgbm and logistic regression 
* We were successful in deploying the strealit app on heruko.
