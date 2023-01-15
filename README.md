Movies Rating Prediction - Rotten Tomatoes - Using Variations in Decision Tree, Random Forest and CountVectorizer
-----------------------------


Objective : 
-----------------------------
Given large datasets from Rotten Tomatoes - a popular online review aggregator for film and television, built a high performing classification algorithm to predict whether a particular movie on Rotten Tomatoes is labeled as 'Rotten', 'Fresh', or 'Certified-Fresh'.
Built and compared multiple predictive models.


Dataset : 
-----------------------------
There are 2 datasets
rotten_tomatoes_movies.csv - contains basic information about each movie listed on Rotten Tomatoes, each row represents one movie.
rotten_tomatoes_critic_reviews_50k.csv - contains 50.000 individual reviews by Rotten Tomatoes critics, each row represents one review corresponding to a movie.


rotten_tomatoes_movies.csv
-----------------------------

![image](https://user-images.githubusercontent.com/26669836/212568177-c8984b1a-d637-424a-b7c5-cbce776e4101.png)


rotten_tomatoes_critic_reviews_50k.csv
-----------------------------

![image](https://user-images.githubusercontent.com/26669836/212568437-f45807f7-c04f-40e2-bf7f-32402943625c.png)


Methodology : 
-----------------------------
Train data - 80%, Test data - 20%

Approach 1: Decision Tree and Random Forest - Using categorical and numerical features in the dataset (rotten_tomatoes_movies.csv)
-----------------------------
Steps :

  Data Preparation and Preprocessing
  
  Decision Tree Classifier: With Three Leaf Nodes Condition - 94.6% accuracy
  
  Decision Tree Classifier: Default - 99.1% accuracy
  
  Random Forest Classifier: Default - 99.0% accuracy
  
  Random Forest Classifier - with feature selection - 99.2% accuracy
  
  Weighted Random Forest Classifier - with feature selection - 99.3% accuracy


Approach 2: CountVectorizer - Using review text from the critics dataset (rotten_tomatoes_critic_reviews_50k.csv)
-----------------------------
Steps :

  Predicted 'review_type' using 'review_content' feature and CountVectorizer tool, CountVectorizer is used to transform a 'review_content' into a vector on the basis of the frequency (count) of each word that occurs in the entire text
  
  Predicted 'review_type' for movies in train data : 
    Random Forest Classifier: Default, 
    Weighted Random Forest Classifier  
  
  Movie Status Prediction : 
    Using predicted review_type estimated 'Positive Review Percent', 
    based on analysis of histogram bins for 'Positive Review Percent' Vs 'Count', set threshold values of Positive Review Percent for labelling movies with status as 'Rotten', 'Fresh', or 'Certified-Fresh'   
