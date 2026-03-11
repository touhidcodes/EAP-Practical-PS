# Basic Problem Solving

# 1. Reverse Words in a Sentence

## Problem

Reverse the **order of words** in a sentence.

### What is Expected

Return a new sentence where **word order is reversed but words remain unchanged**.

### Input

```
"Hello World"
```

### Output

```
"World Hello"
```

## How to Think

A sentence is basically a **list of words separated by spaces**.

Example:

```
"Hello World JS"
```

can be thought of as:

```
["Hello", "World", "JS"]
```

If we reverse the array:

```
["JS", "World", "Hello"]
```

Joining them again with spaces gives the result.

## Algorithm

1. Split the sentence into words.
2. Reverse the array.
3. Join words back into a string.

## Solution

```javascript
function reverseWords(sentence) {

  // Step 1: convert sentence into array
  const words = sentence.split(" ");

  // Step 2: reverse order
  const reversed = words.reverse();

  // Step 3: convert array back to string
  return reversed.join(" ");
}
```

---

# 2. Find All Pairs with Target Sum

## Problem

Find all pairs in an array whose **sum equals a target value**.

### What is Expected

Return every pair of numbers whose sum equals the target.

### Input

```
arr = [2,7,11,15]
target = 9
```

### Output

```
[[2,7]]
```

## How to Think

A **pair** means two numbers.

We need to check:

```
arr[i] + arr[j] = target
```

So we compare **each number with every other number**.

Example:

```
2 + 7 = 9 ✔
2 + 11 = 13 ✖
```

## Algorithm

1. Loop through the array.
2. For each element, check the remaining elements.
3. If sum equals target → store pair.

## Solution

```javascript
function findPairs(arr, target) {

  const pairs = [];

  for (let i = 0; i < arr.length; i++) {

    for (let j = i + 1; j < arr.length; j++) {

      // check if pair sum equals target
      if (arr[i] + arr[j] === target) {
        pairs.push([arr[i], arr[j]]);
      }

    }
  }

  return pairs;
}
```

---

# 3. Check if Array is Palindrome

## Problem

Check whether an array reads **the same forward and backward**.

### What is Expected

Return **true** if palindrome, otherwise **false**.

### Input

```
[1,2,3,2,1]
```

### Output

```
true
```

## How to Think

A **palindrome** means:

```
forward === backward
```

Examples:

```
[1,2,3,2,1] ✔
[1,2,3,4] ✖
```

The first element should equal the last element.

Example:

```
arr[0] === arr[last]
arr[1] === arr[last-1]
```

If all match → palindrome.

## Algorithm

1. Compare first and last element.
2. Move inward.
3. If any pair mismatches → return false.

## Solution

```javascript
function isPalindrome(arr) {

  for (let i = 0; i < arr.length / 2; i++) {

    // compare start and end elements
    if (arr[i] !== arr[arr.length - 1 - i]) {
      return false;
    }

  }

  return true;
}
```

---

# 4. Remove Duplicate Characters

## Problem

Remove duplicate characters from a string **while maintaining order**.

### What is Expected

Return a string containing **only unique characters**.

### Input

```
"programming"
```

### Output

```
"progamin"
```

## How to Think

We need to **keep track of characters we already used**.

Example:

```
p → add
r → add
o → add
g → add
r → skip (already exists)
```

So we only add characters **if we haven't seen them before**.

## Algorithm

1. Create an empty result string.
2. Loop through characters.
3. Add character only if not already included.

## Solution

```javascript
function removeDuplicates(str) {

  let result = "";

  for (let char of str) {

    // add character only if not already present
    if (!result.includes(char)) {
      result += char;
    }

  }

  return result;
}
```

---

# 5. Count Vowels in a String

## Problem

Count how many **vowels** exist in a string.

### What is Expected

Return the number of vowels.

### Input

```
"hello world"
```

### Output

```
3
```

## How to Think

English vowels are:

```
a, e, i, o, u
```

So we check if each character **belongs to the vowel set**.

Example:

```
h → no
e → yes
l → no
o → yes
```

## Algorithm

1. Define vowels.
2. Loop through characters.
3. Increase count when vowel found.

## Solution

```javascript
function countVowels(str) {

  const vowels = "aeiouAEIOU";
  let count = 0;

  for (let char of str) {

    // check if character is a vowel
    if (vowels.includes(char)) {
      count++;
    }

  }

  return count;
}
```

---

# 6. Rotate String by k Positions

## Problem

Rotate a string to the **right by k positions**.

### What is Expected

Move the last **k characters to the beginning**.

### Input

```
"hello", k = 2
```

### Output

```
"lohel"
```

## How to Think

Break the string into **two parts**.

Example:

```
hello
```

Split:

```
hel | lo
```

Then swap order:

```
lo + hel
```

## Algorithm

1. Take last `k` characters.
2. Take remaining characters.
3. Combine them.

## Solution

```javascript
function rotateString(str, k) {

  // last k characters
  const end = str.slice(-k);

  // remaining characters
  const start = str.slice(0, str.length - k);

  return end + start;
}
```

---

# 7. Move All Zeros to End

## Problem

Move all `0` values to the **end of the array** while keeping order.

### What is Expected

Return the updated array.

### Input

```
[0,1,0,3,12]
```

### Output

```
[1,3,12,0,0]
```

## How to Think

Separate numbers into **two groups**:

- Non-zero numbers
- Zero numbers

Then combine them.

## Algorithm

1. Extract non-zero numbers.
2. Extract zeros.
3. Combine arrays.

---

## Solution

```javascript
function moveZeros(arr) {

  // get non-zero numbers
  const nonZero = arr.filter(num => num !== 0);

  // get zeros
  const zeros = arr.filter(num => num === 0);

  // combine both
  return nonZero.concat(zeros);
}
```

---


# 8. Rotate a Matrix 90° Clockwise

### Problem

Given a 2D matrix, rotate it **90 degrees clockwise**.
For example, the first row becomes the last column, the second row becomes the second-to-last column, and so on.

### What is Expected

Return a **new 2D matrix** rotated 90° clockwise.

### Input

```javascript
[
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]
```

### Output

```javascript
[
  [7, 4, 1],
  [8, 5, 2],
  [9, 6, 3]
]
```

## How to Think

Think of a matrix as a **grid of rows and columns**.

* **Original:**

```
1 2 3
4 5 6
7 8 9
```

* **Rotated 90° clockwise:**

```
7 4 1
8 5 2
9 6 3
```

* The **first row `[1,2,3]` becomes the last column**
* The **second row `[4,5,6]` becomes the second column**
* The **third row `[7,8,9]` becomes the first column**

So, the value at **mat[i][j]** in the original matrix moves to **res[j][n-1-i]** in the rotated matrix.

## Algorithm

1. Get the size of the matrix `n` (assume square matrix).
2. Create a new empty matrix `res` of same size.
3. Loop through each row `i` and column `j` of the original matrix: Move `mat[i][j]` to `res[j][n-1-i]`
4. Return the new rotated matrix.

## Solution

```javascript
function rotateMatrix(mat) {
 // number of rows (and columns, since square)
  const n = mat.length;
  
  // create empty matrix to store rotated values
  const res = Array.from({ length: n }, () => Array(n));

  // loop through every element in original matrix
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      // move element mat[i][j] to rotated position res[j][n-1-i]
      res[j][n - 1 - i] = mat[i][j];
    }
  }

  return res; // return the rotated matrix
}
```

---

# 9. Find Majority Element

### Problem

Given an array, find the element that appears **more than n/2 times**, if it exists.

* If no element appears more than half the time, return `null`.

### What is Expected

Return the **majority element** or `null`.

### Input

```javascript
[3, 3, 4, 2, 3, 3]
```

### Output

```javascript
3
```

## How to Think

A **majority element** is one that occurs **more than half the array size**.

* Count how many times each element appears.
* If the count is greater than `n / 2`, it’s the majority.


## Algorithm

1. Create an **empty object** to count occurrences of each element.
2. Loop through the array and **increment the count** in the object.
3. If count of an element **exceeds n/2**, return that element.
4. If no element exceeds n/2, return `null`.

## Solution

```javascript
function majorityElement(arr) {
  const countMap = {}; // object to store frequency

  for (let num of arr) {
    // increment count of current number
    countMap[num] = (countMap[num] || 0) + 1;

    // check if this number is now majority
    if (countMap[num] > arr.length / 2) return num;
  }

  // no majority element found
  return null;
}
```

---

# 10. Find Missing Elements in a Consecutive Sequence

### Problem

Given an unsorted array of numbers that **should form a consecutive sequence**, return **all missing numbers**.

### What is Expected

Return an array of numbers that are missing from the consecutive sequence.

### Input

```javascript
[1, 2, 4, 6]
```

### Output

```javascript
[3, 5]
```

## How to Think

A **consecutive sequence** is a sequence of numbers with **no gaps**.

**Steps to find missing numbers:**

1. Find the **minimum and maximum** numbers in the array.
2. Loop from **min to max**.
3. If a number is **not in the array**, add it to the result.

## Algorithm

1. Initialize an empty array `missing`.
2. Get `min` and `max` of the array.
3. Loop `i` from `min` to `max`: If `i` is **not included** in the array, push to `missing`.
4. Return `missing` array.

## Solution

```javascript
function findMissingElements(arr) {
  const missing = [];
  const min = Math.min(...arr); // smallest number
  const max = Math.max(...arr); // largest number

  for (let i = min; i <= max; i++) {
    if (!arr.includes(i)) { // if number is missing
      missing.push(i);
    }
  }

  return missing;
}
```

---

