# Ensemble_Ada-Boost

Boosting:
Boosting is a sequential approach where models are trained iteratively, with each model focusing on the errors made by the previous ones. This technique improves accuracy and handles complex patterns.

Sequential combination of models(i.e we have 4 models all are weak learners. When we combine all the weak learners will become Strong learner). if model not able to solve any thing it will be transferred to next model. Final it will give o/p

Boosting --> Adaboost, Gradient, xgboost

Adaboost (Adaptive Boosting): Assigns weights to training samples, giving more importance to misclassified instances in subsequent iterations.

Gradient Boosting: Minimizes a loss function by iteratively adding weak learners, each correcting the errors of the previous ones.

XGBoost (Extreme Gradient Boosting): An optimized implementation of gradient boosting, known for its efficiency and performance.

Bagging reduces variance by averaging predictions from multiple models.

Boosting reduces bias by sequentially correcting errors of previous models.


# ADA BOOST

Steps

1. Assign weight to the each datapoint/row. The weight should be 1/n. n=no of rows/datapoints. Intially all weights are same.
2. Take one feature and actual o/p and calculate predicted o/p. If actual o/p and predicted o/p is same that are correctly classified.we have CGPA column(cgpa>=9 and <9). If cgpa>=9 true else false. Calculate predicted o/p and compare with actual o/p
3. Add weights which are incorrectly classified. If 2 are in correctly classified. add 2 weights=Total errror
4. calculate performance of stump=(1/2(log(1-TE)/TE))--> This will be alpha1(α1)
5. Calculate new weights. For correctly classified= wt*e^-performance of stump (α)
 
   for incorrectly classified =wt*e^performance of stump (α)

In some cases for correctly clssified we have diff weigts in that case= wt*no of instance belongs to particular weight*e^-performance of stump (α)+ wt*no of instance belongs to particular weight*e^-performance of stump (α)

7. Weights always equal to 1. if new weights are not equal to 1. calculate the total of new weights and then normalize it.
8. Normalized weight=new weight/total of new weights for each row

calculate for every feature in this way.

If all the records are correctly classified then no need to update the weight we can ignore that feature(no need to coinsder). Calculate for remaining.

one completion of all feature we need to calculated weighted average

Take predicted result for all feature along with respective α value. if yes =1 else 0.

weighted avg=α1*1+α2*1+α3*1(if all are yes. If no take take 0 in place of 1)

Final prediction will be. If wtd avg > 0 then Yes else No.

After assign the bins starts with [0+(normalized wt).

if normalized weights is 0.08 then [0-0.08] second bin starts with [0.08+wt] final bin will be [..- 1]

which bucket size is high we can select the datapoint and process to next iteration.

Then start from step-1.

![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/ada1.png?raw=true)
![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/ada2.png?raw=true)

![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/ada3.png?raw=true)
![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/ada7.jpeg?raw=true)
![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/ada6.jpeg?raw=true)
![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/ada8.jpeg?raw=true)

# Ada Boost Regressor
Follow below steps
![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/adar.png?raw=true)
![Alt text](https://github.com/srirampamerla/Ensemble_Ada-Boost/blob/main/adar2.png?raw=true)
