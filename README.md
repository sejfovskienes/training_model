After training the model and trying to optimize it, I decided to perform a greedy search on some of the parameters.
For example, I noticed that the parameter group Close_pct_change{i}, which represents the percentage change of the Close column over the previous days, slightly improves the prediction performance.
I will implement a greedy search logic to identify the point at which this improvement stops contributing to model optimization.
