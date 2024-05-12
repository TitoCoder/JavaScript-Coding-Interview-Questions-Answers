## 16. Reverse Words in a String

**Description:**
Write a function that takes a string as input and returns a new string with the words reversed. The order of the words should be reversed, but the order of the characters within each word should remain the same.

**Sample Input:**
```
"The quick brown fox"
```

**Sample Output:**
```
"fox brown quick The"
```

**File Name:** `reverseWordsInString.js`

**Code Answer:**

```javascript
function reverseWordsInString(str) {
  // Split the string into an array of words
  const words = str.split(' ');

  // Reverse the order of the words
  const reversedWords = words.reverse();

  // Join the reversed words back into a string
  const reversedString = reversedWords.join(' ');

  return reversedString;
}

// Example usage
const originalString = "The quick brown fox";
const reversedString = reverseWordsInString(originalString);
console.log(reversedString); // Output: "fox brown quick The"
```

**Explanation:**

1. The function `reverseWordsInString` takes a string `str` as input.
2. The string is split into an array of words using the `split` method with the space character `' '` as the separator: `const words = str.split(' ');`. This creates an array of individual words, e.g., `["The", "quick", "brown", "fox"]`.
3. The `reverse` method is called on the `words` array to reverse the order of the words: `const reversedWords = words.reverse();`. This gives us `["fox", "brown", "quick", "The"]`.
4. The `join` method is called on the `reversedWords` array with the space character `' '` as the separator to create a new string with the words in the reversed order: `const reversedString = reversedWords.join(' ');`. This gives us the final string `"fox brown quick The"`.
5. The `reversedString` is returned as the output of the function.

Note that this solution assumes that the input string contains only words separated by single spaces. If the input string contains multiple consecutive spaces or other whitespace characters, you may need to modify the code accordingly.