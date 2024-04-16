# Write a function to count the occurrences of each element in an array

## Problem Description

Given an array of elements, write a function that counts the occurrences of each element in the array and returns an object with the element as the key and the count as the value.

## Requirements

1. The function should take an array as input.
2. The function should return an object where the keys are the unique elements in the array, and the values are the number of occurrences of each element.
3. The function should handle arrays with different data types (e.g., numbers, strings, booleans).

## JavaScript Code Answer

```javascript
function countOccurrences(arr) {
  const occurrences = {};

  for (const item of arr) {
    if (occurrences[item]) {
      occurrences[item]++;
    } else {
      occurrences[item] = 1;
    }
  }

  return occurrences;
}
```

Here's how the `countOccurrences()` function works:

1. We initialize an empty object `occurrences` to store the count of each element.
2. We loop through the input array `arr` using a `for...of` loop.
3. For each element `item` in the array, we check if it already exists as a key in the `occurrences` object.
   - If it does, we increment the value by 1.
   - If it doesn't, we add the element as a new key and set its value to 1.
4. Finally, we return the `occurrences` object, which contains the count of each element in the input array.

You can call the `countOccurrences()` function like this:

```javascript
const myArray = [1, 2, 3, 2, 1, 3, 4, 5, 4, 4];
const result = countOccurrences(myArray);
console.log(result); // Output: { '1': 2, '2': 2, '3': 2, '4': 3, '5': 1 }
```

In this example, the function returns an object where the keys are the unique elements in the array (`1`, `2`, `3`, `4`, `5`), and the values are the number of occurrences of each element.