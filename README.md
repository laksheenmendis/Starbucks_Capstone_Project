# Table of Contents
   
   1.[Project Overview](#project-overview)
  
   2.[Problem Statement](#problem-statement)
  
   3.[Metrics](#metrics)
   
   4.[File Descriptions](#file-descriptions)
   
   5.[Blog Post](#blog-post)
   
   6.[Acknowledgements](#acknowledgements)


# Project Overview

Among several other project options, I chose the Starbucks project, as my capstone project for Udacity Data Scientist Nanodegree. This data was provided by Starbucks to simulate their customers and transactions, to see if there are better approaches to sending out promotional deals to customers.

The different files that were used to create this project are located in data folder, as json files. Here is a quick overview of them:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

#### portfolio.json

* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) -
* channels (list of strings)

#### profile.json

* age (int) - age of the customer
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

#### transcript.json

* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

# Problem Statement

The problem which I will be solving in this project is whether a particular customer will respond positively to a particular offer sent out by Starbucks. In brief, my strategy for solving this problem is by combining all of the 3 datasets (portfolio, profile and transcript). However, combining these data will not be very easy and straightforward. (To get a much deeper understanding, please follow the steps and comments in Starbucks_Capstone_notebook.ipynb).

After processing these datasets, I will have a feature dataset and a target vector, which could be used to train classification models. The target vector would have a boolean value, which depicts whether a customer accepted a particular offer. The classification model I will be using are namely; Decision Tree, Support Vector Machine, Random Forest and Gradient Boosting. 

# Metrics

I will use accuracy and F1-score as metrics to evaluate performance of each classification model. Accuracy measures how well a model correctly predicts the final label. However, we cannot solely depend on accuracy, because it has several deficiencies. Measuring precision and recall of a model is more reliable and provides better insight to its performance. Hence, I chose F1-score which is a weighted average of the precision and recall metrics.

# File Descriptions

1. Starbucks_Capstone_notebook.ipynb

Jupyter Notebook that shows the beginning to end of the this project. This starts with loading datasets, then data exploration and preprocessing steps. Finally, you can find the data analysis steps which include training multiple models and picking up the most suitable one for the problem.

2. customer_offer.pkl

An intermediate dataframe, which contains customer_id, offer_id and completed columns. This is saved as a pickle file. And the creation of this dataframe, has been commented out in the 'Starbucks_Capstone_notebook.ipynb' because it is time consuming.

3. customer-transaction.pkl

An intermediate dataframe, which contains customer_id and avg_amount_spent columns. This is saved as a pickle file. And the creation of this dataframe, has been commented out in the 'Starbucks_Capstone_notebook.ipynb' because it is time consuming.

4. final-df.pkl

The final dataframe which is being used to train the models. This is saved as a pickle file. This was basically needed during the development stage, to avoid running all of the cells in the 'Starbucks_Capstone_notebook.ipynb' notebook.

# Blog Post

Below is the link to the blog written about this project
https://medium.com/@cresclux/which-customers-will-respond-to-starbucks-offers-1421365d7a4e

# Acknowledgements

Must give credit to Starbucks for providing these datasets and letting students work on it as a capstone project.
