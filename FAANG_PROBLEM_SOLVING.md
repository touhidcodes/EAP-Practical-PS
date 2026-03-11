# FAANG Problem Solving Practice

## 1. Rotate an Array by k Positions

### Problem
Write a function to rotate an array **to the right by `k` positions** without using built-in rotate or reverse functions.

### Expected
The elements of the array should shift right `k` times, and elements that fall off the end should wrap around to the front.

### Input

- An array of integers, e.g., `[1, 2, 3, 4, 5]`
- An integer `k` representing number of rotations, e.g., `2`

### Output

Rotated array, e.g., `[4, 5, 1, 2, 3]`

### Hint

- Consider reversing sections of the array in-place.
- Use modulo (`%`) to handle `k` greater than array length.

---

## 2. Find the Missing Number in an Array

### Problem
Given an array of numbers from `1` to `n` with **one number missing**, find the missing number **efficiently**.

### Expected
Return the missing number.

### Input

Array of integers, e.g., `[1, 2, 4, 5]`

### Output

Missing number, e.g., `3`

### Hint

- Use the formula for the sum of the first `n` natural numbers: `n * (n + 1) / 2`.
- Subtract the sum of array elements from this total.

---

## 3. Merge Two Sorted Arrays

### Problem
Write a function to **merge two sorted arrays** into one sorted array without using built-in `sort()`.

### Expected:
Return a single sorted array containing all elements from both arrays.

### Input:

- `arr1 = [1, 3, 5]`
- `arr2 = [2, 4, 6]`

### Output

`[1, 2, 3, 4, 5, 6]`

### Hint

Use two pointers, one for each array, and compare elements to merge step by step.

---

## 4. Find the Longest Substring Without Repeating Characters

### Problem
Given a string, find the **length of the longest substring** that contains no repeated characters.

### Expected
Return the length of the longest substring without duplicates.

### Input

`"abcabcbb"`

### Output

`3` (substring `"abc"`)

### Hint

Use a sliding window and a hash set/map to track characters.

---

## 5. Check if Two Arrays Are Equal

### Problem
Write a function to check whether **two arrays contain the same elements**, regardless of order.

### Expected
Return `true` if arrays are equal, `false` otherwise.

### Input

`[1, 2, 3]` and `[3, 2, 1]`

### Output

`true`

## Hint

Count frequency of each element in both arrays using a map or sort both arrays and compare.

---

## 6. Move All Zeros to the End of an Array

### Problem
Given an array, move all zeros to the **end** while maintaining the order of non-zero elements.

### Expected
Return the modified array.

### Input

`[0, 1, 0, 3, 12]`

### Output

`[1, 3, 12, 0, 0]`

### Hint

Use two pointers: one for scanning elements and one for placing non-zeros.

---

## 7. Implement Your Own `map()` Function

### Problem
Write a custom `map()` function that works like the built-in array `map` method.

### Expected
It should return a new array with the function applied to each element.

### Input

- Array: `[1, 2, 3]`
- Callback: `(x) => x * 2`

## Output

`[2, 4, 6]`

### Hint

Use a `for` loop to iterate through the array and apply the callback to each element.

---

## 8. Find the Intersection of Two Arrays

### Problem
Write a function that returns the **common elements** between two arrays.

### Expected
Return an array of common elements without duplicates.

### Input

`[1, 2, 2, 3]` and `[2, 3, 4]`

### Output

`[2, 3]`

### Hint

Use a set for one array and filter elements from the second array.

---

## 9. Find the First Non-Repeating Character in a String

### Problem
Given a string, return the **first character** that does not repeat.

### Expected
Return the character or `null` if all characters repeat.

### Input

`"swiss"`

### Output

`"w"`

### Hint

Use a frequency map to count characters, then find the first with count `1`.

---

## 10. Check if a Number is a Perfect Square Without `Math.sqrt()`

### Problem
Write a function to determine if a number is a **perfect square** using loops or binary search.

### Expected
Return `true` if it’s a perfect square, `false` otherwise.

### Input

`16`

### Output

`true`

### Hint

- Use binary search between `1` and `num`.
- Or incrementally check `i*i` until it equals or exceeds `num`.

---

## Bonus Questions (Optional for Practice)

**11. Find the Maximum Product of Two Elements in an Array**

* Input: `[3, 5, 2, 7]` → Output: `35` (5 * 7)
* Hint: Track the two largest numbers.

**12. Rotate a Matrix 90° Clockwise**

* Input: `[[1,2],[3,4]]` → Output: `[[3,1],[4,2]]`
* Hint: Transpose + reverse rows.

**13. Find All Pairs with Given Sum**

* Input: `[1,2,3,4]`, sum `5` → Output: `[[1,4],[2,3]]`
* Hint: Use a set to check for complements.

---

