# Write a function to check if a string is a palindrome

# Problem Description
A palindrome is a word, phrase, number, or other sequence of characters that reads the same backward as forward, such as "racecar" or "level". The task is to write a function that takes a string as input and determines whether it is a palindrome or not.

# Requirement
Implement a JavaScript function that takes a string as input and returns a boolean value indicating whether the string is a palindrome or not.

# JavaScript Code Answer
Here's a JavaScript function that checks if a given string is a palindrome:
```javascript
function isPalindrome(str) {
  // Remove non-alphanumeric characters and convert to lowercase
  str = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();

  // Compare the string with its reverse
  return str === str.split('').reverse().join('');
}
```

# Here's how the function works:
* The replace() method is used to remove all non-alphanumeric characters (such as spaces, punctuation, etc.) from the input string, and the resulting string is converted to lowercase using the toLowerCase() method.
* The modified string is then compared to its reverse, which is obtained by splitting the string into an array of characters using split(''), reversing the array using reverse(), and then joining the characters back into a string using join('').
* If the original string is equal to its reverse, the function returns true, indicating that the string is a palindrome. Otherwise, it returns false.

# You can use this function like this:
```javascript
console.log(isPalindrome("racecar")); // true
console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
console.log(isPalindrome("hello")); // false
```

The first two examples will return true, while the third example will return false.