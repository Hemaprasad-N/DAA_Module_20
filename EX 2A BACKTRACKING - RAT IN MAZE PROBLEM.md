# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Initialize a solution matrix sol of the same size as the maze, filled with zeros.
2.Start from cell (0, 0) and attempt to reach the destination cell (N-1, N-1).
3.Check if the current cell is safe (i.e., within bounds and not blocked). If safe, mark it as part of the path.
4.Recursively move either right or down, trying to find a path to the goal. If neither move works, backtrack by unmarking the current cell.
5.If a path is found, print the solution matrix; otherwise, print that no solution exists.

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: HEMAPRASAD N
Register Number: 212222040054
*/
```
```
def is_safe(maze, x, y, n):
    return 0 <= x < n and 0 <= y < n and maze[x][y] == 1

def solve_maze(maze, x, y, sol, n):
    if x == n - 1 and y == n - 1:  # Reached the destination
        sol[x][y] = 1
        return True
    
    if is_safe(maze, x, y, n):
        sol[x][y] = 1
        
        # Move right
        if solve_maze(maze, x, y + 1, sol, n):
            return True
        
        # Move down
        if solve_maze(maze, x + 1, y, sol, n):
            return True
        
        # Backtrack if no path is found
        sol[x][y] = 0
    
    return False

def rat_in_maze(maze, n):
    sol = [[0 for _ in range(n)] for _ in range(n)]
    if solve_maze(maze, 0, 0, sol, n):
        return sol
    else:
        return [[0] * n for _ in range(n)]  # No path found

# Example input
n = 4
maze = [[1, 0, 0, 0],
        [1, 1, 0, 1],
        [0, 1, 0, 0],
        [1, 1, 1, 1]]

solution = rat_in_maze(maze, n)
for row in solution:
    print(" ".join(map(str, row)))
```

## Output:
![image](https://github.com/user-attachments/assets/f2a6a8c9-1ca0-4587-81b1-bc5ffb244244)



## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
