

**Table of Contents:**
	[[#Transforming Word Vectors]]


---


# Transforming Word Vectors

In the [[Vector Space Models|previous week]], I showed you how we can plot word vectors. Now, you will see how you can take a word vector and learn a mapping that will allow you to translate words by learning a "transformation matrix". Here is a visualization:
![[Pasted image 20240303113705.png]]


Here is a visualization of that showing you the aligned vectors:
![[Pasted image 20240303113744.png]]
Note that 
- **X** corresponds to the matrix of English word vectors
- **Y** corresponds to the matrix of French word vectors
- **R** is the mapping matrix.


**K-nearest neighbors (KNN)** - This is a **Machine Learning algorithm/model** that finds the nearest points. When we apply the mapping matrix **R** to English words **X**, we most likely won't get the exact vectors in **Y** but we use K-nearest neighbors (KNN) to find the closest matches
- This is another **Machine Learning Algorithm** that we've seen so far in the course. Other one's include:
	- [[Logistic Regression]]
	- [[Naive Bayes]]



---

