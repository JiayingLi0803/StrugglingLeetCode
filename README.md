# StrugglingLeetCode

## Strings
### Sliding Windows

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

Longest Substring Without Repeating Characters 
