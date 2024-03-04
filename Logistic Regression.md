
Week 1 of Course 1

**Table of Contents:**
	[[#Features in NLP]]
	[[#Preprocessing]]
	[[#Putting it All Together]]
	[[#Logistic Regression]]
	

[[Week1_Slides.pdf|Week 1 Lecture Slides from the course]]

---
# Features in NLP

**Tokenization** - the process of breaking a complex piece of text into smaller units (tokens)
- A token can be as simple as a word or punctuation 

**Sparse Representation** - Representation with a small relative number of non-zero values 
- Ex: Representing "I am happy" as [1, 1, 0, 1, 0..., 0] where the first element in the array represents the existence of the word "I", the second element for "am", the third element for some word not in "I am happy", and the fourth element in "happy."
- Issue: When we have a large set of sentences, we have millions of words so our vocabulary will be millions of words and we will have to represent each sentence as an array of with millions of elements (even though only very few of the elements will have "1" and the rest are "0"s). 

**Frequency Dictionary** - A tool used to map a class (ex. Nice or Mean) and the words to the amount of times that words showed up in that class
- It's useful for representing the most common words in one class (ex. Nice) and the most common words in another class (ex. Mean) so that we can classify a new sentence as Nice or Mean depending on how many Nice and Mean words show up in the sentence

**Feature Extraction with Frequency Dictionary** - Instead of having features with length of the total vocabulary, we can have feature with length of 3 (array with 3 elements)
- [30 second article about this from the course](https://www.coursera.org/learn/classification-vector-spaces-in-nlp/supplement/sfhGt/feature-extraction-with-frequencies)
![[Pasted image 20240227164358.png]]

---
# Preprocessing:

**Stop Words** - Words that appear in English but don't have much affect on the sentiment/meaning of sentences
- Ex. And, Is, Are, At, Has, For, A

**Stemming** - Changing words to their base values so that we cut down the amount of unique words
- Ex. Tune, Tuning, Tuned all have the same **stem** "tun" and they all have similar meaning so we can represent them all as the word "tun" to limit the amount of unique words we have to pay attention to
- You can use porter stemmer to take care of this
- ![[Pasted image 20240227165855.png]]

**Notes:**
- We also get rid of **punctuation** (ex. ! . , " ;) most of the time, except when it's necessary for your specific ML task
	- Ex. keeping https:// when you want to identify spam emails and suspicious links

- It's also important to convert all words to **lowercase**

- Example: "Tuning GREAT AI models" turns into [tun, great, ai, models] due to stemming and lowercasing

---

# Putting it All Together


Cycle - Here's a simple three-step cycle for converting text data to data that is ready to be fed into Machine Learning Models:
1. Create **Frequency Dictionary**
2. **Preprocess** each sentence in the database
3. **Extract features** from each sentence in the database into a matrix so that each row in the matrix represents a single sentence and each column (3 columns total) represents:
	- [bias, sum of positive frequency, sum of negative frequency]
	- The dimension of the matrix is therefore (m, 3), where "m" is the number of sentences in the database
	- An example matrix would look like this:
		- [ [1, 48, 3],
			[1, 2, 70],
			[1, 40, 58] ]

---

# Logistic Regression

![[Pasted image 20240227185801.png]]
- Here, $\theta$ (theta) represents the vector (list) of all the weights (ex. $\theta_0$ represents the bias (b), while $\theta_1$ represents the first weight). In other words, it's the same thing as "w" in y = wx + b. 
	- A full trained model will have all of it's $\theta$ values determined. Just like in neural networks, a logistic regression model is fully trained when it has an architecture and weights
- $x^{(i)}$ represents i'th (ex. the 1st or 2nd element). 
	- For example, $x^{(1)}$ represents the 1st sentence. Given our feature extraction process, it can be $x^{(1)} = [1, 60, 3]$, where "1" is the bias, "60" is the sum of the positive frequency, and "3" is the sum of the negative frequency. 
		- So in this example, the first sentence would be a very positive sentence



---