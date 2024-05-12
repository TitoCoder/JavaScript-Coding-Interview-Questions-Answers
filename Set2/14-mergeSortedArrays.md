## Problem Name
Merge Sorted Arrays

## Description
Write a function that takes two sorted arrays as input and returns a new sorted array that contains all elements from both input arrays.

## Sample Input
```javascript
const arr1 = [1, 3, 5, 7];
const arr2 = [2, 4, 6, 8];
```

## Sample Output
```javascript
[1, 2, 3, 4, 5, 6, 7, 8]
```

## File Name
`mergeSortedArrays.js`

## Code Answer
```javascript
function mergeSortedArrays(arr1, arr2) {
  const mergedArray = [];
  let i = 0, j = 0;

  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      mergedArray.push(arr1[i]);
      i++;
    } else {
      mergedArray.push(arr2[j]);
      j++;
    }
  }

  // Append any remaining elements from arr1
  while (i < arr1.length) {
    mergedArray.push(arr1[i]);
    i++;
  }

  // Append any remaining elements from arr2
  while (j < arr2.length) {
    mergedArray.push(arr2[j]);
    j++;
  }

  return mergedArray;
}

// Example usage
const arr1 = [1, 3, 5, 7];
const arr2 = [2, 4, 6, 8];
const mergedArray = mergeSortedArrays(arr1, arr2);
console.log(mergedArray); // Output: [1, 2, 3, 4, 5, 6, 7, 8]
```

This function takes two sorted arrays `arr1` and `arr2` as input. It initializes an empty array `mergedArray` to store the merged elements. Then, it uses two pointers `i` and `j` to iterate over `arr1` and `arr2`, respectively.

At each iteration, the function compares the elements at the current indices `i` and `j` of `arr1` and `arr2`. The smaller element is added to `mergedArray`, and the corresponding pointer is incremented.

After the main loop, if there are any remaining elements in `arr1` or `arr2`, they are appended to `mergedArray`.

Finally, the function returns the `mergedArray` containing all elements from both input arrays in sorted order.