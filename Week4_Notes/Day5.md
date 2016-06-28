# Week 4 Day 5

# Support Vector Machines
- apparently this will be hard

### Objectives
- Explain the intuition behind SVM
- Paraphrase the conceptual meanings of the math of SVM
- Describe the parameters of the soft margin classifier

---
- instead of the equation of a line $y = mx+b$
- we are going to use $y = W^Tx + b$

---
- kernel tricks - functions that take data to a higher dimension with just a dot product
- these are used when data in the lower dimension cannot be easily parsed into different classes, the kernel tricks will bring it into a higher dimension (basically stretching it out) so that we can separate the data more easily

Just to reiterate, I made a mistake on this morning's board.  The C used is the penalty term for total error, so as C increases variance will increase (because it wants to make less error, thus reducing margin), as C decreases variance will decrease (because my model is no longer stressing about points inside the margin or wrongly classified, allowing margin to grow bigger).
Tammy uses the C as a budget for error.  As C increases variance will decrease (because it is allowing more room for error), and as C decreases variance will increase (because it is allowing less errors to occur).  This version is from Intro to Statistical learning.
Tammy's version will be on Monday's assessment, but my version is consistent with Sklearn's implementation.
