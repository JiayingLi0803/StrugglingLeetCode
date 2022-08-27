# Description

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.

 
**Example 1:**
```
Input: nums = [1,3,5,6], target = 5
Output: 2
```
**Example 2:**
```
Input: nums = [1,3,5,6], target = 2
Output: 1
```
**Example 3:**
```
Input: nums = [1,3,5,6], target = 7
Output: 4
```
**Constraints:**
```
1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums contains distinct values sorted in ascending order.
-104 <= target <= 104
```

# Solution
```ruby
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        if target>nums[-1]:
            return len(nums)
        if target<nums[0]:
            return 0
        k = len(nums)
        left = 0
        right = k-1
        mid = (left+right)//2        
        while left<=right:
            if target == nums[mid]:
                return mid
            else:  
                if right-left == 1:
                    return left+1
                elif target < nums[mid]:
                    right = mid
                elif target > nums[mid]:
                    left = mid              
                mid = (left+right)//2
```
