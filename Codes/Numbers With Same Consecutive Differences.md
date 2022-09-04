# Description
Return all non-negative integers of length n such that the absolute difference between every two consecutive digits is k.

Note that every number in the answer must not have leading zeros. For example, 01 has one leading zero and is invalid.

You may return the answer in any order.

**Example 1:**
```
Input: n = 3, k = 7
Output: [181,292,707,818,929]
Explanation: Note that 070 is not a valid number, because it has leading zeroes.
```
**Example 2:**
```
Input: n = 2, k = 1
Output: [10,12,21,23,32,34,43,45,54,56,65,67,76,78,87,89,98]
```
**Constraints:**
```
2 <= n <= 9
0 <= k <= 9
```
# Solution
**Aproach 1: DFS**
```ruby
class Solution:
    def numsSameConsecDiff(self, n: int, k: int) -> List[int]:
        if n == 1:
            return [i for i in range(0,10)]
        result = []
        def DFS(n, num): #n: steps, num:first digit
            #base case
            if n==0:
                return result.append(num)
            tail_digit = num%10
            #using set to avoid duplicate when k = 0
            next_digits=set([tail_digit+k, tail_digit-k])
            for next_digit in next_digits:
                if 0<=next_digit<10:
                    new_num = num*10+next_digit
                    DFS(n-1, new_num)
        for num in range(1,10):
            DFS(n-1, num)
        return list(result)
```
**Approach 2: BFS**
```ruby
class Solution:
    def numsSameConsecDiff(self, n: int, k: int) -> List[int]:
        if n == 1:
            return [i for i in range(0,10)]
        #initialize level 1 queue
        queue = [i for i in range(1,10)]
        for step in range(0,n-1):#n-1 steps left
            next_queue = []
            for num in queue:
                tail_digit = num%10
                next_digits = set([tail_digit+k, tail_digit-k])
                for next_digit in next_digits:
                    if 0<=next_digit<10:
                        new_num = num*10+next_digit
                        next_queue.append(new_num)
            queue = next_queue
        return queue
```
