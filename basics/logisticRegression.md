# Logistic Regression

Despite having *regression* in its name, Logistic regression is a classification algorithm. It can be both a binary classifier or a multiple class classifier. Logistic regression also follows the same linear model as of linear regression i.e., it models *y<sub>i</sub>* as linear function of **x<sub>i</sub>**. In fact, the equation that is used for logistic regression is similar to the one we saw in linear regression:

*f*<sub>**w**, *b*</sub>(**x**) = **w** **x** + *b*

In binary classification, we only want to know if an input is `0` or `1`, but the above equation produce infinite values based on the inputs. To solve this problem, we apply a logistic function on the output of above equation. *Sigmoid function* is one such *standard logistic function* and is defined as:

*f(x)* = 1 / (1 + e<sup>-x</sup>)

where *e* is called the *Euler's* number, which is also the base of natural log. Sigmoid function produces near to zero values as the input goes to negative and close to `1` output as the input goes higher. Whereas, it produces exactly `0.5` at input `0`. The range of output of sigmoid function is from `0` to `1` and is highly suitable for binary classification.

So to model the logistic regression as a binary classifier, we would substitute the logistic equation into the sigmoid function:

*f*<sub>**w**, *b*</sub>(**x**) = 1 / (1 + e<sup>-(**wx** + *b*)</sup>)

Now that we have our binary logistic classifier model, how do we find the best values, represented as **w\*** and *b\** respectively?

To find the values, we have our labeled training data. We want to maximize the likelihood of our training data, which means we have to come up with a way to find likelihood from each input. 

With our sigmoid function applied, we get a value from `0` to `1` representing if an input value is correctly classified. Let's call this *p*. Then the likelihood of the other class will become *1-p*, as there are only two classes (binary classifier). So in order to increase the likelihood, we can optimize our model using **maximum likelihood** method. Maximum likelihood can be modeled as:

 L<sub>**w**, *b*</sub>  = ∏<sub>i=1..N</sub> *f*<sub>**w**, *b*</sub>(**x<sub>i</sub>**)<sup>*y<sub>i</sub></sup>* (1 - *f*<sub>**w**, *b*</sub>(**x<sub>i</sub>**))<sup>*(1-y<sub>i</sub>)</sup>*

The first term in the above equation becomes `1` if *y<sub>i</sub>* equals `0`, which will be the case of second class classification. While the second term will go `0` in case of first class classification.

The product is used to find the maximum likelihood of N examples, as all observations (input values) are independent of each other.