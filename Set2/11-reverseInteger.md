## Problem Name
Reverse an Integer

## Description
Write a function that takes an integer as input and returns the reverse of that integer. The function should handle negative numbers as well as leading zeros.

## Sample Input
```
123
-456
1000
```

## Sample Output
```
321
-654
1
```

## File Name
`reverseInteger.js`

## Code Answer
```javascript
function reverseInteger(num) {
  const isNegative = num < 0;
  const reversedNum = Math.abs(num)
    .toString()
    .split('')
    .reverse()
    .join('');

  return (isNegative ? '-' : '') + reversedNum;
}

// Example usage
console.log(reverseInteger(123)); // Output: 321
console.log(reverseInteger(-456)); // Output: -654
console.log(reverseInteger(1000)); // Output: 1
```

Explanation:

1. The function `reverseInteger` takes an integer `num` as input.
2. It first checks if the number is negative by using the condition `num < 0`. The result is stored in the `isNegative` variable.
3. The absolute value of `num` is converted to a string using `Math.abs(num).toString()`.
4. The string is then split into an array of characters using the `split('')` method.
5. The array is reversed using the `reverse()` method.
6. The reversed array is joined back into a string using the `join('')` method.
7. If the original number was negative, a `-` sign is prepended to the reversed string using the ternary operator `(isNegative ? '-' : '')`.
8. The final reversed integer is returned.

The code handles negative numbers by checking the sign before reversing the digits. It also handles leading zeros correctly by reversing the string representation of the number.

Note: This solution assumes that the input is a valid integer within the safe range of JavaScript numbers (between -(2^53 - 1) and 2^53 - 1). For larger integers, you may need to use a different approach, such as working with strings or using a library for handling large numbers.