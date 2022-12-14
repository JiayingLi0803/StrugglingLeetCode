# Description
Given an integer num, repeatedly add all its digits until the result has only one digit, and return it.

**Example 1:**
```
Input: num = 38
Output: 2
Explanation: The process is
38 --> 3 + 8 --> 11
11 --> 1 + 1 --> 2 
Since 2 has only one digit, return it.
```
**Example 2:**
```
Input: num = 0
Output: 0
```
**Constraints:**
```
0 <= num <= 2**31 - 1
```
**Follow up:**

Could you do it without any loop/recursion in O(1) runtime?
# Solution
**Approach 1: Recursion**
```ruby
class Solution:
    def addDigits(self, num: int) -> int:
        def recurAdd(num):
            if len(str(num)) == 1:
                return num
            s = str(num)
            num = 0
            for i in s:
                num += int(i)
            return recurAdd(num)
        
        if len(str(num)) == 1:
            return num
        else:
            return recurAdd(num)
```
**Approach 2: mod 9**
```ruby
class Solution:
    def addDigits(self, num: int) -> int:
        return 1 + (num - 1) % 9 if num else 0
```
Or
```ruby
class Solution:
    def addDigits(self, num: int) -> int:
        if num == 0:
            return 0
        if num % 9 == 0:
            return 9
        return num % 9
```
