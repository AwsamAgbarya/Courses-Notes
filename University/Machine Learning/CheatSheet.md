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
* Integration by parts:  $\int_{a}^{b}u(x)v^{'} =\left[u(x)v(x)\right]_{a}^{b}-\int_{a}^{b}u^{\prime}(x)v(x)\,d x$
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
	- The eigenvalues of a symmetric Matrix are orthogonal to each other
	- Can be diagonalized (decomposed) into $VUV^T$
- #### Orthogonal:
	- $A^T A = AA^T = I$
	- Its eigenvalues are placed on the unit circle
	- $A^{−1} = A^T$
	- $det(A) = ±1$
- #### Gram:
	- is Symmetric
	- is PSD
	- can be Written as $XX^T$

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