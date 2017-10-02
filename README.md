# Restaurant_success_model
## A model that predicts if a restaurant is likely to close within the next 4 years.

This repository includes the code to pull data from the Yelp Search API, based on the names and addresses of the restaurants found on a [Yelp Kaggle Dataset](https://www.kaggle.com/c/yelp-recsys-2013) released in 2013. 

That data from the two sources (Yelp Search API and Kaggle) are matched to guarantee the consistency between the two sets and only 65% of the entries had a matching address and name. The Google Custom Search API is used for the unmatched data to find the right restaurant urls ([file: Restaurants_yelp_GoogleCustomSearchAPI.ipynb](./Restaurants_yelp_GoogleCustomSearchAPI.ipynb)) and pull the remaining data using the Yelp Business API ([file: Restaurants_yelp_API_for_GoogleSearchResults.ipynb](.Restaurants_yelp_API_for_GoogleSearchResults.ipynb)).

The two datasets are then matched together with greater accuracy ([file: Restaurants_yelp_join_all.ipynb](./Restaurants_yelp_join_all.ipynb)) and the resulting dataframe is used to generate additional features ([file: Restaurants_yelp_more_features_final.ipynb](./Restaurants_yelp_more_features_final.ipynb)). Different ML algorithms are fitted using the above features Logistic Regression and Gradient Boosting being the most successful ([file: Restaurants_yelp_ML_final.ipynb](./Restaurants_yelp_ML_final.ipynb)).
