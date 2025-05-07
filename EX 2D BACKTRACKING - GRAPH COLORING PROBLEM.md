# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Create a graph using an adjacency matrix for V vertices.
2.Initialize a color array with 0 (unassigned) for all vertices.
3.Use backtracking to assign colors (1 to m) to each vertex.
4.Ensure no two adjacent vertices have the same color using is_safe().
5.Print the color assignment if successful; else, print "Solution does not exist". 

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: HEMAPRASAD N
Register Number: 212222040054 
*/
```
```
class Graph():
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)]for row in range(vertices)]
 
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True

    def graphColourUtil(self, m, colour, v):
        if v == self.V:
            return True
        for c in range(1, m + 1):
            if self.isSafe(v, colour, c) == True:
                colour[v] = c
                if self.graphColourUtil(m, colour, v + 1) == True:
                    return True
                colour[v] = 0

    def graphColouring(self, m):
        colour = [0] * self.V
        if self.graphColourUtil(m, colour, 0) == None:
            return False
        print ("Solution exist and Following are the assigned colours:")
        for c in colour:
            print (c,end=' ')
        return True
```

## Output:
![image](https://github.com/user-attachments/assets/216d65c2-81ac-40e5-bba8-f465a9b15f11)



## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
