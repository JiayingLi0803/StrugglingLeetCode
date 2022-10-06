# Description
Given a string s, return the longest palindromic substring in s.

A string is called a palindrome string if the reverse of that string is the same as the original string.

**Example 1:**
```
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.
```
**Example 2:**
```
Input: s = "cbbd"
Output: "bb"
```
**Constraints:***
```
1 <= s.length <= 1000
s consist of only digits and English letters.
```
# Solution
**Approach 1: Two pointers**
```ruby
class Solution:
    def longestPalindrome(self, s: str) -> str:
        longest = ''
        def findLongest(s, l, r):
            while l>=0 and r<len(s) and s[l] == s[r]:
                l-=1
                r+=1
            return s[l+1:r]
        
        for i in range(len(s)):
            s1 = findLongest(s, i, i)
            if len(s1) > len(longest): longest = s1
            
            s2 = findLongest(s, i, i+1)
            if len(s2) > len(longest): longest = s2
                
        return longest
```
**Approach 2: Dynamic Programming**
```ruby

```
