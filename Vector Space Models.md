

Table of Contents:
	[[#Vector Space Models]]
	[[#Word Embeddings]]
	[[#Similarity Metric]]
	

[[Week3_Slides.pdf|Week 3 Lecture Slides from the course]]

---
# Vector Space Models

**Vectors** - Vector Space Models represent words and documents as **vectors**
- This **captures** relative **meaning** of words



**Applications of Vector Space Models** - These include:
- Information Extraction
- Machine Translation
- Chatbots


**Word by Word Design** - This is one way to design a vector for a certain word. It measures the number of times another word is found within distance "k" of that word in a sentence:
![[Pasted image 20240229210508.png]]
- As you can see, for the word "data", the word "simple" appears 2 times within distance k=2 (ex. "simple data" and "simple raw data'), and then "raw" and "like" appear once within distance k=2 of the word "data"
- This type of vector structure allows for us to see **which words have correlation with one another**

**Word by Document** - This is a more general and less complex vector structure. It count the number of times a word appears in a certain category of a word database. 
![[Pasted image 20240229210833.png]]
- In this example, the word "data" appears 500 times in the word documents that are categorized as "Entertainment" and then this repeats for the other categories of documents (a.k.a. corpus)
- This allows you to see **which categories of documents have correlations with one another**

---



# Word Embeddings

**Word Embeddings** - Representing words as a vector of extremely high dimensionality (vectors with hundreds of indexes). 
- This allows you to turn words in numbers and you can do calculations on them to find correlations between words and also relationships between words

**Manipulating word embeddings** - You can do math on the word embeddings which allows you to find relationships between words.
![[Pasted image 20240229220751.png]]
- For example, if we know the relationship between the vector "USA" and "Washington DC" (capital of US), we can apply the same relationship on "Russia" to find the capital of Russia (Moscow). This allows us to do math on words

---


# Similarity Metric:

**Euclidian Distance** - This is a similarity metric which tells us how close two words are. It is the length of a straight line between two words represented as points on a graph. You use a formula similar to the distance formula but then make it more complex for non 2 dimensional points![[Pasted image 20240229213214.png]]
- This picture above uses the distance formula since this is one a 2 dimensional graph

![[Pasted image 20240229213310.png]]
- This picture includes 3 dimensions (AI, drinks, and food) so it uses the formula on the top of the picture. But, it's similar to the distance formula where you just add more terms under the square root for the amount of dimensions 




**Cosine Similarity** - This is another (and more **popular**) similarity metric. It measures the angle between two vectors, and gives a value between 0 (not similar) to 1 (very similar). 
![[Pasted image 20240229214651.png]]
![[Pasted image 20240229214713.png]]
![[Pasted image 20240229215132.png]]




**Euclidean Distance Vs. Cosine Similarity** - Cosine Similarity is more popular and it's especially better when the corpuses (database of words) are not the same size and you are trying to compare two corpuses (ex. Food Corpus and Agriculture Corpus). The Euclidean Distance heavily depends on size of corpus as well, while Cosine Similarity doesn't penalize as much if two corpus are different size
![[Pasted image 20240229213902.png]]
- Here, the Eucliean Distance incorrectly concludes that "History Corpus" is more similar to "Agriculture Corpus" than "Food Corpus", but that's only because "Food Corpus" size is small so it's not close to anything in terms of Euclidean Distance. 
- But, the Cosine Similarity doesn't punish the "Food Corpus" for having a small size (it has a great personality) so it correctly identifies that it's more close to "Agriculture corpus" than "History corpus" is. 

---