NG MANYI ALPHANIA

ng.alphania@gmail.com

### Overview of the submitted folder and the folder structure.
* src (folder) : contains regression.py
* data (folder) : used to store retrieved/ downloaded data and geojson file.
* root folder : contains README.md, requirements.txt, config.yaml and eda.ipynb

### Instructions for executing the pipeline and modifying any parameters.
The following parameters are in the config.yaml file and the variables defined at the start of the .py file could be amended for ease of running the pipeline.

Within config:
* Data path
* Table name
* Target
* Training size

At start of py file:
* Numerical columns to execute standard scaler
* List of models to be evaluated

### Description of logical steps/flow of the pipeline. 
* Setting up the enviroment (importing libraries)
* Loading the data (either to read from local or url)
* Data preprocessing steps (as defined and explained in eda.ipynb)
* Split data into training and test sets
* Standard scale selected numerical columns
* Log transform target variable
* Run models
* Evaluate performance on exponential of results (due to previously log transformed target) and obtain best RMSE score

### Overview of key findings from the EDA conducted in Task 1 and the choices made in the pipeline based on these findings, particularly any feature engineering.
Based exploratory data analysis the following data preprocessing steps are performed
* Change type. 'date' to datetime, after performing fuzzywuzzy of the textual date which had spelling errors
* Dealing with Missing Values 
> Drop all na records from important columns id, price, date, lot_size and living_room_size as they are critical to the model. 
> Removed review_score column due to high number of missing data and seemingly no correlation to price.
> Drop all na records from remaining columns. 

* Other Preprocessing Steps
> Drop rows where 'date' in Mar 2014 is irregular as the dataset mainly begins from May 2014  (no Apr 2014).
> Drop rows where 'bathrooms' and 'bedrooms' is 0.
> Numerous duplicate data were noted. Thus, removed rows (i.e. keep only one of, and last) where (1) all records are duplicate (2) id is duplicate

* Feature Generation - 
> Add 'built_age' which will contain the age of the home at the date of sale.
> Add 'renovation_age' which will contain the age of the renovation at the date of sale (if no renovation, use built age)
> Add 'is_renovated' data of whether the home was renovated.
> Add 'has_basement' data of whether the home has basement. 

* Drop Unnecessary columns - 
> This includes both source and generated columns as follows: ['date', 'day','month','year','month_upd','id', 'basement_size', 'built', 'renovation', 'latitude','longitude','review_score']

* Dealing with Outlier 
> Drop rows where z_score > 3 for 'price' and 'lot_size' which was very skewed.

* Normalizing Values - 
> The 'condition' column was converted to upper and converted to integer as ordinal.
> Zipcode is deemed as categorical would be converted to dummy variables prior to modelling.
> Standard scaler will be applied prior to running the model

f. Explanation of your choice of models for each machine learning task.

The following model were run for the regression experiments to explore multiple regression models and review the performance of each.
* LinearRegression
* Lasso
* Ridge
* ElasticNet
* DecisionTreeRegressor
* KNeighborsRegressor
* SVR
* SGDRegressor
* RandomForestRegressor
* GradientBoostingRegressor
* AdaBoostRegressor
* MLPRegressor

The following model were run for the regression experiments to explore multiple regression models and review the performance of each.
* LogisticRegression
* DecisionTreeClassifier
* KNeighborsClassifier
* LinearSVC 
* RandomForestClassifier
* MLPClassifier

g. Evaluation of the models developed. Any metrics used in the evaluation should also be explained.
* For regression, SVR has the best RMSE of 107K.
* RMSE is the standard deviation of the residuals (prediction errors). Residuals are a measure of how far from the regression line data points are; RMSE is a measure of how spread out these residuals are. 

* For classification, MLC has the best Accuracy of 0.7027873946479999.

## Other considerations for deploying the models developed.
* More geo-related data could be incorporated into the model considering that King County government has numerous geo-related datasets online.
* Increasing useful features could improve model performance
* Data integrity could be improved, and investigation should be done on duplicate and missing data.
* Feature selection, over sampling, grid search are additional ways to improve the model.

