# Canadian Housing Regression Analysis

## Data Preparation

### To prepare for analyses, all of the missing values were handled. Repetitive data was removed or categories were joined. Rows with missing values were removed or values were filled with means or modes for categorical variables. Outliers were removed from variables of interest (price, beds, baths, square feet). 

## Feature Selection 

### After encoding the data, features with the greatest correlation with the target variable, price, were selected. Polynomial features were used to allow flexibility in the relations between the variables. A loop was used to find the optimal polynomial degree. The data was then split using a train/test split on the polynomial features, and scaled. 

## LassoCV Model 

### The data was fit to a LassoCV model. The RMSE was quite high and many features were considered by the model. The high RMSE could be partcially explained by the scale of the data, since the target variable is in the thousands. 

## ElasticNetCV Model 

### The data was fit to an ElasticNetCV model next. The RMSE was the same and it also produced many coefficients from considering many features. The model used solely L1 regression. 

## GridSearchCV Model

### For the final model, LassoCV was used for a GridSearchCV model. To improve the previous models, more outliers were removed from the target variable, price, that could have been skewing the data. More variables were considered for x. This created a slightly lower RMSE compared to the previous models, though it was still quite high. Using a random sample from the data to test its predictive potential, as expected it was off by quite a bit. 
