## 7. Longest Word

**Description:**
Write a function that takes a string as input and returns the longest word in that string.

**Sample Input:**
```
"The quick brown fox jumps over the lazy dog"
```

**Sample Output:**
```
"brown"
```

**File Name:** `longestWord.js`

**Code Answer:**

```javascript
function longestWord(str) {
  // Split the string into an array of words
  const words = str.split(' ');

  // Initialize a variable to store the longest word
  let longest = '';

  // Iterate over the array of words
  for (let word of words) {
    // If the current word is longer than the longest word so far, update the longest word
    if (word.length > longest.length) {
      longest = word;
    }
  }

  // Return the longest word
  return longest;
}

// Example usage
const sentence = "The quick brown fox jumps over the lazy dog";
const result = longestWord(sentence);
console.log(result); // Output: "brown"
```

**Explanation:**

1. The function `longestWord` takes a string `str` as input.
2. The string is split into an array of words using the `split` method with the space character `' '` as the separator.
3. An empty string `''` is initialized to store the longest word found so far.
4. The function iterates over the array of words using a `for...of` loop.
5. For each word, the length of the word is compared with the length of the current longest word.
6. If the current word is longer than the longest word so far, the `longest` variable is updated with the current word.
7. After iterating over all the words, the `longest` variable contains the longest word in the string.
8. The `longest` word is returned as the output of the function.
9. In the example usage, the sentence `"The quick brown fox jumps over the lazy dog"` is passed to the `longestWord` function, and the output `"brown"` is logged to the console.

This solution has a time complexity of O(n), where n is the number of words in the input string, as it iterates over the array of words once. The space complexity is O(n) as well, since it creates an array of words from the input string.