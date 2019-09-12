# Decision Tree Learning

As the name suggests, decision tree is a graph with nodes, forming a tree like structure. This structure is used to make decisions from the dataset. With a multi-feature dataset, decision tree algorithm calculates the probability of a specific feature at a node to decide which graph segment (left or right) should be followed. At each node, different features are examined until we reach at the end of the graph, that gives us the final decision.

We want to determine the class of an observation or example through a decision tree. For that, a decision tree is trained with a set of labeled data whose labels belong to a set {0, 1}.

An example decision tree algorithm is known as *ID3*, which uses quite similar optimization function as of the logistic regression:

 ID3 Optimization  = ∑<sub>i=1..N</sub> *y<sub>i</sub>* ln  *f*<sub>*ID3*</sub>(**x<sub>i</sub>**) (1 - *y<sub>i</sub>*) ln (1 - *f*<sub>*ID3*</sub>(**x<sub>i</sub>**))

 If you compare the above function to the optimization of logistic regression, then the difference is that here we took the natural logs instead of exponents, which gives the same result but easier for calculations.

 Also, as we are using *ID3* algorithm, instead of finding the best values for parameters **w** and *b*, we find the probability of *y* = 1 with **x** as an input.

 ## ID3 Algorithm

ID3 is defined as 

*f<sub>ID3</sub>*(**x**) = Pr (*y* = 1 | **x**)

or in words, its just a probability of *y* having 1 when **x** is provided as an input.

To build a decision tree, ID3 algorithm starts at the top with all the input data *S* provided a labeled dataset *S*. The ID3 at that root node would be 

*f<sup>S</sup><sub>ID3</sub>* = 1 / |S| * (sum of all values of *y*)

where *S* has labeled pairs of **x** and y. 

Then we determine a threshold value *t* where we can split the data in two. This split is usually performed by determining feature values within *x* feature array. For example, if at some feature *i* in **x**<sup>*i*</sup>, we split the dataset into two in order to form a decision tree. This splitting goes on to form a tree like structure and is trained on the training data in order to classify an observation.
