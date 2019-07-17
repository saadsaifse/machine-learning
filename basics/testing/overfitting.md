# Overfitting

Overfitting of the algorithm is referred to the scenario when the algorithm learns too much about the data that it is being trained on. The algorithm which could also be a neural network learns about the inaccuracies and errors that are found in the training data itself. This causes the algorithm to generalize poorly when it comes to real data, consequently producing wrong predictions and outputs. 

To overcome overfitting, we need to have some sort of early evaluations to know when to stop the algorithm's learning process. This is commonly achieved by setting some part of the data aside for validation and is therefore called the **validation set**. As a general rule, about 20-25% of the data is set apart as a validation set.