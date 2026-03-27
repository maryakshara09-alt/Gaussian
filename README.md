# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Import required modules (numpy and sys) and read the number of variables n.

Step 2: Create an augmented matrix a of size n × (n+1) and input all coefficients and constants.

Step 3: Apply forward elimination to convert the matrix into upper triangular form (eliminate lower elements using row operations).

Step 4: Perform back substitution to calculate the values of unknowns x[i].

Step 5: Display the solutions of variables.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: MARY AKSHARA S
RegisterNumber:212225230169 
*/
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int (input ())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1 ):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end=" ")
    ```

## Output:
<img width="1914" height="1079" alt="Screenshot 2026-03-27 183149" src="https://github.com/user-attachments/assets/31c265f2-29fe-43d2-ac07-62575cf8ea2d" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

