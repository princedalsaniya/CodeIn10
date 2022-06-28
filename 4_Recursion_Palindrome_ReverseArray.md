# Palindrome checking using Recursion

## Palindrome String

Palindrome string are strings which read same from front and back.
>ex. "abcba", "abba"

There are 2 main cases :

1. Length is Odd
2. Length is Even

*****

### Case - 1 (Odd length)

We start from left and right indices stored in `l` and `r`. We will check if both `str[l] == str[r]`. If it is true then we will increase l and decrease r. We will do this until we reach the middle point. Where `l == r`. If anytime it is not same we will return false and we get false as answer.

*****

### Case - 2 (Even Length)

Same as above we will start with `l` and `r`. Increase l and decrease r if `str[l] == str[r]`. But here we will stop when `l > r`. Means l and r crossed each other, we will stop here.

*****

### Code 

```python
def func(s, l, r): 

    if s[l] >= s[r]:
        return true

    if s[l] != s[r]:
        return false

    return func(s, l+1, r-1)
```

*****

## Reverse the Array

*****

We will have an list `ans`. When we will start with index 0 it will ask to get index 1 and then it will add itself to `ans`. While index 1 would ask for index 2, and 1 will add itself to the `ans`. This way we will reach the end of the array, he will say I am the last, I am returning `ans` by adding itself. In return all the indices will be added and the array would be reversed.

*****

### Visualization

```python
arr = [2,4,5,7]

index 0                         ans = [7,5,4,2]
  |                              ^
  |                              |
  -> index 1                    ans = [7,5,4]
        |                        ^
        |                        |
         -> index 2             ans = [7,5]
              |                  ^
              |                  |
               -> index 3       ans = [7]
```

*****

### Code

```python
def func(arr, ans, i):
    
    ## i = currunt index.

    if i == len(arr)-1 :
        ans += ans.append(arr[i])
        return ans
    
    return func(arr, ans, i+1).append(arr[i])
```
