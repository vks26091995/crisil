# crisil
## Problem and Approach
The task involves building a predictive model that uses both structured financial/market data and unstructured text data to predict or explain the rating of a company (e.g., A+, BBB) or another related target (like future performance). The dataset provided contains:
1.	Structured Financial/Market Features: These are numerical or categorical variables representing market and financial data such as company performance indicators (e.g., FundaIndxint, monthvwretd, monthsprtrn).
2.	Categorical Rating Columns: The columns RATING_TYPE and Rating provide categorical data representing company ratings, which are the target of prediction (e.g., company credit rating or investment rating).
3.	Unstructured Text: The string_values column contains short textual statements that describe company performance or market conditions. These are qualitative features that can potentially provide rich insights into the company's status.
The challenge is to combine these two types of data (structured and unstructured) effectively to build a model that can predict or explain company ratings.

# Approach:
1.	**Data Preprocessing:**
Structured Data: Clean and preprocess the financial features (e.g., handle missing values, outliers, scale numerical features, and encode categorical variables).
Text Data: Process the textual data by cleaning (removing stop words, stemming/lemmatization), tokenizing, and transforming it into numerical features using  "nlptown/bert-base-multilingual-uncased-sentiment" model
2.	**Feature Engineering:**
Structured Features: Utilize techniques like normalization, encoding categorical variables (e.g., one-hot encoding).
Text Features: Use pre-trained word embeddings to convert the string_values column into meaningful features that capture the sentiment, themes, or nuances of the text.
3.	**Modeling:**
Fusion Model: Combine both types of features (structured + text) in a single model. Potential approaches:
Use a Regressor model (e.g.,Linear Regression, Random Forest Regressor for structure data analysis).
Use classical machine learning methods (e.g., random forest classifier) for structured data and incorporate textual features by using feature engineering methods like Onehot encoding for multiclass classification.
Explore ensemble methods that combine the predictions from models trained on each type of data separately.
4.	**Model Evaluation:**
Evaluate the model using suitable metrics based on the task (classification accuracy, precision, recall for categorical rating prediction) and  (RMSE,mse,r2 for predicting a continuous score).
5.	**Post-Modeling Analysis:**
Interpret the results to understand the key drivers of company ratings, both from the structured financial features and textual features.
visualize the contribution of each feature using feature importance

## Key Findings and Highlights
1. Out of 154 columns 151 columns are structure, 1 is unstructure and 2 is categorical from which "Rating" is target variable
2. Target variable have 8 categories which means it's a multiclass classification problem
3. Data don't have Multicollinearity.
4. Data have some outliers which are treated by using statistical method. 
5. use regressor model for structure data
6. use classification model for structure data + unstructure data for multiclass classification
7. Sentiment Analysis find out most of the comments are positive

  **NLP Business Context**
For the text:
("Challenges remain in the supply chain, but strategic investments in logistics are improving efficiencies"), the sentiment of 3 stars (Confidence: 0.4615) indicates a neutral or moderately positive outlook. Decision-makers can use this information to understand that while challenges still exist, efforts are being made to improve logistics. This could suggest the need for continued investments in supply chain strategies and monitoring of logistics progress to further reduce inefficiencies.

For the text:
("The company reported a steady increase in revenue, reflecting strong market demand"), the sentiment of 5 stars (Confidence: 0.4906) indicates a very positive outlook. This insight could inform decisions around scaling operations or investing more resources into areas that are experiencing strong market demand, capitalizing on the ongoing revenue growth.


