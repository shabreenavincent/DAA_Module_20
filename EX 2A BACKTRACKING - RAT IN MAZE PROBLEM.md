# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:25.02.2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.

## Algorithm
1. Start at the top-left corner (0, 0) and mark it as visited.
2. Check if the current position is valid (inside bounds, open path, and unvisited).
3. Recursively explore all four possible directions (up, down, left, right) from the current position.
4. If moving in a direction leads to the destination (n-1, n-1), return True; otherwise, backtrack.
5. If the destination is reached, print the path; otherwise, declare that no solution exists.  

## Program:
```

Program to implement Rat in a Maze.
Developed by:SHABREENA VINCENT
Register Number:212222230141
```
```
N = 4
def printSolution( sol ):
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
def solveMaze( maze ):
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     
# A recursive utility function to solve Maze problem
def solveMazeUtil(maze, x, y, sol):
     
    # if (x, y is goal) return True
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
    if isSafe(maze,x,y)==True:
        sol[x][y]=1
        if solveMazeUtil(maze,x+1,y,sol):
            return True
        if solveMazeUtil(maze,x,y+1,sol):
            return True
        sol[x][y]=0
        return False
    return False
    

if __name__ == "__main__":
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```
## Output:
![image](https://github.com/user-attachments/assets/de51bf82-d49f-435a-b2b2-7fa7bc1685ef)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
