# Linear Regression

Linear regression is a model to predict the unknown values of a linear input. Linear regression tries to find a straight line that passes as close as possible to all the data points.

You might have seen the equation of straight line in a 2D xy-plane `y = mx + c` where `m` is the slope of line and `c` is the offset from the origin. Linear regression model takes the same concept and tries to find the optimal `m` and `c` values from the available values of `x` such that a new value of `x` produces an appropriate predicted value.

In machine learning, since the input `x` is a feature vector **x**, and the representation of slopes can be written as weight vector **w** and also offset of constant `c` can represent in terms of biases **b**. The equation of linear regression model becomes

*f*<sub>**w**, *b*</sub>(**x**) = **w** **x** + *b*

where *f*<sub>**w**, *b*</sub>(**x**) represents the output function of **w** and *b* in **x**. 

The task now is to input the training data with **x** feature vector and calculate the best values for **w** vector and *b*. We call them **w**<sup>\*</sup> and *b*<sup>\*</sup> respectively.

Once we have the calculated and optimized parameter values of our regression model, the new data can be supplied as input in order to predict the output values.

## Linear Regression Optimization

While we have a straight line equation and corresponding training data to train i.e., to find the optimal values for **w**<sup>\*</sup> and *b*<sup>\*</sup>; Is there anyway to minimize the error, if yes then how to do it? The answer is below equation

(1/N) ∑<sub>i=1..N</sub>(*f*<sub>**w**, *b*</sub>(**x**) - y<sub>i</sub>)<sup>2</sup>

The above equation is simply a sum of squared differences in predicted label  and real label, which should be `0` if the prediction is exactly the same as real label. In mathematics , above equation is also called an objective as we minimize and maximize it. 

If we notice, (*f*<sub>**w**, *b*</sub>(**x**) - y<sub>i</sub>)<sup>2</sup>
tells us how much our prediction is wrong, and hence is called a **loss function**. Loss function tells us how much our prediction or classification is wrongly calculated. Whereas if we average out the loss function, we get the **cost function** or **empirical risk**.

A common question here is why have we taken a square of the error (*f*<sub>**w**, *b*</sub>(**x**) - y<sub>i</sub>)<sup>2</sup>? Well, we could have taken just an absolute or may be cube or whatever. But it turns out, taking a square of an error creates a continuous derivative, which is easier to deal with in liner algebraic calculations. The above equation is also known as **square error loss**, as we are squaring the loss of the prediction.