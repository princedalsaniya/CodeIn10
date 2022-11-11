# Subset Sum Problem

## Problem Definition

- We are given an array of n non-negative integers, and a value `SUM`, we need find if there is any subset whose sum is equal to given `SUM`.

## Applying Recursion

- So, we have 2 choices in every element of string. Either include it in the sum or don't.
- We will start from index 0, there are 2 possibilities, Include and exclude the currunt element into sum.
  - Increase the index by 1. We will again have 2 choices.
  - Here we will also check if the sum is greater than required sum.
    - If the sum is greater, then there is no point in checking furthur.
    - If sum is lower than required sum, then we will continue our search.
  - Whenever we hit the sum == requiredSum we will return `true`.

## Code

```python
def helper(arr, reqSum, tempSum, index):
    if reqSum == tempSum:
        return True
    if reqSum < tempSum:
        return False
    if index >= len(arr):
        return False
    
    ## include current element
    recCall1 = helper(arr, reqSum, tempSum + arr[index], index+1)
    ## don't include current element
    recCall2 = helper(arr, reqSum, tempSum, index+1)

    return recCall1 or recCall2

arr = [3, 34, 4, 12, 5, 2]
reqSum = 9
## main calling function
print(helper(arr, reqSum, 0, 0))
```
