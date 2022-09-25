# Description
Given the head of a singly linked list, return `true` if it is a palindrome or `false` otherwise.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem234_1.jpeg)
```
Input: head = [1,2,2,1]
Output: true
```
**Example 2:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem234_2.jpeg)
```
Input: head = [1,2]
Output: false
```
**Constraints:**
```
The number of nodes in the list is in the range [1, 10**5].
0 <= Node.val <= 9
``` 
**Follow up:** Could you do it in O(n) time and O(1) space?

# Solution
**Approach 1: Linked List**
```ruby
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        vals = []
        curr = head
        while curr is not None:
            vals.append(curr.val)
            curr = curr.next
        return vals == vals[::-1]
```
**Approach 2: Recursion**
```ruby
def isPalindrome(self, head: ListNode) -> bool:

    self.front_pointer = head

    def recursively_check(current_node=head):
        if current_node is not None:
            if not recursively_check(current_node.next):
                return False
            if self.front_pointer.val != current_node.val:
                return False
            self.front_pointer = self.front_pointer.next
        return True

    return recursively_check()
```
