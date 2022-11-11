# What is Backtracking?

- Explore all possibilities, which ever are not relevent just go back from there. See the graph bellow to get more clear idea.
- So, basically same as recursion, But whenever the condition is violated, just don't go ahead return from. No need to check ahead.

*****

## Visualization 1

*****

```js
                     [_ _ _]
         _______________|_______________
        |               |               |
/->  [A _ _]         [B _ _]         [C _ _]  <-\
|    ___|_______________|_______________|___    |
|   |       |       |       |       |       |   |
x[A B _] [A C _] [B A _] [B C _] [C A _] [C B _]x
            |       |       |       |
         [A C B] [B A C] [B C A] [C A B]
```

*****

## Important problems of this topic.

*****

- Combination Sum
- n Qeens
- Rat in the Maze
- Sudoku Solver
