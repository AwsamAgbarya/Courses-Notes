---
tags:
  - DeepLearning
  - Programming
---
The following note will have relevant code snippets from some basic machine learning concepts alongside some basic python reminders!
## Torch Basics:
**Array initialization:**
```python
torch.FloatTensor(a.shape) # Allocate space
torch.zeros(a.shape) # zeros
```

**Useful torch functions:**
```python
values, indices = torch.sort(a, descending=True) # sorts
torch.clamp(a,min=b, max=c) # clip values
torch.cat(a,b) # concatenate
torch.unique(a) # np.unique
torch.softmax(x) # softmax function
a.item() #returns the actual value of a 1 element tensor
torch.manual_seed(0)# Testing randomness with a seed
```

**Reshaping:**
```python
torch.permute(a, (0,1,2)) # transpose
a.view(1,-1,1) # reshape
A.ravel() #turns the array into one dimensional (flatten)
a.unsqueeze(0) # expand dimensions
```
**NN layers:**
```python
nn.Sequential(
	nn.Linear(in_dim, out_dim),
	nn.ReLU(),
	nn.BatchNorm2d(num_features=out_channels),
	nn.Conv2d(in_channels, out_channels=out_channels, kernel_size=kernel, stride=stride),
	
)
```
## Famous Toy Datasets:
**FashionMNIST:**
```python
data_root = './data'
train_dataset = FashionMNIST(data_root, train=True,download=True, transform=T.ToTensor())
test_dataset = FashionMNIST(data_root, train=False,download=True, transform=T.ToTensor())
```
## Processing tasks:
**Saving a model:**
```python
# save model after each epoch
os.makedirs('models', exist_ok=True)
torch.save(model.state_dict(), f'models/model_{k}.pt')
model.load_state_dict(torch.load(f'models/model_{k}.pt'))
model.eval() # put it in eval mode in order to not do extra computation (freeze)
```
**Training bar:**
```python 
from tqdm.auto import tqdm
from torch.utils.data import DataLoader

train_loader = DataLoader(train_dataset, batch_size=1024, shuffle=True)
# ITERATION
for x, y in tqdm(train_loader):
# Or at once
x, y = next(iter(dl))
```
**Accuracy function:**
```python
@torch.no_grad()
def accuracy(model: torch.nn.Sequential, data_loader: DataLoader) -> [float, float]:
	count = 0
	num_correct = 0

	for x, y in data_loader:
		logits = model(x)
		yh = torch.argmax(logits, dim=1)
		num_correct += (y==yh).float().sum()
		count += x.shape[0]
	return float(num_correct / count)
```
**In-painting missing patch:**
```python
def removepatch(X):
	mask = torch.zeros(len(X),28,28)
	for i in range(len(X)):
		j = numpy.random.randint(-4,5)
		k = numpy.random.randint(-4,5)
		mask[i,11+j:17+j,11+k:17+k] = 1
	mask = mask.view(len(X),784)
	return (X*(1-mask)).data,mask
```
**Transformations:**
```python
from torchvision.transforms import v2
raffine = v2.RandomAffine(degrees=(-15, 15), translate=(0.1, 0.1), scale=(0.8, 1.1))
elastic_transformer = v2.ElasticTransform(alpha=20.0, sigma=6.0)
random_transform = v2.RandomApply(transforms=torch.nn.ModuleList([raffine, elastic_transformer]), p=0.9)
# Or composed into one
v2.Compose(
	[v2.RandomResizedCrop(28, scale=(0.1, 1.0), interpolation=v2.InterpolationMode('bicubic')),
	 v2.RandomHorizontalFlip(),
	 v2.ToTensor(),
	 v2.Normalize((0.5,), (0.5,))
])

# To add to a torchvision dataset we need to define a class
class ViewTransform(object):
	# two views from the image x and return them as tuple
	def __call__(self, x):
		return (augment(x).float(), augment(x).float())

dataset.transform = ViewTransform()
```
 **Contour loss Trajectory :**
 ```python
 def plot_loss_surface_toy(loss_func):
	l = 4
	x = np.linspace(-l, l, 100)
	y = np.linspace(-l, l, 100)
	
	X, Y = np.meshgrid(x, y)
	fig = plt.figure()
	Z = loss_func(torch.stack([torch.tensor(x.flatten()).float() for x in [X, Y]]).T).reshape(X.shape)
	
	plt.contourf(X, Y, Z, cmap='viridis', levels=25)
	plt.ylim(-l,l)
	plt.xlim(-l,l)

def trajectory_plot(loss_func, optim, optim_kwargs, bs=0, nsteps = int(5e2)):
	model = ML_Model()
	optim_ = optim(model.parameters(), **optim_kwargs)
	param_traj = [list(model.params[0].detach().cpu().numpy())]
	
	for i in range(nsteps):
		train_loss = loss_func(model.params)
		train_loss.backward()
		optim_.step()
		model.zero_grad()
		param_traj.append(list(model.params[0].detach().cpu().numpy()))
		
		#if ((i + 1) % max(nsteps//10, 1)) == 0:
		# print(f"Epoch {i + 1} trainloss {train_loss.item():.2e}")
	plt.plot(*np.asarray(param_traj).T, alpha=0.9)
	return model.params
	```
**Numerical Integration:**
```python
import matplotlib.pyplot as plt
import numpy as np
from numpy.typing import ArrayLike
from scipy.integrate import solve_ivp # import ODE solver from SciPy

n_states = 2
n_steps = 501
# Define time interval of integration
t0 = 0.0; te = 15.0
tspan = (t0, te)
t_traj = np.linspace(t0, te, n_steps)
# Initial condition
u0 = np.array([1.0, 1.0])
# Define dynamics
def f_true(_t: float, u: ArrayLike) -> ArrayLike:
	return np.array([1.5 * u[0] - 1.0 * u[0] * u[1], 3.0 * u[0] * u[1] - 1.0 * u[1]])

#ODE solve
sol = solve_ivp(f_true, (t0, te), u0, t_eval=t_traj)
#Plot
fig, ax = plt.subplots()
u_traj = sol.y
# Plot trajectory that generated data
ax.plot(t_traj, u_traj[0, :], label="$u_1(t)$")
ax.plot(t_traj, u_traj[1, :], label="$u_2(t)$")
ax.legend(loc="best")
ax.set_xlabel("$t$")
ax.grid()
```
## Neural Networks:
**Basic MLP :**
```python
class ReluMLP(nn.Module):
	def __init__(self, in_neurons=4, hidden_neurons = [6, 8, 6], out_neurons=1):
		super(ReluMLP, self).__init__()
		self.layer_list = nn.ModuleList()
		
		if not hidden_neurons:
			self.layer_list.append(nn.Linear(in_neurons, out_neurons))
			return
		# Input layer
		self.layer_list.append(nn.Linear(in_neurons, hidden_neurons[0]))
		self.layer_list.append(nn.ReLU())
		# Hidden layers
		for i in range(len(hidden_neurons) - 1):
			self.layer_list.append(nn.Linear(hidden_neurons[i], hidden_neurons[i + 1]))
			self.layer_list.append(nn.ReLU())
		# Output layer
		self.layer_list.append(nn.Linear(hidden_neurons[-1], out_neurons))

	def forward(self, x):
		for __, l in enumerate(self.layer_list):
			x = l(x)
		return x

def train_mlp(model, X, y, num_epochs=3, batch_size=10, lr=0.001):
	assert len(X) >= batch_size
	loss_log = []
	N = len(X) # Num of datapoints
	batch_it = N // batch_size 	# Num of batches

	# Initialize stochastic gradient descent and MSE loss
	loss_func = torch.nn.MSELoss()
	gradient_descent = torch.optim.SGD(model.parameters(), lr=lr)
	
	model.train()
	
	for epoch in range(num_epochs):
		epoch_loss = 0.0
		
		# Permute the data
		permutation = torch.randperm(N)
		X = X[permutation]
		y = y[permutation]
		
		for i in range(batch_it):
			X_batch = X[i * batch_size: (i + 1) * batch_size]
			y_true = y[i * batch_size: (i + 1) * batch_size].reshape(-1,1)
			
			# Compute forward pass, loss and backward pass
			gradient_descent.zero_grad()
			
			loss = loss_func(model(X_batch),y_true) # Compute Forward pass + loss
			loss.backward() # Compute backward pass
			gradient_descent.step() # adjust parameters
			
			# Add loss to the epoch loss
			epoch_loss += loss.item()
			
		# Add average loss per point to history
		loss_log.append(epoch_loss / batch_it)
	
	return loss_log
```

**Generating Adversarial attacks:**
```python
single_img = test_dataset[2][0]

def adversarial_attack(original, model, target=1):
	perturbed = original.clone().requires_grad_() # Cloning our image for pertubation
	wanted_label = torch.Tensor([target]).long() # Label we want to make it predict
	
	# Set up SGD with learning-rate 1
	optim = torch.optim.SGD((perturbed,), lr=1)
	
	# Set up criterion
	criterion = nn.CrossEntropyLoss() # Loss
	pred = model(perturbed.reshape(1, 784)) # Models prediction
	pred_label = pred.argmax()
	counter = 0
	model.eval()
	
	# As long as the prediction_label is not target, do gradient descent on the sample
	while not pred_label == wanted_label:
		# Predict
		pred = model(perturbed.reshape(1, 784))
		pred_label = pred.argmax()
		# See loss from wanted label and take a step backwards
		loss = criterion(pred, wanted_label)
		loss.backward()
		optim.step()
		optim.zero_grad()
	
		counter += 1
		if counter > 50000:
			print('Not Converging')
			break
	
	# To here ------------------------------------------------
	
	fig, ax = plt.subplots(1, 3)
	show_single_image(original, ax[0])
	ax[0].set_title(f'Orig. Pred {model(original.reshape(1, 784)).argmax()}')
	show_single_image(perturbed, ax[1])
	ax[1].set_title(f'Orig. Pred {model(perturbed.reshape(1, 784)).argmax()}')
	show_single_image(perturbed - original, ax[2])
	ax[2].set_title(f'Perturbation L2: {torch.norm(perturbed - original):.1f}')
	model.train()
	
	return perturbed
```

## SimCLR:
[[CookBook2#Representation learning]]
```python
def simclr_loss(z1, z2):
	tau = 0.1
	N = z1.shape[0]
	# Matrix of size (2048,32) which is basically z1 and z2 concatenated horizontally
	z = torch.cat((z1,z2),0)
	# Matrix of size (2048,2048) which is each view's cosine similarity with every other view
	similarity = torch.exp(torch.nn.functional.cosine_similarity(z[:,None,:],z[None,:,:], dim=2)/tau)
	
	numerator = torch.cat((torch.diagonal(similarity,offset=N),torch.diagonal(similarity,offset=-N)),0)
	similarity = similarity - torch.diag(torch.diagonal(similarity))
	denominator = torch.sum(similarity,axis=0)
	
	return -1/(2*N) * torch.sum(torch.log(numerator/denominator))
```

## Transformers:
[[CookBook 2#Transformers]]
**DistillBert Tokenizer:**
```python
from transformers import AutoTokenizer
# model = AutoModelForSequenceClassification.from_pretrained("distilbert-base-uncased-finetuned-sst-2-english")
tokenizer = AutoTokenizer.from_pretrained("distilbert-base-uncased")
sentence = "This was one of the best movies I have ever seen."
inputs = tokenizer(sentence, return_tensors = 'pt')
subtokens = tokenizer.convert_ids_to_tokens(list(inputs['input_ids'].squeeze()))
```
**Embedding layer:**
```python
class Embeddings(nn.Module):
	def __init__(self, config):
		super().__init__()
		self.word_embeddings = nn.Embedding(config.vocab_size, config.dim, padding_idx=config.pad_token_id)
		self.position_embeddings = nn.Embedding(config.max_position_embeddings, config.dim)
		self.LayerNorm = nn.LayerNorm(config.dim, eps=config.eps)

	def forward(self, input_ids: torch.Tensor) -> torch.Tensor:
		"""
		Parameters:
		input_ids (torch.Tensor):
		torch.tensor(bs, max_seq_length) The token ids to embed.
		Returns: torch.tensor(bs, max_seq_length, dim) The embedded tokens (plus position embeddings)
		"""
		# Embedding the input ids into the dictionary
		input_embeds = self.word_embeddings(input_ids) # (bs, max_seq_length, dim)
		seq_length = input_embeds.size(1)
		
		# Creating and embedding the position ids
		position_ids = torch.arange(seq_length, dtype=torch.long, device=input_ids.device) # (max_seq_length)
		position_ids = position_ids.unsqueeze(0).expand_as(input_ids) # (bs, max_seq_length)
		position_embeddings = self.position_embeddings(position_ids) # (bs, max_seq_length, dim)
		
		# Compute the output embeddings
		embeddings = input_embeds + position_embeddings # (bs, max_seq_length, dim)
		embeddings = self.LayerNorm(embeddings) # (bs, max_seq_length, dim)
		
		return embeddings
```
###### Attention Block:
```python
class AttentionBlock(nn.Module):
	
	def __init__(self, config):
		super().__init__()
		self.config = config
		# self-attention components
		self.q_lin = nn.Linear(in_features=config.dim, out_features=config.all_head_size)
		self.k_lin = nn.Linear(in_features=config.dim, out_features=config.all_head_size)
		self.v_lin = nn.Linear(in_features=config.dim, out_features=config.all_head_size)
		# res-net Normalization
		self.out_lin = nn.Linear(in_features=config.dim, out_features=config.dim, bias=True)	
		self.sa_layer_norm = nn.LayerNorm(normalized_shape=config.dim, eps=config.eps)
		# feed-forward network
		self.lin1 = nn.Linear(in_features=config.dim, out_features=3072, bias=True)
		self.lin2 = nn.Linear(in_features=3072, out_features=config.dim, bias=True)
		self.output_layer_norm = nn.LayerNorm(normalized_shape=config.dim, eps=config.eps)
	
	def forward(self, hidden_states):
	
		def shape(x):
			""" separate heads """
			return x.view(1, -1, 12, 64).transpose(1, 2)
		def unshape(x):
			""" group heads """
			return x.transpose(1, 2).contiguous().view(1, -1, 12 * 64)
	
		bs=hidden_states.shape[0] #(bs, input_length, embed_size)
		n_nodes= hidden_states.shape[1] #(bs, n_tokens, embed_size)
		# Input
		query=key=value=hidden_states
		# QKV compute
		q = self.q_lin(query)
		k = self.k_lin(key)
		v = self.v_lin(value)
		
		# Separating the heads
		q = shape(q) # (bs, n_heads, q_length, dim_per_head)
		k = shape(k) # (bs, n_heads, k_length, dim_per_head)
		v = shape(v) # (bs, n_heads, k_length, dim_per_head)
		
		# Normalizing the query-tensor
		q = q / math.sqrt(q.shape[-1])
		
		# Compute attention scores
		scores = torch.matmul(q, k.transpose(2, 3)) # (bs, n_heads, q_length, k_length)
		
		# Transform the scores into probability distribution via softmax
		prob = nn.functional.softmax(scores)
		weights = prob
		
		# Compute the weighted representation of the value-tensor (aka context)
		context = torch.matmul(weights, v) # (bs, n_heads, q_length, dim_per_head)
	
		# Merging the heads again
		context = unshape(context) # (bs, q_length, dim)
		
		# Additional projection of the context to get the output of the self-attention block
		sa_output = self.out_lin(context)
		# Res-Net
		sa_output = self.sa_layer_norm(sa_output + hidden_states)
		
		# Feed-forward network to compute the attention block output
		x = self.lin1(sa_output)
		x = nn.functional.gelu(x)
		ffn_output = self.lin2(x)
		ffn_output = self.output_layer_norm(ffn_output + sa_output)
		
		return ffn_output, weights
```
###### DistillBERT pre-trained model built by our blocks:
```python
class DistillBertAttention(nn.Module):
	def __init__(self, config):
		super().__init__()
		self.config = config
		self.n_layers=config.n_layers
		# embedding layer to compute output embeddings
		self.embeddings = Embeddings(config)
		# encoder consisting of n attention blocks + MLP
		self.attention_layers = torch.nn.Sequential(*[AttentionBlock(config) for i in range(config.n_layers)])
		# classification MLP
		self.pre_classifier = nn.Linear(in_features=config.dim, out_features=config.dim, bias=True)
		self.classifier = nn.Linear(in_features=config.dim, out_features=config.n_classes, bias=True)
		
		self.attention_probs = {i: [] for i in range(config.n_layers)}

	def forward(self, input_ids):
		"""
		Parameters:
		input_ids (torch.Tensor): torch.tensor(bs, max_seq_length) The token ids to embed.
		Returns: torch.tensor(bs, n_classes) The computed logit scores for each class.
		"""
		# Computing the embeddings
		hidden_states = self.embeddings(input_ids=input_ids).to(self.config.device)
		
		# Iteratively going through the attention layers
		encoder_input = hidden_states
		for i,block in enumerate(self.attention_layers):
			output, attention_probs = block(encoder_input)
			self.attention_probs[i] = attention_probs
			encoder_input = output

		# Pooling by selection the [CLS] token
		CLS_output = output[:, 0] # (bs, dim)
		# Classification
		CLS_output = self.pre_classifier(CLS_output) # (bs, dim)
		CLS_output = nn.ReLU()(CLS_output) # (bs, dim)
		logits = self.classifier(CLS_output)
		
		return logits
		
model = DistillBertAttention(config)
state_dict = torch.load('distilbert.pt')
_ = model.load_state_dict(state_dict)
_ = model.eval()
```
## Graph Neural Networks:
**Edge computation given 2d datapoints:**
```python
def compute_edges(points:torch.FloatTensor, cutoff:float=1.) -> torch.LongTensor:
	# COmpute distance between every 2 points and create a distance matrix
	distances = torch.sqrt(torch.sum((points[:,None, :] - points[None,:,:])**2, dim=-1))
	# Create an adjacency matrix by setting neighbors as ones closer or equals to 1
	adjacency_matrix = distances <= cutoff
	# Return indices of where connections are
	edges = torch.nonzero(adjacency_matrix)
	return edges
```
###### Graph Convolution:
```python
class GraphConv(nn.Module):
	def __init__(self, n_in:int , n_out: int, activation=F.relu):
		super().__init__()
		self.n_in = n_in
		self.n_out = n_out
		self.activation = activation
		self.theta = nn.Parameter(torch.empty((n_in, n_out)))
		torch.nn.init.xavier_uniform_(self.theta)
	
	def forward(self, x:torch.Tensor, edges:torch.Tensor) -> torch.Tensor:
		messages = self.compute_message(x, edges)
		# aggregate messages for each node
		aggregated_messages = self.aggregate(messages, edges)
		# update node states
		x = self.compute_update(x, aggregated_messages)
		return x

	def aggregate(self, messages:torch.Tensor, edges:torch.Tensor) -> torch.Tensor:
		n_nodes = torch.max(edges) + 1
		# Only count edges once
		incoming = edges[:, 0]
		#Add the elements of messages to each other according to the edges
		aggregated_messages = scatter_add(messages, incoming, dim_size=n_nodes, dim=0)
		return aggregated_messages

	def compute_message(self, x:torch.Tensor, edges:torch.Tensor) -> torch.Tensor:
		# we assume here that in- and out-degrees are equal, i.e. undirected graphs
		_, degree = torch.unique(edges, return_counts=True)
		# sparse version of GCN D^{-1/2} (A+I) D^{-1/2}
		# (assuming self-connection is already included in edges)
		incoming = edges[:,0]
		outgoing = edges[:,1]
		message = x[incoming]
		degree_normalization = torch.sqrt(degree[incoming]*degree[outgoing])
		message = message/degree_normalization[:, None]
		return message

	def compute_update(self, x:torch.Tensor, m:torch.Tensor) -> torch.Tensor:
		y = torch.mm(m, self.theta)
		y = self.activation(y)
		return y
```

## Neural ODES
[[CookBook 2#Neural Ordinary Differential Equations]]
**RK45 integration method:**
```python
class RungeKuttaSolver(ODESolver):
	def __init__(self, dt):
		super().__init__()
		self.dt = dt
		
	def step(self, f, t, u):
		dt = self.dt
		k1 = f(t, u)
		k2 = f(t + dt / 2, u + dt / 2 * k1)
		k3 = f(t + dt / 2, u + dt / 2 * k2)
		k4 = f(t + dt, u + dt * k3)
		
		t_next = t + self.dt
		u_next = u + self.dt / 6 * (k1 + 2 * k2 + 2 * k3 + k4)
		return t_next, u_next
```
###### Neural ODE:
```python
from torchdiffeq import odeint_adjoint as odeint
class MyNeuralODE(nn.Module):

	def __init__(self, net):
		super().__init__()
		self.net = nn.Sequential(nn.Linear(2, 16), # input dimensionality of u
							nn.Tanh(),
							nn.Linear(16, 2), # output dimensionality of u
							)
		for layer in self.net.modules():
			if isinstance(layer, nn.Linear):
				nn.init.normal_(layer.weight, mean=0.0, std=0.05)
				nn.init.constant_(layer.bias, val=0.0)
	
	def forward(self, _t, u):
		return self.net(u)

neural_ode = MyNeuralODE(net).to(device)
def loss_fn(u, u_pred):
	return torch.mean(torch.norm(u - u_pred, dim=1))

optimizer = optim.Adam(neural_ode.parameters(), lr=2e-3)
n_iters = 1000
print_every = 200

for i in range(1, n_iters + 1):
	optimizer.zero_grad()
	u_pred = odeint(neural_ode, u0_torch, t_torch)
	loss = loss_fn(u_target, u_pred)
	loss.backward()
	optimizer.step()
	if i == 1 or i % print_every == 0:
		print(f"Step: {i :4d} | Loss: {loss.item() :.6f}")
		visualize_prediction_2d(neural_ode)
```
## XAI:
[[CookBook2#XAI]]
###### Sequence classification Transformer (Gradient x Input):
```python
# model from transformers
model = AutoModelForSequenceClassification.from_pretrained("distilbert-base-uncased-finetuned-sst-2-english")
# We want to compute the gradient w.r.t the input embeddings not the input ids, but the embedding module is already included in the
# model thus we can replace it with identity and extract it in order to modify it ourselves
if not isinstance(model.distilbert.embeddings, Identity):
	embeddings_module = model.distilbert.embeddings
	model.distilbert.embeddings = Identity()
# we replace the input from {ids, mask} to {embeddings, mask}
embeddings_out = embeddings_module(inputs['input_ids'])
inputs_ = {'input_ids':None, 'inputs_embeds':embeddings_out.detach().requires_grad_(True), 'attention_mask':inputs['attention_mask']}
# Classify (without argmax)
logits = model(**inputs_).logits
# Which class to compute contribution to
curr_logits = logits[:,0]
# compute Gradient x input
curr_logits.backward()
grad = inputs_['inputs_embeds'].grad
GradxInput=inputs_['inputs_embeds']*grad
relevance_gi = GradxInput.sum(2).detach().numpy()
```
###### Sequence classification Transformer (detachment method Norm):
```python
from typing import Union, Optional, Tuple, Dict
from transformers.models.distilbert.modeling_distilbert import DistilBertForSequenceClassification, MultiHeadSelfAttention

class LayerNormXAI(nn.Module):
	def forward(self, input):
		if self.mode == 'no_norm':
			return input
		elif self.mode == 'distilnorm':
			# compute (X - mean) / (STD + epsilon).detach() normalization
			mean = input.mean(dim=-1,keepdims=True)
			std = torch.std(input,dim=-1,keepdims=True)
			input_norm = (input - mean) / (std.detach() + self.eps)
			# linear
			input_norm = input_norm * self.weight + self.bias
			return input_norm
		else:
			raise
```
###### Sequence classification Transformer (detachment method Attention):
```python
class MultiHeadSelfAttentionXAI(MultiHeadSelfAttention):
	def forward(self,
				query: torch.Tensor,
				key: torch.Tensor,
				value: torch.Tensor,
				mask: torch.Tensor,
				head_mask: Optional[torch.Tensor] = None,
				output_attentions: bool = False,) -> Tuple[torch.Tensor, ...]:
	# get dimensions
	bs, q_length, dim = query.size()
	k_length = key.size(1)
	dim_per_head = self.dim // self.n_heads
	mask_reshp = (bs, 1, 1, k_length)
	# combining heads to compute together
	def shape(x: torch.Tensor) -> torch.Tensor:
		"""separate heads"""
		return x.view(bs, -1, self.n_heads, dim_per_head).transpose(1, 2)
	# Separating heads
	def unshape(x: torch.Tensor) -> torch.Tensor:
		"""group heads"""
		return x.transpose(1, 2).contiguous().view(bs, -1, self.n_heads * dim_per_head)
	# combine
	q = shape(self.q_lin(query)) # (bs, n_heads, q_length, dim_per_head)
	k = shape(self.k_lin(key)) # (bs, n_heads, k_length, dim_per_head)
	v = shape(self.v_lin(value)) # (bs, n_heads, k_length, dim_per_head)
	# Self attention
	q = q / math.sqrt(dim_per_head) # (bs, n_heads, q_length, dim_per_head)
	scores = torch.matmul(q, k.transpose(2, 3)) # (bs, n_heads, q_length, k_length)
	mask = (mask == 0).view(mask_reshp).expand_as(scores) # (bs, n_heads, q_length, k_length)
	scores = scores.masked_fill( mask, torch.tensor(torch.finfo(scores.dtype).min)) # (bs, n_heads, q_length, k_length)
	weights = nn.functional.softmax(scores, dim=-1) # (bs, n_heads, q_length, k_length)
	weights = self.dropout(weights) # (bs, n_heads, q_length, k_length)
	# Mask heads if we want to
	if head_mask is not None:
		weights = weights * head_mask
	# detach p before value computation
	weights = weights.detach()
	context = torch.matmul(weights, v) # (bs, n_heads, q_length, dim_per_head)
	context = unshape(context) # (bs, q_length, dim)
	context = self.out_lin(context) # (bs, q_length, dim)

	if output_attentions:
		return (context, weights)
	else:
		return (context,)  
```
###### Sequence classification Transformer (detachment method Gelu):
```python
class GELUActivationXAI(nn.Module):
	"""
	Original Implementation of the GELU activation function in Google BERT repo when initially created. For
	information: OpenAI GPT's GELU is slightly different (and gives slightly different results): 0.5 * x * (1 +
	torch.tanh(math.sqrt(2 / math.pi) * (x + 0.044715 * torch.pow(x, 3)))) This is now written in C in nn.functional
	Also see the Gaussian Error Linear Units paper: https://arxiv.org/abs/1606.08415
	"""
	def __init__(self):
		super().__init__()
		self.act = self._gelu_python

	def _gelu_python(self, input: Tensor) -> Tensor:
		return input * 0.5 * (1.0 + torch.erf(input / math.sqrt(2.0)))

	def forward(self, input: Tensor) -> Tensor:
		gelu = self.act(input)
		# h = x * [Gelu(x)/x].detach() = Gelu(x)
		# detach the gelu part
		out = input*((gelu/(input+1e-6)).detach())
		return out
```
###### Graph classification GNN (detachment methods GNN-LRP):
```python
class GraphNet(torch.nn.Module):
	def __init__(self,d,h,c):
		super(GraphNet, self).__init__()
		self.U  = torch.nn.Parameter(torch.FloatTensor(numpy.random.normal(0,d**-.5,[d,h])))
		self.W1 = torch.nn.Parameter(torch.FloatTensor(numpy.random.normal(0,h**-.5,[h,h])))
		self.W2 = torch.nn.Parameter(torch.FloatTensor(numpy.random.normal(0,h**-.5,[h,h])))
		self.V  = torch.nn.Parameter(torch.FloatTensor(numpy.random.normal(0,h**-.5,[h,c])))
		self.params = [self.U,self.W1,self.W2,self.V]
	
	def forward(self,A):
		#forward process
		H = torch.eye(len(A))
		# layer 1 projection + relu
		H = H.matmul(self.U).clamp(min=0)
		# layer 2 learning + relu
		H = (A.transpose(1,0).matmul(H.matmul(self.W1))).clamp(min=0)
		# layer 3 learning + relu
		H = (A.transpose(1,0).matmul(H.matmul(self.W2))).clamp(min=0)
		# layer 4 projection + relu
		H = H.matmul(self.V).clamp(min=0)
		return H.mean(dim=0)
	
	def lrp(self,A,gamma,l,inds):
		# Re-write forward process such that grads compute GNN LRP
		if inds is not None:
			j,k = inds
			Mj = torch.FloatTensor(numpy.eye(len(A))[j][:,numpy.newaxis])
			Mk = torch.FloatTensor(numpy.eye(len(A))[k][:,numpy.newaxis])
		# w + gamma * w^+ for positive reinforcement
		W1p = self.W1+gamma*self.W1.clamp(min=0)
		W2p = self.W2+gamma*self.W2.clamp(min=0)
		Vp = self.V+gamma*self.V.clamp(min=0)
		# input
		X = torch.eye(len(A))
		X.requires_grad_(True)
		
		# Layer 1 relu + proj
		H = X.matmul(self.U).clamp(min=0)
		# Normal forward pass Z
		Z = A.transpose(1,0).matmul(H.matmul(self.W1))
		# Gamma reinforced forward pass P
		Zp = A.transpose(1,0).matmul(H.matmul(W1p))
		# Q = P * (Z / P).detach
		H = (Zp*(Z/(Zp+1e-6)).data).clamp(min=0)
		if inds is not None: H = H * Mj + (1-Mj) * (H.data)
		
		# Normal forward pass Z2
		Z = A.transpose(1,0).matmul(H.matmul(self.W2))
		# Gamma reinforced foward pass P2
		Zp = A.transpose(1,0).matmul(H.matmul(W2p))
		# Q2 = P2 * (Z2 / P2).detach
		H = (Zp*(Z/(Zp+1e-6)).data).clamp(min=0)
		if inds is not None: H = H * Mk + (1-Mk) * (H.data)

		# normal forward pass Z3
		Z = H.matmul(self.V)
		# Gamma reinforced forward pass P3
		Zp = H.matmul(Vp)
		# Q3 = P3 * (Z3 / P3).detach
		H = (Zp*(Z/(Zp+1e-6)).data).clamp(min=0)
		# OUTPUT
		Y = H.mean(dim=0)[l]
		# Grad x input = higher order LRP
		Y.backward()
		R = X.data*X.grad
		return R
```

## Generative models:
[[CookBook 2#Generative Modelling]]
###### forward diffusion:
```python
from diffusers import UNet2DModel
def forward_diffusion(clean_images, noise, batch_timesteps, num_train_timesteps):
	# q(xT | X0) it takes the clean images, the noise and the timesteps as input and returns the noisy images
	# batch size
	batch_size = len(batch_timesteps)
	# schedule of decaying alphas linearly with max_timesteps
	# beta is very small, alpha is 1- beta
	alpha_schedule = torch.linspace(0.9999, 0.98, num_train_timesteps).to(device)
	# given the timesteps for the current image in the current batch timesteps[i]
	# bring the alphas from 1 to the current t and multiply all of them
	# alphas will be multiplied with the image so they need to be broadcasted with image sizes
	# alpha hat = prod s=1 -> t alpha_s
	alphas = torch.tensor([torch.prod((alpha_schedule[:batch_timesteps[i]])) for i in range(batch_size)])[:,None,None,None].to(device)
	# compute Xt from X0 and noise
	return torch.sqrt(alphas) * clean_images + torch.sqrt(1 - alphas) * noise

  

for step, batch in enumerate(train_dataloader):
	clean_images = batch[0].to(device)
	# Sample noise to add to the images
	noise = torch.randn(clean_images.shape).to(clean_images.device).to(device)
	bs = clean_images.shape[0]
	
	# Sample a random timestep for each image
	timesteps = torch.randint(0, num_train_timesteps, (bs,), device=clean_images.device).long().to(device)
	
	# Add noise to the clean images according to the noise magnitude at each timestep
	# (this is the forward diffusion process)
	noisy_images = forward_diffusion(clean_images, noise, timesteps, num_train_timesteps).to(device)
	
	# Predict the noise residual
	noise_pred = model(noisy_images, timesteps, return_dict=False)[0]
	loss = F.mse_loss(noise_pred, noise)
	loss.backward()
	optimizer.step()
	optimizer.zero_grad()
	```
	
###### Generative process DDPM:
```python
def reverse_diffusion_ddpm(model, noise, num_timesteps, device, train_timesteps):
	# p(xt-1 | xt) it should take noise, the model and the number of timesteps as input and return the generated images
	# Generate the initial images from the noise (batch size = 5)
	current_image = noise.to(device)
	# Perform reverse diffusion for the specified number of timesteps
	for t in range(num_timesteps-1,-1,-1):
		# Generate the time stamps for the current batch image
		timesteps = torch.ones([current_image.shape[0]], dtype=torch.int32).to(device) * t
		# predicted noise via the model in the current step
		predicted_noise = model(current_image, ts, return_dict=False)
		# get alphas for the current batch
		alphas = torch.tensor([alpha_range[ts[j]] for j in range(len(ts))])[:,None,None,None]
		alphas_prod = torch.tensor([ torch.prod(alpha_range[:ts[j]]) for j in range(len(ts)) ])[:,None,None,None]
		# get the predicted mean and variance
		variance = torch.randn_like(current_image) * torch.tensor(0.01 * (i / num_timesteps)) # Noise z * Sigma_t
		current_image = torch.sqrt(1 / alphas) * (current_image - ((1 - alphas)* predicted_noise[0])/torch.sqrt(1 - alphas_prod) ) + variance
		current_image = current_image.detach()

	return current_image
```
###### Generative process DDIM:
```python
def reverse_diffusion_ddim(model, noise, num_timesteps):
	# it should take noise, the model and the number of timesteps as input and return the generated images
	alpha_range = torch.linspace(0.9999, 0.98, num_timesteps)
	
	current_image = noise
	
	for i in range(num_timesteps-1,0,-1):
		ts = torch.full((current_image.shape[0],),i)
		alphas_prod_old = torch.tensor([ torch.prod(alpha_range[:ts[j]]) for j in range(len(ts)-1) ])[:,None,None,None]
		alphas_prod = torch.tensor([ torch.prod(alpha_range[:ts[j]]) for j in range(len(ts)) ])[:,None,None,None]
		sampled_noise = torch.randn_like(current_image) * torch.tensor(0.0)
		predicted_noise = model(current_image, ts, return_dict=False)[0]
		current_image = torch.sqrt(alphas_prod_old) * ((current_image - torch.sqrt(1 - alphas_prod) * predicted_noise) / torch.sqrt(alphas_prod)) + torch.sqrt(1 - alphas_prod_old - torch.tensor(0)) * predicted_noise + sampled_noise
		current_image = current_image.detach()
	
	return current_image
```


## Reinforcement Learning:
[[CookBook 2#Reinforcement learning]]
###### ActorCritic: 
```python
class ActorCritic(object):
"""
Actor Critic Agent used during trajectory collection. It returns a
distribution and an action given an observation.
"""
	def __init__(self, actor_net: torch.nn.Module, critic_net: torch.nn.Module):
		self.actor_net = actor_net
		self.critic_net = critic_net

	@torch.no_grad()
	def __call__(self, state: torch.Tensor) -> Tuple[torch.distributions.Categorical, torch.Tensor, torch.Tensor, torch.Tensor]:
		'''
		:param state:
		:return: Categorical distribution, action, log probability of action, critic value of state
		'''
		pi = torch.distributions.Categorical(logits=self.actor_net(states))
		action = pi.sample()
		log_p = pi.log_prob(action)
		value = self.critic_net(state)
		return pi, action, log_p, value
```
###### Discounted rewards:
```python
def discount_rewards(self, rewards: List[float], discount: float) -> List[float]:
	"""Calculate the discounted rewards of all rewards in list
	Args:
		rewards: list of rewards/advantages
	Returns:
		list of discounted rewards/advantages
	"""
	assert isinstance(rewards[0], float)
	cumul_reward = []
	sum_r = 0.0
	for r in reversed(rewards):
		sum_r = (sum_r * discount) + r
		cumul_reward.append(sum_r)
	return list(reversed(cumul_reward))
```
###### Advantage:
```python
def calc_advantage(self, rewards: List[float], values: List[float], last_value: float) -> List[float]:
	"""Calculate the advantage given rewards, state values, and the last value of episode
	Args:
		rewards: list of episode rewards
		values: list of state values from critic
		last_value: value of last state of episode
	Returns:
		list of advantages
	"""
	rews = rewards + [last_value]
	vals = values + [last_value]
	# GAE
	delta = [rews[i] + self.gamma * vals[i + 1] - vals[i] for i in range(len(rews) - 1)]
	adv = self.discount_rewards(delta, self.gamma * self.lam) 
	return adv
```
###### PPO:
```python
class PPO(pl.LightningModule):
	def forward(self, x: torch.Tensor) -> Tuple[torch.Tensor, torch.Tensor, torch.Tensor]:
		"""
		Passes in a state x through the network and returns the policy and a sampled action
		Args:
			x: environment state
		Returns:
			Tuple of policy and action
		"""
		action_prob, action = self.actor(x)
		value = self.critic(x)
		return action_prob, action, value
	
	def actor_loss(self, state, action, logp_old, advantage) -> torch.Tensor:
		"""
		Calculate the actor loss.
		Args:
			state: current state of environment
			action: selected action
			logp_old: old log-probability
			advantage: advantage of action
		Returns:
			loss
		"""
		logp_new = self.actor(state)[0].log_prob(action)
		p_new = torch.exp(logp_new)
		p_old = torch.exp(logp_old)
		frac = p_new/p_old
		clip = torch.clamp(frac, 1 + self.clip_ratio)
		loss_actor = (-1*clip*advantage).mean()
		return loss_actor
		
	def critic_loss(self, state: torch.Tensor, d_reward: torch.Tensor) -> torch.Tensor:
		"""
		Calculate the critic loss.
		Args:
			state: current state of environment
			d_reward: discounted reward
		Returns:
			loss
		"""
		value = self.critic(states)
		loss_critic = (value-d_reward)**2
		return loss_critic

	def training_step(self, batch: Tuple[torch.Tensor, torch.Tensor], batch_idx):
		"""
		Carries out a single update to actor and critic network from a batch of replay buffer.
		Args:
			batch: batch of replay buffer/trajectory data
			batch_idx: used for logging
			optimizer_idx: idx that controls optimizing actor or critic network
		Returns:
			loss
		"""
		optims = self.optimizers()
		optim = optims[0] if batch_idx % 2 == 0 else optims[1]
		optim.zero_grad()
		state, action, old_logp, d_reward, advantage = batch
	
		# normalize advantages
		advantage = (advantage - advantage.mean()) / advantage.std()
		self.log("avg_ep_len", self.trainer.datamodule.avg_ep_len, prog_bar=True, on_step=False, on_epoch=True)
		self.log("avg_ep_reward", self.trainer.datamodule.avg_ep_reward, prog_bar=True, on_step=False, on_epoch=True)
		self.log("avg_reward", self.trainer.datamodule.avg_reward, prog_bar=True, on_step=False, on_epoch=True)
	
		if batch_idx % 2 == 0:
			loss_actor = self.actor_loss(state, action, old_logp, advantage)
			self.log('loss_actor', loss_actor, on_step=False, on_epoch=True, prog_bar=True, logger=True)
			self.manual_backward(loss_actor)
			optim.step()
			return loss_actor
	
		elif batch_idx % 2 == 0:
			loss_critic = self.critic_loss(state, d_reward)
			self.log('loss_critic', loss_critic, on_step=False, on_epoch=True, prog_bar=False, logger=True)
			self.manual_backward(loss_critic)
			optim.step()
			return loss_critic

	def configure_optimizers(self) -> List[Optimizer]:
		""" Initialize Adam optimizer"""
		optimizer_actor = optim.Adam(self.actor.parameters(), lr=self.lr_actor)
		optimizer_critic = optim.Adam(self.critic.parameters(), lr=self.lr_critic)
		return optimizer_actor, optimizer_critic
```