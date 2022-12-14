# Description
Implement pow(x, n), which calculates x raised to the power n (i.e., xn).

**Example 1:**
```
Input: x = 2.00000, n = 10
Output: 1024.00000
```
**Example 2:**
```
Input: x = 2.10000, n = 3
Output: 9.26100
```
**Example 3:**
```
Input: x = 2.00000, n = -2
Output: 0.25000
Explanation: 2-2 = 1/22 = 1/4 = 0.25
```
**Constraints:**
```
-100.0 < x < 100.0
-2**31 <= n <= 2**31-1
-10**4 <= xn <= 10**4
```
# Solution
```ruby
class Solution:
    def myPow(self, x: float, n: int) -> float:
        def quickMul(N):
            if N == 0:
                return 1.0
            y = quickMul(N // 2)
            return y * y if N % 2 == 0 else y * y * x
        
        return quickMul(n) if n >= 0 else 1.0 / quickMul(-n)
```
