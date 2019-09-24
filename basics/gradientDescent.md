# Gradient Descent

Loss function of any ML algorithm tells the difference in the actual and predicted values. Using loss function, some algorithms like linear and logistic regressions define a cost function which is used as an optimization criterion for improving the algorithm results. The optimization criteria uses different algorithms to optimize the cost function. If the optimization criterion is differentiable then Gradient descent and Stochastic gradient descent are frequently used algorithms that are used as the optimization algorithms.

Gradient descent can be used to find optimal parameters for linear, logistic regressions, SVM and neural networks. Gradient descent finds the global and local minimums of a function. In case of regression, SVM and other convex algorithms, there is only one global minimum whereas in case of neural networks, local minimums can also be found. Local minimum can be found at some random point, by taking steps proportional to the negative of gradient from that random point. 

Lets see how we can apply gradient descent to find optimal values of *w* and *b* in linear regression algorithm. The linear regression equation looks like this:

y = *wx* + *b*

We know that by minimizing the mean squared error

*l* = 1/N ∑<sub>i=1..N</sub> (*y<sub>i</sub>* - *(wx<sub>i</sub> + b*))<sup>2</sup>

we can find the optimal values of *w* and *b*. To apply gradient descent, we differentiate the above equation with respect to all parameters, which in this case are *w* and *b*.

*dl/dw* = 1/N∑<sub>i=1..N</sub>-2*x<sub>i</sub>* (*y<sub>i</sub> - (wx<sub>i</sub> + b))*

and 

*dl/db* = 1/N∑<sub>i=1..N</sub>-2 (*y<sub>i</sub> - (wx<sub>i</sub> + b))*

where d represent the derivative.