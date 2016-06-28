# Week 4 Day 4

# Boosting

## Objectives
- List features & benefits of boosting
- Compare & contrast boosting vs. other ensemble methods
- Learn, tune, and score a model using sklearn boosting classes
- implement the AdaBoost (additive boosting) algorithm

### Benefits of Bagging/Random Forest
- prevents overfitting
- variance goes down and bias stays the same
- we are averaging many uncorrelated trees (classifiers)
- this works great with trees that are low bias and high variance
- **Boosting** is used to lower the bias
- boosting often provides best in class performance

- we address bias by choosing the right model
- we can address variance by bagging, or using some sort of ensemble method to average out the high variance, this will result in a lower bias and a lower variance
- **For Random Forests:** we want to always use trees that are deep enough to sufficiently capture the information in our data, usually we want something 3 levels deep or more
- very deep trees are extremely variant models

### Boosting
- **eating away at the error**
- uses 'weak learners', basically crappy models that are a little bit better than random guessing
- use a stump (crappy learner), there will be a lot of errors
- train the next stump on the errors from the previous one
- the stumps are NOT independent because the decisions depend on the decisions of the others
- because they are correlated the variance is going to go up but the bias will go down a lot
- trees are slow to train but fast to predict
- stumps are high bias, low variance
- many (boosted) trees are low bias, high variance
- boosting is special in that with more and more trees, the training AND test variance will continue to go down

#### There are two main Boosting Algorithms
1. AdaBoost
2. Gradient Boosting Regression Trees

- In practice:
  1. Choose suitable family of weak learners and loss function for problem and data
  2. Fit using cross-validation
  3. Use grid search to optimize
  4. Evaluate

## AdaBoost
- using the errors from one tree to reweight those points in the next iteration, so if you have something wrong in one, it will try to fix those more so in the next tree
- so instead of training the next tree on the residuals of the errors, it retrains trees on the same datapoints as the first one with reweighted values
- the algorithm 'makes it care more about certain classifiers' by using weights
- in this algorithm you also WEIGHT the data itself
- there are a lot of subtleties in AdaBoost that just needs you to try it
