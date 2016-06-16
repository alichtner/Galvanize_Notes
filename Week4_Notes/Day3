# Week 4 Day 3

# Bagging and Random Forests

### Objectives
- Explain the construction of a random forest algorithm
- Explain the relationship and difference between random forest and bagging
- Explain why random forests are more accurate than a single decision tree

## Notes
- random forests are the most important one
- OOB = out of bag
- ensembles = a way of taking lots of weak classifiers and using them to make a strong classifier
  - this actually isn't that easy in practice because the models often times are not independent
  - bias = error from failure to match training set
  - variance = error from sampling training set
- decision trees are really easy to overfit
- in decision trees we don't have to scale features, they can be used on nonlinear data
- can be expensive to train and has high variance usually in predictions

### Bagging
- building many decision trees using bootstrapped samples
-steps
  - train a bunch of bootstrap samples (n)
  - train a high variance, low bias model on each
  - average the results (or take the plurality in the case of categorical data)
  - can reduce your variance by up to $\sqrt{n}$
  - we will never actually reach that reduction though because the bootstrapped samples are still somewhat correlated
- bagging reduces variance (and increases bias to a small extent)

### Random Forests
- typically the number of features you take for each tree is $\sqrt{n}$ where n is the number of features
- parameters
  - total number of trees
  - number of features to use at each split
  - number of points for each bootstrap sample
  - individual decision tree parameters
    - ex. tree depth, pruning...
- We choose our best random forest using cross-validation
- Pros:
  - gives good performance
  - no scaling needed
  - models nonlinear relationships
  - hard to overfit
- Cons:
  - can be expensive to train (although this can be improved with boosting)
  - not interpretable
---
## Afternoon
### Objectives
- Explain how to get feature importances from random forests
- Explain how OOB error is calculated and what it measures
- **Random Forests are hard to overfit compared with decision trees**

## Notes
- we don't actually have to use a cross_validation dataset with bagging since with baggin we are using a subset of the observation anyway, the left out observations can serve as the testing set. Often times though they are used anyway.
