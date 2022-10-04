# Description
Given a string s, check if it can be constructed by taking a substring of it and appending multiple copies of the substring together.

**Example 1:**
```
Input: s = "abab"
Output: true
Explanation: It is the substring "ab" twice.
```
**Example 2:**
```
Input: s = "aba"
Output: false
```
**Example 3:**
```
Input: s = "abcabcabcabc"
Output: true
Explanation: It is the substring "abc" four times or the substring "abcabc" twice.
```
**Constraints:**
```
1 <= s.length <= 10**4
s consists of lowercase English letters.
```
# Solution
**Approach 1: Brute Force**
```ruby
class Solution:
    def repeatedSubstringPattern(self, s):
        N = len(s)
        for i in range(1, N//2+1):
            if N % i == 0 and s[:i]* (N//i) == s:
                return True
        return False
```
**Approach 2: Linear Matching**
```ruby
class Solution:
    def repeatedSubstringPattern(self, s: str) -> bool:
        return (s*2)[1:-1].find(s) != -1
```
