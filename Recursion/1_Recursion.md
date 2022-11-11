# Recursion

Recursion has only 3 main steps to keep in mind.

>1. BaseCase
>2. Small Calculation
>3. Recursive Call

Let's take an example for this. The question is that you need to find the sum of **1 to n**.
So, we can break this problem into small task. Like,

- 10 will say that, give me sum of 9, I will add 10 and give result.
- 9 will say that, give me sum of 8, I will add 9 and give result.
- ...
- 1 will say that I don't need anyone, so I am passing result 1.
- 2 will get 1, add itself and pass result 3.
- 3 will get 3, add itself and pass result 6.
- ...
- 10 will get 45, add itself and pass result 55.

-------

> `f(n) = f(n-1) + n`
>
>This is the final resursive representation of this problem.

-----------

### Code For this Problem

```python
def nSum(n):
  ## Base Case
  if n==1: 
    return 1
 
  ## Recursive Call
  prevSum = nSum(n-1)
 
  ## Small Calc
  ans = n + prevSum
 
  return ans

print(nSum(5))
```
