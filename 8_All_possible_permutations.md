# Permutations

Let's understand `permutations` first.

- Suppose we have 3 elements and we want to find all possible permutations of that.
- We will see it as a sofa with 3 seats. And we also have 3 persons(elements) = [A, B, C].
- We can make them sit in many different ways. And those will be our permutations.
- In first seat we have 3 people, second seat we will have 2 people, third seat 1 people.
- We can multiply all of that and that would be number of all possible permutations.
- Here answer would be `3 X 2 X 1 = 6` and that is also known as `3!`.

*****

## Method 1

*****

### Visualization 1

```js
                    [1,2,3]
        _______________|_______________            
       |               |               |
    [1 _ _]         [2 _ _]         [3 _ _]
    ___|___         ___|___         ___|___
   |       |       |       |       |       |
[1 2 _] [1 3 _] [2 1 _] [2 3 _] [3 1 _] [3 2 _]
   |       |       |       |       |       |
[1 2 3] [1 3 2] [2 1 3] [2 3 1] [3 1 2] [3 2 1]
```

### Explanation 1

- Here we have used the similar login to inclusion and exclusion.
- This method is called `Counting Array`. In this we have to maintain one extra array.
- This is a bit constly on space complexity. There is one more logic for this.

*****

## Method 2

*****

### Visualization 2

```js
                    [1,2,3]
        _______________|_______________            
       |               |               |
    [1 2 3]         [2 1 3]         [3 1 2]
    ___|___         ___|___         ___|___
   |       |       |       |       |       |
[1 2 3] [1 3 2] [2 1 3] [2 3 1] [3 1 2] [3 2 1]
```

### Explanation 2

- Here we are doing this problem by swapping the elements and not creating the new array.
- This way this won't be costly in space complexity.
- We have 2 choices at each element either swap that with immidiate right or not.
- This is called `Backtracking` approach.

### Code 2

```python
ans = list()

def helper(nums, i):
    if i == len(nums):
        return ans.append(nums)
    for j in range(i, len(nums)):
        nums[i], nums[j] = nums[j], nums[i]
        helper(nums, i+1)
        ## Backtracking
        nums[i], nums[j] = nums[j], nums[i]
    return

nums = [1,2,3]
helper(nums, 0)
print(ans)
```