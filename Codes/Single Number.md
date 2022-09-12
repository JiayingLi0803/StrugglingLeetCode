# Desciption
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

**Example 1:**
```
Input: nums = [2,2,1]
Output: 1
```
**Example 2:**
```
Input: nums = [4,1,2,1,2]
Output: 4
```
**Example 3:**
```
Input: nums = [1]
Output: 1
```
**Constraints:**
```
1 <= nums.length <= 3 * 10**4
-3 * 10**4 <= nums[i] <= 3 * 10**4
Each element in the array appears twice except for one element which appears only once.
```
# SOlution
**Approach 1: Counting**
```ruby
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        countDict = collections.Counter(nums)
        for key, value in countDict.items():
            if value==1:
                return key
```
**Approach 2: Math**

$2∗(a+b+c)−(a+a+b+b+c)=c$
```ruby
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        return 2 * sum(set(nums)) - sum(nums)
```
**Approach 3: Bit Manipulation**
```ruby
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        a = 0
        for i in nums:
            a ^= i
        return a
```
**Approach 4: List operation**
```ruby
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        no_duplicate_list = []
        for i in nums:
            if i not in no_duplicate_list:
                no_duplicate_list.append(i)
            else:
                no_duplicate_list.remove(i)
        return no_duplicate_list.pop()
```
