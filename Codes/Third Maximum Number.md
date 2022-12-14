# Description
Given an integer array nums, return the third distinct maximum number in this array. If the third maximum does not exist, return the maximum number.

**Example 1:**
```
Input: nums = [3,2,1]
Output: 1
Explanation:
The first distinct maximum is 3.
The second distinct maximum is 2.
The third distinct maximum is 1.
```
**Example 2:**
```
Input: nums = [1,2]
Output: 2
Explanation:
The first distinct maximum is 2.
The second distinct maximum is 1.
The third distinct maximum does not exist, so the maximum (2) is returned instead.
```
**Example 3:**
```
Input: nums = [2,2,3,1]
Output: 1
Explanation:
The first distinct maximum is 3.
The second distinct maximum is 2 (both 2's are counted together since they have the same value).
The third distinct maximum is 1.
```
**Constraints:**
```
1 <= nums.length <= 10**4
-2**31 <= nums[i] <= 2**31 - 1
```
**Follow up:** Can you find an O(n) solution?
# Solution
**Approach 1: Set**
```ruby
class Solution:
    def thirdMax(self, nums: List[int]) -> int:
        new = list(set(nums))
        new.sort()
        if len(new) < 3:
            return new[-1]
        return new[-3]
```
**Approach 2: Sorting**
```ruby
class Solution:
    def thirdMax(self, nums: List[int]) -> int:
        # Sort the array.
        nums.sort(reverse = True)
        
        elem_counted = 1
        prev_elem = nums[0]
        
        for index in range(len(nums)):
            # Current element is different from previous.
            if nums[index] != prev_elem:
                elem_counted += 1
                prev_elem = nums[index]
            
            # If we have counted 3 numbers then return current number.
            if elem_counted == 3:
                return nums[index]
        
        # We never counted 3 distinct numbers, return largest number.
        return nums[0]
```
