# Recursion Tree

Basically recursion tree has 2 main types.

1. Linear Tree
2. Multinode Tree

*****

## Linear Tree

*****

**Problem Statement** : You need to find the nth power of 2.

```js
n=4 so the expression would be 2^4.
2^4 = 2 x 2 x 2 x 2
    = 2 x (2^3)
    = 2 x (2 x 2^2)
    = 2 x (2 x (2 x 2^1))
```

This is how we can break down this problem. 

> `f(n) = 2 x f(n-1)`
>
> This would be the final recursive expression of this problem.

### Visualizing this Linear Tree

```js
2^4              = 2x8 = 16
 |_                |
   2^3           = 2x4 = 8
    |_             |
      2^2        = 2x2 = 4
       |_          |
         2^1     = 2
```

#### Code

```python
fun(n):
    if n == 1:
        return 2

    return 2*fun(n-1)
```

*****

## Multi-Node Tree

*****

**Problem Statement** Find nth Fibonacci term.

```js
Fibonacci series : 0, 1, 1, 2, 3, 5, 8, ...

n = 4
FS(4) = FS(3) + FS(2)
      = [FS(2) + FS(1)] + [FS(1) + FS(0)]
      = [ [FS(1) + FS(0)] + FS(1) ] + [FS(1) + FS(0)]
```

This is how we can break down this problem.

> `f(n) = f(n-1) + f(n-2)`
>
> This is the recursive expression of this problem.

Visualizing the Multinode tree.

```js
           f(4)
             |
            / \
           /   \
          /     \
         /       \
        /         \
      f(3)       f(2)
        |          |
       / \         |
      /   \        |
     /     \      / \
  f(2)    f(1) f(1) f(0)
    |     
   / \    
f(1) f(0) 
```

### Code

```python
f(n):
  if n == 0:
    return 0
  if n == 1:
    return 1
    
  return f(n-1) + f(n-2)
```
