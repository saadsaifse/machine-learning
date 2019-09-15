# Support Vector Machine

Support vector machine (SVM) is a supervised learning algorithm which is used for classification. SVM algorithm is quite simple and can be easily applied on real world scenarios for example, in classification of emails as spam or not-spam.

For its application to a problem set, first the domain specific features are identified and extracted. For example, in case of spam emails classification, the text of the email messages are converted to feature vectors using several techniques, such as bag-of-words and Word2Vec, etc. such that a text based email message gets converted to a numeric vector representation, on which mathematical calculations can be applied. Each value in the numeric vector is a new dimension that represents a particular feature. So if we have an array of 10,000 numbers, then its dimension is also 10,000 and it contains 10,000 distinct features, forming a feature vector.

The task of SVM, is to identify if the email is spam or not-spam. As this is a binary output, it represents the output as numeric numbers +1 or -1 for spam and not-spam respectively. But how does it put these two labels on the input features? By drawing a line between two classes and creating a boundary in-between the classes, which is also known as the decision boundary.

Drawing a line is certainly not easy as we have 10,000 dimensional feature vectors, which means this line is rather a *hyperplane* which has to be drawn on an imaginary 10,000 dimensional plane. The equation of such a hyperplane would become

**wx** - *b* = 0

where **x** is a 10,000 dimensional vector and **w** is also a real-values vector of the same dimension. **wx** corresponds to *w*<sup>(1)</sup>*x*<sup>(1)</sup> + *w*<sup>(2)</sup>*x*<sup>(2)</sup> + .... till the last dimension.

From the training data, this model is trained to find the optimal values of **w<sup>\*<sup>** and *b<sup>\*<sup>* such that any unknown or new feature vector extracted from a new email can be applied to this model to predict the class of the email.

In SVM, since the output has to be either +1 or -1, we apply a *sign* function on this hyperplane to give us the final output label.

*y* = *sign*(**w<sup>\*<sup>** **x** - *b<sup>\*<sup>*)

## Optimization

For better generalization, the margin between two classes should be further away from the decision boundary (**wx** - *b* = 0) i.e., the distance between hyperplane of class 1 (**wx** - *b* = 1) and class 2 (**wx** - *b* = -1) should be maximized. How do we maximize the distance and what exactly is the distance between them? The distance between two parallel hyperplanes of our two classes is defined as 2/||**w**||, where ||**w**|| is the Euclidean norm of **w**. The Euclidean norm is defined as 

||**w**|| = √ (∑<sub>j=1..D</sub> (*w<sup>(j)</sup>*)<sup>2</sup>)

Therefore, in order to maximize the distance, we need to minimize the Euclidean norm of **w**, ||**w**||. In the next section, we will discuss about non-linear hyperplanes and dealing with noise in the data.

## Noisy data

In real life, the data would not be completely separable in distinct classes. The data will not be separable with a straight line and examples of other classes will fall into the the wrong place i.e., in the zone of another class. This is considered as noise in the data and can be mitigated through the use of loss function, cost function and hyperparameter *C*. 

Remember we talked about loss function as the function which tells the difference of expected value and predicted value whereas cost function tells us the average of the all the losses. In SVM, the loss function which is used is called **hinge loss function** and is defined as

max(0, 1 - *y*<sub>i</sub>(**wx<sub>i</sub>** - b))

where the term *y*<sub>i</sub>(**wx<sub>i</sub>** - b) is an easier way of writing two conditions of SVM together i.e., following two SVM conditions  

**wx<sub>i</sub>** - b >= 1 if *y*<sub>i</sub> = +1

and 

**wx<sub>i</sub>** - b <= -1 if *y*<sub>i</sub> = -1

can be written in one equation as

*y*<sub>i</sub>(**wx<sub>i</sub>** - b) >= 1

As the right output of *y*<sub>i</sub>(**wx<sub>i</sub>** - b) should be greater than or equal to 1, (1 - *y*<sub>i</sub>(**wx<sub>i</sub>** - b)) will give us either 0 or less than 0 values. However, if the classification is wrong and then this will give us greater than 0 values which will be proportional to the distance of mis-classification from the decision boundary.

### Fixing Noise 

To fix the noise, we take the average of loss function to get the cost function and control the distance ||**w**|| of the margin by a hyperparameter *C*. The equation then becomes

C||**w**||<sup>2</sup> + 1/N ∑<sub>i = 1..N</sub> max(0, 1 - *y*<sub>i</sub>(**wx<sub>i</sub>** - b))

where the left part is just controlling the margin distance and right part is the cost function. The value of cost function will tell us how much our data is far or near to the margin and accordingly we adjust the value of hyperparameter *C* to increase or decrease the distance of the the margin. Increasing *C* will give us better generalization on future examples as it increases the margin by ignoring the cost function. Whereas, decreasing *C* will give us better classification on the training data by minimizing the empirical risk. Setting the value of *C* hyperparameter is therefore a trafeoff and is normally set experimentally to control the noise.

## Non-Linear data

The classes in the dataset are not always separable with a straight hyperplane due to inherent non-linearity in the examples. In this case, different transformations are tried and applied on to the dataset in order to see if the dataset is separable in higher dimensional space. For example, the data that is not separable in 2D space, might be separable in 3D space.

If **x** is a feature vector [q,p] then Φ(**x**) is the transformed feature vector that could be [q<sup>2</sup>, √2qp, p<sup>2</sup>]. But this brings another problem, how do we know before hand, which transformation might work? Fortunately, there is a trick known as **Kernel trick** to implicitly apply transformation during cost function optimization. There are several kernel functions or simply **kernels** that can be applied such as quadratic kernel and **RBF Kernel**, etc. which will be discussed separately in detail. But the take away here is that, non-linear data is first passed through a kernel function and then classified using SVMs. 