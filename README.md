## Exploring Yelp Business Dynamics Through Data Mining
University of Chicago - Data Mining Principles Final Project

#### Business Problem
Yelp, established in 2004, has grown into one of the leading platforms for local business discovery and reviews, serving as a critical bridge between businesses and consumers. With millions of reviews and business listings, Yelp offers a rich dataset that provides insights into consumer preferences, business performance, and market dynamics. 

Utilizing the Yelp dataset for analyzing business onboarding standards presents a compelling opportunity for enhancing the symbiotic relationship between the platform and its associated businesses. The primary objective is to dissect the multitude of factors influencing the star ratings on Yelp, ranging from customer reviews, ratings, location, and service categories, to the nuances of customer engagement and response strategies. 

The analysis of Yelp’s extensive dataset seeks to address the critical challenge of assessing store quality and enhancing the recommendation system by focusing on the diverse features that influence a business’s star ratings. By delving into factors such as customer reviews, service categories, and engagement strategies, this study aims to refine onboarding criteria and best practices for businesses, ensuring a high-quality and diverse selection for users. Ultimately, this effort intends to bolster a symbiotic relationship between Yelp and its associated businesses, fostering an ecosystem where both parties thrive and contribute to a richer, more engaging platform.

#### Data Source: https://www.yelp.com/dataset

### Definition & Scope of Features

#### Overview
- ****73 Features Considered****
- ****5 Dataset for Analysis****

### Main Categories for Features:

#### Business:
- **8** Key Points
  - Service options (Takeout, caters)
  - Dining experience (ambience, outdoor seating)
  - Presence of amenities (e.g., TV, Wi-Fi, parking)

#### Review:
- Sentiment scores
- Frequency of positive/negative words
- Length of review

#### User Engagement:
- Number of reviews received
- Average stars are given by the user
- Number of friends
- Elite status duration

#### Temporal Data:
- Check-in times
- Frequency of reviews over time
- Temporal patterns in user activity
- Tips information

### Data Exploration and Modeling Framework

#### Data Sets Overview

- **5 Data Sets:** Business, User, Review, Check-in, Tips
- **150,346 businesses** - Location, ratings, attributes
- **1,987,897 users**
- **6,990,280 reviews** - Reviews with rating and text
- **908,915 tips** - User tips with text and compliment
- **131,930 check-ins** - User check-ins at business

#### Data Exploration

#### Data Description

- **Primary Unit**
  - Businesses: Evaluated through ratings, categories, and attributes.
  - Users: Analyzed via reviews, tips, and engagement metrics.
- **Secondary Unit**
  - Reviews: Insights on customer satisfaction and feedback.

#### Limitation & Delimitation

- **Subjectivity:** Check-in and tips, being subjective, might introduce bias in understanding business quality so we didn’t incorporate in feature engineering.
- **Focus Area:** Analysis centers on user interactions, review and business-related metrics.

#### Feature Engineering

- **Text Features:** Identify significant words or phrases (TF-IDF).
- **Truncated SVD:** Avoid sparse matrix issue since user compliment/feedback/fans have a lot zeros.
- **One-Hot Encoding:** Each category value is converted into a new column and assigned a 1 or 0 (notation for true/false) value to the column.

#### Validation

- **Cross Validation:** Employ cross-validation techniques to ensure model reliability across different subsets of data.

### Methodology

#### Model Descriptions

- **Baseline:** Linear Regression
- **Non-Linear:**
  - SVM (linear & non-linear)
  - Decision Tree
  - Random Forest
  - AdaBoost
  - XGBoost
- **Customized Ensemble Model:** Stacking the base models above using Bayesian Ridge Regression

### Model Selection and Validation

- **Model Performance Evaluation:**
  - CV error > training set error: overfitting
  - CV error ≈ training set error >> test set error: underfitting
- **Randomized Search Cross-validation (5-fold)** was employed to assess model generalizability, with RMSE (Root Mean Squared Error) as the performance metric to compare different models' predictive accuracy.
