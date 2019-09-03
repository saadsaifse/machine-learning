# Logistic Regression

Despite having *regression* in its name, Logistic regression is a classification algorithm. It can be both a binary classifier or a multiple class classifier. Logistic regression also follows the same linear model as of linear regression i.e., it models *y<sub>i</sub>* as linear function of **x<sub>i</sub>**. In fact, the equation that is used for logistic regression is similar to the one we saw in linear regression:

*f*<sub>**w**, *b*</sub>(**x**) = **w** **x** + *b*

In binary classification, we only want to know if an input is `0` or `1`, but the above equation produce infinite values based on the inputs. To solve this problem, we apply a logistic function on the output of above equation. *Sigmoid function* is one such *standard logistic function* and is defined as:

*f(x)* = 1 / (1 + e<sup>-x</sup>)

where *e* is called the *Euler's* number, which is also the base of natural log. Sigmoid function produces near to zero values as the input goes to negative and close to `1` output as the input goes higher. Whereas, it produces exactly `0.5` at input `0`. The range of output of sigmoid function is from `0` to `1` and is highly suitable for binary classification.

So to model the logistic regression as a binary classifier, we would substitute the logistic equation into the sigmoid function:

*f*<sub>**w**, *b*</sub>(**x**) = 1 / (1 + e<sup>-(**wx** + *b*)</sup>)

Now that we have our binary logistic classifier model, how do we find the best values, represented as **w\*** and *b\** respectively?
