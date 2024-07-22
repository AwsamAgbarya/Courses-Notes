---
tags:
  - MachineLearning
  - Cookbook
---
# Cookbook for Machine learning 2:
## PCA (Recap):
[[PCA]]
- We want to map our high dimensional data to low dimensions while keeping the main contributing features of the data.
- We consider the least contributing features of the data as noise (minimal variance) and the maximal contributing features of the data as Principal components (maximal variance).
- Our objective is to minimize the noise of the projected data  $\arg\min_w \left[\frac{1}{N}\sum_{k=1}^N \|x-ww^tx\|^2 \right]$ Or find the maximal variance in our covariance matrix $\arg\max_{\|w\|^2=1} \left[w^T \hat{\Sigma}w\right]$, These two objectives are equivalent 
- Minimizing the noise of the projected data can be seen equivalent to a linear auto-encoder.
- Data needs to be centered and cleared of outliers, i.e this method assumes mean=0.
- The second objective translates to finding the maximal eigenvectors of our covariance data (which describe the maximally scaled direction according to our covariance matrix)
- Covariance matrix is a PSD gram matrix, meaning its symmetric and all its eigenvectors are orthogonal to each other, furthermore all its eigenvectors are real positive numbers
- SVD is a matrix decomposition describing a matrix $A = UMV^T$ such that U and V contain the eigenvectors of $AA^T$ and $A^TA$ respectively, these are called left singular vectors of A and right singular vectors of A, furthermore M contains the singular values of A $\sqrt{|\lambda|}$ such that $\lambda$ s are the eigenvalues of matrix A. SVD can be done for any matrix and it represents the key structure and information of its mapping.
- SVD for a symmetric matrix is gonna hold the eigenvectors of $A^2$ which are the same as A's eigenvectors.
- SVD computes all the eigenvectors of A which is unnecessary, we only want the first k eigenvectors.
- Power Iteration algorithm says the following:
	1. Initialize w as a unit vector
	2. Multiply that vector with the covariance matrix, which will shape it in the direction of all its eigenvectors, the larger eigenvectors will affect it more than the smaller ones.
	3. Normalize w, to keep its direction but not scale
	4. Repeat step 2-3 t times, the influence of the largest eigenvector on it will get bigger and bigger in comparison to the smallest, which will lead it to exponentially converge to the largest eigenvector
	5. Now you have found the largest current eigenvector, remove it from the covariance matrix and recompute 2-4, until you get k eigenvectors
	
> [!Code]- POWIT Code Snippet
> ![[Code snippets#PCA]]

## Locally Linear Embedding:
[[Locally Linear Embedding]]
- We want to reduce the dimensionality of the data like PCA, but we want to do it in a non-linear way that preserves local neighborhood structure such that neighbors in high dimensions are still neighbors in low dimension.
- If we pick our neighborhood size as too large, two points that are not meant to be neighbors will become neighbors and destroy the underlying manifold, if we pick our neighborhood size as too little we wont be able to get any meaningful characteristics of that neighborhood.
- Transformations such as translations, rotations and scaling compromise our ideal mapping from high to low dimensions because these three transformations do not destroy structure, thus we want to be invariant to those transformations.
- LLE Algorithm:
	1. Compute K nearest neighbors or radius search for each point to identify its neighborhood.
	2. Learn the neighborhood structure of each point, i.e we assume that each point is a linear combination of its neighbors and we want to learn the weights of that linear combination in the least squares sense.
		- If we can represent a point as linear dependent on its neighbors, we essentially remove a dimension that describes the direction of that point and can embed it in a lower dimension
		- Objective to minimize $R_{x_{i}}(w) = \sum_{x_{j} \in N_{i}} \| x_{i} - \sum_{j}^{n} w_{ij} x_{j} \|^2$, This objective formulation is invariance to scaling because it described the reconstruction of point i using linear interpolation of its neighbors, however for it to be a linear combination we require the constraint $\sum_{j \in N_{i}} w_{ij} = 1$ . Furthermore this is invariant to translations because translating an entire neighbor with an equal amount will keep the same ratios between them.
		- Solution is given by $w_{i} = \frac{C^{-1}1}{1^{T}C^{-1}1}$ where the denominator is put there to enforce the constraint such that C is the neighborhood structure covariance matrix $C = (x_{i} - X_{j})(x_{i} - X_{j})^{T}$
	3. Find the best low dimensional mapping of this point such that it describes the same neighborhood structure.
		- We freeze the weights learned by the previous step for this current point i.
		- We have to find a mapping matrix Y  such that the objective in lower dimension $\phi(Y) = \sum_{i=1}^{n} \|y_{i} - \sum_{j \in N_{i}} w_{ij} y_{j} \|^{2}$ is minimal. After simplification we observe that we that we are minimizing a quadratic form which means we want to find the minimal  p eigenvectors of that form, in this case $(I - W)^{T}(I - W)$
		- Those eigenvectors are orthogonal to each other because this is a symmetric matrix, the bottom-most eigenvector is the vector 1 representing a free translation in any direction, thus if we discard of it, we center our mapping to zero
- This method is sensitive to noise as the weights will yield different embeddings according to small pertubation
- This method requires uniform sampling from all regions in the data otherwise we wont be able to represent all neighborhood properly
- We do not learn an explicit mapping from the manifold to the low dimensional mapping so we cannot perform them on new points.
- Quadratic complexity
- We do not know the best low dimensionlity to represent our data, we have to experiment
- Finding neighbors is not robust but has to be problem specific.

> [!Code]- LLE Code Snippet
> ![[Code snippets#LLE]]
