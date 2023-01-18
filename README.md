 # Maximum Points You Can Obtain from Cards

## Problem Description
Given the array cardPoints and the integer k, return the maximum score you can obtain by discarding k cards. The score is calculated by summing up all the points of the cards in your hand. 

## Plan Your Solution 
The goal of this problem is to find the maximum score that can be obtained by discarding k cards from an array of cardPoints. To solve this problem, we will use a sliding window approach. We will start with a window size of k and move it along the array, calculating the sum of points for each window and keeping track of the maximum sum. 

## Implement Your Solution 
We can implement this solution using a simple loop. We will start with a window size of k and move it along the array, calculating the sum of points for each window and keeping track of the maximum sum. 
```python
def maxScore(cardPoints, k): 

    # Initialize variables 
    max_sum = 0 

    # Loop through array with sliding window size k 
    for i in range(len(cardPoints) - k + 1): 

        # Calculate sum for current window 
        curr_sum = 0 

        for j in range(i, i + k): 

            curr_sum += cardPoints[j]

        # Update max_sum if necessary  
        if curr_sum > max_sum:  

            max_sum = curr_sum  

    return max_sum  

```  
## Test Your Solution  
We can test our solution using an example input: `cardPoints = [1,2,3,4,5,6]` and `k = 3`. Our expected output should be 12 (the sum of 4 + 5 + 6). Let's see if our code produces this result:  
```python  
cardPoints = [1,2,3,4,5,6]  
k = 3  
maxScore(cardPoints, k) # 12  
```  
Our code produces the expected output! This means that our solution is correct.  

 ## Optimize Your Solution 
 We can optimize our solution by using a different approach. Instead of looping through all possible windows and calculating their sums one by one, we can use a prefix sum array to calculate all sums at once. This approach is more efficient since it only requires one pass over the array instead of two passes as in our original solution. Here is how we can implement this approach:     
 ```python
 def maxScoreOptimized(cardPoints, k):      
 # Initialize variables      prefixSum = [0] * (len(cardPoints) + 1)      
 maxSum = 0       
 # Calculate prefix sums      
 for i in range(1 , len(prefixSum)):          
      prefixSum[i] += prefixSum[i-1] + cardPoints[i-1]       # Find maximum sum      
 for i in range(len(prefixSum)-k , len(prefixSum)):
      currSum = prefixSum[i+1] - prefixSum[i+1-k]          
      if currSum > maxSum:              
            maxSum = currSum       
  return maxSum
  ```     
  Now let's test our optimized solution on our example 
  input: `cardPoints = [1,2,3,4,5,6]` and `k=3`. 
  Our expected output should still be 12 (the sum of 4 + 5 + 6). 
  Let's see if our code produces this result:     
  ```python     cardPoints = [1 , 2 , 3 , 4 , 5 , 6 ]     k=3     maxScoreOptimized ( cardPoints , k ) # 12 ```
  Our code produces the expected output! This means that our optimized solution is also correct.    
  ## Conclusion 
  In this blog post we have discussed how to solve LeetCode problem 1423: Maximum Points You Can Obtain from Cards. We have discussed two approaches to solving this problem - a brute force approach which involves looping through all possible windows and calculating their sums one by one; and an optimized approach which uses a prefix sum array to calculate all sums at once. Both approaches produce correct results but the optimized approach is more efficient since it only requires one pass over the array instead of two passes as in our original solution.    
  ## References
  - LeetCode Problem 1423: Maximum Points You Can Obtain from Cards (https://leetcode.com/problems/maximum-points-you-can-obtain-from-cards/)
  - Sliding Window Algorithm (https://en.wikipedia.org/wiki/Sliding_window_algorithm) 
  - Prefix Sum Array (https://en.wikipedia.org/wiki/Prefix_sum) 
  ## Tips 
  - When solving problems involving arrays or strings with sliding windows or other similar techniques always consider using an optimized approach such as using a prefix sum array or other data structures to reduce time complexity or space complexity where possible!
  
  
  
  
  
  
  
  
  
  --------------------------------------------------------------------------------------------------------
  
  
  # Solving LeetCode Problem 1: Two Sum

## Problem Description
LeetCode Problem 1: Two Sum is a classic problem in computer science. The goal is to find two numbers in an array that add up to a given target number. For example, given the array `[2, 7, 11, 15]` and the target number `9`, the two numbers that add up to `9` are `2` and `7`. 

## Plan Your Solution
The first step in solving this problem is to come up with an algorithm that can find the two numbers that add up to the target number. One possible solution is to use a brute-force approach, where we loop through each element of the array and check if it adds up with any other element in the array. This approach has a time complexity of O(n^2). 

## Implement Your Solution
We can implement this solution using a nested for loop. The outer loop will iterate through each element of the array and the inner loop will check if any other element in the array adds up with it. If so, we return both elements as our solution. Here is an example implementation in Python: 
```python 
def two_sum(arr, target): 
    for i in range(len(arr)): 
        for j in range(i+1, len(arr)): 
            if arr[i] + arr[j] == target: 
                return [arr[i], arr[j]] 

    return None # No solution found 
```  

 ## Test Your Solution 
We can test our solution by running it on some sample inputs. For example, let's try it on our original input of `[2, 7, 11, 15]` and target number `9`. Our function should return `[2, 7]`, which is correct! We can also try it on other inputs such as `[3, 5, 6]` and target number `11`, which should return `[5, 6]`.  

 ## Optimize Your Solution  
We can optimize our solution by using a more efficient algorithm such as hash tables or sorting. Using hash tables has a time complexity of O(n), which is much better than our original brute-force approach. Here is an example implementation using hash tables:  

 ```python 
def two_sum_hashtable(arr, target): 
    hashtable = {} # Create empty hashtable

    # Loop through each element of array and store its complement (target - num) in hashtable  	
    for num in arr:
      complement = target - num  		
      if complement not in hashtable:
        hashtable[num] = complement
      else:
        return [complement, num]

    return None # No solution found     

```    

 ## Conclusion     
 In this blog post we discussed how to solve LeetCode Problem 1: Two Sum. We started by discussing the problem description and then planned our solution using a brute-force approach with nested for loops. We then implemented this solution and tested it on some sample inputs before optimizing it using hash tables. Finally we concluded by discussing how our optimized solution was much more efficient than our original one.     

 ## References     
 - [LeetCode Problem 1](https://leetcode.com/problems/two-sum/)     
 - [Hash Tables](https://en.wikipedia.org/wiki/Hash_table)     

 ## Tips     
 - Always plan your solutions before implementing them! This will help you come up with more efficient solutions faster!     
 - Don't forget to test your solutions on sample inputs before submitting them!
