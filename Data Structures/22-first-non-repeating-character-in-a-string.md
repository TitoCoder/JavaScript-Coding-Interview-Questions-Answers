# Write a function to find the first non-repeating character in a string

## Problem Description

The problem is to write a function that takes a string as input and returns the first non-repeating character in that string. A non-repeating character is a character that appears only once in the string.

## Requirement

The function should have the following characteristics:

1. **Input**: The function should take a string as input.
2. **Output**: The function should return the first non-repeating character in the string. If there are no non-repeating characters, the function should return `null`.
3. **Time Complexity**: The function should have a time complexity of O(n), where n is the length of the input string.
4. **Space Complexity**: The function should have a space complexity of O(1), as it should not use any additional data structures that grow with the size of the input.

## JavaScript Code Answer

Here's a JavaScript function that solves the problem:

```javascript
function findFirstNonRepeatingChar(str) {
  // Create an object to store the count of each character
  const charCount = {};

  // Iterate through the string and count the occurrences of each character
  for (let i = 0; i < str.length; i++) {
    const char = str[i];
    charCount[char] = (charCount[char] || 0) + 1;
  }

  // Iterate through the string again and return the first character with a count of 1
  for (let i = 0; i < str.length; i++) {
    const char = str[i];
    if (charCount[char] === 1) {
      return char;
    }
  }

  // If no non-repeating character is found, return null
  return null;
}
```

Here's how the function works:

1. We create an object `charCount` to store the count of each character in the input string.
2. We iterate through the input string and update the `charCount` object with the count of each character.
3. We iterate through the input string again and return the first character whose count is 1 (i.e., the first non-repeating character).
4. If no non-repeating character is found, we return `null`.

The time complexity of this solution is O(n), where n is the length of the input string, because we iterate through the string twice. The space complexity is O(1) because the size of the `charCount` object does not depend on the size of the input string.