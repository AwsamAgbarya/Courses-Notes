---
tags:
  - MachineLearning
  - Programming
---
The following note will have relevant code snippets from some basic machine learning concepts alongside some basic python reminders!
## Python Basics:
**Array initialization:**
```python
# Values
np.zeros(size) #0
np.ones(size) #1
np.full(size,val) #val
np.empty(size) #no value
# Ranges
np.arange(start:end:step) #custom range
np.linspace(startval,endval,size) #linear range
# miscellaneous
np.repeat(container,times,axis)
np.identity(size)/np.eye(size)
```

**Useful numpy functions:**
```python
np.cumsum(arr,axis) #Cumulative sum
np.vstack(a,b) #appends 2 arrays while keeping the objects
np.hstack(a,b) #appends 2 arrays horizontally 
np.argmin/max(a)  #returns index of min/max
np.unique(arr, return_index, return_inverse, return_counts) # counts unique values and returns their index/count
np.expand_dims(arr, axis) #expanding the dimension of an array
np.argwhere(a>c).flatten() #returns indices of non-zero elements
np.where(cond, x,y) #returns elements that match the condition (returns x otherwise y)
np.put(a,indices,values) #replaces indices in a with values
np.hsplit(a,number) #splits array horizontally given a number of elements
pad_shape = (
	(0, 0),  # Add no row at the top and no row at the bottom
	(1, 0),  # Add one column at the left and no column at the right
)
transition = np.pad(arr,pad_shape,constant_values=0) 
```

**Reshaping:**
```python
A.T #flips the axis 
A.transpose(indices) #transposes the arrays axis according to the indices of the original axis
A.reshape(shape) #keeps the data in the same order but changes the dimensions accordingly, You are allowed to use '...' to indicate all previous indexes
A.flatten() #turns the array into one dimensional
A[:,None] #To add a new dimensions (usually for broadcasting)
A[A>c] #filter out all the elements in A that dont apply to the condition
```

**Linear Algebra:**
```python
np.linalg.norm(point1-point2) #Used to calculate euclidean distances or l2 norm
np.linalg.inv(A) #inverse matrix
np.linalg.eig(A) #returns eigen values vectors
np.linalg.eigh(A) #returns eigenvalues and vectors given that the matrix A is symmetric (i.e all eigenvalues are real)
scipy.linalg.eigs(A, k=num) #returns eigenvalues and vectors given that the matrix A is sparse 
np.linalg.det(A) #returns determinant
np.linalg.einsum('ii->i',a) #returns the diagonal einsum('ii',a) returns sum of diagonal
np.linalg.norm(x - (w.dot(x)/np.linalg.norm(w)) # calculating distance of x from hyperplane w
((A - B)**2).mean(axis=0) # performs mean squared error
```

## Famous Toy Datasets:
**Labeled Faces in the wild:***
```python
import numpy, sklearn.datasets
D = sklearn.datasets.fetch_lfw_people(resize=0.5)['images']
# Fetching random data
D = [numpy.random.mtrand.RandomState(1).permutation(len(D))[:2000]]*1.0
# Centering
D = D - D.mean(axis=(1,2), keepdims=True)
# Normalizing
D = D / D.std(axis=(1,2), keepdims=True)
print(D.shape) # (2000,62,47)
```
## PCA:
[[CookBook2#PCA (Recap)]]
##### SVD:
```python
import numpy as np
# D.shape = (2000,62,47)
X = D.reshape(len(D), -1).T # X.shape = (2914, 2000)
X -= X.mean(axis=1, keepdims=True) # Centering
Z = X / X.shape[1]**.5 # 1\SQRT(N) * X
U, L ,V =  np.linalg.svd(Z, full_matrices=False) # SVD decompositon
U[:,0].dot(X) # Project onto the first PC
V[k,:].dot(X) # Project onto the first K PC
```
##### POWIT:
```python
import numpy as np
w = numpy.random.normal(0,1,[X.shape[0]]) # init w
w /= (w**2).sum()**.5 # Normalize
Cov = np.dot(X,X.T) / X.shape[1] # compute covariance matrix
Jold = float('nan')
# POWIT
for iteration in range(100):
	Sw = np.dot(Cov,w)
	J = w.dot(Sw) 
	print('iteration %2d J(w) = %10.3f'%(iteration,J))
	
	if J - Jold < 0.01:
		print("Critereon reached")
		break
	Jold = J
	w = Sw / (Sw**2).sum()**.5
```

## LLE:
[[CookBook2#Locally Linear Embedding]]
```python
import numpy as np

k = 10 #num of neighbors
N = len(X)
W = np.zeroes([N,N])

for i in range(N):
	# Step 1:
	x = X[i] #iterate over every point
	dists = ((x-X)**2).sum(axis=1)**.5 # find nearest neighbors
	dists[i] = float('inf') #Remove the node itself from its neighbors
	ind = dist < sorted(dist)[k] # find k nearest
	# Step 2:
	diff = x - X[ind]
	C = np.dot(diff, diff.T) # Construct C
	C += 0.05 * np.identity(k)
	# find w
	w = np.linalg.solve(C, np.ones([k]))
	w /= w.sum()
	W[i,ind] = w
# Step 3:
M = np.identity(N) - W	- W.T + np.dot(W.T, W)
E = np.linalg.svd(M)[0][:,-3:-1]
```