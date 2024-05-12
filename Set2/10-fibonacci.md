## 10. Fibonacci Sequence

**Description:**
Write a function that takes a number `n` as input and returns the `n`th number in the Fibonacci sequence. The Fibonacci sequence is a series of numbers in which each number is the sum of the two preceding ones, usually starting with 0 and 1. The first few numbers in the Fibonacci sequence are 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, and so on.

**Sample Input:**
```
n = 7
```

**Sample Output:**
```
13
```

**File Name:** `fibonacci.js`

**Code Answer:**

```javascript
function fibonacci(n) {
  if (n <= 0) {
    return 0;
  } else if (n === 1) {
    return 1;
  } else {
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}

// Example usage:
console.log(fibonacci(7)); // Output: 13
```

**Explanation:**
The `fibonacci` function takes a number `n` as input and returns the `n`th number in the Fibonacci sequence. It uses recursion to calculate the `n`th Fibonacci number by calling itself with `n - 1` and `n - 2` until it reaches the base cases of `n <= 0` (which returns 0) and `n === 1` (which returns 1).

The recursive calls build up the Fibonacci sequence by adding the previous two numbers until it reaches the desired `n`th number. For example, when `n = 7`, the function calls itself as follows:

```
fibonacci(7)
= fibonacci(6) + fibonacci(5)
= (fibonacci(5) + fibonacci(4)) + (fibonacci(4) + fibonacci(3))
= (fibonacci(4) + fibonacci(3)) + (fibonacci(3) + fibonacci(2)) + (fibonacci(2) + fibonacci(1))
= (fibonacci(3) + fibonacci(2)) + (fibonacci(2) + fibonacci(1)) + (fibonacci(1) + fibonacci(0)) + 1
= (fibonacci(2) + fibonacci(1)) + (fibonacci(1) + fibonacci(0)) + 1 + 1 + 0
= (fibonacci(1) + fibonacci(0)) + 1 + 1 + 1 + 0
= 1 + 1 + 1 + 1 + 0
= 13
```

Note that this recursive implementation can be inefficient for large values of `n` due to redundant calculations. A more efficient approach would be to use dynamic programming or an iterative solution.