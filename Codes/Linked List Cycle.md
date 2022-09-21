# Description
Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return true if there is a cycle in the linked list. Otherwise, return false.

**Example 1:**
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem141_1.png)
```
Input: head = [3,2,0,-4], pos = 1
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).
```
**Example 2:**
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem141_2.png)
```
Input: head = [1,2], pos = 0
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.
```
**Example 3:**
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem141_3.png)
```
Input: head = [1], pos = -1
Output: false
Explanation: There is no cycle in the linked list.
```
**Constraints:**
```
The number of the nodes in the list is in the range [0, 104].
-10**5 <= Node.val <= 10**5
pos is -1 or a valid index in the linked-list.
```
Follow up: Can you solve it using O(1) (i.e. constant) memory?
# Solution
```ruby
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def hasCycle(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        node_seen = set()
        while head is not None:
            if head in node_seen:
                return True
            node_seen.add(head)
            head = head.next
        return False
```
