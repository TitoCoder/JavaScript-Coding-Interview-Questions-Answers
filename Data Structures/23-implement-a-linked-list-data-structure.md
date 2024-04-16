# Write a function to implement a linked list data structure

## Linked List Data Structure

### Problem Description
A linked list is a fundamental data structure in computer science that consists of a sequence of nodes, where each node contains a value and a reference (or link) to the next node in the sequence. Unlike arrays, which have a fixed size, linked lists can grow and shrink dynamically as elements are added or removed.

Implementing a linked list data structure in JavaScript can be a useful exercise to understand the concepts of dynamic memory allocation, pointer manipulation, and the advantages and disadvantages of linked lists compared to other data structures.

### Requirements
1. Implement a `Node` class that represents a single node in the linked list, with properties for the `value` stored in the node and a `next` reference to the next node.
2. Implement a `LinkedList` class that provides the following methods:
   - `append(value)`: Add a new node with the given value to the end of the list.
   - `prepend(value)`: Add a new node with the given value to the beginning of the list.
   - `insert(value, index)`: Insert a new node with the given value at the specified index in the list.
   - `remove(index)`: Remove the node at the specified index from the list.
   - `get(index)`: Retrieve the value of the node at the specified index.
   - `length()`: Return the number of nodes in the list.

### JavaScript Code Solution

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  append(value) {
    const newNode = new Node(value);

    if (!this.head) {
      this.head = newNode;
    } else {
      let currentNode = this.head;
      while (currentNode.next) {
        currentNode = currentNode.next;
      }
      currentNode.next = newNode;
    }

    this.size++;
  }

  prepend(value) {
    const newNode = new Node(value);
    newNode.next = this.head;
    this.head = newNode;
    this.size++;
  }

  insert(value, index) {
    if (index < 0 || index > this.size) {
      throw new Error('Invalid index');
    }

    if (index === 0) {
      this.prepend(value);
      return;
    }

    const newNode = new Node(value);
    let currentNode = this.head;
    let prevNode = null;

    for (let i = 0; i < index; i++) {
      prevNode = currentNode;
      currentNode = currentNode.next;
    }

    prevNode.next = newNode;
    newNode.next = currentNode;
    this.size++;
  }

  remove(index) {
    if (index < 0 || index >= this.size) {
      throw new Error('Invalid index');
    }

    let currentNode = this.head;
    let prevNode = null;

    if (index === 0) {
      this.head = currentNode.next;
    } else {
      for (let i = 0; i < index; i++) {
        prevNode = currentNode;
        currentNode = currentNode.next;
      }
      prevNode.next = currentNode.next;
    }

    this.size--;
    return currentNode.value;
  }

  get(index) {
    if (index < 0 || index >= this.size) {
      throw new Error('Invalid index');
    }

    let currentNode = this.head;
    for (let i = 0; i < index; i++) {
      currentNode = currentNode.next;
    }
    return currentNode.value;
  }

  length() {
    return this.size;
  }
}
```

This implementation provides a basic linked list data structure in JavaScript, with methods for appending, prepending, inserting, removing, and retrieving nodes. The `Node` class represents a single node in the list, and the `LinkedList` class manages the overall structure of the list.

You can use this implementation to practice working with linked lists and explore their properties and use cases in various programming scenarios.