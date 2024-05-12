## 12. Count Vowels and Consonants

**Description:**
Write a function that takes a string as input and returns the count of vowels and consonants in that string.

**Sample Input:**
```
"Hello, World!"
```

**Sample Output:**
```
{
  vowels: 3,
  consonants: 7
}
```

**File Name:** `countVowelsConsonants.js`

**Code Answer:**

```javascript
function countVowelsConsonants(str) {
  const vowels = ['a', 'e', 'i', 'o', 'u'];
  let vowelCount = 0;
  let consonantCount = 0;

  for (let char of str.toLowerCase()) {
    if (vowels.includes(char)) {
      vowelCount++;
    } else if (/[a-z]/.test(char)) {
      consonantCount++;
    }
  }

  return {
    vowels: vowelCount,
    consonants: consonantCount
  };
}

// Example usage
const result = countVowelsConsonants("Hello, World!");
console.log(result); // { vowels: 3, consonants: 7 }
```

**Explanation:**

1. The `countVowelsConsonants` function takes a string `str` as input.
2. An array `vowels` is defined with all the vowels.
3. Two variables `vowelCount` and `consonantCount` are initialized to keep track of the counts.
4. A `for...of` loop iterates over each character `char` in the string `str` after converting it to lowercase.
5. If `char` is a vowel (checked using the `includes` method on the `vowels` array), `vowelCount` is incremented.
6. If `char` is a consonant (checked using a regular expression `/[a-z]/` to match lowercase letters), `consonantCount` is incremented.
7. After the loop, an object with the `vowels` and `consonants` counts is returned.
8. In the example usage, the function is called with the input string `"Hello, World!"`, and the result is logged to the console.

Note: This solution assumes that only lowercase letters are considered for counting vowels and consonants. If you need to handle uppercase letters or non-alphabetic characters differently, you may need to modify the code accordingly.