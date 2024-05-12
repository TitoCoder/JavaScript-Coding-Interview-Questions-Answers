## 13. Palindrome Permutation

**Description:**
Given a string, write a function to determine if the string is a permutation of a palindrome. A palindrome is a word, phrase, number, or other sequence of characters that reads the same backward as forward.

**Sample Input:**
```
"racecar"
"level"
"hello"
```

**Sample Output:**
```
true
true
false
```

**File Name:** `palindromePermutation.js`

**Code Answer:**

```javascript
function isPalindromePermutation(str) {
  // Convert the string to lowercase and remove non-alphanumeric characters
  const cleanedStr = str.replace(/[^a-zA-Z]/g, '').toLowerCase();

  // Create a frequency map for the characters
  const charFrequency = {};
  for (let char of cleanedStr) {
    charFrequency[char] = (charFrequency[char] || 0) + 1;
  }

  // Check if at most one character has an odd frequency
  let oddCount = 0;
  for (let freq of Object.values(charFrequency)) {
    if (freq % 2 !== 0) {
      oddCount++;
    }
    if (oddCount > 1) {
      return false;
    }
  }

  return true;
}

// Example usage
console.log(isPalindromePermutation('racecar')); // true
console.log(isPalindromePermutation('level')); // true
console.log(isPalindromePermutation('hello')); // false
```

**Explanation:**

1. First, we clean the input string by removing non-alphanumeric characters and converting it to lowercase using a regular expression and the `replace` method.
2. Next, we create a frequency map for the characters in the cleaned string using an object. We iterate over each character and update its frequency in the `charFrequency` object.
3. Then, we check if at most one character has an odd frequency. We iterate over the frequency values in the `charFrequency` object and keep track of the number of odd frequencies using the `oddCount` variable. If `oddCount` becomes greater than 1, we return `false` because a palindrome can have at most one character with an odd frequency.
4. If we finish iterating over all frequencies and `oddCount` is 0 or 1, we return `true` because the string is a permutation of a palindrome.

The time complexity of this solution is O(n), where n is the length of the input string, because we iterate over the string once to create the frequency map and once to check the frequencies. The space complexity is O(1) because the frequency map can have at most 26 characters (for lowercase letters) or 52 characters (for both lowercase and uppercase letters), which is a constant amount of space.