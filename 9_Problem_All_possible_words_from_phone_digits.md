# Possible Words From Phone Digits

## Problem Statement

- We are given an array `a[]` of `N` numbers from `0-9`.
- Which are assiciated with few aplphabets same as the old Nokia phone keypads.
- We need to tell how many words can be typed out that numbers.

### **NumPad**

```js
1 -> []
2 -> [a, b, c]
3 -> [d, e, f]
4 -> [g, h, i]
5 -> [j, k, l]
6 -> [m, n, o]
7 -> [p, q, r, s]
8 -> [t, u, v]
9 -> [w, x, y, z]
```

*****

## Applying Recursion

*****

- We have choices equal to number of characters at the given number.
- Suppose `a = [2,3]`.
- We will start from index 0. We have 3 choices `[a,b,c]`.
  - Now we will choose `a`. Then again we will have 3 choices `[d,e,f]`.
  - Now we will take each of them.
  - If there was an third number then we would made another recursive call for all the choices at the index 1.

*****

## Visualization 1

*****

```js
                       [a,b,c]
         _________________|_________________
        |                 |                 |
       [a]               [b]               [c]
   _____|_____       _____|_____       _____|_____ 
  |           |     |           |     |           |
[a,d] [a,e] [a,f] [b,d] [b,e] [b,f] [c,d] [c,e] [c,f]
```

*****

## Code

*****

```python
keys = ['', '', 'abc', 'def', 'ghi', 'jkl', 'mno', 'pqrs', 'tuv', 'wxyz']
ans = list()

"""
Parameters : 
    a = array which contains number which were pressed.
    temp = temporary string which is making word.
    i = index of the number that we are considering.
    j = index of the character which we are taking 
        for a specific number at index i.
"""
def helper(a, temp, i):
    if i == len(a):
        return ans.append(temp)
    for j in range(len(keys[a[i]])):
        helper(a, n, temp+keys[a[i]][j], i+1)
    return

a = [2,3]
helper(a, '', 0)
print(ans)
```
