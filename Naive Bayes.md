
Table of Contents:
	[[#Probability]]
	[[#Naive Bayes]]
	[[#Naive Bayes Cycle]]




### Probability:

**Probability of Intersection $P(A \cap B)$** - The probability of $P(A \cap B)$, also written as P(A,B), is the number of elements in the intersection divided by the number of total elements 

![[Pasted image 20240228164419.png]]



**Conditional Probabilities $P(B | A)$** - The probability of $P(B | A)$ means the probability of B given A. This probability is given by the number of elements in B divided by the total number of elements in A. 
- Importantly, $P(A \mid B) = \frac{P(A \cap B)}{P(B)}$

![[Pasted image 20240228164743.png]]



**Bayes' Rule** - Bayes' Rule says that $P(A \mid B) = P(B \mid A) \times \frac{P(A)}{P(B)}$

---

### Naive Bayes 

**Naive Bayes Formula for Binary Classification** - $\prod_{i=1}^{m} \frac{P(w_i|\text{pos})}{P(w_i|\text{neg})}$

![[Pasted image 20240228172125.png]]

**Naive Bayes For Machine Learning** - Naive Bayes is another Machine Learning model. It's a good alternative to [[Logistic Regression]] for Positive-Negative Sentiment classification.



**Laplacian Smoothing** - We use this technique to avoid the cases where a word has probability of 0 or undefined. This is due to Naive Bayes formula, where if a word doesn't appear in a certain class, it's probability might be 0 or undefined (since we might divide by 0 or have 0 in the numerator)
- We apply Laplacian Smoothing to each probability in Naive Bayes (numerator and denominator). For each probability, we apply Laplacian Smoothing by adding one to the numerator of the probability and then add V (number of unique words in vocabulary) to the denominator. 
	- This will ensure that we don't have 0 in the numerator nor denominator
![[Pasted image 20240228173131.png]]

**Naive Bayes Applications** - Some applications of Naive Bayes Model's include:
- Sentiment Analysis
- Author Identification
- Information retrieval
- Word disambiguation
- Simple, fast, and robust!

**Naive Bayes Assumptions** - There are some assumptions made by the Naive Bayes model that can cause it to preform badly if the assumptions are not met (and it's often not always met)
- **Independence Assumption**
	- When you are given the word "It is sunny and hot in a desert" and "it's always cold and snowy," the Naive Bayes model assumes each word is independent but "sunny, hot, and desert" usually end up in the same sentences (therefore not very independent), and "cold and snowy" are also not very independent
- **Relative frequencies in corpus** (Database of words)
	- The Naive Bayes model assumes a close to 50/50 split in the ratio of the two classes in the problem. But, in the real world, it's often not a 50/50 split for most problems. If there is a lot more of one class, the predictions will be heavily biased towards that class even if the validation/test set is more balanced, leading to some terrible predictions
		- Ex. 10,000 positive tweets and 10,000 negative tweets.



---

### Naive Bayes Cycle

**Step 0:** Collect and Annotate Corpus (database of words, like positive and negative tweets)

**Step 1:** Preprocess data 
- Lowercase
- Remove punctuation, urls, names
- Remove stop words
- Stemming
- Tokenize Words

**Step 2:** Word Count (finding vocabulary for every unique word)
- Make a Frequency Dictionary 

**Step 3:** $P(word \mid class)$ 
- Conditional probability, a.k.a probability of a word given the class
- Using the **Laplacian Smoothing Formula**, we do this:
	- $P(word \mid class) = \frac{frequency(word, class) + 1}{N_{class} + V_{class}}$
		- $N_{class}$ is the number of words in the class (pos or negative)
		- $V_{class}$ is the number of unique words in vocabulary

**Step 4:** Get $\lambda(word) = log(\frac{P(word \mid pos)}{P(word \mid neg)})$
- Convert all words to $\lambda(word)$

**Step 5:** Calculate the log prior
- log_prior = $log(\frac{D_{pos}}{D_{neg}})$
	- $D_{pos}$ = Number of Positive Tweets
	- $D_{neg}$ = Number of Negative Tweets



---