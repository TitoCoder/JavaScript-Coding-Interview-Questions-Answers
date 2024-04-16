# Write a function to find the missing number in an array of consecutive numbers

## Problem Description

Given an array of consecutive numbers, write a function that can find the missing number in the array.

## Requirements

1. The function should take an array of integers as input.
2. The array should contain consecutive numbers, with one number missing.
3. The function should return the missing number.
4. The function should handle empty arrays and arrays with only one element.

## JavaScript Code Answer

Here's a JavaScript function that solves the problem:

```javascript
function findMissingNumber(arr) {
  // Check if the array is empty or has only one element
  if (arr.length === 0 || arr.length === 1) {
    return null;
  }

  // Calculate the expected sum of the consecutive numbers
  const n = arr.length + 1;
  const expectedSum = (n * (n + 1)) / 2;

  // Calculate the actual sum of the numbers in the array
  const actualSum = arr.reduce((sum, num) => sum + num, 0);

  // Return the difference between the expected sum and the actual sum
  return expectedSum - actualSum;
}
```

Here's how the function works:

1. First, we check if the input array is empty or has only one element. In these cases, we return `null` since there is no missing number.
2. We calculate the expected sum of the consecutive numbers using the formula for the sum of an arithmetic series: `(n * (n + 1)) / 2`, where `n` is the length of the array plus one (since there is one missing number).
3. We calculate the actual sum of the numbers in the array using the `reduce()` method.
4. Finally, we return the difference between the expected sum and the actual sum, which is the missing number.

Here's an example usage:

```javascript
const numbers = [1, 2, 3, 4, 6, 7, 8, 9, 10];
const missingNumber = findMissingNumber(numbers);
console.log(missingNumber); // Output: 5
```

In this example, the array `` is missing the number 5, and the function correctly identifies it as the missing number.