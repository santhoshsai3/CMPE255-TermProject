# Product Recommender System Based on the Ratings



## Contents
* Understanding Recommender System
* Quick Start
* Folder Structure
* Installation
* Steps to run the Project
* Dataset
* Problem being investigated
* Data Science Life Cycle
* Conclusion
* Contributors


## Understanding Recommender System

![image](https://user-images.githubusercontent.com/90812789/169641899-81540bf0-9c19-47d2-b6b3-e3960c3219e4.jpeg)


Nowadays, all of the well-known firms such as Netflix, YouTube, Amazon, Facebook, Spotify, and others have become successful as a result of one method: the recommendation system, which benefits both consumers and businesses.

Online shopping is all over the internet . All our needs are just a click away. The biggest of them all is the website AMAZON. The one thing that Amazon is known for other than the variety of products it sells. It's very powerful and accurate recommendation system. A website such as Amazon is built on the business model of recommending the right products to the right user. Successfully doing this might result in a huge revenue jump for the company. Here we are trying to build a recommendation product system based on the previous purchase patterns and ratings.

It suggests to customers the most often viewed products, as well as related products with high ratings, to assist individuals in online shopping in finding the perfect product.

## Installation
Installation of the packages available in requirements.txt before running the code.

* pip install -r requiremnts.txt 

### Steps to run the project

* Install the code Zip file from the above Git repo in your system's local folder and execute the scripts in the terminal.

      $ git clone https://github.com/santhoshsai3/CMPE255-TermProject.git
      
* Navigate to the code folder to run the ipynb files in jupyter notebook.

## Drive Link
The drive link contains the recording of out presentation and also the ppt. [here](https://drive.google.com/drive/folders/1IxE4bAtqsOXTbo2FfDR3597ojpM-5KwY?usp=sharing)

## Dataset
Dataset:  We are using a dataset from Kaggle from the link below.
https://www.kaggle.com/datasets/skillsmuggler/amazon-ratings?select=ratings_Beauty.csv
The CSV consists of around 12 lakh items and 4 columns. The dataset contains lakhs of rows for user id, the product id and the corresponding ratings that particular user has given to that particular product. 


## Problem being investigated
Many online systems have recommender systems as an inherent feature. From online streaming platforms to e-commerce.
Recommender systems use the user's previous purchase history to anticipate which other products they might be interested in and likely to buy. Recommending the proper products provides the company a huge edge. Recommendations account for a significant amount of the revenue. 

We intend to use memory-based distance proximity techniques such as cosine distances and nearest neighbors, as well as model-based techniques such as Single Value Decomposition, which factors a matrix into a single value and single vector. We may also use Jackard similarity to play with data. Customers connect with particular products (in our case, beauty products) and rank them using the Collaborative Filtering approach, which is widely utilized in streaming platforms and e-commerce sites.

## Data Science Life cyle
### 1. Data Preprocessing
* Data Exploration
* Handling Outliers

### 2. Data Analysis
* Analyzing the Dataset

### 3. Data Visualization
* Visualizing the data using bar plots, Box plots and violin plots.

### 3. Data Modelling
* Popularity Recommendation model
* Cosine Similarity
* KNN
* SVD

### Contributors
* Sai Santhosh Yamsani
* Saroja Kandula - 015911467
* Supriya Bhupathiraju
* Vineet Kiragi








