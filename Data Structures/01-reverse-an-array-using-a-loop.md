# Write a function to reverse an array

# Problem Description
Given an array of elements, the task is to write a function that reverses the order of the elements in the array using a loop.

# Requirement
Implement a function that takes an array as input and returns the reversed array.

# Code
Here's a JavaScript function that reverses an array using a loop:
```javascript
function reverseArray(arr) {
  // Create a new array to store the reversed elements
  let reversedArr = [];

  // Iterate through the input array in reverse order
  for (let i = arr.length - 1; i >= 0; i--) {
    // Add each element to the new array
    reversedArr.push(arr[i]);
  }

  // Return the reversed array
  return reversedArr;
}
```

# Here's how the function works:
* We create a new empty array called reversedArr to store the reversed elements.
* We use a for loop to iterate through the input array arr in reverse order, starting from the last index (arr.length - 1) and going down to the first index (0).
* For each iteration, we add the current element arr[i] to the reversedArr using the push() method.
* After the loop completes, we return the reversedArr containing the reversed elements.

You can use this function like this:
```javascript
const myArray = [1, 2, 3, 4, 5];
const reversedArray = reverseArray(myArray);
console.log(reversedArray); // Output: [5, 4, 3, 2, 1]
```

This solution has a time complexity of O(n), where n is the length of the input array, as we need to iterate through the entire array once to reverse it.