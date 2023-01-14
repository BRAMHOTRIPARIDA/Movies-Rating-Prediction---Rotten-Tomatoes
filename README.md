Movies Rating Prediction - Rotten Tomatoes
-----------------------------


Objective : 
-----------------------------
Given large datasets from Rotten Tomatoes - a popular online review aggregator for film and television, btild a high performing classification algorithm to predict whether a particular movie on Rotten Tomatoes is labeled as 'Rotten', 'Fresh', or 'Certified-Fresh'.
Built and compared multiple predictive models.


Dataset : 
-----------------------------
There are 2 datasets
rotten_tomatoes_movies.csv - contains basic information about each movie listed on Rotten Tomatoes; each row represents one movie;
rotten_tomatoes_critic_reviews_50k.csv - contains 50.000 individual reviews by Rotten Tomatoes critics; each row represents one review corresponding to a movie;


rotten_tomatoes_movies.csv
-----------------------------
rotten_tomatoes_link - movie ID
movie_title - title of the movie as displayed on the Rotten Tomatoes website
movie_info - brief description of the movie
critics_consensus - comment from Rotten Tomatoes
content_rating - category based on the movie suitability for audience
genres - movie genres separated by commes, if multiple
directors - name of director(s)
authors - name of author(s)
actors - name of actors
original_release_date - date in which the movie has been released in theatres, in YYY-MM-DD format
streaming_release_date - date in which the movie has been released on streaming platforms, in YYY-MM-DD format
runtime - duration of the movie in minutes
production_company - name of a studio/company that produced the movie
tomatometer_status - a label assgined by Rotten Tomatoes: "Fresh", "Certified-Fresh" or "Rotten"; this is the target variables in this challenge
tomatometer_rating - percentage of positive critic ratings
tomatometer_count - critic ratings counted for the calculation of the tomatomer status
audience_status - a label assgined based on user ratings: "Spilled" or "Upright"
audience_rating - percentage of positive user ratings
audience_count - user ratings counted for the calculation of the audience status
tomatometer_top_critics_count - number of ratings by top critics
tomatometer_fresh_critics_count - number of critic ratings labeled "Fresh"
tomatometer_rotten_critics_count - - number of critic ratings labeled "Rotten"


rotten_tomatoes_critic_reviews_50k.csv
-----------------------------
rotten_tomatoes_link - movie ID
critic_name - name of critic who rated the movie
top_critic - boolean value that clarifies whether the critic is a top critic or not
publisher_name - name of the publisher for which the critic works
review_type - was the review labeled "Fresh" or "Rotten"?
review_score - review score provided by the critic
review_date - date of the review in YYYY-MM-DD format
review_content - text of the review


Methodology : 
-----------------------------
Train data - 80%, Test data - 20%

Approach 1: Using categorical and numerical features in the dataset (rotten_tomatoes_movies.csv)
-----------------------------
Steps :
  Data Preparation and Preprocessing
  Decision Tree Classifier: With Three Leaf Nodes Condition
  Decision Tree Classifier: Default
  Random Forest Classifier: Default
  Random Forest Classifier - with feature selection
  Weighted Random Forest Classifier - with feature selection


Approach 2: Using review text from the critics dataset (rotten_tomatoes_critic_reviews_50k.csv)
-----------------------------
Steps :
  Predicting 'review_type' using 'review_content' feature and CountVectorizer tool
  
  CountVectorizer is used to transform a 'review_content' into a vector on the basis of the frequency (count) of each word that occurs in the entire text
  
  Predict 'review_type' for movies in train data : 
    Random Forest Classifier: Default 
    Weighted Random Forest Classifier  
  
  Movie Status Prediction : 
    Using predicted 'review_type', estimated 'Positive Review Percent'
    Based on analysis of histogram bins for 'Positive Review Percent' Vs 'Count', set threshold values of 'Positive Review Percent' for labelling movies with status as 'Rotten', 'Fresh', or 'Certified-Fresh'   
