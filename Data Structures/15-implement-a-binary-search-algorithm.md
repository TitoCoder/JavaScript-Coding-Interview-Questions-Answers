## Problem Description

Binary search is a fundamental algorithm used to efficiently search for a target value within a sorted array. The algorithm works by repeatedly dividing the search interval in half until the target value is found or the search interval becomes empty.

## Requirements

Implement a `binarySearch` function that takes the following parameters:

1. `arr`: a sorted array of numbers
2. `target`: the value to search for in the array

The function should return the index of the `target` value if it is found in the array, or `-1` if the `target` value is not present in the array.

## JavaScript Code

Here's an implementation of the `binarySearch` function in JavaScript:

```javascript
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);

    if (arr[mid] === target) {
      return mid;
    } else if (arr[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return -1;
}
```

Here's how the `binarySearch` function works:

1. The function takes two parameters: `arr` (a sorted array of numbers) and `target` (the value to search for in the array).
2. It initializes two variables, `left` and `right`, to represent the left and right boundaries of the search interval. Initially, `left` is set to `0` and `right` is set to the last index of the array (`arr.length - 1`).
3. The function then enters a `while` loop that continues as long as `left` is less than or equal to `right`. This means the loop will continue until the search interval becomes empty.
4. Inside the loop, the function calculates the middle index `mid` by taking the average of `left` and `right` and rounding down to the nearest integer.
5. The function then checks if the value at the middle index `arr[mid]` is equal to the `target` value. If so, it returns the middle index `mid`.
6. If the value at the middle index is less than the `target` value, the function updates `left` to `mid + 1`, effectively discarding the left half of the search interval.
7. If the value at the middle index is greater than the `target` value, the function updates `right` to `mid - 1`, effectively discarding the right half of the search interval.
8. The loop continues until the `target` value is found or the search interval becomes empty.
9. If the `target` value is not found in the array, the function returns `-1`.

This implementation of the binary search algorithm has a time complexity of O(log n), where n is the size of the input array. This makes it an efficient way to search for a value in a sorted array.