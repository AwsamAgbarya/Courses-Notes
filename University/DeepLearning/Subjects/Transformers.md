---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Transformers ^VxM9Zp2Z

Saliency is the prominence of a particular thing in a given context
Transformers and specifically attention came to tackle such tasks
and implement it in our models, a way to simulate saliency and to focus
our models attention on what is relevant given the current context. ^gztxjHo5

Sequence Modelling ^lwhqKlst

The goal of sequence modelling is to generate/predict a sequence of components
these sub-components are modality dependent as they can be text or images or speech

For our model to read a sequence of variable length, it has to update its decision the
more we add to it and thus it needs a way to look back at everything its seen before and
remember what was there and correlate the new addition to it. ^KUVGtCw6

This is something we have already learned about in RNNs ^mVnTNgpq

For the decoder to generate information, all the relevant information about the input
needs to be put in the encoder state (context), which updates every time we have
a new input to the sequence. ^h6bqpO9X

OTHER then the issue of exploding gradient which occurs in RNNs, the encoder and encoder-state
processing one sequence at a time and updating the entire encoder state from scratch for
every new input can become really problematic with the increase of the length of the sequence ^Hn7e98v3

Attention ^vofBZXmU

Instead of allowing the decoder to directly look at input features
from the encoder, let the model decide what to focus on for the current
decoding step using an attention mechanisms that filters the input features
i.e if for the current decoding context, certain inputs are not relevant, then
why bother including them? let the model learn the relevance of each input for
each context and thus only look at relevant ones. ^P52DWdlU

Context = What matters x features ^SHsFwbC4

Note that theres a big difference between interpretability and explainability, transformers show us
their interpretation of attention, this however is not sufficient to explain why they make their
decision because attention only contributes to a part of their decision, there are other things
not showed in their interpretation that also contribute and explain the decision. ^5AiqhMRi

Self Attention ^HMztEBFz

also briefly explained
before in this note ^x8nOBBbs

YES THIS TOOK
ME AN HOUR TO DO ^9m7YN2cO

Embedding X ^lWm98oTC

NxD ^nZJEvFuq

Token ^RjdybtEh

Token ^ilPjGdMr

Token ^L9nYsN1N

Token ^YSP1zzzo

Token ^F31mQgTc

Input of Tokens ^v3UoToRw

1. Embed meaning
and position of
input ^nGzUM1os

2.1 Compute Query ^fsfRLJuO

2.2 Compute Key ^mMDqNSTq

2.3 Compute Value ^N44nnDVX

Learnable parameters ^sMQftesh

Learnable parameters ^UHThmYoj

Query ^PHPiIlT4

Key ^0QzL4nC8

Attention ^5El3kDW4

3. Dot Product ^gNUe2SKx

Learnable parameters ^YKw7Jgkr

Value ^MwzFGxR1

4. Scale
down ^hIQ85kOv

Scaled down
Attention ^OwUEbRQn

5. (Optional) Mask
future tokens ^ml18MqLB

Masked
Attention ^JWRmi8fY

6. Preform softmax
in order to get
probability dist ^qhhJHJ11

Weights ^BoNFtDtM

7. Multiply by values
to apply the attention
to the values ^pSMcFmLR

Softmax ^rTn6yFIV

Mask ^QgR5yKFm

Division ^HDVpQVW0

Dot Product ^NE8keUFk

Matrix Mult ^jo7ylYnf

Matrix Mult ^NozjapoF

Matrix Mult ^dOjfiAsy

Output ^rSVCbUBx

1) Embedding

The embedding process is a simple pre-determined process
that involves turning our tokens (for example words or sub-words)
into a set of vectors that have already been established by the embedding
method we use, its just a basic lookup table for all words.

alongside the embedding of the semantic of the token we also need to embed the
position of each word, I wont get into much details in this as its a bit irrelevant
but the process is by taking some sin function and cosine function and alternating
between them in odd and even positions to generate unique position vectors
which are then added to the semantic embedding ^7bwAnWUJ

2) Computing Query, Key, Value

This is the process in which we introduce Learnable parameters, because this is the
part that will later tell us what the relations of different tokens are.
Lets start by explaining what each Q,K,V are:



Query:
Query is usually interpreted as our current query, our current token treated
as context, the token we are looking to understand.
As in, given our current token as context, when we want to produce an output for it
what should we pay attention to/ put weight on in other tokens?



Key:
Keys are interpreted as a potential answer to the query question.
as in, given our current token as context, does it play any major role or weight
in describing other tokens?




Value:
Value can be seen as the adjustment we need to do on the current context embedding to
correctly model all of those other words that affected it.
this is all talking in representation space of the embedding.
 ^lKLCO5ti

lets be clear first that we do not understand what is saved in those learnable
parameters as it is beyond our understanding, it is what the model will learn
and we only make interpretations of what it will learn according to results. ^zyf5sL7f

(e.g Given the current word in a sentence, are there any adjectives behind it that give it more meaning?
our noun is the token and the query is the question of what we need to pay attention to) ^KVDN69AL

Wq ^5nEKHXka

Wk ^IxQ25jja

(e.g Given the current word in a sentence, are there any nouns in front of it that give it contributes to?
our adjective is the token and the key is the answer of what it affects) ^FQLdx2gZ

(e.g Assuming our current token has an influence on our context token, what is the value that I need to add
to the embedding of the context token in order for it to describe itself under the influence of the current token.
another lovely example from 3b1b: if our current context in the query is creature, and we determine that fluffy adjective
is describing creature, then the Value vector of fluffy is a vector that moves in representation space towards fluffyness
which if added to the vector of creature it would move it to a vector of fluffy creature) ^bxeKyKFS

3) Dot Product:
We know that the dot product is a similarity measure for vectors
giving us a score of how strongly do they align in their space.

So computing a dot product between all the token vectors viewed as the current
context (queries) and all the tokens' influence of other vectors being the context (keys)
we get a score matrix (size of 2x context window) that describes which tokens affect
which tokens in front and behind them. ^fv8gJqsk

4) Scaling:
This score matrix then undergos several modifications
to tune it to something we want.
the matrix is usually scaled down using the square root of the context size
in order to prevent exploding gradients, because so far we have only been
using matrix multiplication to move forward (we need numerical stability) ^o4Y6uetZ

5) Masking:
Since we take all of the tokens together and perform
these operations on them, we will end up with a matrix 
multiplication that shows each words effect on the ones
in front and behind it, this is sometimes unwanted as we do not
want to see its effect on future words, thus we mask the
lower triangle of the matrix and set it to -infinity score ^U2LcnvxM

6) Softmax:
This is quite a simple operation, we want to to turn our matrix
of score of attention, into a probability distribution (or weights that sum up to 1)
in order to properly quantify a linear combination of other tokens as the influence
on ours ^plxSKVCT

7) Multiply by values:

Now that we have the weights, all we need to do is multiply
them with the displacement vector in order to get the overall displacement
that our sentence has on our current context token ^fzoa3pRs

Cross Attention ^qQqzSlAO

Everything described in self attention is modeled such that the stream of tokens is
influencing itself so we need the model to look at itself to figure out what to pay
attention to!

Cross attention is also identical to self-attention, except the query and key
work on completely different datasets, for example a sentence in english and
in spanish, or even text and speech.

Also there is no masking in cross attention as there is no "future prediction"
part of it, its two different modalities affect each other equally ^bb3UxKUA

Multi-Headed attention ^mhXcVVyd

Multi-headed attention is compromised of many Attention heads that do not share
their learnable parameters but are instead set out to figure out their own patterns in the
tokens.
this is necessary because in such complicated tasks we often have MANY different ways a token
can influence another.
for example in words, on attention head can discover that adjectives describe nouns, while another head
can describe how nouns affect other nouns, anothe head can discover how certain words can describe
the tone of the sentence or turn the sentence into a question... and these are merely just logical
pattern we draw, there are many more hidden patterns that the model learn within itself! ^BxIBgKAf

Embeddings ^3QeyZ19w

Multi-headed
attention ^P3cwXDv5

Attention Head ^6wRqHtln

Attention Head ^qLDhNak5

Attention Head ^1XOO1rmz

+ ^Lsl6gMFO

The Output of each attention Head gets concatenated together
But then theyre also Projected down into the appropriate dimensionality
using another Matrix of learnable parameters (Linear Layer Projection head) ^cI7mwOPl

Skip-Connection & Linear Layer ^RHNKaaK0

As described in the explanation of why Resnets are beneficial for very large/deep
models, We introduce the Skip-connections here for better information AND gradient
flow in the transformer block, alongside a Normalization Layer.

For further processing and a more rich representation, We then send the output of
what we have into a few Layers called the feed forward network, this is just
a standard Neural network architecture, its not too special but it is necessary
to learn as much as possible about the data.

We also require to introduce the skip connection and batch normalization afterwards of course
because it is treated as a block in a resnet. ^3wnzmzdz

Decoder ^1vrskXsk

The transformer we have described so far is just an Encoder part of the entire mechanism
Obviously if we are using our model for any sort of task that does not require generation of
something, we do not need the Decoder part.
But usually in such complicated task we have another Transformer attached called the decoder and
it follows the exact same architecture but for a different purpose ^P4PzIO9X

Encoder ^YXJnDDrD

Decoder ^Fb2ylH55

embedding and
positional encoding of
output token (partially
masked) ^3LyT64MN

The Decoder is auto-regressive which means it takes
as its input the previous tokens it has generated, runs it through a multi-headed attention head
to see its effects, then takes in the input sequence interpreted by the encoder and combines
that information in the same architecture.
The decoder stops its process only when it has generated a token that marks the end of of a sequence.

The decoder is ended with a softmax function that gives a probability distribution of the best
next possible token which is then sampled and outputted and the decoding process begins again
with that token included. 

And just to be fully clear, the Encoder Transformer and Decoder Transformer can be stacked
on top of each other, each Decoder taking from its matching encoder to get a lot more nuanced
and rich representation ^ikY78YSx

Since this uses quadratic complexity
it can be rewritten in ways that has
linear complexity and constant memory
using an appropriate kernel function ^jvHYqTNu

Vision Transformer
(Convolution-free) ^Bz2eGNu5

Main Idea:
Instead of using convolutional layers represent an image as
a sequence of image patches (tokens) which helps the transformer
aggregate global information early due to self-attention (instead of
only building them in later layers as CNNs) ^KtFNemF9

This can sometimes outperform popular CNN architecture because CNNs heavily rely on textures
instead of patterns, whereas Transformers conclude their information from patterns

Obviously somewhat similarly to Unet, the skip connections help a lot in propagating low
level information forward. ^T3zk3vRJ

Read at the end ^pZehlBTg

Conclusions ^o1AdZzPf

1) Assumptions:
In comparison, Transformers have less strong inductive
biases as compared to CNNs or RNNs, this means there is a lot less
restrictions in their representation space, but also require a lot more training data
in order to perform well and are trained for weeks (Large carbon footprint).
This flexibility is given through the idea that we take the entire input as a whole and
model relations accordingly, whether we want future and past influenced is possible, spatial
information is not lost due to positional encoding, and different head learn different roles!


2) Efficiency:
Self attention heads are way more efficient than RNN block architecture and CNN filters
only when the sequence length is smaller than the size of the hidden dimension.

RNNs need to grow with the sequence length whereas self-attention is feed-forward
which means we only need to update the context window but the computation stays
the same
self-attention reduces maximal path length between long range dependencies
of input and output (attending all elements at the same time) and does suffer from short
term memory.

In Transformers, number of sequential computations are independent of sequence length during encoding,
but decoding complexity grows with the sequence length!


3) Parallelization
RNNs can memorize but operations can not be parallelized.
 CNNs can be parallelized but are not designed to store information.
Transformers can be parallelized in parts (the encoder and self-attention, the decoder only during training) and are able to memorize.


4) Interpretability:
Learned attention units are not directly interpretable, as there are a lot of processes that go on in transformers which are not 
shown in their visualized score matrix thus their interpretability is not explainability.
 ^XdvKFCDP

Are there any guarantees that the
different heads will learn different thing?
No, there is nothing stopping them
from doing so, but it is very unlikely
given the random initialization of the
weight matrix. ^14FAhQQ9

# Element Links
mVnTNgpq: [[RNN]]
x8nOBBbs: [[CNN]]
RHNKaaK0: [[CNN]]

# Embedded files
abbf541e9a3ea7694da52c91dcb9c9cc9021dbdf: [[Pasted Image 20240424170152_378.png]]
5d9ef33b446ff0bca2f52f582462b18286001ded: [[Pasted Image 20240424170332_854.png]]
366fd12db3fa947a4548e82b1d9db616989f5240: [[Pasted Image 20240424171343_925.png]]
196e33fe1cd528a6f0c33048e507a48555138a1d: [[Pasted Image 20240426150315_297.png]]
5be755c9687c057ba90a583b752c1c9eb648d439: [[Pasted Image 20240426151747_486.png]]
a7196e83173a6671a2aa260fa230f944509cf6ed: [[Pasted Image 20240426152629_410.png]]
6cd5127e4521ae573c886b5533dbcf8ba9b3148e: [[Pasted Image 20240426153920_637.png]]
c91d565a026d52c1f808aa1824172ddbd33fc3c0: [[Pasted Image 20240426154026_650.png]]
20f361f535c516198fa0b297aa3c2054e1a2b2e5: [[Pasted Image 20240426154234_667.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"id": "wX0UncgH2IbaZGjDXcE1Y",
			"type": "image",
			"x": 2492.39281436152,
			"y": 2688.7988278315806,
			"width": 241.5092609245584,
			"height": 439.46767151845864,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1116040391,
			"version": 298,
			"versionNonce": 1375578825,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137712804,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5be755c9687c057ba90a583b752c1c9eb648d439",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 1439056777,
			"isDeleted": false,
			"id": "VxM9Zp2Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -36.81444370033097,
			"y": 71.00328546923328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 182.95277404785156,
			"height": 35,
			"seed": 1149628426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Transformers",
			"rawText": "Transformers",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Transformers",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 408,
			"versionNonce": 56120711,
			"isDeleted": false,
			"id": "gztxjHo5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -357.9688966703806,
			"y": 143.7087287363949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 712.9193115234375,
			"height": 100,
			"seed": 2126786198,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Saliency is the prominence of a particular thing in a given context\nTransformers and specifically attention came to tackle such tasks\nand implement it in our models, a way to simulate saliency and to focus\nour models attention on what is relevant given the current context.",
			"rawText": "Saliency is the prominence of a particular thing in a given context\nTransformers and specifically attention came to tackle such tasks\nand implement it in our models, a way to simulate saliency and to focus\nour models attention on what is relevant given the current context.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Saliency is the prominence of a particular thing in a given context\nTransformers and specifically attention came to tackle such tasks\nand implement it in our models, a way to simulate saliency and to focus\nour models attention on what is relevant given the current context.",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 187,
			"versionNonce": 1025960553,
			"isDeleted": false,
			"id": "VJ5QzsmHzKoyqtxPp5ZYA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -294.49804310421,
			"y": 122.36652396969629,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 723.4797686902028,
			"height": 140.36373955426683,
			"seed": 297567382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 1021447335,
			"isDeleted": false,
			"id": "lwhqKlst",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1175.6138598269765,
			"y": 315.19753439443497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 251.46908569335938,
			"height": 35,
			"seed": 725532746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Sequence Modelling",
			"rawText": "Sequence Modelling",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sequence Modelling",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 714,
			"versionNonce": 59749705,
			"isDeleted": false,
			"id": "KUVGtCw6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1602.2174054286133,
			"y": 359.20284577686465,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 912.2191162109375,
			"height": 150,
			"seed": 1461364822,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The goal of sequence modelling is to generate/predict a sequence of components\nthese sub-components are modality dependent as they can be text or images or speech\n\nFor our model to read a sequence of variable length, it has to update its decision the\nmore we add to it and thus it needs a way to look back at everything its seen before and\nremember what was there and correlate the new addition to it.",
			"rawText": "The goal of sequence modelling is to generate/predict a sequence of components\nthese sub-components are modality dependent as they can be text or images or speech\n\nFor our model to read a sequence of variable length, it has to update its decision the\nmore we add to it and thus it needs a way to look back at everything its seen before and\nremember what was there and correlate the new addition to it.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The goal of sequence modelling is to generate/predict a sequence of components\nthese sub-components are modality dependent as they can be text or images or speech\n\nFor our model to read a sequence of variable length, it has to update its decision the\nmore we add to it and thus it needs a way to look back at everything its seen before and\nremember what was there and correlate the new addition to it.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 206,
			"versionNonce": 107470791,
			"isDeleted": false,
			"id": "qUYLhwG8P-ASHo7fBzhxY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1184.503967472514,
			"y": 517.7797392388334,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 292,
			"height": 94,
			"seed": 2126586646,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "abbf541e9a3ea7694da52c91dcb9c9cc9021dbdf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 1549542441,
			"isDeleted": false,
			"id": "mVnTNgpq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1371.6910245573497,
			"y": 620.6550101128978,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 567.8193359375,
			"height": 25,
			"seed": 474850442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": "[[RNN]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This is something we have already learned about in RNNs",
			"rawText": "This is something we have already learned about in RNNs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is something we have already learned about in RNNs",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 274,
			"versionNonce": 1107709671,
			"isDeleted": false,
			"id": "4_yzcCbQYDKcLGrLkF3DL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1359.2388816205012,
			"y": 666.9386529032258,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 669.8980880119941,
			"height": 213.8641783324676,
			"seed": 557871254,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5d9ef33b446ff0bca2f52f582462b18286001ded",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 478,
			"versionNonce": 58177289,
			"isDeleted": false,
			"id": "h6bqpO9X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1541.346294702321,
			"y": 894.5847611589847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 852.7791137695312,
			"height": 75,
			"seed": 1279958614,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "For the decoder to generate information, all the relevant information about the input\nneeds to be put in the encoder state (context), which updates every time we have\na new input to the sequence.",
			"rawText": "For the decoder to generate information, all the relevant information about the input\nneeds to be put in the encoder state (context), which updates every time we have\na new input to the sequence.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For the decoder to generate information, all the relevant information about the input\nneeds to be put in the encoder state (context), which updates every time we have\na new input to the sequence.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 557,
			"versionNonce": 1514789383,
			"isDeleted": false,
			"id": "Hn7e98v3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1482.1520200126704,
			"y": 983.3666913224013,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 774.7215576171875,
			"height": 60,
			"seed": 1128892426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "OTHER then the issue of exploding gradient which occurs in RNNs, the encoder and encoder-state\nprocessing one sequence at a time and updating the entire encoder state from scratch for\nevery new input can become really problematic with the increase of the length of the sequence",
			"rawText": "OTHER then the issue of exploding gradient which occurs in RNNs, the encoder and encoder-state\nprocessing one sequence at a time and updating the entire encoder state from scratch for\nevery new input can become really problematic with the increase of the length of the sequence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "OTHER then the issue of exploding gradient which occurs in RNNs, the encoder and encoder-state\nprocessing one sequence at a time and updating the entire encoder state from scratch for\nevery new input can become really problematic with the increase of the length of the sequence",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 589,
			"versionNonce": 727576041,
			"isDeleted": false,
			"id": "CCWBwHEI8Y9fomf-AdLhY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -618.8071126559246,
			"y": 633.6841021890584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 1068222678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 875495719,
			"isDeleted": false,
			"id": "vofBZXmU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -13.203364503700357,
			"y": 315.1975340656389,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 128.94053649902344,
			"height": 35,
			"seed": 1542989590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Attention",
			"rawText": "Attention",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Attention",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 401,
			"versionNonce": 723142857,
			"isDeleted": false,
			"id": "P52DWdlU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -397.136912598306,
			"y": 359.202846147376,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 774.0391235351562,
			"height": 150,
			"seed": 1182840906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Instead of allowing the decoder to directly look at input features\nfrom the encoder, let the model decide what to focus on for the current\ndecoding step using an attention mechanisms that filters the input features\ni.e if for the current decoding context, certain inputs are not relevant, then\nwhy bother including them? let the model learn the relevance of each input for\neach context and thus only look at relevant ones.",
			"rawText": "Instead of allowing the decoder to directly look at input features\nfrom the encoder, let the model decide what to focus on for the current\ndecoding step using an attention mechanisms that filters the input features\ni.e if for the current decoding context, certain inputs are not relevant, then\nwhy bother including them? let the model learn the relevance of each input for\neach context and thus only look at relevant ones.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Instead of allowing the decoder to directly look at input features\nfrom the encoder, let the model decide what to focus on for the current\ndecoding step using an attention mechanisms that filters the input features\ni.e if for the current decoding context, certain inputs are not relevant, then\nwhy bother including them? let the model learn the relevance of each input for\neach context and thus only look at relevant ones.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1629635655,
			"isDeleted": false,
			"id": "SHsFwbC4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -166.76612428022662,
			"y": 528.0058463454773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 367.1595458984375,
			"height": 25,
			"seed": 1236253514,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Context = What matters x features",
			"rawText": "Context = What matters x features",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Context = What matters x features",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 178,
			"versionNonce": 1816676265,
			"isDeleted": false,
			"id": "Wbl9dchup2-9cFgcR8aZU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -84.79505338925759,
			"y": 559.1667891819233,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 283.6619376802627,
			"height": 280.5447735299302,
			"seed": 1140212682,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "366fd12db3fa947a4548e82b1d9db616989f5240",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 539,
			"versionNonce": 285221735,
			"isDeleted": false,
			"id": "5AiqhMRi",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -410.07142242686405,
			"y": 845.3245134025151,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 785.265625,
			"height": 80,
			"seed": 1884716618,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that theres a big difference between interpretability and explainability, transformers show us\ntheir interpretation of attention, this however is not sufficient to explain why they make their\ndecision because attention only contributes to a part of their decision, there are other things\nnot showed in their interpretation that also contribute and explain the decision.",
			"rawText": "Note that theres a big difference between interpretability and explainability, transformers show us\ntheir interpretation of attention, this however is not sufficient to explain why they make their\ndecision because attention only contributes to a part of their decision, there are other things\nnot showed in their interpretation that also contribute and explain the decision.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that theres a big difference between interpretability and explainability, transformers show us\ntheir interpretation of attention, this however is not sufficient to explain why they make their\ndecision because attention only contributes to a part of their decision, there are other things\nnot showed in their interpretation that also contribute and explain the decision.",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 725,
			"versionNonce": 420702857,
			"isDeleted": false,
			"id": "iU6GZdebdMVA3otK7PJ9m",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948966,
			"x": -57.6747334786819,
			"y": 1036.9217743213444,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 1285412746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 1142234759,
			"isDeleted": false,
			"id": "HMztEBFz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -44.49870614915608,
			"y": 1247.9875026203365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 196.25283813476562,
			"height": 35,
			"seed": 383930890,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Self Attention",
			"rawText": "Self Attention",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Self Attention",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 65,
			"versionNonce": 171389289,
			"isDeleted": false,
			"id": "hKK--Ejt1shdLpSI8Lb80",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 181.85120008867693,
			"y": 1249.0259580628144,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 86.59666664707117,
			"height": 29.213333326722932,
			"seed": 1537227210,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					33.386666659111825,
					-28.16999999362588
				],
				[
					86.59666664707117,
					-29.213333326722932
				]
			]
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 1025357223,
			"isDeleted": false,
			"id": "x8nOBBbs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 268.1714429675193,
			"y": 1204.5559580762713,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 164.52835083007812,
			"height": 40,
			"seed": 629277962,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": "[[CNN]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "also briefly explained\nbefore in this note",
			"rawText": "also briefly explained\nbefore in this note",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "also briefly explained\nbefore in this note",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 364,
			"versionNonce": 1962875977,
			"isDeleted": false,
			"id": "zR8UsmZbHtggocKxo2LXP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8.775346608990674,
			"y": -73.91287997134293,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"width": 34.15569151450337,
			"height": 34.15569151450338,
			"seed": 877119574,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.4231538131043082,
					-9.524183210774986
				],
				[
					13.355751169132722,
					8.101029397670677
				],
				[
					12.589437577461172,
					17.18731912749049
				],
				[
					8.538922878625849,
					20.252573494176676
				],
				[
					-14.559958241759444,
					24.631508303728396
				],
				[
					-20.799940345370644,
					12.479964207222395
				],
				[
					-18.06310608940082,
					8.538922878625849
				],
				[
					-14.231538131043067,
					11.823123985789637
				],
				[
					0.21894674047758586,
					-0.8757869619103434
				]
			]
		},
		{
			"type": "line",
			"version": 572,
			"versionNonce": 860252359,
			"isDeleted": false,
			"id": "f81vQLPTcOsacPcveVZs_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 110.08319543043349,
			"y": -68.3906141245408,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"width": 33.51461121437571,
			"height": 33.96751136592133,
			"seed": 1457170326,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.715191167982162,
					-4.868676629115403
				],
				[
					-7.432495061256052,
					-0.9058003030912426
				],
				[
					-11.205915630816817,
					7.13317738684347
				],
				[
					-28.24348123277302,
					6.453827159525042
				],
				[
					-24.584406741077718,
					-7.133177386843486
				],
				[
					-21.95444695017173,
					-18.908581327029545
				],
				[
					-26.41394398692536,
					-20.833406971098437
				],
				[
					-33.288161138602916,
					0.5661251894320206
				],
				[
					-33.51461121437571,
					13.134104394822899
				],
				[
					-10.403251005800326,
					13.020879356936508
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 886,
			"versionNonce": 1497803561,
			"isDeleted": false,
			"id": "bkv2kniwsd9OLrTvkY2Ad",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 71.971998634576,
			"y": -31.09948504896265,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"width": 124.98318935398952,
			"height": 105.17951498451934,
			"seed": 479839882,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.601224789823366,
					0
				],
				[
					27.72514411725824,
					-4.18077570022149
				],
				[
					39.38730791261289,
					-1.3202449579646796
				],
				[
					39.607348738940324,
					15.842939495576124
				],
				[
					39.38730791261289,
					58.53085980310071
				],
				[
					23.7644092433642,
					80.31490160951789
				],
				[
					10.121878011062533,
					87.79628970465106
				],
				[
					-7.921469747788078,
					99.23841267367827
				],
				[
					-14.962776190266347,
					94.83759614712936
				],
				[
					-25.74477668031122,
					95.71775945243914
				],
				[
					-31.68587899115228,
					100.99873928429786
				],
				[
					-47.5288184867284,
					91.53698375221767
				],
				[
					-66.67237037721625,
					83.83555483075702
				],
				[
					-82.51530987279237,
					56.55049236615369
				],
				[
					-82.29526904646494,
					21.784041806417182
				],
				[
					-85.37584061504919,
					6.38118396349593
				],
				[
					-77.01428921460622,
					-1.9803674369470194
				],
				[
					-61.1713497190301,
					-2.200408263274471
				],
				[
					-48.629022618365646,
					0.8801633053097758
				],
				[
					-44.888328570799075,
					-1.9803674369470194
				],
				[
					-41.36767534955991,
					6.821265616150818
				],
				[
					-20.46379684845253,
					13.862572058629103
				],
				[
					-2.640489915929359,
					5.501020658186154
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 537,
			"versionNonce": 1143715815,
			"isDeleted": false,
			"id": "peFozQzyOwfk_HNJAjqwl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 32.46420582543546,
			"y": 50.88238706588092,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 71.32837473357085,
			"height": 45.91844738725358,
			"seed": 1788900182,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.673830207988814,
					7.094142152525128
				],
				[
					-17.283909971606672,
					1.1608596249586571
				],
				[
					-3.740547680422343,
					-8.899923791349716
				],
				[
					-2.57968805546367,
					-18.18680079101898
				],
				[
					-11.60859624958657,
					-29.79539704060556
				],
				[
					-3.0956256665564137,
					-38.30836762363572
				],
				[
					16.896956763287147,
					-28.247584207327346
				],
				[
					40.243133665233486,
					-38.82430523472845
				],
				[
					47.72422902607816,
					-31.730163082203315
				],
				[
					39.08227404027483,
					-19.863598027070374
				],
				[
					40.50110247077985,
					-12.2535182634525
				],
				[
					54.044464761964186,
					-0.5159376110927435
				],
				[
					48.36915103994407,
					5.030391708154186
				],
				[
					39.598211651367556,
					-1.418828430505029
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 792,
			"versionNonce": 796483081,
			"isDeleted": false,
			"id": "dCY4_wSNp0ufkz-pfmdru",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 114.43992596905208,
			"y": -55.54305092036053,
			"strokeColor": "transparent",
			"backgroundColor": "#ffd534",
			"width": 42.008853798714284,
			"height": 67.25607017150766,
			"seed": 1722535434,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.190409356480215,
					-11.523625730320616
				],
				[
					-13.09502923900071,
					-0.9428421052080366
				],
				[
					-37.81844444223406,
					-0.3142807017360122
				],
				[
					-36.66608186920199,
					-16.971157893744913
				],
				[
					-29.123345027537585,
					-30.79950877012967
				],
				[
					-34.15183625531386,
					-34.36135672313786
				],
				[
					-40.75173099177021,
					-36.14228069964196
				],
				[
					-39.18032748309013,
					-7.228456139928375
				],
				[
					-42.008853798714284,
					23.990093565849318
				],
				[
					-33.83755555357783,
					24.409134501497352
				],
				[
					-18.333040934600987,
					20.847286548489148
				],
				[
					-7.228456139928391,
					21.89488888760921
				],
				[
					-0.7333216373840338,
					31.113789471865697
				],
				[
					-0.6285614034720244,
					16.552116958096907
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 970,
			"versionNonce": 635052807,
			"isDeleted": false,
			"id": "5PcR2FdKWmdy7grFcuMIn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -12.855924943713816,
			"y": -25.47851521877581,
			"strokeColor": "transparent",
			"backgroundColor": "#ffd534",
			"width": 41.89152109485021,
			"height": 64.15628419563961,
			"seed": 1971513366,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.1656061280743164,
					-24.586207594710565
				],
				[
					0.738641429884023,
					-35.982389655778135
				],
				[
					4.115287966496627,
					-32.2891825063581
				],
				[
					5.698091030533785,
					-24.69172779897971
				],
				[
					30.706379442320948,
					-28.17389453986147
				],
				[
					34.505106796010125,
					-32.81678352770382
				],
				[
					33.97750577466441,
					-41.04735946069705
				],
				[
					24.586207594710586,
					-58.24715275656755
				],
				[
					36.087909860047304,
					-64.15628419563961
				],
				[
					38.725914966775896,
					-5.276010213457225
				],
				[
					29.12357637828379,
					-6.331212256148663
				],
				[
					13.612106350719593,
					-8.019535524454964
				],
				[
					5.592570826264641,
					-6.225692051879504
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 273,
			"versionNonce": 1452455145,
			"isDeleted": false,
			"id": "s70fVP9XqApVOYrWD6HRx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 32.141349740846394,
			"y": 28.495357078355333,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 38.749736269112525,
			"height": 35.857964905745916,
			"seed": 1434494102,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 463,
			"versionNonce": 416164391,
			"isDeleted": false,
			"id": "Wnwn3Ukc4dnJsGNDLmawZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 29.636181181014834,
			"y": -25.52641101107561,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 47.03394518859826,
			"height": 30.430592965129396,
			"seed": 1872258378,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.9109784896294535,
					1.0946256462276778
				],
				[
					-17.29508521039731,
					-1.7514010339642747
				],
				[
					-26.052090380218715,
					-3.2838769386830173
				],
				[
					-36.56049658400441,
					-1.0946256462276778
				],
				[
					-40.28222378117851,
					2.1892512924553555
				],
				[
					-35.68479606702227,
					19.046486244361585
				],
				[
					-28.460266801919605,
					26.0520903802187
				],
				[
					-13.135507754732132,
					27.146716026446377
				],
				[
					-0.21892512924554822,
					24.73853960474549
				],
				[
					6.751721407419751,
					24.00406011275116
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 475,
			"versionNonce": 1109274569,
			"isDeleted": false,
			"id": "MWx5TXnN_DC3bNtGX-OsT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 36.04063329370409,
			"y": 33.35435264643703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 30.533364496059377,
			"height": 26.543208908506184,
			"seed": 27023190,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 441,
			"versionNonce": 435440967,
			"isDeleted": false,
			"id": "jLpeQP3td2Dd4iBNy_yyC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 38.295938625799394,
			"y": 36.997538182898666,
			"strokeColor": "#e9ecef",
			"backgroundColor": "#e9ecef",
			"width": 1.0409101532747496,
			"height": 19.95077793776609,
			"seed": 1112284810,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 475,
			"versionNonce": 1748455081,
			"isDeleted": false,
			"id": "3kDkd5VpxM5kzRJgxTrCA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 63.36452481716633,
			"y": 37.43125074676316,
			"strokeColor": "#e9ecef",
			"backgroundColor": "#e9ecef",
			"width": 0.8674251277289657,
			"height": 19.95077793776609,
			"seed": 607551382,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 514,
			"versionNonce": 1420364903,
			"isDeleted": false,
			"id": "YJJSw73T0Lt7bXZ8MiLB8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 58.50694410188416,
			"y": 34.48200531248467,
			"strokeColor": "#e9ecef",
			"backgroundColor": "#e9ecef",
			"width": 1.0409101532747493,
			"height": 24.461388601956685,
			"seed": 1530544278,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 546,
			"versionNonce": 1871286665,
			"isDeleted": false,
			"id": "HH1GfzQKyFfJqTSrjNfj2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 43.15351934108156,
			"y": 34.135035261393085,
			"strokeColor": "#e9ecef",
			"backgroundColor": "#e9ecef",
			"width": 1.0409101532747493,
			"height": 24.461388601956685,
			"seed": 961077386,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 569,
			"versionNonce": 1421404039,
			"isDeleted": false,
			"id": "JL-s1Z3N0aEDdtLba70GM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 48.18458508190952,
			"y": 33.441095159209915,
			"strokeColor": "#e9ecef",
			"backgroundColor": "#e9ecef",
			"width": 0.8674251277289656,
			"height": 26.71669393405198,
			"seed": 568632202,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 558,
			"versionNonce": 491812969,
			"isDeleted": false,
			"id": "GIxGj92G9vM1O2gn6n4ny",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 53.90959092492065,
			"y": 32.400185005935185,
			"strokeColor": "#e9ecef",
			"backgroundColor": "#e9ecef",
			"width": 1.0409101532747493,
			"height": 28.451544189509903,
			"seed": 571795594,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 665,
			"versionNonce": 2019581607,
			"isDeleted": false,
			"id": "WnghBNAKgY8CTQLq5P2DA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -20.77056868416588,
			"y": -31.628276146487977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 31.491319080416574,
			"height": 60.92885648167555,
			"seed": 1448678486,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.409898217542235,
					6.389543001823667
				],
				[
					-21.450608648979404,
					16.658451397611678
				],
				[
					-20.99421272027772,
					37.42446615353854
				],
				[
					-19.625024934172654,
					51.344541978940065
				],
				[
					-14.37647175410321,
					60.92885648167555
				],
				[
					8.671522645332102,
					60.7006585173247
				],
				[
					10.040710431437168,
					39.47824783269615
				],
				[
					8.44332468098126,
					16.430253433260834
				],
				[
					7.074136894876193,
					7.074136894876193
				],
				[
					1.8255837148067506,
					5.933147073121967
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 307,
			"versionNonce": 56066889,
			"isDeleted": false,
			"id": "I-7Q1c3--MxOLUU6yiMrD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -37.88541601047923,
			"y": -13.600636962771233,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 27.155557757750515,
			"height": 44.04220711971305,
			"seed": 856408010,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 241,
			"versionNonce": 575402439,
			"isDeleted": false,
			"id": "AO4B6DsNV8xH4MgP5dT0V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -35.6034363669708,
			"y": -6.526500067895057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.8255837148067666,
			"height": 28.98114147255728,
			"seed": 1518753430,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8255837148067666,
					28.98114147255728
				]
			]
		},
		{
			"type": "line",
			"version": 283,
			"versionNonce": 1845113385,
			"isDeleted": false,
			"id": "Q3NQDDjWGpNi9Bf4Gxz6W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -30.97645768859134,
			"y": -8.76250062230676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.2819796435084503,
			"height": 35.1424865100301,
			"seed": 344032150,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.2819796435084503,
					35.1424865100301
				]
			]
		},
		{
			"type": "line",
			"version": 273,
			"versionNonce": 731390183,
			"isDeleted": false,
			"id": "QVxZ26moXeLco0-at294P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.043310615469366,
			"y": -8.762500622306732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.510177607859292,
			"height": 35.370684474380944,
			"seed": 1167587286,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.510177607859292,
					35.370684474380944
				]
			]
		},
		{
			"type": "line",
			"version": 273,
			"versionNonce": 304350473,
			"isDeleted": false,
			"id": "kapBkjlcZWrYrumQVu9b4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -19.110163542347394,
			"y": -8.762500622306732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.8255837148067666,
			"height": 35.370684474380944,
			"seed": 293307594,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8255837148067666,
					35.370684474380944
				]
			]
		},
		{
			"type": "line",
			"version": 289,
			"versionNonce": 366046215,
			"isDeleted": false,
			"id": "idw4zj9wnJqqPjZnu0Bzr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -14.089808326628813,
			"y": -0.7755718700271643,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.22819796435084186,
			"height": 23.960786256838695,
			"seed": 1819138314,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.22819796435084186,
					23.960786256838695
				]
			]
		},
		{
			"type": "line",
			"version": 770,
			"versionNonce": 2068872169,
			"isDeleted": false,
			"id": "yOIN70BSQQSCELkLTtS8u",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 122.11169543075836,
			"y": -32.78608704570681,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 32.18525918259974,
			"height": 58.55580165631003,
			"seed": 77893514,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.64720370007878,
					4.016488176458147
				],
				[
					21.68791413151595,
					14.285396572246157
				],
				[
					21.231518202814264,
					35.05141132817302
				],
				[
					19.8623304167092,
					48.97148715357455
				],
				[
					14.613777236639756,
					58.55580165631003
				],
				[
					-8.434217162795557,
					58.327603691959176
				],
				[
					-10.49734505108379,
					37.10519300733063
				],
				[
					-9.940869453902616,
					14.577653684532699
				],
				[
					-8.051226591160182,
					5.568507197239622
				],
				[
					-1.5882782322702065,
					3.560092247756447
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 351,
			"versionNonce": 2096386855,
			"isDeleted": false,
			"id": "1XKDdX2fONr_FSuBsAiiw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 112.30829048185772,
			"y": -17.13150268735555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 27.155557757750515,
			"height": 44.04220711971305,
			"seed": 946921226,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 298,
			"versionNonce": 965416649,
			"isDeleted": false,
			"id": "hnKB56x4dT1U7MHVEqnOL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 135.95696243737007,
			"y": -8.396227414723498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.31016562802219383,
			"height": 27.082697612264848,
			"seed": 1104440778,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.31016562802219383,
					27.082697612264848
				]
			]
		},
		{
			"type": "line",
			"version": 372,
			"versionNonce": 1231902279,
			"isDeleted": false,
			"id": "NaoKAb0Dr5EqJmBI1Kb3d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 130.84509410936482,
			"y": -11.818755381817994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.09107518185705421,
			"height": 30.39637685929905,
			"seed": 1566057610,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.09107518185705421,
					30.39637685929905
				]
			]
		},
		{
			"type": "line",
			"version": 326,
			"versionNonce": 1332696489,
			"isDeleted": false,
			"id": "Be6XRR6qfk6v8ED9HUdyu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 126.2274301204525,
			"y": -12.530671829427632,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6117337475668758,
			"height": 35.1333789918444,
			"seed": 615973706,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6117337475668758,
					35.1333789918444
				]
			]
		},
		{
			"type": "line",
			"version": 325,
			"versionNonce": 572061031,
			"isDeleted": false,
			"id": "2_KzbDxsy_1cjjcRmiW6R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 120.30059502676166,
			"y": -12.293366346891062,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5474711105587696,
			"height": 35.370684474380944,
			"seed": 1112279562,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5474711105587696,
					35.370684474380944
				]
			]
		},
		{
			"type": "line",
			"version": 343,
			"versionNonce": 1613281417,
			"isDeleted": false,
			"id": "QbE28zuNi-J3NKOnsNwu_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 115.43381967349912,
			"y": -4.306437594611495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.48371848325882216,
			"height": 23.723480774302136,
			"seed": 1561475274,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.48371848325882216,
					23.723480774302136
				]
			]
		},
		{
			"type": "line",
			"version": 470,
			"versionNonce": 507752583,
			"isDeleted": false,
			"id": "kXa7_kvRNOSeUpooa5hiP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 15.536883597210746,
			"y": -26.621036657303293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 35.9037211962678,
			"height": 23.862839087763344,
			"seed": 2064458186,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.597427714156259,
					-0.43785025849106474
				],
				[
					-15.105833917941956,
					4.159577455665178
				],
				[
					-19.703261632098183,
					8.100229782084808
				],
				[
					-12.040882108504471,
					23.42498882927228
				],
				[
					7.443454394348196,
					22.768213441535682
				],
				[
					16.200459564169616,
					18.827561115116055
				],
				[
					14.230133400959778,
					3.064951809437501
				],
				[
					9.63270568680355,
					1.970326163209823
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 382,
			"versionNonce": 494059369,
			"isDeleted": false,
			"id": "EjvFJOyMzTioduSpaepxo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 25.82636467175088,
			"y": -24.43178536484794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 29.55489244814728,
			"height": 24.957464733991024,
			"seed": 1952678038,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.224529265102648,
					-0.8757005169821295
				],
				[
					-13.354432883977633,
					-2.62710155094642
				],
				[
					-21.23573753681691,
					1.31355077547321
				],
				[
					-25.39531499248209,
					11.603031850013375
				],
				[
					-21.016812407571376,
					22.330363183044604
				],
				[
					-4.378502584910679,
					21.235737536816924
				],
				[
					4.159577455665194,
					16.200459564169616
				],
				[
					3.5028020679285814,
					5.473128231138388
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 503,
			"versionNonce": 933889959,
			"isDeleted": false,
			"id": "L9uMwnilFOjgRG8R9kNgx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -13.451916005388824,
			"y": -25.40183468942135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 8.009547239895898,
			"height": 23.11171489243547,
			"seed": 1607421462,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.799090139221503,
					-0.9993607400285535
				],
				[
					-8.009547239895898,
					-17.857511790542596
				],
				[
					-2.536419008757525,
					-23.11171489243547
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 706,
			"versionNonce": 1972955721,
			"isDeleted": false,
			"id": "MlOuEBMSH8J1bUf33FBt3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 47.93780272554994,
			"y": -100.39880521304866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 50.57170485571866,
			"height": 83.19154911330344,
			"seed": 1406899094,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-21.89251292455349,
					7.443454394348227
				],
				[
					-23.86283908776333,
					21.454662666062458
				],
				[
					-23.20606370002675,
					35.24694580853119
				],
				[
					-22.549288312290134,
					58.67193463780345
				],
				[
					-17.951860598133877,
					74.65346907272753
				],
				[
					-8.975930299066938,
					80.78337269160254
				],
				[
					2.4081764217009036,
					83.19154911330344
				],
				[
					14.23013340095981,
					79.90767217462037
				],
				[
					23.424988829272266,
					69.18034084158919
				],
				[
					26.489940638709783,
					45.09857662458027
				],
				[
					26.70886576795533,
					24.30068934625441
				],
				[
					23.20606370002675,
					5.25420310189284
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 708,
			"versionNonce": 2088270535,
			"isDeleted": false,
			"id": "SJZ1sDsHNGvdWmF9XUOKe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 26.800943622126,
			"y": -93.6121262064371,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 44.22287610759814,
			"height": 80.78337269160255,
			"seed": 13794966,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.313550775473194,
					43.347175590616
				],
				[
					7.005604135857099,
					67.21001467837934
				],
				[
					24.73853960474549,
					73.99669368499094
				],
				[
					39.943251956080374,
					64.90795919472062
				],
				[
					43.56610071986153,
					48.16352843401777
				],
				[
					44.22287610759814,
					31.963068869848154
				],
				[
					44.22287610759814,
					15.324759047187456
				],
				[
					43.34717559061598,
					-0.43785025849109643
				],
				[
					32.181993999093685,
					-5.035277972647323
				],
				[
					20.141111890589233,
					-6.786679006611615
				],
				[
					9.413780557558002,
					-4.159577455665162
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 634,
			"versionNonce": 24557865,
			"isDeleted": false,
			"id": "hEgFZCkSZxheasjvqI5_y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 45.74855143309459,
			"y": -99.74202982531207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.32486266167575,
			"height": 65.66919590159098,
			"seed": 1451468042,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0946256462276778,
					41.81469968589725
				],
				[
					-10.581054873971325,
					42.06119137874941
				],
				[
					-5.09041109986053,
					48.36947397126372
				],
				[
					-4.837521105861387,
					60.30328897591517
				],
				[
					4.231497095974797,
					65.45027077234548
				],
				[
					13.731880880245898,
					60.507458537896085
				],
				[
					13.683624267649703,
					47.67215242792092
				],
				[
					19.743807787704423,
					42.03362481514279
				],
				[
					6.567753877366066,
					41.81469968589725
				],
				[
					5.473128231138388,
					-0.21892512924551652
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 570,
			"versionNonce": 21727719,
			"isDeleted": false,
			"id": "TjRn0a6rGOzkxqn1m8W7y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 16.50697959740441,
			"y": -60.82051706134419,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 46.51082784552843,
			"height": 56.65864483000735,
			"seed": 474900106,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.748367099963057,
					3.382605661492966
				],
				[
					-20.295633968957876,
					4.016844223022908
				],
				[
					-24.101065338137474,
					-9.090752715262372
				],
				[
					-33.826056614929776,
					-23.88965248429415
				],
				[
					-39.745616522542484,
					-24.101065338137474
				],
				[
					-46.51082784552843,
					-34.883120884146344
				],
				[
					-44.39669930709533,
					-41.225506499445665
				],
				[
					-21.35269823817442,
					-52.64180060698444
				],
				[
					-11.839119815225429,
					-37.42007513026605
				],
				[
					-17.758679722838142,
					-30.866276661123408
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 208,
			"versionNonce": 846703625,
			"isDeleted": false,
			"id": "4nTIlZ6CaCY1iI9iK1_66",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 9.953181128261747,
			"y": -71.60257260735304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.335854015151494,
			"height": 1.4798899769031746,
			"seed": 938679126,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.335854015151494,
					1.4798899769031746
				]
			]
		},
		{
			"type": "line",
			"version": 208,
			"versionNonce": 321893639,
			"isDeleted": false,
			"id": "O0ZJApIMB5_v8SVHvkODS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1.2852541206860053,
			"y": -86.61288523022813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.587486915188455,
			"height": 7.822275592202522,
			"seed": 465408970,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-14.587486915188455,
					7.822275592202522
				]
			]
		},
		{
			"type": "line",
			"version": 390,
			"versionNonce": 1083654889,
			"isDeleted": false,
			"id": "_eDyEoO6wUKBuU5U81kgp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8.896116859045193,
			"y": -74.35093970731609,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.32932241500369,
			"height": 28.11790956116038,
			"seed": 955580746,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6342385615299411,
					-8.456514153732448
				],
				[
					6.130972761456023,
					1.2684771230598664
				],
				[
					9.302165569105696,
					15.433138330561704
				],
				[
					4.651082784552848,
					19.027156845897995
				],
				[
					-14.376074061345147,
					19.661395407427936
				],
				[
					-19.027156845897995,
					8.667927007575756
				],
				[
					-14.164661207501837,
					12.896184084441972
				]
			]
		},
		{
			"type": "line",
			"version": 394,
			"versionNonce": 698448935,
			"isDeleted": false,
			"id": "fHbmSkvLBjL_OMafPy9TP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -10.131039986852798,
			"y": -65.47159984589703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.44889979501102,
			"height": 32.98040519955652,
			"seed": 13824278,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.1597974262009827,
					3.284852440347324
				],
				[
					1.057064269216558,
					6.765211322985964
				],
				[
					3.382605661492982,
					14.79889976903178
				],
				[
					27.69508385347375,
					11.839119815225413
				],
				[
					31.289102368810042,
					7.610862738359198
				],
				[
					31.077689514966732,
					-1.057064269216558
				],
				[
					21.35269823817442,
					-18.181505430524744
				],
				[
					19.66139540742795,
					-17.33585401515151
				]
			]
		},
		{
			"type": "line",
			"version": 213,
			"versionNonce": 1482751433,
			"isDeleted": false,
			"id": "7NynznU3OZQvVj_mMal4P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 23.42763997503141,
			"y": -90.20448499241022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.431797144755643,
			"height": 6.567741887795428,
			"seed": 372098954,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.431797144755643,
					6.567741887795428
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 411918151,
			"isDeleted": false,
			"id": "7-MBKrnf9KOGc7m0yWdY2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -12.460378197565078,
			"y": -62.057019759001236,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.456681995289757,
			"height": 12.900921565312457,
			"seed": 1177275094,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.456681995289757,
					12.900921565312457
				]
			]
		},
		{
			"type": "line",
			"version": 283,
			"versionNonce": 149970089,
			"isDeleted": false,
			"id": "jPEEe1vV8GP3mdKX0m1jU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 26.242386498372312,
			"y": -34.37867894614904,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.40645132677262,
			"height": 9.851612831693142,
			"seed": 1895872650,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.5801843130624853,
					4.222119785011342
				],
				[
					-17.59216577088063,
					0.938248841113628
				],
				[
					-32.60414722869877,
					3.049308733619299
				],
				[
					-39.40645132677262,
					9.851612831693142
				]
			]
		},
		{
			"type": "line",
			"version": 400,
			"versionNonce": 38788711,
			"isDeleted": false,
			"id": "rrHc-bNZF3-IjjhAR34xL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 36.797685960900694,
			"y": -2.9473427688423186,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.54285703726133,
			"height": 42.2211978501135,
			"seed": 483749002,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.3331796775170295,
					-20.64147450449993
				],
				[
					1.876497682227256,
					-16.419354719488588
				],
				[
					7.271428518630657,
					-1.876497682227272
				],
				[
					2.5801843130624853,
					8.4442395700227
				],
				[
					6.3331796775170295,
					16.653916929767
				],
				[
					1.4073732616704262,
					21.579723345613573
				],
				[
					-7.271428518630673,
					14.54285703726133
				],
				[
					-1.1728110513920589,
					5.394930836403385
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 429,
			"versionNonce": 1911611273,
			"isDeleted": false,
			"id": "vlflFSZ0guirpKszCUyhh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 20.61289345169051,
			"y": 21.447127100112155,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 29.78940070535786,
			"height": 44.80138216317599,
			"seed": 1209128470,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3331796775170295,
					-7.036866308352258
				],
				[
					5.864055256960215,
					-14.0737326167045
				],
				[
					-8.913363990579514,
					-10.086175041971558
				],
				[
					-20.876036714778344,
					-10.320737252249973
				],
				[
					-18.999539032551088,
					13.370045985869288
				],
				[
					-5.864055256960215,
					30.727649546471486
				],
				[
					8.678801780301114,
					20.876036714778344
				],
				[
					8.913363990579514,
					11.493548303642015
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 975,
			"versionNonce": 162888071,
			"isDeleted": false,
			"id": "eSHywRLGgfmV0oYlfjRVG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 62.2601376696704,
			"y": 5.8611920101604085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.752534397005633,
			"height": 28.691301015340223,
			"seed": 614038026,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.878202066407657,
					-0.019636175638371445
				],
				[
					-6.956940883900248,
					-13.028047532475254
				],
				[
					-9.865834596346549,
					-13.018458411161893
				],
				[
					-9.851612831693174,
					-8.885853171915914
				],
				[
					-14.777419247539745,
					-8.913363990579514
				],
				[
					-14.829833853328145,
					-13.210195136965266
				],
				[
					-17.631545218975056,
					-13.185291349840494
				],
				[
					-17.780440070395137,
					-8.72046073651299
				],
				[
					-18.272389117866695,
					-0.12973299870160104
				],
				[
					-22.60258380292806,
					-0.019636175638371445
				],
				[
					-18.924827671176676,
					7.8126572690230995
				],
				[
					-22.752534397005633,
					12.197234934477244
				],
				[
					-12.19723493447726,
					15.481105878374958
				],
				[
					-1.17541808293084,
					11.670481845054434
				],
				[
					-5.527270866643815,
					7.249131763044659
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 214,
			"versionNonce": 832439913,
			"isDeleted": false,
			"id": "kA18RXQNM4y53MDM29nH5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 44.203452413663584,
			"y": 5.559571528852956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.084685042111488,
			"height": 0,
			"seed": 721400022,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.084685042111488,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 243,
			"versionNonce": 1140502695,
			"isDeleted": false,
			"id": "PHqOUY3SQ0u2uMt4nbMiV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 45.2937493030516,
			"y": 19.915147239128494,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.902968893880145,
			"height": 9.085807411566787,
			"seed": 974144266,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.725742223470036,
					-7.26864592925343
				],
				[
					7.995510522178767,
					-7.26864592925343
				],
				[
					10.902968893880145,
					-0.1817161482313421
				],
				[
					4.542903705783393,
					1.8171614823133575
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 248,
			"versionNonce": 314790217,
			"isDeleted": false,
			"id": "kLa_ET_BqIkxy9o6avR8v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 45.05792849721725,
			"y": 37.5562406835707,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 12.723793998813065,
			"height": 26.20330731597833,
			"seed": 1434808086,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 463,
			"versionNonce": 1791755207,
			"isDeleted": false,
			"id": "A6fxtXw1mw0-uI4-zbwkb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 67.09445286640087,
			"y": -19.211610093937935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.175017529033422,
			"height": 36.952310441253694,
			"seed": 1892561994,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.89849086855693,
					-0.5204550766373668
				],
				[
					-10.929556609384925,
					14.57274214584654
				],
				[
					-4.510610664190597,
					25.502298755231433
				],
				[
					-10.235616507201728,
					32.26821475151731
				],
				[
					-5.3780357919195625,
					36.431855364616325
				],
				[
					6.245460919648497,
					30.186394444967814
				],
				[
					-0.1734850255457995,
					24.287903576410887
				],
				[
					-2.428790357641098,
					14.39925712030074
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 426,
			"versionNonce": 2059157545,
			"isDeleted": false,
			"id": "xWE-oiHWUYAu88sUvkEsF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -0.9116771475496108,
			"y": 11.842209478758846,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 37.993220594528445,
			"height": 14.919712196938123,
			"seed": 330144342,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.2143951788205332,
					-11.970466762659658
				],
				[
					13.531831992571774,
					-9.541676405018562
				],
				[
					32.9621548537005,
					-12.83789189038861
				],
				[
					36.778825415707914,
					-9.541676405018562
				],
				[
					28.104574138418332,
					2.0818203065495147
				],
				[
					27.58411906178093,
					-4.857580715282181
				],
				[
					12.317436813751241,
					-0.6939401021831664
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 613,
			"versionNonce": 1313207015,
			"isDeleted": false,
			"id": "5C_i0PNHcAK4HON7-xDuq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 25.1110766843192,
			"y": 60.4180166315806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.76744849977352,
			"height": 19.60380788667449,
			"seed": 799735562,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.674251277289612,
					4.857580715282181
				],
				[
					14.57274214584654,
					9.194706353926978
				],
				[
					21.338658142132438,
					4.684095689736381
				],
				[
					19.950777937766087,
					4.857580715282181
				],
				[
					2.428790357641098,
					-6.071975894102714
				],
				[
					7.112886047377478,
					-10.409101532747512
				],
				[
					-2.4287903576410823,
					-2.2553053320952987
				]
			]
		},
		{
			"type": "line",
			"version": 576,
			"versionNonce": 393499401,
			"isDeleted": false,
			"id": "4at5jmr5d1tJ7rNACPmS_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 80.19646931433857,
			"y": 18.616375218951788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 29.789400705357856,
			"height": 44.280927086538604,
			"seed": 2007862486,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.3331796775170295,
					-7.036866308352258
				],
				[
					-5.864055256960215,
					-14.0737326167045
				],
				[
					8.913363990579514,
					-10.086175041971558
				],
				[
					20.876036714778344,
					-10.320737252249973
				],
				[
					17.091203751547358,
					12.502620858140338
				],
				[
					6.037540282506015,
					30.207194469834104
				],
				[
					-7.811376652572149,
					18.794216408228827
				],
				[
					-8.913363990579514,
					11.493548303642015
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 540,
			"versionNonce": 116719111,
			"isDeleted": false,
			"id": "QsqiMJCQFkw2HxVcoRcsU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 101.35774541169484,
			"y": 9.76038917220933,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 37.47276551789108,
			"height": 14.919712196938123,
			"seed": 624162646,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2143951788205332,
					-11.970466762659658
				],
				[
					-13.531831992571774,
					-9.541676405018562
				],
				[
					-32.9621548537005,
					-12.83789189038861
				],
				[
					-36.258370339070545,
					-11.450011686022277
				],
				[
					-33.74283746865658,
					-3.643185536461631
				],
				[
					-28.104574138418332,
					2.0818203065495147
				],
				[
					-27.58411906178093,
					-4.857580715282181
				],
				[
					-12.317436813751241,
					-0.6939401021831664
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 395,
			"versionNonce": 1298598377,
			"isDeleted": false,
			"id": "GKdGeS_Lz_oeMPeznIH5M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 15.22243022820905,
			"y": 52.09073540538259,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 37.81973556898266,
			"height": 85.00766251743808,
			"seed": 1185052298,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.021221328381195,
					8.327281226198012
				],
				[
					-8.327281226198012,
					0.6939401021831664
				],
				[
					-21.685628193224005,
					-18.042442656762372
				],
				[
					-25.50229875523142,
					-27.757604087326733
				],
				[
					-26.369723882960383,
					-63.322034324214094
				],
				[
					-28.798514240601467,
					-76.68038129124007
				]
			]
		},
		{
			"type": "line",
			"version": 720,
			"versionNonce": 1742054695,
			"isDeleted": false,
			"id": "tJzzsyzODRi7UqsCedffD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 80.53954234619972,
			"y": 56.34111853125449,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.07350839759032,
			"height": 19.60380788667449,
			"seed": 1809353354,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-10.409101532747496,
					7.633341124014861
				],
				[
					-16.307592401304426,
					11.970466762659658
				],
				[
					-23.07350839759032,
					7.459856098469062
				],
				[
					-21.685628193223973,
					7.633341124014861
				],
				[
					-4.163640613098982,
					-3.2962154853700323
				],
				[
					-8.847736302835363,
					-7.63334112401483
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 495,
			"versionNonce": 1704977609,
			"isDeleted": false,
			"id": "A3tjgQKKUK5REL5eNIHA-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 86.52477572752956,
			"y": 50.18240012437887,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.53336449605938,
			"height": 77.20083636787744,
			"seed": 1214294410,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.245460919648497,
					5.551520817465347
				],
				[
					-5.204550766373795,
					6.76591599628588
				],
				[
					9.368191379472762,
					-2.4287903576410823
				],
				[
					24.287903576410887,
					-23.940933525319302
				],
				[
					24.287903576410887,
					-70.43492037159156
				],
				[
					15.960622350212857,
					-52.04550766373761
				]
			]
		},
		{
			"type": "line",
			"version": 326,
			"versionNonce": 810838087,
			"isDeleted": false,
			"id": "_R7uxc167oPqFRbJGswb7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 114.10889478931053,
			"y": -27.191921269044386,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 7.63334112401483,
			"height": 27.410634036235148,
			"seed": 1793541834,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6939401021831664,
					-27.410634036235148
				],
				[
					5.204550766373764,
					-25.502298755231433
				],
				[
					6.939401021831664,
					-17.69547260567079
				],
				[
					6.939401021831664,
					-2.0818203065495147
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1032,
			"versionNonce": 2075812777,
			"isDeleted": false,
			"id": "KOGp302h5P-Sy7sFAK6Nc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 81.64940419051698,
			"y": -66.55556421267815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd534",
			"width": 46.684312871074205,
			"height": 56.311674778915766,
			"seed": 149874698,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0135168445051568,
					5.117455916950882
				],
				[
					17.17290350913361,
					5.578209452935024
				],
				[
					24.101065338137474,
					-9.090752715262372
				],
				[
					29.835901027376575,
					-19.205556794557754
				],
				[
					39.57213149699669,
					-19.06999959730951
				],
				[
					46.684312871074205,
					-31.066450322138916
				],
				[
					43.1823041282748,
					-36.714895835255064
				],
				[
					16.148147471800655,
					-50.733465325980745
				],
				[
					8.369419304309567,
					-36.379164976991284
				],
				[
					12.901099007555947,
					-28.26400127793654
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 523,
			"versionNonce": 2119026535,
			"isDeleted": false,
			"id": "t13OX4rDnXzObALPcL7fV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 86.64183742974755,
			"y": -75.42928447768321,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.856309091788862,
			"height": 1.4798899769031746,
			"seed": 1202280138,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.856309091788862,
					1.4798899769031746
				]
			]
		},
		{
			"type": "line",
			"version": 545,
			"versionNonce": 736233097,
			"isDeleted": false,
			"id": "Hp4vyDA6viD3AiRDr0orX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 93.22794413077376,
			"y": -89.57217197282938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.587486915188455,
			"height": 7.822275592202522,
			"seed": 178777482,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.828663589327602,
					3.5688270437614795
				],
				[
					14.587486915188455,
					7.822275592202522
				]
			]
		},
		{
			"type": "line",
			"version": 519,
			"versionNonce": 934535,
			"isDeleted": false,
			"id": "fdl8MswNDXA-lV9DPdVli",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 109.92282188330329,
			"y": -68.83297706360995,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.456681995289757,
			"height": 12.900921565312457,
			"seed": 1531435146,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.456681995289757,
					12.900921565312457
				]
			]
		},
		{
			"type": "line",
			"version": 420,
			"versionNonce": 13782377,
			"isDeleted": false,
			"id": "9STDpnltRPhNU3I2GfsD_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 73.16642876050358,
			"y": -92.24880584871642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.778825415707914,
			"height": 36.778825415707914,
			"seed": 1448771734,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.450011686022261,
					4.684095689736365
				],
				[
					5.204550766373764,
					16.481077426850256
				],
				[
					3.469700510915832,
					27.757604087326715
				],
				[
					3.643185536461663,
					35.04397516024999
				],
				[
					11.623496711568091,
					36.778825415707914
				],
				[
					27.23714901068935,
					35.04397516024999
				],
				[
					36.778825415707914,
					23.59396347422772
				]
			]
		},
		{
			"type": "line",
			"version": 481,
			"versionNonce": 1716672935,
			"isDeleted": false,
			"id": "FHKklt39asWcPTM9wJ5ES",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 109.94525417621152,
			"y": -68.82832740003448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 30.880334547151012,
			"height": 30.359879470513615,
			"seed": 374188374,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.2553053320953302,
					-3.9901555875531987
				],
				[
					-8.847736302835427,
					6.765915996285895
				],
				[
					-19.60380788667452,
					10.582586558293327
				],
				[
					-30.880334547151012,
					9.88864645611016
				],
				[
					-30.706849521605182,
					-3.6431855364616155
				],
				[
					-21.68562819322402,
					-18.042442656762358
				],
				[
					-26.19623885741465,
					-19.77729291222029
				]
			]
		},
		{
			"type": "line",
			"version": 209,
			"versionNonce": 567720009,
			"isDeleted": false,
			"id": "SsmFT_orkhPzGA1xcPzU7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 88.60659603407906,
			"y": -87.04425508234266,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.9083352810036995,
			"height": 9.021221328381195,
			"seed": 745493002,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.9083352810036995,
					9.021221328381195
				]
			]
		},
		{
			"type": "line",
			"version": 192,
			"versionNonce": 373722311,
			"isDeleted": false,
			"id": "SxPH2vemU1SI4sFpmA_NC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 107.51646381857041,
			"y": -72.47151293649611,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.337125638644798,
			"height": 3.296215485370048,
			"seed": 1082361226,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.337125638644798,
					3.296215485370048
				]
			]
		},
		{
			"type": "line",
			"version": 807,
			"versionNonce": 1087031081,
			"isDeleted": false,
			"id": "LYMUKBIW-qp6PxZL0QF38",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 68.00221248768116,
			"y": -26.246556543709644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 44.01973987671273,
			"height": 30.333712788394497,
			"seed": 510665674,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					13.622039185046606,
					-1.9999356717738133
				],
				[
					24.746940430593718,
					-4.528642877561677
				],
				[
					39.91379682479096,
					-2.6327858282870342
				],
				[
					40.78880777061003,
					6.992334575722767
				],
				[
					35.39290693805909,
					21.575850339373968
				],
				[
					31.309522524236762,
					23.90921286155816
				],
				[
					18.913534125133218,
					25.80506991083282
				],
				[
					1.0861341397269182,
					22.812334357009608
				],
				[
					-2.404259846262991,
					24.649383823320093
				],
				[
					-3.230932106102702,
					20.516022524121492
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 955,
			"versionNonce": 461855719,
			"isDeleted": false,
			"id": "vC1fWwcFcAqB6_hAKye2b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 66.95794045392444,
			"y": -13.001335694148821,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 34.9783896546248,
			"height": 22.246351129197873,
			"seed": 1991249366,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.304604415626772,
					-11.665923668571157
				],
				[
					6.89176855085103,
					-13.156350601344837
				],
				[
					25.64537730671393,
					-15.148830889665291
				],
				[
					34.9783896546248,
					-12.258742706693033
				],
				[
					33.61329990761909,
					2.1391248798911513
				],
				[
					29.80838775939723,
					7.070905269774592
				],
				[
					11.35353185833574,
					7.097520239532582
				],
				[
					2.735708851068575,
					6.359392676788508
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 443,
			"versionNonce": 1209661961,
			"isDeleted": false,
			"id": "z3yL0wqtXwOBz7kpLoryJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 74.51975821371086,
			"y": -5.545717150154729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 28.72952605439288,
			"height": 22.45861427602288,
			"seed": 1648124246,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.645878940912812,
					-7.000087566552596
				],
				[
					-1.895857049274675,
					-17.937724389291
				],
				[
					15.166856394197241,
					-22.45861427602288
				],
				[
					25.08364711348007,
					-14.291845448378204
				],
				[
					22.89611974893238,
					-4.083384413822346
				],
				[
					18.95857049274656,
					-1.5860309830791143e-14
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 390,
			"versionNonce": 1512130311,
			"isDeleted": false,
			"id": "ZtwwIQzqwE4Wk453kMluP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 72.08578088239187,
			"y": -31.360574874243625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.35111831681213,
			"height": 10.06262587691932,
			"seed": 563906518,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.350680484049219,
					0.6819206172545534
				],
				[
					16.871657937333662,
					-2.5264528507487083
				],
				[
					30.14265728225626,
					-3.4014637965677768
				],
				[
					37.87192063699142,
					-0.3389254862010371
				],
				[
					40.35111831681213,
					6.661162080351542
				]
			]
		},
		{
			"type": "line",
			"version": 380,
			"versionNonce": 1220530409,
			"isDeleted": false,
			"id": "HTohx_kbfVAXT6VLWAlIP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 61.863873343802766,
			"y": -54.29737380827416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.654342625556415,
			"height": 17.604988038779776,
			"seed": 1155821462,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.654342625556415,
					6.5061912317229655
				],
				[
					-7.42956097145355,
					17.604988038779776
				]
			]
		},
		{
			"type": "line",
			"version": 339,
			"versionNonce": 9489959,
			"isDeleted": false,
			"id": "qx5VgQvng4yK2-WTeaWXt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 37.944052638938985,
			"y": -54.393053091093606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.248405390162919,
			"height": 17.562718912114047,
			"seed": 1557592726,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.228418322473164,
					7.175946211459159
				],
				[
					8.248405390162919,
					17.562718912114047
				]
			]
		},
		{
			"type": "line",
			"version": 333,
			"versionNonce": 675793865,
			"isDeleted": false,
			"id": "sWJCvvcGL9lj2GuWOS_tv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 41.612162347759806,
			"y": -57.76566391397502,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.69863379230486,
			"height": 5.6254262775495025,
			"seed": 1737582026,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.69863379230486,
					-0.11843002689576981
				],
				[
					12.257507783713145,
					5.506996250653732
				],
				[
					4.381910995143825,
					5.447781237205856
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 308,
			"versionNonce": 969044295,
			"isDeleted": false,
			"id": "iEgKdUFBZaHzGv1F9uK4y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 47.65209371944452,
			"y": -35.73767891136008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.559556035487495,
			"height": 2.9607506723944677,
			"seed": 808451786,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.361945309301456,
					-2.9607506723944677
				],
				[
					3.3752557665297096,
					-2.9015356589465906
				],
				[
					4.559556035487495,
					-0.05921501344787698
				]
			]
		},
		{
			"type": "line",
			"version": 359,
			"versionNonce": 248343209,
			"isDeleted": false,
			"id": "mLO4LzSZaK3s_CmB9ojR_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 52.80379988941091,
			"y": -47.78691319949789,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.0791806992902573,
			"height": 0.8882252017183608,
			"seed": 1896710550,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.0791806992902573,
					-0.030628455231673277
				],
				[
					1.4478266864212463,
					0.8575967464866876
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 422,
			"versionNonce": 521318503,
			"isDeleted": false,
			"id": "Iaye2r6_u8hbvcAFLc5nk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 44.6437377481905,
			"y": -47.4612306255345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 2.8121299185216584,
			"height": 1.0178272149478453,
			"seed": 290099542,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.8121299185216584,
					0.022781700922053057
				],
				[
					1.3944165302675298,
					1.0178272149478453
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 408,
			"versionNonce": 352071049,
			"isDeleted": false,
			"id": "uixsN4voq_FdgXPst_AKc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 50.964607805771095,
			"y": -52.1693166133697,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.1898164023024567,
			"height": 10.414980449975047,
			"seed": 909302026,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.05341015615371575,
					10.414980449975047
				],
				[
					-1.97617577768757,
					10.308160137667599
				],
				[
					-2.136406246148741,
					0.05341015615368403
				]
			]
		},
		{
			"type": "line",
			"version": 305,
			"versionNonce": 1783499655,
			"isDeleted": false,
			"id": "f73mdaKebLlVPvgv5Pmwg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 62.39941678329612,
			"y": -97.01912896972578,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.845043236254657,
			"height": 38.56258902325127,
			"seed": 1151645770,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.955137335718078,
					14.634008142156883
				],
				[
					-4.845043236254657,
					38.56258902325127
				]
			]
		},
		{
			"type": "line",
			"version": 309,
			"versionNonce": 839881833,
			"isDeleted": false,
			"id": "oAtbHxGbtFFapHd_9liex",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 33.131400498982316,
			"y": -95.93146620240333,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.206909971615021,
			"height": 37.87043998950061,
			"seed": 473322966,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.427098170541886,
					10.67887080643879
				],
				[
					8.206909971615021,
					37.87043998950061
				]
			]
		},
		{
			"type": "line",
			"version": 277,
			"versionNonce": 1739653799,
			"isDeleted": false,
			"id": "1O7n3-sQ0XfhH5peE-pS8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 59.433063781507556,
			"y": -38.779731701277086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.537192270005331,
			"height": 11.469898273582457,
			"seed": 300835082,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2854196341083726,
					7.613639371257307
				],
				[
					5.537192270005331,
					11.469898273582457
				]
			]
		},
		{
			"type": "line",
			"version": 266,
			"versionNonce": 1775443785,
			"isDeleted": false,
			"id": "VvyMTt5MyZ7ccde_ZpoKw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 40.942796737025546,
			"y": -38.87861013467004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.0203687708995925,
			"height": 12.063168873940139,
			"seed": 3265238,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3842980675013328,
					7.514760937864346
				],
				[
					-7.0203687708995925,
					12.063168873940139
				]
			]
		},
		{
			"type": "ellipse",
			"version": 450,
			"versionNonce": 669521351,
			"isDeleted": false,
			"id": "JZKUksriQwcDhy-VQsa2E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3.9965036110308176,
			"y": -24.38239464901531,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 23.279592165469186,
			"height": 21.033532291408903,
			"seed": 1879367958,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 303,
			"versionNonce": 983715369,
			"isDeleted": false,
			"id": "PY8OwZNe8skNSjwb0VboM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6.345799076870179,
			"y": -22.183608121442333,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 18.537847019164285,
			"height": 16.919463549237264,
			"seed": 1374790550,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 251,
			"versionNonce": 1913636071,
			"isDeleted": false,
			"id": "jl96Bgrem81zPSneQFgJY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8.650769473432916,
			"y": -20.221931188197416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 14.025990072701026,
			"height": 12.799941989422967,
			"seed": 877062154,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 263,
			"versionNonce": 1265148169,
			"isDeleted": false,
			"id": "6yGOXGdJSzvB6rB_v6bxt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 11.30883905598516,
			"y": -17.552595907845884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.689054722987187,
			"height": 7.373954548697232,
			"seed": 1654511050,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 245,
			"versionNonce": 1974767623,
			"isDeleted": false,
			"id": "pwboHkfHUDDdkwtY6ePf5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 12.999682137215103,
			"y": -16.425367187025913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 5.260400697159807,
			"height": 4.9316256535873375,
			"seed": 1807627286,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 592,
			"versionNonce": 1503762409,
			"isDeleted": false,
			"id": "ZhTvChjePsP36gwzgf32k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 73.3899868948302,
			"y": -26.296324902154396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 23.279592165469186,
			"height": 21.033532291408903,
			"seed": 1800067798,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 445,
			"versionNonce": 1020458791,
			"isDeleted": false,
			"id": "I2TkqwspXCsCGicWqb-EG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 75.73928236066956,
			"y": -24.097538374581433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 18.537847019164285,
			"height": 16.919463549237264,
			"seed": 1242894358,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 393,
			"versionNonce": 1733866185,
			"isDeleted": false,
			"id": "zac04hoPHG-luUKTwmgLj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 78.0442527572323,
			"y": -22.135861441336544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 14.025990072701026,
			"height": 12.799941989422967,
			"seed": 1416011094,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 404,
			"versionNonce": 1574402631,
			"isDeleted": false,
			"id": "QHVG3ZAr_6trdaGpfKw6Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 80.70232233978454,
			"y": -19.466526160984998,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.689054722987187,
			"height": 7.373954548697232,
			"seed": 1335132822,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 463,
			"versionNonce": 690581929,
			"isDeleted": false,
			"id": "I0Zz6zKvuNACYdcxeb6Di",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 82.3931654210145,
			"y": -18.339297440165012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 5.260400697159807,
			"height": 4.9316256535873375,
			"seed": 240369622,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 71,
			"versionNonce": 1839110503,
			"isDeleted": false,
			"id": "99FCy9rkOnaGSy8c9U_P-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 109.67446675961716,
			"y": 50.4076415088048,
			"strokeColor": "#e03131",
			"backgroundColor": "#343a40",
			"width": 33.78565217128218,
			"height": 7.381739129859994,
			"seed": 2081543690,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.801304347140757,
					7.381739129859994
				],
				[
					33.78565217128218,
					2.839130434561554
				]
			]
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 876565641,
			"isDeleted": false,
			"id": "9m7YN2cO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 137.57928298192377,
			"y": 43.042279146076595,
			"strokeColor": "#e03131",
			"backgroundColor": "#343a40",
			"width": 35.25244140625,
			"height": 8.46927540923528,
			"seed": 1496279498,
			"groupIds": [
				"wlO4rSYfyYRS3be-6oCfn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467357,
			"link": null,
			"locked": false,
			"fontSize": 3.3877101636941123,
			"fontFamily": 1,
			"text": "YES THIS TOOK\nME AN HOUR TO DO",
			"rawText": "YES THIS TOOK\nME AN HOUR TO DO",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "YES THIS TOOK\nME AN HOUR TO DO",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 416,
			"versionNonce": 829740167,
			"isDeleted": false,
			"id": "WALV-U8ywmlixjSixN9Au",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -421.9498065870514,
			"y": 1587.7021954804304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 222.9377889941765,
			"height": 23.523962299364392,
			"seed": 135715798,
			"groupIds": [
				"LLxWGzH69CnV7KN8urYln"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 448,
			"versionNonce": 1817566057,
			"isDeleted": false,
			"id": "O0F3VrnPpNHP3Jn2CdfIh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -432.12220873810065,
			"y": 1599.1518634090426,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 222.9377889941765,
			"height": 23.523962299364392,
			"seed": 1347434902,
			"groupIds": [
				"LLxWGzH69CnV7KN8urYln"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "uFfuCiF0c11DvrB7kajnR",
					"type": "arrow"
				},
				{
					"id": "FrO7_guJyH2FzSlESD_M0",
					"type": "arrow"
				},
				{
					"id": "qyXiYdD4RccBlY6Wt-ANf",
					"type": "arrow"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 457,
			"versionNonce": 286698407,
			"isDeleted": false,
			"id": "7ynhjnEvOQAbORuecg0V2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -441.0038346627016,
			"y": 1610.6298751589513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 222.9377889941765,
			"height": 23.523962299364392,
			"seed": 186041110,
			"groupIds": [
				"LLxWGzH69CnV7KN8urYln"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "uFfuCiF0c11DvrB7kajnR",
					"type": "arrow"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 503,
			"versionNonce": 834176585,
			"isDeleted": false,
			"id": "vUR6bI08ted_59JMmA8h6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -451.4157894048408,
			"y": 1622.162892264154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 222.9377889941765,
			"height": 23.523962299364392,
			"seed": 306179286,
			"groupIds": [
				"LLxWGzH69CnV7KN8urYln"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 446,
			"versionNonce": 1219534535,
			"isDeleted": false,
			"id": "lWm98oTC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -370.5590382167745,
			"y": 1540.679752744472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 89.57688903808594,
			"height": 19.3710195272423,
			"seed": 134458698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Embedding X",
			"rawText": "Embedding X",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Embedding X",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 362,
			"versionNonce": 1329780009,
			"isDeleted": false,
			"id": "nZJEvFuq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -335.5852808060531,
			"y": 1564.7184829130265,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 24.576980590820312,
			"height": 15.49681562179384,
			"seed": 1453357066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 12.397452497435072,
			"fontFamily": 1,
			"text": "NxD",
			"rawText": "NxD",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "NxD",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 636,
			"versionNonce": 1524575719,
			"isDeleted": false,
			"id": "uFfuCiF0c11DvrB7kajnR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -197.7688134638977,
			"y": 1624.0266916118035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 203.74576608713627,
			"height": 0.20798390143148657,
			"seed": 1443349846,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "O0F3VrnPpNHP3Jn2CdfIh",
				"focus": 1.093605536348313,
				"gap": 11.415606280026495
			},
			"endBinding": {
				"elementId": "jnswlVn7xxRO4L6_w4R4J",
				"focus": 0.453024336043699,
				"gap": 5.092416488701616
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					203.74576608713627,
					0.20798390143148657
				]
			]
		},
		{
			"type": "rectangle",
			"version": 306,
			"versionNonce": 677398537,
			"isDeleted": false,
			"id": "zeZgAUXvcoH4Lzat7bIej",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -730.4537485041578,
			"y": 1496.6979510950396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 94.26865026151278,
			"height": 30,
			"seed": 1132268950,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "RjdybtEh"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 298,
			"versionNonce": 1118755079,
			"isDeleted": false,
			"id": "RjdybtEh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -705.4542729217413,
			"y": 1502.0124413314184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 44.26969909667969,
			"height": 19.3710195272423,
			"seed": 1071788886,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Token",
			"rawText": "Token",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "zeZgAUXvcoH4Lzat7bIej",
			"originalText": "Token",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 330,
			"versionNonce": 655122153,
			"isDeleted": false,
			"id": "ZFsqwln1vKYDuFZI-bAbY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -730.453748504158,
			"y": 1546.5270962660436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 94.26865026151278,
			"height": 30,
			"seed": 1835933654,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ilPjGdMr"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 312,
			"versionNonce": 1704730663,
			"isDeleted": false,
			"id": "ilPjGdMr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -705.4542729217416,
			"y": 1551.8415865024224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 44.26969909667969,
			"height": 19.3710195272423,
			"seed": 294106390,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Token",
			"rawText": "Token",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ZFsqwln1vKYDuFZI-bAbY",
			"originalText": "Token",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 319,
			"versionNonce": 1775409609,
			"isDeleted": false,
			"id": "O7X4FUXDKCoGlUtVBpHjT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -731.2019123951222,
			"y": 1598.3554766344855,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 94.26865026151278,
			"height": 30,
			"seed": 1605864150,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "L9nYsN1N"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 301,
			"versionNonce": 1167295303,
			"isDeleted": false,
			"id": "L9nYsN1N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -706.2024368127057,
			"y": 1603.6699668708643,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 44.26969909667969,
			"height": 19.3710195272423,
			"seed": 1835778070,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Token",
			"rawText": "Token",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "O7X4FUXDKCoGlUtVBpHjT",
			"originalText": "Token",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 338,
			"versionNonce": 835614889,
			"isDeleted": false,
			"id": "RGnAv98bTz_NUj312mGwd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -731.2019123951225,
			"y": 1650.183856805011,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 94.26865026151278,
			"height": 30,
			"seed": 1380164234,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "YSP1zzzo"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 320,
			"versionNonce": 1928430183,
			"isDeleted": false,
			"id": "YSP1zzzo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -706.202436812706,
			"y": 1655.4983470413897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 44.26969909667969,
			"height": 19.3710195272423,
			"seed": 729989450,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Token",
			"rawText": "Token",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "RGnAv98bTz_NUj312mGwd",
			"originalText": "Token",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 381,
			"versionNonce": 279673737,
			"isDeleted": false,
			"id": "6t91wRtGBurPp2oeZroAb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -730.453748551553,
			"y": 1696.648838862664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 94.26865026151278,
			"height": 30,
			"seed": 1218874890,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "F31mQgTc"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 363,
			"versionNonce": 1048747399,
			"isDeleted": false,
			"id": "F31mQgTc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -705.4542729691365,
			"y": 1701.9633290990428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 44.26969909667969,
			"height": 19.3710195272423,
			"seed": 1031552202,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Token",
			"rawText": "Token",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "6t91wRtGBurPp2oeZroAb",
			"originalText": "Token",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 222,
			"versionNonce": 1453662825,
			"isDeleted": false,
			"id": "ahuAp4_fuB64SFEZItnsk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -687.808406719188,
			"y": 1746.472607775148,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.237147236750622,
			"height": 5.237147236750622,
			"seed": 1272033238,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 224,
			"versionNonce": 730027175,
			"isDeleted": false,
			"id": "hBwMXjdJS3F6CdfaagUrv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -688.1824886646702,
			"y": 1773.0324259043837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.237147236750622,
			"height": 5.237147236750622,
			"seed": 1528280406,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 228,
			"versionNonce": 1082584393,
			"isDeleted": false,
			"id": "Lyw73KFWP88-dgyUvM9sm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -688.1824886646702,
			"y": 1797.7218343062082,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.237147236750622,
			"height": 5.237147236750622,
			"seed": 506350794,
			"groupIds": [
				"neJO_SmHuRcAPWXvMUisr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 195,
			"versionNonce": 564144071,
			"isDeleted": false,
			"id": "v3UoToRw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -759.0920602957976,
			"y": 1467.3515967187675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 125.11341857910156,
			"height": 19.3710195272423,
			"seed": 1868586506,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Input of Tokens",
			"rawText": "Input of Tokens",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Input of Tokens",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 137,
			"versionNonce": 1705794601,
			"isDeleted": false,
			"id": "nI8GjKqt31Q03FbpIdCCW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -614.6818662628325,
			"y": 1614.5626320305619,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 140.0018121581076,
			"height": 2.1538740332016855,
			"seed": 534941706,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					140.0018121581076,
					2.1538740332016855
				]
			]
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 1593153255,
			"isDeleted": false,
			"id": "nGzUM1os",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -614.649153781312,
			"y": 1537.7411248463695,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 123.5185546875,
			"height": 58.113058581726904,
			"seed": 1793735254,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "1. Embed meaning\nand position of\ninput",
			"rawText": "1. Embed meaning\nand position of\ninput",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Embed meaning\nand position of\ninput",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 1711337225,
			"isDeleted": false,
			"id": "fsfRLJuO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -178.26409174557307,
			"y": 1589.8997880265606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 139.04931640625,
			"height": 19.3710195272423,
			"seed": 21395402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "2.1 Compute Query",
			"rawText": "2.1 Compute Query",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2.1 Compute Query",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 518,
			"versionNonce": 705700359,
			"isDeleted": false,
			"id": "FrO7_guJyH2FzSlESD_M0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -197.63280487630664,
			"y": 1623.9669268089197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 203.60151568330983,
			"height": 242.3981095677104,
			"seed": 487283542,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "O0F3VrnPpNHP3Jn2CdfIh",
				"focus": 0.9140544065557544,
				"gap": 11.551614867617545
			},
			"endBinding": {
				"elementId": "xYJRyJy7IQma0suwbxq2a",
				"focus": 0.5603671312457196,
				"gap": 5.047885499348098
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					19.418658274632516,
					0.19875397931802094
				],
				[
					16.45592209234028,
					-242.19935558839222
				],
				[
					203.60151568330983,
					-242.1993555883924
				]
			]
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 1476404713,
			"isDeleted": false,
			"id": "mMDqNSTq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -169.6509281153145,
			"y": 1353.637446335646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 128.99996948242188,
			"height": 19.371019527242296,
			"seed": 345838602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.496815621793838,
			"fontFamily": 1,
			"text": "2.2 Compute Key",
			"rawText": "2.2 Compute Key",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2.2 Compute Key",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 631,
			"versionNonce": 1139558695,
			"isDeleted": false,
			"id": "qyXiYdD4RccBlY6Wt-ANf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -197.12555564539628,
			"y": 1623.8627428293835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 208.16511270673175,
			"height": 244.65025706291402,
			"seed": 589688074,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "O0F3VrnPpNHP3Jn2CdfIh",
				"focus": 1.1018344391114572,
				"gap": 12.058864098527906
			},
			"endBinding": {
				"elementId": "Hr28ZpFBCY7wJ-WpiN5F6",
				"focus": 0.5153360889643194,
				"gap": 2.712227619576197
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					19.399650959639175,
					-0.2977197628204062
				],
				[
					16.115179420889238,
					244.35253730009345
				],
				[
					208.16511270673175,
					244.35253730009362
				]
			]
		},
		{
			"type": "text",
			"version": 206,
			"versionNonce": 1991606473,
			"isDeleted": false,
			"id": "N44nnDVX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -180.3712263050296,
			"y": 1838.4502144383118,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 142.9668426513672,
			"height": 19.371019527242296,
			"seed": 1276415446,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"fontSize": 15.496815621793838,
			"fontFamily": 1,
			"text": "2.3 Compute Value",
			"rawText": "2.3 Compute Value",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2.3 Compute Value",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 464,
			"versionNonce": 435588167,
			"isDeleted": false,
			"id": "B7r3tbzUdhKLeKuPxa9Rp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -154.08760039832748,
			"y": 1424.359471392037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 107.36130264062218,
			"height": 99.55267133816344,
			"seed": 383090006,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZdO_LdyuMllJh80Z9DF1X",
					"type": "arrow"
				}
			],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 399,
			"versionNonce": 264011689,
			"isDeleted": false,
			"id": "Y5vapr39WpyBmhDUre_nJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -139.62762832073122,
			"y": 1424.7194261166755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1723663190,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 417,
			"versionNonce": 940272487,
			"isDeleted": false,
			"id": "cVRkmolhaWFZ-Eb-Byl_G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -124.06018210673335,
			"y": 1424.7194262867138,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 116476234,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 408,
			"versionNonce": 826319497,
			"isDeleted": false,
			"id": "MWpe26BMtW6Ib6eW6zmJd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -108.49273587676987,
			"y": 1424.7194262176604,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 804349590,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 409,
			"versionNonce": 2054645383,
			"isDeleted": false,
			"id": "pPVEBBoaPEtB_x69DmKFI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -92.92528998701357,
			"y": 1424.7194260050471,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 874842134,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 414,
			"versionNonce": 402483561,
			"isDeleted": false,
			"id": "8Ki6JMTpg1P_RO12wAlD6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -77.3578437730157,
			"y": 1424.3594715162462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 831416022,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 415,
			"versionNonce": 2146893223,
			"isDeleted": false,
			"id": "Ty9j9TGnFB0DIhWO0OReQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -61.79039817556986,
			"y": 1424.3594714099395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1815650966,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 417,
			"versionNonce": 1564365897,
			"isDeleted": false,
			"id": "nH_OQHiw4TEhli5U7mI-F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.22294979299636,
			"y": 1448.9940883329232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1374615434,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 1538699463,
			"isDeleted": false,
			"id": "0ZNlNzocfzGZPhIllmLFJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.90704092216731,
			"y": 1464.0338245997264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1259336150,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 452,
			"versionNonce": 1692328745,
			"isDeleted": false,
			"id": "LmC-9ypcZyLUgm35bAG4v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.16752969663776,
			"y": 1479.0735610791428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1375448534,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 467,
			"versionNonce": 122879975,
			"isDeleted": false,
			"id": "ke14IcOr88A4hLVa7vS2I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.959094768906766,
			"y": 1494.377152476342,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1962044490,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 466,
			"versionNonce": 189437449,
			"isDeleted": false,
			"id": "d_nerEMh7UVv4qeaVd_iU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.48680481708607,
			"y": 1508.8891788012727,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 165317590,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 349727495,
			"isDeleted": false,
			"id": "zy3d-UCEz0GvGBcAPri0n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.75065984117566,
			"y": 1437.1206122488888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 975165898,
			"groupIds": [
				"6V7Q7LxyaQkFs4g1Kl_D1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 487,
			"versionNonce": 326954217,
			"isDeleted": false,
			"id": "uS945AJG-wlYUA-NpHQNw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -154.08760010947458,
			"y": 1663.9108293313473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 107.36130264062218,
			"height": 99.55267133816344,
			"seed": 973000650,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 424,
			"versionNonce": 549679655,
			"isDeleted": false,
			"id": "8FeX3DtWO7fLj2TMEdSyJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -139.6276280318782,
			"y": 1664.2707840559858,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1709590154,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 441,
			"versionNonce": 1426155465,
			"isDeleted": false,
			"id": "MGEReYHGkHuNGor9-I4sY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -124.06018181788033,
			"y": 1664.270784226024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 2066801994,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467358,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 433,
			"versionNonce": 67147079,
			"isDeleted": false,
			"id": "Dr_HSCpugo-z5fdeAXnP5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -108.49273558791685,
			"y": 1664.2707841569706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 859417610,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 434,
			"versionNonce": 703825577,
			"isDeleted": false,
			"id": "pk4KRw1-9u6vY8FrVvmI0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -92.92528969816067,
			"y": 1664.2707839443574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1677433546,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 438,
			"versionNonce": 1173116007,
			"isDeleted": false,
			"id": "9Zidq7lzHkEo8407mUkO-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -77.35784348416269,
			"y": 1663.9108294555565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1813098890,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 439,
			"versionNonce": 486459785,
			"isDeleted": false,
			"id": "gDyoS2GzJhBETjuK4fhmO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -61.790397886716846,
			"y": 1663.9108293492498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 515305546,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 442,
			"versionNonce": 1314074503,
			"isDeleted": false,
			"id": "c9WaY4yKmOyANlnxSVzHG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.22294950414346,
			"y": 1688.5454462722334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 801527562,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 478,
			"versionNonce": 1465823337,
			"isDeleted": false,
			"id": "0cLbna7g5126rODN_MWG-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.90704063331441,
			"y": 1703.5851825390364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 532342218,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 1467066023,
			"isDeleted": false,
			"id": "7rL7cnzghqK0y2N6dRK1N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.167529407784855,
			"y": 1718.6249190184533,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 665820298,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 492,
			"versionNonce": 1323219785,
			"isDeleted": false,
			"id": "xtMVwVCWQLuhu2dDUNdS9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.959094480053864,
			"y": 1733.9285104156525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 627014474,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 491,
			"versionNonce": 536099271,
			"isDeleted": false,
			"id": "Mhk1L6WSRZD7eEj9zvedp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.48680452823305,
			"y": 1748.4405367405834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 119898634,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 869952041,
			"isDeleted": false,
			"id": "1DfRKv8sY2zESL_poWUx0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.75065955232276,
			"y": 1676.6719701881989,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 939307210,
			"groupIds": [
				"EjfGe2W09Rb0tnwcopjpI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 1559718119,
			"isDeleted": false,
			"id": "sMQftesh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -178.00080262612778,
			"y": 1643.1647307157455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 132.62413024902344,
			"height": 15.49681562179384,
			"seed": 1484327446,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"fontSize": 12.397452497435072,
			"fontFamily": 1,
			"text": "Learnable parameters",
			"rawText": "Learnable parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Learnable parameters",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 524107017,
			"isDeleted": false,
			"id": "UHThmYoj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -179.4114650204117,
			"y": 1404.2465818809897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 132.62413024902344,
			"height": 15.49681562179384,
			"seed": 1409112662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"fontSize": 12.397452497435072,
			"fontFamily": 1,
			"text": "Learnable parameters",
			"rawText": "Learnable parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Learnable parameters",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 309,
			"versionNonce": 1812444167,
			"isDeleted": false,
			"id": "ZdO_LdyuMllJh80Z9DF1X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.48088045314705,
			"y": 1470.5374790546687,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 50.07851499707856,
			"height": 0,
			"seed": 266254422,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "B7r3tbzUdhKLeKuPxa9Rp",
				"focus": -0.07228993372216082,
				"gap": 1
			},
			"endBinding": {
				"elementId": "xYJRyJy7IQma0suwbxq2a",
				"focus": -0.5980113138440519,
				"gap": 7.418961762419784
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					50.07851499707856,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 227,
			"versionNonce": 8565737,
			"isDeleted": false,
			"id": "2U6rP_7ympOWk_OsitBcc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.83354605171803,
			"y": 1711.0554172800744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 50.07851499707856,
			"height": 0,
			"seed": 660396950,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "jnswlVn7xxRO4L6_w4R4J",
				"focus": -0.6791314864608651,
				"gap": 7.824400166579679
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					50.07851499707856,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 171,
			"versionNonce": 1159830311,
			"isDeleted": false,
			"id": "xYJRyJy7IQma0suwbxq2a",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 11.016596306351289,
			"y": 1348.07722640653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"width": 74.36566138220846,
			"height": 153.26581431211267,
			"seed": 955478614,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "FrO7_guJyH2FzSlESD_M0",
					"type": "arrow"
				},
				{
					"id": "ZdO_LdyuMllJh80Z9DF1X",
					"type": "arrow"
				},
				{
					"id": "Li9ZXOup8VocdgmBIGVjR",
					"type": "arrow"
				}
			],
			"updated": 1714137467359,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 1270238921,
			"isDeleted": false,
			"id": "PHPiIlT4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 16.191864641798702,
			"y": 1319.8816060993108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"width": 58.96833801269531,
			"height": 27.11942733813922,
			"seed": 1853774666,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467359,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511377,
			"fontFamily": 1,
			"text": "Query",
			"rawText": "Query",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Query",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 187,
			"versionNonce": 749837895,
			"isDeleted": false,
			"id": "jnswlVn7xxRO4L6_w4R4J",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 11.069369111940205,
			"y": 1582.378689975308,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9775fa",
			"width": 74.36566138220846,
			"height": 153.26581431211267,
			"seed": 2047153878,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "uFfuCiF0c11DvrB7kajnR",
					"type": "arrow"
				},
				{
					"id": "2U6rP_7ympOWk_OsitBcc",
					"type": "arrow"
				},
				{
					"id": "hJ9ALG5BRbF57cx9MJDoi",
					"type": "arrow"
				}
			],
			"updated": 1714137467359,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1735626153,
			"isDeleted": false,
			"id": "0QzL4nC8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 35.04994851308095,
			"y": 1550.816910882244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9775fa",
			"width": 35.32896423339844,
			"height": 27.11942733813922,
			"seed": 1718804298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511377,
			"fontFamily": 1,
			"text": "Key",
			"rawText": "Key",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Key",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 754,
			"versionNonce": 630472039,
			"isDeleted": false,
			"id": "Li9ZXOup8VocdgmBIGVjR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 88.70111784974256,
			"y": 1449.4242121167606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9775fa",
			"width": 202.61310633312496,
			"height": 57.965634411161794,
			"seed": 1792435798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xYJRyJy7IQma0suwbxq2a",
				"focus": 0.3177912100502317,
				"gap": 3.318860161182812
			},
			"endBinding": {
				"elementId": "YfLToCTsyl4NSUUwDfVuF",
				"focus": 0.36961541595826175,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					97.73275569323795,
					0.6740190047809747
				],
				[
					97.73275569323795,
					57.965634411161794
				],
				[
					202.61310633312496,
					57.69342756722444
				]
			]
		},
		{
			"type": "arrow",
			"version": 784,
			"versionNonce": 1525018761,
			"isDeleted": false,
			"id": "hJ9ALG5BRbF57cx9MJDoi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 88.7011176325467,
			"y": 1635.5790120542283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9775fa",
			"width": 201.73478050971448,
			"height": 57.965634411161915,
			"seed": 1514451414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jnswlVn7xxRO4L6_w4R4J",
				"focus": -0.30112921870908516,
				"gap": 3.266087138398035
			},
			"endBinding": {
				"elementId": "YfLToCTsyl4NSUUwDfVuF",
				"focus": -0.5363942503104563,
				"gap": 1.124641883547298
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					97.73275569323816,
					-0.6740190047809761
				],
				[
					97.73275569323816,
					-57.965634411161915
				],
				[
					201.73478050971448,
					-56.36495806851334
				]
			]
		},
		{
			"type": "rectangle",
			"version": 275,
			"versionNonce": 588642439,
			"isDeleted": false,
			"id": "YfLToCTsyl4NSUUwDfVuF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 291.56054002580845,
			"y": 1456.6830820425184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 66.69885201995108,
			"height": 159.83688862438723,
			"seed": 1168419018,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "Li9ZXOup8VocdgmBIGVjR",
					"type": "arrow"
				},
				{
					"id": "hJ9ALG5BRbF57cx9MJDoi",
					"type": "arrow"
				},
				{
					"id": "jKVVizJAoYpn-FmN_aQyM",
					"type": "arrow"
				}
			],
			"updated": 1714137467360,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 222,
			"versionNonce": 1003026281,
			"isDeleted": false,
			"id": "5El3kDW4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 279.6274094956634,
			"y": 1431.4456785755099,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 76.19876098632812,
			"height": 20.702612604214234,
			"seed": 239527114,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"fontSize": 16.562090083371388,
			"fontFamily": 1,
			"text": "Attention",
			"rawText": "Attention",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Attention",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 2062765991,
			"isDeleted": false,
			"id": "gNUe2SKx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 147.1161688385323,
			"y": 1533.8821288836848,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 119.27581787109375,
			"height": 19.3710195272423,
			"seed": 1532935178,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "3. Dot Product",
			"rawText": "3. Dot Product",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3. Dot Product",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 655,
			"versionNonce": 1550328393,
			"isDeleted": false,
			"id": "jKVVizJAoYpn-FmN_aQyM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 359.5417484298655,
			"y": 1536.6769658286782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 99.60659449084045,
			"height": 0.7020360580850911,
			"seed": 1448186698,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "YfLToCTsyl4NSUUwDfVuF",
				"focus": -0.002104067740991125,
				"gap": 1.2823563841059524
			},
			"endBinding": {
				"elementId": "D9IWtHGv3tDnIroL4XFmz",
				"focus": -0.03268388582303324,
				"gap": 1.4868885559504292
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					99.60659449084045,
					0.7020360580850911
				]
			]
		},
		{
			"type": "rectangle",
			"version": 516,
			"versionNonce": 391692999,
			"isDeleted": false,
			"id": "D65zq-cnth3DkgkENImP6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -150.35535210825344,
			"y": 1905.949516363356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 107.36130264062218,
			"height": 99.55267133816344,
			"seed": 190173782,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "dhKPFM2vnMTD7iwW4aYgY",
					"type": "arrow"
				}
			],
			"updated": 1714137467360,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 452,
			"versionNonce": 966717737,
			"isDeleted": false,
			"id": "0Gm2nLiN4VfzKKwinCRxP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -135.89538003065707,
			"y": 1906.309471087995,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 752162710,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 469,
			"versionNonce": 1759695335,
			"isDeleted": false,
			"id": "HNVpmu-TcSk-Zo2biVGlg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -120.3279338166592,
			"y": 1906.3094712580332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 12170454,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 461,
			"versionNonce": 685302793,
			"isDeleted": false,
			"id": "ctm2UiToZRcYO0mkl4hFo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -104.76048758669572,
			"y": 1906.3094711889798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1083746838,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 462,
			"versionNonce": 413007111,
			"isDeleted": false,
			"id": "X8hdAtOtDeBVHOHzq1lAL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -89.19304169693942,
			"y": 1906.3094709763664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 728168278,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 466,
			"versionNonce": 1175550697,
			"isDeleted": false,
			"id": "ddghF5lgynaLkYa1nXjec",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -73.62559548294155,
			"y": 1905.9495164875657,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 1501142166,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 467,
			"versionNonce": 2047263783,
			"isDeleted": false,
			"id": "-oBKsHoQaqWrNVafOjCN5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -58.058149885495595,
			"y": 1905.949516381259,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0.5277100481793101,
			"height": 99.20948905770709,
			"seed": 277191126,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5277100481793101,
					99.20948905770709
				]
			]
		},
		{
			"type": "line",
			"version": 470,
			"versionNonce": 567555529,
			"isDeleted": false,
			"id": "38KLXNBReW-eq9inw0IGq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.49070150292221,
			"y": 1930.5841333042426,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 396357398,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 506,
			"versionNonce": 1024042823,
			"isDeleted": false,
			"id": "1n2n6LfNoKo-KRhydVSCp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.17479263209316,
			"y": 1945.6238695710454,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 188587094,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 792499369,
			"isDeleted": false,
			"id": "sIwbEgGFIHmiuMiaXK7Tw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -41.43528140656372,
			"y": 1960.663606050462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 825467286,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 520,
			"versionNonce": 1610819175,
			"isDeleted": false,
			"id": "lBnSy-KnNl1fmWIALQcLW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.22684647883261,
			"y": 1975.9671974476614,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1287061206,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 519,
			"versionNonce": 1911953289,
			"isDeleted": false,
			"id": "cfNvjiOhSK__MOcnTzfWn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.754556527011914,
			"y": 1990.4792237725924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1918678038,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 1639956871,
			"isDeleted": false,
			"id": "MdlOCd_2nv49vRKfZutob",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -43.01841155110162,
			"y": 1918.7106572202078,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 108.18055987675503,
			"height": 0,
			"seed": 1545191766,
			"groupIds": [
				"aeEN7w0WTWPy6b-q0dmgs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-108.18055987675503,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 1815887465,
			"isDeleted": false,
			"id": "YKw7Jgkr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -174.26855462490664,
			"y": 1885.2034177477544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 132.62413024902344,
			"height": 15.49681562179384,
			"seed": 1027810966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"fontSize": 12.397452497435072,
			"fontFamily": 1,
			"text": "Learnable parameters",
			"rawText": "Learnable parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Learnable parameters",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 352,
			"versionNonce": 863762599,
			"isDeleted": false,
			"id": "dhKPFM2vnMTD7iwW4aYgY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.34265150391059,
			"y": 1953.0158119788662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 50.07851499707856,
			"height": 0,
			"seed": 1695360266,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "D65zq-cnth3DkgkENImP6",
				"focus": -0.054444346236896105,
				"gap": 1
			},
			"endBinding": {
				"elementId": "Hr28ZpFBCY7wJ-WpiN5F6",
				"focus": -0.5912450782710557,
				"gap": 6.0159211877437
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					50.07851499707856,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 212,
			"versionNonce": 1289390409,
			"isDeleted": false,
			"id": "Hr28ZpFBCY7wJ-WpiN5F6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 13.751784680911669,
			"y": 1831.0740756331886,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f783ac",
			"width": 74.36566138220846,
			"height": 153.26581431211267,
			"seed": 745276298,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "qyXiYdD4RccBlY6Wt-ANf",
					"type": "arrow"
				},
				{
					"id": "dhKPFM2vnMTD7iwW4aYgY",
					"type": "arrow"
				},
				{
					"id": "5WK00Etj6ZlluU2fCYmD3",
					"type": "arrow"
				}
			],
			"updated": 1714137467360,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 1793346503,
			"isDeleted": false,
			"id": "MwzFGxR1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 21.755939918174818,
			"y": 1801.4958815484833,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f783ac",
			"width": 55.56340026855469,
			"height": 27.11942733813922,
			"seed": 773056406,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511377,
			"fontFamily": 1,
			"text": "Value",
			"rawText": "Value",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Value",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 265,
			"versionNonce": 1563195433,
			"isDeleted": false,
			"id": "hIQ85kOv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 370.28973271592554,
			"y": 1489.1105628738271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f783ac",
			"width": 61.95280456542969,
			"height": 38.7420390544846,
			"seed": 1494338134,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467360,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "4. Scale\ndown",
			"rawText": "4. Scale\ndown",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4. Scale\ndown",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 305,
			"versionNonce": 873806567,
			"isDeleted": false,
			"id": "D9IWtHGv3tDnIroL4XFmz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 460.6352314766564,
			"y": 1455.0863593439567,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 66.69885201995108,
			"height": 159.83688862438723,
			"seed": 544454870,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "jKVVizJAoYpn-FmN_aQyM",
					"type": "arrow"
				},
				{
					"id": "yNMkH7d5K1poHM4vpQNR6",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 790465289,
			"isDeleted": false,
			"id": "OwUEbRQn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 439.5371699189873,
			"y": 1412.7649078216941,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 96.88249206542969,
			"height": 41.40522520842847,
			"seed": 1591758230,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 16.562090083371388,
			"fontFamily": 1,
			"text": "Scaled down\nAttention",
			"rawText": "Scaled down\nAttention",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Scaled down\nAttention",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 815,
			"versionNonce": 60507655,
			"isDeleted": false,
			"id": "yNMkH7d5K1poHM4vpQNR6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 528.2405298531994,
			"y": 1537.588159318244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 92.80852112669075,
			"height": 0.12772741486161152,
			"seed": 252909962,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ml18MqLB",
				"focus": 2.010791062208948,
				"gap": 12.013087496806293
			},
			"endBinding": {
				"elementId": "76uKjfvEmgi5w1GcmqpKW",
				"focus": -0.033434352754103135,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					92.80852112669075,
					0.12772741486161152
				]
			]
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 187253225,
			"isDeleted": false,
			"id": "ml18MqLB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 524.5858288920788,
			"y": 1501.914943130907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#4dabf7",
			"width": 85.66361999511719,
			"height": 23.660128690530552,
			"seed": 789334282,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "yNMkH7d5K1poHM4vpQNR6",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 9.464051476212221,
			"fontFamily": 1,
			"text": "5. (Optional) Mask\nfuture tokens",
			"rawText": "5. (Optional) Mask\nfuture tokens",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "5. (Optional) Mask\nfuture tokens",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 302,
			"versionNonce": 141749543,
			"isDeleted": false,
			"id": "76uKjfvEmgi5w1GcmqpKW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 621.0565480874409,
			"y": 1451.8917462489555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#3bc9db",
			"width": 66.25838710219679,
			"height": 166.18030958696127,
			"seed": 3419018,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "yNMkH7d5K1poHM4vpQNR6",
					"type": "arrow"
				},
				{
					"id": "IQC4nxyyZPO0ApWc8zrkn",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 196,
			"versionNonce": 509287625,
			"isDeleted": false,
			"id": "JWRmi8fY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 610.7851548595934,
			"y": 1409.8356042683902,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#3bc9db",
			"width": 76.19876098632812,
			"height": 41.40522520842847,
			"seed": 1710910934,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 16.562090083371388,
			"fontFamily": 1,
			"text": "Masked\nAttention",
			"rawText": "Masked\nAttention",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Masked\nAttention",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 745,
			"versionNonce": 1577627719,
			"isDeleted": false,
			"id": "IQC4nxyyZPO0ApWc8zrkn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 689.9980369668046,
			"y": 1537.158262692311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#3bc9db",
			"width": 91.90307918494436,
			"height": 133.6212704679006,
			"seed": 1271347734,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qhhJHJ11",
				"focus": 1.4732581362733381,
				"gap": 8.661501360847865
			},
			"endBinding": {
				"elementId": "3g73WoPrwFpsGRCS8zglP",
				"focus": -0.05619466791421459,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					91.64195658616639,
					1.223448759231732
				],
				[
					91.90307918494436,
					133.6212704679006
				]
			]
		},
		{
			"type": "text",
			"version": 238,
			"versionNonce": 1749982121,
			"isDeleted": false,
			"id": "qhhJHJ11",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 682.8285063044586,
			"y": 1493.0065682956674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#3bc9db",
			"width": 91.36383056640625,
			"height": 35.490193035795826,
			"seed": 964197526,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IQC4nxyyZPO0ApWc8zrkn",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 9.464051476212221,
			"fontFamily": 1,
			"text": "6. Preform softmax\nin order to get\nprobability dist",
			"rawText": "6. Preform softmax\nin order to get\nprobability dist",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "6. Preform softmax\nin order to get\nprobability dist",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 457,
			"versionNonce": 2117668711,
			"isDeleted": false,
			"id": "5WK00Etj6ZlluU2fCYmD3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 90.84731379924733,
			"y": 1901.552122330152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#3bc9db",
			"width": 773.7304753389736,
			"height": 0.3831159378654659,
			"seed": 4176010,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Hr28ZpFBCY7wJ-WpiN5F6",
				"focus": -0.08003903449056002,
				"gap": 2.729867736127204
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					773.7304753389736,
					-0.3831159378654659
				]
			]
		},
		{
			"type": "rectangle",
			"version": 257,
			"versionNonce": 1764703881,
			"isDeleted": false,
			"id": "3g73WoPrwFpsGRCS8zglP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 715.9073332214878,
			"y": 1671.554373941301,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 140.00202979692537,
			"height": 69.14734398506701,
			"seed": 1662384214,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "IQC4nxyyZPO0ApWc8zrkn",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 1934658183,
			"isDeleted": false,
			"id": "BoNFtDtM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 632.7407278461303,
			"y": 1693.2698801798638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 55.97584533691406,
			"height": 19.3710195272423,
			"seed": 1691099030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Weights",
			"rawText": "Weights",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weights",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 281,
			"versionNonce": 263751017,
			"isDeleted": false,
			"id": "jpRN7TRY2OhTTlbWduUvc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 783.2415075338806,
			"y": 1740.3387870064325,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 81.2225052154438,
			"height": 111.68094467123525,
			"seed": 312437910,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					0.6768542101286558,
					110.32723625097795
				],
				[
					81.2225052154438,
					111.68094467123525
				]
			]
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 1242276263,
			"isDeleted": false,
			"id": "pSMcFmLR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 580.7140897507034,
			"y": 1836.6007744194203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 173.82708740234375,
			"height": 58.113058581726904,
			"seed": 1911124362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "7. Multiply by values\nto apply the attention\nto the values",
			"rawText": "7. Multiply by values\nto apply the attention\nto the values",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "7. Multiply by values\nto apply the attention\nto the values",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 1731588169,
			"isDeleted": false,
			"id": "rTn6yFIV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 735.0521139136595,
			"y": 1695.3132269163998,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 88.37660217285156,
			"height": 27.11942733813922,
			"seed": 1127297354,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511377,
			"fontFamily": 1,
			"text": "Softmax",
			"rawText": "Softmax",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Softmax",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 207,
			"versionNonce": 1133958343,
			"isDeleted": false,
			"id": "QgR5yKFm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5774987432523009,
			"x": 626.338369792096,
			"y": 1514.73290876788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 53.41632080078125,
			"height": 27.11942733813922,
			"seed": 1565195990,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511377,
			"fontFamily": 1,
			"text": "Mask",
			"rawText": "Mask",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mask",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 229,
			"versionNonce": 92471081,
			"isDeleted": false,
			"id": "HDVpQVW0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.574199129893807,
			"x": 451.95342629910033,
			"y": 1521.3890427398337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 76.4267578125,
			"height": 27.11942733813922,
			"seed": 1303802454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511377,
			"fontFamily": 1,
			"text": "Division",
			"rawText": "Division",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Division",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 309,
			"versionNonce": 1200530407,
			"isDeleted": false,
			"id": "NE8keUFk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5802080937817387,
			"x": 252.70460345655385,
			"y": 1522.7202695342244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 135.50357055664062,
			"height": 27.119427338139218,
			"seed": 59450326,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 21.695541870511374,
			"fontFamily": 1,
			"text": "Dot Product",
			"rawText": "Dot Product",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dot Product",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 180,
			"versionNonce": 957035017,
			"isDeleted": false,
			"id": "jo7ylYnf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.575954046315296,
			"x": -3.5515513796418645,
			"y": 1412.4293651434164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 90.90849304199219,
			"height": 19.3710195272423,
			"seed": 2130595670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Matrix Mult",
			"rawText": "Matrix Mult",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Matrix Mult",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 369069831,
			"isDeleted": false,
			"id": "NozjapoF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.575954046315296,
			"x": -4.363719799554701,
			"y": 1645.7688511278243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 90.90849304199219,
			"height": 19.3710195272423,
			"seed": 1151646154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Matrix Mult",
			"rawText": "Matrix Mult",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Matrix Mult",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 168,
			"versionNonce": 1992952041,
			"isDeleted": false,
			"id": "dOjfiAsy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.575954046315296,
			"x": -1.9272145398164184,
			"y": 1895.916724460953,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ff8787",
			"width": 90.90849304199219,
			"height": 19.3710195272423,
			"seed": 1483441174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Matrix Mult",
			"rawText": "Matrix Mult",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Matrix Mult",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 150,
			"versionNonce": 962991655,
			"isDeleted": false,
			"id": "aABzhH_hDecn1QnOUtOI_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 860.3951027327744,
			"y": 1815.679926037948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"width": 62.061417238039816,
			"height": 123.75560715514428,
			"seed": 130978966,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 139133897,
			"isDeleted": false,
			"id": "rSVCbUBx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.561047003010306,
			"x": 858.0296351296597,
			"y": 1863.419477759517,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"width": 53.962890625,
			"height": 19.3710195272423,
			"seed": 2073149898,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 15.49681562179384,
			"fontFamily": 1,
			"text": "Output",
			"rawText": "Output",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Output",
			"lineHeight": 1.25
		},
		{
			"id": "7bwAnWUJ",
			"type": "text",
			"x": -1087.9797395798732,
			"y": 1901.0403357687983,
			"width": 815.2391357421875,
			"height": 300,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1975425289,
			"version": 812,
			"versionNonce": 950974791,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "1) Embedding\n\nThe embedding process is a simple pre-determined process\nthat involves turning our tokens (for example words or sub-words)\ninto a set of vectors that have already been established by the embedding\nmethod we use, its just a basic lookup table for all words.\n\nalongside the embedding of the semantic of the token we also need to embed the\nposition of each word, I wont get into much details in this as its a bit irrelevant\nbut the process is by taking some sin function and cosine function and alternating\nbetween them in odd and even positions to generate unique position vectors\nwhich are then added to the semantic embedding",
			"rawText": "1) Embedding\n\nThe embedding process is a simple pre-determined process\nthat involves turning our tokens (for example words or sub-words)\ninto a set of vectors that have already been established by the embedding\nmethod we use, its just a basic lookup table for all words.\n\nalongside the embedding of the semantic of the token we also need to embed the\nposition of each word, I wont get into much details in this as its a bit irrelevant\nbut the process is by taking some sin function and cosine function and alternating\nbetween them in odd and even positions to generate unique position vectors\nwhich are then added to the semantic embedding",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Embedding\n\nThe embedding process is a simple pre-determined process\nthat involves turning our tokens (for example words or sub-words)\ninto a set of vectors that have already been established by the embedding\nmethod we use, its just a basic lookup table for all words.\n\nalongside the embedding of the semantic of the token we also need to embed the\nposition of each word, I wont get into much details in this as its a bit irrelevant\nbut the process is by taking some sin function and cosine function and alternating\nbetween them in odd and even positions to generate unique position vectors\nwhich are then added to the semantic embedding",
			"lineHeight": 1.25
		},
		{
			"id": "5nEKHXka",
			"type": "text",
			"x": -106.96412700676075,
			"y": 1526.9677670856502,
			"width": 20.672042846679688,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2076305031,
			"version": 25,
			"versionNonce": 2041160361,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Wq",
			"rawText": "Wq",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Wq",
			"lineHeight": 1.25
		},
		{
			"id": "IxQ25jja",
			"type": "text",
			"x": -112.21753937548914,
			"y": 1769.0709238394224,
			"width": 19.728042602539062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1105852457,
			"version": 26,
			"versionNonce": 154531943,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Wk",
			"rawText": "Wk",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Wk",
			"lineHeight": 1.25
		},
		{
			"id": "lKLCO5ti",
			"type": "text",
			"x": -646.2704720175592,
			"y": 2291.3146974247816,
			"width": 894.59912109375,
			"height": 725,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"YNcIDHFb7bNe-2gmfaU72"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1540688297,
			"version": 1567,
			"versionNonce": 1200711049,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "6Sb5GhUp_dh_qJX7E8qD6",
					"type": "arrow"
				},
				{
					"id": "fKc0ZMD4MK67KQJ9jY1Kd",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "2) Computing Query, Key, Value\n\nThis is the process in which we introduce Learnable parameters, because this is the\npart that will later tell us what the relations of different tokens are.\nLets start by explaining what each Q,K,V are:\n\n\n\nQuery:\nQuery is usually interpreted as our current query, our current token treated\nas context, the token we are looking to understand.\nAs in, given our current token as context, when we want to produce an output for it\nwhat should we pay attention to/ put weight on in other tokens?\n\n\n\nKey:\nKeys are interpreted as a potential answer to the query question.\nas in, given our current token as context, does it play any major role or weight\nin describing other tokens?\n\n\n\n\nValue:\nValue can be seen as the adjustment we need to do on the current context embedding to\ncorrectly model all of those other words that affected it.\nthis is all talking in representation space of the embedding.\n",
			"rawText": "2) Computing Query, Key, Value\n\nThis is the process in which we introduce Learnable parameters, because this is the\npart that will later tell us what the relations of different tokens are.\nLets start by explaining what each Q,K,V are:\n\n\n\nQuery:\nQuery is usually interpreted as our current query, our current token treated\nas context, the token we are looking to understand.\nAs in, given our current token as context, when we want to produce an output for it\nwhat should we pay attention to/ put weight on in other tokens?\n\n\n\nKey:\nKeys are interpreted as a potential answer to the query question.\nas in, given our current token as context, does it play any major role or weight\nin describing other tokens?\n\n\n\n\nValue:\nValue can be seen as the adjustment we need to do on the current context embedding to\ncorrectly model all of those other words that affected it.\nthis is all talking in representation space of the embedding.\n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Computing Query, Key, Value\n\nThis is the process in which we introduce Learnable parameters, because this is the\npart that will later tell us what the relations of different tokens are.\nLets start by explaining what each Q,K,V are:\n\n\n\nQuery:\nQuery is usually interpreted as our current query, our current token treated\nas context, the token we are looking to understand.\nAs in, given our current token as context, when we want to produce an output for it\nwhat should we pay attention to/ put weight on in other tokens?\n\n\n\nKey:\nKeys are interpreted as a potential answer to the query question.\nas in, given our current token as context, does it play any major role or weight\nin describing other tokens?\n\n\n\n\nValue:\nValue can be seen as the adjustment we need to do on the current context embedding to\ncorrectly model all of those other words that affected it.\nthis is all talking in representation space of the embedding.\n",
			"lineHeight": 1.25
		},
		{
			"id": "zyf5sL7f",
			"type": "text",
			"x": -503.6498212501731,
			"y": 2419.109569219653,
			"width": 637.873291015625,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"YNcIDHFb7bNe-2gmfaU72"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1523532295,
			"version": 99,
			"versionNonce": 1086870407,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "lets be clear first that we do not understand what is saved in those learnable\nparameters as it is beyond our understanding, it is what the model will learn\nand we only make interpretations of what it will learn according to results.",
			"rawText": "lets be clear first that we do not understand what is saved in those learnable\nparameters as it is beyond our understanding, it is what the model will learn\nand we only make interpretations of what it will learn according to results.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lets be clear first that we do not understand what is saved in those learnable\nparameters as it is beyond our understanding, it is what the model will learn\nand we only make interpretations of what it will learn according to results.",
			"lineHeight": 1.25
		},
		{
			"id": "KVDN69AL",
			"type": "text",
			"x": -607.1059857037603,
			"y": 2617.151305102634,
			"width": 828.44970703125,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"YNcIDHFb7bNe-2gmfaU72"
			],
			"frameId": null,
			"roundness": null,
			"seed": 609769255,
			"version": 272,
			"versionNonce": 1295895657,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "(e.g Given the current word in a sentence, are there any adjectives behind it that give it more meaning?\nour noun is the token and the query is the question of what we need to pay attention to)",
			"rawText": "(e.g Given the current word in a sentence, are there any adjectives behind it that give it more meaning?\nour noun is the token and the query is the question of what we need to pay attention to)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(e.g Given the current word in a sentence, are there any adjectives behind it that give it more meaning?\nour noun is the token and the query is the question of what we need to pay attention to)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 374,
			"versionNonce": 128076455,
			"isDeleted": false,
			"id": "FQLdx2gZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -620.6757149248954,
			"y": 2795.193041644598,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffa94d",
			"width": 843.4096069335938,
			"height": 40,
			"seed": 1426117001,
			"groupIds": [
				"YNcIDHFb7bNe-2gmfaU72"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(e.g Given the current word in a sentence, are there any nouns in front of it that give it contributes to?\nour adjective is the token and the key is the answer of what it affects)",
			"rawText": "(e.g Given the current word in a sentence, are there any nouns in front of it that give it contributes to?\nour adjective is the token and the key is the answer of what it affects)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(e.g Given the current word in a sentence, are there any nouns in front of it that give it contributes to?\nour adjective is the token and the key is the answer of what it affects)",
			"lineHeight": 1.25
		},
		{
			"id": "bxeKyKFS",
			"type": "text",
			"x": -685.8118538422834,
			"y": 2992.171902907855,
			"width": 973.681884765625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"YNcIDHFb7bNe-2gmfaU72"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1733290375,
			"version": 770,
			"versionNonce": 1920620361,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "(e.g Assuming our current token has an influence on our context token, what is the value that I need to add\nto the embedding of the context token in order for it to describe itself under the influence of the current token.\nanother lovely example from 3b1b: if our current context in the query is creature, and we determine that fluffy adjective\nis describing creature, then the Value vector of fluffy is a vector that moves in representation space towards fluffyness\nwhich if added to the vector of creature it would move it to a vector of fluffy creature)",
			"rawText": "(e.g Assuming our current token has an influence on our context token, what is the value that I need to add\nto the embedding of the context token in order for it to describe itself under the influence of the current token.\nanother lovely example from 3b1b: if our current context in the query is creature, and we determine that fluffy adjective\nis describing creature, then the Value vector of fluffy is a vector that moves in representation space towards fluffyness\nwhich if added to the vector of creature it would move it to a vector of fluffy creature)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(e.g Assuming our current token has an influence on our context token, what is the value that I need to add\nto the embedding of the context token in order for it to describe itself under the influence of the current token.\nanother lovely example from 3b1b: if our current context in the query is creature, and we determine that fluffy adjective\nis describing creature, then the Value vector of fluffy is a vector that moves in representation space towards fluffyness\nwhich if added to the vector of creature it would move it to a vector of fluffy creature)",
			"lineHeight": 1.25
		},
		{
			"id": "fv8gJqsk",
			"type": "text",
			"x": -88.1355750281947,
			"y": 2012.2250917120498,
			"width": 882.299072265625,
			"height": 200,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 161430535,
			"version": 637,
			"versionNonce": 1248878023,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "pUDIX69FkczCv1PJ5Ny_0",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "3) Dot Product:\nWe know that the dot product is a similarity measure for vectors\ngiving us a score of how strongly do they align in their space.\n\nSo computing a dot product between all the token vectors viewed as the current\ncontext (queries) and all the tokens' influence of other vectors being the context (keys)\nwe get a score matrix (size of 2x context window) that describes which tokens affect\nwhich tokens in front and behind them.",
			"rawText": "3) Dot Product:\nWe know that the dot product is a similarity measure for vectors\ngiving us a score of how strongly do they align in their space.\n\nSo computing a dot product between all the token vectors viewed as the current\ncontext (queries) and all the tokens' influence of other vectors being the context (keys)\nwe get a score matrix (size of 2x context window) that describes which tokens affect\nwhich tokens in front and behind them.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) Dot Product:\nWe know that the dot product is a similarity measure for vectors\ngiving us a score of how strongly do they align in their space.\n\nSo computing a dot product between all the token vectors viewed as the current\ncontext (queries) and all the tokens' influence of other vectors being the context (keys)\nwe get a score matrix (size of 2x context window) that describes which tokens affect\nwhich tokens in front and behind them.",
			"lineHeight": 1.25
		},
		{
			"id": "o4Y6uetZ",
			"type": "text",
			"x": 437.7131666148121,
			"y": 2338.809553933857,
			"width": 763.439208984375,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2006204839,
			"version": 483,
			"versionNonce": 430081577,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "pUDIX69FkczCv1PJ5Ny_0",
					"type": "arrow"
				},
				{
					"id": "rkF5144eGVlsvWES3fsj5",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "4) Scaling:\nThis score matrix then undergos several modifications\nto tune it to something we want.\nthe matrix is usually scaled down using the square root of the context size\nin order to prevent exploding gradients, because so far we have only been\nusing matrix multiplication to move forward (we need numerical stability)",
			"rawText": "4) Scaling:\nThis score matrix then undergos several modifications\nto tune it to something we want.\nthe matrix is usually scaled down using the square root of the context size\nin order to prevent exploding gradients, because so far we have only been\nusing matrix multiplication to move forward (we need numerical stability)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4) Scaling:\nThis score matrix then undergos several modifications\nto tune it to something we want.\nthe matrix is usually scaled down using the square root of the context size\nin order to prevent exploding gradients, because so far we have only been\nusing matrix multiplication to move forward (we need numerical stability)",
			"lineHeight": 1.25
		},
		{
			"id": "6Sb5GhUp_dh_qJX7E8qD6",
			"type": "arrow",
			"x": -735.0153220021505,
			"y": 2252.365825809583,
			"width": 138.38706510203133,
			"height": 201.74499852223835,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 242189641,
			"version": 143,
			"versionNonce": 743378151,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-66.69256149495482,
					100.03884224243211
				],
				[
					-50.019421121216055,
					201.74499852223835
				],
				[
					71.69450360707651,
					190.07380026062083
				]
			],
			"lastCommittedPoint": [
				71.69450360707651,
				190.07380026062083
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "lKLCO5ti",
				"focus": 0.631245657817065,
				"gap": 17.050346377514757
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "fKc0ZMD4MK67KQJ9jY1Kd",
			"type": "arrow",
			"x": 253.7019021605538,
			"y": 2454.1108243318213,
			"width": 131.71780895253573,
			"height": 183.40454411112614,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 799455337,
			"version": 92,
			"versionNonce": 1302452489,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					131.71780895253573,
					-31.67896671010385
				],
				[
					111.7100405040494,
					-183.40454411112614
				]
			],
			"lastCommittedPoint": [
				111.7100405040494,
				-183.40454411112614
			],
			"startBinding": {
				"elementId": "lKLCO5ti",
				"focus": -0.19322989774786864,
				"gap": 5.373253084363
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "pUDIX69FkczCv1PJ5Ny_0",
			"type": "arrow",
			"x": 797.2462783444334,
			"y": 2085.6344220721953,
			"width": 201.74499852223835,
			"height": 249.84110157412397,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 457197801,
			"version": 187,
			"versionNonce": 952817671,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					158.39483355051766,
					26.677024597981926
				],
				[
					201.74499852223835,
					161.72946162526523
				],
				[
					94.46477881336523,
					249.84110157412397
				]
			],
			"lastCommittedPoint": [
				126.71586684041426,
				266.77024597981926
			],
			"startBinding": {
				"elementId": "fv8gJqsk",
				"focus": -0.5818095353259308,
				"gap": 3.082781107003143
			},
			"endBinding": {
				"elementId": "o4Y6uetZ",
				"focus": -0.0488276336650556,
				"gap": 3.3340302875376437
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "rkF5144eGVlsvWES3fsj5",
			"type": "arrow",
			"x": 607.4642344750563,
			"y": 2513.075092010023,
			"width": 71.11996982865458,
			"height": 113.79734002428586,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1751904265,
			"version": 607,
			"versionNonce": 804507625,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-71.11996982865458,
					51.0992260368339
				],
				[
					-66.12849159702205,
					113.79734002428586
				]
			],
			"lastCommittedPoint": [
				-61.47410613827742,
				199.50087275063606
			],
			"startBinding": {
				"elementId": "o4Y6uetZ",
				"focus": 0.15184101303094985,
				"gap": 24.265538076166195
			},
			"endBinding": {
				"elementId": "U2LcnvxM",
				"focus": -0.053081611352307684,
				"gap": 18.37484405604846
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "U2LcnvxM",
			"type": "text",
			"x": 250.55806551189994,
			"y": 2645.2472760903574,
			"width": 632.7393798828125,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1884319655,
			"version": 563,
			"versionNonce": 1440759591,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VJq7FhnIPCv64NA4OgNa5",
					"type": "arrow"
				},
				{
					"id": "rkF5144eGVlsvWES3fsj5",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "5) Masking:\nSince we take all of the tokens together and perform\nthese operations on them, we will end up with a matrix \nmultiplication that shows each words effect on the ones\nin front and behind it, this is sometimes unwanted as we do not\nwant to see its effect on future words, thus we mask the\nlower triangle of the matrix and set it to -infinity score",
			"rawText": "5) Masking:\nSince we take all of the tokens together and perform\nthese operations on them, we will end up with a matrix \nmultiplication that shows each words effect on the ones\nin front and behind it, this is sometimes unwanted as we do not\nwant to see its effect on future words, thus we mask the\nlower triangle of the matrix and set it to -infinity score",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "5) Masking:\nSince we take all of the tokens together and perform\nthese operations on them, we will end up with a matrix \nmultiplication that shows each words effect on the ones\nin front and behind it, this is sometimes unwanted as we do not\nwant to see its effect on future words, thus we mask the\nlower triangle of the matrix and set it to -infinity score",
			"lineHeight": 1.25
		},
		{
			"id": "VJq7FhnIPCv64NA4OgNa5",
			"type": "arrow",
			"x": 642.6834253626637,
			"y": 2834.6857069874895,
			"width": 230.13230035227957,
			"height": 63.65774433879005,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1549844201,
			"version": 453,
			"versionNonce": 648276681,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.889212212294183,
					39.29901760851362
				],
				[
					221.1225028752607,
					22.13484123745684
				],
				[
					230.13230035227957,
					63.65774433879005
				]
			],
			"lastCommittedPoint": [
				379.06726136751263,
				-155.55349769264467
			],
			"startBinding": {
				"elementId": "U2LcnvxM",
				"focus": -0.002152451145432895,
				"gap": 14.438430897132093
			},
			"endBinding": {
				"elementId": "plxSKVCT",
				"focus": 0.05778161163565462,
				"gap": 9.817198146975898
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "plxSKVCT",
			"type": "text",
			"x": 453.79053619245997,
			"y": 2908.1606494732555,
			"width": 820.4590454101562,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1281742503,
			"version": 409,
			"versionNonce": 1979433543,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VJq7FhnIPCv64NA4OgNa5",
					"type": "arrow"
				},
				{
					"id": "WRYh0huijV594psUp-P2M",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "6) Softmax:\nThis is quite a simple operation, we want to to turn our matrix\nof score of attention, into a probability distribution (or weights that sum up to 1)\nin order to properly quantify a linear combination of other tokens as the influence\non ours",
			"rawText": "6) Softmax:\nThis is quite a simple operation, we want to to turn our matrix\nof score of attention, into a probability distribution (or weights that sum up to 1)\nin order to properly quantify a linear combination of other tokens as the influence\non ours",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "6) Softmax:\nThis is quite a simple operation, we want to to turn our matrix\nof score of attention, into a probability distribution (or weights that sum up to 1)\nin order to properly quantify a linear combination of other tokens as the influence\non ours",
			"lineHeight": 1.25
		},
		{
			"id": "fzoa3pRs",
			"type": "text",
			"x": 865.0839553880232,
			"y": 2557.963972583832,
			"width": 743.6791381835938,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2062027559,
			"version": 428,
			"versionNonce": 1032035273,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "WRYh0huijV594psUp-P2M",
					"type": "arrow"
				}
			],
			"updated": 1714139456450,
			"link": null,
			"locked": false,
			"text": "7) Multiply by values:\n\nNow that we have the weights, all we need to do is multiply\nthem with the displacement vector in order to get the overall displacement\nthat our sentence has on our current context token",
			"rawText": "7) Multiply by values:\n\nNow that we have the weights, all we need to do is multiply\nthem with the displacement vector in order to get the overall displacement\nthat our sentence has on our current context token",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "7) Multiply by values:\n\nNow that we have the weights, all we need to do is multiply\nthem with the displacement vector in order to get the overall displacement\nthat our sentence has on our current context token",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 847,
			"versionNonce": 167371111,
			"isDeleted": false,
			"id": "3SFwz0-flEYgH9RLJxKy5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.132069131996179,
			"x": -1360.8737905809653,
			"y": 1713.3112703040645,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 1594076105,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "qQqzSlAO",
			"type": "text",
			"x": -1882.6804647766749,
			"y": 1588.3354017878114,
			"width": 218.9329071044922,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 612436041,
			"version": 123,
			"versionNonce": 337415305,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Cross Attention",
			"rawText": "Cross Attention",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cross Attention",
			"lineHeight": 1.25
		},
		{
			"id": "bb3UxKUA",
			"type": "text",
			"x": -2208.1439155927887,
			"y": 1643.7750350931358,
			"width": 835.2391357421875,
			"height": 250,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 473524551,
			"version": 666,
			"versionNonce": 858201223,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Everything described in self attention is modeled such that the stream of tokens is\ninfluencing itself so we need the model to look at itself to figure out what to pay\nattention to!\n\nCross attention is also identical to self-attention, except the query and key\nwork on completely different datasets, for example a sentence in english and\nin spanish, or even text and speech.\n\nAlso there is no masking in cross attention as there is no \"future prediction\"\npart of it, its two different modalities affect each other equally",
			"rawText": "Everything described in self attention is modeled such that the stream of tokens is\ninfluencing itself so we need the model to look at itself to figure out what to pay\nattention to!\n\nCross attention is also identical to self-attention, except the query and key\nwork on completely different datasets, for example a sentence in english and\nin spanish, or even text and speech.\n\nAlso there is no masking in cross attention as there is no \"future prediction\"\npart of it, its two different modalities affect each other equally",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Everything described in self attention is modeled such that the stream of tokens is\ninfluencing itself so we need the model to look at itself to figure out what to pay\nattention to!\n\nCross attention is also identical to self-attention, except the query and key\nwork on completely different datasets, for example a sentence in english and\nin spanish, or even text and speech.\n\nAlso there is no masking in cross attention as there is no \"future prediction\"\npart of it, its two different modalities affect each other equally",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1157,
			"versionNonce": 1271665513,
			"isDeleted": false,
			"id": "WB_3YvcR5H0bu-RF_yVdA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.019099722972755195,
			"x": 1167.96144373768,
			"y": 1616.338353239786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 1157042151,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "mhXcVVyd",
			"type": "text",
			"x": 1875.192243538132,
			"y": 1440.4192563252327,
			"width": 318.02532958984375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 194911049,
			"version": 321,
			"versionNonce": 893383591,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Multi-Headed attention",
			"rawText": "Multi-Headed attention",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multi-Headed attention",
			"lineHeight": 1.25
		},
		{
			"id": "BxIBgKAf",
			"type": "text",
			"x": 1498.372916290543,
			"y": 1491.2669219975237,
			"width": 1038.43896484375,
			"height": 225,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1620845641,
			"version": 942,
			"versionNonce": 900185673,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Multi-headed attention is compromised of many Attention heads that do not share\ntheir learnable parameters but are instead set out to figure out their own patterns in the\ntokens.\nthis is necessary because in such complicated tasks we often have MANY different ways a token\ncan influence another.\nfor example in words, on attention head can discover that adjectives describe nouns, while another head\ncan describe how nouns affect other nouns, anothe head can discover how certain words can describe\nthe tone of the sentence or turn the sentence into a question... and these are merely just logical\npattern we draw, there are many more hidden patterns that the model learn within itself!",
			"rawText": "Multi-headed attention is compromised of many Attention heads that do not share\ntheir learnable parameters but are instead set out to figure out their own patterns in the\ntokens.\nthis is necessary because in such complicated tasks we often have MANY different ways a token\ncan influence another.\nfor example in words, on attention head can discover that adjectives describe nouns, while another head\ncan describe how nouns affect other nouns, anothe head can discover how certain words can describe\nthe tone of the sentence or turn the sentence into a question... and these are merely just logical\npattern we draw, there are many more hidden patterns that the model learn within itself!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multi-headed attention is compromised of many Attention heads that do not share\ntheir learnable parameters but are instead set out to figure out their own patterns in the\ntokens.\nthis is necessary because in such complicated tasks we often have MANY different ways a token\ncan influence another.\nfor example in words, on attention head can discover that adjectives describe nouns, while another head\ncan describe how nouns affect other nouns, anothe head can discover how certain words can describe\nthe tone of the sentence or turn the sentence into a question... and these are merely just logical\npattern we draw, there are many more hidden patterns that the model learn within itself!",
			"lineHeight": 1.25
		},
		{
			"id": "jp3-_JFLBxzlbFXDYIe1r",
			"type": "rectangle",
			"x": 1582.6438166528978,
			"y": 1862.3009045147273,
			"width": 74.83228083903987,
			"height": 241.12623825912897,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 370519175,
			"version": 280,
			"versionNonce": 678487751,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "8xAmZLJpliKj7hlg708vo",
					"type": "arrow"
				},
				{
					"id": "vDPvHMZzhsSRHT7UhMXc2",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"id": "3QeyZ19w",
			"type": "text",
			"x": 1546.8396506759332,
			"y": 1958.1166162006562,
			"width": 146.44061279296875,
			"height": 35,
			"angle": 1.554582586046977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 482441639,
			"version": 350,
			"versionNonce": 9112873,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Embeddings",
			"rawText": "Embeddings",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Embeddings",
			"lineHeight": 1.25
		},
		{
			"id": "8xAmZLJpliKj7hlg708vo",
			"type": "arrow",
			"x": 1659.5547719596898,
			"y": 1989.1420693909417,
			"width": 267.109669106017,
			"height": 115.80199154051752,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 779277993,
			"version": 1014,
			"versionNonce": 1800828391,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					136.1531776376969,
					-13.55340638377811
				],
				[
					146.5465499764523,
					-108.13309466645387
				],
				[
					267.109669106017,
					-115.80199154051752
				]
			],
			"lastCommittedPoint": [
				268.1490063398933,
				-113.28775849243584
			],
			"startBinding": {
				"elementId": "jp3-_JFLBxzlbFXDYIe1r",
				"focus": 0.08214462588842443,
				"gap": 2.07867446775208
			},
			"endBinding": {
				"elementId": "H-xBi6Q-o5bTklOPXExfO",
				"focus": 0.6363720720022613,
				"gap": 4.055978108524414
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Fecslt4qX7ac-kjxsWq9E",
			"type": "arrow",
			"x": 1654.3580857903112,
			"y": 1988.0607098136697,
			"width": 273.345692509271,
			"height": 3.511515531115492,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 383400039,
			"version": 640,
			"versionNonce": 1944158217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					273.345692509271,
					3.511515531115492
				]
			],
			"lastCommittedPoint": [
				273.345692509271,
				0
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "H-xBi6Q-o5bTklOPXExfO",
				"focus": -0.03188287799848604,
				"gap": 3.016640874649056
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "vDPvHMZzhsSRHT7UhMXc2",
			"type": "arrow",
			"x": 1657.4760974919386,
			"y": 1986.4841351833325,
			"width": 270.1252019516528,
			"height": 113.13081724453559,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1707480265,
			"version": 1078,
			"versionNonce": 1425875207,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					143.42853827482622,
					14.04862143684386
				],
				[
					148.62522444420392,
					105.51029801789355
				],
				[
					270.1252019516528,
					113.13081724453559
				]
			],
			"lastCommittedPoint": [
				271.26701804152026,
				142.38920104095132
			],
			"startBinding": {
				"elementId": "jp3-_JFLBxzlbFXDYIe1r",
				"focus": -0.0003601944442048512,
				"gap": 1
			},
			"endBinding": {
				"elementId": "H-xBi6Q-o5bTklOPXExfO",
				"focus": -0.618116290719118,
				"gap": 3.1191197306397953
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "H-xBi6Q-o5bTklOPXExfO",
			"type": "rectangle",
			"x": 1930.7204191742312,
			"y": 1799.4805720417921,
			"width": 428.61504385560886,
			"height": 377.55392628749723,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 2078817097,
			"version": 471,
			"versionNonce": 1952418281,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "8xAmZLJpliKj7hlg708vo",
					"type": "arrow"
				},
				{
					"id": "Fecslt4qX7ac-kjxsWq9E",
					"type": "arrow"
				},
				{
					"id": "vDPvHMZzhsSRHT7UhMXc2",
					"type": "arrow"
				},
				{
					"id": "tTJ7BOLY9OjGz_Yv4nBtZ",
					"type": "arrow"
				}
			],
			"updated": 1714139359222,
			"link": null,
			"locked": false
		},
		{
			"id": "P3cwXDv5",
			"type": "text",
			"x": 2176.464694181337,
			"y": 1807.344339350249,
			"width": 173.18072509765625,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 591696521,
			"version": 361,
			"versionNonce": 652306471,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467361,
			"link": null,
			"locked": false,
			"text": "Multi-headed\nattention",
			"rawText": "Multi-headed\nattention",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multi-headed\nattention",
			"lineHeight": 1.25
		},
		{
			"id": "4kAAcj3u_pUJ51r8xNQTJ",
			"type": "rectangle",
			"x": 1950.7173152959126,
			"y": 1836.3743523146013,
			"width": 173.31879990865264,
			"height": 72.13809509711518,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1598216297,
			"version": 350,
			"versionNonce": 1080414665,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "6wRqHtln"
				},
				{
					"id": "EJODOkKPQ_9kLFXMfA3Cd",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"id": "6wRqHtln",
			"type": "text",
			"x": 1962.9867921545358,
			"y": 1859.943399863159,
			"width": 148.77984619140625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 152433639,
			"version": 263,
			"versionNonce": 671326569,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467756,
			"link": null,
			"locked": false,
			"text": "Attention Head",
			"rawText": "Attention Head",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "4kAAcj3u_pUJ51r8xNQTJ",
			"originalText": "Attention Head",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 353,
			"versionNonce": 1094365353,
			"isDeleted": false,
			"id": "5PmkGJlxk4jl6Saw_cBxt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1954.8497076975805,
			"y": 1953.215009846895,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"width": 173.31879990865264,
			"height": 72.13809509711518,
			"seed": 2136295079,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "qLDhNak5"
				},
				{
					"id": "n5snQpfo--ulPHAE22-4i",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"id": "qLDhNak5",
			"type": "text",
			"x": 1967.1191845562037,
			"y": 1976.7840573954527,
			"width": 148.77984619140625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 56171335,
			"version": 241,
			"versionNonce": 1656167209,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467756,
			"link": null,
			"locked": false,
			"text": "Attention Head",
			"rawText": "Attention Head",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "5PmkGJlxk4jl6Saw_cBxt",
			"originalText": "Attention Head",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 334,
			"versionNonce": 1439740809,
			"isDeleted": false,
			"id": "y_057qa1Guk5hFu_Pa5xU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1951.8465524827484,
			"y": 2067.742487006919,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"width": 173.31879990865264,
			"height": 72.13809509711518,
			"seed": 1359954343,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "1XOO1rmz"
				},
				{
					"id": "zRqCHgCjPjbJoBTXdJj_F",
					"type": "arrow"
				}
			],
			"updated": 1714137467361,
			"link": null,
			"locked": false
		},
		{
			"id": "1XOO1rmz",
			"type": "text",
			"x": 1964.1160293413716,
			"y": 2091.3115345554766,
			"width": 148.77984619140625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 751024647,
			"version": 257,
			"versionNonce": 849814761,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467757,
			"link": null,
			"locked": false,
			"text": "Attention Head",
			"rawText": "Attention Head",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "y_057qa1Guk5hFu_Pa5xU",
			"originalText": "Attention Head",
			"lineHeight": 1.25
		},
		{
			"id": "EJODOkKPQ_9kLFXMfA3Cd",
			"type": "arrow",
			"x": 2126.415573789723,
			"y": 1866.513908351038,
			"width": 149.74179043477443,
			"height": 97.88161805763366,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1664112615,
			"version": 733,
			"versionNonce": 1826280007,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714138954962,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					65.92927237199046,
					4.661665723271653
				],
				[
					67.26117686435418,
					86.57379200362402
				],
				[
					149.74179043477443,
					97.88161805763366
				]
			],
			"lastCommittedPoint": [
				146.50949415998002,
				103.88855040434919
			],
			"startBinding": {
				"elementId": "4kAAcj3u_pUJ51r8xNQTJ",
				"gap": 2.379458585157863,
				"focus": -0.28972010026972256
			},
			"endBinding": {
				"elementId": "1RE7jy8_sUfHIJVYBP5N6",
				"gap": 1,
				"focus": 0.394261032359869
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "n5snQpfo--ulPHAE22-4i",
			"type": "arrow",
			"x": 2130.4112872668134,
			"y": 1989.0491216484756,
			"width": 143.84568517525304,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1660219783,
			"version": 394,
			"versionNonce": 1093527559,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714138954961,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					143.84568517525304,
					0
				]
			],
			"lastCommittedPoint": [
				143.84568517525304,
				0
			],
			"startBinding": {
				"elementId": "5PmkGJlxk4jl6Saw_cBxt",
				"gap": 2.242779660580254,
				"focus": -0.0065135001599574815
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "zRqCHgCjPjbJoBTXdJj_F",
			"type": "arrow",
			"x": 2127.0815260359045,
			"y": 2104.2588602379146,
			"width": 149.17334208566763,
			"height": 95.23117831494528,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 72497863,
			"version": 752,
			"versionNonce": 1920397671,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714138954962,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					70.59093809526348,
					-5.327617969453968
				],
				[
					72.5887948338086,
					-81.24617403417051
				],
				[
					149.17334208566763,
					-95.23117831494528
				]
			],
			"lastCommittedPoint": [
				148.50735089852515,
				-93.89926671162357
			],
			"startBinding": {
				"elementId": "y_057qa1Guk5hFu_Pa5xU",
				"gap": 1.9161736445034876,
				"focus": 0.16738743198805192
			},
			"endBinding": {
				"elementId": "1RE7jy8_sUfHIJVYBP5N6",
				"gap": 3.1387434322242314,
				"focus": -0.4545612671832455
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "1RE7jy8_sUfHIJVYBP5N6",
			"type": "ellipse",
			"x": 2271.593163457341,
			"y": 1945.6786384499255,
			"width": 78.5823650494444,
			"height": 78,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1428145543,
			"version": 390,
			"versionNonce": 35954633,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "Lsl6gMFO"
				},
				{
					"id": "EJODOkKPQ_9kLFXMfA3Cd",
					"type": "arrow"
				},
				{
					"id": "zRqCHgCjPjbJoBTXdJj_F",
					"type": "arrow"
				}
			],
			"updated": 1714137467757,
			"link": null,
			"locked": false
		},
		{
			"id": "Lsl6gMFO",
			"type": "text",
			"x": 2299.851276748599,
			"y": 1962.10147398365,
			"width": 22.500015258789062,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 564396039,
			"version": 277,
			"versionNonce": 1403840617,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467758,
			"link": null,
			"locked": false,
			"text": "+",
			"rawText": "+",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "1RE7jy8_sUfHIJVYBP5N6",
			"originalText": "+",
			"lineHeight": 1.25
		},
		{
			"id": "cI7mwOPl",
			"type": "text",
			"x": 1615.0847763941124,
			"y": 2195.9188211967053,
			"width": 762.9992065429688,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1631138791,
			"version": 459,
			"versionNonce": 228908775,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467362,
			"link": null,
			"locked": false,
			"text": "The Output of each attention Head gets concatenated together\nBut then theyre also Projected down into the appropriate dimensionality\nusing another Matrix of learnable parameters (Linear Layer Projection head)",
			"rawText": "The Output of each attention Head gets concatenated together\nBut then theyre also Projected down into the appropriate dimensionality\nusing another Matrix of learnable parameters (Linear Layer Projection head)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Output of each attention Head gets concatenated together\nBut then theyre also Projected down into the appropriate dimensionality\nusing another Matrix of learnable parameters (Linear Layer Projection head)",
			"lineHeight": 1.25
		},
		{
			"id": "sTUE0Yi7wQI6uLJUT6-nX",
			"type": "image",
			"x": 1816.5418744306407,
			"y": 2283.2525226808493,
			"width": 380,
			"height": 67,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2001084007,
			"version": 213,
			"versionNonce": 852109065,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137467362,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "196e33fe1cd528a6f0c33048e507a48555138a1d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "WRYh0huijV594psUp-P2M",
			"type": "arrow",
			"x": 1069.1693625647529,
			"y": 2899.6954224451424,
			"width": 191.81139977960788,
			"height": 195.16561018118318,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2070635495,
			"version": 126,
			"versionNonce": 1233386889,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714139456466,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					168.11077573245598,
					-24.722172901831527
				],
				[
					191.81139977960788,
					-195.16561018118318
				]
			],
			"lastCommittedPoint": [
				243.92543929807357,
				-130.2034439496474
			],
			"startBinding": {
				"elementId": "plxSKVCT",
				"focus": -0.33214132472890695,
				"gap": 8.465227028113077
			},
			"endBinding": {
				"elementId": "fzoa3pRs",
				"focus": -0.09393947271468288,
				"gap": 21.565839680127283
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "line",
			"version": 1267,
			"versionNonce": 1344318985,
			"isDeleted": false,
			"id": "vrmusJpV5X27tkClvzjy5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5351517161967836,
			"x": 1972.5637757273826,
			"y": 2522.1574163457803,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 718640999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714137706474,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "RHNKaaK0",
			"type": "text",
			"x": 1877.8347108459525,
			"y": 2727.940151216955,
			"width": 421.7937316894531,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1299794503,
			"version": 275,
			"versionNonce": 1685023145,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137712804,
			"link": "[[CNN]]",
			"locked": false,
			"text": "Skip-Connection & Linear Layer",
			"rawText": "Skip-Connection & Linear Layer",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Skip-Connection & Linear Layer",
			"lineHeight": 1.25
		},
		{
			"id": "3wnzmzdz",
			"type": "text",
			"x": 1607.9654838447696,
			"y": 2797.8982128672533,
			"width": 945.0390014648438,
			"height": 275,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1765294729,
			"version": 960,
			"versionNonce": 67521673,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137712804,
			"link": null,
			"locked": false,
			"text": "As described in the explanation of why Resnets are beneficial for very large/deep\nmodels, We introduce the Skip-connections here for better information AND gradient\nflow in the transformer block, alongside a Normalization Layer.\n\nFor further processing and a more rich representation, We then send the output of\nwhat we have into a few Layers called the feed forward network, this is just\na standard Neural network architecture, its not too special but it is necessary\nto learn as much as possible about the data.\n\nWe also require to introduce the skip connection and batch normalization afterwards of course\nbecause it is treated as a block in a resnet.",
			"rawText": "As described in the explanation of why Resnets are beneficial for very large/deep\nmodels, We introduce the Skip-connections here for better information AND gradient\nflow in the transformer block, alongside a Normalization Layer.\n\nFor further processing and a more rich representation, We then send the output of\nwhat we have into a few Layers called the feed forward network, this is just\na standard Neural network architecture, its not too special but it is necessary\nto learn as much as possible about the data.\n\nWe also require to introduce the skip connection and batch normalization afterwards of course\nbecause it is treated as a block in a resnet.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "As described in the explanation of why Resnets are beneficial for very large/deep\nmodels, We introduce the Skip-connections here for better information AND gradient\nflow in the transformer block, alongside a Normalization Layer.\n\nFor further processing and a more rich representation, We then send the output of\nwhat we have into a few Layers called the feed forward network, this is just\na standard Neural network architecture, its not too special but it is necessary\nto learn as much as possible about the data.\n\nWe also require to introduce the skip connection and batch normalization afterwards of course\nbecause it is treated as a block in a resnet.",
			"lineHeight": 1.25
		},
		{
			"id": "HfA_rCgIqclQUybWcd6N9",
			"type": "line",
			"x": 2939.713612230349,
			"y": 2828.4782892632406,
			"width": 668.5714285714284,
			"height": 662.8571428571427,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 91432647,
			"version": 1241,
			"versionNonce": 1286091655,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714137809880,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					398.5714285714289,
					74.28571428571422
				],
				[
					374.2857142857143,
					-375.71428571428584
				],
				[
					255.71428571428606,
					-370.0000000000006
				],
				[
					458.57142857142844,
					-475.7142857142858
				],
				[
					668.5714285714284,
					-371.42857142857156
				],
				[
					551.4285714285711,
					-372.8571428571431
				],
				[
					501.42857142857156,
					165.7142857142859
				],
				[
					1.4285714285715727,
					187.14285714285688
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				1.4285714285715585,
				-7.142857142857338
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "1vrskXsk",
			"type": "text",
			"x": 3338.6685209986645,
			"y": 1762.718733458262,
			"width": 110.01248168945312,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 433332007,
			"version": 123,
			"versionNonce": 1688568647,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714138446962,
			"link": null,
			"locked": false,
			"text": "Decoder",
			"rawText": "Decoder",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Decoder",
			"lineHeight": 1.25
		},
		{
			"id": "P4PzIO9X",
			"type": "text",
			"x": 2890.8152647730785,
			"y": 1813.5663994582621,
			"width": 1005.718994140625,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 245468617,
			"version": 705,
			"versionNonce": 1606648423,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714138446962,
			"link": null,
			"locked": false,
			"text": "The transformer we have described so far is just an Encoder part of the entire mechanism\nObviously if we are using our model for any sort of task that does not require generation of\nsomething, we do not need the Decoder part.\nBut usually in such complicated task we have another Transformer attached called the decoder and\nit follows the exact same architecture but for a different purpose",
			"rawText": "The transformer we have described so far is just an Encoder part of the entire mechanism\nObviously if we are using our model for any sort of task that does not require generation of\nsomething, we do not need the Decoder part.\nBut usually in such complicated task we have another Transformer attached called the decoder and\nit follows the exact same architecture but for a different purpose",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The transformer we have described so far is just an Encoder part of the entire mechanism\nObviously if we are using our model for any sort of task that does not require generation of\nsomething, we do not need the Decoder part.\nBut usually in such complicated task we have another Transformer attached called the decoder and\nit follows the exact same architecture but for a different purpose",
			"lineHeight": 1.25
		},
		{
			"id": "zdf_a1VDJzs9esonIcj3l",
			"type": "image",
			"x": 3899.0072630239993,
			"y": 1818.5240750840912,
			"width": 414.8276625417274,
			"height": 647.733696538619,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1922392839,
			"version": 168,
			"versionNonce": 1407635271,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714138274246,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a7196e83173a6671a2aa260fa230f944509cf6ed",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "uLEdLjKuoDZk9LugLf4TS",
			"type": "arrow",
			"x": 3965.1859951804618,
			"y": 2051.775990956365,
			"width": 13.8352750152883,
			"height": 84.85635342710162,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1945513639,
			"version": 140,
			"versionNonce": 995351913,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714138274497,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.53411000611532,
					-51.651693390409704
				],
				[
					-8.30116500917298,
					-84.85635342710162
				]
			],
			"lastCommittedPoint": [
				-12,
				-122.66666666666674
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "YXJnDDrD",
				"focus": 0.15854790759182516,
				"gap": 6.648507201079951
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "YXJnDDrD",
			"type": "text",
			"x": 3929.295461600193,
			"y": 1942.9770365590734,
			"width": 51.78538202705742,
			"height": 17.294093769110376,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 904704201,
			"version": 67,
			"versionNonce": 1903356295,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "uLEdLjKuoDZk9LugLf4TS",
					"type": "arrow"
				}
			],
			"updated": 1714138274246,
			"link": null,
			"locked": false,
			"text": "Encoder",
			"rawText": "Encoder",
			"fontSize": 13.8352750152883,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Encoder",
			"lineHeight": 1.25
		},
		{
			"id": "rWP9MR6VKzHo7McjNEbba",
			"type": "arrow",
			"x": 4259.471182430681,
			"y": 1994.7139205913518,
			"width": 142.05720700388326,
			"height": 50.859987692748255,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 972123753,
			"version": 87,
			"versionNonce": 900089929,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714138274497,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					66.64412180429072,
					-14.907237772012405
				],
				[
					142.05720700388326,
					35.95274992073585
				]
			],
			"lastCommittedPoint": [
				205.35508957632828,
				51.97258439894722
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "Fb2ylH55",
				"focus": 0.5677189975340484,
				"gap": 11.399652413892113
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Fb2ylH55",
			"type": "text",
			"x": 4381.364188138637,
			"y": 2042.0663229259796,
			"width": 54.35874402433922,
			"height": 17.294093769110376,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 838210983,
			"version": 66,
			"versionNonce": 330916583,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rWP9MR6VKzHo7McjNEbba",
					"type": "arrow"
				}
			],
			"updated": 1714138274246,
			"link": null,
			"locked": false,
			"text": "Decoder",
			"rawText": "Decoder",
			"fontSize": 13.8352750152883,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Decoder",
			"lineHeight": 1.25
		},
		{
			"id": "W2I9XbP2wUuj3KdOqDK2O",
			"type": "arrow",
			"x": 4230.533603226185,
			"y": 2408.6089928495794,
			"width": 75.41308519959193,
			"height": 29.81447554402481,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1987601351,
			"version": 118,
			"versionNonce": 1411929897,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714138274498,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					67.52101814382046,
					2.6306890185904894
				],
				[
					75.41308519959193,
					29.81447554402481
				]
			],
			"lastCommittedPoint": [
				109.01566483681563,
				43.099216330834224
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "3LyT64MN",
				"focus": 0.050014743424080244,
				"gap": 7.892067055771577
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "3LyT64MN",
			"type": "text",
			"x": 4235.088467627136,
			"y": 2446.3155354493756,
			"width": 157.5005757088242,
			"height": 69.1763750764415,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1402018697,
			"version": 91,
			"versionNonce": 1732106311,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "W2I9XbP2wUuj3KdOqDK2O",
					"type": "arrow"
				}
			],
			"updated": 1714138274246,
			"link": null,
			"locked": false,
			"text": "embedding and\npositional encoding of\noutput token (partially\nmasked)",
			"rawText": "embedding and\npositional encoding of\noutput token (partially\nmasked)",
			"fontSize": 13.8352750152883,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "embedding and\npositional encoding of\noutput token (partially\nmasked)",
			"lineHeight": 1.25
		},
		{
			"id": "ikY78YSx",
			"type": "text",
			"x": 2851.934514973756,
			"y": 1967.882663544085,
			"width": 1054.2589111328125,
			"height": 325,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1311392103,
			"version": 1054,
			"versionNonce": 2009323463,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714138715024,
			"link": null,
			"locked": false,
			"text": "The Decoder is auto-regressive which means it takes\nas its input the previous tokens it has generated, runs it through a multi-headed attention head\nto see its effects, then takes in the input sequence interpreted by the encoder and combines\nthat information in the same architecture.\nThe decoder stops its process only when it has generated a token that marks the end of of a sequence.\n\nThe decoder is ended with a softmax function that gives a probability distribution of the best\nnext possible token which is then sampled and outputted and the decoding process begins again\nwith that token included. \n\nAnd just to be fully clear, the Encoder Transformer and Decoder Transformer can be stacked\non top of each other, each Decoder taking from its matching encoder to get a lot more nuanced\nand rich representation",
			"rawText": "The Decoder is auto-regressive which means it takes\nas its input the previous tokens it has generated, runs it through a multi-headed attention head\nto see its effects, then takes in the input sequence interpreted by the encoder and combines\nthat information in the same architecture.\nThe decoder stops its process only when it has generated a token that marks the end of of a sequence.\n\nThe decoder is ended with a softmax function that gives a probability distribution of the best\nnext possible token which is then sampled and outputted and the decoding process begins again\nwith that token included. \n\nAnd just to be fully clear, the Encoder Transformer and Decoder Transformer can be stacked\non top of each other, each Decoder taking from its matching encoder to get a lot more nuanced\nand rich representation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Decoder is auto-regressive which means it takes\nas its input the previous tokens it has generated, runs it through a multi-headed attention head\nto see its effects, then takes in the input sequence interpreted by the encoder and combines\nthat information in the same architecture.\nThe decoder stops its process only when it has generated a token that marks the end of of a sequence.\n\nThe decoder is ended with a softmax function that gives a probability distribution of the best\nnext possible token which is then sampled and outputted and the decoding process begins again\nwith that token included. \n\nAnd just to be fully clear, the Encoder Transformer and Decoder Transformer can be stacked\non top of each other, each Decoder taking from its matching encoder to get a lot more nuanced\nand rich representation",
			"lineHeight": 1.25
		},
		{
			"id": "4XhjSBRXiv_5eH2kATCtt",
			"type": "image",
			"x": 891.6267696670142,
			"y": 1734.6437758745396,
			"width": 269,
			"height": 76,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 60519913,
			"version": 71,
			"versionNonce": 1047925863,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "MjKuWYIIdunrHyz3ufQyq",
					"type": "arrow"
				}
			],
			"updated": 1714139472045,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6cd5127e4521ae573c886b5533dbcf8ba9b3148e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "MjKuWYIIdunrHyz3ufQyq",
			"type": "arrow",
			"x": 1039.1057873164896,
			"y": 1821.7571211780526,
			"width": 77.81068425227704,
			"height": 96.08988000432305,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2138285897,
			"version": 103,
			"versionNonce": 262467463,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714139472045,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					65.28800568419115,
					37.896256070277104
				],
				[
					77.81068425227704,
					96.08988000432305
				]
			],
			"lastCommittedPoint": [
				62.61339284042924,
				67.76978989787631
			],
			"startBinding": {
				"elementId": "4XhjSBRXiv_5eH2kATCtt",
				"focus": 0.3582290231897931,
				"gap": 11.113345303512915
			},
			"endBinding": {
				"elementId": "jvHYqTNu",
				"focus": -0.1864533601981645,
				"gap": 21.841727736735038
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "jvHYqTNu",
			"type": "text",
			"x": 982.2572983485977,
			"y": 1939.6887289191106,
			"width": 373.9796142578125,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1972178471,
			"version": 195,
			"versionNonce": 1187632583,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "MjKuWYIIdunrHyz3ufQyq",
					"type": "arrow"
				}
			],
			"updated": 1714139467428,
			"link": null,
			"locked": false,
			"text": "Since this uses quadratic complexity\nit can be rewritten in ways that has\nlinear complexity and constant memory\nusing an appropriate kernel function",
			"rawText": "Since this uses quadratic complexity\nit can be rewritten in ways that has\nlinear complexity and constant memory\nusing an appropriate kernel function",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since this uses quadratic complexity\nit can be rewritten in ways that has\nlinear complexity and constant memory\nusing an appropriate kernel function",
			"lineHeight": 1.25
		},
		{
			"id": "_Mb3bSiXwqnJMq3d58eVF",
			"type": "image",
			"x": 1028.7306819631735,
			"y": 2048.711888957939,
			"width": 253.99999999999997,
			"height": 92,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1042003625,
			"version": 59,
			"versionNonce": 1716857703,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139468861,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c91d565a026d52c1f808aa1824172ddbd33fc3c0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Bz2eGNu5",
			"type": "text",
			"x": 1953.3375108852451,
			"y": 3421.9433168287605,
			"width": 252.2810516357422,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1590846119,
			"version": 285,
			"versionNonce": 1803453353,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714138981948,
			"link": null,
			"locked": false,
			"text": "Vision Transformer\n(Convolution-free)",
			"rawText": "Vision Transformer\n(Convolution-free)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vision Transformer\n(Convolution-free)",
			"lineHeight": 1.25
		},
		{
			"id": "KtFNemF9",
			"type": "text",
			"x": 1739.2784212246006,
			"y": 3523.9502269062577,
			"width": 680.3992309570312,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 110367495,
			"version": 291,
			"versionNonce": 613152295,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139024464,
			"link": null,
			"locked": false,
			"text": "Main Idea:\nInstead of using convolutional layers represent an image as\na sequence of image patches (tokens) which helps the transformer\naggregate global information early due to self-attention (instead of\nonly building them in later layers as CNNs)",
			"rawText": "Main Idea:\nInstead of using convolutional layers represent an image as\na sequence of image patches (tokens) which helps the transformer\naggregate global information early due to self-attention (instead of\nonly building them in later layers as CNNs)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Main Idea:\nInstead of using convolutional layers represent an image as\na sequence of image patches (tokens) which helps the transformer\naggregate global information early due to self-attention (instead of\nonly building them in later layers as CNNs)",
			"lineHeight": 1.25
		},
		{
			"id": "sI4DP4itXPhl4leuWppN_",
			"type": "image",
			"x": 1822.6761693823446,
			"y": 3672.991854384889,
			"width": 521,
			"height": 344,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 538574153,
			"version": 320,
			"versionNonce": 473324489,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139034973,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "20f361f535c516198fa0b297aa3c2054e1a2b2e5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 743,
			"versionNonce": 1646816073,
			"isDeleted": false,
			"id": "84cmwkykbt5UOJEoHJwAn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948966,
			"x": 1962.4721971379572,
			"y": 3223.081503309827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 180671081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714138978417,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "T3zk3vRJ",
			"type": "text",
			"x": 1605.0169927812335,
			"y": 4046.2303008032018,
			"width": 955.4389038085938,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 713473417,
			"version": 343,
			"versionNonce": 94537927,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139115692,
			"link": null,
			"locked": false,
			"text": "This can sometimes outperform popular CNN architecture because CNNs heavily rely on textures\ninstead of patterns, whereas Transformers conclude their information from patterns\n\nObviously somewhat similarly to Unet, the skip connections help a lot in propagating low\nlevel information forward.",
			"rawText": "This can sometimes outperform popular CNN architecture because CNNs heavily rely on textures\ninstead of patterns, whereas Transformers conclude their information from patterns\n\nObviously somewhat similarly to Unet, the skip connections help a lot in propagating low\nlevel information forward.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This can sometimes outperform popular CNN architecture because CNNs heavily rely on textures\ninstead of patterns, whereas Transformers conclude their information from patterns\n\nObviously somewhat similarly to Unet, the skip connections help a lot in propagating low\nlevel information forward.",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1168,
			"versionNonce": 59938953,
			"isDeleted": false,
			"id": "ioales18-IUF-RtLDx4pk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.019099722972755195,
			"x": 590.7635106934415,
			"y": 600.7385526913451,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 878710729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714139140003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "pZehlBTg",
			"type": "text",
			"x": 602.8271129593429,
			"y": 558.6038890727041,
			"width": 167.63980102539062,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 43293383,
			"version": 45,
			"versionNonce": 1851491975,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139148383,
			"link": null,
			"locked": false,
			"text": "Read at the end",
			"rawText": "Read at the end",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Read at the end",
			"lineHeight": 1.25
		},
		{
			"id": "o1AdZzPf",
			"type": "text",
			"x": 1350.3151100606915,
			"y": 217.60502664824236,
			"width": 149.07260131835938,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2098385095,
			"version": 45,
			"versionNonce": 306920583,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139156895,
			"link": null,
			"locked": false,
			"text": "Conclusions",
			"rawText": "Conclusions",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conclusions",
			"lineHeight": 1.25
		},
		{
			"id": "XdvKFCDP",
			"type": "text",
			"x": 765.1126419246053,
			"y": 303.7426999069873,
			"width": 1332.7188720703125,
			"height": 875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2137953767,
			"version": 1356,
			"versionNonce": 387423049,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139884330,
			"link": null,
			"locked": false,
			"text": "1) Assumptions:\nIn comparison, Transformers have less strong inductive\nbiases as compared to CNNs or RNNs, this means there is a lot less\nrestrictions in their representation space, but also require a lot more training data\nin order to perform well and are trained for weeks (Large carbon footprint).\nThis flexibility is given through the idea that we take the entire input as a whole and\nmodel relations accordingly, whether we want future and past influenced is possible, spatial\ninformation is not lost due to positional encoding, and different head learn different roles!\n\n\n2) Efficiency:\nSelf attention heads are way more efficient than RNN block architecture and CNN filters\nonly when the sequence length is smaller than the size of the hidden dimension.\n\nRNNs need to grow with the sequence length whereas self-attention is feed-forward\nwhich means we only need to update the context window but the computation stays\nthe same\nself-attention reduces maximal path length between long range dependencies\nof input and output (attending all elements at the same time) and does suffer from short\nterm memory.\n\nIn Transformers, number of sequential computations are independent of sequence length during encoding,\nbut decoding complexity grows with the sequence length!\n\n\n3) Parallelization\nRNNs can memorize but operations can not be parallelized.\n CNNs can be parallelized but are not designed to store information.\nTransformers can be parallelized in parts (the encoder and self-attention, the decoder only during training) and are able to memorize.\n\n\n4) Interpretability:\nLearned attention units are not directly interpretable, as there are a lot of processes that go on in transformers which are not \nshown in their visualized score matrix thus their interpretability is not explainability.\n",
			"rawText": "1) Assumptions:\nIn comparison, Transformers have less strong inductive\nbiases as compared to CNNs or RNNs, this means there is a lot less\nrestrictions in their representation space, but also require a lot more training data\nin order to perform well and are trained for weeks (Large carbon footprint).\nThis flexibility is given through the idea that we take the entire input as a whole and\nmodel relations accordingly, whether we want future and past influenced is possible, spatial\ninformation is not lost due to positional encoding, and different head learn different roles!\n\n\n2) Efficiency:\nSelf attention heads are way more efficient than RNN block architecture and CNN filters\nonly when the sequence length is smaller than the size of the hidden dimension.\n\nRNNs need to grow with the sequence length whereas self-attention is feed-forward\nwhich means we only need to update the context window but the computation stays\nthe same\nself-attention reduces maximal path length between long range dependencies\nof input and output (attending all elements at the same time) and does suffer from short\nterm memory.\n\nIn Transformers, number of sequential computations are independent of sequence length during encoding,\nbut decoding complexity grows with the sequence length!\n\n\n3) Parallelization\nRNNs can memorize but operations can not be parallelized.\n CNNs can be parallelized but are not designed to store information.\nTransformers can be parallelized in parts (the encoder and self-attention, the decoder only during training) and are able to memorize.\n\n\n4) Interpretability:\nLearned attention units are not directly interpretable, as there are a lot of processes that go on in transformers which are not \nshown in their visualized score matrix thus their interpretability is not explainability.\n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Assumptions:\nIn comparison, Transformers have less strong inductive\nbiases as compared to CNNs or RNNs, this means there is a lot less\nrestrictions in their representation space, but also require a lot more training data\nin order to perform well and are trained for weeks (Large carbon footprint).\nThis flexibility is given through the idea that we take the entire input as a whole and\nmodel relations accordingly, whether we want future and past influenced is possible, spatial\ninformation is not lost due to positional encoding, and different head learn different roles!\n\n\n2) Efficiency:\nSelf attention heads are way more efficient than RNN block architecture and CNN filters\nonly when the sequence length is smaller than the size of the hidden dimension.\n\nRNNs need to grow with the sequence length whereas self-attention is feed-forward\nwhich means we only need to update the context window but the computation stays\nthe same\nself-attention reduces maximal path length between long range dependencies\nof input and output (attending all elements at the same time) and does suffer from short\nterm memory.\n\nIn Transformers, number of sequential computations are independent of sequence length during encoding,\nbut decoding complexity grows with the sequence length!\n\n\n3) Parallelization\nRNNs can memorize but operations can not be parallelized.\n CNNs can be parallelized but are not designed to store information.\nTransformers can be parallelized in parts (the encoder and self-attention, the decoder only during training) and are able to memorize.\n\n\n4) Interpretability:\nLearned attention units are not directly interpretable, as there are a lot of processes that go on in transformers which are not \nshown in their visualized score matrix thus their interpretability is not explainability.\n",
			"lineHeight": 1.25
		},
		{
			"id": "tTJ7BOLY9OjGz_Yv4nBtZ",
			"type": "arrow",
			"x": 2377.929147472022,
			"y": 1844.3524135168173,
			"width": 193.13553364477048,
			"height": 61.06491137297894,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 526946727,
			"version": 62,
			"versionNonce": 663407977,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1714139359626,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					132.07062227179176,
					-36.92296966738263
				],
				[
					193.13553364477048,
					24.14194170559631
				]
			],
			"lastCommittedPoint": [
				193.13553364477048,
				24.14194170559631
			],
			"startBinding": {
				"elementId": "H-xBi6Q-o5bTklOPXExfO",
				"focus": -0.3168308866400727,
				"gap": 18.593684442182166
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "14FAhQQ9",
			"type": "text",
			"x": 2367.144911829683,
			"y": 1886.9558400561048,
			"width": 407.83953857421875,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 329415177,
			"version": 315,
			"versionNonce": 1194938439,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714139446340,
			"link": null,
			"locked": false,
			"text": "Are there any guarantees that the\ndifferent heads will learn different thing?\nNo, there is nothing stopping them\nfrom doing so, but it is very unlikely\ngiven the random initialization of the\nweight matrix.",
			"rawText": "Are there any guarantees that the\ndifferent heads will learn different thing?\nNo, there is nothing stopping them\nfrom doing so, but it is very unlikely\ngiven the random initialization of the\nweight matrix.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Are there any guarantees that the\ndifferent heads will learn different thing?\nNo, there is nothing stopping them\nfrom doing so, but it is very unlikely\ngiven the random initialization of the\nweight matrix.",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1315,
			"versionNonce": 1629104297,
			"isDeleted": true,
			"id": "Y82JUloLdMkKl9K7g_kPN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.726157453058118,
			"x": 1985.8410351169941,
			"y": 3327.628848019435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 255.61087436747334,
			"height": 162.02656517282466,
			"seed": 1085837895,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714138975825,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5608121408702686,
					92.35388895469862
				],
				[
					190.97364176880194,
					67.64409555860533
				],
				[
					191.0458890481597,
					124.10487523845498
				],
				[
					255.61087436747334,
					48.17079532203714
				],
				[
					190.973641768802,
					-37.92168993436968
				],
				[
					192.15368066497734,
					21.89499150958345
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "7iOp0C2d",
			"type": "text",
			"x": 2783.2850484311725,
			"y": 2809.549717834669,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 928103945,
			"version": 2,
			"versionNonce": 1148701223,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714137744532,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "KVR0JGoq",
			"type": "text",
			"x": 3271.856477002601,
			"y": 2990.97828926324,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1386770953,
			"version": 2,
			"versionNonce": 442816039,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714137782790,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "cP8VFRDB",
			"type": "text",
			"x": 3408.8406039867277,
			"y": 1485.224321009272,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 131612103,
			"version": 2,
			"versionNonce": 224655625,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714137817640,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "mo94GwMf",
			"type": "text",
			"x": 3997.6739373200608,
			"y": 1742.5576543426052,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 427250503,
			"version": 2,
			"versionNonce": 2027298121,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714137997390,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "uLEdLjKuoDZk9LugLf4TS",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "h82dDtV4",
			"type": "text",
			"x": 4511.426209906873,
			"y": 1713.1869122009934,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 328029961,
			"version": 2,
			"versionNonce": 510690151,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138017451,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rWP9MR6VKzHo7McjNEbba",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "U7eEooFS",
			"type": "text",
			"x": 4470.862241595496,
			"y": 2336.8579249883605,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1161625287,
			"version": 2,
			"versionNonce": 1268791753,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138081502,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "W2I9XbP2wUuj3KdOqDK2O",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "hrqkNwUk",
			"type": "text",
			"x": 1249.1676838861172,
			"y": 1877.829955746555,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1083819657,
			"version": 2,
			"versionNonce": 915643367,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138781050,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "MjKuWYIIdunrHyz3ufQyq",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "i8oqADYu",
			"type": "text",
			"x": 3290.116851390905,
			"y": 832.6060082230113,
			"width": 298.9012451171875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1729818919,
			"version": 2,
			"versionNonce": 88542855,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138909876,
			"link": null,
			"locked": false,
			"text": "Instead of using con-",
			"rawText": "Instead of using con-",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Instead of using con-",
			"lineHeight": 1.25
		},
		{
			"id": "NqQWzDMo",
			"type": "text",
			"x": 3293.364867748327,
			"y": 877.6060082230113,
			"width": 292.40521240234375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1629837513,
			"version": 2,
			"versionNonce": 559694185,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138909876,
			"link": null,
			"locked": false,
			"text": "volutional layers rep-",
			"rawText": "volutional layers rep-",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "volutional layers rep-",
			"lineHeight": 1.25
		},
		{
			"id": "ZG54uwvo",
			"type": "text",
			"x": 3306.426925243444,
			"y": 922.6060082230113,
			"width": 266.2810974121094,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 823145543,
			"version": 2,
			"versionNonce": 1653712295,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138909876,
			"link": null,
			"locked": false,
			"text": "resent an image as",
			"rawText": "resent an image as",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "resent an image as",
			"lineHeight": 1.25
		},
		{
			"id": "XvF2UBGO",
			"type": "text",
			"x": 3298.9928737297723,
			"y": 967.6060082230113,
			"width": 281.1492004394531,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1316050857,
			"version": 2,
			"versionNonce": 84028489,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138909876,
			"link": null,
			"locked": false,
			"text": "a sequence of image",
			"rawText": "a sequence of image",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a sequence of image",
			"lineHeight": 1.25
		},
		{
			"id": "ww2R7rGo",
			"type": "text",
			"x": 3324.388991893835,
			"y": 1012.6060082230113,
			"width": 230.35696411132812,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 229643111,
			"version": 2,
			"versionNonce": 1690065095,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714138909876,
			"link": null,
			"locked": false,
			"text": "patches (tokens)",
			"rawText": "patches (tokens)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "patches (tokens)",
			"lineHeight": 1.25
		},
		{
			"id": "Zwn4zd1I",
			"type": "text",
			"x": 2504.9997773732084,
			"y": 1794.9294438494346,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1832118343,
			"version": 2,
			"versionNonce": 1568618569,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1714139359627,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tTJ7BOLY9OjGz_Yv4nBtZ",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#ced4da",
		"currentItemFillStyle": "cross-hatch",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": -425.82404858608834,
		"scrollY": 43.48093537414809,
		"zoom": {
			"value": 0.7041687121653212
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		},
		"objectsSnapModeEnabled": false
	},
	"files": {}
}
```
%%