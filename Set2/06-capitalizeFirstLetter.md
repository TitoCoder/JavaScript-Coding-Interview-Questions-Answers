## 6. Capitalize First Letter

**Description:**
Write a function that takes a string as input and returns the string with the first letter of each word capitalized.

**Sample Input:**
```
"hello world"
```

**Sample Output:**
```
"Hello World"
```

**File Name:** `capitalizeFirstLetter.js`

**Code Answer:**

```javascript
function capitalizeFirstLetter(str) {
  // Split the string into an array of words
  const words = str.split(' ');

  // Capitalize the first letter of each word
  const capitalizedWords = words.map(word => {
    return word.charAt(0).toUpperCase() + word.slice(1);
  });

  // Join the capitalized words back into a string
  const capitalizedStr = capitalizedWords.join(' ');

  return capitalizedStr;
}

// Example usage
console.log(capitalizeFirstLetter('hello world')); // Output: "Hello World"
console.log(capitalizeFirstLetter('the quick brown fox')); // Output: "The Quick Brown Fox"
```

**Explanation:**

1. The `capitalizeFirstLetter` function takes a string `str` as input.
2. The string is split into an array of words using the `split` method with the space character `' '` as the separator.
3. The `map` method is used to iterate over each word in the array. For each word:
   - The `charAt(0)` method is used to get the first character of the word.
   - The `toUpperCase()` method is used to capitalize the first character.
   - The `slice(1)` method is used to get the remaining characters of the word (starting from the second character).
   - The capitalized first character and the remaining characters are concatenated to form the capitalized word.
4. The `join` method is used to combine the capitalized words back into a single string, with the space character `' '` as the separator.
5. The capitalized string is returned.

The code demonstrates the use of string methods like `split`, `map`, `charAt`, `toUpperCase`, `slice`, and `join` to manipulate and transform the input string.