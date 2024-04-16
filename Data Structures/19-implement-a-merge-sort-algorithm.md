# Write a function to implement a merge sort algorithm
## Problem Description

Merge sort is a popular sorting algorithm that follows the divide-and-conquer paradigm. The algorithm works by recursively dividing the input array into smaller subarrays, sorting them, and then merging the sorted subarrays back together to form the final sorted array.

The merge sort algorithm has a time complexity of O(n log n), making it an efficient choice for sorting large datasets.

## Requirement

Implement a `mergeSort` function that takes an array as input and returns the sorted array using the merge sort algorithm.

## JavaScript Code Answer

Here's an implementation of the `mergeSort` function in JavaScript:

```javascript
function mergeSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const middle = Math.floor(arr.length / 2);
  const left = arr.slice(0, middle);
  const right = arr.slice(middle);

  return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
  let result = [];
  let leftIndex = 0;
  let rightIndex = 0;

  while (leftIndex < left.length && rightIndex < right.length) {
    if (left[leftIndex] < right[rightIndex]) {
      result.push(left[leftIndex]);
      leftIndex++;
    } else {
      result.push(right[rightIndex]);
      rightIndex++;
    }
  }

  return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex));
}

// Example usage
const unsortedArray = [5, 2, 8, 1, 9, 3];
const sortedArray = mergeSort(unsortedArray);
console.log(sortedArray); // Output: [1, 2, 3, 5, 8, 9]
```

The `mergeSort` function first checks if the input array has 1 or fewer elements, in which case it returns the array as is. Otherwise, it divides the array into two halves, recursively sorts the left and right halves, and then merges the sorted halves using the `merge` function.

The `merge` function takes two sorted arrays, `left` and `right`, and merges them into a single sorted array. It does this by comparing the first elements of the two arrays and adding the smaller one to the `result` array. It then moves the pointer of the array with the smaller element and continues the process until one of the arrays is empty. Finally, it concatenates the remaining elements from the non-empty array to the `result` array.

The time complexity of the `mergeSort` function is O(n log n), as it divides the input array into smaller subarrays and then merges them back together in a logarithmic time.