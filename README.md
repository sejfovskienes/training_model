# Gold Price Prediction Notes

### Train1 
Added day and month sin and cos transformation, lags and rolling features for 'Close', 'Close sp500', 'Close usd_index', 'CPIAUCSL' columns from 1, 3 and 7 days before.
Resulted with R² Score: -0.4236 and Mean Squared Error: 0.0237.


### Train2
Dropped 'Open sp500', 'High sp500', 'Low sp500','Volume sp500', 'Open usd_index', 'High usd_index', 'Low usd_index', 'IR14270' columns. For each day the 'Open', 'High', 'Low' columns were taken from previous one.
Resulted with R² Score: -0.3996 and Mean Squared Error: 0.0233.


### Train3
Added rolling features just for the 'Close' column.
Resulted with R² Score: -0.4100 and Mean Squared Error: 0.0234.


### Train4 
Added lags for the 'Close' column for the previous 10 days. Added lags for the percentage change of the 'Close' column for the previous 1, 3, 5, 7, 14, 30th days. 
Resulted with R² Score: -0.3747 and Mean Squared Error: 0.0229.


### Train5 
Added lags for the 'Close' column for the previous 10 days. Applied greedy search for the best number of lags for the percentage change in the 'Close' column. Algorithm finded that optimal number of lags for this feature is 105 over that the model is underperforming. The dataset is saved in ../dataset/dataset_v3.csv. Progress is made ,the R² score improved by approximately 87.9%.
Resulted with R² Score: -0.0453 and Mean Squared Error: 0.0176.


### Train6 
Used the ../dataset/dataset_v3.csv. Applied greedy search algorithm for the number of lags for percentage change in 'CPIAUCSL' which resulted with R² = -0.0297 at lag = 217(slightly improved). Then also greedy search algorithm was applied for number of lags for the 'CPIAUCSL' algorithm values in the past. The algorithm find out that if we add 185 lags to each row for the 'CPIAUCSL' column the model prediction will increse in R² = -0.0109. This dataset is not saved. Added 4 more columns to the dataset for time features like 'year', 'month', 'day_of_year', 'time_index'. this dataset is saved in ../dataset/dataset_v4.csv. 
Resulted with R² Score: -0.0396 and Mean Squared Error: 0.0175.


### Train6.1 (inside train6.ipynb)
Used ../dataset/dataset_v4.csv dataset. Added sin and cos transformation for the day and month. 
Resulted with R² Score: -0.0316 and Mean Squared Error: 0.0174. 


### Train7
Used smaller version of the main dataset(from 2015 up to today). The training performs well up to some point but then predicts constant values. 
Resulted with R² Score: -0.7118 and Mean Squared Error: 0.0590.


### Train8 
Same dataset from previous training applied on a script found on internet. The results are too good to be true. Needs inspecting. This script uses Random Forest Regressor. 
update: data leakage was found: the train_test_split was made with shuffle=True parameter, because it is time series prediction it needs to be made with shuffle=False argument. 
no progress.


### Train9
Predicting gold prices using lstm and opimizing the architecture according to the error it gives.
Resulted with RMSE: 15.48 MAE: 11.92 R² Score: 0.6245


### Train10
Predicting gold prices using Random Forest Regressor.
Generally results with small positive R² Score.


### Gold_Price_Prediction.ipynb
Found this script on internet, it suprised me with the really good results but instead i found mistake in the train and test split. It was not time series prediction because of the shuffle parameter set on default by True and needed to be changed to False which resulted with bad results. 


### Train11 
Trying to divide the dataset into 98:2 train-test split ratio. performed with better results but not sure how it will perform in production. Tried to add lags to this model training method but instead performed worse. 


### Train12
Tried to combine both of lstm and random forest regression models to predict the target column. Showed to perform better then all previous methods. The work will continue in this direction to optimize the models, or balance the combining ratio between both of the models.
Results:
<img width="677" height="157" alt="image" src="https://github.com/user-attachments/assets/d4756e24-485c-47e2-823c-493560412df1" />

