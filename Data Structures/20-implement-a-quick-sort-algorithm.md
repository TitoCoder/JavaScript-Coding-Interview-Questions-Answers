# Write a function to implement a quick sort algorithm
## Problem Description

Quick sort is a popular sorting algorithm that uses a divide-and-conquer strategy to sort an array in ascending order. The algorithm works by selecting a 'pivot' element from the array, and then partitioning the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then recursively sorted.

## Requirements

Implement a `quickSort` function that takes an array of numbers as input and returns the sorted array in ascending order.

The `quickSort` function should have the following characteristics:

1. It should use the quick sort algorithm to sort the input array.
2. It should be implemented using JavaScript.
3. It should have a time complexity of O(n log n) in the average case.
4. It should be able to handle arrays of any size and with any range of values.

## JavaScript Code

Here's an implementation of the `quickSort` function in JavaScript:

```javascript
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const pivot = arr[Math.floor(arr.length / 2)];
  const left = [];
  const right = [];
  const middle = [];

  for (const item of arr) {
    if (item < pivot) {
      left.push(item);
    } else if (item > pivot) {
      right.push(item);
    } else {
      middle.push(item);
    }
  }

  return [...quickSort(left), ...middle, ...quickSort(right)];
}

// Example usage
const unsortedArray = [5, 2, 9, 1, 7, 3, 8, 4, 6];
const sortedArray = quickSort(unsortedArray);
console.log(sortedArray); // Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Here's how the `quickSort` function works:

1. If the input array has 0 or 1 elements, it is already sorted, so the function simply returns the array.
2. The function selects a pivot element, which is the middle element of the array.
3. The function then partitions the array into three sub-arrays: `left` (elements less than the pivot), `right` (elements greater than the pivot), and `middle` (elements equal to the pivot).
4. The function recursively sorts the `left` and `right` sub-arrays using the `quickSort` function.
5. Finally, the function concatenates the sorted `left`, `middle`, and `right` sub-arrays and returns the result.

The time complexity of the `quickSort` function is O(n log n) in the average case, as the algorithm divides the input array into smaller sub-arrays and recursively sorts them. However, in the worst case scenario, where the input array is already sorted or reverse-sorted, the time complexity can be O(n^2).