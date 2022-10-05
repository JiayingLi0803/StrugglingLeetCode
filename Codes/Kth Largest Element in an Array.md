# Description
Given an integer array nums and an integer k, return the kth largest element in the array.

Note that it is the kth largest element in the sorted order, not the kth distinct element.

You must solve it in O(n) time complexity.

**Example 1:**
```
Input: nums = [3,2,1,5,6,4], k = 2
Output: 5
```
**Example 2:**
```
Input: nums = [3,2,3,1,2,4,5,5,6], k = 4
Output: 4
```
**Constraints:**
```
1 <= k <= nums.length <= 10**5
-10**4 <= nums[i] <= 10**4
```
# Solution
**Approach 1: Sorting (O(NlogN))**
```ruby
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        new = sorted(nums)
        return new[-k]
```
**Approach 2: QuickSelect (O(N))**
```ruby
```
