# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
step 1- Import numpy library using import statement.
step 2- Import sys library
step 3- Create a variable n to recieve to recieve dimention of the matrix.
step 4- using input n,create a zero matrix 'a' of x(n+1) and a zero row matrix 'x' of n using np.zeros.
step 5- Initiate 1st nested for loop to get values from user and store it in the 'a' matrix using float(input).
step 6- Initiate 2nd nested for loop to apply gaussian elimination.
step 7- Initiate 3rd nested for loop to calculate the solution of the 'a' matrix using back substitution.
step 8- Display the solution for each variable upto 2 decimals using for loop and printO with '%" operator. 
```

## Program:
```

Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Subha shree U
RegisterNumber: 2305002025


import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
        
for i in range(n):
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i]-a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```

## Output:
![image](https://github.com/subha2406/Gaussian/assets/155226504/90d2fafa-e797-437a-8d0f-08f1909690d0)
![image](https://github.com/subha2406/Gaussian/assets/155226504/f2c3b136-071e-4f31-a402-1cef7227a1f1)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

