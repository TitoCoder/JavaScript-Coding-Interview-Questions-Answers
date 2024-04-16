# Write a function to find the second largest number in an array

# Problem Description
Given an array of numbers, write a function that returns the second largest number in the array.

# Requirements
* The function should take an array of numbers as input.
* The function should return the second largest number in the array.
* If the array has less than two elements, the function should return null.
* The function should handle both positive and negative numbers.

# JavaScript Code Answer
Here's a JavaScript function that finds the second largest number in an array:
```javascript
function findSecondLargest(arr) {
  // Check if the array has less than two elements
  if (arr.length < 2) {
    return null;
  }

  // Initialize variables to keep track of the largest and second largest numbers
  let largest = -Infinity;
  let secondLargest = -Infinity;

  // Iterate through the array and update the largest and second largest numbers
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > largest) {
      secondLargest = largest;
      largest = arr[i];
    } else if (arr[i] > secondLargest && arr[i] !== largest) {
      secondLargest = arr[i];
    }
  }

  // Return the second largest number
  return secondLargest;
}
```

# Here's how the function works:
* First, we check if the array has less than two elements. If so, we return null because there is no second largest number.
* We initialize two variables, largest and secondLargest, to keep track of the largest and second largest numbers in the array. We set them both to -Infinity to ensure that any number in the array will be larger than these initial values.
* We then iterate through the array and update the largest and secondLargest variables as we go. If we find a number that is larger than the current largest value, we update secondLargest to the current largest value, and then update largest to the new number. If we find a number that is larger than the current secondLargest value, but not larger than the current largest value, we update secondLargest to the new number.
* Finally, we return the secondLargest value, which will be the second largest number in the array.

Here are some example usages of the findSecondLargest function:

```javascript
console.log(findSecondLargest([10, 20, 30, 40, 50])); // Output: 40
console.log(findSecondLargest([50, 40, 30, 20, 10])); // Output: 40
console.log(findSecondLargest([-10, -20, -30, -40, -50])); // Output: -20
console.log(findSecondLargest([100])); // Output: null
console.log(findSecondLargest([])); // Output: null
```