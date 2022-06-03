# Count ways to Reach Nth Stair Problem

In this video we haven't learned anything new. But we learnt how to implement recursion in problem.

*****

**Problem Statement**: Person can jump only 1step or 2step at a time. Find out in how many ways person can reach the Nth stair.

```python
n=1
1 way.                                            
                                                    .__
[1]                                                 |
```

```python
n=2
2 ways.                                             .__
                                                 .__|
[1,1], [2]                                       |
```

```python
n=3                                                 .__
3 ways.                                          .__|
                                              .__|
[1,1,1], [1,2], [2,1]                         |
```

```python
n=4                                                 .__
5 ways.                                          .__|
                                              .__|
[1,1,1,1],                                 .__|
[1,1,2], [1,2,1], [2,1,1]                  |
[2,2]
```

*****

From this we can clearly see that it is same as the **Fibonacci Series**. Answer would be sum of previous 2.

But the only difference here is of **Base Case**. There base case was of `n=1,0`. But here we have base case for `n=1,2`.

> f(n) = f(n-1) + f(n-2)
>
> This is the recursive expression for this problem.

*****

## Code

```python
func(n):
    ## Base Case
    if n==1 or n==2:
        return n
    
    ## Recursive Call
    recCall1, recCall2 = func(n-1), func(n-2)

    ## Small Calculation
    smallCalc = recCall1 + recCall2

    return smallCalc
```
