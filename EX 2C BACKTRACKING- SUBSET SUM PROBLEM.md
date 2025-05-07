# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Input the array a: Read the number of elements and then read the elements into list a.
2.Input the target sum that needs to be achieved by any subset of a.
3.Define a recursive function SubsetSum() to check whether the target sum can be achieved.
4.At each step, either include the current element in the sum or exclude it, and move to the next element.
5.Print "True, subset found" if a subset exists that matches the target; otherwise, print "False, subset not found".
## Program:
```
/*
Program to implement Subset sum problem.
Developed by: HEMAPRASAD N
Register Number: 212222040054
*/
```
```
def SubsetSum(a,i,sum,target,n):
# Write your code here
    if i==n:
        return sum==target
    if sum>target:
        return False
    if sum==target:
        return True
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)


a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")


```
## Output:
![image](https://github.com/user-attachments/assets/b0b5bbd1-6706-406b-9e32-39b3b8d304fa)



## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
