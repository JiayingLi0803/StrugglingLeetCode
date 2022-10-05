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
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        def partition(nums, left, right, pivot_index):
            pivot = nums[pivot_index]
            # move pivot to the right most
            nums[pivot_index], nums[right] = nums[right], nums[pivot_index]
            # store pivot index
            store_index = left
            for i in range(left, right):
                if nums[i] < pivot:
                    nums[i], nums[store_index] = nums[store_index], nums[i]
                    store_index += 1
            # place pivot in the correct position
            nums[store_index], nums[right] = nums[right], nums[store_index]
            return nums, store_index
        def select(nums, left, right, k_smallest):
            if left == right:
                return nums[left]
            pivot_index = random.randint(left, right)
            # select a random pivot_index between 
            pivot_index = random.randint(left, right)     
                            
            # find the pivot position in a sorted list   
            nums, pivot_index = partition(nums, left, right, pivot_index)

            # the pivot is in its final sorted position
            if k_smallest == pivot_index:
                 return nums[k_smallest]
            # go left
            elif k_smallest < pivot_index:
                return select(nums, left, pivot_index - 1, k_smallest)
            # go right
            else:
                return select(nums, pivot_index + 1, right, k_smallest)
        
        # kth largest is (n - k)th smallest 
        return select(nums, 0, len(nums) - 1, len(nums) - k)
```
