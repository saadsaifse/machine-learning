# Training, Testing and Validation Sets

After selecting the machine learning algorithm, the next task is to train it with the data that we already have. Whether we are doing Supervised learning or Unsupervised learning, we have some targets of the outcome from the algorithm. If we taking the input data in the form arrays or vectors, then we have our Input Vector and the corresponding Target Vector. To avoid [Overfitting](overfitting.md), we also have our Validation Vector.

But the data that we have is in one form. It does not come in chunks of inputs, targets, training, testing and validation sets. That means we have to define a strategy to divide our data in terms of sets, to effectively use them in our machine learning algorithms.

The typical strategy to create training, testing and validation sets is to divide the data in **50-25-25%** ratio. This data has to be properly shuffled and randomized in order to have all types of classes visible in each data set. A related concept while determining the data sets is called [Overfitting](overfitting.md) and that is why need to make a separate validation data set to stop the training on the right time.