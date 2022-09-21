# Description
Given the root of a binary tree, return the postorder traversal of its nodes' values.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem145.jpg)
```
Input: root = [1,null,2,3]
Output: [3,2,1]
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
The number of the nodes in the tree is in the range [0, 100].
-100 <= Node.val <= 100
```
**Follow up:** Recursive solution is trivial, could you do it iteratively?
# Solution
**Approach 1: Recrusion**
```ruby
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        def dfs(root,res):
            if root is None: return []
            dfs(root.left, res)
            dfs(root.right, res)
            res.append(root.val)
            return res
        return dfs(root, [])
```
**Approach 2: Iteration**
```ruby
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        res = []
        stack = [root]
        while stack:
            node = stack.pop()
            if node:
                res.append(node.val)
                stack.append(node.left)
                stack.append(node.right)
        return res[::-1]
```
