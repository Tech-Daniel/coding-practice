# Two Number Sum
Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum. If any two numbers in the input array sum up to the target sum, the function should return them in an array, in any order. If no two numbers sum up to the target sum, the function should return an empty
array.

Note: The target sum has to be obtained by summing two different integers in the array; you can't add a single integer to itself in order to obtain the target sum.

You can assume that there will be at most one pair of numbers summing up to the target sum.


## Intuition:
The intuition for the Two Number Sum problem can be approached from three perspectives: brute force, time optimization, and space optimization.

#### Brute Force Approach: 
The most straightforward approach is to use two nested loops to iterate over each pair of numbers in the array. For each pair, we check if their sum equals the target sum. This approach has a time complexity of O(n^2) and a space complexity of O(1), as we are not using any additional data structures. However, this approach is not efficient for large arrays because it checks every possible pair of numbers.

#### Time Optimization: 
To improve the time complexity, we can use a Set or a Hashmap (Dictionary). We iterate over the array once, and for each number, we calculate its complement (i.e., target sum - current number). If the complement is in the Set or Hashmap, we have found the pair that sums up to the target. If not, we add the current number to the Set or Hashmap. This approach has a time complexity of O(n) and a space complexity of O(n), as we are using a Set or Hashmap to store the numbers. This approach is more efficient than the brute force approach, especially for large arrays, as it only requires a single pass through the array.

#### Space Optimization: 
If we want to optimize for space, we can sort the array first, which takes O(n log n) time. Then, we use two pointers, one at the start of the array and one at the end. We calculate the sum of the numbers at the two pointers. If the sum equals the target, we have found the pair. If the sum is less than the target, we move the left pointer to the right. If the sum is greater than the target, we move the right pointer to the left. We repeat this process until the pointers meet. This approach has a time complexity of O(n log n) due to the sorting, and a space complexity of O(1), as we are not using any additional data structures. This approach is efficient in terms of space, but it requires the array to be sorted first, which may not be desirable in some cases