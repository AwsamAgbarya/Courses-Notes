---
tags:
  - MachineLearning
  - Programming
---
The following note will have relevant code snippets from some basic machine learning concepts alongside some basic python reminders!
## Python Basics:
**Array initialization:**
```python
# Values
np.zeros(size) #0
np.ones(size) #1
np.full(size,val) #val
np.empty(size) #no value
# Ranges
np.arange(start:end:step) #custom range
np.linspace(startval,endval,size) #linear range
# miscellaneous
np.repeat(container,times,axis)
np.identity(size)/np.eye(size)
```

**Useful numpy functions:**
```python
np.cumsum(arr,axis) #Cumulative sum
np.vstack(a,b) #appends 2 arrays while keeping the objects
np.hstack(a,b) #appends 2 arrays horizontally 
np.argmin/max(a)  #returns index of min/max
np.unique(arr, return_index, return_inverse, return_counts) # counts unique values and returns their index/count
np.expand_dims(arr, axis) #expanding the dimension of an array
np.argwhere(a>c).flatten() #returns indices of non-zero elements
np.where(cond, x,y) #returns elements that match the condition (returns x otherwise y)
np.put(a,indices,values) #replaces indices in a with values
np.hsplit(a,number) #splits array horizontally given a number of elements
pad_shape = (
	(0, 0),  # Add no row at the top and no row at the bottom
	(1, 0),  # Add one column at the left and no column at the right
)
transition = np.pad(arr,pad_shape,constant_values=0) 
```

**Reshaping:**
```python
A.T #flips the axis 
A.transpose(indices) #transposes the arrays axis according to the indices of the original axis
A.reshape(shape) #keeps the data in the same order but changes the dimensions accordingly, You are allowed to use '...' to indicate all previous indexes
A.flatten() #turns the array into one dimensional
A[:,None] #To add a new dimensions (usually for broadcasting)
A[A>c] #filter out all the elements in A that dont apply to the condition
```

**Linear Algebra:**
```python
np.linalg.norm(point1-point2) #Used to calculate euclidean distances or l2 norm
np.linalg.inv(A) #inverse matrix
np.linalg.eig(A) #returns eigen values vectors
np.linalg.eigh(A) #returns eigenvalues and vectors given that the matrix A is symmetric (i.e all eigenvalues are real)
scipy.linalg.eigs(A, k=num) #returns eigenvalues and vectors given that the matrix A is sparse 
np.linalg.det(A) #returns determinant
np.linalg.einsum('ii->i',a) #returns the diagonal einsum('ii',a) returns sum of diagonal
np.linalg.norm(x - (w.dot(x)/np.linalg.norm(w)) # calculating distance of x from hyperplane w
((A - B)**2).mean(axis=0) # performs mean squared error
```

## Famous Toy Datasets:
**Labeled Faces in the wild:***
```python
import numpy, sklearn.datasets
D = sklearn.datasets.fetch_lfw_people(resize=0.5)['images']
# Fetching random data
D = [numpy.random.mtrand.RandomState(1).permutation(len(D))[:2000]]*1.0
# Centering
D = D - D.mean(axis=(1,2), keepdims=True)
# Normalizing
D = D / D.std(axis=(1,2), keepdims=True)
print(D.shape) # (2000,62,47)
```
**20 NewsGroups:**
```python
from sklearn.datasets import fetch_20newgroups

train = fetch_20newsgroups(subset='train', categories=['sci.med'])
test = fetch_20newsgroups(subset='test', categories=['sci.med'])

# Sampling seuqences
def sample(data, T=50):
	 i = np.random.randint(len(data))
	 O = data[i].upper().replace('\n', ' ')
	 O = np.array([ord[s] for s in O])
	 O = np.maximum(O[(0>=65) * (0<90) + (O==32)]-64,0)
	 j = np.random.randint(len(O)-T)
	 return O[j:j+T]
```
**GMM:**
```python
import sklearn.datasets
X = sklearn.datasets.make_blobs(n_samples=2000, centers=10, random_state=2)[0]
X = X - X.mean(axis=0)
X = X / X.std() * 4.0
```
**MNIST:**
```python
import torch
trainset = torchvision.datasets.MNIST(root='./data', train=True, download=True)
testset = torchvision.datasets.MNIST(root='./data', train=False, download=True)
Xr = trainset.data[:2500].float().view(-1,784)/127.5-1
Xt = testset.data.float().view(-1,784)/127.5-1
```
## Data Processing:
##### Whitening:
```python
def Whiten(X):
	S = X.T@X
	V = np.linalg.eigh(S)[1]
	P = X@V
	P = P/(P**2).mean(axis=0)**.5 # standardizing
	Z = P@V.T
	return Z
```
## PCA:
[[CookBook2#PCA (Recap)]]
##### SVD:
```python
import numpy as np
# D.shape = (2000,62,47)
X = D.reshape(len(D), -1).T # X.shape = (2914, 2000)
X -= X.mean(axis=1, keepdims=True) # Centering
Z = X / X.shape[1]**.5 # 1\SQRT(N) * X
U, L ,V =  np.linalg.svd(Z, full_matrices=False) # SVD decompositon
U[:,0].dot(X) # Project onto the first PC
V[k,:].dot(X) # Project onto the first K PC
```
##### POWIT:
```python
import numpy as np
w = numpy.random.normal(0,1,[X.shape[0]]) # init w
w /= (w**2).sum()**.5 # Normalize
Cov = np.dot(X,X.T) / X.shape[1] # compute covariance matrix
Jold = float('nan')
# POWIT
for iteration in range(100):
	Sw = np.dot(Cov,w)
	J = w.dot(Sw) 
	print('iteration %2d J(w) = %10.3f'%(iteration,J))
	
	if J - Jold < 0.01:
		print("Critereon reached")
		break
	Jold = J
	w = Sw / (Sw**2).sum()**.5
```

## LLE:
[[CookBook2#Locally Linear Embedding]]
```python
import numpy as np

k = 10 #num of neighbors
N = len(X)
W = np.zeroes([N,N])

for i in range(N):
	# Step 1:
	x = X[i] #iterate over every point
	dists = ((x-X)**2).sum(axis=1)**.5 # find nearest neighbors
	dists[i] = float('inf') #Remove the node itself from its neighbors
	ind = dist < sorted(dist)[k] # find k nearest
	# Step 2:
	diff = x - X[ind]
	C = np.dot(diff, diff.T) # Construct C
	C += 0.05 * np.identity(k)
	# find w
	w = np.linalg.solve(C, np.ones([k]))
	w /= w.sum()
	W[i,ind] = w
# Step 3:
M = np.identity(N) - W	- W.T + np.dot(W.T, W)
E = np.linalg.svd(M)[0][:,-3:-1]
```

## T-SNE:
[[CookBook2#Stochastic Neighbor Selection]]
```python
def student(Y):
	pd = (Y - Y[:,:,None])**2
	Q_num = 1 / (1 + pd)
	Q_denom = Q_num.sum(axis=1, keepdims=True) - pd
	return Q_num / Q_denom

def Objective(P,Q):
	return (P * np.log(P/Q)).sum()

def gradient(P,Y):
	Q = student(Y)
	pd = (Y - Y[:,:,None])**2
	return 4 * ((P-Q)*(pd)*(1/(1+pd)).sum(axis=1)

N,d = X.shape
P = utils.getaffinity(X,perplexity)
Y = Y0*1
dY = Y*0
for t in range(T):
	Q = student(Y)
	if t %50 == 0: print('%3d %.3f'%(t,objective(P,Q)))
	# update
	dY = (0.5 if t < 100 else 0.9)*dY + learningrate*gradient(P,Y)
	Y = Y - dY
```

## CCA:
[[CookBook2#Canonical Component Analysis]]
```python
N = len(X)
X = X - X.mean(axis=0)
Y = Y - Y.mean(axis=0)

Kxx = (X@X.T)
Kyy = (Y@Y.T)
Z = np.zeros([N,N])

A = np.block([[Z, Kxx@Kyy],[Kyy@Kxx, 0]])
B = np.block([[Kxx@Kxx, Z],[Z, Kyy@Kyy]])

eigvals, eigvecs = scipy.linalg.eigh(A,B)
maxeig = eigvecs[:,0]

alpha_x = maxeig[:N]
alpha_y = maxeig[N:]

w_x = X.T@alpha_x
w_y = Y.T@alpha_y
```

## ICA:
[[CookBook2#Independent Component Analysis]]
```python
Z = whiten(X) # Function to whiten and center
N, d =  Z.shape
h = 64
a = 1.5

def G(u): return 1/a * np.log(np.cosh(a*u)) # Non-quadratic function on the projections
def g(u): return np.tanh(a*u) # first derivative
def dg(u): return a*(1-g(u)**2) # second derivative

epsilon = np.random.normal(0,1,[N,h]) # Random noise
W = np.random.normal(0,1,[h,d])
for i in range(200):
	W = whiten(W.T).T / d**.5 # Decorrelate w's
	P = np.dot(Z, W.T) # project data on W
	W = np.dot(g(P).T,Z) / N - dg(P).mean(axis=0)[:,None]*W # newtons method to find new w
	if it%25:
		J = (G(P).mean(axis=0)-G(epsilon).mean(axis=0))**2 # Objective function we want to maximize
		print(J.sum())
```
## Auto-encoder:
[[CookBook2#Representation learning]]
```python
# X is a tensor of size m x d containing data  minibatches of size m
d = X.shape[1]
h = 400
# V is a tensor of size d x h containing weights of the encoder
V = torch.nn.Parameter(d**-.5*torch.randn([d,h]))
# W is a tensor of size h x d containing the weights of the decoder
W = torch.nn.Parameter(torch.randn([h,d]))
# b is a tensor of size h containing the bias of the encoder
b = torch.nn.Parameter(torch.randn([h]))
# a is a tensor of size d containing the bias of the decoder
a = torch.nn.Parameter(torch.randn([d]))

Optimizer = torch.optim.Adam((V,W,b,a), lr=0.0001)

for i in range(10000):
	Optimizer.zero_grad()
	x = X[numpy.random.permutation(len(X))[:100]]
	
	Z = x.matmul(V) + b
	S = Z.clamp(min=0)
	X_hat = S.matmul(W) + a
	
	rec = ((X_hat - x)**2).sum(dim=1).mean()
	spa = S.sum(dim=1).mean()
	ent = (1/S.mean(dim=0)).sum()
	reg = (W**2).sum()

	(rec + lambda*spa + eps*ent +eta*reg).backward()
	optimizer.step()
```

## HMM:
[[CookBook2#Hidden Markov Models]]
```python
import hmm

hmm_model = hmm.HMM(num_of_states,num_of_observations)
Otrain = O[:int(len(O)*0.8)]
Otest = O[int(len(O*0.8)):]

for i in range(iterations):
	hmm_model.loaddata(Otrain)
	hmm_model.forward()
	hmm_model.backward()
	# Learning process
	# Compute gamma, xi and psi
	hmm_model.gamma = hmm_model.alpha*hmm_model.beta / hmm_model.pobs
	hmm_model.xi = hmm_model.alpha[:-1,:,None] * hmm_model.A[None,:,:] * hmm_model.beta[1:, None, :] * self.Z[1:, None, :] / self.pobs
	hmm_model.psi = hmm_model.gamma[:,:, None]* (hmm_model.O[:,None,None] == np.arange(hmm_model.B.shape[1])[None,None,:])
	# Update the parameters
	hmm_model.A = 0.9*hmm_model.A + 0.1*(hmm_model.xi.sum(axis=0) / hmm_model.gamma[:-1].sum(axis=0)[:,None])
	hmm_model.B = 0.9*hmm_model.B + 0.1*(hmm_model.psi.sum(axis=0) / hmm_model.gamma.sum(axis=0)[:,None])
	hmm_model.Pi = 0.9*hmm_model.Pi + 0.1*(hmm_model.gamma[0])
	

hmm_model.loaddata(Otrain)
hmm_model.forward()
logptrain = np.log(hmm_model.pobs)

hmm_model.loaddata(Otest)
hmm_model.forward()
logtest = np.log(hmm_model.pobs)
```

## Structured input kernels:
[[CookBook2#Kernels (Input, Output, Anomaly detection)]]
##### Text Kernel (tokens)
```python
# Givens S1 and S2 as two lists of tokens/words, we want to define a function that compares the two
def sortedKernel(s1, s2):
	ss1 = sorted(list(s1))
	ss2 = sorted(list(s2))

	k, i, j = 0
	while True:
		if i==len(ss1) or j==len(ss2): break
		elif ss1[i]==ss2[j]: k+=1; i+=1; j+=1
		elif ss1[i]<ss2[j]: i+=1
		elif ss2[j]<ss1[i]: j+=1

	return k
```
##### Text Kernel (n-grams):
```python
def betaContributions(beta):
	N=101
	s2c = np.zeros([N])
	for i in range(1,N):
		s2c[i] = beta[:i].sum() + s2c[i-1]
	return s2c
	
def k(X, Z, beta):
	beta_cont = betaContributions(beta)
	
	I = numpy.concatenate([
		Xtrain[None,:,:]==Xtrain[:,None,:], # Match the characters of each sequence from X and
		numpy.full([len(Xtrain),len(Xtrain),1], False, dtype=bool) # Adding false to the end of sequence
		],axis=2)
	blocksize = np.zeros([len(X), len(Z)], dtype=int) # Keep track of block sizes
	K = np.zeros([len(X), len(Z)]) # keep track of Kernel values

	for i in range(I.shape[2]):
		# add the contribution of the s2c to the kernel whenever we reach the end of that matching sequence
		K = K+s2c[blocksize]*(~I[:,:,j])
		# update the blocksize and count up until you hit a false then reset to 0
		blocksize = (blocksize+I[:,:,j])*(I[:,:,j])
	return K
```
## Anomaly Detection:
##### KDE:
```python
class KDE:
	def __init__(self,kernel):
		self.kernel=kernel

	def fit(self, X):
		self.X = X
		self.N = X..shape[0]
		return self

	def predict(self, X):
		return - np.log(1/self.N * self.kernel(X,self.X).sum(axis=1))
kernel = lambda x,y: sklearn.metrics.pairwise.rbf_kernel(x,y,gamma=0.25)
KDE(kernel).fit(X).predict(Xgrid)
```
##### KPCA:
```python
class UKPCA:

    def __init__(self,kernel,dims):
        self.kernel = kernel
        self.dims = dims
        
    def fit(self,X): 
        self.X = X
        lambdas, v = np.linalg.eigh(self.kernel(X,X)) 
        self.L = lambdas[-self.dims:]
        self.V = v[:,-self.dims:]
        return self
        
    def predict(self,X):
        ker = self.kernel(X,X).diagonal() # k(x,x)
        proj_sum = (self.kernel(X,self.X) @ self.V * self.L**(-0.5))**2 # k(x,X) * V:i * lambda:i^-0.5
        o = ker - proj_sum.sum(axis=1)
        return o
kernel = lambda x,y: sklearn.metrics.pairwise.rbf_kernel(x,y,gamma=0.1)
UKPCA(kernel,25).fit(X).predict(Xgrid)
```
##### OCSVM:
```python
class OCSVM:

    def __init__(self,kernel,nu):
        self.kernel = kernel
        self.nu = nu
        
    def fit(self,X):
        self.X = X
        n = X.shape[0]
        p = cvxopt.matrix(self.kernel(X,X))
        q = cvxopt.matrix(np.zeros(n))
        g = cvxopt.matrix(np.vstack((-np.eye(n), np.eye(n))))
        h = cvxopt.matrix(np.concatenate((np.zeros(n),np.full(n,1/(n*self.nu)))))
        a = cvxopt.matrix(np.ones(n).reshape((1,n)))
        b = cvxopt.matrix(np.array([1.0]))
        self.alphas = cvxopt.solvers.qp(p,q,g,h,a,b)['x']
        self.SSV = np.argmin(abs(self.alphas-1/(2*n*self.nu)))
        return self
        
    def predict(self,X):

        top = -1 * np.log((self.kernel(X,self.X).dot(self.alphas)))
        bot = np.log(self.kernel(self.X[self.SSV:self.SSV+1],self.X).dot(self.alphas))
        o = top + bot
        return o
kernel = lambda x,y: sklearn.metrics.pairwise.rbf_kernel(x,y,gamma=0.1)
OCSVM(kernel,0.0001).fit(X).predict(Xgrid)
```
## Neural Netowrk:
[[CookBook2#Deep Learning]]
```python
import torch
import torch.optim as optim
import torch.nn as nn
import numpy,numpy.random

class NNClassifier:
	def __init__(self,net,flat=False):
		self.net = net
		self.flat = flat
		
	def fit(self,X,T,mb=100,lr=0.01,epochs=1):
		if self.flat: X = X.view(len(X),-1)
		criterion = nn.CrossEntropyLoss()
		optimizer = optim.SGD(self.net.parameters(), lr=lr, momentum=0.9)
		for epoch in range(epochs):
			for i in range(len(X)//mb):
				x = X[mb*i:mb*(i+1)]
				t = T[mb*i:mb*(i+1)]
				optimizer.zero_grad()
				criterion(self.net.forward(x).view(mb,-1),t).backward()
				optimizer.step()
		return self

	def predict(self,X):
		if self.flat: X = X.view(len(X),-1)
		return self.net.forward(X).view(len(X),-1).data
	
	def graphdata(N=3000,m=15):
		numpy.random.seed(0)
		A = numpy.zeros([N,m,m])
		T = numpy.zeros([N])
		
		# Stars
		for i in range(N//3):
			j = numpy.random.randint(0,m)
			A[i,j,:] = 1.0; A[i,:,j] = 1.0; A[i,j,j] = 0.0; T[i] = 0
		# Chains
		for i in range(N//3,(N*2)//3):
			p = numpy.random.permutation(m)
			A[i,p[:-1],p[1:]] = 1.0; A[i,p[1:],p[:-1]] = 1.0; T[i] = 1
		# Random
		for i in range((N*2)//3,N):
			r = numpy.arange(m)
			p = numpy.random.permutation(m)
			A[i,r,p] = 1.0; A[i,p,r] = 1.0; T[i] = 2
		# Partitioning
		P = numpy.random.permutation(N)
		Ptr,Ptt = P[:N//2],P[N//2:]
		Ar = torch.FloatTensor(A[Ptr])
		Tr = torch.LongTensor(T[Ptr])
		At = torch.FloatTensor(A[Ptt])
		Tt = torch.LongTensor(T[Ptt])
		return Ar,Tr,At,Tt
```
##### GNN:
```python
class GNN(torch.nn.Module):
	def __init__(self,nbnodes,nbhid,nbclasses):
		torch.nn.Module.__init__(self)
		self.m = nbnodes
		self.h = nbhid
		self.c = nbclasses
		
		self.U = torch.nn.Parameter(torch.FloatTensor(numpy.random.normal(0,nbnodes**-.5,[nbnodes,nbhid])))
		self.W = torch.nn.Parameter(torch.FloatTensor(numpy.random.normal(0,nbhid**-.5,[nbhid,nbhid])))
		self.V = torch.nn.Parameter(torch.zeros([nbhid,nbclasses]))
		
	def forward(self,A):
		D = A.sum(dim=2)
		L = A / (D[len(A),None,-1]**.5 + D[len(A),None,-1]**.5 + 1e-6)
		 
		H0 = self.U
		H1 = L.matmul(H0).matmul(self.W).clamp(min=0)
		H2 = L.matmul(H1).matmul(self.W).clamp(min=0)
		H3 = L.matmul(H2).matmul(self.W).clamp(min=0)
		
		Y = H3.sum(dim=1).matmul(self.V)
	
		return Y
```
## Energy based models:
[[CookBook2#Deep Learning]]
```python
import torch.optim as optim

torch.manual_seed(0)
enet = nn.Sequential(
	nn.Linear(784,1024),nn.Hardtanh(),
	nn.Linear(1024,1024),nn.Hardtanh(),
	nn.Linear(1024,1),
)

gnet = nn.Sequential(
	nn.Linear(784,1024),nn.Hardtanh(),
	nn.Linear(1024,1024),nn.Hardtanh(),
	nn.Linear(1024,784),nn.Hardtanh(),
)
N = 2500
mb = 25
optimizer = optim.SGD(list(enet.parameters())+list(gnet.parameters()), lr=0.025)

for epoch in numpy.arange(1,40):
	for i in range(N//mb):
		optimizer.zero_grad()
		# Take a minibatch and train it
		x = Xr[mb*i:mb*(i+1)].data*1.0
		z,m = removepatch(x)
		# Build the forward pass from the input until the loss function
		xgen = gnet(x)
		# In the forward pass this does nothing and only produces xgen
		# In the backwards pass this will propagate -xgen which makes the generator maximize the loss
		# While the discriminator still minimizes the loss
		xgen = (2*xgen).data - xgen
		# only take the masked inpainting part
		xgen = x*(1-m) + xgen*m
		# find the energy for the contrastive and true inputs
		edata = enet(x)
		egen = enet(xgen)
		# log loss of difference
		err = torch.log(1 + torch.exp(edata-egen)).mean()
		# Compute the gradient and perform one step of gradient descent
		err.backward()
		optimizer.step()
	
	print('%3d %.3f'%(epoch,err.data.numpy()))
	```
