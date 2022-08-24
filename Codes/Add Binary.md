# Description
Given two binary strings a and b, return their sum as a binary string.

**Example 1:**
```
Input: a = "11", b = "1"
Output: "100"
```
**Example 2:**
```
Input: a = "1010", b = "1011"
Output: "10101"
```
**Constraints:**
```
1 <= a.length, b.length <= 104
a and b consist only of '0' or '1' characters.
Each string does not contain leading zeros except for the zero itself.
```

# Solution
```ruby
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        reverse_a = a[::-1]
        reverse_b = b[::-1]
        int_a, int_b = 0,0
       
        for i in range(0, len(a)):
            int_a += int(reverse_a[i])*2**i
        for i in range(0,len(b)):
            int_b += int(reverse_b[i])*2**i
        
        int_ans = int_a+int_b
        
        ans = ""
        num = int_ans
        if num == 0:
            return "0"
        while num>0:
            x = num%2
            ans += str(x)
            num = num//2
        return ans[::-1]
```
