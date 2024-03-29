# Natural-Language-Processing-with-Disaster-Tweets
This data science project is based on a kaggle competition! Social media is undeniably the most important platform of communication in these times. It enables people to express their feelings, thoughts or opinions in real time. Hence news agencies and disaster relief organizations use social media in monitoring for potential emergency announcements for prompt responses. This project seeks to apply natural language processing methods to build a machine learning model to classsify tweets that announce emergencies or disasters and those that do not.

## Data Description
The dataset was created by the company figure-eight however the dataset I worked with can be found [here on Kaggle](https://www.kaggle.com/competitions/nlp-getting-started/data).
Below is the Data Dictionary:

| Attributes/Variables                     | Description   | 
|:-------------------                      |:--------------|
| id                                       |Tweet ID         | 
| keyword                                  | keyword of the tweet         | 
| location                                 | location of the tweeter          | 
| text                                     | actual tweet          | 
| target (target variable)                 | whether or not the tweet announces an emergency or disaster          | 


## Project Organization
* Step 1: Exploratory Data Analysis
* Step 2: Text Vectorization
* Step 3: Fitting the Model


### Exploratory Data Analysis
* The location variable was dropped since there were a lot of missing values.
* The keyword column was dropped since that insight can be derived from the text column.
* The id column was dropped since it is irrelevant to the model prediction.

### Text Vectorization
I experimented with both the bag of words and term frequency inverse document frequency for vectorizing. 
Short recap for those not familiar: Machine learning models do not understand inputs in text form, hence the words needs to be be represented by numbers to keep the models happy. The bag of words model represents each word by the number of times it appears in each document (or tweet). The term frequency inverse document frequency on the other hand, represents each word by it's relative importance, given more weight to words that are less common across the training data and less weight to words that are more common.

### Fitting the model
Each vectorized texts (bag of words and term frequeny inverse document frequency) were fitted to a random forest model(grid searching over a range of hyperparameters). Each model gave the same result with an F1 score of 0.73. An XGBoost model on the bag of words vectorized text, performed slightly better with an f1 score of 0.74.

### Next Steps
The next step is to experiment on other vectorization techniques, to improve on the model performance.
