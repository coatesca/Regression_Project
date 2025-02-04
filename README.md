# Canadian Housing Regression Analysis

## Data Preparation

### To prepare for analyses, repetitive data was removed or categories were joined appropriately. Rows with missing values were removed entirely or values were filled with averages, or modes for categorical variables. Outliers were removed from initial variables of interest (price, beds, baths, square feet). 

## Feature Selection 

### After encoding the data, features with the greatest correlation with the target variable, price, were selected. Polynomial features were used to allow flexibility in the relations between the variables. A loop was used to find the optimal polynomial degree. The data was then split using a train/test split on the polynomial features and subsequently scaled. 

## LassoCV Model 

### The data was fit to a LassoCV model. The RMSE was quite high and many features were considered by the model. The high RMSE could be partially explained by the scale of the data, since the target variable is in the thousands. 

## ElasticNetCV Model 

### The data was fit to an ElasticNetCV model next. The RMSE was the same and it also produced many coefficients from considering many features. The model used solely L1 regression. 

## GridSearchCV Model

### For the final model, LassoCV was used for a GridSearchCV model. To improve from previous models, more outliers were removed from the target variable that could have been skewing the data. More variables were also considered for x. This created a slightly lower RMSE compared to the previous models, though it was still quite high and more polynomial features being considered only added to the model's complexity without much improvement in terms of accuracy in its predictions. 
