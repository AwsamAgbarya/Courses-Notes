---
tags:
  - DeepLearning
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
## Processing tasks:
**In-painting missing patch:**
```python
def removepatch(X):
	mask = torch.zeros(len(X),28,28)
	for i in range(len(X)):
		j = numpy.random.randint(-4,5)
		k = numpy.random.randint(-4,5)
		mask[i,11+j:17+j,11+k:17+k] = 1
	mask = mask.view(len(X),784)
	return (X*(1-mask)).data,mask
```