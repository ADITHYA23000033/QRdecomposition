# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
	
     ![image](https://github.com/ADITHYA23000033/QRdecomposition/assets/148514544/336dbce0-915c-4177-8790-89660652146f)


3.	Obtain the Q matrix   
     ![image](https://github.com/ADITHYA23000033/QRdecomposition/assets/148514544/0283e7f4-69f7-46a7-b13d-8a14ce0678ba)

4.	Construct the upper triangular matrix R
     ![image](https://github.com/ADITHYA23000033/QRdecomposition/assets/148514544/ac2c8ef0-0e19-456e-98c4-ffb379d75e94)


## Program:

### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: ADITHYA V
RegisterNumber: 23000033
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    
    Q=np.empty((n,n))
    u=np.empty((n,n))
    
    u[:, 0]=A[:, 0]
    Q[:, 0]=u[:, 0] / np.linalg.norm(u[:, 0])
    
    for i in range(1,n):
        
        u[:, i]=A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j])*Q[:, j]
        
        Q[:, i]=u[:, i] / np.linalg.norm(u[:, i])
    
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i, j]=A[:, j] @ Q[:, i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)


```

## Output

![image](https://github.com/ADITHYA23000033/QRdecomposition/assets/148514544/56c98b46-bfdd-41af-94c8-309cd0c396be)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
