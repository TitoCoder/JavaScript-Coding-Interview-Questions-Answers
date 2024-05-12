## 9. Sum of Digits

**Description:**
Write a function that takes a positive integer as input and returns the sum of its digits.

**Sample Input:**
```
123
```

**Sample Output:**
```
6
```

**File Name:** `sumOfDigits.js`

**Code Answer:**

```javascript
function sumOfDigits(num) {
  // Convert the number to a string
  const numStr = num.toString();

  // Initialize the sum to 0
  let sum = 0;

  // Iterate over each character in the string
  for (let i = 0; i < numStr.length; i++) {
    // Convert the character to a number and add it to the sum
    sum += parseInt(numStr[i]);
  }

  // Return the sum
  return sum;
}

// Example usage
console.log(sumOfDigits(123)); // Output: 6
console.log(sumOfDigits(456)); // Output: 15
```

**Explanation:**

1. The function `sumOfDigits` takes a positive integer `num` as input.
2. We convert the number to a string using the `toString()` method.
3. We initialize a variable `sum` to 0, which will store the sum of the digits.
4. We iterate over each character in the string using a `for` loop.
5. For each character, we convert it to a number using `parseInt` and add it to the `sum` variable.
6. After iterating over all characters, we return the `sum`.
7. In the example usage, we call the `sumOfDigits` function with different inputs and log the results to the console.

This solution has a time complexity of O(n), where n is the number of digits in the input number, since we need to iterate over each digit once. The space complexity is O(1), as we only use a constant amount of extra space to store the sum and the string representation of the number.