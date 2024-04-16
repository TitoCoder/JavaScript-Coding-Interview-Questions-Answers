# Write a function to find the height of a binary tree

## Problem Description

The problem is to write a function that can find the height or maximum depth of a binary tree. The height of a binary tree is the number of nodes along the longest path from the root node down to the farthest leaf node.

## Requirements

1. Implement a function that takes a binary tree as input and returns the height of the tree.
2. The function should work for any valid binary tree, including empty trees.
3. The time complexity of the function should be O(n), where n is the number of nodes in the tree, as the function needs to visit each node once.
4. The space complexity should be O(h), where h is the height of the tree, as the function may need to use recursion and the maximum depth of the recursion stack is the height of the tree.

## JavaScript Code Solution

Here's a JavaScript implementation of a function to find the height of a binary tree:

```javascript
class TreeNode {
  constructor(val) {
    this.val = val;
    this.left = null;
    this.right = null;
  }
}

function getTreeHeight(root) {
  if (!root) {
    return 0; // Empty tree has a height of 0
  }

  let leftHeight = getTreeHeight(root.left);
  let rightHeight = getTreeHeight(root.right);

  return Math.max(leftHeight, rightHeight) + 1;
}

// Example usage:
let root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

console.log(getTreeHeight(root)); // Output: 3
```

In this solution, the `getTreeHeight` function takes a `TreeNode` object as input, which represents the root of the binary tree. The function recursively calculates the height of the left and right subtrees, and then returns the maximum of the two plus 1 (to account for the root node).

The base case is when the `root` is `null`, which means the tree is empty, and the height is 0.

The time complexity of this solution is O(n), as the function visits each node in the tree exactly once. The space complexity is O(h), where h is the height of the tree, due to the recursive calls on the call stack.