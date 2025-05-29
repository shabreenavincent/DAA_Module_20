# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:04.03.2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.
## Algorithm
1. Loop through all possible subset sizes from 0 to n.
2. For each size, generate all combinations (subsets) of that length.
3. Calculate the sum of each subset.
4. If the sum equals the target x, print the subset.
5. Continue checking until all combinations are tested.

## Program:
```
Program to implement Subset sum problem.
Developed by:SHABREENA VINCENT
Register Number: 212222230141
```
```
def subsetSum(arr, n, i,sum, count):
    if(i==n):
        if(sum==0):
            count +=1
        return count
    count = subsetSum(arr,n,i+1,sum-arr[i],count)
    count = subsetSum(arr,n,i+1,sum,count)    
    return count

arr=[]
size=int(input())
for j in range(size):
    value=int(input())
    arr.append(value)
sum = int(input())
n = len(arr)
 
print(subsetSum(arr, n, 0, sum, 0))
```
## Output:
![image](https://github.com/user-attachments/assets/2918d79d-0854-4d51-87e1-be79b0245a8d)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
