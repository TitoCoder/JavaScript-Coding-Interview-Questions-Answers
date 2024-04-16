# Write a function to implement a bubble sort algorithm

## Problem Description

Bubble sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. Bubble sort has a time complexity of O(n^2), making it inefficient for large datasets, but it is easy to implement and can be useful for small lists.

## Requirements

Write a JavaScript function that takes an array of numbers as input and returns the sorted array using the bubble sort algorithm.

## JavaScript Code

Here's an implementation of the bubble sort algorithm in JavaScript:

```javascript
function bubbleSort(arr) {
  const n = arr.length;

  // Traverse through all array elements
  for (let i = 0; i < n - 1; i++) {
    // Last i elements are already in place
    for (let j = 0; j < n - i - 1; j++) {
      // Traverse the array from 0 to n-i-1
      // Swap if the element found is greater
      // than the next element
      if (arr[j] > arr[j + 1]) {
        // Swap arr[j] and arr[j+1]
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }

  return arr;
}

// Example usage
const unsortedArray = [64, 34, 25, 12, 22, 11, 90];
const sortedArray = bubbleSort(unsortedArray);
console.log(sortedArray); // Output: [11, 12, 22, 25, 34, 64, 90]
```

The `bubbleSort` function takes an array `arr` as input and returns the sorted array. It uses two nested loops to traverse the array. The outer loop runs `n-1` times, where `n` is the length of the array. The inner loop runs `n-i-1` times, where `i` is the current iteration of the outer loop. This is because the last `i` elements are already in place and don't need to be compared.

Inside the inner loop, the function compares adjacent elements and swaps them if they are in the wrong order. The swapping is done using the array destructuring assignment `[arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]`.

Finally, the function returns the sorted array.