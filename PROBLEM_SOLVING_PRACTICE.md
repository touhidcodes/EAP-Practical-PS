# String & Array Manipulation 

---

## 1. Longest Substring Without Repeating Characters

### Problem
Find the **length of the longest substring** without repeating characters.

### Input

`"abcabcbb"`

### Output

`3` (`"abc"`)

### Hint

Use a sliding window with a hash set/map to track characters.

---

## 2. Count Character Frequency

### Problem
Count the frequency of **each character** in a string.

### Input

`"hello"`

### Output

`{h:1, e:1, l:2, o:1}`

### Hint

Use a map/object to store counts as you iterate through the string.

---

## 3. Check Anagrams

### Problem
Check if two strings are **anagrams** (same characters, different order).

### Input

`"listen"`, `"silent"`

### Output

`true`

### Hint

Sort both strings or use a frequency map for comparison.

---

## 4. Capitalize First Letter of Each Word

### Problem
Capitalize the **first letter of each word** in a string.

### Input

`"hello world from js"`

### Output

`"Hello World From Js"`

### Hint

Split the string by spaces, capitalize first character of each word, and join.

---


## 5. Merge Two Sorted Arrays

### Problem
Merge two sorted arrays into a **single sorted array** without using `sort()`.

### Input

`[1,3,5]`, `[2,4,6]`

### Output

`[1,2,3,4,5,6]`

### Hint

Use two pointers, compare elements, and build the merged array.

---


## 6. Find Intersection of Two Arrays

### Problem:
Find the **common elements** between two arrays.

### Input

`[1,2,2,3]`, `[2,3,4]`

### Output

`[2,3]`

### Hint

Use a set for one array and filter elements from the second array.

---

# Numbers & Math Problems

---

## 7. Generate Fibonacci Numbers

### Problem
Generate the first `n` Fibonacci numbers.

### Input

`n = 5`

### Output

`[0,1,1,2,3]`

### Hint

Use iteration or recursion to generate the sequence.

---

## 8. Factorial Using Recursion

### Problem
Find the factorial of a number using recursion.

### Input

`5`

### Output

`120`

### Hint

Factorial of `n` = `n * factorial(n-1)`. Base case `factorial(0)=1`.

---

## 9. Check Perfect Square Without `Math.sqrt()`

### Problem
Check if a number is a **perfect square** without using built-in sqrt.

### Input

`16`

### Output

`true`

### Hint

Use binary search or loop from 1 to n to check if `i*i == n`.

---

## 10. Second Largest Number in Array

### Problem
Find the second largest number in an unsorted array.

### Input

`[10,5,20,8]`

### Output

`10`

### Hint

Track largest and second largest in one pass.

---

## 11. Maximum Sum of Contiguous Subarray

### Problem
Find the **maximum sum** of a contiguous subarray (Kadane’s algorithm).

### Input

`[-2,1,-3,4,-1,2,1,-5,4]`

### Output

`6` (`[4,-1,2,1]`)

### Hint

Keep running sum, reset if negative, track max sum.

---

# Recursion & Advanced Array Problems

---

## 12. Flatten Nested Array

### Problem
Flatten a nested array of arbitrary depth.

### Input

`[1,[2,[3,4],5]]`

### Output

`[1,2,3,4,5]`

### Hint

Use recursion: check if element is an array, then flatten.

---

## 13. Generate All Subsets (Power Set)

### Problem
Generate all subsets of an array.

### Input

`[1,2]`

### Output

`[[],[1],[2],[1,2]]`

### Hint

Use recursion or bit manipulation.

---

## 14. N-th Stair Climbing Problem

### Problem
Given `n` stairs, find the number of ways to climb 1 or 2 steps at a time.

### Input

`n = 4`

### Output

`5`

### Hint

Recursive formula: `ways(n) = ways(n-1) + ways(n-2)`

---

## 15. Find All Permutations of a String

### Problem
Generate all permutations of a string.

### Input

`"abc"`

### Output

`["abc","acb","bac","bca","cab","cba"]`

### Hint

Use recursion and backtracking.

---

## 16. Trapping Rain Water Problem

### Problem
Given an array of heights, find the **total trapped water**.

### Input

`[0,1,0,2,1,0,1,3,2,1,2,1]`

### Output

`6`

### Hint

Use two-pointer approach or precompute left/right max heights.

---

# Hashing / Frequency / Map Based Problems

---

## 17. First Non-Repeating Character

### Problem
Find the first character that does not repeat in a string.

### Input

`"swiss"`

### Output

`"w"`

### Hint

Use a frequency map to count characters, then find the first with count `1`.

---

## 18. Two Sum Problem

### Problem
Find indices of two numbers in an array that add up to a target.

### Input

`[2,7,11,15]`, target `9`

### Output

`[0,1]`

### Hint

Use a map to store visited numbers and their indices.

---

## 19. Group Strings into Anagrams

### Problem
Group an array of strings into anagrams.

### Input

`["eat","tea","tan","ate","nat","bat"]`

### Output

`[["eat","tea","ate"],["tan","nat"],["bat"]]`

### Hint

Use sorted string as key in a map.

---

## 20. Longest Subarray with Sum Zero

### Problem
Given an array of integers, find the **length of the longest subarray whose sum is 0**.

### Input

`[1, 2, -3, 3, -1, 2, -2]`

### Output

`3` `([1,2,-3]` or `[3,-1,-2])`

### Hint

- Use a prefix sum array and a map to store first occurrences of sums.
 - If the same sum occurs again, the subarray in between has sum 0.
