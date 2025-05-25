# EX:5D - Minimum Jump to Reach End Array

### DATE: 01/05/2025

## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.

## Algorithm

1. Define minJumps(arr, n) to find the minimum jumps to reach the end of the array.
2. Initialize a list jumps of size n with all 0s.
3. Return infinity if n == 0 or arr[0] == 0 (cannot move).
4. Set jumps[0] = 0 since no jump is needed at the start.
5. Loop from index 1 to n - 1.
6. For each index i, set jumps[i] = infinity.
7. Check all previous indices j to see if i is reachable from j.
8. If reachable and jumps[j] is not infinity, update jumps[i] = jumps[j] + 1 and break.
9. Return jumps[n - 1] as the result.
10. Read input values, call the function, and print the minimum number of jumps.

## Program:
```
# To implement the program to finding the minimum number of jumps needed to reach end of the array.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

def minJumps(arr, n):
    jumps = [0 for i in range(n)]
    if (n == 0) or (arr[0] == 0):
        return float('inf')
    jumps[0] = 0
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if (i <= j + arr[j]) and (jumps[j] != float('inf')):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    return jumps[n-1]
arr = []
n = int(input()) #len(arr)
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr,n))
 
```
## Output:

![image](https://github.com/user-attachments/assets/bf6472b3-4266-493e-ae04-45145700ab5f)

## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
