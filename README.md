# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy module and sys module to use the built-in functions for calculation. 
2. Read the number of unknowns. Make a numpy array of (n x n+1) size and initialise it to zero for storing augmented matrix. Also, make another numpy array but having n size and initialise it to zero for storing solution vector.
3. Reading augmented matrix coefficients and perform Gaussian elimination without partial pivoting.
4. Perform back substitution.
5. End the program

## Program:
```python
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: V. RAKSHITA
RegisterNumber: 24900032

import numpy as np
import sys

#reading number of unknowns
n = int(input())

#Making numpy array of (n x n+1) size and initialising to zero for storing augmented matrix
a = np.zeros((n,n+1)) #---------

#Making numpy array of n size and initialising to zero for storing solution vector
x = np.zeros(n)

#Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

#Applying Gaussian elimination WITHOUT PARTIAL PIVOTING
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit("Divide by zero detected!!")
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - (ratio * a[i][k])

#Back substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i]/a[i][i]

#Displaying solution
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end = " ")
*/
```

## Output:
![gaussian elimination]()
![GAUSSIAN ELIMINATION](https://github.com/user-attachments/assets/813afc0b-a6d3-4384-84b4-38a97f956550)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

