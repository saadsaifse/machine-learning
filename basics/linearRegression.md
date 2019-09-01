# Linear Regression

Linear regression is a model to predict the unknown values of a linear input. Linear regression tries to find a straight line that passes as close as possible to all the data points.

You might have seen the equation of straight line in a 2D xy-plane `y = mx + c` where `m` is the slope of line and `c` is the offset from the origin. Linear regression model takes the same concept and tries to find the optimal `m` and `c` values from the available values of `x` such that a new value of `x` produces an appropriate predicted value.

In machine learning, since the input `x` is a feature vector **x**, and the representation of slopes can be written as weight vector **w** and also offset of constant `c` can represent in terms of biases **b**. The equation of linear regression model becomes

*f*<sub>**w**, *b*</sub>(**x**) = **w** **x** + *b*

where *f*<sub>**w**, *b*</sub>(**x**) represents the output function of **w** and *b* in **x**. 

The task now is to input the training data with **x** feature vector and calculate the best values for **w** vector and *b*. We call them **w**<sup>\*</sup> and *b*<sup>\*</sup> respectively.

Once we have the calculated and optimized parameter values of our regression model, the new data can be supplied as input in order to predict the output values.


// TODO: add more details such as loss function and examples