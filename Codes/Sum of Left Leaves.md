# Description
Given the root of a binary tree, return the sum of all left leaves.

A leaf is a node with no children. A left leaf is a leaf that is the left child of another node.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem404.jpeg)
```
Input: root = [3,9,20,null,null,15,7]
Output: 24
Explanation: There are two left leaves in the binary tree, with values 9 and 15 respectively.
```
**Example 2:**
```
Input: root = [1]
Output: 0
```
**Constraints:**
```
The number of nodes in the tree is in the range [1, 1000].
-1000 <= Node.val <= 1000
```
# Solution
```ruby
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    
    def sumOfLeftLeaves(self, root: TreeNode) -> int:
        
        # An empty root is one of the test cases!
        if root is None:
            return 0

        def process_subtree(subtree, is_left):
            
            # Base case: This is a leaf node.
            if subtree.left is None and subtree.right is None:
                return subtree.val if is_left else 0
            
            # Recursive case: We need to add and return the results of the 
            # left and right subtrees.
            total = 0
            if subtree.left:
                total += process_subtree(subtree.left, True)
            if subtree.right:
                total += process_subtree(subtree.right, False)
            return total
        
        # Call the recursive function on the root node to start the process.
        # We need to be careful of the case that the root is empty.
        return process_subtree(root, False)
```
