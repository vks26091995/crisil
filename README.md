# crisil
## Problem and Approach
The task involves building a predictive model that uses both structured financial/market data and unstructured text data to predict or explain the rating of a company (e.g., A+, BBB) or another related target (like future performance). The dataset provided contains:
1.	Structured Financial/Market Features: These are numerical or categorical variables representing market and financial data such as company performance indicators (e.g., FundaIndxint, monthvwretd, monthsprtrn).
2.	Categorical Rating Columns: The columns RATING_TYPE and Rating provide categorical data representing company ratings, which are the target of prediction (e.g., company credit rating or investment rating).
3.	Unstructured Text: The string_values column contains short textual statements that describe company performance or market conditions. These are qualitative features that can potentially provide rich insights into the company's status.
The challenge is to combine these two types of data (structured and unstructured) effectively to build a model that can predict or explain company ratings.

# Approach:
1.	**Data Preprocessing:**
o	Structured Data: Clean and preprocess the financial features (e.g., handle missing values, outliers, scale numerical features, and encode categorical variables).
o	Text Data: Process the textual data by cleaning (removing stop words, stemming/lemmatization), tokenizing, and transforming it into numerical features using  "nlptown/bert-base-multilingual-uncased-sentiment" model
2.	**Feature Engineering:**
o	Structured Features: Utilize techniques like normalization, encoding categorical variables (e.g., one-hot encoding).
o	Text Features: Use pre-trained word embeddings to convert the string_values column into meaningful features that capture the sentiment, themes, or nuances of the text.


3.	**Modeling:**
o	Fusion Model: Combine both types of features (structured + text) in a single model. Potential approaches:
	Use a Regressor model (e.g.,Linear Regression, Random Forest Regressor for structure data analysis).
	Use classical machine learning methods (e.g., random forest classifier) for structured data and incorporate textual features by using feature engineering methods like Onehot encoding for multiclass classification.
	Explore ensemble methods that combine the predictions from models trained on each type of data separately.
4.	**Model Evaluation:**
o	Evaluate the model using suitable metrics based on the task (classification accuracy, precision, recall for categorical rating prediction) and  (RMSE,mse,r2 for predicting a continuous score).
5.	**Post-Modeling Analysis:**
o	Interpret the results to understand the key drivers of company ratings, both from the structured financial features and textual features.
o	visualize the contribution of each feature using feature importance




