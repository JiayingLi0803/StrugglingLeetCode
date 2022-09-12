# Description
Given two strings ransomNote and magazine, return true if ransomNote can be constructed by using the letters from magazine and false otherwise.

Each letter in magazine can only be used once in ransomNote.

**Example 1:**
```
Input: ransomNote = "a", magazine = "b"
Output: false
```
**Example 2:**
```
Input: ransomNote = "aa", magazine = "ab"
Output: false
```
**Example 3:**
```
Input: ransomNote = "aa", magazine = "aab"
Output: true
```
**Constraints:**
```
1 <= ransomNote.length, magazine.length <= 10**5
ransomNote and magazine consist of lowercase English letters.
```
# Solution
**Approach 1: Two Hash Tables**
```ruby
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        if len(ransomNote)>len(magazine):
            return False
        ransomCount = collections.Counter(ransomNote)
        magazineCount = collections.Counter(magazine)
        
        for key, rValue in ransomCount.items():
            mValue  = magazineCount[key]
            if rValue > mValue:
                return False
        return True
```
**Approach 2: One Hash Table**
```ruby
def canConstruct(self, ransomNote: str, magazine: str) -> bool:
    
    # Check for obvious fail case.
    if len(ransomNote) > len(magazine): return False

    # In Python, we can use the Counter class. It does all the work that the
    # makeCountsMap(...) function in our pseudocode did!
    letters = collections.Counter(magazine)
    
    # For each character, c, in the ransom note:
    for c in ransomNote:
        # If there are none of c left, return False.
        if letters[c] <= 0:
            return False
        # Remove one of c from the Counter.
        letters[c] -= 1
    # If we got this far, we can successfully build the note.
    return True
```
**Approach 3: Sorting and Stacks**
```ruby
def canConstruct(self, ransomNote: str, magazine: str) -> bool:
    
    # Check for obvious fail case.
    if len(ransomNote) > len(magazine): return False
    
    # Reverse sort the note and magazine. In Python, we simply 
    # treat a list as a stack.
    ransomNote = sorted(ransomNote, reverse=True) 
    magazine = sorted(magazine, reverse=True)
    
    # While there are letters left on both stacks:
    while ransomNote and magazine:
        # If the tops are the same, pop both because we have found a match.
        if ransomNote[-1] == magazine[-1]:
            ransomNote.pop()
            magazine.pop()
        # If magazine's top is earlier in the alphabet, we should remove that 
        # character of magazine as we definitely won't need that letter.
        elif magazine[-1] < ransomNote[-1]:
            magazine.pop()
        # Otherwise, it's impossible for top of ransomNote to be in magazine.
        else:
            return False   
    # Return true iff the entire ransomNote was built.
    return not ransomNote
```
