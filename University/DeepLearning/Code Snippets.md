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