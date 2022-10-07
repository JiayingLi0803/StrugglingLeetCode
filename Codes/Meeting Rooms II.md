# Description
Given an array of meeting time intervals intervals where ``intervals[i] = [start_i, end_i]``, return the minimum number of conference rooms required.

**Example 1:**
```
Input: intervals = [[0,30],[5,10],[15,20]]
Output: 2
```
**Example 2:**
```
Input: intervals = [[7,10],[2,4]]
Output: 1
```
**Constraints:**
```
1 <= intervals.length <= 10**4
0 <= starti < endi <= 10**6
```
# Solution
```ruby
class Solution:
    def minMeetingRooms(self, intervals: List[List[int]]) -> int:
        if not intervals:
            return 0
        
        used_rooms = 0

        start_timings = sorted([i[0] for i in intervals])
        end_timings = sorted(i[1] for i in intervals)
        L = len(intervals)

        end_pointer = 0
        start_pointer = 0

        while start_pointer < L:
            
            if start_timings[start_pointer] >= end_timings[end_pointer]:

                used_rooms -= 1
                end_pointer += 1

            used_rooms += 1    
            start_pointer += 1   

        return used_rooms
```
