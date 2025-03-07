# Bank Term-Deposit Subscription Prediction

This repository contains a machine learning project that explores how to predict whether a client will subscribe to a term deposit. The primary motivation is to assist a company specializing in telemarketing for term-deposit subscriptions by providing data-driven insights and predictive models that can enhance targeting and overall campaign performance.

## Table of Contents

- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Data Description](#data-description)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Data Preprocessing & Feature Engineering](#data-preprocessing--feature-engineering)
- [Model Development & Evaluation](#model-development--evaluation)
- [Results & Discussion](#results--discussion)
- [How to Run the Project](#how-to-run-the-project)
- [Dependencies](#dependencies)
- [Repository Structure](#repository-structure)
- [Future Work](#future-work)
- [Acknowledgements](#acknowledgements)

## Project Overview

This project leverages machine learning techniques to address a real-world marketing problem for a financial institution. Using a dataset that contains information about clients and their responses to previous marketing campaigns, we built and evaluated several machine learning models which attempt to predict whether a client will subscribe to a term deposit. The end goal is to help the company refine its phone-based sales strategy and allocate resources more efficiently.

Our machine learning product consists of three sections. The first section is a 'Customer Model', which takes as inputs features that are related to customers. Here, we attempt to create a classification model that predicts whether a customer is likely to subscribe to our product, ignoring any features related to our company's advertising campaign. The main goal of this model is to cut down on the unnecessary calls made to customers who are unlikely to subscribe. By doing this, we save the company significant costs related to these unnecessary calls (a reduction in 44% of calls overall). 

The second section is a 'call model', which takes as inputs all our features related to the customer and number of calls made to them. Here, we attempt to create a classification model that accurately predicts whether a customer will subscribe to the product or not. Here, we attempt to understand what combination of customer features and advertising campaign strategies makes a sale. Thus, we can make recommendations to our calling staff, suggesting ways to improve their likelihood of making a sale to their customers. 

The third and final part consists of an unsupervised machine learning model for our subscribers base. Here, we attempt to understand the main groups in our subscriber base, in order to make recommendations to our callers for which general demographics to target. This section can be seen as an extension/accompinement to our Customers Model.

## Motivation

Telemarketing can be expensive and time-consuming. By applying predictive modeling to the available client data, the project aims to:
- **Improve Targeting:** Identify high-probability prospects to optimize marketing efforts.
- **Increase Efficiency:** Reduce costs by focusing on leads that are most likely to convert.
- **Enhance Strategy:** Provide actionable insights that can inform broader marketing and customer relationship strategies.

## Data Description

The dataset used in this project contains various client attributes such as:
- **Demographic Information:** Age, job type, marital status, education.
- **Financial Status:** Balance, housing loan status, personal loan status.
- **Campaign Data:** Contact details, previous marketing campaign outcomes, and more.
- **Target Variable:** Whether the client ultimately subscribed to a term deposit.

## Exploratory Data Analysis (EDA)

In the Jupyter Notebook, a thorough EDA was performed to:
- **Understand the Data Distribution:** Visualizing distributions of key features and identifying potential outliers.
- **Examine Relationships:** Analyzing correlations between variables and their relationship with the target variable.
- **Identify Imbalances:** Noting any class imbalances which can affect model performance.

Visualizations such as histograms, box plots, and correlation heatmaps were used to gain insights into the data structure.

## Data Preprocessing & Feature Engineering

The following preprocessing steps were implemented:
- **Handling Missing Values:** Imputation strategies were applied where necessary.
- **Encoding Categorical Variables:** Techniques like one-hot encoding and label encoding were used to transform categorical data.
- **Scaling & Normalization:** Numerical features were scaled to improve model convergence.

These steps ensured that the data was in the best possible shape for model training.

## Model Development & Evaluation

Multiple machine learning models were developed and compared, including:
- **Customer Model:** Here we experimented with a variety of classification models, and found that a decision tree classifier model performed the best.
- **Call Model:** Here, we experimented with a variety of models, and found that a soft-voting ensemble model, made up of a logistic regression, SVC and decision tree classifier worked the best.
- **Unsupervised Learning Model for Subscriber Base:** Here, we implemented a K-means++ model, examining the 6 main clusters in our subscribers base.

Each model was evaluated using metrics such as accuracy, precision, recall, F1 score, and ROC AUC. Hyperparameter tuning was performed to optimize model performance. Cross-validation techniques ensured the robustness and generalizability of the results.

## Results & Discussion

The evaluation results provided insights into:
- **Model Performance:** Which models performed best in terms of predictive accuracy and recall for the positive class.
- **Feature Importance:** Key drivers influencing term-deposit subscriptions, which can inform business decisions.
- **Trade-offs:** Discussion on the balance between false positives and false negatives in the context of the marketing campaign.

The main takeaways from analysis of our models are the following:

- **Customer Model:** Our model managed to cut down all calls by 44%, drastically reducing costs, while maintaining 76% of potential clients. Analysis from our models indicated that our callers should target an older demographic with significant funds in their bank account.
- **Call Model:** Our model achieved an overall accuracy of 89% and a recall score of 71%. Analysis from our models indicated that our callers should try to speak for as long as possible, and call potential customers later in the month.
- **Unsupervised Learning Model for Subscriber Base:** Most of the clusters in our subscribers base consisted of older individuals wiht significant funds in their bank accounts. However, an important cluster in our database consisted of younger, very wealthy and educated demographic. Therefore, we recommend that our callers continue targetting this demographic, along with the older and richer one.
## How to Run the Project

### Data Analysis using Tableau

Data Analysis I have performed using Tableau can be found [here](https://dub01.online.tableau.com/#/site/alexanderkneale109-5655d79c05/projects/892499?:origin=card_share_link). 

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/alexkneale/apziva_project_2.git
   cd apziva_project_2
