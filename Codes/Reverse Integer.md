# Description

Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

**Example 1:**
```
Input: x = 123
Output: 321
```
**Example 2:**
```
Input: x = -123
Output: -321
```
**Example 3:**
```
Input: x = 120
Output: 21
```
**Constraints:**
```
-231 <= x <= 231 - 1
```

# Solution
```ruby
class Solution:
    def reverse(self, x: int) -> int:
        if x==0:
            return 0
        s = str(x)
        if s[-1]=="0":
            s = s[:-1]
        if s[0]=="-":
            s = s[1:]
        s = s[::-1]
        if x>=0:
            y = int(s)
        else:
            y = -int(s)
        if y < -2**31 or y>2**31-1:
            return 0
        else:
            return y
```
