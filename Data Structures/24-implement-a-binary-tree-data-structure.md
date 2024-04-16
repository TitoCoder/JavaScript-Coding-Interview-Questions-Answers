# Write a function to implement a binary tree data structure

## Problem Description

A binary tree is a fundamental data structure in computer science, where each node has at most two child nodes, typically referred to as the left and right child. Binary trees are widely used in various algorithms and applications, such as search, sorting, and traversal.

The task is to implement a basic binary tree data structure in JavaScript, including the following operations:

1. **Create a new binary tree node**: This function should create a new node with a given value and initialize its left and right child pointers to `null`.
2. **Insert a new node**: This function should insert a new node with a given value into the binary tree, following the binary search tree (BST) property, where all values in the left subtree are less than the current node's value, and all values in the right subtree are greater than the current node's value.
3. **Traverse the binary tree**: Implement three common tree traversal algorithms: in-order, pre-order, and post-order traversal, which visit the nodes in different orders.

## Requirements

1. Implement a `BinaryTreeNode` class that represents a single node in the binary tree, with the following properties:
   - `value`: the value stored in the node
   - `left`: a reference to the left child node (or `null` if no left child)
   - `right`: a reference to the right child node (or `null` if no right child)
2. Implement a `BinaryTree` class that manages the overall binary tree, with the following methods:
   - `createNode(value)`: creates a new `BinaryTreeNode` with the given value
   - `insert(value)`: inserts a new node with the given value into the binary tree
   - `inOrderTraversal()`: performs an in-order traversal of the binary tree and returns an array of the visited node values
   - `preOrderTraversal()`: performs a pre-order traversal of the binary tree and returns an array of the visited node values
   - `postOrderTraversal()`: performs a post-order traversal of the binary tree and returns an array of the visited node values

## JavaScript Code

```javascript
class BinaryTreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinaryTree {
  constructor() {
    this.root = null;
  }

  createNode(value) {
    return new BinaryTreeNode(value);
  }

  insert(value) {
    const newNode = this.createNode(value);

    if (!this.root) {
      this.root = newNode;
      return;
    }

    let currentNode = this.root;
    while (true) {
      if (value < currentNode.value) {
        if (!currentNode.left) {
          currentNode.left = newNode;
          return;
        }
        currentNode = currentNode.left;
      } else {
        if (!currentNode.right) {
          currentNode.right = newNode;
          return;
        }
        currentNode = currentNode.right;
      }
    }
  }

  inOrderTraversal() {
    const result = [];
    this.inOrderTraversalHelper(this.root, result);
    return result;
  }

  inOrderTraversalHelper(node, result) {
    if (!node) return;
    this.inOrderTraversalHelper(node.left, result);
    result.push(node.value);
    this.inOrderTraversalHelper(node.right, result);
  }

  preOrderTraversal() {
    const result = [];
    this.preOrderTraversalHelper(this.root, result);
    return result;
  }

  preOrderTraversalHelper(node, result) {
    if (!node) return;
    result.push(node.value);
    this.preOrderTraversalHelper(node.left, result);
    this.preOrderTraversalHelper(node.right, result);
  }

  postOrderTraversal() {
    const result = [];
    this.postOrderTraversalHelper(this.root, result);
    return result;
  }

  postOrderTraversalHelper(node, result) {
    if (!node) return;
    this.postOrderTraversalHelper(node.left, result);
    this.postOrderTraversalHelper(node.right, result);
    result.push(node.value);
  }
}

// Example usage
const tree = new BinaryTree();
tree.insert(10);
tree.insert(5);
tree.insert(15);
tree.insert(3);
tree.insert(7);
tree.insert(12);
tree.insert(20);

console.log('In-order Traversal:', tree.inOrderTraversal()); // [3, 5, 7, 10, 12, 15, 20]
console.log('Pre-order Traversal:', tree.preOrderTraversal()); // [10, 5, 3, 7, 15, 12, 20]
console.log('Post-order Traversal:', tree.postOrderTraversal()); // [3, 7, 5, 12, 20, 15, 10]
```

This implementation provides a basic binary tree data structure with the ability to insert new nodes and perform in-order, pre-order, and post-order traversals. The `BinaryTreeNode` class represents a single node in the tree, and the `BinaryTree` class manages the overall tree structure and operations.

The `insert` method follows the binary search tree (BST) property, where all values in the left subtree are less than the current node's value, and all values in the right subtree are greater than the current node's value. The traversal methods (`inOrderTraversal`, `preOrderTraversal`, and `postOrderTraversal`) recursively visit the nodes in the respective orders and return the visited node values as an array.

You can use this implementation as a starting point for more advanced binary tree operations, such as deletion, search, and balancing.