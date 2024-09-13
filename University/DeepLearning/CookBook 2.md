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