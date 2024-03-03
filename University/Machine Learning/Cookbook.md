### Bayes Decision Theory:
* Optimal classifier : $$\arg\max_j log(P(x|w_j)) + log(P(w_j))$$
* Non-Numerical Data: $$ P(x|w_{ij}) = \Pi_{i=1}^d \left[q_{ij}x_i + (1-q_{ij})(1-x_i)\right]$$
* Minimum Cost: $$\lambda(\alpha_k|x) = \sum_{j=1}^C \lambda(\alpha_k |w_j) P(w_j|x)$$
* Bayes Error rate: $$P(Err) = \int P(Err|x) p(x)dx = \int min \left[P(w_j|x)\right]p(x)dx$$
### Maximum Likelihood
* To find the maximum of a function, make sure its concave/turn it into concave (by using log) and find the point at which the gradient becomes 0
* if the second derivative of a function is negative definite then it is always concave
* a negative definite square matrix is a matrix if multiplied by a vector by both sides will always result in a negative number
* Parameter estimation in general: $$\arg\max_{\theta} \prod_{k=1}^N p(x_k | \theta)$$
* Mu estimation in a Gaussian distribution is the empirical mean: $$ \frac{1}{N} \sum_{k=1}^N x_k$$
### Bayesian estimator
* Distribution describing our parameter space: $$ p(\theta |D) = \frac{p(D|theta) p(\theta)}{\int_{\theta} p(D|\theta) p(\theta)}$$
* Data generating distribution: $$p(x|w_i, D_i) = \int p(x, \theta_i) p(\theta_i | D) d\theta_i$$
* Classifier: $$\arg\max P(w_i |x,D) = \arg\max p(x|w_i,D)P(w_i)$$
* Multivariate Gaussian mean estimation: $$ \mu_n = \frac{n\sigma_n^2}{\sigma^2}\hat{\mu} + \frac{\sigma_n^2}{\sigma_0^2}\mu_0$$
* with confidence of: $$\sigma_n^2 = \left( \frac{n}{\sigma^2} + \frac{1}{\sigma_0^2 }\right)^{-1}$$
### Fischer's Discriminant
* We want to maximize the between class ratio and minimize the within class ration in projective space :$$J(w) = \frac{w^TS_Bw}{w^TS_w w} = \arg\max_w w^TS_Bw \text{ , } w^TS_ww = 1$$
* Between Class matrix: $$S_B =(\mu_2 - \mu_1)(\mu_2 - \mu_1)^T $$
* Within Class matrix: $$S_W = S_1+S_2 = \sum_i \sum_k(x_k - \mu_j)(x_k - \mu_j)^T$$
* Final w solution if S_w is inveritble: $$w = S_w^{-1}(\mu_2 - \mu_1)$$
### Principal Component Analysis
*  PCA can be interpreted as a linear Auto-encoder
* Data needs to be centered and cleared of outliers for this method to work
* Minimum noise min distance(original-projection): $$\arg\min_w \left[\frac{1}{N}\sum_{k=1}^N \|x-ww^t\|^2 \right]$$
* Maximum variance of projected data max sum( positive length of projection): $$\arg\max_{\|w\|^2=1} \left[w^T \hat{\Sigma}w\right]$$
* Covariance is a Gram matrix:
	* All its eigenvalues are positive
	* Its trace is the sum of its eigenvalues
	* its diagonizable
	* all its eigenvectors are orthogonal to each other
	* symmetrical
* SVD Is factorizing a matrix M as UAV such that U contains the eigenvectors of MM^T and U contains the roots corresponding eigenvectors on the diagonal
* PCA using POWIT:
```
Cov = 1/N * Data * Data^T
for i in k:
	w = random_unit_norm
	for i in t:
		w = (Cov*w).normalize()
	save w
	Cov = Cov - w*w.T*Cov
```

### SVM:
* Hinge Loss: $$max( 0,1-y_i(wx_i +b))$$
* Primal problem: $$min_{w,b} \frac{1}{2} \|w\|^2 \text{ such that } y_i(wx_i+b) \geq 1 \text{ }\forall i \in \{1...N\}$$
* Dual problem Formulation: $$\max_{\alpha_i \geq 0} min_{w,b} \mathcal{L}(w,b,\alpha)$$
* Initial Dual problem reformulation: $$ \max_{\alpha_i \geq0} \left[-\frac{1}{2} \sum_{\text{ Pair of SV }} \alpha_i \alpha_j y_i y_j x_i^T x_j + \sum_{SV} \alpha_i\right]$$
* Conditions of the dual problem without slack: $$\sum_i^N \alpha_i y_i = 0 $$
* Recovering w: $$w = \sum_i^N \alpha_i y_i x_i$$
* Primal Problem in Kernel space + Slack: $$min_{w,b} \frac{1}{2} \|w\|^2 +C\sum_i^N \epsilon_i\text{ such that } y_i(wx_i+b) \geq 1-\epsilon_i \text{ and } \epsilon_i \geq 0 \text{ }\forall i \in \{1...N\}$$
* Dual problem reforumlation: $$ \max_{\alpha_i \geq0} \left[-\frac{1}{2} \sum_{\text{ Pair of SV }} \alpha_i \alpha_j y_i y_j k(x_i,x_j) + \sum_{SV} \alpha_i\right]$$
* Conditions of the dual problem with slack: $$\sum_i^N \alpha_i y_i = 0 \text{ and } C \geq \alpha_i \geq 0$$
* Recovering b: $$b = y_i - w^T\phi(x_i)$$
* Classifier: $$f(x) = sign \left(\sum_i^N \alpha_i y_i k(x,x_i) + b \right)$$
* VC dimension: $$d \leq min\{[R^2 \|w\|^2] + 1 , n+1 \}$$
* Mercer Kernels / Representer theorem: $$k(x,y) = \langle \phi(x) , \phi(y) \rangle$$
* Mercer's condition: $$\sum_i^n \sum_j^n c_i c_j k(x_i,x_j) \geq 0$$
* Inner product properties:
	* Positive definite  <x,x> >= 0 for every x and only is 0 if x=0
	* conjugate symmetric <x,y> = <y,x> if we are dealing with real numbers
	* conjugate Linear <x,y1 +y2> = <x,y1> + <x,y2> or <x,cy> = c<x,y>

### Model Selection
- Bias Variance Tradeoff:
	- High Bias = a lot of assumptions = Underfitting data
	- Linear models have higher bias than nonlinear models
	- High Variance = a lot of variations in the output = does not generalize = leads to overfitting
	- Biased estimator can be used in high dimensional data to trade off lower variance
	- Biased estimator make the model less sensitive to training data
* Holdout selection:
	* design multiple models with multiple complexities, decide on the simplest model that has the highest accuracy by testing it on some validation test to simulate the true accuracy
	* partition data in k partitions, iterate over partitions, train the model on the rest of the data and test it with that partition, then combine all the losses from all the partition tests
* Bias: $$E[\hat{\mu} - \mu]$$
* Variance: $$E[(\hat{\mu} - E[\hat{\mu}])^2] = E[\hat{\mu}^2] - E[\hat{\mu}]^2$$
* MSE: $$E[(\hat{\mu} - \mu)^2] = Var + Bias^2$$
### Neural Networks [[DeepLearning/CookBook|CookBook]]

### Trees and Forests
*  Gini Index: $$\sum_i^{\text{\#children}} \frac{\text{\#Total Records going to that child}}{\text{\#Total Records}} * \left(1 - \sum_j^{\text{\#Classes in node}} \frac{\text{\#Belonging to class j}}{\text{\#Total records in child}}^2 \right)$$
* Entropy: $$\sum log(\frac{1}{p(X)})p(x)$$
* Information Gain: $$IG(T) = H(T) - \sum_{children}\frac{\text{points in child}}{\text{total}}H(\text{child}) $$
* Building a tree:
	* Build a very complex tree according to your splitting metric
	* Trim the trees that contribute the least in reducing the cost to get lower complexity

* Build a forest: (Bagging)
	* Draw random samples with duplicates from training data
	* Build a minimum size tree:
		* pick m features at random
		* pick best split variable
		* split accordingly
	* Combine their predictions!

### Boosting
* Adaboost:
	* start with 1/N weights
	* Train a weak base learner which gives you your initial hypothesis h1
	* calculate the error by summing over all the weights of the incorrectly classified points
	* the influence of this hypothesis is then $$\alpha_t = \frac{1}{2} log\frac{1-\epsilon_t}{\epsilon_t}$$
	* Update the weights and normalize them: $$w_i^{(t+1)} = \frac{W_i^{t} e^{-\alpha_i y_i h_t(x_i)}}{\sum W_i^{t} e^{-\alpha_i y_i h_t(x_i)}}$$
	* make a prediction: $$f_{\alpha}(x_i) = \sum_t \alpha_t h_t(x_i)$$
	* Add slack variables (Optional): $$C_n = C(\sum_r \frac{\alpha_r}{\|\alpha\|_1} W_n^r)$$

### Clustering
* Cluster algorithm:
	1) Firstly we initialize the initial cluster means (by assigning them to K random points)
	2) We split up all datapoints according to the closest center to it$$S_k = \{ x_n : \|x_n - \mu_k\|^2 \leq \|x_n - \mu_l \|^2, \text{for every l} \in \{1..K\} \} $$
	3) we calculate the means of the resulting clusters and update our mean values $$\mu_k = \frac{1}{\|S_k\|} \sum_{x_n \in S_k} x_n $$
	4) Iterate over 2 and 3 until we converge to a local minimum

* Likelihood of the data given GMM model: $$\prod_{n=1}^N \sum_{k=1}^K \mathcal{T}_k p_k(x_n | \mu_k \Sigma_k)$$
## Expectation Maximization
* Algorithm:
	* Firstly we initialize the initial cluster variables
	*  EXPECTATION: we try to optimally find our latent variable Z by computing the membership probabilities given the current parameters which are treated as constant for this step $$q^{(t)} (z_{nk}) = p (z_{nk} = 1 | x_n, \theta^{(t)} ) = \frac{p (x_n | z_{nk} , \theta^{(t)}) p( z_{nk}, \theta^{(t)} )}{ p{(x_n | \theta{(t)} )}} = \frac{\mathcal{T_k^{(t)}} p_k (x_n | \mu_k^{(t)} , \Sigma_k^{(t)} ) }{\sum_{I=1}^K \mathcal{T_I^{(t)}} p_I (x_n | \mu_k^{(I)} , \Sigma_l^{(I)} ) }$$
	* MAXIMIZATION: according to our naive assumption of membership, update the parameters theta such that they reflect it better $$\mathcal{T_k^{(t+1)}} = \frac{1}{N} \sum_{(n=1)}^N q^{(t)} (z_{nk})$$ $$ \mu_k^{(t+1)} = \frac{1}{N_{\mathcal{T_k^{(t+1)}}}} \sum_{n=1}^N q^{(t)} (z_{nk}) x_n$$ $$\Sigma_k^{(t+1)} = \frac{1}{N_{\mathcal{T_k^{(t+1)}}}} \sum_{n=1}^N q^{(t)} (z_{nk}) (x_n - \mu_k^{(t+1)})(x_n - \mu_k^{(t+1)})^T$$
* Lower Bound we are optimizing $$\sum_z q(z) log \left[ \frac{p(X,z|\theta)}{q(z)} \right]$$
### Linear Regession
* Linear Regression model $$y = w^T x$$
* minimizing error $$ w = (XX^T)^{-1} Xy$$
### Kernel Ridge Regression
* Model $$y = w^T \phi(x)$$
* Minimizing the error $$w = (\phi(X)\phi(X)^T + \lambda I)^{-1} \phi(X)y$$
* Rewritten as $$y = k^* ( K+\lambda I)^{-1}y$$
### Gaussian Process:
* Prior: $$p(x) = \mathcal{N}(0,k(x_i,x_j) +\sigma^2 \delta_{ij})$$
* Training Process $$\begin{bmatrix} y \\ y^* \end{bmatrix} = \mathcal{N}(0, \begin{bmatrix}k(X,X)+ \sigma^2 I & k(X,x^*) \\ k(x^*,X) & k(x^*,x^*) \end{bmatrix})$$
* Predicting: $$p(y*|y) = \mathcal{N}\left(k^* (K+ \sigma^2 I)^{-1}y , k^{**} - k^* (K+ \sigma^2 I)^{-1} k^{*T} \right)$$

### Explainable AI
##### Activation maximization:
* Generate the datapoints from the distribution of points that is most likely to activate the neurons that give us the highest probability of the class we want $$\arg\max_x log(p(w_c|x)) + log(p(x))$$
* ##### Attribution Using shapley Vlaues:
	* Use the rewritten shapley value formula $$ \phi_i = \frac{!}{d!}\sum [f(x_{afterEqual(S,i)} - f(x_{After(S,i)}]$$
	* To sample t times for the set of all possible subsets S
* ##### Taylor Expansions $$f(x) = f(\hat{x}) + \sum_i^d [\nabla f(\hat{x})]_i \cdot (x_i - \hat{x}_i) + ....$$
* ##### Attribution Using LRP $$R_j = \sum_k \frac{a_jw_{jk}}{\sum_{0,j} a_j w_{jk}} R_k$$