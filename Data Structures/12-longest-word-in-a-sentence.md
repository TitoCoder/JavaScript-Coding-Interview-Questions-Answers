# Write a function to find the longest word in a sentence

## Problem Description

The task is to write a function that takes a sentence as input and returns the longest word in that sentence.

## Requirements

1. The function should accept a single string parameter representing the sentence.
2. The function should return the longest word in the sentence as a string.
3. If there are multiple words of the same length that are the longest, the function should return the first one that appears in the sentence.
4. The function should handle sentences with multiple words, including punctuation and capitalization.

## JavaScript Code Answer

Here's a JavaScript function that meets the requirements:

```javascript
function findLongestWord(sentence) {
  // Split the sentence into an array of words
  const words = sentence.split(" ");

  // Initialize variables to track the longest word
  let longestWord = "";
  let longestLength = 0;

  // Iterate through the words and update the longest word if necessary
  for (let i = 0; i < words.length; i++) {
    const word = words[i].replace(/[.,!?]/g, ""); // Remove punctuation
    if (word.length > longestLength) {
      longestWord = word;
      longestLength = word.length;
    }
  }

  return longestWord;
}
```

Here's how the function works:

1. The `sentence` parameter is split into an array of words using the `split(" ")` method.
2. The function initializes two variables: `longestWord` to store the longest word, and `longestLength` to store the length of the longest word.
3. The function then iterates through the array of words, removing any punctuation using a regular expression (`/[.,!?]/g`).
4. For each word, the function checks if its length is greater than the current `longestLength`. If so, it updates `longestWord` and `longestLength` accordingly.
5. Finally, the function returns the `longestWord`.

You can use this function like this:

```javascript
const sentence = "The quick brown fox jumps over the lazy dog.";
const longestWord = findLongestWord(sentence);
console.log(longestWord); // Output: "jumps"
```

In this example, the function correctly identifies "jumps" as the longest word in the sentence.