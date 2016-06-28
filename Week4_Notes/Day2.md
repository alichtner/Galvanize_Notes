# Week 4 Day 2
---
### Objectives
- Explain the difference between a parametric and non-parametric learner
- Describe the difference between euclidean distance and cosine similarity
- Construct a k-nearest neighbors model

## Parametric Models (linear and logistic)
- if the data is too complex to separate with a logistic method (parametric) we have to use something different
- parametric forces functional form
- easy to interpret
- they are also easy to compute

## Non-parametric
- flexible in shape
- harder to explain
- more likely to overfit the data (use cross-validation)
- less assumptions

## k-nearest neighbors
- jocks with jocks, nerds with nerds, theatre with theatre...
- we get training data in some matrix with a target vector of labels
- try to predict what something is based on the relative 'proximity' to other points
- whenever you put in a new value you compute the distances between the old points and the new point
  - sort the data (and make labels) by distance from the new point
  - determine the label of the new datapoint using the labels from the k nearest points
- the training part is very fast, the predictions are slow since you have to calculate distances from every current point and then sort all the distances
  - my thought: would you really have to sort it? you can just keep sorting the lowest distance and use those

### Euclidean Distance
- $z$ is the new, added datapoint
- $D(x_i, z) = ||x_i - z||$ = $\sqrt{\sum(x_{ij} - z_j)^2}$

### Cosine Similarity
- another way of computing distance between points
- \[D(x_i, z) = \frac{x_i \cdot z}{||x_i||||z||}\]

### Cosine Distance (often used for knn)
- 1 - Cosine Similarity

### The curse of dimensionality
- when adding features to these algorithms, the computations scale exponentially
- when flexibility/complexity/dimension increase, they lead to reduced bias and increased variance (more overfitting)
- when adding a feature, in addition, you need 10^2 more datapoints to have the same information as before because you have 10^2 more possible combinations as before

---
## Afternoon Objectives

### Objectives
- Construct a decision tree
- Explain methods of finding the best split
- Explain how to reduce the variance of a decision tree

## We want to know...
1. what is a good split?
2. what is the best to split on?
3. when do we stop?

## What should we split on?
- try everything
- pick the best info gain
- when do we stop? --> when a node a pure

### Identifying a good split
- Q: hwo pure is our node? meaning, after a split, what percent of the node is of one class, if it's highly one thing it's a good split, if it isn't, the previous split should be improved or another split is needed
  - Gini Impurity
  - Entropy
  - Information Gain

#### Gini Impurity: how impure is our node?
- metric for measuring the purity at a node
\[Gini = \sum{P(c_i)(1 - P(c_i))}\]
- this function goes from 0 to 0.5 where 0.5 is an even split of values and 0 shows that it's purely one or the other class

#### Entropy
\[Entropy = \sum{-P(c_i)log_2(P(c_i))}\]
- ranges from 0 to 1 where 1 is fully mixed

#### Information Gain
- Gini of the parent minus the gini of the children
  - the gini of the children is a weighted average of the ginis from each child at the child level

## Steps in Decision Tree
1. cycle through every variable, and every value and split
  - if continuous use >= and <
  - if categorical use == or !=
2. Compute IG, pick the split with highest IG
3. Repeat the process for left and right node
4. Stop if current node is pure

### Pruning
- there is pre and post pruning where we actually alter our tree
- these are rules for the tree
#### Pre-pruning
1. stop if information gain is less than some threshold
2. If the tree reaches a maximum depth that you have previously set
3. Stop if each node is pure enough (i.e. 95% pure)
4. If the number of items in each node becomes too small

#### Post-pruning
- run a model
- prune some nodes
- if the pruned version has a better error rate than the prior then keep the new one
- **Steps**
  1. calculate the error for pair of nodes
  2. merge the pair and calculate error again
  3. if merged is better, keep merged
  4. repeat

- we can apply decision trees to linear regression by changing the Information Gain to using MSE instead of Gini
