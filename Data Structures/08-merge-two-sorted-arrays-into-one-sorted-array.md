# Write a function to merge two sorted arrays into one sorted array
## Problem Description

Given two sorted arrays, write a function that merges the two arrays into a single sorted array.

## Requirements

1. The function should take two sorted arrays as input parameters.
2. The function should return a single sorted array that contains all the elements from the two input arrays.
3. The function should maintain the sorted order of the input arrays in the output array.
4. The function should have a time complexity of O(n), where n is the total number of elements in the two input arrays.

## JavaScript Code Answer

Here's a JavaScript function that merges two sorted arrays into a single sorted array:

```javascript
function mergeSortedArrays(arr1, arr2) {
  let result = [];
  let i = 0, j = 0;

  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      result.push(arr1[i]);
      i++;
    } else {
      result.push(arr2[j]);
      j++;
    }
  }

  // Add any remaining elements from the first array
  while (i < arr1.length) {
    result.push(arr1[i]);
    i++;
  }

  // Add any remaining elements from the second array
  while (j < arr2.length) {
    result.push(arr2[j]);
    j++;
  }

  return result;
}
```

Here's how the function works:

1. We initialize an empty array `result` to store the merged sorted array.
2. We use two pointers `i` and `j` to keep track of the current position in the first and second arrays, respectively.
3. We compare the elements at the current positions in the two arrays. If the element in the first array is smaller, we add it to the `result` array and increment `i`. Otherwise, we add the element from the second array to the `result` array and increment `j`.
4. After the loop, we check if there are any remaining elements in either of the input arrays and add them to the `result` array.
5. Finally, we return the `result` array, which contains the merged sorted array.

The time complexity of this function is O(n), where n is the total number of elements in the two input arrays, because we only need to iterate through the arrays once.