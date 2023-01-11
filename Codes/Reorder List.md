# Description
You are given the head of a singly linked-list. The list can be represented as:
```
L0 → L1 → … → Ln - 1 → Ln
```
Reorder the list to be on the following form:
```
L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → …
```
You may not modify the values in the list's nodes. Only nodes themselves may be changed.

 

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem143_1.jpg)

```
Input: head = [1,2,3,4]
Output: [1,4,2,3]
```
**Example 2:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem143_2.jpg)

```
Input: head = [1,2,3,4,5]
Output: [1,5,2,4,3]
```
**Constraints:**
```
The number of nodes in the list is in the range [1, 5 * 10**4].
1 <= Node.val <= 1000
```

# Solution
```ruby
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reorderList(self, head: Optional[ListNode]) -> None:
        """
        Do not return anything, modify head in-place instead.
        """
        if not head:
            return
        # find middle
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        # reverse the second list
        prev = None
        curr = slow
        while curr:
            curr.next, prev, curr = prev, curr, curr.next
        # merge two lists
        first, second = head, prev
        while second.next:
            first.next, first = second, first.next
            second.next, second = first, second.next
```
