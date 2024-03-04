
Week 4 of Course 1

**Table of Contents:**
	[[#Transforming Word Vectors]]
	[[#K-nearest neighbors (KNN)]]
	[[#Locality Sensitive Hashing]]
	[[#Searching Documents]]
	[[#Putting it All Together]]
	
	
[[Week4_Slides.pdf|Week 4 Lecture Slides from the course]]

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



---


# K-nearest neighbors (K-NN)

**K-nearest neighbors (KNN)** - This is a **Machine Learning algorithm/model** that finds the nearest points. When we apply the mapping matrix **R** to English words **X**, we most likely won't get the exact vectors in **Y** but we use K-nearest neighbors (KNN) to find the closest matches
- This is another **Machine Learning Algorithm** that we've seen so far in the course. Other one's include:
	- [[Logistic Regression]]
	- [[Naive Bayes]]


**Approximate Nearest (friendly) Neighbors** - Approximate nearest neighbors does not give you the full nearest neighbors but gives you an approximation of the nearest neighbors. I**t usually trades off accuracy for efficiency**. Look at the following plot:
![[Pasted image 20240304135143.png]]
- You are trying to find the nearest neighbor for the red vector (point). The first time, the plane gave you green points. You then ran it a second time, but this time you got the blue points. The third time you got the orange points to be the neighbors. **So you can see as you do it more times, you are likely to get all the neighbors.**



---

# Locality Sensitive Hashing

**Locality sensitive hashing** - Locality sensitive hashing is a technique that allows you to hash similar inputs into the same buckets with high probability.

![[Pasted image 20240304133756.png]]


**Multiple Planes** - You can use multiple planes to get a single hash value. Let's take a look at the following example:
![[Pasted image 20240304134307.png]]

---

# Searching Documents


**Searching Documents** - We can add up words (represented as vectors, using word embedding) as vectors of a document to get the **document vector**, which we can use to compare the similarity of two documents.
- Here is an example:
	![[Pasted image 20240304135727.png]]
	- Here, we have a document with the words "I", "love", "learning" and we were able to represent as the vector [1, 0, 3]. Now, we could do the same for other documents and use **K-NN** to find similar documents

---

# Putting it All Together

So in summary you should now be familiar with the following concepts:
![[Pasted image 20240304135946.png]]


---

