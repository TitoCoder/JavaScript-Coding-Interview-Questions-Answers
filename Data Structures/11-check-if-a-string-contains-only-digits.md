# Write a function to check if a string contains only digits

## Problem Description

The task is to write a function that checks if a given string contains only digits (0-9). This is a common problem in programming, as it is often necessary to validate user input or perform data manipulation tasks that require checking the format of a string.

## Requirement

Implement a JavaScript function that takes a string as input and returns a boolean value indicating whether the string contains only digits or not.

## JavaScript Code Answer

Here's a JavaScript function that checks if a string contains only digits:

```javascript
function containsOnlyDigits(str) {
  // Use a regular expression to check if the string contains only digits
  return /^\d+$/.test(str);
}
```

Explanation:

1. The function `containsOnlyDigits` takes a string `str` as input.
2. The regular expression `/^\d+$/` is used to check if the entire string `str` contains only digits (0-9). The `^` and `$` anchors ensure that the entire string matches the pattern.
3. The `test()` method is used to test the string against the regular expression. It returns `true` if the string matches the pattern, and `false` otherwise.

You can use this function like this:

```javascript
console.log(containsOnlyDigits("123")); // true
console.log(containsOnlyDigits("abc")); // false
console.log(containsOnlyDigits("123abc")); // false
console.log(containsOnlyDigits("123.45")); // false
```

In the examples above, the function correctly identifies that "123" contains only digits, while "abc", "123abc", and "123.45" do not.