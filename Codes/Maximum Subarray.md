# Description
Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

A subarray is a contiguous part of an array.

**Example 1:**
```
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```
**Example 2:**
```
Input: nums = [1]
Output: 1
```
**Example 3:**
```
Input: nums = [5,4,-1,7,8]
Output: 23
```
**Constraints:**
```
1 <= nums.length <= 10**5
-10**4 <= nums[i] <= 10**4
```
**Follow up:** If you have figured out the O(n) solution, try coding another solution using the divide and conquer approach, which is more subtle.
# Solution
**Approach 1: Brute Force (Time Limit Exceeded)**
```ruby
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        sumlist = []
        for i in range(len(nums)-1):
            add = nums[i]
            for j in range(i+1,len(nums)+1):
                add = max(add, sum(nums[i:j+1]))
            sumlist.append(add)
        sumlist.append(nums[-1])
        return max(sumlist)
```
**Approach 2: Divide and Conquer**
```ruby
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        def divide(nums, left, right):
            if left>right:
                return -math.inf
            mid = (left+right)//2
            # left half
            leftHalfAdd, rightHalfAdd, curr = 0, 0, 0
            for i in range(mid-1, left-1, -1):
                curr += nums[i]
                leftHalfAdd = max(leftHalfAdd, curr)
            curr = 0
            for i in range(mid+1, right+1):
                curr += nums[i]
                rightHalfAdd = max(rightHalfAdd, curr)
            combineAdd = nums[mid] + rightHalfAdd+leftHalfAdd
            left_half = divide(nums, left, mid - 1)
            right_half = divide(nums, mid + 1, right)
            return max(combineAdd, left_half, right_half)
        return divide(nums, 0, len(nums) - 1)
```
**Approach 3: Dynamic Programming**
```ruby
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        # Initialize our variables using the first element.
        current_subarray = max_subarray = nums[0]
        
        # Start with the 2nd element since we already used the first one.
        for num in nums[1:]:
            # If current_subarray is negative, throw it away. Otherwise, keep adding to it.
            current_subarray = max(num, current_subarray + num)
            max_subarray = max(max_subarray, current_subarray)
        
        return max_subarray
```
