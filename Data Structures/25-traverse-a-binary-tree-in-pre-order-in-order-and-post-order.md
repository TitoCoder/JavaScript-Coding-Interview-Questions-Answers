# Write a function to traverse a binary tree in pre-order, in-order, and post-order

## Problem Description

Binary trees are a fundamental data structure in computer science, and traversing them is a common task. There are three main ways to traverse a binary tree: pre-order, in-order, and post-order. Each traversal method visits the nodes of the tree in a different order, which can be useful for different applications.

## Requirements

Write a JavaScript function that can perform pre-order, in-order, and post-order traversals of a binary tree. The function should take a binary tree as input and return the traversal results as arrays.

## JavaScript Code Answer

Here's a JavaScript implementation of a function that performs pre-order, in-order, and post-order traversals of a binary tree:

```javascript
class TreeNode {
  constructor(val) {
    this.val = val;
    this.left = null;
    this.right = null;
  }
}

function traverseBinaryTree(root) {
  const preOrder = [];
  const inOrder = [];
  const postOrder = [];

  function dfs(node) {
    if (!node) return;

    // Pre-order traversal
    preOrder.push(node.val);

    // In-order traversal
    dfs(node.left);
    inOrder.push(node.val);
    dfs(node.right);

    // Post-order traversal
    postOrder.push(node.val);
  }

  dfs(root);
  return { preOrder, inOrder, postOrder };
}

// Example usage
const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

const result = traverseBinaryTree(root);
console.log('Pre-order:', result.preOrder); // Output: [1, 2, 4, 5, 3]
console.log('In-order:', result.inOrder); // Output: [4, 2, 5, 1, 3]
console.log('Post-order:', result.postOrder); // Output: [4, 5, 2, 3, 1]
```

In this implementation, we define a `TreeNode` class to represent the nodes of the binary tree. The `traverseBinaryTree` function takes the root of the binary tree as input and returns an object with the pre-order, in-order, and post-order traversal results as arrays.

The `dfs` (depth-first search) function is a helper function that performs the actual traversal. It recursively visits the left subtree, then the current node, and finally the right subtree, which corresponds to the pre-order, in-order, and post-order traversals, respectively.

The `traverseBinaryTree` function calls the `dfs` function with the root node and returns the resulting traversal arrays.

You can use this function to traverse any binary tree and obtain the pre-order, in-order, and post-order traversal results.