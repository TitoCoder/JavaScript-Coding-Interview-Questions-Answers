# Write a function to flatten a nested array

## Problem Description

Given a nested array, write a function that flattens the array into a single-level array.

For example, if the input is `[1, , [4, ]]`, the output should be `[1,4]`.

## Requirements

1. The function should be able to handle nested arrays of any depth.
2. The function should return a new flattened array, without modifying the original array.
3. The function should work efficiently for large input arrays.

## JavaScript Code Answer

Here's a JavaScript function that flattens a nested array:

```javascript
function flattenArray(arr) {
  return arr.reduce((result, item) => {
    if (Array.isArray(item)) {
      return result.concat(flattenArray(item));
    } else {
      return result.concat(item);
    }
  }, []);
}
```

Here's how the function works:

1. The `flattenArray` function takes a nested array `arr` as input.
2. It uses the `reduce` method to iterate over each element in the array.
3. For each element, it checks if the element is an array using `Array.isArray(item)`.
4. If the element is an array, it recursively calls `flattenArray` on that element and concatenates the result to the `result` array.
5. If the element is not an array, it simply concatenates the element to the `result` array.
6. The initial value of the `result` array is an empty array `[]`.
7. The final result is the flattened array.

Here's an example usage:

```javascript
const nestedArray = [1, [2, 3], [4, [5, 6]]];
const flattenedArray = flattenArray(nestedArray);
console.log(flattenedArray); // Output: [1, 2, 3, 4, 5, 6]
```

This solution has a time complexity of O(n), where n is the total number of elements in the nested array, as it needs to visit each element once. It also has a space complexity of O(n), as it creates a new flattened array.