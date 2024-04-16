# Write a function to implement a stack data structure

## Problem Description

A stack is a fundamental data structure in computer science that follows the Last-In-First-Out (LIFO) principle. It allows you to store and retrieve elements in a specific order, where the last element added is the first one to be removed.

## Requirement

Implement a stack data structure in JavaScript with the following operations:

1. `push(element)`: Adds an element to the top of the stack.
2. `pop()`: Removes and returns the top element from the stack.
3. `peek()`: Returns the top element of the stack without removing it.
4. `isEmpty()`: Returns `true` if the stack is empty, and `false` otherwise.
5. `size()`: Returns the number of elements in the stack.

## JavaScript Code Answer

Here's an implementation of a stack data structure in JavaScript:

```javascript
class Stack {
  constructor() {
    this.items = [];
  }

  // Push an element to the top of the stack
  push(element) {
    this.items.push(element);
  }

  // Remove and return the top element from the stack
  pop() {
    if (this.items.length === 0) {
      return "Underflow";
    }
    return this.items.pop();
  }

  // Return the top element from the stack without removing it
  peek() {
    return this.items[this.items.length - 1];
  }

  // Check if the stack is empty
  isEmpty() {
    return this.items.length === 0;
  }

  // Return the size of the stack
  size() {
    return this.items.length;
  }
}

// Example usage
const stack = new Stack();
stack.push(10);
stack.push(20);
console.log(stack.pop()); // Output: 20
console.log(stack.size()); // Output: 1
console.log(stack.isEmpty()); // Output: false
console.log(stack.peek()); // Output: 10
```

In this implementation, we use an array `items` to store the elements of the stack. The `push()` method adds an element to the top of the stack, the `pop()` method removes and returns the top element, the `peek()` method returns the top element without removing it, the `isEmpty()` method checks if the stack is empty, and the `size()` method returns the number of elements in the stack.

The example usage at the end demonstrates how to use the stack data structure in JavaScript.