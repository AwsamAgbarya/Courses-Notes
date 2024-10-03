## Representation Learning:
[[Representation Learning]]
- When using data hungry models or developing in fields with lack of data, its very useful to be able to use unlabeled data because its a lot more common than labeled data that requires experts.
- Representation learning is about taking unsupervised data and learning features and patterns that occur in the data without having explicit labels, in other words, encoding the observation space into the latent space which represents all modalities combined.
- Since we lack labels we cannot compare things with the ground truth provided instead we need to define clear objectives that we can measure the error of, these are called Pretext Tasks:
	1. Rearranging: rearranging parts of the puzzle to match the full image
	2. Masked Image Modelling: Fill in the blank of a masked patch of an image
	3. Colorization: Color and grey image back to its original color.
	4. Contrastive objective: which 2 augmented images belong to the same image and which dont
	5. Rotation prediction: Predict the current rotation
- These pretext tasks can be used for:
	1. Downstream classification task
	2. Clustering
	3. Semantic search
	4. Anomaly detection
	5. ICA
	6. matching modalities
#### Self-Supervised learning:
- Comprised of an unsupervised feature extractor whose job is to learn the General task in a general context through pretext tasks, and a downstream task with a small amount of labeled data that finetunes the model to a very specific window of data. Downstream tasks can be categorized into two types:
	- Linear Probing: Adds a MLP head at the end of the task and only changes that head during the downstream training in order to achieve the objective, this is usually done when the feature extractor is already familiar enough with out dataset.
	- Fine-tuning: alongside adding the MLP head, you fine-tune the entire model during the downstream training in order to steer the model into the specific window of your downstream task.
#### Multi-Modal Models:
- Mixing two different  modalities in a self supervised fashion by encoding them both into latent space and doing a nearest neighbor/clustering search.
- Maximize the similarity between the encoded text and encoded image (of the same dimensions)
- Images with captions can easily be scrapped from the internet which allows for large amounts of data.
- allows for image generation from captions, zeroshot image classification, text-image search
- Zero-shot Image classification is pre-trained by using Multi modal self supervised models, and does not require extra training, instead a dataset of classes is created from the text and the encoded class text is then compared with the image and the highest probability is returned.
#### Contrastive Learning:
- Contrastive learning Takes the idea of self-supervised learning on a "new" pretext task, The task revolves around getting 2 augmented versions of one image and putting them as close as possible to each other in latent space, whilst separating them from every other augmented view images that are not the same.
- Contrastive learning NEEDS negative samples otherwise representation collapse will happen which is when the solution to everything is a constant vector, by pushing away dissimilar stuff with contrastive examples we avoid this.
- This creates a representation latent space that meaningfully measures semantics with invariance to size, color and other augmentations.
- This creates 2 limitations/ problems:
	1. The model is augmentation dependent, and the augmentations are task dependent so we have to test out every combo of augmentations for our task in order to get the best model
	2. Contrastive learning requires a large batch with a lot of contrastive examples in order for it not to collapse.
	Both of these problems will be solved in the following 2 topics respectively.
-  SimCLR loss is given by: $$\mathcal{L} = - \frac{1}{N} \sum_{i,j \in MB} log \frac{exp \left( \frac{sim(z_i,z_j)}{\tau} \right) }{\sum_{k=1}^{2N} 1_{k \neq i} exp \left( \frac{sim(z_i,z_j)}{\tau} \right)}$$ such that sim is usually the cosine similarity $\frac{u \cdot v}{|u|\cdot|v|}$ the numerator maximizes the similarity between 2 views of the same image and the denominator minimizes the similarity between the views of different images.
> [!example]- SIMCLR loss Code Snippet
> ![[DeepLearning/Code Snippets#SimCLR|Code Snippets]]
-  The softmax distribution is controlled by the cosine similarity which is bounded by [-1,1] , The temperature parameter Controls the following:
	- Higher temperature leads to a more Uniform distribution of the similarities because the loss is less sensitive to changes in the similarity of views
	- Lower temperature leads to a distribution to have less entropy meaning that the similarities after the softmax become larger because the loss becomes more sensitive to changes in the similarity of 2 views
#### 1. Masked Modelling:
- Masked modelling consists of hiding/masking a part of your input and only inserting the unmasked parts to let the model learn from them and take a guess at the unmasked parts in order to reconstruct the image back into the truth.
- This allows it to learn necessary semantic properties in order to be able to understand how to fill in the blanks.
- MM allows us to pass in the image as is without needing to do augmentations.
##### BERT:
- BERT is a Masked Language Modelling technique that uses transformers to perform Bidirectional encoding representation of text.
- Unlike GPT and other methods that use Transformers for text, The masking property allows the model to use tokens from both directions in order to associate and understand the language
- BERT can have an input of a sentence or a Question Answer pair, for each  token embedding we then add a positional embedding alongside a segment embedding.
- Masking ratio of input is optimal at 15% because token languages provide a lot of new information with little redundancies.
##### BEiT 1&2:
-  Based off of BERT but is generalized to images using Vision Transformers.
- BEIT2 uses VQ-KD method in order to train an online tokenizer technique to distill knowledge from a teacher model, which helps define codebook embeddings of visual tokens and helps the encoder tokenize images into visual tokens better to reconstruct the discretized version into the teachers output.
- Pre-training of BEIT is as follows: the input image is separated into patches and visual tokens (using the trained tokenzier), we then mask the patches and insert the unmasked patches into the encoder and force it to predict the visual tokens that match the masked patches.
- Patch aggregation techniques help the model learn global representation by adding a classification token that has its own projection head, we append some layers tokens to the CLS token at the end of the last layer in order to force the information flow of global features that are lost in the l+1 -> L layers into the CLS token and we add both head's losses.

#### 2. Self distillation:
- Knowledge distillation is the technique of having a trained big model judge the the correctness of the outputs of a smaller models which "passes its knowledge to its student" or "compresses the teacher into the student" in a way.
- Self-distillation is a self-supervised approach of Knowledge distillation where we do not have any labels to train the Teacher anymore, instead we teach it alongside the teacher but give it better information to have a small advantage.
- Self-distillation and in general Non-contrastive loss is a way to avoid needing large batch sizes and large amount of counter examples in order to do representation learning.
- There needs to be asymmetry in the pipeline of student and teacher even though they have the same architecture in order for them not to learn the same things and collapse.
##### BYOL:
- Teacher is randomly initialized, the student model's loss is according to the MSE of his answer given the teachers "correct" answer,  and the teacher is then updated but the EMA of the student and not off of its own loss.
- this still requires large number of batches but not necessarily contrastive examples
##### DINO:
- Dino built upon this architecture but changed the asymmetry by adding centering  and sharpening, instead of batch normalizations which removed the need for large batches to avoid collapse.
#### iBOT:
-  Combined the idea of MIM and SD in order to avoid all need for augmentations, batchsizes and contrastive examples.
- The Student network:
	-  Gets 2 masked (corrupted) images
	- The BEIT encoder produces a CLS token and predicts the visual tokens for the masked patches for both masked images
- The teacher network:
	- takes in 2 full images
	- has an online tokenizer that has been traine to give meaningful visual tokens for the patches
	- produces a CLS token as well for both images.
	- the teacher is updated with an EMA of the weights of the student, not its own output.
- We then have 2 Types of losses that are symmetric for the 2 views (Thus 4 losses):
	1. One type of loss tries to match the CLS token of the student with the CLS token of teacher across the views which will make it want to predict global representation classification from the teacher
	2. the other type of loss will try to compare the predicted patches of the student with the visual tokens produces by the teachers tokenizer and try to improve upon it

## Transformers:
[[Transformers]]
- Attention -the main component of transformers- is the algorithm that allows our neural network to analyze the input and tell the deduce which part of the input is related and influenced by other parts the most, i.e which token should we pay attention to while processing each token in the input. With such algorithm, we do not have to do an exhaustive search over all tokens and and consider all feature tokens when processing input tokens, instead we can pay attention only to the ones that matter.
- Attention was revolutionary in the sequence modelling field because previously RNNs had to consider one token at a time sequentially, which lead to both scaling complexity with the context window AND a short term memory since over a long context window the information gets lost /explodes/diminishes.
- Self-attention is an attention algorithm applied to the input as context and as features, this is often used to understand the underlying structure of a given input and to generate that structure (instead of relating a certain input to a certain output)
- Cross-attention is an attention algorithm applied to a pair of inputs-output, such that it analyzes how each part of the input is influences each part of the output.
- Transformers have less inductive biases then CNN and RNNs making them build a richer representation space and also require a lot more data to train.
- Attention heads are efficient and can operate at large window sizes (Which RNNs cant since they have short term memory), and unlike RNNs they do not need to grow with the sequence length, self-attention also reduces maximal path length between long range dependencies (attend to all elements at the same time)
- Unlike RNN's Transformers can be parallelized during training
- Unlike CNN's Transformers store information
- Unlike RNNs and CNNs, transformers often provide us with a little interpretation (not explanation, big difference) if we try to analyze the attention scores given.
##### Attention Algorithm:
1. **Tokenization:** As mentioned above transformers have to have its input split into core elements, those core elements are called tokens and its those tokens we analyze, the assumption here is that for our problem tokens are the primal building blocks and they cannot be broken down into simpler tokens. (This process is done for the pair of inputs in cross attention)
2. **Embedding:** Tokens are input data building blocks, they could be of many modalities (string, images, numbers...), however our model only takes in numerical vectors. The embedding process is a semantic preserving process that takes in an input of any kind, and returns a vector that represent a latent of sorts for the features of this token. Additionally for our problem, it may be important to also not lose spatial information and thus the embedding also includes position information for each token in the entire structure. (This process is done for the pair of inputs in cross attention)
3. **Query, Key, Value computation:** The next computation is the heart of the attention algorithm, its the main part with learnable parameters in the Attention head and its comprised of three operations:
	1. *Query computation:* The term query is used to resemble our current context that are processing, i.e if we were to go to analyze one word (token) at a time in a sentence (For Cross-attention this is relating to a token in the first half of the pair, and for self-attention this is the input embedding itself), at each iteration the current word we are at is our Query, and its used later on to compute and analyze which other tokens relate to it the most . Query computation is straight forward, its simply a projection of the embedding of the token along a learnable parameter $q_{i} = Wq_{i}E_{x_{i}}$
	2. *Key computation:* The term key is used to resemble the token we are examining against our current query, i.e given our current query token, how much does this particular key token relate to it (for Cross attention this is relating to a token in the second part of the pair, whereas with self-attention its just the input embedding itself).  Key computation is quite similar to query except it uses different learnable parameters $k_{i} = Wk_{i}E_{x_{i}}$
	3. *Value computation:* Values are basically the latent outputs vector that we are looking for each matching token (In cross attention this is usually related to the later half of the pair, in self-attention this is the input embedding token itself), values can also be seen as displacement vectors that represent the displacement this current token causes in the semantic latent space.
4. **Attention Computation:** Taking our queries and keys for all the tokens, computed previously, we now perform a dot product between every key and query. The dot product is a measure of similarity between numerical vectors, and it produces a score that roughly indicates which keys contribute to which queries the most.
5. **Extra Score modification:** After getting the attention scores, a few things are noted, firstly the process we have achieved so far has been stacked with matrix multiplication which we want to avoid due to exploding gradients. Another thing to note is that the scale of the scores is usually out of proportion, while we do care about the "order of importance" in the scores, we often want to convert it to numerically stable probabilities where there aren't regions that experience extremely small gradients, thus we perform a scaling down process with a fraction $\frac{1}{\sqrt{d}}$ relative to the context size. Furthermore in certain tasks where we are meant to generate words, it is often wrong to have the knowledge of "future/ahead tokens" influence on our current token since we treat the input as if the query is the last token (only in self-attention), We can fix this issue by adding a mask that covers the upper triangular matrix with -infinity scores.
6. **Softmax:** We convert from scores to probabilities using the softmax function
7. **Compute Output:** We can compute an output for an attention head by multiplying the probabilities with the values we have computed earlier, i.e produce an output that consists of only the values that we should pay attention to according to our scores. $y_{i} = \sum\limits_{i} v_{i} softmax(\frac{q_{j}^{T}k_{i}}{\sqrt{D}})$
- **Note:** The gradients of an attention layer w.r.t to its QKV is: $$\frac{\partial f}{\partial q_{j}} = \sum\limits_{k} \sum\limits_{i} \frac{\partial f}{\partial y_{k}} \frac{\partial y_{k}}{\partial p_{ik}} \frac{\partial p_{ik}}{\partial q_{j}}$$ $$ \frac{\partial f }{\partial k_{i}} = \sum\limits_{k} \frac{\partial f }{\partial y_{k}} \left( \frac{\partial y_{k}}{\partial x_{i}} + \sum\limits_{l} \frac{\partial y_{k}}{\partial p_{lk} } \frac{\partial p_{lk}}{\partial x_{i}} \right)$$
> [!example]- Attention  Code Snippet
> ![[DeepLearning/Code Snippets#Attention Block|Code Snippets]]
##### Multi-Headed Attention:
- Multi-headed attention is a component that is comprised of many attention heads randomly initilialized such that each one of them learns its own "features", which is then combined (concatenated) with its other attention heads in the MHA. Lastly since the output dimension is going to be much larger than needed, we add a projection head at the end of the MHA to project that information back into the size we want it to be.
##### Transformer Architecture:
- The transformer is usually made of an Encoder and a Decoder, those of which have similar structure but differ in certain areas.
- **The Encoder** part is made up of many layers of transformer encoders, each of which is comprised of a res-net of multi-headed attention block alongside a feed-forward network (MLP) block. A Batch normalization is also added at the end of each resnet block. The encoder is fed positional input embeddings and will output embeddings in latent space that are forwarded to the decoder.
- **The Decoder** is often auto-regressive, meaning it generates one token at a time and will take all previously generated tokens as input in each iteration. At the start it will take a [CLS] token as input and will stop generating when it generates a [SEP] token.
  The architecture of the decoder consists of 3 Res-net blocks, first a MHA that is masked for future tokens that takes in the previous output as input followed up by BN, then a MHA that takes in the previous MHA's input plus input from the Encoder plus BN, then a feed forward MLP network plus BN. at the end we convert the output into probabilities using a linear layer with a softmax and pick the token with the highest probability.
##### Vision Transformers (ViT):
- So far we have only mentioned Text Transformers but they can be generalized into Convolution-free image transformers, the Idea is described in [[CookBook2#BEIT]] where we first need to tokenize the image into "visual tokens" followed up by the same architecture as previously mentioned.

## Graph Neural Networks:
[[Graph NN]]
- Graph neural networks are typically formulated as functions that take a varying size graph as input and output a representation of the graph. The representation usually takes the form of an embedding of the graph nodes in Euclidean space
- Graphs consists of  a set of nodes V and a set of directed/undirected weighted/unweighted edges E connecting the vertices, edges are symmetric in their representations, labels can also be attached to nodes and edges to provide extra information.
- Graph features can be learned through:
	- Sub-graphs: Represent the graph as a bunch of sub-graphs. This number exponentially grows with the size of the graph (Think of embedding space/feature space)
	-  Random Walks: Sample a random walk in a random direction alongside the graph , information about (non)locality of walks may be hard to recover. Many walks are required to represent the graph since theyre treated as sequences (think RNN). However This does not capture global information.
- Graph-focused applications: independent of the node i and implements a classifier or a regressor on a graph structured data set, i.e the whole graph is used to produce one output.
- Node focused applications: depends on the node n, so that the classification (or the regression) depends on the properties of each node. 
- Lets define a Graph G=(V,A) that consists of V a set of nodes, and A an adjacency matrix where aij denotes the weight between two nodes i and j, missing edge is represented through aij = 0 We define the degree matrix D = diag(d1, . . . , dn) is a diagonal matrix where each entry on the diagonal is equal to the row-sum of the adjacency matrix Each node vi in the graph has a corresponding d-dimensional feature vector xi Each node belongs to one out of C classes and can be labeled with a C-dimensional one-hot vector yi. 
- #### Weisfeiler-Lehman isomorphism test
	-  A test that allows us to learn more about two graphs that are "isomorphic", this test does not guarantee that they are, but it is necessary to prove that they are (If it fails then theyre not isomorphic for sure, if it succeeds then theres a chance theyre isomorphic and a chance that theyre not)
	- The idea behind it is the basis of the GNN network
	1. if nodes are not labeled, assign the same label to each node.
	2. Relabel nodes with tuple of own label and sorted multi-set of neighbor labels.
	3. Compress labels using hash function (here: sequential id). Its important to note that this hash function encodes the label of the current node and its neighbors, nodes that have the same label and same number of neighbors will result in the same label after hashing, moving  forward we will use this has function multiple times.
	4. We check our stop conditions and compare:
		- If the labels of the graph nodes differed from the last iteration -> We continue with step 2
		- If the labels of the graph nodes did not differ from the last iteration (at least one of the two graphs) -> Stop and check isomorphism
			- If both graphs have the same representation -> Isomorphic
			- If the graphs have a different representation -> Not isomorphic
- #### Message Passing NN:
	- Similar to CNNs or MLPs, GNNs learn a new feature representation for the feature xi of each node over multiple layers, which is subsequently used as input into a linear classifier.
	- Has many implementations like GCN, DTNN, GGSNN but they all follow the same logic with diff functions and implementations.
	- The network consists of two phases:
		1. Message passing (transition): information is exchanged between the nodes of the NN.
		   Usually written as the function $x = F_w(x,I)$ such that I is extra node labels.
		   Theoretically the transition function needs to keep updating the graph until we reach a fixed point, We can guarantee the convergences to a unique fixed point according to Banach fixed-point theorem: Which denotes that in a metric space (for example euclidean governed by l2 norm) the map F is called a contraction map (converges to a fixed point) on X if there exists $\alpha \in [0,1)$ such that $\|F(x) - F(Y)\| \leq \alpha \|x-y\|$. In our case we can guarantee this by adding lipschitz Regularization (which is basically a gradient penalty to the loss function) $\| \frac{\partial F_w}{\partial x}\|$ Lipschitz regularization enforces Lipschitz continuity which ensures a certain smoothness (in the sense that there are no sudden jumps and step function like movement) to the function applied. hence an existence of a unique solution to converge to. This is important to prove for implementations of Transition functions.
		   However in practice we dont apply this until convergence, we just choose T times/layers where we apply this until it has a rich representation of our graph features.
		   There is no need in storing the states of every iteration of message passing in this phase, only the final output is require for gradient computation because we reached a unique point.
		2. Readout Phase (output): computes an output from the given representation we have reached according to our problem (whether graph based or node based) 
	- ##### GCNN:
		- Quite complicated in the process of reaching the final product, id suggest you read the visual note about it, as i wont go into detail here besides the fact that we use the Laplacian eigenvectors as the fourier basis functions to perform convolution filters in the spectral domain.
		- Note: in order for a graph to have a discrete spatial convolution with translation, the laplacian needs to be a toeplitz matrix (diagonals' values are equal), in which case all nodes have to have equal degrees
		- The definition of convolution in the spatial domain faces many challenges, limitations and just doesnt work, which is why we define it in the spectral domain.
		- The convolution Operating is comprised of three stages:
			1. Feature propagation where we update our graph representation with the message passing between neighbors $H^{l+1} = \tilde{D}^{-\frac{1}{2}} \tilde{A} \tilde{D}^{-\frac{1}{2}} H^{l}$
			2. Linear transformation Where we multiply the representation with learnable parameters W to project into a representation we want
			3. non-linear pointwise activation function to enrich the solution space
			- Transition function: $H^{l+1} = \sigma(\tilde{D}^{-\frac{1}{2}} \tilde{A} \tilde{D}^{-\frac{1}{2}} H^{l} W^{l})$ Where it performs a convolution of the neighbors if each node and the receptive field gets larger by the layer
		- The output function is not unique in GCNN and can be written like any output function in GNN commonly used as:
			- Graph based output: $Y = \frac{1}{N} \sum\limits_{i=1}^{N}f(x_{i})$
			- Node based Classification: $Y = softmax(H^{K})$
> [!example]- Graph Convolution  Code Snippet
> ![[DeepLearning/Code Snippets#Graph Convolution|Code Snippets]]

## Neural Ordinary Differential Equations:
[[ODE NN]]
- Differential equations are functions that describe the rate of change of another unknown function that we desire to approximate $\frac{\partial u(t)}{t} = f(u(t),t)$
- The ODE that we use here is non-linear, autonomous (time invariant) and homogeneous.
- Initial Value problems are problems that have an initial value at time 0 and an ODE describing them. According to picard lindelof theorem if f is continuous in t and locally lipschitz continuous then there exists a unique solution such that this ODE describes the trajectory though its solution
- **Integration Methods:**
	1.  Explicit Euler: $u(t+h) = u(t) + h\cdot f(u(t))$
	2. Implicit Euler: $u(t+h) = u(t) + h \cdot f(u(t+h))$
	3. Runge-Kutta 4-5: $u(t+h) = u(t) + \frac{h}{6} \left( f_1(u(t)) + 2 f_2(u(t) + \frac{h}{2}u(f_{1}))+ 2 f_{3}(u(t) + \frac{h}{2}f_{2}) +f_{4}(u(t)+hf_{3})\right)$ which uses a 4th order solution to estimate error and set step size and  steps with 5th order solution
- ##### Neural ODEs:
	- Implicitly theyre discretized and defined as resnets, since L layers of resnets will modify the input slightly each time until the target point is reached. Other methods like depe equilibrium modes can be seen as ODEs as they transform infinite layers into a one iterative layer that reaches a state of equilibrium through a root finding method to optimize on memory.
	- Explicitly it can be modelled as a neural network parameterized by theta to describe the phase space, the time is then modelled from 0-1 since there is no real meaning for time and our input is the IV. The ODE solver is an initial layer, which is followed up by some linear layers and softmax (according to our goal) to classify accordingly.
	- However Back-propagation through the iterative ODE solver is not completely straight-forward:
		1. Discretize then Optimize: which does back-propagation through all step of the ODE solver by saving the states in memory which makes it memory inefficient, but accurate. This method uses automatic differentation to differentiate the forward process and back-propagates it.
		2. Optimize then discretize: which involves solving another ODE (adjoint ODE) back in time to find the relations of the loss function to our parameters defined in the change of rate function, this is only possible because the ODE is invertible. This is memory efficient because nothing needs to be saved however its slightly inaccurate due to discretization errors.
> [!example]- Neural ODE  Code Snippet
> ![[DeepLearning/Code Snippets#Neural ODE]]
- ##### Augmented NODES:
	- Neural ODEs are not universal function approximators, if anything they sometimes cannot model simple functions like $g(x) = -x$ because of the IVP unique solution property that states that we always have a unique solution (which makes it invertible and bijective), which means no two flows shall intersect otherwise the solution wont be unique. This limits the complexity of the problems we can model quite a lot, becuase we are only limited to topology preserving deformation.
	- Augmented NODES -similarly to Kernels- map the input into a higher dimensional feature space that allows expressiveness and allows linearly inseparable models to be linearly separable. this will also make the learned (augmented) g smoother, giving rise to simpler flows that the ODE solver can compute in fewer step

## XAI
[[Explainable AI]]
- ##### LRP:
	- Use the structure of the neural network to robustly Propagate the output of the network backwards by means of propagation rules
	1. **Gradient x Input (LRP-0): ** $R_j = \sum_k \frac{a_jw_{jk}}{\sum_{0,j} a_j w_{jk}} R_k$
		- Suffers from shattered Gradients
		- not faithful nor understandable
		- can be use as a composite in upper layers
	2. **LRP Epsilon:** $R_j = \sum_k \frac{a_jw_{jk}}{\epsilon_k + \sum_{0,j} a_j w_{jk}} R_k$  The role of epsilon is to absorb some relevance when the contributions to the activation of neuron k are weak or contradictory.
		-  too sparse to be understandable but its regularized so its faithful
		- used in middle layers as a composite to filter out spurious variations and r
	3. **LRP Gamma:** $R_j = \sum_k \frac{a_j(w_{jk} + \gamma w_{jk}^+)}{\sum_{0,j} a_j (w_{jk} + \gamma w_{jk}^+)} R_k$ focusing on the positive contributions over the negative contributions
		- not super faithful since it favors positive ones over negative contributions, but is the features are densly highlighted and understandable.
		- Used in lower layers to translate it to something more understandable for humans
- ##### BiLRP:
	- Cant use GI methods because of the shattered gradient effect (White noise type gradients in deep neural networks's last layers).
	- We upgrade to a hessian x input implementation inspired implementation
	- takes two pairs and if they jointly activate such that the pairs in the next layer also jointly activate then a relevance score is calculated (LRP gamma adaptation for 2 terms jointly)
	- This can be quite expensive so we can composite it into a bunch of factored LRP forms
	- $R_{jm} = \sum\limits_{k} \frac{a_{j} \rho(w_{jk})}{\sum\limits_{j} a_{j} \rho{w_{jk}}}$ and $R_{kk^{'}} = \sum\limits_{m=1}^{h}R_{km}R_{k^{'}m}$
- ##### TransLRP:
	- Conservasion axiom says that the scores assigned to the input must sum up to the output scores at each neuron
	- Transformers by default are not conservative thus we need to detach extra paths
	- In the attention head we reformulate the contribution to: $R(x_i) = \sum_j \frac{x_i p_{ij}}{\sum_k x_k p_{kj}} R(y_j)$ which means that we detach the softmax in y computation
	- In the layer norm we reformulate the contribution to: $R(x_i) = \sum_j \frac{x_i \cdot (\delta_{ij} - \frac{1}{N})}{\sum_k x_k \cdot (\delta_{kj} - \frac{1}{N})} R(y_j)$ which means we detach the normalization variance term at the bottom of the fraction
 > [!example]- Transformer LRP  Code Snippet
> ![[DeepLearning/Code Snippets#Sequence classification Transformer (detachment method Attention)]]
 > [!example]- LayerNorm LRP  Code Snippet
> ![[DeepLearning/Code Snippets#Sequence classification Transformer (detachment method Norm)]]
- ##### GraphLRP:
	- Graphs have message passing layers where nodes contribute to all their neighbors, first order methods will not cut it for explanations.
	- We can use the detachment method to re-write the graph LRP to a form that can compute LRP per layer for the state of the graph.
 > [!example]- GNN LRP  Code Snippet
> ![[DeepLearning/Code Snippets#Graph classification GNN (detachment methods GNN-LRP)]]


## Generative Modelling:
[[Generative Modelling]]
- Unlike Traditional Machine learning models Generative Models do not produce a conditional probability $p(Y|X)$  but instead produce the joint probability of our latent representation $P(X,Y)$ further allowing us to sample from it and to estimate probabilities for a given sample
- Implicit likelihood models (GAN, DDM): the likelihood of data samples P(x) is used indirectly, it can be inferred and approximated from the model, which leads it to give very diverse generations.
- Explicit likelihood models (VAE, NF): the likelihood of data is modeled directly, which leads it to generate higher quality data in more complex distributions
- #### Auto-Regressive Generative Models:
	-  Auto-regressive models do not learn the latent space of data distribution and thus are not able to handle semi-supervised approaches
	- ###### PixelCNN:
		- A CNN based Generative model that generates pixels according to thepreviously generated pixels.
		- This is done by masking a filter over the pixels to only take in the previous pixels.
		- Blind spots in the receptive field are avoided by combining two convolutional filters (Vertical and horizontal)
	- ###### GPT:
		- A model based on transformer architecture with self attention heads.
		- trained on large amount of self-supervised data in an auto-regressive manner (given the previous words generate the most likely upcoming word)
	- ###### Generative SchNet:
		- a model that uses atom charges and distance embeddings with a feature extractor to extract certain features about atoms in a mollecule.
		- this information is then fed to a generative network that produces a distribution over the possible positions of this new attached atom
		- This model generates one atom at a time based off of the previously generated atoms in a mollecule
- #### Variational Auto-Encoder:
	-  Given an observsation X and a latent variable Z we can calculate the posterior distribution $P(Z | X)$ using bayes theorem, given $P(X|Z)$ and $P(Z)$
	- The likelihood $P(X|Z)$ is infact generally intractable, however we can try to either approximate it using monte carlo, Or try to learn a distribution Q such that its as close to the likelihood as possible.
	- **Variational Inference:** is the approximation of a likelihood distribution with a tractable distribution and its the minimization of the follow KL divergence $D_{KL}[ Q(Z|X) \| P(Z|X)]$ 
		- The KL-divergence can be re-written into $E_{z~Q}[log Q(z|X) - log P(X|z) - log P(z)] + log P(X)$ and its goal (Objective1) is to approximate the posterior by minimizing the distance of our learned distribution to it
		- P(X) is not known but we can add another objective to try and approximate P(X) (jointly with our Variational inference objective1) we call objective 2 which is approximating P(X)
		- Evidence Lower bound (ELBO) which is the new objective: $log(P(X)) - D_{KL}[ Q(Z|X) \| P(Z|X)] = E_{z~Q}[log P(X|z)] - D_{KL}[Q(z|X) \| P(z)]$
		- The left side defines our objectives: Objective 2 is the first term and its approximating P(x), Objective 1 is the second term and its approximating the posterior by minimizing discrepancy
		- The right side is the actual optimization Process: the first term tries to sample our learned latents such that theyre perfectly decoded into a distribution that models P(X) as best as possible, and the second term tries to encode X into latent space using Q using as much of the prior distribution as possible.
		- P(Z) needs to be a simple tractable distribution that we can easily sample from
	- This allows us to sample from the simple distribution P(Z) and decode it into an actual X that makes sense.
	- This allows us to find a dense representation of a datapoint by encoding it
	- This allows us to calculate the evidence/outlier score of a new datapoint.
	- Generative models usually fail at Outlier detection even tho they try to estimate the evidence distribution because The lowest latent variables learn generic low-level features yet theyre seen as features that would suggest that it is part of the distribution that we have.
	- Note: Does not give exact likelihood but an approximation (lower bound) of it
- #### Normalizing flows
	- In previous methods, we tried to approximate the likelihood dist which is complex and intractable with another distribution that is simpler to sample from. This "simple" family constraint on our estimate really limits our options, and does not allow us to learn overly complex distributions accurately.
	- normalizing flow describes the transformation of a probability density through a sequence of invertible mappings. By repeatedly applying the rule for change of variables, the initial density ‘flows’ through the sequence of invertible mappings.
	- Each transformation must be invertible (bijective which leads to no reconstruction loss) and differentiable, but can be a learned neural network. furthermore to ease the computation of the det Jacobian which can be expensive, we choose f carefully such that it simplifies the computation.
	- Change of variable formula: $p_{\theta}(x) = p_{\theta}(f^{-1}(x)) |det(\frac{\partial f^{-1}(x)}{\partial x}) |$ which simplifies to $log p_{\theta}(x) = log p_{\theta}(z) + \sum_i log|det(\frac{\partial f_i^{-1}}{\partial x}) |$
	- The change of variable forumla tends to expand thevvolume of representation space associated with more“interesting” regions of the input (e.g., highvdensity regions, in the unsupervised learning case).
	- ##### Coupling Layer trick (NICE, GLOW, RealNVP):
		- we limit our choice of f such that the determinant of the Jacobian and its inverse are trivially obtained.
		- This triviality comes from the fact that if a matrix is triangular then the determinant of it is the sum of its diagonal
		- The core idea behind this is that we can split x into two blocks (x1, x2) and apply a transformation as building block a transformation from (x1, x2) to (y1, y2) of the form: $y_{1}= x_{1}$ and $y_{2} = g(x_{2} , m(x_1))$ which inverts to $x_{1}= y_{1}$ and $x_{2}= g^{-1}(y_{2}, m(y_{1}))$
		- This building block has a simple Jacobian det for any arbitrarily complex m (RELU MLP for example) and is trivially inversed by ensuring a simple g.
		- This can be combined in an alternating matter to form multiple layers of coupling such that no half is left untouched by the transformation and all the variables interact with each other.
	- ##### Free-Form Jacobian Continuous Normalizing Flow (FFJORD):
		- Continuous normalizing flows are models that sample from a base distribution a latent z then given an ODE parameterized by a NN solve the initial value problem to obtain z1 which constitutes as the observable x.
		- The change of variable formula is however different in this model the change in log-density under this model follows a second differential equation, called the instantaneous change of variables formula: $\frac{\partial logp(z(t))}{\partial t} = -Tr(\frac{\partial f}{\partial z(t)})$
		- No need to ensure bijectiveness because Banachs fixed point theorem for Initial value problems ensures uniqueness in the function c if its lipshitz continuous which can be satisfied using lipschitz regularization on activations.
		- Given a datapoint x, we can compute both the point z0 which generates x, as well as log p(x) under the model by solving the initial value problem: $$ \begin{bmatrix}z_{0}\\ logp(x) - logp_{z_{0}}(z_{0})\end{bmatrix} = \int_{t_{1}}^{t_{0}} \begin{bmatrix} f(z(t),t) \\ E_{p(\epsilon)[\epsilon^{T} \frac{\partial f}{\partial z)t)} \epsilon]}\end{bmatrix}dt$$ given that $$\begin{bmatrix}z(t_{1}) \\ logp(x) - logp(z(t_{1}))\end{bmatrix} = \begin{bmatrix}x \\ 0\end{bmatrix}$$ is the initial Value
	- ##### Counter-Factual information generation:
		- if we take a datapoint from class 1 and force it to change its features to be apart of class 2 (adversarial attack), usually this will produce a nonsense version of the datapoint that doesnt necessarily look like class 2 but is out of the manifold that its not classified as class 1.
		- This is because normal models do not learn the data manifold, instead they learn how to separate regions in it, but they learn the entire input space X that can have nonesense as a part of it.
		- If we tried this in the latent space Z of models that model the likelihood function explicitly we would see that in fact we can make sense of counterfactual information.
- #### Generative Adversarial Nets:
	- GAN is a generative implicit likelihood estimator model via an adversarial process. The model consists of two networks, D the discriminator which tries to predict whether the input given was from the dataset or not, whilst G the generator network tries to generate datapoints similar to our dataset such that it fools our discriminator.
	- GAN is then trained on the following objective: $min_G max_D E_{x \sim p_{data(x)}}[ \log D(x) ] + E_{z\sim p_x(x)} [\log (1-D(G(z)))]$
	- The first term tells us How well can the discriminator tell that x is from the dataset, the second term tells us How well can the discriminator tell that G(z) is not from the dataset.
	- the optimal discriminator D for any given generator G is : $D^{*}(x) = \frac{p_{data(x)}}{p_{data(x)}+ p_{g}(x)}$ which reaches a global minimum value of -log4
	- ##### Conditional GAN (PatchGAN, LapGAN):
		- conditional GANs (cGANs) learn a conditional generative model that maps a random noise z given an observed image x to a generated image y, this significantly improves the sample quality .
		- PatchGAN suggests using L1 Loss as a second objective to help be near the ground truth output in quality. The L1 and L2 norm produces blurry results on  image generation problems because they fail to encourage high-frequency crispness in many cases they nonetheless accurately capture the low frequencies This motivates restricting the GAN discriminator to only model high-frequency structure, relying on an L1 term to force low-frequency correctness $\mathcal{L}_{L1} (G) = E_{x,y,z} [ \| y - G(x,z) \|_1 ]$
		- This discriminator is run convolutionally across the image, averaging all responses to provide the ultimate output of D
		- LAPGAN on the other hand exploits the Laplacian structure of images to build a laplacian pyramid reconstruction The Laplacian pyramid is a linear invertible image representation consisting of a set of band-pass images, spaced an octave apart, plus a low-frequency residuals (more explained in the note).
		- This is exactly the conditional Gan (specifically the generator's) objective now, its given K generators, for each an upsampled version of the smallest image is given (different sizes) and a noise vector, the generator has to turn the noise vector into the corrosponding level  laplacian coefficients given the previously upsampled picture
		- The discriminator is then trained on differentiating between the real laplacian coefficient at every level and the Generated laplacian  coefficient of the generator network
	- ##### Cycle Translation GAN (cycleGAN, UNIT):
		- we are given one set of images in domain X and a different set in domain Y, a mapping  G : X → Y such that the output ˆy = G(x), x ∈ X, is indistinguishable from images y ∈ Y by an adversary trained to classify ˆy apart from y
		- Key Idea: the Image to image translation in cycleGAN needs to be cycle consistent, in the sense that if we translate, e.g., a sentence from English to French, and then translate it back from French to English, we should arrive back at the original sentence, this is a necessary condition to ensure that x to y are mapped in a meaningful way
		- Generator G turns from domain X to domain Y, Generator F turns from domain Y to domain X, discriminator Dx tells the difference between x and F(y), discriminator Dy tells the difference between y and G(x).
		- Objective is now : $L(G,F,D_X,D_{Y)}= \mathcal{L}_{GAN}(G, D_{Y}, X, Y) +  \mathcal{L}_{GAN}(F, D_{X}, X, Y) + E_{x \sim p_{data}(x)} [ \|F(G(x)) - x \|_{1}] + E_{y \sim p_{data}(y)} [ \|G(F(y)) - y \|_{1}]$
		- UNIT builds upon this cycle consistency idea but introduces two VAE that map X and Y to one latent domain Z which is then used in the Generators that map to the opposite domain back and two discriminators for them.
- #### Diffusion Models:
	- ###### DDPM:
		-  Diffusion models are latent variable models of the form $p(x_{0}) = \int p(x_{0...T}) dx_{1...T}$ where x1...xT are latents of the same dimensionality as the input data x0 Diffusion models continuously add noise to the input data over T interation until it turns into Gaussian noise.
		- The generative process is then the reverse of the learned gaussian noise applied at every step, such that we can sample a gaussian noise image and turn it into an actual image
		- **Forward / diffusion / inference process:** adds noise and goes from t=0 to t=T converts any complex data distribution into a simple, tractable, distribution.
			- The data distribution is labeled $q(x_0)$ which is gradually converted into a well behaved and tractable distribution, usually a 0 mean diagonal covariance gaussian
			- each step is defined as $q(x_{t}|x_{t-1}) = \mathcal{N}(x_{t}; \sqrt{1- \beta_{t}} x_{t-1}, \beta_{t}I)$, but since each step is a gaussian (typically), a composition of gaussians is also a gaussian and can be written out as $q(x_{t}|x_{0}) = \mathcal{N}(x_{t}; \sqrt{\hat{\alpha}_t} x_{0}, (1-\hat{\alpha}_t)I)$ such that $\alpha_{t}= 1 - \beta_{t}$ and $\hat{\alpha}_{t}= \prod\limits_{s=1}^{t}\alpha_{s}$ which means xt can now be written a linear combination of x0 and a noise variable.
			- the entire trajectory is then described with $q(x_{0...T}) = q(x_{0}) \prod\limits_{t=1}^{T} q(x_{t} | x_{t-1})$
		- **Generative / sampling / reverse process:**
			- removes noise and goes from t=T to t=0, a finite-time reversal of the diffusion (or an approximation of the reversal in some cases)
			- The reverse process describes the same trajectory but in reverse
			- the entire reverse trajectory is then described by $p(x_{0...T}) = p(x_{T})\prod\limits_{t=1}^{T} p (x_{t-1} | x_{t})$
			- During learning only the mean and covariance for a Gaussian diffusion kernel need to be estimated $p(x_{t-1}|x_{t}) = \mathcal{N}(x_{t-1}; \mu_{\theta}(x_{t},t), \Sigma_{\theta}(x_{t},t))$
		- The object that models the maximization of the log likelihood is given out in the form $$L = E[ \log p(x_{0})] = \int q(x_{0}) \log \left[ \int q(x_{1...T}|x_{0}) p(x_{T}) \prod\limits_{t=1}^{T} \frac{p(x_{t-1} | x_{t})}{q(x_{t} | x_{t-1})} dx_{1...T} \right]dx_{0}$$
		- But it is intractable thus we compute its variational lower bound which we then simplify into an efficient objective $$= -\log p_{\theta}(x_0|x_1) + D_{KL} \left[q(x_T | x_0) ||  p_{\theta}(x_T) \right] + \sum_{t=2}^T D_{KL} \left[ q(x_{t-1} | x_t,x_0) || p_\theta(x_{t-1} | x_t) \right]$$
		- each step of this objective is trying to approximate our generative process step at time t, to the reverse of the forward process at time t.
		- we usually set the variance to a time constant sigma, and then end up with an objective that tries to estimate the mean at every t, with the help of reformulation, the objective of minimizing the distance between the two means can be written as an objective of predicting the noise in the posterior forward process mean $\| \epsilon - \epsilon_{\theta}(x_{t},t)\|^2$
		- The length of T allows the forward process to converge to a gaussian and thus the generative process to be accurate, but its downside is that its extremely slow to generate from.
	- ###### DDIM:
		- DDIM is a faster better and deterministic version of DDPM that trains on the same objective but introduces a non-markovian process of inference.
		- we define a new family of forward processes indexed by sigma which indicates the stochasticity of the step, at sigma=0 the model is deterministic, and it can be shown that at certain values of sigma, the model is equivalent to DDPM.
		- q no longer depends on the previous step, but it also depends on x0  which makes it an IVP
		- DDIM samples have the following “consistency” property, which does not hold for DDPMs: if we start with the same initial latent variable and generate several samples with Markov chains of various lengths, these samples would have similar high-level features
		- DDIMs have superior sample generation quality compared to DDPMs, DDIM also have 10x sample generation speed
		-  a model trained on any value of sigma can be used for all other values of sigma, so theoritically DDPM trained models can be tweaked to generate DDIM style because both training objectives are the same!
		- with the way The model generation process is now defined, it can be seen as a neural ODE process such that the initial value is x_0 and each time step is taken toward this deterministic trajectory, the more steps we take the more accurate the result is.
		- by breaking the Markovian condition, we can now skip steps in the generation process to make the generation faster, because the objective does not depend on the length of the diffusion process T.
		- We find out that the high level features stay the same with different sequence lengths and instead we get more details with longer sequences
		- This is because the noise generated at the start is the embedding of those high level features
		- we can also interpolate between high level features, by interpolating between the initially sampled noise.
		- we can also train a classifier to associate noise with class labels and thus guide the sampling to be more classk like by introducing the gradient of the classifier to the noise sampling function
> [!example]- Diffusion process  Code Snippet
> ![[DeepLearning/Code Snippets#Generative models]]]

## Reinforcement learning:
[[Deep Reinforcement Learning]]
- Reinforcement learning is an algorithmic concept that places you (the agent) in an environment that reacts to your actions, the goal is to explore the environment such that you find the best course of action at any given situation to maximize your rewards.
- Reinforcement learning does not have a metric of accuracy -unlike supervised and unsupervised learning- , it instead has a holistic view on the total performance by calculating the reward/score you got, youre given an evaluation on how well you did without breaking it down into steps.
- **Notation:**
	- S is the set of all possible states s of our system
	- A(s) is the set of all possible actions (a) that can be taken at state s
	- $T(s^{'} | s, a)$ is a state sampling distribution conditioned on the previous action and state
	- $\pi (a|s)$ is an action sampling distribution (policy) conditioned on the previous state
	- R(s,a) is a reward function that calculates the appropriate reward for taking the action a at state s
	- V(s) is a value function that evaluates the value of current state s by estimating the future potential of our systems score given we are at that state.
	- Q(s,a) is a value-action function that evaluates the value of the current action a performed at statse s by estimating the future potential of our systems score.
	- $\gamma$ is a discount factor that weighs the importance of future long term rewards.
- **Value function as a model metric:**
	- We are given a model of a RL environment and are trying to learn the best policy, one way of evaluating the quality of our actions is by using the value function to estimate the value of the states we sample from our model.
	- The value function is formulated as follows: $$V^{\pi}(s) = E_{\pi, T} \left[\sum\limits_{t=0}^{\inf} \gamma^{t} R(s_{t}, a_{t}) | s_{0}=s \right]$$ given the starting position S, the value of s according to our distributions is the entire future rewards we ought to get by walking that path, each step consecutively discounted with a decaying factor.
	- According to the bellman equations this defines a recursive relationship into the future which can be solved iteratively backwards in time by dynamic programming by doing $V^{\pi}(s^{t}) = E_{\pi, T}[R(s^{t}, a) + \gamma V^{\pi}(s^{t+1})]$ 
	- a small problem arises by using the value function as a metric. We usually aim for a metric that helps us improve during training by updating our output, the value function here evaluates the state value regardless of which action we take afterwards, and if we want to improve our action policy, we want a metric that takes in different actions into account.
	- Which is why we use the state-action value function: $$Q^{\pi} (s,a) = R(s,a) + \sum\limits_{s^{'}}T(s^{'}|s,a) \gamma V(s^{'})$$ which is calculated if we know the transition function T (typically we dont)
- ### Reinforcement learning models:
	- There are MANY different types of RL models, and they differ in their methodologies, metrics and updates. They generally split into 2 types, Model-based RL models learn a model based off of a given environment that is already set and cant be changed (this is not the type we focus on here), While Model-free RL takes in a dataset of episodes (simulations/walkthroughs) and treats the model as a blackbox that is trying to estimate the environment and learn from it as best as possible.
- #### Model-Free RL:
	- ##### Naive Monte-Carlo Method:
		- Monte-carlo methods for random sampling and estimating values in RL is used in situations with a finite length episode (win/lose situations)
		- an episode defines a full simulation from the starting position until the result.
		- Given M episodes such that M is a very large number, monte carlo will converge to the real value: $V(s) = E[G_{1...M}(s)]$
		- Monte Carlo tries to improve the estimation of future values of every state (visited) by sampling episodes and updating according to the experienced episode, it goes as follows:
			1. Sample and run an entire episode. $G_{i}= \sum\limits_{k=i+1}^{T} \gamma^{k-i-1}R_{k}$
			3. Go over every state visited in that episode
			4. Update the future value of each state by averaging over the future value you have experienced from that state in that episode. $V(s) \leftarrow V(s) + \alpha (G_{i} - V(s))$
			5. repeat for many many samples.
		- Alpha is a normalization term associated to the length of the future sequence (average), this will converge once the estimate is equal to the real experience $G_{i} = V(s)$ as there is no more learning to be done.
		- Remember that the updates happen after the entire episode is done, and is averaged out over the sequence length. This gives the steps taken in an episode equal importance even if theyre bad steps (which is why this method requires millions of episodes to converge)
	- ##### Temporal Difference Method:
		- Temporal difference is an adaptation of the Monte carlo method such that the window of importance is limited (i.e only the last window of actions contribute to the current reward gotten), which means we also update the values after every step because we dont take into account the entire episode. In the simplest form we take a window size of 1
		- The idea is at every state in the episode to update that state's value function by using the future rewards gotten in the window, since this state is within the window of context that contributed to that future reward. $$V(s_{t}) \leftarrow V(s_{t}) + \alpha ( R_{t+1} + \gamma V(s_{t+1}) - V(s_{t}))$$
		- Here yet again we compare our estimate $V(s_t)$ with what we experienced in the episode $R_{t+1} + V(s_{t+1})$ (for our entire window) which we calculate by using the bellman equation backwards in the window of time.
		- ##### Off-Policy Methods:
			- Off policy methods are methods that tend to have a sense of exploration, they will update their value estimation according to the reward but then dont have to necessarily take that reward all the time instead they will have an element of randomness where they decide to take a risk and explore to find new routes.
			- This results in worse performance while learning but it has higher potential of reaching better results. it also learns faster due to not being scared of risk taking and learning from those mistakes.
			- It also introduces potential for major data efficiency as we can learn from previously used examples and replays.
			- ###### Q-Learning:
				- An example off-policy method that updates the values according to the best action to take but does not always take that action. For each step in every episode:
				1. Take an action a according to $\epsilon$ greedy sampling, i.e given an $\epsilon$, take the most optimal action according to the current policy with probability $\epsilon$ and take a random action sampled from a uniform distribution with $1-\epsilon$ probability.
				2. Observe the current state we reached and the reward we got by taking action a.
				3. Update the value you were at according to your future window $Q(s,a) = Q(s,a) + \alpha \left[R(s,a) + \gamma \max_{a^{'}}Q(s^{'},a^{'}) - Q(s,a)\right]$
				4. Go to the next state in the episode and repeat.
		- ##### On-Policy Methods:
			- On Policy methods are methods that only consider and take the best option estimate they have
			- this give a better performance during training because we always maximizing the reward we would get, but this is very conservative and doesnt like to explore, meaning it will be slower to train and less potential for an optimal path
			- usually worse than off-policy except in situations where mistakes are very costly and best avoided, becuase it learns the safer path.
			- ###### SARSA:
				- An example on-policy method that updates the values according to the best action to take and takes that best action. for each step in every episode:
				1. Take the best action according to our policy
				2. Observe the reward we got and the next state we reached by taking action a.
				3. look for the best action $a^{'}$ to take in the next state we reached.
				4. update the current state using it $Q(s,a) \leftarrow Q(s,a) + \alpha [ R(s,a) + \gamma Q(s^{'}, a^{'}) - Q(s,a) ]$
- #### Deep Model-free methods:
	- ##### Deep Q-Network (Value-Based):
		- DQN aims to greatly improve and stabilize the training procedure of Q-learning by using neural networks as a general value approximator and uses the following techniques to improve stability:
			- Experience Replay: all the episode steps et are stored in a replay memory D={e1...eT} During Q-learning updates, samples are drawn at random from the replay memory and thus one sample could be used multiple times this improves data efficiency, removes correlations in the observation sequences, and smooths over changes in the data distribution.
			- Frozen Target for periodical updates: Q is optimized towards target values that are only periodically updated. The Q network is cloned and kept frozen as the optimization target every C steps which makes the training more stable as it overcomes the short-term oscillations Our Objective
		- DQN goal is to minimize the MSE between True Q and the estimated Q: $$J(\theta) = E_{\pi}[(Q(a,s) - \hat{Q}(a,s;\theta))^{2}]$$
		- But we do not know the true Q thus we bootstrap our model to predict the Q-learning future value approximation using bellmans equation: $$J(\theta) = E_{\pi}[  R(s,a) + \gamma Q(s^{'}, a^{'})- \hat{Q}(a,s;\theta))^{2}]$$
	- ##### Deep Policy Network (Policy Based):
		- Does not learn the value function instead learns the policy function itself.
		- in continuous space where there are an infinite number of action or states to the estimate the value for, it is computationally more expensive to have a value based approach which makes policy based naturally better.
		- Our objective is formulated as follows: $$J(\theta) = E_{\pi} \left[R^{\pi(s, a)} \right] =  \sum_{a \in \mathcal{A}} \pi_\theta(a \vert s) R^{\pi(s, a)}$$
		- Using the policy gradient theorem we can reformulate the gradient to: $$\nabla J(\theta) = E_{\pi} \left[ \sum_{a \in \mathcal{A}}(R^{\pi(s, a)} )\nabla \log \pi_\theta(a \vert s)\right]$$
		- This has high variance and does not work all that well without further improvements
	- ##### Actor-Critic (Value and Policy based):
		- A method that combined the latter 2 methods by learning both the value function and the critic functions via neural networks.
		- Actor performs and updates the policy parameters in the direction suggested by the critic.
		- Critic evaluates and updates value function parameters, knowing the value function can assist the policy update, such as by reducing gradient variance in vanilla policy gradients $$\nabla J(\theta) = E_{\pi} \left[ Q^{\pi(s, a)} \nabla \log \pi_\theta(a \vert s)\right]$$
			1.  initialize the distributions and start with a sampled action
			2. sample reward and next state given by taking that action
			3. Sample the next action (On policy style)
			4. Update the actor parameters given your estimate of the value $\theta \leftarrow \theta + \alpha_\theta Q_w(s, a) \nabla_\theta \ln \pi_\theta(a \vert s)$
			5. compute the correction -TD error- for action-value at time t $\delta_t = r_t + \gamma Q_w(s’, a’) - Q_w(s, a)$
			6. use it to update the Critic $w \leftarrow w + \alpha_w \delta_t \nabla_w Q_w(s, a)$
			7. Repeat step 2-6 by setting the next action and state as current action and state
		- To reduce variance in this method without adding any bias, we introduce the Advantage function which removes the baseline from our objective $A(s, a) = Q(s, a) - V(s)$
			-  Intuitively, a step in the policy gradient direction should increase the probability of better-than-average actions and decrease the probability of worse-than- average action
			- the advantage function is not known and must be estimated
			- $\nabla J(\theta) = E_{\pi} \left[ A^{\pi(s, a)} \nabla \log \pi_\theta(a \vert s)\right]$
		- We can introduce a weighting term to the objective such that this turns into an Off-policy algorithm by defining a policy beta that we use to sample trajectories and a a policy that we optimize on $r(\theta) = \frac{\pi_\theta(a \vert s)}{\beta(a \vert s)}$ such that the objective is now: $$\nabla J(\theta) = \mathbb{E}_\beta \Big[\frac{\color{blue}{\pi_\theta(a \vert s)}}{\color{blue}{\beta(a \vert s)}} A^{\pi(s, a)} \nabla_\theta \ln \pi_\theta(a \vert s)\Big]$$
		- ###### Trust Region Policy Optimization:
			- The goal is to Maximize policy probability given the advantage function where to use the old policy, with the constraint that the old policy does not stray away from the optimized policy (using KL divergence)
			- This occurs a lot in off-policies (divergence of old from new) and can occur in on-policies when there are multiple async workers, thus we need to add contraints to ensure they dont stray away from each other.
			- The objective: $$\begin{aligned} J(\theta) &= \mathbb{E} \Big[ r(\theta)  \hat{A}_{\theta_\text{old}}(s, a) \Big]\\ & \text{s.t } \mathbb{E} \Big[D_\text{KL}(\pi_{\theta_\text{old}}(.\vert s) \| \pi_\theta(.\vert s)\Big] \leq \delta\end{aligned} $$
		- ###### Proximal policy optimization:
			- Aims to achieve the same thing as TRPO except its much simpler to formulate and compute
			-  The objectie imposes a constraint by forcing the parameter updates to the policies to be within a small interval of 1 $$J^\text{CLIP} (\theta) = \mathbb{E} [ \min( r(\theta) \hat{A}_{\theta_\text{old}}(s, a), \text{clip}(r(\theta), 1 - \epsilon, 1 + \epsilon) \hat{A}_{\theta_\text{old}}(s, a))]$$
> [!example]- RL   Code Snippet
> ![[DeepLearning/Code Snippets#Reinforcement Learning]]]


