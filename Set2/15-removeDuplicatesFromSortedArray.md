## Problem Name
Remove Duplicates from Sorted Array

## Description
Given a sorted array `nums`, remove the duplicates in-place such that each element appears only once and returns the new length. Do not allocate extra space for another array; you must do this by modifying the input array in-place with O(1) extra memory.

## Sample Input
```
nums = [1, 1, 2]
```

## Sample Output
```
length = 2, nums = [1, 2]
```

## File Name
`removeDuplicatesFromSortedArray.js`

## Code Answer
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    if (nums.length === 0) return 0;
    let j = 0;
    for (let i = 1; i < nums.length; i++) {
        if (nums[i] !== nums[j]) {
            j++;
            nums[j] = nums[i];
        }
    }
    return j + 1;
};
```

**Explanation:**

1. We first check if the input array `nums` is empty. If it is, we return `0`.
2. We initialize a variable `j` to `0`. This variable will keep track of the position where we should place the next unique element.
3. We iterate through the array starting from the second element (index `1`). For each element `nums[i]`, we check if it is different from the last unique element `nums[j]`.
4. If `nums[i]` is different from `nums[j]`, we increment `j` and assign `nums[i]` to `nums[j+1]`. This way, we overwrite the duplicates with the unique elements.
5. After the loop finishes, `j+1` will be the length of the new array with duplicates removed.
6. We return `j+1` as the new length of the array.

The time complexity of this solution is O(n), where n is the length of the input array `nums`. We iterate through the array once. The space complexity is O(1) since we modify the input array in-place without using any additional data structures.