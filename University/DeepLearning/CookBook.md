### Backpropagation
* To address drawing a decision boundary for a specific function, write down all combinations of the last hidden layer and the required input in order to achieve that combination.
* The universal approximation theorem It implies that any suitably smooth function can be approximated with any precision using neural networks.
* Number of biases = number of hidden neurons +  number of outputs
* Number of parameters = number of input x number of hidden + number of hidden x number of output
* $$\frac{\partial \cosh x}{\partial x} = \sinh x$$
* $$\frac{\partial sigmoid(x)}{\partial x} = sigmoid(x)-sigmoid(x)^2$$
* $$\frac{\partial Softmax(z_{j})}{\partial z_{i}} = \delta_{ij}S(z_{i}) - S(z_{i})S(z_{j})$$
* $$\frac{\partial \tanh(x)}{\partial x} = 1 - \tanh(x)^2$$
```python
# array for logging the losses
loss_log = []
# Identifying how many batches it requires
N = len(X)
batch_it = N // batch_size
# Defining the model
SGD_model = torch.nn.Sequential(
			torch.nn.Linear(dim_in, dim_h),
			torch.nn.ReLU(),
			torch.nn.Linear(dim_h,dim_out),
			)
# Defining loss
loss_func = torch.nn.MSELoss()
# Defining the optimizer (can be done with momentum or weight decay)
SGD = torch.optim.SGD(model.parameters(), lr=lr)

# Iterating over epochs
for epoch in range(num_epochs):
	epoch_loss = 0.0
	# Permute the data
	permutation = torch.randperm(N)
	X = X[permutation]
	y = y[permutation]
	# iterate over all batches
		for i in range(batch_it):
		# get range of current batch
		X_batch = X[i * batch_size: (i + 1) * batch_size]
		y_true = y[i * batch_size: (i + 1) * batch_size].reshape(-1,1)
		# Clear the gradient
		SGD.zero_grad()
		# comput the result and compare it with the truth given the loss function
		loss = loss_func(model(X_batch),y_true)
		# calculate the gradient
		loss.backward()
		# adjust weights
		gradient_descent.step()
		# Add loss to the epoch loss
		epoch_loss += loss.item()
	# Add average loss per point to history    
	loss_log.append(epoch_loss / batch_it)
```

### Optimization
* $$Variance(x) = E[(x-E(x))(x-E(x))^T]$$
* Variance is expectation of covariance matrix given the mean
* $$E[x x^T] = \sigma^2I + \mu \mu^T = Var(x) + E(x)^2$$
* The hessian depends on the variance and the mean!! hence we need to center it
* All eigenvectors are aligned orthogonal to each other
* centering makes the condition number lower!
* $$Variance(XY) = E(X)^2Var(Y) + E(Y)^2Var(X) + Var(Y)Var(X)$$
* $$E(XY)= E(X)E(Y)$$
* $$E\left[ \sum Y^{(i)} \right] = \sum E[Y^{(i)}] = nE[Y^{(i)}]$$
* Tanh is approximately linear around x=0 i.e Var(tanh) = Var(z) 
* Variance of every layer will be similar if we center our data! which prevents it from exploding
* Larger Batches = less variance
* Well conditioned = easier to escape local minima
* Normalization + choice of activation function = easier to escape local minima
* Adam combines RMSPROP and Adagrad
* RMSPROP is Stochastic gradient descent algorithm that
	* uses of a moving average of the squared gradients to scale the learning rate for each parameter (Momentum)
* ADAGrad
	* is an algorithm for gradient-based optimization. The learning rate is adapted component-wise to the parameters by incorporating knowledge of past observations
* Adam does not guarantee convergence to global minima
* Adam calculates an exponential moving average of the gradient and the squared gradient.
* The initial value of β1 and β2 values close to 1.0 result in a bias of moment estimates towards zero.
* Higher momentum values doesnt always lead to better convergence and faster training.
* Gradient descent algorithm with momentum is likely to skip local minima.
* Adam divides the gradient by an estimate of its second gradient per dimension

### Regularization 

* Frobenius Norm
* $$\|M\|_f =\sqrt{ \sum_i \sum_j | v_{ij} |^2}$$
* Mixed norm
*  $$\|M\|_f =\sqrt{ \sum_i (\sum_j | v_{ij} |)^2}$$
* Cauchy Schwarz Inequality
* $$|x \cdot y| \leq \|x\| \|y\|$$
* $$|x \cdot y|^2 \leq \|x\|^2\|y\|^2$$
* Some inequality proven by induction
* $$(\sum_j | v_{ij} |)^2 \leq h\sum_j | v_{ij} |^2$$
* Using Cauchy
*  $$(\sum_j 1*| v_{ij} |)^2 \leq \sum_j 1^2 \sum_j | v_{ij} |^2$$
* $$|1\cdot v|^2 \leq \|1\|^2 \|v\|^2$$

### Loss Functions

* $$\theta = (\mu,\sigma) \rightarrow \frac{\partial J}{\partial \theta} = \frac{\partial J}{\partial \mu} \frac{\partial \mu}{\partial \theta} + \frac{\partial J}{\partial \sigma} \frac{\partial \sigma}{\partial \theta}$$
### CNN
* Convolution dimension calculation:
* $$\frac{(input - kernal + padding +stride)}{stide}$$
* Receptive field calculation from one layer to another:
* $$r_{l−1}=s_l⋅r_l+(k_l−s_l)$$
* Receptive field calculation using L layers:
* $$RF = \sum_{l=1}^L ((k_l - 1)\Pi_{i=1}^{l-1}S_i) + 1$$
* parameter sharing in convolutional neural nets allow:
	* It reduces the total number of parameters, thus reducing overfitting
	* It enables for convolutional layers to be translation invariant.
	* It allows parameters trained for one task to be shared even for a different image-related tasks.

* Convolution Layer:
```python
def forward(self, x:torch.Tensor):
	# Initialize the parameters
	W = self.W
	b = self.b
	k = W.shape[0]
	# calculate output size
	steps = int((x.shape[1]-k))+1
	y = torch.empty((1,steps,steps))
	
	for i in range(steps):
		for j in range(steps):
			# one output of a convolution is =
			# x from 0->k * W summed up + b
			y[0,i,j] = (x[0,i:i+k,j:j+k]*W).sum() + b
	return y
```
* Max pooling layer:
```python
def forward(self, x:torch.Tensor):
	# Calculate output size
	steps = int((x.shape[0]-self.kernel_size)/self.stride)+1
	# over both dimensions, take x 0*s->kernel*s and take the max
	y = torch.tensor([x[i*self.stride:i*self.stride+self.kernel_size,j*self.stride:j*self.stride+self.kernel_size].max() for i in range(0,steps) for j in range(0,steps)])
	return y.reshape(steps,steps)
```
* Self Attention Layer:
```python
def forward(self, x, y):
	# Get the matrices
	K, Q, V = self.get_key_query_value(x, y)
	d = (self.w_kq.shape[1])**0.5
	# Comput the weights (normalized)
	qk = Q@(K.T)/d
	# Use softmax to turn into probability
	attention_weights = nn.functional.softmax(qk,dim=1)
	# compute weighted sum
	output=attention_weights@V
	return output, attention_weights

def get_key_query_value(self, x, y):
	# K = x*W
	K = x@self.w_kq
	# Q = y*W
	Q = y@self.w_kq
	# V = x
	V = x
	return K, Q, V
```