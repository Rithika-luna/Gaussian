# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1: 
Start the program.

### Step 2:
Import the NumPy library using import numpy as np.

### Step 3: 
Define the coefficient matrix and the constant matrix using the np.array() function.

### Step 4:
Apply Gaussian Elimination to convert the augmented matrix into an upper triangular matrix using forward elimination.

### Step 5:
Use back substitution to find the values of the unknown variables.

### Step 6: 
Display the solution of the given system of linear equations.

### Step 7:
Stop the program. 

## Program:
```
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"
import numpy as np
import sys

n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected! ')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio*a[i][k]

x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i]= x[i]-a[i][j]*x[j]
    x[i]= x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')
        

```

## Output:

<img width="1432" height="827" alt="image" src="https://github.com/user-attachments/assets/767d567f-d3a6-425d-b0d8-80c3830396c7" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

