## Problem Name
Remove Duplicates

## Description
Write a function that takes an array as input and returns a new array with all duplicate elements removed.

## Sample Input
```javascript
const arr = [1, 2, 3, 2, 4, 5, 1, 6];
```

## Sample Output
```javascript
[1, 2, 3, 4, 5, 6]
```

## File Name
`removeDuplicates.js`

## Code Answer
```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}

// Example usage
const arr = [1, 2, 3, 2, 4, 5, 1, 6];
const uniqueArr = removeDuplicates(arr);
console.log(uniqueArr); // Output: [1, 2, 3, 4, 5, 6]
```

Explanation:
1. The `removeDuplicates` function takes an array `arr` as input.
2. Inside the function, we create a new `Set` object from the input array using the spread operator `...`. The `Set` object automatically removes duplicate values.
3. We then spread the `Set` object back into a new array using the spread operator `...` again.
4. The resulting array contains only unique elements from the original array.
5. In the example usage, we create an array `arr` with duplicate elements.
6. We call the `removeDuplicates` function with `arr` as the argument and store the result in `uniqueArr`.
7. Finally, we log `uniqueArr` to the console, which outputs the array with duplicate elements removed.

This solution uses the `Set` object in JavaScript, which is a built-in data structure that stores unique values. By creating a `Set` from the input array and then converting it back to an array, we effectively remove all duplicate elements.