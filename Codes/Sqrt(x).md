# Description
Given a non-negative integer x, compute and return the square root of x.

Since the return type is an integer, the decimal digits are truncated, and only the integer part of the result is returned.

Note: You are not allowed to use any built-in exponent function or operator, such as pow(x, 0.5) or x ** 0.5.

**Example 1:**
```
Input: x = 4
Output: 2
```
**Example 2:**
```
Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since the decimal part is truncated, 2 is returned.
```
**Constraints:**
```
0 <= x <= 2**31 - 1
```
# Solution
```ruby
class Solution:
    def mySqrt(self, x: int) -> int:
        if x==1:
            return 1
        if x==0:
            return 0
        L = 1
        R = x
        mid = (L+R)//2
        while mid < R:
            if mid**2 < x:
                if (mid+1)**2 >x:
                    return mid
                else:
                    L = mid
                    mid = (L+R)//2
            elif mid**2 == x:
                return mid
            elif mid**2 > x:
                if (mid-1)**2 < x:
                    return mid-1
                else:
                    R = mid
                    mid = (L+R)//2
```
