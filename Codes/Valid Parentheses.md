# Description
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
 
**Example 1:**
```
Input: s = "()"
Output: true
```
**Example 2:**
```
Input: s = "()[]{}"
Output: true
```
**Example 3:**
```
Input: s = "(]"
Output: false
 ```
**Constraints:**
```
1 <= s.length <= 104
s consists of parentheses only '()[]{}'.
```

# Solution
```ruby
class Solution:
    def isValid(self, s: str) -> bool:
        if not s:
            return False
        if len(s)%2 != 0:
            return False
        dic = {
            ")":"(",
            "]":"[",
            "}":"{"
        }
        stack = []
        for i in s:
            if stack and i in dic:
                if stack[-1] == dic[i]:
                    stack.pop()
                else:
                    return False
            else:
                stack.append(i)
        return not stack
```
