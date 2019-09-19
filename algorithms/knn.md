# k-Nearest Neighbors (kNN)

kNN is non-parametric algorithm used for both classification and regression. Unlike other algorithms, instead of discarding the training data after the model is trained, kNN keeps the training data to compare it with the new examples. When it takes a new example, it compares the new feature vector with the existing ones (from training data) and accordingly assign majority label (classification) or average label (regression) to it. 

For comparison, different methods are used, for example **Euclidean distance** is one way to compare two feature vectors, which is defined as

d(**x**, **x<sup>,</sup>**) = √∑<sub> i..D (x<sup>(i)</sup> - x<sup>,(i)</sup>)<sup>2</sup>

where D is the dimension of feature vector.

There are several other distance functions which can be used depending upon the data e.g., Chebychev distance, Mahalanobis distance, and Hamming distance. Also, the value of *k* is set as per the problem and dataset and therefore these two are hyperparameters of kNN algorithm.

## Negative Cosine Similarity

In addition to Euclidean distance, negative Cosine Similarity also provides a measure of similarity between two feature vectors. Cosine similarity is defined as 

s(**x<sub>i</sub>**, **x<sub>k</sub>**) = cos(∠(**x<sub>i</sub>**, **x<sub>k</sub>**)) = ∑<sub>j = 1..D</sub> (*x<sub>i</sub>*<sup>(j)</sup> *x<sub>k</sub>*<sup>(j)</sup>) / (√ (∑<sub>j = 1..D</sub> (*x<sub>i</sub>*<sup>(j)</sup>)<sup>2</sup>) √ (∑<sub>j = 1..D</sub> (*x<sub>k</sub>*<sup>(j)</sup>)<sup>2</sup>))

and is multiplied by -1 in order to be used as a distance metric. The interpretation of angles is that if the angle between two vectors is 

* 0, then both points to the same direction
* -1, then both points to the opposite direction
* 1, then both vectors are orthogonal

the above interpretation is only valid if we multiply the result of cosine similarity equation above with -1.