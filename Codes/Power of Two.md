# Description
Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2x.

**Example 1:**
```
Input: n = 1
Output: true
Explanation: 2**0 = 1
```
**Example 2:**
```
Input: n = 16
Output: true
Explanation: 2**4 = 16
```
**Example 3:**
```
Input: n = 3
Output: false
``` 

**Constraints:**
```
-2**31 <= n <= 2**31 - 1
```

Follow up: Could you solve it without loops/recursion?

# Solution
**Approach 1: Recursive**
```ruby
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        while n>0:
            if n%2 == 0:
                n = n/2
            else:
                if n == 1:
                    return True
                else:
                    return False
```
**Approach 2: n & (n - 1) == 0**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem231_1.png)
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem231_2.png)
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem231_3.png)
```ruby
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        if n == 0:
            return False
        return n & (n-1) == 0
```
**Approach 3: n & (-n) == n**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem231_4.png)
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem231_5.png)
```ruby
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        if n == 0:
            return False
        return n & (-n) == n
```
