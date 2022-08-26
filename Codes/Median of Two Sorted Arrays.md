# Description
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).


**Example 1:**
```
Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
Explanation: merged array = [1,2,3] and median is 2.
```
**Example 2:**
```
Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
```
**Constraints:**
```
nums1.length == m
nums2.length == n
0 <= m <= 1000
0 <= n <= 1000
1 <= m + n <= 2000
-106 <= nums1[i], nums2[i] <= 106
```

# Solution
```ruby
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        def findKsmallest(nums1,nums2,k): #len(nums1)<len(nums2)   
            if len(nums1)>len(nums2):
                nums1, nums2 = nums2, nums1
            while k>=1:
                if len(nums1) == 0:
                    return nums2[k-1] 
                elif len(nums2) == 0:
                    return nums1[k-1]
                if k==1:
                    return min(nums1[0],nums2[0])
                if k//2 <= len(nums1) and k//2 <= len(nums2):
                    compare1 = nums1[k//2-1]
                    compare2 = nums2[k//2-1]
                    ex = k//2
                elif k//2 > len(nums1):
                    compare1 = nums1[-1]
                    compare2 = nums2[k//2-1]
                    ex = len(nums1)                
                if compare1>=compare2:
                    nums2 = nums2[ex:]                    
                elif compare2>compare1:
                    nums1 = nums1[ex:]
                k = k-ex        
        if (len(nums1)+len(nums2))%2 == 1:
            k = (len(nums1)+len(nums2))//2+1
            return findKsmallest(nums1,nums2,k)
        else:
            k = (len(nums1)+len(nums2))//2
            k2 = k+1
            return (findKsmallest(nums1,nums2,k)+findKsmallest(nums1,nums2,k2))/2
        
```
