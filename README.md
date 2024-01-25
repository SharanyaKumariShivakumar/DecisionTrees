**Decision Trees in Machine Learning**

**Overview**

A decision tree is a non-parametric, supervised learning algorithm that is widely used for classification and regression tasks. It is called non-parametric because it does not make any underlying assumptions about the distribution of the data. The decision tree algorithm represents a series of decisions based on the data's features leading to a prediction or classification.

**Structure of a Decision Tree**

Root Node: This is the topmost node of the tree from which the data splitting starts. It contains the entire dataset which then gets divided into subsets.
Branch Nodes: These are internal nodes representing decisions based on a certain condition. Each branch node splits the data into two or more sub-nodes.
Leaf Nodes (Terminal Nodes): These nodes represent the final output of the decision process, which could be a class label in classification or a continuous value in regression.
Decision Rules: Each branch in the tree represents a rule, which is a specific condition applied to a feature. These rules are conjunctive (ANDed together) as you move down the tree.

**Creation of a Decision Tree**

**Recursive Binary Splitting**: The tree is built by splitting the dataset into subsets based on feature values. This process starts at the root node and is repeated recursively for each derived subset.
**Attribute Selection Measure (ASM)**: To determine the split, an ASM is used. Common methods include:
**Information Gain**: Used to measure how well a given attribute separates the training examples according to their target classification.
**Gini Index**: A measure of impurity or purity used in the CART (Classification and Regression Trees) algorithm, where a lower Gini Index indicates a better split.
**Variance Reduction**: In regression problems, the feature causing the most reduction in variance is chosen for the split.
**Stopping Criteria**: The recursion is halted at a point where further splitting is not beneficial. This could be for several reasons, such as all instances in a node having the same class, reaching a maximum tree depth, or not achieving a minimum information gain from a split.

**Advantages of Decision Trees**

1. Interpretability: Trees can be visualized, which makes them easy to interpret and understand.
2. Handling Non-Linear Relationships: Capable of capturing non-linear relationships between features and labels.
3. No Feature Scaling Needed: Decision trees do not require feature scaling to be performed as they are not sensitive to the variance in the data.

**Disadvantages of Decision Trees**

1. Overfitting: Without proper tuning, decision trees can create over-complex trees that do not generalize well from the training data.
2. Instability: Small variations in the data can result in a completely different tree being generated.
3. Greedy Algorithm: Decision trees are considered greedy because they make the optimal decision at each node, which does not necessarily lead to a globally optimal tree.

**Pruning**

To avoid overfitting, trees are pruned. Pruning can be done by setting a maximum depth for the tree, requiring a minimum number of samples to split a node, or setting a minimum gain for a split to occur. Post-pruning methods such as cost-complexity pruning are also commonly used, where the least important branches are trimmed based on a complexity parameter.

**Conclusion**

Decision trees are a valuable tool for tasks involving classification and regression. They form the building blocks for more complex models like Random Forests and Gradient Boosted Trees. With proper setup and tuning, decision trees can be powerful models that are also intuitive and easily shared.


DecisionTrees.ipynb implements a Decision Tree on the titanic dataset using the scikit-learn Decision Tree Classifier. The Decision Tree created initially overfits on the data, and pruning is performed to avoid overfitting. Alpha value to prune is selected based on the number of nodes, depth of the tree and alpha vs accuracy values for training and test datasets. Accuracy value for the test set increases post pruning.

Data - titanic.csv file is included in this repository.
