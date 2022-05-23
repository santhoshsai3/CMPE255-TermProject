---
title: Product Recommender System Based on the Ratings
date: "3rd May 2022"
authors: Vineet Kiragi, Sai Santhosh, Supriya Bhupathiraju, Saroja, San José State University

header-includes: |
  \usepackage{booktabs}
  \usepackage{caption}
---

# Abstract

The business of online shopping thrives on recommending the right product to the right user. Recommending products to an user based on the ratings he has given to similar products might entice the user to buy more Products. So we are trying to create a Recommendation System which with an acceptable accuracy predict the Beauty products a user might like and probably buy depending upon the ratings he/she has given to other Beauty Products. This will help E-Commerce companies(in our case Amazon) make better product placements. Better product placements inturn ensures their product marketing actually reach the corrected most probable potential buyers, inturn generating much more revenue and also better returns on money spent of marketing in per dollar terms.

# Introduction

In today's world we are overloaded with data which provides us the useful information. But it's not possible for the user to get the information in which they are interested in from the available data. In order to help the user to find out information about the product, recommedation systems are developed.

Recommeder system helps in creating a relation between the user and items and utilizes the similarity between user/item to make recommendations. Many popular Ecommerce sites widely use Recommended Systems to recommend news, music, research articles, books, and product items. More the development of e-commerce websites more is the need emerged for providing recommendations compiled from filtering the whole range of available options.With a wide variety of options that are provided to the users from multiple websites, users find it very difficult to make the most appropriate choices.

# Methods

Our goal of the project is to recommend products to users based on the ratings given to the products. Before diving into data modeling methods, we have to process and clean the data to prepare the dataset for modeling. We will go through the data cleaning, data analysis and data processing in this section.
 
**1.Data Collection:** We have used a dataset from kaggle. The dataset contains 2 million customer reviews and ratings and 4 features. The entries are from May 1996 - July 2014.

**2.Data Cleaning:** We have checked for any null values in the data. We didn't find any null values or duplicates in this dataset. So the dataset is mostly clean. Apart from the null or missing values we found alphanumeric data for UserId and product. So in order to normalize the data we used label encoder to convert alphanumeric data to numeric.

**3.Data Analysis and Visualization:** As part of data analysis we analyzed the relationship between user and the products as this dataset is mainly based on the ratings that are provided by the user for every product. We analyzed scenarios like the number of rated products per user and the number of ratings for per product. From this we understood which user has given the max/min number of ratings and which product has the max/min number of ratings. 

We have plotted the following plots to infer few observations

**- Bar plot for unique users,products and total records**

<img width="700" alt="bar_plot_user" src="/images/bar_plot_user.png">

We can infer from the above graph how the data is distributed in the dataset. The total number of records is 2M and total number of users is 1.2M which makes us conclude that on an average every user rates at least twice. The total number of unique products is 250K. We can conclude that on an average, each product is rated at least 8-10 times.
 
**- Bar plot for ratings given by users**

<img width="700" alt="bar_plot_user_ratings" src="/images/bar_plot_user_ratings.png">
 
The above graph shows the distribution of various ratings. The rating 5 was given by 1.2M users which is highest and rating 2 is given by 113k users which is lowest.
We can also see that the sum of users which gave 1,2,3,4 ratings is still less than the users who gave rating 5.
 
**- Bar plot to show the most popular products**

<img width="700" alt="bar_plot_high_rated_products" src="/images/bar_plot_high_rated_products.png">

 
The above graph shows the most popular products and their frequency. The most popular product is B001MA0QY2 which is rated by 7533 Users.
The number of ratings for the first popular product and second popular product is very high.
 
**- Bar plot to show the ratings range**

<img width="700" alt="ratings_count_products" src="/images/ratings_count_products.png">
 
 
Most of the products have received less than 10 ratings.
Out of 200k products, 2000 products have received more than 100 ratings.
 
**- Violin plot to show the product ratings**

<img width="600" alt="violin_plot_ratings" src="/images/violin_plot_ratings.png">
 
From the above Violin Plot we can conclude that the number of products with 5 star ratings is high and this number is greater than the sum of all other ratings given to other products.
The number of products with ratings 2 stars is the least.
The maximum rating given by any user is 5 and lowest rating given by any user is 1.
 
**- Distplot to show the probability of total ratings**

<img width="600" alt="distplot_total_ratings" src="/images/distplot_total_ratings.png">
 
 
From the above graph we can see that the majority of the products have less than 100 ratings and the number of products having more than 100 ratings is very low.
 
 
**- Jointplot for mean ratings and total ratings**

<img width="450" alt="joint_plot_ratings" src="/images/joint_plot_ratings.png">
 
 
Here, as you can see every Data Point represents a distinct product, with y-coordinate representing the total number of users which have rated that product and x-coordinate representing the mean of all the ratings of the corresponding users.
Also you can see that there is a huge Density in the region corresponding to 0-1000 no of users and between mean rating 3.5-5


# Models
Recommendations are mainly of two types: personalized and non-personalized. In personalized recommendations, different users receive different suggestions. In non-personalized recommendations, all the users get same suggestions. 

Recommended Systems are mainly classified into the 6 types: 

1.Popularity based systems :- These systems provide items that are viewed and purchased by most people and which are highly rated.

2.Classification model based:- This model tries to understand the features of the user and then applies the classification algorithm to decide whether the user is interested in the prodcut or not.

3.Content based recommedations:- This model is mainly based on the information of the contents of the item rather than on the user opinions.

4.Collaberative Filtering:- This model works on assumption that people like things similar to other things they like, and things that are liked by other people with similar taste. It is mainly of two types: a) User-User b) Item -Item

5.Hybrid Approaches:- This method combines collaborative filtering, content-based filtering, and other approaches.

6.Association rule mining :- Association rules capture the relationships between items based on their patterns of co-occurrence across transactions.

From the above classified methods of Recommended Systems we decided to implement Popularity Based Recommended systems, User Based Collaborative Filtering and Item based Collaborative Filtering methods. We are not using Content based recommender systems because it recommends products or items based on their description or features. We don’t have any features or descriptions provided in our dataset that can be used for content based. 

# Comparisons

From the visualiation of the data in the above section. Lets look at what are the conslusions we make and what are the models we are planning to use.

1.Popularity based systems:- This method we can use when we encounter a cold start problem. As you will see below we are planning to use Collaberative Filtering for our Recommendation System. But this method is user-user or user-Product Recommendation system. That means we need to have history of that particular user or Product to find a similar entity. But this will not be the case for new users or new products. So we have implemented a Popularity based recommendation system which will recommend the top 10 highest rated Products.

2.Content based recommedations:- As we can see from the data visualization above there are not enough attributes to the data, infact there no attributes to the product except for the ratings. So Content based recommendation cannot be a vaiable option for our recommendation system for this particular data set.

3.Collaberative Filtering:- By looking at the attributes available in the dataset that describe the Product(which is only user Ratings). And also by looking at the clear User-User and User-Product connection from the data. We have decided that Collaberative Filtering will be the apt method for our recommendation system. 

We are working on different models like cosine similarity,SVD and KNN to acheive the required results and will update the results once we are done with the work.

# Example Analysis

# Conclusions


# References
