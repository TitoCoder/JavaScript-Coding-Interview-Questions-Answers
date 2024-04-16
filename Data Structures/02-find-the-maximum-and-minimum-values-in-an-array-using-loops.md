# Write a function to find the maximum and minimum values in an array using loops

# Problem Description
Given an array of numbers, write a function that finds the maximum and minimum values in the array using loops.

# Requirements
* The function should take an array of numbers as input.
* The function should return an object with two properties: max and min, representing the maximum and minimum values in the array, respectively.
* The function should use loops to iterate through the array and find the maximum and minimum values.

# Code
Here's a JavaScript function that meets the requirements:
```javascript
function findMaxMin(arr) {
  let max = arr[0];
  let min = arr[0];

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] > max) {
      max = arr[i];
    }
    if (arr[i] < min) {
      min = arr[i];
    }
  }

  return {
    max: max,
    min: min
  };
}
```

# Here's how the function works:
* We initialize max and min variables with the first element of the input array.
* We then loop through the rest of the array, starting from the second element.
* For each element, we check if it's greater than the current max value. If it is, we update max to the current element.
* Similarly, we check if the current element is less than the current min value. If it is, we update min to the current element.
* After the loop, we return an object with the max and min properties.

You can call the function like this:

```javascript
const numbers = [10, 5, 8, 12, 3];
const result = findMaxMin(numbers);
console.log(result); // { max: 12, min: 3 }
```
This function has a time complexity of O(n), as it iterates through the array once to find the maximum and minimum values.