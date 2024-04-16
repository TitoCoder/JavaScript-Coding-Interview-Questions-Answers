# Write a function to remove duplicates from an array

# Problem Description
Given an array of elements, the task is to write a function that removes all the duplicate elements from the array and returns a new array with only unique elements.

# Requirements
* The function should take an array as input and return a new array.
* The function should remove all the duplicate elements from the input array.
* The order of the unique elements in the output array should be the same as in the input array.
* The function should be efficient in terms of time and space complexity.

# Code Answer
Here's a JavaScript function that removes duplicates from an array:
```javascript
function removeDuplicates(arr) {
  // Create a new Set to store unique elements
  const uniqueSet = new Set(arr);

  // Convert the Set back to an array and return it
  return Array.from(uniqueSet);
}
```

# Explanation:
* We create a new Set object and pass the input array arr to it. The Set object will automatically remove any duplicate elements, as it only stores unique values.
* We then use the Array.from() method to convert the Set back to an array and return it.
* This solution has a time complexity of O(n), where n is the length of the input array, as we iterate through the array once to create the Set. The space complexity is also O(n), as we use a Set to store the unique elements.

# Here's an example usage:
```javascript
const myArray = [1, 2, 3, 2, 4, 1, 5];
const uniqueArray = removeDuplicates(myArray);
console.log(uniqueArray); // Output: [1, 2, 3, 4, 5]
```