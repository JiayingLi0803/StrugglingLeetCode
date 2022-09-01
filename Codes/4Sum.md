# Description
Given an array nums of n integers, return an array of all the unique quadruplets [nums[a], nums[b], nums[c], nums[d]] such that:

+ 0 <= a, b, c, d < n
+ a, b, c, and d are distinct.
+ nums[a] + nums[b] + nums[c] + nums[d] == target
+ You may return the answer in any order.

**Example 1:**
```
Input: nums = [1,0,-1,0,-2,2], target = 0
Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]
```
**Example 2:**
```
Input: nums = [2,2,2,2,2], target = 8
Output: [[2,2,2,2]]
```
**Constraints:**
```
1 <= nums.length <= 200
-10**9 <= nums[i] <= 10**9
-10**9 <= target <= 10**9
```
# Solution
```ruby
class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        
        def ksum(nums: List[int], target: int, k: int) -> List[List[int]]:
            res = []
            #1. null, 2. len(nums)<k, 3. smallest>average/largset<avergae
            if not nums or len(nums)<k:
                return res
            average = target/k
            if nums[0]>average or nums[-1]<average:
                return res
            # main branch
            if k==2: # 2sum
                return twoSum(nums, target)
            for i in range(len(nums)):
                if i==0 or nums[i-1]!=nums[i]: # unique
                    for sols in ksum(nums[i+1:], target-nums[i], k-1):
                        res.append([nums[i]]+sols)
            return res
                           
        def twoSum(nums: List[int], target: int):# two pointers
            res = []
            L, R = 0, len(nums)-1
            while L<R:
                if nums[L]+nums[R]<target or (L>0 and nums[L-1]==nums[L]):
                    L+=1
                elif nums[L]+nums[R]>target or (R<len(nums)-1 and nums[R+1]==nums[R]):
                    R-=1
                elif nums[L]+nums[R]==target:
                    res.append([nums[L],nums[R]])
                    L+=1
                    R-=1
            return res

        # main function
        nums.sort()
        return ksum(nums,target,4)
```
