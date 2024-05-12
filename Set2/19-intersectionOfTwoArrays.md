## Problem Name
Intersection of Two Arrays

## Description
Write a function that takes two arrays as input and returns a new array containing the elements that are common to both input arrays.

## Sample Input
```javascript
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [4, 5, 6, 7, 8];
```

## Sample Output
```
[4, 5]
```

## File Name
`intersectionOfTwoArrays.js`

## Code Answer
```javascript
function intersectionOfTwoArrays(arr1, arr2) {
  const result = [];

  for (let i = 0; i < arr1.length; i++) {
    if (arr2.includes(arr1[i]) && !result.includes(arr1[i])) {
      result.push(arr1[i]);
    }
  }

  return result;
}

// Example usage
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [4, 5, 6, 7, 8];
const intersection = intersectionOfTwoArrays(arr1, arr2);
console.log(intersection); // Output: [4, 5]
```

This function takes two arrays as input (`arr1` and `arr2`). It initializes an empty array called `result` to store the common elements.

The function then iterates over the first array (`arr1`) using a `for` loop. For each element in `arr1`, it checks if the element is present in `arr2` using the `includes` method. If the element is present in `arr2` and not already in the `result` array, it is added to the `result` array using the `push` method.

Finally, the function returns the `result` array containing the common elements from both input arrays.

In the example usage, the function is called with `arr1 = ` and `arr2 = `. The expected output is ``, which represents the elements that are common to both input arrays.