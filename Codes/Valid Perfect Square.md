# Description
Given a positive integer num, write a function which returns True if num is a perfect square else False.

Follow up: Do not use any built-in library function such as sqrt.

**Example 1:**
```
Input: num = 16
Output: true
```
**Example 2:**
```
Input: num = 14
Output: false
``` 
**Constraints:**
```
1 <= num <= 2^31 - 1
```
# Solution
**Approach 1: Hash Table**
```ruby
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        table = list(map(lambda x: x**2, [i for i in range(2**16)]))
        if num in table:
            return True
        else:
            return False
```
**Approach 2: Newton's Method**
```ruby
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        if num < 2:
            return True
        
        x = num // 2
        while x * x > num:
            x = (x + num // x) // 2
        return x * x == num
```
**Approach 3: Binary Search**
```ruby
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        if num < 2:
            return True
        
        left, right = 2, num // 2
        
        while left <= right:
            x = left + (right - left) // 2
            guess_squared = x * x
            if guess_squared == num:
                return True
            if guess_squared > num:
                right = x - 1
            else:
                left = x + 1
        
        return False
```
