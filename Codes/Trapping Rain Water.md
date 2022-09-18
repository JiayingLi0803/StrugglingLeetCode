# Description
Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.

**Example 1**
![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem42.png)

```
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.
```
**Example 2:**
```
Input: height = [4,2,0,3,2,5]
Output: 9
```
**Constraints:**
```
n == height.length
1 <= n <= 2 * 10**4
0 <= height[i] <= 10**5
```
# Solution
```ruby
class Solution:
    def trap(self, height: List[int]) -> int:
        if not height:
            return 0
        res = 0
        size = len(height)
        left_max = [0]*size
        right_max = [0]*size
        
        left_max[0] = height[0]
        right_max[-1] = height[-1]
        
        for i in range(1, size):
            left_max[i] = max(height[i], left_max[i-1])
        for i in range(size-2, -1, -1):
            right_max[i] = max(height[i], right_max[i+1])
            
        for i in range(1, size-1):
            res = res+ min(left_max[i], right_max[i])-height[i]
        return res
```
