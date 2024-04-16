# Write a function to implement an insertion sort algorithm

## Problem Description

Insertion sort is a simple sorting algorithm that works by iterating through an array, removing one element at a time, and inserting it into the correct position in the sorted portion of the array. This process is repeated until the entire array is sorted.

The algorithm works as follows:

1. Iterate through the array, starting from the second element.
2. For each element, compare it to the elements in the sorted portion of the array (the elements to the left of the current element).
3. Insert the current element into the correct position in the sorted portion of the array.
4. Repeat steps 2 and 3 until the entire array is sorted.

## Requirements

Write a function that takes an array of numbers as input and returns the sorted array using the insertion sort algorithm.

## JavaScript Code

Here's an implementation of the insertion sort algorithm in JavaScript:

```javascript
function insertionSort(arr) {
  for (let i = 1; i < arr.length; i++) {
    let currentElement = arr[i];
    let j = i - 1;

    while (j >= 0 && arr[j] > currentElement) {
      arr[j + 1] = arr[j];
      j--;
    }

    arr[j + 1] = currentElement;
  }

  return arr;
}
```

Here's how the `insertionSort()` function works:

1. The function takes an array `arr` as input.
2. It starts a `for` loop that iterates through the array, starting from the second element (index 1).
3. For each element, it stores the current element in the `currentElement` variable.
4. It then starts a `while` loop that compares the current element to the elements in the sorted portion of the array (the elements to the left of the current element).
5. If the current element is smaller than the element in the sorted portion, it shifts the element in the sorted portion to the right to make room for the current element.
6. Once the correct position for the current element is found, it inserts the current element into that position.
7. The function repeats steps 3-6 until the entire array is sorted.
8. Finally, the function returns the sorted array.

You can use this function like this:

```javascript
const unsortedArray = [5, 2, 8, 1, 9];
const sortedArray = insertionSort(unsortedArray);
console.log(sortedArray); // Output: [1, 2, 5, 8, 9]
```