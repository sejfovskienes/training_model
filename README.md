Gold Price Prediction Notes
Hypothesis 1
After training the model and trying to optimize it, I decided to perform a greedy search on some of the parameters.

For example, I noticed that the parameter group Close_pct_change{i}, which represents the percentage change of the Close column over the previous days, slightly improves the prediction performance.

I will implement a greedy search logic to identify the point at which this improvement stops contributing to model optimization.

Update: R² score increased.

Hypothesis 2
After conducting a greedy search for the optimal number of lags to track the gold price trend, we observed increased model performance.

Now we are going to test the hypothesis that the same method can be applied to the interest level and inflation rate.

Major Update
We are migrating to a new dataset to support the inclusion of more macroeconomic and technical indicators.
