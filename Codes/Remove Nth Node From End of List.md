# Description
Given the head of a linked list, remove the nth node from the end of the list and return its head.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem19.jpg)
```
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
```
**Example 2:**
```
Input: head = [1], n = 1
Output: []
```
**Example 3:**
```
Input: head = [1,2], n = 1
Output: [1]
```
**Constraints:**
```
The number of nodes in the list is sz.
1 <= sz <= 30
0 <= Node.val <= 100
1 <= n <= sz
```
Follow up: Could you do this in one pass?
# Solution
```ruby
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        begin = ListNode()
        begin.next = head
        first = head
        length = 0
        while first != None:
            length += 1
            first = first.next
        pos = length - n
        first = begin
        while pos>0:
            pos -=1
            first = first.next
        first.next = first.next.next
        return begin.next
```
