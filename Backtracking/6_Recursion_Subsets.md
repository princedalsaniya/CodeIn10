# Subsets

- Subset means we can take or not take any element from array/set and whatever becomes that is subsets.
- All of these `subsets` and `subarray` problems can be done by `DP(dynamic programming)`. In that solution time-complexity decerases deastically.
- There are 2<sup>n</sup> number of subsets for a given array of `n` elements.

## Applying Recursion

- So, we have 2 choices in every element of string. Either include it in the result or don't.
- We will start from index 0, there are 2 possibilities, Include and exclude the currunt element.
  - Increase the index by 1. We will again have 2 choices.
  - This way we will reach the last index and print the answers. This would be out base case.

## Code

```python
def helper(arr, tempAns, ind):
    ## base case
    if len(arr) == ind :
        print(tempAns, " ")
    
    ## include current element
    helper(arr, tempAns+arr[index], index+1)

    ## don't include current element
    helper(arr, tempAns, index+1)

arr = [1,2,4]
## main calling function
print(helper(arr, "", 0))
```
