# Description
Given the root of a binary tree, return all root-to-leaf paths in any order.

A leaf is a node with no children.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem257.jpeg)
```
Input: root = [1,2,3,null,5]
Output: ["1->2->5","1->3"]
```
**Example 2:**
```
Input: root = [1]
Output: ["1"]
```
**Constraints:**
```
The number of nodes in the tree is in the range [1, 100].
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
    def binaryTreePaths(self, root):
        """
        :type root: TreeNode
        :rtype: List[str]
        """
        def construct_paths(root, path):
            if root:
                path += str(root.val)
                if not root.left and not root.right:  # if reach a leaf
                    paths.append(path)  # update paths  
                else:
                    path += '->'  # extend the current path
                    construct_paths(root.left, path)
                    construct_paths(root.right, path)

        paths = []
        construct_paths(root, '')
        return paths
```
