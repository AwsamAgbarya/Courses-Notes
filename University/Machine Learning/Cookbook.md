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