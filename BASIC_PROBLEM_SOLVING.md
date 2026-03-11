# Basic Problem Solving

---

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

---

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

---

## Algorithm

1. Split the sentence into words.
2. Reverse the array.
3. Join words back into a string.

---

## JavaScript Solution

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

---

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

---

## Algorithm

1. Loop through the array.
2. For each element, check the remaining elements.
3. If sum equals target → store pair.

---

## JavaScript Solution

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

---

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

---

## Algorithm

1. Compare first and last element.
2. Move inward.
3. If any pair mismatches → return false.

---

## JavaScript Solution

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

---

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

---

## Algorithm

1. Create an empty result string.
2. Loop through characters.
3. Add character only if not already included.

---

## JavaScript Solution

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

---

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

---

## Algorithm

1. Define vowels.
2. Loop through characters.
3. Increase count when vowel found.

---

## JavaScript Solution

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

---

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

---

## Algorithm

1. Take last `k` characters.
2. Take remaining characters.
3. Combine them.

---

## JavaScript Solution

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

---

## How to Think

Separate numbers into **two groups**:

- Non-zero numbers
- Zero numbers

Then combine them.

---

## Algorithm

1. Extract non-zero numbers.
2. Extract zeros.
3. Combine arrays.

---

## JavaScript Solution

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
