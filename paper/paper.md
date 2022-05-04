---
title: Product Recommender System Based on the Ratings
date: "3rd May 2022"
authors: Vineet Kiragi, Sai Santhosh, Supriya, Saroja, San José State University

header-includes: |
  \usepackage{booktabs}
  \usepackage{caption}
---

# Abstract

The bussiness of online shopping thrives on recommending the right product to the right user. Recommending products to an user based on the ratings he has given to similar products might entice the user to buy more Products. So we are trying to create a Recommendation System which with an acceptable accuracy predict the Beauty products a user might like and probably buy depending upon the ratings he/she has given to other Beauty Products. This will help E-Commerce companies(in our case Amazon) make better product placements. Better product placements inturn ensures their product marketing actually reach the corrected most probable potential buyers, inturn generating much more revenue and also better returns on money spent of marketing in per dollar terms.

# Introduction
In today's world we are overloaded with data which provides us the useful information. But it's not possible for the user to get the information in which they are interested in from the available data. In order to help the user to find out information about the product, recommedation systems are developed.

Recommeder system helps in creating a relation between the user and items and utilizes the similarity between user/item to make recommendations.
Many popular Ecommerce sites widely use Recommended Systems to recommend news, music, research articles, books, and product items. More the development of e-commerce websites more is the need emerged for providing recommendations compiled from filtering the whole range of available options.With a wide variety of options that are provided to the users from multiple websites, users find it very difficult to make the most appropriate choices.

The objective of this project is to develop a recommended system for beauty products that are sold on Amazon based on the reviews and ratings provided for the products. This dataset contains product reviews and metadata from Amazon, including 142.8 million reviews spanning May 1996 - July 2014.

This is a dataset related to over 2 Million customer reviews and ratings of Beauty related products sold on their website.

It contains

● userId : Every user identified with a unique id

● productId : Every product identified with a unique id

● Rating : Rating of the corresponding product by the corresponding user

● timestamp : Time of the rating ( ignore this column for this exercise)

So by trining the data using different methods we will develop a recommended system.

# Methods
Recommendations are mainly of two types: personalized and non-personalized. In personalized recommendations, different users receive different suggestions. In non-personalized recommendations, all the users get same suggestions. 

RSs are mainly classified into the 6 types: 

1.Popularity based systems :- These systems provide items that are viewed and purchased by most people and which are highly rated.

2.Classification model based:- This model tries to understand the features of the user and then applies the classification algorithm to decide whether the user is interested in the prodcut or not.

3.Content based recommedations:- This model is mainly based on the information of the contents of the item rather than on the user opinions.

4.Collaberative Filtering:- This model works on assumption that people like things similar to other things they like, and things that are liked by other people with similar taste. It is mainly of two types: a) User-User b) Item -Item

5.Hybrid Approaches:- This method combines collaborative filtering, content-based filtering, and other approaches.

6.Association rule mining :- Association rules capture the relationships between items based on their patterns of co-occurrence across transactions.


# Comparisons

# Example Analysis

# Conclusions


# References
