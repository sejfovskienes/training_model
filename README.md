-hypothesis: 1 
After training the model and trying to optimize it, I decided to perform a greedy search on some of the parameters.
For example, I noticed that the parameter group Close_pct_change{i}, which represents the percentage change of the Close column over the previous days, slightly improves the prediction performance.
I will implement a greedy search logic to identify the point at which this improvement stops contributing to model optimization.
***update: r2 score increased

-hypothesis: 2
After greedy search for the optimal number of lags to track the gold price trend we increased the performance of the model. Now we are going to test the hypothesis if same method can be applied for the interest level, and inflation rate.
