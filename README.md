# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1. Input the number of unknowns n and the augmented matrix of the system of equations.

2. Convert the matrix into an upper triangular form using forward elimination.

3. Apply back substitution to compute the values of the unknown variables.

4. Display the solution vector and stop the program.
````

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: V G SAIRAIMA
RegisterNumber: 212225040359
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

for i in range(n):
    if a[i][i]==0.0:
        sys.exit("Divide by 0 detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
print(f"X0 = {x[0]:.2f} X1 = {x[1]:.2f} X2 = {x[2]:.2f}")

```

## Output:
![image](https://github.com/VGSAIRAIMA/Gaussian/blob/main/Screenshot%202026-03-22%20162705.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

