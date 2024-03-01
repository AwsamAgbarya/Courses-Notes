*** 
# Derivatives:
- Derivative of a Vector Norm: $\frac{\partial}{\partial w} \|w\|^{2}= 2w$
- $\frac{\partial a^TXb}{\partial X}= ab^T$
- $\frac{\partial a^TX^Tb}{\partial X} =b^Ta$
- $\frac{\partial x^{T}Ax}{\partial x} = (A+A^T)x$
- You can observe that the derivative above can be simplified to $2Ax$ if A is symmetric because $A = A^T$

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
- #### Symmetric:
	- Whenever we consider a quadratic form $x^T Ax$, we can assume without loss of generality that the matrix A is symmetric
	- The eigenvalues of a symmetric real-valued matrix A are real
- #### Orthogonal:
	- $A^T A = AA^T = I$
	- Its eigenvalues are placed on the unit circle
	- $A^{−1} = A^T$
	- $det(A) = ±1$


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
***
# Convex Optimization:
