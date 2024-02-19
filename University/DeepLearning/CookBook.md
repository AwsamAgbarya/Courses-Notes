### Back-propagation
* Error Back-propagation w.r.t a specific neuron:
* $$\delta_j =  \frac{\partial \mathcal{E} }{\partial a_j} = \sum_k \frac{\partial \mathcal{E} }{\partial a_k} \frac{\partial a_k}{\partial z_k} \frac{\partial z_k}{ \partial a_j} = \sum_k \delta_k a_k'(z_k)w_{jk}$$
* Error Back-propagation w.r.t a specific weight:
* $$\frac{\partial \mathcal{E}}{\partial w_{jk}} = \frac{\partial \mathcal{E} }{\partial a_k} \frac{\partial a_k}{\partial z_k} \frac{\partial z_k}{ \partial w_{jk}} = \delta_k a_k'(z_k)a_j$$
*  Error Back-propagation w.r.t a specific weight that is shared ( v = wij = wkl ... ):
* $$ \frac{\partial \mathcal{E}}{\partial v} = \frac{\partial \mathcal{E} }{\partial a_k} \frac{\partial a_k}{\partial z_k} (\frac{\partial z_k}{ \partial w_{ij}} + \frac{\partial z_k}{ \partial w_{kl}} ...) $$
* To address drawing a decision boundary for a specific function, write down all combinations of the last hidden layer and the required input in order to achieve that combination.
* The universal approximation theorem It implies that any suitably smooth function can be approximated with any precision using neural networks.
* Number of biases = number of hidden neurons +  number of outputs
* Number of parameters = number of input x number of hidden + number of hidden x number of output
* $$\frac{\partial \cosh x}{\partial x} = \sinh x$$
* $$\frac{\partial sigmoid(x)}{\partial x} = sigmoid(x)-sigmoid(x)^2$$
* $$\frac{\partial Softmax(z_{j})}{\partial z_{i}} = \delta_{ij}S(z_{i}) - S(z_{i})S(z_{j})$$
* $$\frac{\partial \tanh(x)}{\partial x} = 1 - \tanh(x)^2$$
### Backwards Pass
```python
 def forward(self, x):
	"""Computes the forward pass layer by layer. Stores the activation after every layer in self.A.
		x : np.ndarray The input to the neural network of size (batch_size, in_neurons)
		y : np.ndarray The output tensor of size (batch_size, out_neurons)
		"""
	# Input layer
	self.A=[x]
	batches = x
	Y=[]
	# Iterate over all layers of W, Each layer describes the weight connecting between to layers
	for k,w_layer in enumerate(self.W[:len(self.W)-1]):
		activations = []
		# for each batch we compute the weighted sum and activate it via relu and append them to each other
		for batch in batches:
			weighted = batch.dot(w_layer)+self.B[k]
			relu = np.maximum(0,weighted)
			activations.append(relu)
		# store the batches
		batches=activations
		self.A.append(activations)
	# compute the output
	for batch in self.A[-1]:
		Y.append(batch.dot(self.W[-1])+self.B[-1])
		
	return Y
    
    
def backward(self, y, t):
	"""Computes the backward pass of every layer and returns it in reverse order (from back to front).
		y : np.ndarray The output of the neural network of size (batch_size, out_neurons)
		t : np.ndarray The target of size (batch_size, out_neurons)
	"""
	self.DW = []
	self.DB = []
	
	lastLayerLoss = 2 * (y - t) / y.shape[0] # initialize as MSE derivative
	# go through the network in reverse order and compute the gradients
	for i in reversed(range(len(self.W))):
		# compute the gradients
		dloss_dW = np.dot(self.A[i].T, lastLayerLoss)
		dloss_dB = np.sum(lastLayerLoss, axis=0)

		# store the gradients
		self.DW.append(dloss_dW)
		self.DB.append(dloss_dB)

		# compute the gradient for the next layer
		lastLayerLoss = np.dot(lastLayerLoss, self.W[i].T) * self._relu_derivative(self.A[i])

	# reverse the gradients
	self.DW.reverse()
	self.DB.reverse()
```

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
* ##### To help reduce getting stuck at plateaus/ local minima/ saddle points:
	* Avoid parameter symmetry, we will not be able to learn meaningful features
	* Dont initialize weights to 0, we will get stuck at plateaus
	* Dont set the scale of the weights too high due to saturated points in non-linear functions
	* Retrain model multiple times with different initializations and get the best model
	* Preform some sort of learning rate decay in order to jump out of local minima
	* Use a sufficient amount of neurons to not underfit the problem
	* do not go deeper than necessary in terms of layers unless you're using Resnets
* ##### Hessian optimization:
	*  If the hessian is ill-conditioned set the learning rate to something low, it will slow down our learning but its better than the bouncing effect caused by the discrepancy of its eigenvalues
	* Ideally the best learning rate is 0.99x alpha_min / alpha_max
	* Since the hessian is highly correlated to the mean and covariance of the data, we wanna set them as low as possible in order to lower the contribution of the hessian onto our gradient estimation, aka center the data and use some sort of covariance equalization to map it closer to the identity
	* It is not enough to center the data we also have to normalize the data after every activation or by choosing activations that normalize the data for us (centered activations)
	* Use equal number of neurons per layer to keep the layer hessians on the same scale
	* Perform batch normalization between layers to keep the data centered and normalized to reduce the effects of layer hessians, Variance of every layer will be similar if we center our data! which prevents it from exploding
	* connection skipping like in resnets is useful in order to propagate the gradients backward properly and reduce the interactions between parameters stopping them from exploding
* ##### Hessian ill-conditioning combat:
	* Momentum: compute an accumulation of the previous gradients and make a portion of it contribute to the current gradient estimation, not that the effective learning rate depends both on the momentum and lr hyperparameters.
	* Use SGD to converge in phase 1 faster where the gradients are highly corrolated, combined with a learning rate decay to help us converge in phase 2
	* learning rate decay should converge to 0 but its series should converge to infinity
* ##### How to pick the right batchsize:
	* During phase 1 we pick smaller batches because theyre highly correlated, During phase 2 we can pick bigger ones.
	* For rich and diverse datasets we like a larger batch size in order to learn more, for datasets with a lot of redundancies its okay to take smaller ones
	* Batch-size heavily depends on the size of blocks in our architecture
	* Smaller batches offer regularization effects when necessary, Larger Batches = less variance
	* larger batches offer less errors in estimations of gradients especially in second order updating methods
	* Depending on how much computation power you are willing to spend on making truly random batches should be considered
	* do we have a big enough machine to handle this large of a batch?
* ##### Extra tips:
	* dont bottleneck your layers, design them to be somewhat computationally equal
	* Use local connectivity when needed to reduce number of parameters
	* dont make the model too big
	* use parallelization technology to compute matrices for layer wise updates
	* use data parallelism/ Model parallelism for large tasks
		* data parallelism is when you divide the data into different replicas of the model working in parallel
		* model parallelism is when you divide the model into diff layers working in parallel
* $$Variance(x) = E[(x-E(x))(x-E(x))^T]$$
* Variance is expectation of covariance matrix given the mean
* $$E[x x^T] = \sigma^2I + \mu \mu^T = Var(x) + E(x)^2$$
* All eigenvectors are aligned orthogonal to each other
* $$Variance(XY) = E(X)^2Var(Y) + E(Y)^2Var(X) + Var(Y)Var(X)$$
* $$E(XY)= E(X)E(Y)$$
* $$E\left[ \sum Y^{(i)} \right] = \sum E[Y^{(i)}] = nE[Y^{(i)}]$$
* Tanh is approximately linear around x=0 i.e Var(tanh) = Var(z) 
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
* ##### Dataset Bias:
	* The data is over representation a part of the distribution
	* possible in image and text data
	* possible in games
* ##### Finite data:
	* There is not enough datapoints to fully represent the entire distribution
	* simulated and medical data suffer from this
* ##### distribution shift:
	* data was once good but has now shifted due to changed
	* medical and sensor data suffer from this
* ##### How to deal with dataset bias:
	* Crop the feature out before training
	* photoshop them out with noise without adding another feature
	* add them to all classes so that the model is invariant to it
	* check which neurons detect it and kill them
	* Penalize them at the loss function
* ##### How to deal with distribution shifts:
	* use predictive uncertainty whether its by training a bunch of models on diff data or by training a BNN to tell you how confident it is of the prediction
	* Use a domain critic where your model is trying to classify correctly and at the same time trying to represent the data features such that both domains have the same representation
* ##### How to deal with overfitting:
	* Use some feature extractor to reduce dimensionality
	* Choosing appropriate complexity by training a model with changing parameters of regularization and testing it against a validation set to test reality, only stop when the model is getting worse and use the last snapshot of the best model
	* Introduce weight decay that penalizes the size of weights in the loss function making the useless weights tend to 0, this works because the norm of the weights are an upper bound to the gradient of the function and the gradient is much harder to optimize (the weight decay procedure is gradient descent of its norm)
	* introduce dropout that adds bernoulli noise to each neurons
	* Use prior knowledge
* ##### How to deal with finite data:
	* Include prior knowledge in our model by removing features that do not contribute to the solution or encoding them in a way that theyre invariant
	* Use transfer learning by hooking up your model to an already well trained model of a similar problem
* ##### How to deal with adversarial attacks:
	* search for high local variations in the function and remove them
	* generate adversarial attacks and make your model predict them correctly
	* use spectral norm regularization
	* dimensionality reduction
* ##### Transfer Learning:
	* The pre-trained model and the fine-tuning process can be computationally expensive and may require specialized hardware.
	* The pre-trained model may not be well-suited to the second task if the two tasks are vastly different or the data distribution between the two tasks is very different.
	* The potential for negative transfer, where the knowledge from the source task hurts performance on the target task.
	* Transfer learning can lead to overfitting if the model is fine-tuned too much on the second task, as it may learn task-specific features that do not generalize well to new data.
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
* ##### Best loss function for classification is the logloss given by $$log(1+exp(-t\cdot y)$$also called the cross entropy because its equivalent to it
* for Multiple clssess we can use the softmax function to give us probabilities of being a certain class and procceed with cross entropy loss
* ##### for regression the best loss function is the log-cosh which is given by $$\frac{1}{\beta}log\cosh(\beta \cdot (y-t))$$
* For calculating the loss of different costs we use the expected value of such action
* for taking into account quality of labels we define a loss function for each and multiply by scalar
* $$\theta = (\mu,\sigma) \rightarrow \frac{\partial J}{\partial \theta} = \frac{\partial J}{\partial \mu} \frac{\partial \mu}{\partial \theta} + \frac{\partial J}{\partial \sigma} \frac{\partial \sigma}{\partial \theta}$$
### CNN
* Convolution dimension calculation:
* $$\frac{(input - kernal + padding +stride)}{stide}$$
* Receptive field calculation from one layer to another:
* $$r_{l−1}=s_l⋅r_l+(k_l−s_l)$$
* Receptive field calculation using L layers:
* $$RF = \sum_{l=1}^L ((k_l - 1)\Pi_{i=1}^{l-1}S_i) + 1$$
* Self attention is a mehcanism to encode global relations between queries, it compromises of the following steps, get the positionally encoded input, turn it into Keys, Values and Query , multiply the keys and queries with each other in order to get the attention weights, scale it down so it doesnt explode, if you dont want to look ahead mask the latter words, use softmax to generate probabilities, multiply it with the actual values of words and use in NN
* Resnets allow deeper training of NN because they give shorter paths for gradients to flow backwards such that they dont become random noise/vanish/explode, it also allows modelling of the data as block such that relevant data is propagated forward when needed, the model just has to add to it something to make it what we want to predict
* parameter sharing in convolutional neural nets allow:
	* It reduces the total number of parameters, thus reducing overfitting
	* It enables for convolutional layers to be translation invariant.
	* It allows parameters trained for one task to be shared even for a different image-related tasks.
* Pooling layers are what makes CNNs translation invariance

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

### RNNs
* Backwards Pass:
* $$\frac{\partial \mathcal{E}}{\partial \theta} = \sum^T \frac{\partial \mathcal{E}}{\partial y} (\frac{\partial^+y}{\partial \theta} + \frac{\partial y}{\partial h_{t-1}}\frac{\partial h_{t-1}}{\partial \theta})$$
* $$\frac{\partial L}{\partial w} = \frac{\partial L}{\partial y}(\frac{\partial^+ y}{\partial h_2}\frac{\partial^+ h_2}{\partial w} + \frac{\partial y}{\partial h_1}\frac{\partial h_1}{\partial w})$$
* ![[Pasted Image 20240114140554_910.png]]
* How to initialize h0:
	* set it at random such that the RNN will desensitize itself from that noise at each iteration
	* set it to random and run it for a few iterations to learn something useful then reuse that value
* LSTM technology:
	* Forget gate determines how much of the long term memory we want to pass through
	* input gate determines how much of the short term memory we want through
	* the short term memory is normalized through tanh and combined with the long term memory
	* lastly we normalize the new long term memory and we decide what precentage we want to save in our state using the output gate
### Auto-Encoders:
* Sparse encoding used for:
	* Compression
	* Correlating data
	* disentangling components
	* extracting high level semantic features
* Loss function for encoders is the reconstruction cost + sparsity term + Weight restriction 
* Convolutional encoding is when W becomes h convolution filters and the source code are h sparse feature maps
* We use Noise at the start of encoders to make it invariant to small irrelevant variations
* U-nets skip connections allow low level data like spatial information to flow properly for really good reconstruction
* can be used for anomaly detection and video compression and segmentation
* To make auto encoders invariant to rotations we give it randomly rotated versions of the images as input

```python
def encode(self, x):
	# Turning pics into a vector
	x = x.reshape(x.shape[0], -1)
	# xV + b encoding
	z = (x@self.V) + self.b
	# Relu
	return torch.max(torch.zeros(self.V.shape[1]),z)

def decode(self, z):
	# Decoding + turning it back into an image
	return ((z@self.W) + self.a).reshape(z.shape[0], self.d, self.d)
	
def sparsitycheck(x, model):
	# Get source code
    z = model.encode(x)
    # Count the amount of zeros
    count = z[(z==0)]
    return count.shape[0]/z.shape[0]
    
def anomaly_score(x, reconstruction):
    # Norm of reconstruction difference summing over all columns and rows
    return ((reconstruction - x) ** 2).sum(axis=-1).sum(axis=-1)

def get_squared_loss_with_sparisty(x, model):
    lam=0.5
    z = model.encode(x)
    x_rec = model.decode(z)
    # Reconstruction cost
    rec = torch.sum((x - x_rec) ** 2)
    # Sparsity term
    sp = torch.sum(torch.abs(z))
    return (rec + lam * sp) / x.shape[0]

def get_squared_loss_denoising(x, model, noise=0.1):
	# Add noise to x
    x_noisy = x + noise * torch.randn_like(x)
    # generate reconstruction
    x_rec = model(x_noisy)
    # calc loss
    rec = torch.sum((x - x_rec) ** 2)
    return rec / x.shape[0]

```

### Energy Based Models:
* Softmax derivative when i and j aren't known is $$ \delta_{ij}\alpha_i - \alpha_i\alpha_j$$
### Explainable AI
* ##### Activation maximization:
	* Generate the datapoints from the distribution of points that is most likely to activate the neurons that give us the highest probability of the class we want $$\arg\max_x log(p(w_c|x)) + log(p(x))$$
* ##### Attribution Using shapley Vlaues:
	* Use the rewritten shapley value formula $$ \phi_i = \frac{!}{d!}\sum [f(x_{afterEqual(S,i)} - f(x_{After(S,i)}]$$
	* To sample t times for the set of all possible subsets S
* ##### Attribution Using LRP:
	* Use LRP formulas to propagate the contribution in one backwards pass
		* LRP-0: makes a weighted normalized sum of all activations times their contribution
		* LRP-epsilon is the same but it has an epsilon to absorb some relevance making smaller contributions irrelevant and only bigger ones important
		* LRP-gamma: We make it focus on the positively affecting weights
	* Composite LRP: 
		* Use LRP-0 at top layers cause its more accurate but least understandable
		* Use LRP-epsilon at middle layers because its nor sparse enough to be understandable but it removes a lot of the noise
		* use LRP-gamma at bottom layers because its most understandable to humans and densly highlighted
	* Pros:
		* Flexible due to hyper parameters
		* Good quality on depe netowkrs
		* fast
	* Cons:
		* Model has to actually solve the function properly
		* not adaptive to new architecture
		* need to choose hyper parameters correctly