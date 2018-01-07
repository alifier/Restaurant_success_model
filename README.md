# Project: Restaurant Success Model
## A model that predicts if a restaurant is likely to close within the next 4 years.

### Project Description

The goal of this project was to built a model that can predict whether a restaurant is likely to close within a 4-year period. This information would be useful to restaurant lenders (such as banks) and investors.

To achieve the above goal I started by building a relevant dataset which I then used to fit a logistic regression algorithm that can separate between restaurants that are likely to close and restaurants that are likely to remain open. Building a meaningful dataset involved several steps that are breaken down below:

1) Find an initial list of restaurants that used to exist in the [past](https://www.kaggle.com/c/yelp-recsys-2013).
2) Find information about the current state of the restaurants from the past.
    a) Pull information from the Yelp Search API.
    b) Check if the information is correct (restaurant names and addresses have changed in 4 years).
    c) Find additional information about non-matched restaurants using the Google Search API.
    d) Pull new information from Yelp Business API using the web addresses found through Google.
    e) Match information from old and new datasets to make sure it is correct.
3) Engineer relevant features.
4) Test different Machine Learning models and optimize parameters based on above use case.

The work described in the above steps is split in five Jupyter notebooks.


### Code
All code is presented in a series of notebooks showing the steps followed for each of the individual processes and the resulting numbers and graphs.

This repository includes the code to pull data from the Yelp Search API, based on the names and addresses of the restaurants found on a [Yelp Kaggle Dataset](https://www.kaggle.com/c/yelp-recsys-2013) released in 2013. 

The data from the two sources (Yelp Search API and Kaggle) are matched to guarantee the consistency between the two sets and only 65% of the entries had a matching address and name. The Google Custom Search API is used for the unmatched data to find the right restaurant urls ([file: Restaurants_yelp_GoogleCustomSearchAPI.ipynb](./Restaurants_yelp_GoogleCustomSearchAPI.ipynb)) and pull the remaining data using the Yelp Business API ([file: Restaurants_yelp_API_for_GoogleSearchResults.ipynb](./Restaurants_yelp_API_for_GoogleSearchResults.ipynb)).

The two datasets are then matched together with higher success rate ([file: Restaurants_yelp_join_all.ipynb](./Restaurants_yelp_join_all.ipynb)) and the resulting dataframe is used to generate additional features ([file: Restaurants_yelp_more_features_final.ipynb](./Restaurants_yelp_more_features_final.ipynb)). 

Different ML algorithms are fitted using the above features Logistic Regression and Gradient Boosting being the most successful ([file: Restaurants_yelp_ML_final.ipynb](./Restaurants_yelp_ML_final.ipynb)).

For a more detailed discussion of the process followed to develop this model and the obtained results, see the relevant [blog post](https://medium.com/@alifier/using-yelp-data-to-predict-restaurant-closure-8aafa4f72ad6).
