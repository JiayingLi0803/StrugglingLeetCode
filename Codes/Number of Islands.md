# Description
Given an m x n 2D binary grid grid which represents a map of '1's (land) and '0's (water), return the number of islands.

An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Example 1:**
```
Input: grid = [
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
]
Output: 1
```
**Example 2:**
```
Input: grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]
Output: 3
```
**Constraints:**
```
m == grid.length
n == grid[i].length
1 <= m, n <= 300
grid[i][j] is '0' or '1'.
```
# Solution
```ruby
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        def DFS(r, c):
            row_num = len(grid)
            col_num = len(grid[0])
            
            if r<0 or c<0 or r>=row_num or c>=col_num or grid[r][c] == "0":
                return
            grid[r][c] = "0"
            DFS(r+1, c)
            DFS(r-1, c)
            DFS(r, c+1)
            DFS(r, c-1)
        if grid == None or len(grid) == 0:
            return 0
        row_num = len(grid)
        col_num = len(grid[0])
        r, c = 0, 0
        result = 0
        for r in range(row_num):
            for c in range (col_num):
                if grid[r][c] == "1":
                    DFS(r, c)
                    result += 1
        return result
```
