# Gradient Descent

Loss function of any ML algorithm tells the difference in the actual and predicted values. Using loss function, some algorithms like linear and logistic regressions define a cost function which is used as an optimization criterion for improving the algorithm results. The optimization criteria uses different algorithms to optimize the cost function. If the optimization criterion is differentiable then Gradient descent and Stochastic gradient descent are frequently used algorithms that are used as the optimization algorithms.

Gradient descent can be used to find optimal parameters for linear, logistic regressions, SVM and neural networks. Gradient descent finds the global and local minimums of a function. In case of regression, SVM and other convex algorithms, there is only one global minimum whereas in case of neural networks, local minimums can also be found. Local minimum can be found at some random point, by taking steps proportional to the negative of gradient from that random point. 

Lets see how we can apply gradient descent to find optimal values of *w* and *b* in linear regression algorithm. The linear regression equation looks like this:

y = *wx* + *b*

We know that by minimizing the mean squared error

*l* = 1/N ∑<sub>i=1..N</sub> (*y<sub>i</sub>* - *(wx<sub>i</sub> + b*))<sup>2</sup>

we can find the optimal values of *w* and *b*. To apply gradient descent, we differentiate the above equation with respect to all parameters, which in this case are *w* and *b*. The partial derivatives of *l*, *dl* with respect to both parameters are calculated as per the mathematics of derivative and are given below.

*dl/dw* = 1/N ∑<sub>i=1..N</sub>-2*x<sub>i</sub>* (*y<sub>i</sub> - (wx<sub>i</sub> + b))*

and 

*dl/db* = 1/N ∑<sub>i=1..N</sub>-2 (*y<sub>i</sub> - (wx<sub>i</sub> + b))*

Since we have the training data with N observations, we get N values of *w* and *b*. These values are calculated along with the learning rate α which can be set to control the size of the update.

For each *w<sub>i</sub>* and *b<sub>i</sub>* we get the following formulas

*w<sub>i</sub>* = α *  1/N * (</sub>-2*x<sub>i</sub>* (*y<sub>i</sub> - (w<sub>i-1</sub> x<sub>i</sub> + b<sub>i-1</sub>))*)

*b<sub>i</sub>* = α * 1/N * (</sub>-2 (*y<sub>i</sub> - (w<sub>i-1</sub> x<sub>i</sub> + b<sub>i-1</sub>))*)

Using above equations derived from the derivatives, we can get N values for *w* and *b*. For the first training example, we set the *w<sub>0</sub>* and *b<sub>0</sub>* to 0. After an iteration of all the training examples, one epoch gets complete. Multiple epochs are executed until the values of parameters do not change much and that gives us the optimal *W* and *b* values to be used for future predictions.