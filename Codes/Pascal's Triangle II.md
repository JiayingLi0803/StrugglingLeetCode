# Description

Given an integer rowIndex, return the rowIndexth (0-indexed) row of the Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem119.gif)

**Example 1:**
```
Input: rowIndex = 3
Output: [1,3,3,1]
```
**Example 2:**
```
Input: rowIndex = 0
Output: [1]
```
**Example 3:**
```
Input: rowIndex = 1
Output: [1,1]
```
**Constraints:**
```
0 <= rowIndex <= 33
```

**Follow up: ** Could you optimize your algorithm to use only O(rowIndex) extra space?
# Solution
```ruby
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        out = [1]
        if rowIndex==0:
            return out
        for i in range(1,rowIndex):
            nfact = math.factorial(rowIndex)
            ifact = math.factorial(i)
            refact = math.factorial(rowIndex-i)
            select = nfact/(ifact*refact)
            out.append(int(select))
        out.append(1)
        return out
```
