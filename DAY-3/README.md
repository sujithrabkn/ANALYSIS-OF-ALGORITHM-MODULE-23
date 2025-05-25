# EX 5C Kadane's Algorithm

### DATE:

## AIM:
To write a python program to find the maximum contiguous subarray.

## Algorithm

1. Define a function maxSubArraySum(a, size) to find the maximum sum of a contiguous subarray.
2. Initialize max_so_far with the first element of the array a[0].
3. Initialize max_ending_here as 0 to track the sum of the current subarray.
4. Loop through each element of the array from index 0 to size - 1.
5. Add the current element a[i] to max_ending_here.
6. If max_ending_here becomes negative, reset it to 0.
7. If max_so_far is less than max_ending_here, update max_so_far.
8. After completing the loop, return max_so_far as the result.
9. Read the input n for the size of the array.
10. Read n integers and append them to the list a.
11. Call the maxSubArraySum function with a and n, and print the result.
12. 
## Program:
```
# To implement the program to find the maximum contiguous subarray.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

def maxSubArraySum(a,size):
    max_so_far = a[0]
    max_ending_here = 0
    for i in range(0, size):
        max_ending_here = max_ending_here + a[i]
        if max_ending_here < 0:
            max_ending_here = 0
        elif (max_so_far < max_ending_here):
            max_so_far = max_ending_here
              
    return max_so_far
    
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
  
print("Maximum contiguous sum is", maxSubArraySum(a,n))
```
## Output:

![image](https://github.com/user-attachments/assets/f37287c1-e0a1-4911-8d0b-b6089846cef0)

## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray.
