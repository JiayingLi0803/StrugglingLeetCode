# Description
Given an array of strings words, return true if it forms a valid word square.

A sequence of strings forms a valid word square if the kth row and column read the same string, where 0 <= k < max(numRows, numColumns).

**Example 1:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem422_1.jpg)
```
Input: words = ["abcd","bnrt","crmy","dtye"]
Output: true
Explanation:
The 1st row and 1st column both read "abcd".
The 2nd row and 2nd column both read "bnrt".
The 3rd row and 3rd column both read "crmy".
The 4th row and 4th column both read "dtye".
Therefore, it is a valid word square.
```
**Example 2:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem422_2.jpg)
```
Input: words = ["abcd","bnrt","crm","dt"]
Output: true
Explanation:
The 1st row and 1st column both read "abcd".
The 2nd row and 2nd column both read "bnrt".
The 3rd row and 3rd column both read "crm".
The 4th row and 4th column both read "dt".
Therefore, it is a valid word square.
```
**Example 3:**

![](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Figures/Problem422_3.jpg)
```
Input: words = ["ball","area","read","lady"]
Output: false
Explanation:
The 3rd row reads "read" while the 3rd column reads "lead".
Therefore, it is NOT a valid word square.
```
**Constraints:**
```
1 <= words.length <= 500
1 <= words[i].length <= 500
words[i] consists of only lowercase English letters.
```
# Solution
**Approach 1: Map**
```ruby
class Solution:
    def validWordSquare(self, words: List[str]) -> bool:
        return (transposed:=list(itertools.zip_longest(*words))) == list(zip(*transposed))
```
**Approach 2: List Operations**
```ruby
class Solution:
    def validWordSquare(self, words: List[str]) -> bool:
        transpose = []
        for w in words:
            while len(w) > len(transpose): transpose.append([])
            for i in range(len(w)): transpose[i].append(w[i])
        for i in range(len(words)):
            if words[i] != ''.join(transpose[i]): return False
        return True
```
