# Description
You have n coins and you want to build a staircase with these coins. The staircase consists of ``k`` rows where the ith row has exactly ``i`` coins. The last row of the staircase may be incomplete.

Given the integer ``n``, return the number of complete rows of the staircase you will build.

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem441_1.jpeg)
```
Input: n = 5
Output: 2
Explanation: Because the 3rd row is incomplete, we return 2.
```
**Example 2:**
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem441_2.jpeg)
```
Input: n = 8
Output: 3
Explanation: Because the 4th row is incomplete, we return 3.
```
**Constraints:**
```
1 <= n <= 2**31 - 1
```
# Solution
**Approach 1: Brute Force**
```ruby
class Solution:
    def arrangeCoins(self, n: int) -> int:
        step = 0
        add = 1
        while add<=n:
            step += 1
            add = (step+1)*(step+2)/2
        return step
```
**Approach 2: Binary Search**
```ruby
class Solution:
    def arrangeCoins(self, n: int) -> int:
        left, right = 0, n
        while left <= right:
            k = (right + left) // 2
            curr = k * (k + 1) // 2
            if curr == n:
                return k
            if n < curr:
                right = k - 1
            else:
                left = k + 1
        return right
```
**Approach 3: Math**
```ruby
class Solution:
    def arrangeCoins(self, n: int) -> int:
        return (int)((2 * n + 0.25)**0.5 - 0.5)
```
