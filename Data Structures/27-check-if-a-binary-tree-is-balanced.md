# Write a function to check if a binary tree is balanced

## Problem Description

A binary tree is considered balanced if the height of the left and right subtrees of any node never differ by more than 1. In other words, for each node in the tree, the absolute difference between the heights of its left and right subtrees must be no greater than 1.

The task is to write a function that takes a binary tree as input and returns `true` if the tree is balanced, and `false` otherwise.

## Requirement

Implement a function `isBalanced(root)` that takes the root node of a binary tree as input and returns a boolean value indicating whether the tree is balanced or not.

## JavaScript Code Answer

Here's a JavaScript implementation of the `isBalanced` function:

```javascript
class TreeNode {
  constructor(val) {
    this.val = val;
    this.left = null;
    this.right = null;
  }
}

function isBalanced(root) {
  return getHeight(root) !== -1;
}

function getHeight(node) {
  if (!node) {
    return 0;
  }

  const leftHeight = getHeight(node.left);
  if (leftHeight === -1) {
    return -1;
  }

  const rightHeight = getHeight(node.right);
  if (rightHeight === -1) {
    return -1;
  }

  if (Math.abs(leftHeight - rightHeight) > 1) {
    return -1;
  }

  return Math.max(leftHeight, rightHeight) + 1;
}
```

The `isBalanced` function calls the `getHeight` helper function, which recursively calculates the height of the left and right subtrees of each node. If the absolute difference between the heights of the left and right subtrees is greater than 1 for any node, the function returns `-1` to indicate that the tree is not balanced. Otherwise, it returns the maximum height of the left and right subtrees plus 1.

The `isBalanced` function then checks the return value of `getHeight`: if it is not `-1`, the tree is balanced, and the function returns `true`. Otherwise, it returns `false`.

This solution has a time complexity of O(n), where n is the number of nodes in the binary tree, as it visits each node once to calculate the height. The space complexity is O(h), where h is the height of the tree, due to the recursive calls on the call stack.