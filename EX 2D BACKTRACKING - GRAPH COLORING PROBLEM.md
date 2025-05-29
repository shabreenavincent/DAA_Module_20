# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:08.03.2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.
## Algorithm
1. Start with the first vertex and try assigning each of the m colors to it.
2. For each vertex, check if assigning a color is safe (i.e., no adjacent vertex has the same color).
3. If it’s safe, assign the color and recursively try to color the next vertex.
4. If all vertices are colored without conflicts, print the color assignments.
5. If no valid coloring exists, return false.
## Program:
```

Program to implement Graph Coloring Problem using backtracking.
Developed by:SHABREENA VINCENT
Register Number:212222230141
```
```
class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)] for row in range(vertices)]

    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True

    def graphColouringUtil(self, m, colour, v):
        if v == self.V:
            return True

        for c in range(1, m + 1):
            if self.isSafe(v, colour, c):
                colour[v] = c
                if self.graphColouringUtil(m, colour, v + 1):
                    return True
                colour[v] = 0
        return False

    def graphColouring(self, m):
        colour = [0] * self.V
        if not self.graphColouringUtil(m, colour, 0):
            return False
        return colour

g = Graph(4)
g.graph = [[0, 1, 1, 1], [1, 0, 1, 0], [1, 1, 0, 1], [1, 0, 1, 0]]
m = 3
result = g.graphColouring(m)
if result:
    print("Solution exist and Following are the assigned colours:")
    for c in result:
        print(c, end=" ")
else:
    print("Solution does not exist")
```

## Output:
![image](https://github.com/user-attachments/assets/6f68ed5c-fda7-4c29-beda-5cbec1cf8c31)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
