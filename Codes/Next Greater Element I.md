# Description
The next greater element of some element x in an array is the first greater element that is to the right of x in the same array.

You are given two distinct 0-indexed integer arrays nums1 and nums2, where nums1 is a subset of nums2.

For each 0 <= i < nums1.length, find the index j such that nums1[i] == nums2[j] and determine the next greater element of nums2[j] in nums2. If there is no next greater element, then the answer for this query is -1.

Return an array ans of length nums1.length such that ans[i] is the next greater element as described above.

**Example 1:**
```
Input: nums1 = [4,1,2], nums2 = [1,3,4,2]
Output: [-1,3,-1]
Explanation: The next greater element for each value of nums1 is as follows:
- 4 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
- 1 is underlined in nums2 = [1,3,4,2]. The next greater element is 3.
- 2 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
```
**Example 2:**
```
Input: nums1 = [2,4], nums2 = [1,2,3,4]
Output: [3,-1]
Explanation: The next greater element for each value of nums1 is as follows:
- 2 is underlined in nums2 = [1,2,3,4]. The next greater element is 3.
- 4 is underlined in nums2 = [1,2,3,4]. There is no next greater element, so the answer is -1.
```
**Constraints:**
```
1 <= nums1.length <= nums2.length <= 1000
0 <= nums1[i], nums2[i] <= 10**4
All integers in nums1 and nums2 are unique.
All the integers of nums1 also appear in nums2.
```
**Follow up: **Could you find an O(nums1.length + nums2.length) solution?
# Solution
**Approach 1: Brute Force**
```ruby
class Solution:
    def nextGreaterElement(self, nums1: List[int], nums2: List[int]) -> List[int]:
        out = []
        for i in nums1:
            if not list(filter(lambda x: x>i, nums2[nums2.index(i):])):
                out.append(-1)
            else:
                goal = max(nums2)
                for j in range(nums2.index(i),len(nums2)):
                    if nums2[j]>i:
                        break
                out.append(nums2[j])
        return out
```
**Approach 2: Stacks**
```ruby
class Solution:
    def nextGreaterElement(self, nums1: List[int], nums2: List[int]) -> List[int]:
        # using stack make a ngr 
        stack = []
        ngr = []
        for i in reversed(range(len(nums2))):
            while stack and nums2[i]>= stack[-1]:
                stack.pop()
            if not stack:
                ngr.append(-1)
            else:
                ngr.append(stack[-1])
            stack.append(nums2[i])
        ngr = ngr[::-1]
        val_to_id = {}
        for i,val in enumerate(nums2):
            val_to_id[val] = i
        ans = []
        for val in nums1:
            ans.append(ngr[val_to_id[val]])
        return ans 
```
