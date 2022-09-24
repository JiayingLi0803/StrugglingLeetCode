# Description

Given the root of a binary tree, invert the tree, and return its root.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem226_1.jpeg)
```
Input: root = [4,2,7,1,3,6,9]
Output: [4,7,2,9,6,3,1]
```
**Example 2:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem226_2.jpeg)
```
Input: root = [2,1,3]
Output: [2,3,1]
```
**Example 3:**
```
Input: root = []
Output: []
```
**Constraints:**
```
The number of nodes in the tree is in the range [0, 100].
-100 <= Node.val <= 100
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
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if not root:
            return None
        
        right = self.invertTree(root.right)
        left = self.invertTree(root.left)
        root.left = right
        root.right = left
        return root
```
