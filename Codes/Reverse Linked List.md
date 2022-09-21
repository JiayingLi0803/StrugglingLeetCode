# Description
Given the head of a singly linked list, reverse the list, and return the reversed list.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem206_1.jpg)
```
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
```
**Example 2:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem206_2.jpg)
```
Input: head = [1,2]
Output: [2,1]
```
**Example 3:**
```
Input: head = []
Output: []
```
**Constraints:**
```
The number of nodes in the list is the range [0, 5000].
-5000 <= Node.val <= 5000
```
**Follow up:** A linked list can be reversed either iteratively or recursively. Could you implement both?
# Solution
```ruby
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev = None
        curr = head
        while curr:
            next_temp = curr.next
            curr.next = prev
            prev = curr
            curr = next_temp
        return prev
```
