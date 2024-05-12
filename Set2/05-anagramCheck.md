## Problem Name
Anagram Check

## Description
Write a function that takes two strings as input and returns `true` if they are anagrams (contain the same characters in a different order), and `false` otherwise.

## Sample Input
```
"listen", "silent"
"hello", "world"
```

## Sample Output
```
true
false
```

## File Name
`anagramCheck.js`

## Code Answer
```javascript
function anagramCheck(str1, str2) {
  // Remove whitespace and convert to lowercase
  str1 = str1.replace(/\s/g, '').toLowerCase();
  str2 = str2.replace(/\s/g, '').toLowerCase();

  // Check if lengths are different
  if (str1.length !== str2.length) {
    return false;
  }

  // Create character maps
  const charMap1 = {};
  const charMap2 = {};

  // Populate character maps
  for (let char of str1) {
    charMap1[char] = (charMap1[char] || 0) + 1;
  }
  for (let char of str2) {
    charMap2[char] = (charMap2[char] || 0) + 1;
  }

  // Compare character maps
  for (let char in charMap1) {
    if (charMap1[char] !== charMap2[char]) {
      return false;
    }
  }

  return true;
}
```

This function first removes any whitespace and converts both input strings to lowercase. It then checks if the lengths of the two strings are different, in which case they cannot be anagrams.

Next, it creates two character maps (objects) to store the count of each character in the respective strings. It populates these maps by iterating over each character in the strings and incrementing the count for that character in the corresponding map.

Finally, it compares the two character maps. If any character has a different count in the two maps, the function returns `false` because the strings cannot be anagrams. If all characters have the same count in both maps, the function returns `true`, indicating that the strings are anagrams.

Note that this solution assumes that the input strings contain only alphabetic characters (no numbers or special characters). If the input strings can contain other characters, the code would need to be modified accordingly.