# Description
Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

**Example 1:**
```
Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]
```
**Example 2:**
```
Input: n = 1
Output: ["()"]
```
**Constraints:**
```
1 <= n <= 8
```
# Solution
```ruby
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        if n==0:
            return [""]
        result = []
        for i in range(0,n):
            for left in self.generateParenthesis(i):
                for right in self.generateParenthesis(n-i-1):
                    result.append('({}){}'.format(left, right))
        return result
```
