# EX 5A Minimum Cost Path

### DATE: 01/05/2025

## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.

## Algorithm

1. Take input for number of rows R and columns C.
2. Import the sys module for using maximum integer value.
3. Define a function minCost(cost, m, n) to compute the minimum cost to reach cell (m, n).
4. Check if m or n is less than 0 and return sys.maxsize to indicate invalid move.
5. Check if both m and n are 0 and return the value at cost[0][0] as it is the starting point.
6. Recursively return the sum of cost[m][n] and the minimum of three recursive calls: minCost(cost, m-1, n-1), minCost(cost, m-1, n), and minCost(cost, m, n-1).
7. Define a helper function min(x, y, z) that returns the minimum among the three input values.
8. Create a cost matrix with predefined values.
9. Call the minCost function with parameters (cost, R-1, C-1).
10. Print the result returned by the function.

## Program:

```
# A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

R = int(input())
C = int(input())
import sys
def minCost(cost, m, n):
    if (n < 0 or m < 0):
        return sys.maxsize
    elif (m == 0 and n == 0):
        return cost[m][n]
    else:
        return cost[m][n] + min( minCost(cost, m-1, n-1),
                                minCost(cost, m-1, n),
                                minCost(cost, m, n-1) )
def min(x, y, z):
    if (x < y):
        return x if (x < z) else z
    else:
        return y if (y < z) else z
cost= [ [1, 2, 3],
        [4, 8, 2],
        [1, 5, 3] ]
print(minCost(cost, R-1, C-1))
```
## Output:

![image](https://github.com/user-attachments/assets/4391b23c-add8-4878-8bd9-53afd3eb61f7)

## Result:
Thus the above program was executed successfully for finding the minimum cost.
