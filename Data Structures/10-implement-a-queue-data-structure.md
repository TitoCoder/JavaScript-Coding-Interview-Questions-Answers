# Write a function to implement a queue data structure

## Problem Description

A queue is a fundamental data structure that follows the First-In-First-Out (FIFO) principle. It is a linear data structure where elements are added at the rear (enqueue) and removed from the front (dequeue). Implementing a queue data structure from scratch can be a useful exercise to understand its underlying mechanics and practice basic programming concepts.

## Requirements

1. Implement a `Queue` class that has the following methods:
   - `enqueue(element)`: Adds an element to the end of the queue.
   - `dequeue()`: Removes and returns the element at the front of the queue.
   - `peek()`: Returns the element at the front of the queue without removing it.
   - `isEmpty()`: Returns `true` if the queue is empty, `false` otherwise.
   - `size()`: Returns the number of elements in the queue.

2. The queue should be able to store any type of data (e.g., numbers, strings, objects).

3. The queue should handle edge cases, such as trying to dequeue from an empty queue.

## JavaScript Code Solution

```javascript
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(element) {
    this.items.push(element);
  }

  dequeue() {
    if (this.isEmpty()) {
      return "Underflow";
    }
    return this.items.shift();
  }

  peek() {
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  size() {
    return this.items.length;
  }
}

// Example usage:
const queue = new Queue();
queue.enqueue(10);
queue.enqueue(20);
queue.enqueue(30);
console.log(queue.dequeue()); // Output: 10
console.log(queue.peek()); // Output: 20
console.log(queue.size()); // Output: 2
console.log(queue.isEmpty()); // Output: false
```

In this implementation, the `Queue` class uses an array `items` to store the elements. The `enqueue` method adds an element to the end of the array, and the `dequeue` method removes and returns the first element. The `peek` method returns the first element without removing it, and the `isEmpty` and `size` methods provide information about the queue's state.

The example usage at the end demonstrates how to create a new queue, add elements, remove elements, and check the queue's properties.