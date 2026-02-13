# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: R.DEEPIKA
RegisterNumber: 212225230046
'''
import numpy as np
def qr_decomposition(A):
    A=np.array(A,dtype=float)
    m,n = A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A=np.array(eval(input()))
Q,R=qr_decomposition(A)
print("The Q Matrix is")
print("",Q)
print("The R Matrix is")
print("",R)


```

## Output

<img width="1666" height="840" alt="Screenshot 2026-02-13 225613" src="https://github.com/user-attachments/assets/6bd46140-46f0-4833-955b-45d3591beef9" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
