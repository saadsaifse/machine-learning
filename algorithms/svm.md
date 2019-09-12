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

