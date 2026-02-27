# Gaussian Elimination
## Devoloped by: CHIDROOP M J
## Registered by: 212225240029
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of unknowns and form the augmented matrix.
2. Perform forward elimination to convert the matrix into upper triangular form.
3. Apply back substitution to find the values of unknowns.
4. Print the computed solutions. 

## Program:
```py
import numpy as np
import sys

n = int(input())

a = np.zeros((n, n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
        
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit('Divide by zero detected')
    for j in range(i+1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
            
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1, n):
        x[i] =x[i] - a[i][j]* x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i, x[i]), end = ' ')
```

## Output:
<img width="1410" height="548" alt="image" src="https://github.com/user-attachments/assets/c59cb4b9-1066-4a8e-9619-0f60581e06f6" />

<img width="590" height="918" alt="image" src="https://github.com/user-attachments/assets/e4090965-16d3-48d6-aa18-46811f60c2bf" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

