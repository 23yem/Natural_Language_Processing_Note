Week 1 of Course 2 


Table of Contents:
	[[#Autocorrect]]
	[[#Minimum Edit Distance]]
	[[#Minimum Edit Distance Algorithm]]

[[C2_W1.pdf|Week 1 slides]]

---
# Autocorrect


**Steps for Autocorrect:**
1. **Identify a misspelled word**
	- For simplicity, we will just mark a word as misspelled if it isn't in our dictionary of words. We won't mark it if it's spelled correctly but used in wrong context (we need more advanced algorithm for that)
2. **Find strings n edit distance away** 
	- We can use insert, delete, switch (two adjacent letters), and replace
	- Using minimum edit distance 
	- These could be random strings
3. **Filter candidates**
	- Keep only the real words from the previous steps
		- Remove words not in dictionary
4. **Calculate word probabilities**
	- Choose the word that is most likely to occur in that context
	- The probability is $P(w) = \frac{C(w)}{V}$
		- P(w) = Probability of the word
		- C(w) = The number of times the word appears
		- V = Total size of the corpus


---
# Minimum Edit Distance

Minimum Edit Distance -  minimum edit distance tells you the **minimum amount of edits to change one word into another**.
 


---
# Minimum Edit Distance Algorithm

When computing the minimum edit distance, you would start with a _source word_ and transform it into the _target word_. Let's look at the following example:

![[Pasted image 20240315183356.png]]

To populate the following table: 
![[Pasted image 20240315183754.png]]

There are three equations:

- **D[i,j] = D[i-1, j] + del_cost:** this indicates you want to populate the current cell (i,j) by using the cost in the cell found directly above.
    
- **D[i,j] = D[i, j-1] + ins_cost:** this indicates you want to populate the current cell (i,j) by using the cost in the cell found directly to its left.
    
- **D[i,j] = D[i-1, j-1] + rep_cost:** the rep cost can be 2 or 0 depending if you are going to actually replace it or not.
    
At every time step you check the three possible paths where you can come from and you select the least expensive one. Once you are done, you get the following:
![[Pasted image 20240315183821.png]]




![[Pasted image 20240315184140.png]]

To summarize, you have seen the **levenshtein distance** which specifies the cost per operation. If you need to reconstruct the path of how you got from one string to the other, you can use a **backtrace**. You should keep a simple pointer in each cell letting you know where you came from to get there. So you know the path taken across the table from the top left corner, to the bottom right corner. You can then reconstruct it.

This method for computation instead of brute force is a technique known as dynamic programming. You first solve the smallest subproblem first and then reusing that result you solve the next biggest subproblem, saving that result, reusing it again, and so on. This is exactly what you did by populating each cell from the top right to the bottom left. It’s a well-known technique in computer science!



---


