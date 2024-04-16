## Problem Description

An anagram is a word or phrase formed by rearranging the letters of another word or phrase. For example, the words "listen" and "silent" are anagrams because they both use the same letters (l, i, s, t, e, n) in a different order.

The task is to write a function that takes two strings as input and determines whether they are anagrams of each other.

## Requirements

1. The function should accept two strings as input parameters.
2. The function should return a boolean value indicating whether the two strings are anagrams or not.
3. The function should be case-insensitive, meaning that "Listen" and "silent" should be considered anagrams.
4. The function should ignore any non-alphabetic characters (such as spaces, punctuation, or numbers) when checking for anagrams.

## JavaScript Code Solution

Here's a JavaScript function that checks if two strings are anagrams:

```javascript
function areAnagrams(str1, str2) {
  // Remove non-alphabetic characters and convert to lowercase
  str1 = str1.replace(/[^a-zA-Z]/g, '').toLowerCase();
  str2 = str2.replace(/[^a-zA-Z]/g, '').toLowerCase();

  // Check if the lengths of the cleaned strings are equal
  if (str1.length !== str2.length) {
    return false;
  }

  // Convert the strings to arrays, sort them, and compare
  const sortedStr1 = str1.split('').sort().join('');
  const sortedStr2 = str2.split('').sort().join('');

  return sortedStr1 === sortedStr2;
}
```

Here's how the `areAnagrams()` function works:

1. The function first removes any non-alphabetic characters (such as spaces, punctuation, or numbers) from the input strings using a regular expression, and then converts the strings to lowercase.
2. It then checks if the lengths of the cleaned strings are equal. If they are not, the function returns `false` because anagrams must have the same number of characters.
3. Next, the function converts the cleaned strings to arrays, sorts the characters in each array, and then joins the sorted characters back into strings.
4. Finally, the function compares the sorted strings. If they are equal, the function returns `true`, indicating that the two input strings are anagrams. Otherwise, it returns `false`.

You can use this function like this:

```javascript
console.log(areAnagrams('listen', 'silent')); // true
console.log(areAnagrams('hello', 'world')); // false
console.log(areAnagrams('A decimal point', 'I'm a dot in place')); // true
```