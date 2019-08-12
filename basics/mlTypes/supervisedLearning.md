# Supervised Learning

In supervised learning, correct output is known to the model before hand. The training data contains inputs and their corresponding expected outputs so that the model learns what to expect or suggest based on the new input data. The algorithm generalizes to respond correctly to all possible inputs. This is also called learning from exemplars.

## What is Expected Output?

Expected output is from among the labels that are applied to the training data. These labels can either be from a set of discrete user defined classes, a real number or any data structure like trees, etc. 

For example consider a dataset of an image, `{Xi}` where `i` is from 1 to `N` that represents the pixel values of the image. If we were to label each pixel of the image based on their color, as either black or white. Then either we can label all pixels as `0` or `1` or label them as classes with names `White` and `Black`.

Once labels are applied to the data, it can be represented as `{(Xi, Yi)}` where `Yi` is the label for each `Xi`