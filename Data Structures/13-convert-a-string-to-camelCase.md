# Write a function to convert a string to camelCase
## Problem Description

The task is to write a function that takes a string as input and converts it to camelCase format. In camelCase, the first word starts with a lowercase letter, and each subsequent word starts with an uppercase letter, with no spaces between the words.

## Requirements

1. The function should accept a string as input.
2. The function should return the input string converted to camelCase format.
3. The function should handle different input formats, such as:
   - Words separated by spaces
   - Words separated by underscores
   - Words separated by hyphens
4. The function should preserve the original capitalization of the words, if any.

## JavaScript Code Answer

Here's a JavaScript function that converts a string to camelCase:

```javascript
function toCamelCase(str) {
  // Remove any leading/trailing spaces
  str = str.trim();

  // Split the string into an array of words
  let words = str.split(/[-_\s]+/);

  // Convert the first word to lowercase
  let camelCaseStr = words[0].toLowerCase();

  // Convert the remaining words to camelCase
  for (let i = 1; i < words.length; i++) {
    camelCaseStr += words[i][0].toUpperCase() + words[i].slice(1);
  }

  return camelCaseStr;
}
```

Here's how the function works:

1. The `trim()` method is used to remove any leading or trailing spaces from the input string.
2. The `split()` method is used to split the string into an array of words, using a regular expression that matches one or more of the following characters: `-`, `_`, or whitespace.
3. The first word in the array is converted to lowercase using the `toLowerCase()` method, and stored in the `camelCaseStr` variable.
4. A loop is used to iterate through the remaining words in the array. For each word, the first character is converted to uppercase using the `toUpperCase()` method, and the rest of the word is concatenated to `camelCaseStr` using the `slice()` method.
5. The final camelCase string is returned.

You can use this function like this:

```javascript
console.log(toCamelCase("hello world")); // Output: helloWorld
console.log(toCamelCase("my_name_is_john")); // Output: myNameIsJohn
console.log(toCamelCase("The-quick-brown-fox")); // Output: theQuickBrownFox
```