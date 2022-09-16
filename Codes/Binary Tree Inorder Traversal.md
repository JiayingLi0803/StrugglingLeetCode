# Description
Given the root of a binary tree, return the inorder traversal of its nodes' values.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem94.jpeg)
```
Input: root = [1,null,2,3]
Output: [1,3,2]
```
**Example 2:**
```
Input: root = []
Output: []
```
**Example 3:**
```
Input: root = [1]
Output: [1]
```
**Constraints:**
```
The number of nodes in the tree is in the range [0, 100].
-100 <= Node.val <= 100
```
**Follow up:** 

Recursive solution is trivial, could you do it iteratively?
# Solution
```ruby
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        def helper(root):
            if root == None:
                return None
            if root.left != None:
                helper(root.left)
            res.append(root.val)
            if root.right != None:
                helper(root.right)
            
        res = []
        helper(root)
        return res
```
