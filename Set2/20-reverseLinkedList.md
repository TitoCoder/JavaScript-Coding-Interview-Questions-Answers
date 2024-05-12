## 20. Reverse Linked List

**Description:**
Write a function that takes a linked list as input and returns a new linked list with the nodes reversed.

**Sample Input:**
```javascript
const head = {
  val: 1,
  next: {
    val: 2,
    next: {
      val: 3,
      next: {
        val: 4,
        next: null
      }
    }
  }
}
```

**Sample Output:**
```javascript
{
  val: 4,
  next: {
    val: 3,
    next: {
      val: 2,
      next: {
        val: 1,
        next: null
      }
    }
  }
}
```

**File Name:** `reverseLinkedList.js`

**Code Answer:**

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    let prev = null;
    let curr = head;
    
    while (curr !== null) {
        let next = curr.next;
        curr.next = prev;
        prev = curr;
        curr = next;
    }
    
    return prev;
};
```

**Explanation:**

1. We initialize two pointers: `prev` and `curr`. `prev` will keep track of the previous node, and `curr` will keep track of the current node.
2. We start by setting `prev` to `null` and `curr` to the head of the linked list.
3. We iterate through the linked list using a `while` loop until `curr` becomes `null` (end of the list).
4. Inside the loop, we store the next node in a temporary variable `next`.
5. We reverse the link by setting the `next` pointer of the current node to the previous node (`curr.next = prev`).
6. We move `prev` and `curr` one step forward (`prev = curr` and `curr = next`).
7. After the loop ends, `prev` will be pointing to the new head of the reversed linked list.
8. We return `prev` as the new head of the reversed linked list.

The time complexity of this solution is O(n), where n is the number of nodes in the linked list, as we need to iterate through the entire list once. The space complexity is O(1) since we are using a constant amount of extra space (the pointers `prev`, `curr`, and `next`).