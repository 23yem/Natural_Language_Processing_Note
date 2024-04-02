Week 4 of Course 2

Table of Contents:
	[[#Overview]]
	[[#Basic Word Representations]]
	[[#Word Embeddings]]


[[Week4_Slides.pdf|Week 4 Lecture Slides from the course]]


---


# Overview


We've seen word embeddings previously in [[Vector Space Models]]


Word embeddings are used in most NLP applications. Whenever you are dealing with text, you first have to find a way to encode the words as numbers. Word embedding are a very common technique that allows you to do so. Here are a few applications of word embeddings that you should be able to implement by the time you complete the specialization.

![[Pasted image 20240401112109.png]]

By the end of this week you will be able to:

- Identify the key concepts of word representations
- Generate word embeddings
- Prepare text for machine learning
- Implement the continuous bag-of-words model

---

# Basic Word Representations

Basic word representations could be classified into the following:

- Integers
- One-hot vectors
- Word embeddings

![[Pasted image 20240401112534.png]]

To the left, you have an example where you use integers to represent a word. The issue there is that there is no reason why one word corresponds to a bigger number than another. To fix this problem we introduce one hot vectors (diagram on the right). To implement one hot vectors, you have to initialize a vector of **zeros** of dimension _V_ and then put a 1 in the index corresponding to the word you are representing.

The **pros** of one-hot vectors: simple and require no implied ordering.

The **cons** of one-hot vectors: huge and encode no meaning.


---

# Word Embeddings

So why use word embeddings? Let's take a look.

![[Pasted image 20240401112956.png]]

From the plot above, you can see that when encoding a word in 2D, similar words tend to be found next to each other. Perhaps the first coordinate represents whether a word is positive or negative. The second coordinate tell you whether the word is abstract or concrete. This is just an example, in the real world you will find embeddings with hundreds of dimensions. You can think of each coordinate as a number telling you something about the word.

The **pros**:

- Low dimensions (less than V)
- Allow you to encode meaning

---

# How to create word embeddings

To create word embeddings you always need a corpus of text, and an embedding method.

The context of a word tells you what type of words tend to occur near that specific word. The context is important as this is what will give meaning to each word embedding.

## Embeddings

There are many types of possible methods that allow you to _learn_ the word embeddings. The machine learning model performs a learning task, and the main by-products of this task are the word embeddings. The task could be to learn to predict a word based on the surrounding words in a sentence of the corpus, as in the case of the continuous bag-of-words.

The task is **self-supervised**: it is both unsupervised in the sense that the input data — the corpus — is unlabelled, and supervised in the sense that the data itself provides the necessary context which would ordinarily make up the labels. 

When training word vectors, there are some parameters you need to tune. (i.e. the dimension of the word vector)

![[Pasted image 20240401113442.png]]