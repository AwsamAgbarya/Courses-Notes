---
tags:
  - Cookbook
  - MachineLearning
---
 Child of [[MLRoadmap]]
*** 
# Derivatives:
- Vector Norm Squared: $\frac{\partial}{\partial w} \|w\|^{2}= 2w$
- function Norm:   $\frac{\partial}{\partial x} \|x − a\|_{2}= \frac{x − a}{\|x − a\|_2}$
- matrix:  $\frac{\partial a^TXb}{\partial X}= ab^T$
- matrix Transpose:    $\frac{\partial a^TX^Tb}{\partial X} =b^Ta$
- quadratic form:   $\frac{\partial x^{T}Ax}{\partial x} = (A+A^T)x$
- You can observe that the derivative above can be simplified to $2Ax$ if A is symmetric because $A = A^T$
- Gaussian:  $\frac{\partial p(x)}{\partial x} = −p(x)Σ^{−1}(x − m)$   or   $\frac{\partial p(x)}{\partial\sigma}\;=\;p(x)\frac{1}{\sigma}\left[\frac{(x-\mu)^{2}}{\sigma^{2}}-1\right]$
***
# Integration:
* Integration by parts:  $\int_{a}^{b}u(x)v(x)^{'} =\left[u(x)v(x)\right]_{a}^{b}-\int_{a}^{b}u^{\prime}(x)v(x)\,d x$
*** 
# Matrix Properties:
- #### Positive Semi-definite: 
	- $x^T Ax ≥ 0, ∀x ∈ R^n$
	- Negative Semi-definite if -A is PSD
	- All eigenvalues of PSD are non-negative
- #### Positive definite: 
	- $x^T Ax > 0, ∀x ∈ R^n, x \neq 0$
	- Negative definite if -A is PD
	- Is inveritble
	- $det( A) > 0$
	- Positive definite matrices are also Positive Semi-definite
	- $X^T AX = 0 ⇒ AX = 0$
	- If X is $n × r$, where $n ≤ r$ and $rank(X) = n$, then $XX^T$ is positive definite
- #### Symmetric :
	- Covariance matrices are symmetric :BoBxsSmile:
	- Symmetric $A^{T}= A$ and anti symmetric if $A = -A^{T}$
	- Whenever we consider a quadratic form $x^T Ax$, we can assume without loss of generality that the matrix A is symmetric
	- The eigenvalues of a symmetric real-valued matrix A are real
	- The eigenvectors of a symmetric Matrix are orthogonal to each other
	- Can be diagonalized (decomposed) into $VUV^T$ if it has full rank
- #### Orthogonal:
	- $A^T A = AA^T = I$
	- Its eigenvalues are placed on the unit circle
	- $A^{−1} = A^T$
	- $det(A) = ±1$
- #### Gram:
	- is Symmetric
	- is PSD
	- can be Written as $XX^T$
- #### Invertible:
	- A square matrix A is invertible (non-singular) if there exists a matrix $A^{-1}$ such that $AA^{-1} = A^{-1}A=I$
	- A is invertible if and only if rank(A) = n
	- A is invertible if and only if $det(A) \neq 0$
	- $(A · B)^{−1} = B^{−1} · A^{−1}$
	- $(A^{T})^{−1} = (A^{−1})^{T}$
	- $\begin{bmatrix} a & b \\ c & d \end{bmatrix}^{-1} = \frac{1}{ad-bc}\begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$
- #### Diagonizable:
	- The eigen decomposition of a diagonizable matrix is $A = UVU^{-1}$ such that V is a diagonal matrix and U is an invertible matrix
	- If its symmetric, its decomposition is $A = UVU^{T}$
	- A of dimensions $R^{nxn}$ has n linearly independent eigenvectors (n different eigenvalues) ⇔ A is diagonalizable
	- The columns of U are the eigenvectors of A, the diagonal of V contains the corresponding eigenvalues.
	- All eigenvalues nonzero ⇔ A is invertible ⇔ rank(A) = n ⇔  $det(A) \neq 0$
	- We can also infer that The determinant of A is the product of its eigenvalues.
	- This properly makes it easier to exponentiate $A^{p} = UV^{p}U^{-1}$ 
	- The trace of A is the sum of its eigenvalues

*** 
# Determinant:
- if A is trinagular, its determinant is the product of the coefficients on its main diagonal
- If rank(A) < n then det(A) = 0
- $det(AB) = det(A) det(B)$
- $det(A^{-1}) = det(A)^{-1}$
- $det(A) = det(A^{T})$
- $det(λA) = λ^{n} det(A)$
***
# Norms:
- #### Types:
	-  The 2-norm: $||x|| = \sqrt{\sum_{i} x_i^2}$
	- The 1-norm: $||x||_1 = ∑_i |x_i|$
	- The inf-norm: $||x||_∞ = max_i |x_i|$
	- The p-norm: $||x||_p = (∑_i |x_i|^p)^{1/p}, p ≥ 1$
	- The Frobenius norm: $||A||_F = \sqrt{Tr(A^T A) }=\sqrt{∑_{i,j} A^2_{i,j}}$
- #### Properties:
	1. Positivity:    $\|x\| ≥ 0, \|x\| = 0 ⇔ x = 0$ 
	2. homogeneity:     $\|αx\| = |α|\|x\|, ∀α ∈ R$
	3. Triangle Inequality:    $\|x + y\| ≤ \| x\| + \|y\|$
***
# Inner Products and Kernels:
- Properties of Inner Products:
	1. Positivity:   $〈x, x〉 ≥ 0, 〈x, x〉 = 0 ⇔ x = 0$
	2. Symmetry:  $〈x, y〉 = 〈y, x〉$
	3. Additivity (For real numbers and vectors):   $〈x + y, z〉 = 〈x, z〉 + 〈y, z〉$
	4. Homogeneity (For real numbers and vectors):  $〈rx, y〉 = r〈x, y〉 for all r ∈ R$
	5. Homogeneity for second term: $〈x, ry〉 = r〈x, y〉$
	6. Additivity for second term:   $〈x , z+ y〉 = 〈x, z〉 + 〈x, y〉$
	7. Orthogonality: $\langle x,y \rangle = 0$
	8. Cauchy Schwarz:   $|〈x, y〉| ≤ ||x|| ||y||$
-  Kernels: 
	1. Summation of two Kernels is also a kernel
		$c^{T}(K_{1}+ K_{2})c=c^{T}K_{1}c + c^{T}K_{2}c$
	2. Product of two Kernels is also a kernel
		$\phi_{1}(X)^{T}\phi_{1}(Y) \cdot \phi_{2}(X)^{T}\phi_{2}(Y) = \phi_{1}(X)^{T}\phi_{2}(X) \cdot \phi_{1}(Y)^{T}\phi_{2}(Y) = (\phi_{1}(X)^{T}\phi_{2}(X))^{2}$ 
***
# Projections:
- a linear transformation P, is called a projection if it holds that $P \cdot P = P$
- let $u_{1}....u_{n}$ be an orthonormal basis of U, $P_{U}(x) = \sum^{n}x^{T}u_{i}u_{i}$
***
# Statistics and Probability:
- $Var[Ax] = AVar[x]A^T$
- $E[xx^T ] = \sigma^2I + \mu \mu^T = Var(x) + E(x)^2$
- $E[xa^T x] = (M + mm^T )a$
- $E[x^T x] = Tr(M) + m^T m$
- $E[p(x)] = \int x*p(x)$ such that $f(x)$ is continuous density function
- $Variance(x) = E[(x-E(x))(x-E(x))^T]$
-  For independent variables:
	- $Variance(XY) = E(X)^2Var(Y) + E(Y)^2Var(X) + Var(Y)Var(X)$
	- $E(XY)= E(X)E(Y)$
	- $E\left[ \sum Y^{(i)} \right] = \sum E[Y^{(i)}] = nE[Y^{(i)}]$
***
# Convex Optimization:
- Slater's conditions state that for an optimization problem to have strong duality:
	-  The inequalities must be feasibly strict
- Given an optimization problem constrained by an equality g and an inequality h, KKT rules must apply to the solution of the Lagrangian:
	- Stationary: $\frac{\partial L(\theta)}{\partial \theta} = 0$
	- Dual feasibility: $\forall_{i=1}^{l}: \lambda_{i}\geq 0$
	- Complementary slackness: $\forall_{i=1}^{l}:\ \lambda_{i}h_{i}(\theta)=0$
***
# Programming:
```python
# Numpy Functions to initialize arrays
	np.zeros(size)
	np.ones(size)
	np.full(size,val)
	np.empty(size)
	np.arange(start:end:step)
	np.linspace(startval,endval,size)
	np.repeat(containee,times,axis)
	np.identity(size)/np.eye(size)
# Numpy useful operations
	np.cumsum(arr,axis) #Cumulative sum
	np.vstack(a,b) #appends 2 arrays while keeping the objects
	np.hstack(a,b) #appends 2 arrays horizontally 
	np.argmin/max(a)  #returns index of min/max
	np.unique(arr, return_index, return_inverse, return_counts) #returning unique elements of arrays
	np.expand_dims(arr, axis) #expanding the dimension of an array
	np.argwhere(a>c).flatten() #returns indices of non-zero elements
	np.where(cond, x,y) #returns elements that match the condition (returns x otherwise y)
	np.put(a,indices,values) #replaces indices in a with values
	np.hsplit(a,number) #splits array horizontally given a number of elements
# Shaping
	A.T #flips the axis 
	A.transpose(indices) #transposes the arrays axis according to the indices of the original axis
	A.reshape(shape) #keeps the data in the same order but changes the dimensions accordingly, You are allowed to use '...' to indicate all previous indexes
	A.Flatten() #turns the array into one dimensional
#Linear Agebra operations
	np.linalg.norm(point1-point2) #Used to calculate euclidean distances or l2 norm
	np.linalg.inv(A) #inverse matrix
	np.linalg.eig(A) #returns eigen values vectors
	np.linalg.det(A) #returns determinant
	np.linalg.einsum('ii->i',a) #returns the diagonal einsum('ii',a) returns sum of diagonal
# Randomizing
	random.randint(low,high,size) # random integer
	np.shuffle(array) #shuffle the sequence around randomly
	random.uniform(low,high,size) #all samples have equal probability
	rng.normal(mean,cov,size) #is a gaussian distribution
# Tips and Tricks
	pad_shape = (
	    (0, 0),  # Add no row at the top and no row at the bottom
	    (1, 0),  # Add one column at the left and no column at the right
	)
	transition = np.pad(arr,pad_shape,constant_values=0) 
	A[:,None] #To add a new dimensions (usually for broadcasting)
	A[A>c] #filter out all the elements in A that dont apply to the condition
	np.linalg.norm(x - (w.dot(x)/np.linalg.norm(w)) # calculating distance of x from hyperplane w
	((A - B)**2).mean(axis=0) # performs mean squared error
```