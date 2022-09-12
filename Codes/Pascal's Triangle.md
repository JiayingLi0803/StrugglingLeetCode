# Description
Given an integer numRows, return the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem118.gif)

**Example 1:**
```
Input: numRows = 5
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
```
**Example 2:**
```
Input: numRows = 1
Output: [[1]]
```
**Constraints:**
```
1 <= numRows <= 30
```
# Solution
**Approach 1: List**
```ruby
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        out = [[1]]
        nextList = [1]
        def nextBinary(numList):
            outList = [1]
            for i in range(len(numList)-1):
                outList.append(numList[i]+numList[i+1])
            outList.append(1)
            return outList
        k = 0
        while k < numRows-1:
            out.append(nextBinary(nextList))
            nextList = out[-1]
            k+=1
        return out
```
**Approach 2: Dynamic Programming**
```ruby
class Solution:
    def generate(self, num_rows: int) -> List[List[int]]:
        triangle = []

        for row_num in range(num_rows):
            # The first and last row elements are always 1.
            row = [None for _ in range(row_num + 1)]
            row[0], row[-1] = 1, 1

            # Each triangle element is equal to the sum of the elements
            # above-and-to-the-left and above-and-to-the-right.
            for j in range(1, len(row) - 1):
                row[j] = triangle[row_num - 1][j - 1] + triangle[row_num - 1][j]

            triangle.append(row)

        return triangle
```
