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
* Holdout selection:
	* design multiple models with multiple complexities, decide on the simplest model that has the highest accuracy by testing it on some validation test to simulate the true accuracy
	* partition data in k partitions, iterate over partitions, train the model on the rest of the data and test it with that partition, then combine all the losses from all the partition tests
* Bias: $$E[\hat{\mu} - \mu]$$
* Variance: $$E[(\hat{\mu} - E[\hat{\mu}])^2] = E[\hat{\mu}^2] - E[\hat{\mu}]^2$$
* MSE: $$E[(\hat{\mu} - \mu)^2] = Var + Bias^2$$
