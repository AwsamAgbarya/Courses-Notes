### Bayes Decision Theory:
* Optimal classifier : $$\arg\max_j log(P(x|w_j)) + log(P(w_j))$$
* Non-Numerical Data: $$ P(x|w_{ij}) = \Pi_{i=1}^d \left[q_{ij}x_i + (1-q_{ij})(1-x_i)\right]$$
* Minimum Cost: $$\lambda(\alpha_k|x) = \sum_{j=1}^C \lambda(\alpha_k |w_j) P(w_j|x)$$
* Bayes Error rate: $$P(Err) = \int P(Err|x) p(x)dx = \int min \left[P(w_j|x)\right]p(x)dx$$