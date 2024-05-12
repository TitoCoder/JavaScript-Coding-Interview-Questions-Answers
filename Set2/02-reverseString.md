## 2. Reverse a String

**Description:**
Write a function that takes a string as input and returns the reverse of that string.

**Sample Input:**
```
"hello"
```

**Sample Output:**
```
"olleh"
```

**File Name:** `reverseString.js`

**Code Answer:**

```javascript
function reverseString(str) {
  // Convert the string to an array of characters
  const charArray = str.split('');

  // Reverse the array using the reverse() method
  const reversedArray = charArray.reverse();

  // Convert the reversed array back to a string using the join() method
  const reversedStr = reversedArray.join('');

  return reversedStr;
}

// Example usage
console.log(reverseString('hello')); // Output: "olleh"
console.log(reverseString('world')); // Output: "dlrow"
```

**Explanation:**

1. The `reverseString` function takes a string `str` as input.
2. The string is converted to an array of characters using the `split('')` method, which splits the string into an array of individual characters.
3. The `reverse()` method is called on the character array to reverse the order of the elements.
4. The reversed array is then converted back to a string using the `join('')` method, which joins all the elements of the array into a single string.
5. The reversed string is returned by the function.

In the example usage, the `reverseString` function is called with the strings `'hello'` and `'world'`, and the reversed strings `'olleh'` and `'dlrow'` are printed to the console, respectively.

Note that this solution has a time complexity of O(n), where n is the length of the input string, as it needs to iterate through the entire string to convert it to an array and then reverse the array.