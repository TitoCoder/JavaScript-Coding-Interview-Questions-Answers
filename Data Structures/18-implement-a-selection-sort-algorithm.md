# Write a function to implement a selection sort algorithm

## Problem Description

Selection sort is a simple sorting algorithm that works by repeatedly finding the minimum element from the unsorted part of the array and swapping it with the first element of the unsorted part. This process is repeated until the entire array is sorted.

The algorithm works as follows:

1. Find the minimum element in the unsorted part of the array.
2. Swap the minimum element with the first element of the unsorted part.
3. Repeat steps 1 and 2 for the remaining unsorted part of the array.

## Requirement

Write a function that takes an array of numbers as input and returns the sorted array using the selection sort algorithm.

## JavaScript Code Answer

Here's a JavaScript implementation of the selection sort algorithm:

```javascript
function selectionSort(arr) {
  const n = arr.length;

  for (let i = 0; i < n - 1; i++) {
    let minIdx = i;

    for (let j = i + 1; j < n; j++) {
      if (arr[j] < arr[minIdx]) {
        minIdx = j;
      }
    }

    // Swap the found minimum element with the first element
    [arr[i], arr[minIdx]] = [arr[minIdx], arr[i]];
  }

  return arr;
}
```

Here's how the `selectionSort` function works:

1. The function takes an array `arr` as input.
2. It initializes a variable `n` to the length of the input array.
3. It then iterates through the array from index `0` to `n-1` using a `for` loop.
4. For each iteration, it initializes a variable `minIdx` to the current index `i`.
5. It then iterates through the remaining unsorted part of the array (from `i+1` to `n-1`) to find the minimum element.
6. If a smaller element is found, it updates the `minIdx` variable to the index of the smaller element.
7. After the inner loop, it swaps the element at index `i` with the element at index `minIdx` using destructuring assignment.
8. Finally, it returns the sorted array.

You can call the `selectionSort` function with an array of numbers as an argument, and it will return the sorted array:

```javascript
const unsortedArray = [5, 2, 8, 1, 9];
const sortedArray = selectionSort(unsortedArray);
console.log(sortedArray); // Output: [1, 2, 5, 8, 9]
```