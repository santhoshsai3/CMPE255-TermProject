---
title: Product Recommender System Based on the Ratings
date: "3rd May 2022"
authors: Vineet Kiragi, Sai Santhosh, Supriya, Saroja, San José State University

header-includes: |
  \usepackage{booktabs}
  \usepackage{caption}
---

# Abstract

The business of online shopping thrives on recommending the right product to the right user. Recommending products to an user based on the ratings he has given to similar products might entice the user to buy more Products. So we are trying to create a Recommendation System which with an acceptable accuracy predict the Beauty products a user might like and probably buy depending upon the ratings he/she has given to other Beauty Products. This will help E-Commerce companies(in our case Amazon) make better product placements. Better product placements inturn ensures their product marketing actually reach the corrected most probable potential buyers, inturn generating much more revenue and also better returns on money spent of marketing in per dollar terms.

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

So by training the data using different methods we will develop a recommended system.

# Methods
Recommendations are mainly of two types: personalized and non-personalized. In personalized recommendations, different users receive different suggestions. In non-personalized recommendations, all the users get same suggestions. 

Recommended Systems are mainly classified into the 6 types: 

1.Popularity based systems :- These systems provide items that are viewed and purchased by most people and which are highly rated.

2.Classification model based:- This model tries to understand the features of the user and then applies the classification algorithm to decide whether the user is interested in the prodcut or not.

3.Content based recommedations:- This model is mainly based on the information of the contents of the item rather than on the user opinions.

4.Collaberative Filtering:- This model works on assumption that people like things similar to other things they like, and things that are liked by other people with similar taste. It is mainly of two types: a) User-User b) Item -Item

5.Hybrid Approaches:- This method combines collaborative filtering, content-based filtering, and other approaches.

6.Association rule mining :- Association rules capture the relationships between items based on their patterns of co-occurrence across transactions.

From the above classified methods of Recommended Systems we decided to implement Popularity Based Recommended systems, User Based Collaborative Filtering and Item based Collaborative Filtering methods. We are not using Content based recommender systems because it recommends products or items based on their description or features. We don’t have any features or descriptions provided in our dataset that can be used for content based. 


# Preliminary Analysis
We will be seeing differnt data visualization and exploration techniques below as part of understanding the data.
# Data Exploration
This dataset has been taken from kaggle which consists of over 2 Million customer reviews and ratings of Beauty related products sold on their website.
The dataset consists of the following features:

<img width="347" alt="Screen Shot 2022-05-03 at 10 08 59 PM" src="https://user-images.githubusercontent.com/93508580/166625846-1eb43160-f687-4db1-bf71-ea931b2b0f25.png">
Since there are large no of samples in the dataset. We can assume the dataset probably covers a wide range of users and the resulting conclusions on the data are also satisfactory.

The figure shows if there are any missing values for these features. 

<img width="264" alt="Screen Shot 2022-05-03 at 10 14 49 PM" src="https://user-images.githubusercontent.com/93508580/166626259-eb4b28c4-7c32-492a-8840-27f0d2ff9373.png">
The dataset doesnt contain any null values or misplaced values. So in that way dataset is completely clean and doesnt need data cleaning in terms of missing values and noise.

# Data Cleaning

As part of data cleaning we checked for any missing values or duplicates and we found that there are no missing values or duplicates. So the data is clean to a certain extent. Once this is done we tried analyzing the relationship between user and the products and this dataset is mainly based on the ratings that are provided by the user for every product. As part of this we analyzed scenarios like the number of rated products per user and the number of ratings for per product which are shown below. From this we understood which user has given the max/min number of ratings and which product has the max/min number of ratings. 


We can see if there are any duplicate or non unique values as follows

<img width="691" alt="Screen Shot 2022-05-03 at 10 25 40 PM" src="https://user-images.githubusercontent.com/93508580/166627006-dfe170e7-73ef-42be-b965-f8b32b9996bf.png">

As we can see there are no duplicate records nor any missing data to be handled as part of cleaning.

# Data Analysis

As part of data analysis we analysed some scenarios as below:

1.The number of rated products per user

<img width="264" alt="Screen Shot 2022-05-03 at 10 29 55 PM" src="https://user-images.githubusercontent.com/93508580/166627311-bda768d7-346b-4fdb-80a6-5fd08dbb845b.png">



2. The Number of ratings per product

<img width="262" alt="Screen Shot 2022-05-03 at 10 30 43 PM" src="https://user-images.githubusercontent.com/93508580/166627363-0ac1b7c4-5ac0-450a-b2d4-6fcb7057dc92.png">

3. The Number of products rated by each user

<img width="411" alt="Screen Shot 2022-05-03 at 10 31 57 PM" src="https://user-images.githubusercontent.com/93508580/166627441-5fddf7b1-1ac9-429f-865b-8597af62d6bf.png">

<img width="367" alt="Screen Shot 2022-05-03 at 10 32 13 PM" src="https://user-images.githubusercontent.com/93508580/166627462-a697423b-e9b5-4638-84ee-be6fbbd671da.png">

# Data Visualization

After analysing the data we made data visuaization using different graphs and charts. Below is the plot showing the total number of users and products with respect to the size of the dataset.


<img width="1264" alt="Screen Shot 2022-05-03 at 10 40 09 PM" src="https://user-images.githubusercontent.com/93508580/166628050-b06aafd3-4c44-43aa-a889-7785e9755bc2.png">

So here we can see there are only 3 attributes to the data that re ProductID, UserID and the ratings for different combinations of these two. There is also time stamp which is not of more use for us. From the above graph we can see that there are actually enough no of data samples to make a recommendation system with satisfactory conclusions.

From the above graph we can also see that the Total size of records is much higher than the no of unique users and no of unique products. That means there are range of rating values for different combination of users and Products. Which makes this dataset a perfect fit for Colloberative Filtering.

A bar plot is plotted to show the ratings given by the users and the mosted rated products

<img width="1285" alt="Screen Shot 2022-05-03 at 10 44 23 PM" src="https://user-images.githubusercontent.com/93508580/166628372-2a8d94a5-4e2a-4b2c-a75d-1f2a3d60a901.png">

From the above we can see that the ratings from all the user tends to be on the higher side which gives rise to posibility of user bias. To eliminate this noramlization can be done as explained below.

<img width="1276" alt="Screen Shot 2022-05-03 at 10 45 24 PM" src="https://user-images.githubusercontent.com/93508580/166628449-9ea9eec2-b535-4eb8-900c-1fad60c3f7e8.png">

Here we can see some products tend to have more no of ratings than other. In some cases its disproportionately higher. So to eliminate this we have filtered out the products keeping a threshold for minimun no of ratings.

In order to find the average rating provided by individual users we plotted a histogram by grouping the userid aganist the ratings and also to show the number of ratings per product

<img width="1237" alt="Screen Shot 2022-05-03 at 10 47 04 PM" src="https://user-images.githubusercontent.com/93508580/166628556-653ff13c-9b89-4807-9c12-e8c825f6dc74.png">

<img width="1231" alt="Screen Shot 2022-05-03 at 10 49 07 PM" src="https://user-images.githubusercontent.com/93508580/166628691-f8d9c0b1-9f6d-42de-ab77-b10c8f3a48fa.png">

A box plot is used to show how ratings data is distributed


<img width="430" alt="Screen Shot 2022-05-03 at 10 50 38 PM" src="https://user-images.githubusercontent.com/93508580/166628785-e52df916-80b0-4930-9b84-7825f8c3d6ce.png">

Similarly we are using violin plot for ratings feature to depict summary statistics and the density.

<img width="399" alt="Screen Shot 2022-05-03 at 10 51 20 PM" src="https://user-images.githubusercontent.com/93508580/166628839-7e889fbd-be8e-47a1-ae91-5f62a0a4a7e5.png">

From the above two graphs we can see that most user have rated the products very highly as the concentraion of the ratings is fairly on the higher end. So to eliminate this bias where some user tends to rate Products very leninetly we have normalized the ratings by substracting average rating value from each rating.

# Comparisons

From the visualiation of the data in the above section. Lets look at what are the conslusions we make and what are the models we are planning to use.

1.Popularity based systems:- This method we can use when we encounter a cold start problem. As you will see below we are planning to use Collaberative Filtering for our Recommendation System. But this method is user-user or user-Product Recommendation system. That means we need to have history of that particular user or Product to find a similar entity. But this will not be the case for new users or new products. So we have implemented a Popularity based recommendation system which will recommend the top 10 highest rated Products.

2.Content based recommedations:- As we can see from the data visualization above there are not enough attributes to the data, infact there no attributes to the product except for the ratings. So Content based recommendation cannot be a vaiable option for our recommendation system for this particular data set.

3.Collaberative Filtering:- By looking at the attributes available in the dataset that describe the Product(which is only user Ratings). And also by looking at the clear User-User and User-Product connection from the data. We have decided that Collaberative Filtering will be the apt method for our recommendation system. 

We are working on different models like cosine similarity,SVD and KNN to acheive the required results and will update the results once we are done with the work.

# Example Analysis

# Conclusions


# References
