# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm


1. Put all coefficients and constants into an augmented matrix.
2. Use row operations to make the matrix upper triangular (zeros below the diagonal).
3. Start from the last equation, solve for that variable, then substitute upward to find the others.
4. Collect all values of variables into the solution vector and present the answer.


## Program:



```
/*
Program to find the solution of a matrix using Gaussian Elimination. 
*/
'''
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: MAHALAKSHMI P
RegisterNumber: 25017517
'''

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
   for j in range(n+1):
       a[i][j]=float(input())
    
for i in range(n):
    if a[i][i]==0:
        sys.exit("Divide by zero detected!")
        
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
                 
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')

```



## Output:



<img width="809" height="671" alt="Screenshot 2025-11-27 200534" src="https://github.com/user-attachments/assets/dd24cb25-e1ff-44f3-ba3d-d0461c5b71aa" />
<img width="1048" height="788" alt="Screenshot 2025-11-27 200624" src="https://github.com/user-attachments/assets/04ad9a7c-4201-4d99-951e-1cdb1c3d2692" />
<img width="1193" height="571" alt="Screenshot 2025-11-27 200635" src="https://github.com/user-attachments/assets/bb855031-3334-4545-93bb-203b7c1fddd0" />





## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

