## 17. Valid Parentheses

**Description:**
Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

**Sample Input:**
```
s = "()"     // Valid
s = "()[]{}" // Valid
s = "(]"     // Invalid
s = "([)]"   // Invalid
s = "{[]}"   // Valid
```

**Sample Output:**
```
true
true
false
false
true
```

**File Name:** `validParentheses.js`

**Code Answer:**

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
function isValid(s) {
  const stack = [];
  const openingBrackets = ['(', '{', '['];
  const closingBrackets = [')', '}', ']'];
  const bracketMap = { '(': ')', '{': '}', '[': ']' };

  for (let i = 0; i < s.length; i++) {
    const char = s[i];

    if (openingBrackets.includes(char)) {
      stack.push(char);
    } else if (closingBrackets.includes(char)) {
      const lastOpeningBracket = stack.pop();
      if (bracketMap[lastOpeningBracket] !== char) {
        return false;
      }
    }
  }

  return stack.length === 0;
}
```

**Explanation:**

1. We create an empty stack to keep track of the opening brackets.
2. We define two arrays, `openingBrackets` and `closingBrackets`, to store the opening and closing bracket characters, respectively.
3. We also create a `bracketMap` object to map each opening bracket to its corresponding closing bracket.
4. We iterate through the input string `s`.
5. If the current character is an opening bracket, we push it onto the stack.
6. If the current character is a closing bracket, we pop the last opening bracket from the stack. If the popped opening bracket does not match the current closing bracket according to the `bracketMap`, we return `false` because the brackets are not valid.
7. After iterating through the entire string, if the stack is empty, it means all opening brackets have been properly closed, so we return `true`. Otherwise, we return `false`.

The time complexity of this solution is O(n), where n is the length of the input string `s`, because we iterate through the string once. The space complexity is O(n) in the worst case, where all characters in the string are opening brackets, and we need to store them all in the stack.