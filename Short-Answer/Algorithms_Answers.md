#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

### a) O(n)
- Despite the size of the input, it will always grow at the same rate because `a` is iterating over the input by `n * n` each time.


### b) O(log n)
- Since `j` doubles each time in the loop until it reaches `n`, it is considering logarithmic.


### c) O(n)
- The function is called `n` times, so it would be linear. For example, an input of 4 would just be called four times as `n` decreases by one each time.

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.

- Drop the egg from the middle floor
- If the egg breaks, find the next midpoint below and drop the egg from there
- If the egg doesn't break, do the same thing but above
- Keep going until `n` can't be divided anymore - if the egg breaks at that point, the answer is the floor directly underneath. If it doesn't break, the answer is the floor you're on
- Runtime complexity would be O(log n)
```
length = len(n)
mid = length // 2
f = mid

while length > 1:
    throw egg from mid
    if egg == broken:
        f = mid - 1
        mid = len(n[:mid]) / 2
    else:
        f = mid
        mid = len(n[mid + 1]) / 2
```