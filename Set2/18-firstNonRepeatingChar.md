## 18. First Non-Repeating Character

**Description:**
Write a function that takes a string as input and returns the first non-repeating character in that string. If there are no non-repeating characters, return `null`.

**Sample Input:**
```
"hello"
```

**Sample Output:**
```
"h"
```

**File Name:** `firstNonRepeatingChar.js`

**Code Answer:**

```javascript
function firstNonRepeatingChar(str) {
  // Create a Map to store character counts
  const charCount = new Map();

  // Count the occurrences of each character
  for (const char of str) {
    charCount.set(char, (charCount.get(char) || 0) + 1);
  }

  // Find the first character with count 1
  for (const char of str) {
    if (charCount.get(char) === 1) {
      return char;
    }
  }

  // If no non-repeating character found, return null
  return null;
}

// Example usage
console.log(firstNonRepeatingChar("hello")); // Output: "h"
console.log(firstNonRepeatingChar("aabbcc")); // Output: null
```

**Explanation:**

1. We create a `Map` called `charCount` to store the count of each character in the input string.
2. We iterate over the string and update the count of each character in the `charCount` map.
3. We iterate over the string again and check if any character has a count of 1 (non-repeating). If found, we return that character.
4. If no non-repeating character is found, we return `null`.

The time complexity of this solution is O(n), where n is the length of the input string, as we iterate over the string twice. The space complexity is O(k), where k is the number of unique characters in the string, as we store the count of each character in the `charCount` map.