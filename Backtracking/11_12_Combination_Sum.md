# Combination Sum (ProblemSolving)

## Problem Statement

- We are given an array of `candidates` and `target`.
- We need to find the pairs from `candidates` which add up to `target`.
- Same number can be chosen unlimited times from candidates.
- 2 combinations are unique if frequency of any one of the number is different.
- Example : 
  - (candidates) `arr = [2,3,6,7,]`
  - `target = 7`

*****

### Implementation

*****

- We will track the currSum.
- If the currSum is greater than target then condition is violeted and we will backtrack.
- If the currSum is equal to target then the condition is met, we will add this to possible solution and we will backtrack.

*****

### Visualization 1

*****

(i, CA, CS) = (currunt index, currunt tempAnswer, currunt sum)

```js
[2, 3, 6, 7] and target = 7

(0,[2],2) -> (0,[2,2],4) -> (0,[2,2,2],6) -> (0,[2,2,2,2],8)
    |              |                |------<---------|
    |              |                |
    |              |        (1,[2,2,2,3],9)
    |              |------<---------|
    |              |
    |        (1,[2,2,3],7)                                  ------------------>  ANS
    |----<---------|
    
(1,[3],3) -> (1,[3,3],6) -> (1,[3,3,3],9)
    |            |------<---------|
    |            |
    |        (2,[3,3,6],12)
    |------<-----|
    
(2,[6],6) -> (2,[6,6],12)
    |-------<-----|
    
(3,[7],7)                                                   ------------------>  ANS
```

*****

Code

*****

```python
def helper(candidates, target, i, currSum, temp):
    ## BOUNDING CONDITION
    if currSum > target: 
        return

    ## BASE CASE
    if i == len(candidates):
        if currSum == target:
            print(temp)
        return

    ## INCLUSION
    currSum += candidates[i]
    temp.append(candidates[i])
    helper(candidates, target, i, currSum, temp)

    ## EXCLUSION
    currSum -= candidates[i]
    temp.pop()
    helper(candidates, target, i+1, currSum, temp)

candidates = [2,3,6,7]
target = 7
temp = []
helper(candidates, target, 0, 0, temp)
```
