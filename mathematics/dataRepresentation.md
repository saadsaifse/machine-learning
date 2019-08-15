# Data Representation

There are some terminologies that are used to represent data on which machine learning algorithm is to be applied. For example, in case of supervised learning, we have labeled data and the data usually is more than one dimensional. So how do we represent it mathematically?

## Vectors
In mathematics, a vector simply is an ordered list of values. Each value is called its attribute. With addition of each attribute in the vector, its dimension increases. For example, if we have a vector representing three attributes of a person (age, height, and weight) then this vector has three dimensions, each corresponding to the its attribute. Vectors are usually denoted by a bold character, for example, **x** or **y**.

In machine learning, attributes are usually called features and hence, such a vector is also called a **feature vector** as it contains features of the entity, which in this case is a person. We refer to each feature with italicized name of the vector with superscript of the index in brackets. For example, if our vector of persons is denoted by **p** then the age would be referred as *p<sup>(i)</sup>* where *i* is the index/dimension of the feature vector. Consequently, *p<sup>(1)</sup>* represents age, *p<sup>(2)</sup>* represents height, and so on.

## Sets
Conversely to a vector, a Set is an unordered list of unique values and is represented by *S*. A finite set has curly brackets e.g., {1,2,3,4,5} whereas an infinite set which contains infinite values among intervals is represented by square brackets, [1,2,3,4,5]. Set can also be represented by parenthesis (1,2,3,4,5) which excludes first and last values from the set. 

## Dataset

In machine learning, datasets are represented in the same way as Sets in mathematics. For example a dataset of persons can be represented as {**p**<sub>1</sub>,**p**<sub>2</sub>,**p**<sub>3</sub>,**p**<sub>4</sub>,...**p**<sub>n</sub>}. Where each **p** is a feature vector of a person that contains multiple features as discussed in the Vectors sections above.