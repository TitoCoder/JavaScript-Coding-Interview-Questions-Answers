## 4. Vowel Count

**Description:**
Write a function that takes a string as input and returns the count of vowels (a, e, i, o, u) in that string.

**Sample Input:**
```
"hello"
```

**Sample Output:**
```
2
```

**File Name:** `vowelCount.js`

**Code Answer:**

```javascript
function vowelCount(str) {
  // Convert the string to lowercase for case-insensitive matching
  str = str.toLowerCase();

  // Define a set of vowels
  const vowels = new Set(['a', 'e', 'i', 'o', 'u']);

  // Initialize a counter
  let count = 0;

  // Iterate over each character in the string
  for (let char of str) {
    // Check if the character is a vowel
    if (vowels.has(char)) {
      count++;
    }
  }

  return count;
}

// Example usage
console.log(vowelCount("hello")); // Output: 2
console.log(vowelCount("JavaScript")); // Output: 3
```

**Explanation:**

1. The `vowelCount` function takes a string `str` as input.
2. The string is converted to lowercase using `str.toLowerCase()` to handle case-insensitive matching of vowels.
3. A set `vowels` is created with the vowel characters 'a', 'e', 'i', 'o', and 'u'.
4. A counter variable `count` is initialized to 0.
5. The function iterates over each character `char` in the input string using a `for...of` loop.
6. For each character, it checks if the character is a vowel by checking if it exists in the `vowels` set using `vowels.has(char)`.
7. If the character is a vowel, the `count` is incremented.
8. After iterating over all characters, the function returns the final `count`.
9. Example usage is shown by calling `vowelCount` with different input strings and logging the output to the console.

This solution has a time complexity of O(n), where n is the length of the input string, as it iterates over each character once. The space complexity is O(1) since the set of vowels has a fixed size, regardless of the input string length.