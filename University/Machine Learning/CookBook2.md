---
tags:
  - MachineLearning
  - Cookbook
cssclasses:
  - embedded_code
---
## PCA (Recap):
[[PCA]]
- We want to map our high dimensional data to low dimensions while keeping the main contributing features of the data.
- We consider the least contributing features of the data as noise (minimal variance) and the maximal contributing features of the data as Principal components (maximal variance).
- Our objective is to minimize the noise of the projected data  $\arg\min_w \left[\frac{1}{N}\sum_{k=1}^N \|x-ww^tx\|^2 \right]$ Or find he maximal variance in our covariance matrix $\arg\max_{\|w\|^2=1} \left[w^T \hat{\Sigma}w\right]$, These two objectives are equivalent 
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
- Kernelized PCA assumes the data has been projected into feature space via $\phi(x_i)$ and that now we compute the principal components of the covariance of the centered feature space.
- Assuming K is the kernel matrix that induces such feature map, the leading whitened eigenvectors of this matrix are computed via $\alpha_{\tau} = \frac{1}{\sqrt{\lambda_{\tau}(K)}}u_{\tau}$ Which give us the most meaningful components of our kernel space, if we project our feature space data onto this PC we get the PC of our data onto the PC of the kernel $v_{\tau} = \sum\limits_{i} \alpha_{i}^{\tau} \phi(x_{i})$
- This is all assuming the data is centered but if we have to center it using $\tilde{\phi}(x) = \phi(x) - \frac{1}{N}\sum\limits_{i} \phi(x_{i})$ then the centered kernel matrix is given via $\hat{K} = K -1_N K - K 1_N + 1_N K 1_N$
- This can be used in the context of two classes if our Kernel PCA can properly define the PC of the decision boundary, then we can estimate the relevant information needed to classify a point y, only lies in the largest PCs and the smaller PCs contribute nothing but noise
- If we reconstruct our labels using the most relevant information via $\hat{y} = \sum\limits_{\tau=1}^{d} u_{\tau}u_{\tau}^{T}y$ then we can estimate how much noise the separation of the first d PCs will yield via $e(d) = \sum\limits_{i=1}^{N}L(\hat(y)_{i}, y_{i})$
> [!example]- POWIT Code Snippet
> ![[Machine Learning/Code Snippets#PCA]]

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

> [!example]+ LLE Code Snippet
> ![[Machine Learning/Code Snippets#LLE]]
## Pairwise distances:
[[T-Sne]]
- Multi-dimensional Scaling tries to minimize the discrepancy between the pairwise distances in the original space and the low dimensional space.
- We define the pairwise distances between the points as $d_{ij} = \|x_{i} - x_{j}\|^2$ and the pairwise distances between the low dimensional approximations of the points as $\tilde{d_{ij}} = \|y_{i} - y_{j}\|^2$ such that our objective function to minimize is now $J(Y) = \sum_{i<j}(d_{ij} - \tilde{d_{ij}})^2$
- If data lies on a hyperplane, the distances can be perfectly preserved by finding that hyperplane, this is equivalent to PCA
- Double centering the distance matrix (centering columns and rows so for example for $d_{ij}$ we do $\|x_{i} - x_{j} - x_{i}\|^{2}= x_{j}^{T}x_{j}$) will turn it into a dot product matrix, which is exactly what PCA works on and MDS will be equivalent to PCA.
- Some problems lie with MDS:
	- It measures distance globally and not across the data manifold, meaning if two points are close to each other in euclidean space but not in the manifold space they will be mapped close to each other in the low dimensional space, This gets improved upon using Isomap.
	- We try to linearly map all distances as close as possible, but sometimes we dont care about points that are super far away, we dont want to map their distance super accurate we just want to map them far away but in a non-linear way, we introduce a new cost function in this case that weights the cost by the distance, the larger the distance the less we care about how accurate our mapping is $J(Y) = \sum_{i<j}\left(\frac{d_{ij} -\tilde{d_{ij}}}{d_{ij}} \right)^2$ this is referred to as Sammons mapping, it slow to optimize and gets stuck in local optima
- Isomap is conceptually similar to MDS except for the fact that we measure distances along the data manifold not in Euclidean space.
- Isomap Algorithm:
	- Take small neighborhoods around every point
	- Connect each point to its K nearest neighbors in high dimensional space as a graph.
	- put the euclidean distance on those graph links
	- approximate the manifold distances between any pair of points as the shortest path on the graph between those two points.
- Isomap does not generate new points, it can only read and understand the structure of the points in the dataset graph.
## Stochastic Neighbor Selection:
[[T-Sne]]
- SNE algorithm assumes our data is represented as a Gaussian mixture model.
- SNE measures the probability $p_{ij}$ of point $x_{i}$ belonging to Gaussian $N_{j}$ in high dimensional space and then tries to find a low dimensional mapping such that it represents the same weight contributions $q_{ij}$ of each of the Gaussians in high dimensional space (Think LLE but the structure is GMM).
- $p_{ij} = \frac{exp(-\frac{\|x_{i} - x_{j}\|^{2}}{2\sigma^2})}{\sum_{k!=l}exp(-\frac{\|x_{k} - x_{l}\|^{2}}{2\sigma^2})}$ and $q_{ij} = \frac{exp(-\frac{\|y_{i} - y_{j}\|^{2}}{2\sigma^2})}{\sum_{k!=l}exp(-\frac{\|y_{k} - y_{l}\|^{2}}{2\sigma^2})}$ which form a probability distribution of P and Q respectively (over all is and js)
- Our objective function tries to get the probability Q as close as possible to P, i.e Minimize the KL-divergence $D_{KL}(P||Q) =\sum_{i}\sum\limits_{j} p_{ij} log \frac{p_{ij}}{q_{ij}}$
- We optimize using gradient descent along the gradient vector plus some momentum term.
- We view our optimization as a set of forces between the mapped points i and j, if the points are too close, the force repels the two points away from each other, if the points are too far they are attracted to each other which is proportional to its length.
- a problem arises while trying to map our high dimensional manifold to a low dimensional one, since we focus on similarities and dis-similarities, the very dissimilar parts will have to have a large distance between them which results in crushing everything together because of the force that it exerts, this is mainly due to how the gaussian is defined as it tends to 0 exponentially fast over further distances, so having gaussian terms in the denominator will make the fraction explode beyond necessity.
- a plausible solution is to say that if the points are super far away, we don't care as much about the accuracy , we will model them far away but not accurately proportionally far away, we can do this by replacing the gaussian with a student distribution that tends to 1 instead of 0 which is $\frac{1}{1+\|x_{i}-x_{j}\|^{2}}$.

> [!example]- T-SNE Code Snippet
> ![[Machine Learning/Code Snippets#T-SNE]]
## Non-metric data:
[[T-Sne]]
- Metric data follows similarity measures that do not conform to the l2 norm because of some violations:
	1. Intransitive similarities: If A is similar to B in one way and similar to C in a different way, this does not mean B and C are similar, yet in euclidean distance according to the triangle equality, B and C should also be similar, this is limiting semantics.
	2. Centrality: if B,C,D,E,F,G 's nearest neighbor is A, this can no longer be modeled in euclidean space because of the hexagon distance from center theorem (i.e theyre gonna be as close to each other as they are to A, we cannot model infinitely many points that the closest neighbor to them is A, but this is semantically possible)
	3. Asymmetries: If A considers B a close friend but B does not, this is impossible to model with euclidean distances as they are symmetric, this again limits semantics.
- We want to reformulate the dissimilarity matrix using general similarity measures that are not the l2 norm.
- if D is squared Euclidean (D is metric and relies on l2 norm to calculate squared distances) then its mapping is PSD and is called the covariance matrix, and all its eigenvalues are positive.
- Low dimensional embedding techniques usually rely on the largest eigenvectors of the covariance matrix and assume all of them are positive
- if we use non-metric data, D is no longer squared Euclidean which means its mapping now has negative eigenvalues.
- We need to reformulate our issues to consider Eigenvalues instead of ignoring them (so instead of only taking the k largest eigenvectors we take the k largest eigenvectors in both the positive and the negative spectrum, because large eigenvectors in the negative spectrum also hold maximal variance).
- We can use Multiple maps T-SNE to solve non-metric data, its basically TSNE except we have multiple maps representing multiple eigenvectors (negative and positive) which measure similarities in different way (e.g two objects are the same brand, two objects are the same color, two objects are the same shape).
	- TSNE attributes a weight for each point such that the sum across all maps is 1.
	- Similarity between two points is the distance between them at every map multiplied by their weight at every map
	- Each point exists somewhere in every map
	- $q_{ij} = \frac{\sum_{m} w_{i}^{m}w_{j}^{m} (1+\tilde{d_{ij}})^{-1}}{\sum_{m} \sum_{i!=k} w_{i}^{m}w_{k}^{m} (1+\tilde{d_{ik}})^{-1}}$
## Canonical Correlation Analysis:
[[Canonical Correlation analysis]]
- We have dataset X of dimension N and dataset Y of dimension M, both those datasets are of different modalities and we want to combine them in one latent feature space such that their correlation is maximized.
- We need to find a projection of X $w_{x}$ and a projection of Y $w_{y}$ such that their correlation is maximized.
- Reminder, a correlation matrix between two datasets, is the covariance matrix divided by the variance of each of the two sets.
- Our objective $max_{w_{x}, w_{y}} \frac{w_{x}^{T}XY^{T}w_{y}}{\sqrt{w_{x}^TXX^{T}w_{x}}\sqrt{w_{y}^{T}YY^{T}w_{y}}}$ which we can simplify by maximizing the numerator while constraining the variance of the two projected sets to 1, $argmax_{w_{x}, w_{y}} w_{x}^{T}XY^{T}w_{y}$     s.t    $w_{x}^{T}XX^{T}w_{x} = 1$   and    $w_{y}^{T}YY^{T}w_{y}=1$
- We denote the cross covariance matrices (of two centered datasets) as $C_{xy} = \frac{1}{N} XY^{T}$ and the auto covariance matrices as $C_{xx} = \frac{1}{N}XX^{T}$
- The solution of our objective is our highest eigenvector of the following problem $$\begin{bmatrix}0 & C_{xy} \\ C_{yx} & 0 \end{bmatrix}\begin{bmatrix}w_{x}\\ w_{y}\end{bmatrix} = \lambda \begin{bmatrix}C_{xx}&0 \\0& C_{yy} \end{bmatrix}\begin{bmatrix}w_{x}\\ w_{y}\end{bmatrix}$$ and in the Kernerlized object its : $$\begin{bmatrix}0 & K_{x}K_{y} \\ K_{y}K_{x} & 0 \end{bmatrix}\begin{bmatrix}\alpha_{x}\\ \alpha_{y}\end{bmatrix} = \lambda \begin{bmatrix}K_{x}K_{x}&0 \\0& K_{y}K_{y} \end{bmatrix}\begin{bmatrix}\alpha_{x}\\ \alpha_{y}\end{bmatrix}$$
> [!example]- CCA Code Snippet
> ![[Machine Learning/Code Snippets#CCA]]
## Independent Component Analysis:
[[Component Analysis]]
- Tries to Separate observed data X into N sources with their coefficients. $x_{i} = As_{i}$ with the assumption that the signals S are independent of each other $P(u) = \prod\limits_{i=1}^{n}p_{i}(u_{i})$.
- Many different algorithms:
	- Some algorithms like Jade try to minimize the divergence between the combined data and their multipliciation $D(w) = \int p(u) log \left(\frac{p(u)}{\prod\limits_{i=1}^{n}} \right)du$ by performing gradient descent down that gradient in orthogonal spaces that dont include Gaussian noise.
	- some algorithms like TDSEP assume an auto-correlation over time with itself and does so by whitening the data using $v A^{-\frac{1}{2}} v^T$ inversed and some roation matrix W whcih is good with sinsoidal subspaces
	- Some algorithms try to maximize info (InfoMax) by minimizing mutual info which means minimizing the entropy of the sources using Gradient descent and convenient function.
	- Some algorithms (FASTICA) try to maximize Kurtosis as its a way of measuring the dissimilarity of the data from a Gaussian distribution (which we want because gaussian distributions dont have independent components)
- To measure uncertainty in ICA:
	- We have to do our initial BSS guess to get A
	- We produce surrogate data to test the uncertainty
	- We whiten the surrogate data
	- We do BSS for this surrogate data which gives us rotation matrices.
	- We turn rotation matrices into angles
	- The std of the angles define the seperability matrix
	- measure instability of the mixing matrix via $S_{ij} = \sqrt{<\alpha_{ij}^{2}>}$
	- The uncertainty of the estimated projection direction i is $max_{j}S_{ij}$
> [!example]- FastICA Code Snippet
> ![[Machine Learning/Code Snippets#ICA]]
## Representation learning:
[[Auto-encoders]], [[CNN]], [[Generative Modelling]], [[Regularization]] [[Representation Learning]]
- We want to be able to represent our data in a sparse way such that the sparse code for each input is some weight times high level features, that way we can represent x as a bunch of weights S that can be multiplied by a dictionary of known features W such that it reconstruct the datapoint x.
- Reconstruction objective: we don't want to lose important information while sparse encoding, thus we have to get the reconstruction of the image from the sparse code and the dictionary to be as close as possible to the original image $\|x- \hat{x} \|^2$ such that $\hat{x_{i}} = Ws_{i}$.
- We also want our reconstruction to be as sparse as possible, we could use the zero norm which computes the maximally sparse representation of S, but it is non-convex, we prefer a differentiable convex expression that induces some sparsity so we use the 1 norm instead $\lambda \|s\|_{1}$, higher values of lambda will produce results that are maximally sparse but do not reconstruct the data that well, lower values of lambda will perfectly reconstruct the data but produce dense representations.
- We want to constrain or features dictionary W not to explode when learnt (because S becomes so small), otherwise W is no longer stable, we do so by $\eta \|W\|_{f}^{2}$
- Our objective function is now : $min_{W, S} \frac{1}{N}\sum_{i=1}^{N} [\|x_{i} - Ws_{i}\|^{2}+ \lambda \|s_{i}\|_{1} ]+ \eta\|W\|_{f}^{2}$
- This can be seen as an auto encoder of two neural networks such that we learn S from x using a neural network with weights $s_{i} = Vx_{i}$ and the reconstruction is learned by a neural network with weights W $\hat{x}_{i} = WVx_{i}$.
- If these neural networks were linear, this problem will be equivalent to PCA, so we have to use non-linear activation functions in those Neural networks to produce better solutions. ReLU happens to be really good at producing sparse representations because it clamps all negative results to 0 which is what we want.
- These neural networks can be multi-layered and complex, and just like any other NN, they can be trained using backpropagation.
- Sparse encoding can be applied to images using the convolution operator such that the feature dictionary W can be detected at any part of the image and will now represent image filters.
- We often add a Noise layer at the start of auto encoder architecture to allow it to Generalize and learn a more general representation of our data (stop it from overfitting)[[Auto-encoders]]
-  Skip connections are connections between blocks of NN layers that improve stability and output in 2 different ways:
	1. Res-net style skip connections allow for better Information flow and gradient flow in backprop in really deep neural networks, since all weights are initialized normally, in the first iterations a NN with 20 layers will produce noise as output and noise as backprop gradient which makes it really hard to train and optimize, skip connections allow for the relevant information to flow without being multiplied exponentially with noise [[CNN]]
	2. U-net style skip connections allow flow of low-level information (spatial positions for example) gotten from CNNs into the decoder CNN at the appropriate level to propagate the answer to the question "Where?" wheres the encoder itself transforms the information of "What?". [[Auto-encoders]]
- Normalizing flows is the sequence of transformations from the complex unfeasible data probability distribution, into a simple gaussian distribution. The idea is that if we build a set of transformations that are all invertible and differentiable then we can sample a point from a Gaussian distribution and do the inverse of those transformations to get to a datapoint, thus we indirectly learn the complex data distribution. i.e if X is achieved via $f(z)$ and z is achieved by $f(x)^{-1}$ then the probability distribution of x is achieved by $p(x) = p^{'}(f(x)^{-1}) * scale$
- if we try to maximize the log of the probability distribution of x we can iteratively go over the inverse of each our transformations, make sure we dont scale the probability distribution beyond 1 and find the transformations that best represent that data distribution.
- In order to ensure that we keep probability distributions to 1, we multiple with the determinant of the inverse Jacobian which describes how much that transformation of that function f scales space, and if it scales space this needs to be multiplied in order to ensure that it stays at 1.[[Generative Modelling]]
- Self-Supervised learning is to define a task given a set of data with no labels (for example fill in the hole in the image, or puzzles),  such that your model now learns key features of the data, which later on can be frozen and used on a different task that uses those same features [[Representation Learning]]
- Data from different domains is an issue that occurs in datasets, such that you have in the same class 2 diff subsets that belong to that class but have a few different features, one domain might be not very well represented or the data does not have a lot of labels, we want our objective function to find a decision boundary that separates the classes while keeping in the mind the distribution of different domains per class [[Regularization]].
- Domain auxiliary network is a neural network model that has a feature extractor and two networks with competing objective:
	1. Normal task network (for example classifying images) that tries to predict the data as best as possible, the error is large when the classification is incorrect
	2. Domain Critic tries to differentiate between the two domains of that class, the error is large when the critic can tell which domain this datapoint belongs to correctly.
	Our feature extractor is then modified and optimized such that it can fool the domain critic network into not being able to tell the difference between the domains while not affecting the error task at hand.
	- This is often done using the Wasserstein distance.
- Representation based learning is a learning task that tries to learn general transformations between data and not the local information in the datapoint itself (e.g how to rotate an image). This can be done by producing two version of one datapoint, one rotated the other not, and encoding them with an encoder such that the decoder takes in the input of both and tries to learn to rotate the original image using the difference between the two representations produced by the two encoders working on the original and rotated image.

> [!example]- Auto-encoders Code Snippet
> ![[Machine Learning/Code Snippets#Auto-encoder]]
## Hidden Markov Models
[[Markov Models]]
- Often times we are tackled with issues that require us to understand the probability distribution of the data, it is usually difficult to formulate a solution for this because of the infinite possibilities, more often than not we can induce some prior knowledge in enforcing some constraints and structure, that inlaying structure is compromised of some dependencies that we can exploit that simplify our options.
- These dependencies can be modeled using directed graphs.
- Markov chains are directed graphs of dependencies that have 2 very important properties:
	1. Markov chain property states that for every state in the chain, The of the current sequence of states that lead us to the current state does not contribute or matter in the decision of which state we choose next, in other words, every state is reached by a dependency and a decision only made by its previous state in the sequence.
	2. Stationarity property states that the probability distributions describing the states and the model do not change over time.
- When we discretize a markov model (i.e add a countable finite amount of states) we usually model the transition probabilities via matrices/vectors of probabilities such that the indices indicate the states.
- Hidden Markov models are a generalization of markov chains such that we can no longer observe/know what the states are, Each state now emits a result from a probability distribution and we must infer causality of Observations with the sequence of states we went through.
- HMM are quite notation intensive so lets try to keep note of everything :)
	- $q_{t}$ is the indicator of the current state we are at at time T
	- $S_{i}$ is the indicator of the state associated with index i
	- $O_{t}$ is the indicator of the state at time t.
	- $v_{k}$ is the indicator of the observation value as kth value in the alphabet
	- Transition probabilities from state i to state j: $a_{ij} = P(q_{t} = S_{j} | q_{t-1} = S_{i} )$
	- Emission probability from state j to produce observation value k: $b_{j}(k) = P(O_{t}=v_{k} | q_{t}= S_{j})$
	- The probability of starting at state i at time t=1 is: $\pi_{i} = P(q_{1}=S_{i})$
	- $\lambda$ Denotes our model parameters as a whole $\lambda = (A,B,\pi)$
- **Objective 1:** How to calculate the probability of our Observation sequence O being produced by our model parameters? $P(O|\lambda)$
	- $\alpha_t(i)$ indicates the probability of us observing the first t observations according to our model AND we end that sequence at state $S_{i}$ this is given by $P(O_{1}...O_{t}, q_{t}=S_{i} | \lambda)$
	- Alpha can be recursively computed using the forward backward algorithm:
		- *Base Case:*      $\alpha_{1(i)}= \pi_{i}b_{i}(O_{1})$
		- *Recursive Definition:*     $\alpha_{t+1}(j) = [\sum_{i=1}^{N} \alpha_{t}(i)a_{ij}]b_{j}(O_{t+1})$
	- Finally we can compute Our objective using the following method: $P(O|\lambda) = \sum\limits_{i=1}^{N} \alpha_T(i)$
- **Objective 2:** How to calculate the sequence of states that is most likely to produce a given Observation? $max_{Q} P(O | Q, \lambda)$
	- $\delta_{t}(i)$ indicates the probability of Observing the first t observations using our sequence of states such that the last state is i $\max\limits_{Q} P(q_{1}...,q_{t}=i, O_{1}...O_{t}| \lambda)$
	- Delta can be recursively computed using the forward backward algorithm:
		- *Base Case:*  $\delta_{1}(i) = \pi_{i}b_{i}(O_{1})$
		- *Recusrive definition:* $\delta_{t}(j) = \max\limits_{i} [\delta_{t-1}(i)a_{ij}] b_{j}(O_{t})$
		- Note that we do have to save an index i associated to the state that maximizes that inner term in order to save the sequence.
	- Finally we can compute our Objective using the following method: $\hat{Q} = \arg\max\limits_{1 \leq i \leq N} \delta_T(i)$
- **Objective 3:** How do we update our model parameters such that it best reflects a given Observation, i.e how do we train our model to be the model that is most likely to produce the observation data we have?
	-  We currently have 3 parameters that are apart of our model, A, B and $\pi$ and we cant directly compute the optimal solution for all of them, we will try to infer some distributions from the model parameters and then perform a Expectation maximization style coordinate gradient descent.
	- Just as a reminder this algorithm will fix one unknown as "optimal at the current state" and try to infer the optimal solution for the second one from it then fix the inferred one and try to find the optimal solution from it over many iterations.
	- Lets define the following 2 unknowns, these 2 can be inferred from the model parameters, and the model parameters can be inferred from them, such that we can iteratively improve them:
		- $\gamma_t(i)$ is the probability of being at state i at timestep t given our model parameters and our observation
		- $\xi_t(i,j)$ is the probability of being at state i at timestep t and transitioning to state j at the next timestep given our model and our observation.
	- How do we compute these two probabilities?
		- $\alpha_t(i)$ is our forward variable (that we previously shown we can calculate) that describes the probability of our observation being produced from our model such that we end on state i at time t $P(O_{1}....O_{t}, q_{t}=S_{i}| \lambda )$
		- $\beta_t(i)$ is our backward variable that can be calculated in a similar manner and describes the probability of our future observations (beyond observation t) occurring given that we are currently at current state i at timestep t $P(O_{t+1}...O_{T} | q_{t}, \lambda) = \sum\limits_{j=1}^{N}a_{ij}b_{j}(O_{t+1})\beta_{t+1}(j)$
		- We have also shown in Objective 1 that we can calculate $P(O|\lambda)$
		- The rest is a straight forward calculation:
			- $\gamma_{t}(i) = \frac{\alpha_{t}(i)\beta_{t}(i)}{P(O|\lambda)} = \frac{\alpha_{t}(i)\beta_{t}(i)}{\sum\limits_{i=1}^{N}\alpha_{t}(i)\beta_{t}(i)}$
			- $\xi_{t}(i,j) = \gamma_{t}(i) * \gamma_{t+1}(j)$
	- How does this help us compute our model parameters?
		- $a_{ij} = \frac{\sum\limits_{t=1}^{T-1}\xi_{t}(i,j)}{\sum\limits_{t=1}^{T-1}\gamma_{t}(i)}$
		- $\pi_{i} = \gamma_{t}(i)$
		- $b_{i}(k)= \frac{\sum\limits_{t=1 \text{ s.t } O_{t}=v_{k}}^{T}\gamma_{t}(i)}{\sum\limits_{t=1}^{T}\gamma_{t}(i)}$
> [!example]- HMM Code Snippet
> ![[Machine Learning/Code Snippets#HMM]]
## Kernels (Input, Output, Anomaly detection):
[[Kernel Methods]]
- Tree Kernels are kernels that compare trees derived from some sort of grammar, this can be done by computing the mutual subtrees and adding them up only if the two roots produce the same thing. $$c(v,w) = \begin{cases} 0 & if & p(v)\ne p(w) \\ 1 & if & |v|=|w|=0 \\ \prod\limits_{i=1}^{|v|}(1+ c(v_{i}, w_{i})) & otherwise \end{cases}$$
- Tree kernels are improved upon using bottom up dynamic programming.
- String kernels can differ a lot with the objective, but most commonly used is the 'n-grams' approach where we count the number of match sub-sequences of symbols with full shift in-variance. $k(x,z) = \sum\limits_{i=1}^{L+1-n}I(x_{i...i+n-1} = z_{i...i+n-1})$
- We can build sorted versions of the lists of n-grams before performing the evaluation to speed up the computation.
- Model induced kernels tell us that there is no point in trying to build a new structural kernel to compare two things in a model that already induces structure.
- For generative probabilistic models, things that are very conforming to the structure have a high likelihood and things that do not have a low likelihood, Fisher kernel measures similarity by comparing the gradients of the log likelihood of the model using $k(x,x^{'})=g_{x}^{T}(E_{z~p_{\theta}}[g_{z}g_{z}^{T}])^{-1}g_{x^{'}}$ we divide by the expectation of the covariance matrix of the gradients in order to normalize the scores.
- Diffusion Kernels use the exponentiation of the generator matrix in order to simulate lazy random walks across the graph $k(x_{i},x_{j}) = [e^{\beta H}]_{ij}$ such that $\beta$ is a hyper-parameter that indicates the probability of the random walk for any vertex with valence smaller than the maximal and the exponentiation will indicate the sum over the paths of the random walks.
 > [!example]- Text Kernels Code Snippet
> ![[Machine Learning/Code Snippets#Structured input kernels]]
- In structured Output prediction, we want to learn complex structures that abide by certain rules instead of predicting a number or a class, i.e we want to output a structure that is compatible with our input, for this we need to learn a compatibility function between our x and y such that it scores high for super compatible structures and low otherwise.
- We can technically theoretically do this with Multi-class SVM such that each possible output is mapped to a class, and only the most compatible output is the correct class to choose, but this is unfeasible as the number of possible outputs can tend to infinity.
- If we have a dual-feature extractor $\Psi$ such that it takes in a pair of x and y, and represents the pair in a higher dimension of their compatible features (which is design specific) we can formulate our score function as the dot product between the alignment of the features of x and y (true y) with our learned parameter w that best represents the correct "class" for the output structure.
- $w^{T}\Psi(x,y)$ score will lie somewhere in space, if y is compatible with x then it will be its own "class 1" and if y is incompatible it will be "class 2" and thus is a margin  1 away from the first class in the direction of the normal of the decision boundary w, so we enforce a constraint that all incorrect predictions should be a large margin away from the correct predictions separable in the direction of w $w^{T}\Psi(x,y) - w^{T}\Psi(x,\hat{y}) \geq 1$
- When searching for the most optimal prediction y, we cannot brute force search through all possibilities Y, instead we assume that every y is decomposed into several non-overlapping features, and we try to find the y that has the optimally compatible subparts.
- We want to punish really far away (from the truth) predictions more than closer ones, we have two approaches by doing so in soft SVM (with slack):
	1. Slack rescaling: if the "distance"/"Loss" between the wrong prediction and the truth is large, divide the slack by the loss to achieve lower slack, i.e stricter punishment and larger margin and vice versa.
	2. Margin rescaling: measure the loss between the two predictions and put the margin distance as that loss/distance.
- We can use the Kernel trick between two pairs of mutual features, constructing kernels valid kernels for features maps that involve 2 parameters can follow simple combination rules between valid kernels.
- To apply Anomaly detection using Kernel methods we have three following approaches:
	1. Density estimation: We try to estimate the real data distribution through some model, this model inherently will be able to detect how likely a sample is to belong to the data, thus we if use the negative log of the likelihood we arrive at an outlier score.
		- Lets for example use KDE such that our model corresponds to $p(x) = \frac{1}{Z} \sum\limits_{i=1}^{N}k(x,x_{i})$
		- Which can be interpreted as some dot product in the feature space such that it checks how aligned our point is according to the mean of our observations $< \phi(x), \frac{1}{Z} \sum\limits_{i=1}^{N} \phi(x_{i}) >$
	2. Reconstruction Based: We try to reconstruct the datapoints according to the learned features from our observations, and we check the difference between our point and the reconstruction, if the reconstruction is far from the truth then the features of the datapoint does not align well with our observations and vice versa.
		- Take for example Kernel PCA, the reconstruction error can be given as $o(x) = \| \phi(x) - \sum\limits_{i=1}^{a}u_{i}u_{i}^{T} \phi(x) \|^{2}$ which is the difference between the data and the projection of the data on the first a eigenvecs.
		- In reality this can be simplified to $o(x) = k(x, x^{'}) - \sum\limits_{i=1}^{a} (k(x,X) \cdot V_{:,i} \cdot \lambda_{i}^{-0.5})^{2}$
	3. Boundary based: We try to seperate our positive class from the entirety of space using a decision boundary.
		- We can learn SVDD to describe the data in the minimal containing sphere having the knowledge of a percentage of data we expect to be outliers, the outlier score is then computed according to the distance from the center within a given radius. The problem is that that the experts cannot add their own input in SVDD
		- We can Generalize this hyper-sphere approach to a semi-supervised setting where we have a bunch of labeled data and a bunch of unlabeled data and we have different slack variables for them and different boundary constraints but this is no longer convex! and need gradient descent.
		- One class SVM is also a generalized of SVDD that tries to compare the datapoint in the space of kernels to our learned features and if the features are near the origin then they have values near 0 and the "similarities" are little with the data and thus we seperate the origin from the class with as big a margin as we can
 > [!example]- Anomaly detection Code Snippet
> ![[Machine Learning/Code Snippets#Anomaly Detection]]
## Deep Learning:
This is a quick summary of DL in ML, this will not go into details because everything will be summarized in the DL section on its own.
- Backpropagation algorithm for weights: $\frac{\partial E}{\partial w_{ij}} = \frac{\partial E}{\partial a_{j}}\frac{\partial a_{j}}{\partial z_{j}} \frac{\partial z_{j}}{\partial w_{ij}}$
- Backpropagation algorithm for neurons: $\frac{\partial E}{\partial a_{i}} =\sum\limits_{j} \frac{\partial E}{\partial a_{j}} \frac{\partial a_{j}}{\partial z_{j}} \frac{\partial z_{j}}{\partial a_{i}}$ [[Basics]]
- CNNS are comprised of two essential layers:
	1. The convolution layer which does convolution of a Kernel/weight matrix over the entirety of the input image (its actually cross correlation not convolution) and tries to capture meaningful features in the data using the filters.
	2. The pooling layer which squeezes a neighborhood of pixels into one by either doing average pooling or max pooling, Pooling layers provide translation invariances.[[CNN]]
- GNNs are neural networks that learn the structure of a Graph using a message passing process. This process is done in two steps:
	1. The pooling step which takes in the adjacency matrix multiplied by the representation of the graph from the previous layer
	2. The processing step which then multiplies the result of the pooling step with learnable parameters which are then passed through non-linearity to create a better representation of the current graph.[[Graph NN]]
- MDNs assume the data is made up of some Gaussian mixture model, and the neural network is then trained on predicting the mean and variance of those gaussians that describe the data, alongside some prior alpha that dictates the weight of that gaussians contribution to the dataset. This model then builds the likelihood function and optimizes accordingly.[[Energy Based Models]]
- CRBMs are a variation of RBMS that work on structured output, they take in an input X and its corrosponding label y as binary vectors, and ties them into some binary vector of hidden states, the model then learn the joint data distribution, this is governed by an energy function $E(x,h,y) = -x^{T}Wh -y^{T}Uh$ which can also be transformed into the Free energy function when marginalizing over h $F(x,y) = \sum\limits_{k=1}^{K} log(1 + exp(W_{:k}^{T}x + U_{:k}^Ty))$
- The probability distribution of CRBMs is given by $p(x,y) = \frac{1}{Z} exp(-F(x,y))$ and the generation process entails iterating over values of y and finding the lowest energy (highest probability) one $y|x = argmin_{y}F(x,y)$
- The training procedure to maximize the data likelihood is called contrastive divergence and its models the push pull approach as it takes in a sample that we think belongs to the data distribution and decreases its energy, and takes a random point (that is gotten through gibbs sampling method) and increases its energy, this converges until our model built distribution matches the true probability distribution described by out dataset [[Energy Based Models]]
- The model can sometimes assume that the label is sequential and thus divide the iteration over possible ys into N smaller problems which reduces the computation required.
- In situations where this is not applicable we can train a Generator network that learns to produce good contrastive examples which is trained alongside the discriminator network in order to fool it, similar to the GAN approach.
 > [!example]- Competing Generator network Code Snippet
> ![[Machine Learning/Code Snippets#Energy based models]]