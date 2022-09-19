# Description
Given the root of a binary tree, check whether it is a mirror of itself (i.e., symmetric around its center).

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem101_1.jpeg)
```
Input: root = [1,2,2,3,4,4,3]
Output: true
```
**Example 2:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem101_2.jpeg)
```
Input: root = [1,2,2,null,3,null,3]
Output: false
 

Constraints:

The number of nodes in the tree is in the range [1, 1000].
-100 <= Node.val <= 100
 

Follow up: Could you solve it both recursively and iteratively?
```

# Solution
**Approach 1: Recursion**
```ruby
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        def isMirror(tree1, tree2):
            if not tree1 and not tree2:
                return True
            if not tree1 or not tree2:
                return False
            return tree1.val == tree2.val and isMirror(tree1.left, tree2.right) and isMirror(tree1.right, tree2.left)
        return isMirror(root, root)
```
**Approach 2: Iteration**
```ruby
```
