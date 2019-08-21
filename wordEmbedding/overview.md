# Word Embedding

Word embedding is a way to convert words to real vector representations such that their semantic and syntactical characteristics are preserved. A main advantage that word embedding provide is that similar words have  similar mappings. 

Following are some of the techniques used:

## Bag-of-Words
Bag-of-Words (BoW) model is a way to extract information from texts prior to performing machine learning. It tells the frequency of each word irrespective of their location and structure in the text. It only counts the words that exist in a provided dictionary of words. If the dictionary has more words, the size of the vector representing text will be more. Its computationally expensive and does not respect grammar and word order. Also does not provide any semantics associated with the words.

## Vector Space Model
Vector Space Model (VSM) is a way to extract information from texts documents in order to input them in machine learning models. The model can provide semantics of words by mapping similar words closer to each other. An example of VSM is *Word2vec* model which is very popular in converting words to related vectors.

## Social Network-Specific Models
Social Network-Specific models are similar to VSM but are designed with social media settings. As people write informal text, grammatically incorrect sentences, abbreviations, and also insert emoticons or symbols. These problems are addressed in models such as *Tweet2vec* that takes an entire tweet and embeds it to vector after handling above mentioned concerns. There is an open-source pre-trained word vectors for twitter, called *GloVE*, which is trained on global word-word co-occurrence statistics.

// ToDo: add some examples and refine definitions
