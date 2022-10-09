Welcome to the StrugglingLeetCode Page!

# Integers
## Basic Math

[Problem 119: Pascal's Triangle II (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Pascal's%20Triangle%20II.md)

[Problem 231: Power of Two (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Power%20of%20Two.md)

[Problem 263: Ugly Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Ugly%20Number.md)

[Problem 342: Power of Four (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Power%20of%20Four.md)

[Problem 492: Construct the Rectangle (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Construct%20the%20Rectangle.md)

## Bit Operations

[Problem 191: Number of 1 Bits (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Number%20of%201%20Bits.md)

[Problem 461: Hamming Distance (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Hamming%20Distance.md)

[Problem 476: Number Complement (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Number%20Complement.md)

---

# Strings

## Basic Operations
**Problem**

[Problem 157: Read N Characters Given Read4 (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Read%20N%20Characters%20Given%20Read4.md)

[Problem 389: Find the Difference (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Find%20the%20Difference.md)

[Problem 408: Valid Word Abbreviation (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Word%20Abbreviation.md)

[Problem 485: Max Consecutive Ones (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Max%20Consecutive%20Ones.md)

## Reverse Strings

**Key Idea**

```ruby
s = s[::-1]
```

**Problems**

[Problem 7: Reverse Integer (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Reverse%20Integer.md)

[Problem 9: Palindrome Number (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Palindrome%20Number.md)

[Problem 246: Strobogrammatic Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Two%20Sum.md)

## Splitting Strings

**Problems**

[Problem 58: Length of Last Word (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Length%20of%20Last%20Word.md)

[Problem 434: Number of Segments in a String (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Number%20of%20Segments%20in%20a%20String.md)

## Judging Characters & Punctuations

**Problems**

[Problem 125: Valid Palindrome (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Palindrome.md)

## Searching and Finding

**Problems**

[Problem 1: Two Sum (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Two%20Sum.md)

[Problem 28: Implement strStr() (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Implement%20strStr().md)

[Problem 205: Isomorphic Strings (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Isomorphic%20Strings.md)

[Problem 242: Valid Anagram (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Anagram.md)

[Problem 243: Shortest Word Distance (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Shortest%20Word%20Distance.md)

[Problem 268: Missing Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Missing%20Number.md)

[Problem 290: Word Pattern (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Word%20Pattern.md)

## Shuffling Order

**Problems**

[Problem 869: Reordered Power of 2 (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Reordered%20Power%20of%202.md)

## Converting Base Systems
**Key Idea**
```ruby
def toBinary(num):
    reverse_ans = ""
    if num == 0:
        return "0"
    while num>0:
        x = num%2
        reverse_ans += str(x)
        num = num//2
    return reverse_ans[::-1]
```
**Problems**

[Porblem 67: Add Binary (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Add%20Binary.md)

[Problem 168: Excel Sheet Column Title (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Excel%20Sheet%20Column%20Title.md)

[Problem 171: Excel Sheet Column Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Excel%20Sheet%20Column%20Number.md)

## Sliding Windows

**Key Idea**

```ruby
left, right = 0, 0
win = []
while right < len(s):
  win.append(s[right])
  right += 1
  while isValid(win):
    win.pop(0)
    left += 1
```

**Problems**

[Problem 03: Longest Substring Without Repeating Characters (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Longest%20Substring%20Without%20Repeating%20Characters.md)

[Problem 482: License Key Formatting (Easy))](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/License%20Key%20Formatting.md)

## ord()
**Problems**

[Problem 415: Add Strings (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Add%20Strings.md)

---

# Lists
## Basic Operations
**Problems**

[Problem 27: Remove Element (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Remove%20Element.md)

[Problem 61: Plus One (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Plus%20One.md)

[Problem 121: Best Time to Buy and Sell Stock (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Best%20Time%20to%20Buy%20and%20Sell%20Stock.md)

[Problem 163: Missing Ranges (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Missing%20Ranges.md)

[Problem 217: Contains Duplicate (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Contains%20Duplicat.md)

[Problem 252: Meeting Rooms (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Meeting%20Rooms.md)

[Problem 338: Counting Bits (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Counting%20Bits.md)

[Problem 412: Fizz Buzz (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Fizz%20Buzz.md)

[Problem 414: Third Maximum Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Third%20Maximum%20Number.md)

[Problem 495: Teemo Attacking (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Teemo%20Attacking.md)

## List Matrices
**Problems**

[Problem 48: Rotate Image (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Rotate%20Image.md)

[Problem 118: Pascal's Triangle (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Pascal's%20Triangle.md)

[Problem 422: Valid Word Square (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Word%20Square.md)

[Problem 1329: Sort the Matrix Diagonally (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Sort%20the%20Matrix%20Diagonally.md)

## Recursion
**Problems**

[Problem 22: Generate Parentheses (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Generate%20Parentheses.md)

[Problem 70: Climbing Stairs (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Climbing%20Stairs.md)

[Problem 429: N-ary Tree Level Order Traversal (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/N-ary%20Tree%20Level%20Order%20Traversal.md)

[Problem 967: Numbers With Same Consecutive Differences (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Numbers%20With%20Same%20Consecutive%20Differences.md)

[Problem 987: Vertical Order Traversal of a Binary Tree (Hard)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Vertical%20Order%20Traversal%20of%20a%20Binary%20Tree.md)

---

# Sets
## Basic Operations
**Problems**

[Problem 202: Happy Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Happy%20Number.md)

[Problem 349: Intersection of Two Arrays (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Intersection%20of%20Two%20Arrays.md)

## issubset()
**Problems**

[Problem 500: Keyboard Row (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Keyboard%20Row.md)

---

# Stacks
**Basic Idea: Last-In/First-Out (LIFO)**
```ruby
top() / peek() #Returns a reference to the topmost element of the stack – Time Complexity: O(1)
push(a)        #Inserts the element ‘a’ at the top of the stack – Time Complexity: O(1)
pop()          #Deletes the topmost element of the stack – Time Complexity: O(1)
```
**Problems**

[Problem 20: Valid Parentheses (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Parentheses.md)

[Problem 496: Next Greater Element I (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Next%20Greater%20Element%20I.md)

---

# Queue
**Problems**

[Problem 346: Moving Average from Data Stream (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Moving%20Average%20from%20Data%20Stream.md)

---

# Hash Table
**Problems**

[Problem 136: Single Number](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Single%20Number.md)

[Problem 160: Intersection of Two Linked List (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Intersection%20of%20Two%20Linked%20Lists.md)

[Problem 219: Contains Duplicate II (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Contains%20Duplicate%20II.md)

[Problem 359: Logger Rate Limiter (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Logger%20Rate%20Limiter.md)

[Problem 383: Ransom Note (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Ransom%20Note.md)

[Problem 387: First Unique Character in a String (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/First%20Unique%20Character%20in%20a%20String.md)

[Problem 509: Fibonacci Number (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Fibonacci%20Number.md)

---

# Trees
**Problems**

[Problem 100: Same Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Same%20Tree.md)

[Problem 101: Symmetric Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Symmetric%20Tree.md)

[Problem 104: Maximum Depth Binary Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Maximum%20Depth%20of%20Binary%20Tree.md)

[Problem 108: Convert Sorted Array to Binary Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Convert%20Sorted%20Array%20to%20Binary%20Search%20Tree.md)

[Problem 110: Balanced Binary Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Balanced%20Binary%20Tree.md)

[Problem 111: Minimum Depth Binary Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Minimum%20Depth%20of%20Binary%20Tree.md)

[Problem 112: Path Sum (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Path%20Sum.md)

[Problem 144: Binary Tree Preorder Traversal (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Binary%20Tree%20Preorder%20Traversal.md)

[Problem 145: Binary Tree Postorder Traversal (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Binary%20Tree%20Postorder%20Traversal.md)

[Problem 257: Binary Tree Path (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Binary%20Tree%20Paths.md)

---

# Searching
## Binary Searching
**Key Idea**
```ruby
def find_index(elements, value, key):
    left, right = 0, len(elements) - 1

    while left <= right:
        middle = (left + right)//2
        middle_element = key(elements[middle])

        if middle_element == value:
            return middle
        if middle_element < value:
            left = middle + 1
        elif middle_element > value:
            right = middle - 1
```

**Problems**

[Problem 4: Median of Two Sorted Arrays (Hard)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Median%20of%20Two%20Sorted%20Arrays.md)

[Problem 35: Search Insert Position (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Search%20Insert%20Position.md)

[Problem 69: Sqrt(x) (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Sqrt(x).md)

[Problem 367: Valid Perfect Square (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Perfect%20Square.md)

[Problem 441: Arranging Coins (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Arranging%20Coins.md)

## Two Pointers
**Key Idea**

```ruby
while i < j:
    # Do something
    i += 1
    j -= 1
```
[Problem 5: Longest Palindromic Substring (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Longest%20Palindromic%20Substring.md)

[Problem 11: Container With Most Water (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Container%20With%20Most%20Water.md)

[Problem 15: 3Sum (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/3Sum.md)

[Problem 16: 3Sum Closest (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/3Sum%20Closest.md)

[Problem 18: 4Sum (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/4Sum.md)

[Problem 26: Remove Duplicates from Sorted Array (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Remove%20Duplicates%20from%20Sorted%20Array.md)

[Problem 278: First Bad Version (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/First%20Bad%20Version.md)

[Problem 344: Reverse String (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Reverse%20String.md)

[Problem 345: Reverse Vowels of a String (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Reverse%20Vowels%20of%20a%20String.md)

[Problem 374: Guess Number Higher or Lower (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Guess%20Number%20Higher%20or%20Lower.md)

[Problem 392: Is Subsequence (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Is%20Subsequence.md)

[Problem 680: Valid Palindrome II (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Valid%20Palindrome%20II.md)

[Problem 704: Binary Search (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Binary%20Search.md)

## BFS (Breadth-First Search)
**Key Idea**

```ruby
def BFS(graph, s):
    queue = []
    queue.append(s)
    seen = set()
    seen.add(s)
    while len(queue) > 0:
        vetex = queue.pop(0)
        nodes = graph[vetex]
        for w in nodes:
            if w not in seen:
                queue.append(w)
                seen.add(w)
        print(vetex)
```
**Problems**

[Problem 39: Combination Sum (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Combination%20Sum.md)

## DFS (Depth-First Search)

**Key Idea**

```ruby
def DFS(graph, s):
    stack = []
    stack.append(s)
    seen = set()
    seen.add(s)
    while len(stack) > 0:
        vetex = stack.pop()
        nodes = graph[vetex]
        for w in nodes:
            if w not in seen:
                stack.append(w)
                seen.add(w)
        print(vetex)
```

[Problem 200: Number of Islands (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Number%20of%20Islands.md)

[Problem 226: Invert Binary Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Invert%20Binary%20Tree.md)

[Problem 404: Sum Left Leaves (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Sum%20of%20Left%20Leaves.md)

---

# Sorting
[Problem 56: Merge Intervals (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Merge%20Intervals.md)

[Problem 88: Merge Sorted Array (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Merge%20Sorted%20Array.md)

[Problem 94: Binary Tree Inorder Traversal (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Binary%20Tree%20Inorder%20Traversal.md)

[Problem 169: Majority Element (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Majority%20Element.md)

[Problem 215: Kth Largest Element in an Array (Hard)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Kth%20Largest%20Element%20in%20an%20Array.md)

[Problem 229: Majority Element II (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Majority%20Element%20II.md)

[Problem 253: Meeting Rooms II (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Meeting%20Rooms%20II.md)

[Problem 637: Average of Levels in Binary Tree (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Average%20of%20Levels%20in%20Binary%20Tree.md)

[Problem 910: Smallest Range II (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Smallest%20Range%20II.md)

---

# Linked List

**Data Structure**

```ruby
# Definition for singly-linked list.
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
```
## Merging
**Problems**

[Problem 2: Add Two Numbers (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Add%20Two%20Numbers.md)

[Problem 21: Merge Two Sorted Lists (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Merge%20Two%20Sorted%20Lists.md)

[Problem 141: Linked List Cycle (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Linked%20List%20Cycle.md)

## Editing
**Problems**

[Problem 19: Remove Nth Node From End of List (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Remove%20Nth%20Node%20From%20End%20of%20List.md)

[Problem 83: Remove Duplicates from Sorted List (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Remove%20Duplicates%20from%20Sorted%20List.md)

[Problem 203: Remove Linked List Elements (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Remove%20Linked%20List%20Elements.md)

[Problem 206: Reverse Linked List (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Reverse%20Linked%20List.md)


[Problem 234: Palindrome Linked List (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Palindrome%20Linked%20List.md)

---

# Divide and Conquer
**Problems**

[Problem 273: Integer to English Words (Hard)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Integer%20to%20English%20Words.md)

---

# Dynamic Programming
**Problems**

[Problem 42: Trapping Rain Water (Hard)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Trapping%20Rain%20Water.md)

[Problem 53: Maximum Subarray (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Maximum%20Subarray.md)

---

# Uncommon Algorithms
## Exponentiation by squaring

**Problems**

[Problem 50: Pow(x, n)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Pow(x%2C%20n).md)

---

# Tricky
**Problems**

[Problem 31: Next Permutation (Medium)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Next%20Permutation.md)

[Problem 258: Add Digits (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Add%20Digits.md)

[Problem 292: Nim Game (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Nim%20Game.md)

[Problem 459: Repeated Substring Pattern (Easy)](https://github.com/JiayingLi0803/StrugglingLeetCode/blob/main/Codes/Repeated%20Substring%20Pattern.md)
