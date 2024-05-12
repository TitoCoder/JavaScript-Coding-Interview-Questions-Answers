## 1. Palindrome Check

**Description:**
Write a function that takes a string as input and returns `true` if the string is a palindrome (reads the same forward and backward), and `false` otherwise.

**Sample Input:**
```
"racecar"
"hello"
```

**Sample Output:**
```
true
false
```

**File Name:** `palindromeCheck.js`

**Code Answer:**

```javascript
function isPalindrome(str) {
  // Convert the string to lowercase and remove non-alphanumeric characters
  const cleanedStr = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();

  // Reverse the cleaned string
  const reversedStr = cleanedStr.split('').reverse().join('');

  // Check if the original cleaned string is equal to the reversed string
  return cleanedStr === reversedStr;
}

// Example usage
console.log(isPalindrome("racecar")); // true
console.log(isPalindrome("hello")); // false
```

**Explanation:**

1. The `isPalindrome` function takes a string `str` as input.
2. First, we convert the string to lowercase and remove all non-alphanumeric characters using a regular expression and the `replace` method. This ensures that the function works correctly with strings containing spaces, punctuation, or mixed cases.
3. Next, we reverse the cleaned string using the `split`, `reverse`, and `join` methods.
4. Finally, we compare the original cleaned string with the reversed string and return `true` if they are equal (indicating a palindrome), and `false` otherwise.

The code handles various cases, such as strings with spaces, punctuation, and mixed cases. It also works for single-character strings and empty strings (which are considered palindromes).