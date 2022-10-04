# Description
Given a string s, reverse only all the vowels in the string and return it.

The vowels are 'a', 'e', 'i', 'o', and 'u', and they can appear in both lower and upper cases, more than once.

**Example 1:**
```
Input: s = "hello"
Output: "holle"
```
**Example 2:**
```
Input: s = "leetcode"
Output: "leotcede"
```
**Constraints:**
```
1 <= s.length <= 3 * 10**5
s consist of printable ASCII characters.
```
# Solution
**Approach 1: List Operation**
```ruby
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowelList = ["a", "e", "i", "o", "u", "A", "E", "I", "O", "U"]
        vowels = []
        for i in s:
            if i in vowelList:
                vowels.append(i)
        vowels = vowels[::-1]
        cnt = 0
        sList = list(s)
        for i in range(len(sList)):
            if sList[i] in vowelList:
                sList[i] = vowels[cnt]
                cnt +=1
        return "".join(sList)
```
**Approach 2: Two Pointers**
```ruby
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowel=set('aeiouAEIOU')
        temp=list(s)
        l=0
        r=len(temp)-1
        while l<r:
            if temp[l] in vowel and temp[r] in vowel:
                temp[l],temp[r]=temp[r],temp[l]
                l+=1
                r-=1
                continue
            if temp[l] not in vowel:
                l+=1
            if temp[r] not in vowel:
                r-=1
        
        return "".join(temp)
```
