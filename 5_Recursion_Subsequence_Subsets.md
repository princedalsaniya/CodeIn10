# Subsequence or Subarray using Recursion

- Subsequenece is a sequence which can be derived by removing 0 or more elements, without changing the original order of the string. If the string is `abcd` then `abd`, `acd`, `ab` can be subsequence.
- If we have string, then this would be `subsequence` and if we have array or set, then this would be `subarray`.

- Subsequence is kind of superset of `substring` or `subarray`.
- **Substring / Subarray** :
  - This is the portion of the original string/array where we haven't removed any element from between.
  - We just took out any portion without breaking it and that would be it.
  - If the string is `abcd` then [`a`, `b`, `c`, `d`, `ab`, `bc`, `cd`, `abc`, `bcd`] would be our substrings.
  - As you can see here we haven't included `ac` or `bd` or `ad` anything becasue they are missing some elements in between.
  - This was the main difference in Substring and Subsequence.

## Applying Recursion

- So, we have 2 choices in every element of string. Either include it in the result or don't.
- We will start from index 0, there are 2 possibilities, Include and exclude the currunt element.
  - Increase the index by 1. We will again have 2 choices.
  - This way we will reach the last index and print the answers. This would be out base case.

## Code

```python
heper(s, tempAns, ind):
    ## base case
    if len(s) == ind :
        print(tempAns, " ")
    
    ## include current element
    helper(s, tempAns+s[index], index+1)

    ## don't include current element
    helper(s, tempAns, index+1)

## main calling function
print(helper(s, "", 0))
```
