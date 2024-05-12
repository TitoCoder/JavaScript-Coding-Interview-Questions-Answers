## 3. FizzBuzz

**Description:**
Write a function that prints the numbers from 1 to 100. But for multiples of 3, print "Fizz" instead of the number, and for multiples of 5, print "Buzz". For numbers that are multiples of both 3 and 5, print "FizzBuzz".

**Sample Input:**
```
fizzBuzz(15);
```

**Sample Output:**
```
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
```

**File Name:** `fizzBuzz.js`

**Code Answer:**

```javascript
function fizzBuzz(n) {
  for (let i = 1; i <= n; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      console.log("FizzBuzz");
    } else if (i % 3 === 0) {
      console.log("Fizz");
    } else if (i % 5 === 0) {
      console.log("Buzz");
    } else {
      console.log(i);
    }
  }
}
```

To use this function, simply call `fizzBuzz(100)` to print the numbers from 1 to 100, with the appropriate "Fizz", "Buzz", or "FizzBuzz" replacements.

The function uses a `for` loop to iterate from 1 to `n` (in this case, 100). For each number `i`, it checks if `i` is divisible by both 3 and 5 (using the modulus operator `%`). If it is, it prints "FizzBuzz". If `i` is only divisible by 3, it prints "Fizz". If `i` is only divisible by 5, it prints "Buzz". If `i` is not divisible by either 3 or 5, it prints the number `i`.

This problem is a classic coding interview question that tests your understanding of control flow and modular arithmetic.