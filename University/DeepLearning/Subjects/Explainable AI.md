---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - DeepLearning
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Types of explanations ^aOlT8ogT

Generate an example of The features that
distinguish the current class from all others ^eFPhTehy

Pineapple ^FXuTwphC

Highlight features for a given input that
strongly swayed the output to be what it is
(LRP Heatmap) ^4dw4FTZN

Cat ^37xIcnLR

Person ^9qVqkONj

Generate ^gGlgagN6

Elaborate ^DwTKgcSG

Conceptualize ^yejqnjWY

Generate Concept Activation Vectors
that highlight mid-level concepts that
result in the prediction for a given
input ^tHj9Hsgg

Input ^B2HYKTsr

Stripes ^Dz8Abdin

Cat ^E8O9GDnF

Output ^gRTZrrsJ

58% ^6VyG0BVo

42% ^1wrzhvSy

E ^P89AhelJ

x ^XEd24d7Z

p ^SCAnYY3J

l ^4N8gsCgJ

a ^nW0y4dmj

i ^GlHDRZ8H

n ^To1MKy27

a ^Ga48Ye6A

b ^8Mkuaecl

l ^D5NbcNG1

e ^cTyfdkgd

  ^LIGn1RYT

A ^ugDhIj99

I ^iRAO5FXw

F ^Py8PA51g

i ^WKEf1JvT

n ^hNDOHdBG

a ^tHWkQyey

l ^lDox6imr

l ^vcogVMWH

y ^4zfLaj7x

. ^9OC4VjFk

. ^sbB9WAuY

. ^bUGfZaSe

  ^Xjj0TeRt

a ^ePB17FH3

n ^fIHcq1a2

  ^LalN8Mc9

e ^muas2aKL

x ^Dr6GYyxS

p ^Lff7VskO

l ^SwfdKQMZ

a ^5UG4PHxD

n ^eLPjqHKQ

a ^audeMIsP

t ^a7bmFY1f

i ^ik20hjrS

o ^XXX9AtUN

n ^bMnCq3Rl

  ^MOSCbfV5

f ^6hluPbPm

o ^laRRDAp8

r ^kqjyVRui

  ^ENmuaWZr

t ^1tv4I3vd

h ^TCGbXPhl

i ^deNDEtfT

s ^VHcmVfyY

  ^2JXFD3Q4

s ^rEmTUCrG

h ^0Fh6zC84

i ^NLbCIpjf

t ^wjnav8Mx

? ^8eh3jAi0

Nerd ^KficlfDC

You ^QOqfq2QY

maybe I should
keep changing the
parameters until
it says im cool? ^ibknqWor

Why explainable AI? ^CubllqYm

Improve ^HnjDFlkF

Our Model is not working properly, perhaps an
explanation will help us improve on making the
model make the right decisions ^ejGJmkch

Assist ^zsnI0YD2

Assist users in making decisions faster
by highlighting relevant regions that need to
be focused on in complex situtions ^SywYouQA

Explain ^LiHQlPM3

helps scientists discover relations between
different variables in a complex system that
is not well-studied ^LjeewRQq

Dont sue me ^862JxZPc

Legal obligations demand for an explanation
of why our AI model makes the decisions that
it does in order to be publicly available ^61pJEDjh

Okay that's cool and all,
But how do we actually Generate
these explanations? ^5ENRpxKm

1. Activation Maximization ^60QIpT1p

Given a Neural Netowrk, we would like to understand
 what concept is associated with a particular output
class and which input x Maximizes our desired output




Think of our model as a function and try to understand
how to produce the maximum output from a given input  ^L3JAlreY

Problem:
X can just grow to infinity and maximizing
the value of our function
BUT
infinity input does not make much sense ^DJ7TME9H

Idea:
Lets restrict x into a certain domain where things make
sense and are plausibly sampled from the real world ^HbWOT23J

Approach 1:
Penalize Large values by adding
the negative norm to the max function ^5iECxm3b

Approach 2:
Only sample points from the given
data distribution! ^w6CMsXmV

Assume that our model produces a log-probability for class wc
i.e the function that the model learned to classify class wc
from input x which is where our model is SURE its wc ^KPhFYHhy

We can penalize this term by only drawing from
the distribution of x,       ^j02NwSCr

Bayes Theorem ^rfZfFYDu

The distribution of wc does not have to do
with out choice of x! and its constant thus
we take it out of the function ^oo8kaE83

Which makes sense because it can now be
interpreted as the most typical input for class ^Zo6FqbVE

2. Attribution ^NwlRhPuS

The data point X ∈ R is fed to the ML model and we get a prediction
f (x) ∈ R
We try to explain the prediction of this given point by pointing out
the additive contribution of each input feature ^wjyw97Vf

d ^7TCQJl6q

Using Game theory's
Shapley Values! ^E0fBXiwg

Shapley Values ^9uk3y5Bo

A model agnostic commonly used technique to interpret the way the model works

Answers the question
"how much do each of the features contribute to the difference
between our prediction and the average prediction?" ^IE047TRc

Example:
Calculate the shapley Values of f(1) ^NWCVs3io

Note that Xi
are binary variables ^JGHEejBQ

S ^4FcItLT4

{}

{2}

{3}

{2,3} ^WJk33SGt

Multiplied ^xVaDiTts

0 ^sSWPXB4R

1 ^chDmRHvy

1 ^tyP4l6Wy

2 ^7It7ZHcA

0 ^CLYHDqqy

S ^ArSCcuaC

{}

{1}

{3}

{1,3} ^HrgtU4nE

Multiplied ^4sdJKBf2

0 ^sBNYH9OJ

1 ^yhfSU1aA

0 ^55DBKrde

1 ^PJnJydAD

0 ^FVJsoIQj

0 ^7N5qQmXO

dimensions ^ooZd71mJ

all possible
subsets that
dont include i ^jwy1zUem

very similar calculation for phi3 so its the same result ^OG5Kr184

We (some nerd) observed that that the
shapley values formula can be rewritten as ^LKsZ9mHi

all possible
permutation ^0yCbqhkW

set of features
that precede
feature i in the
order of S ^ezJROd0j

set of features
that precede
feature i in the
order of S
INCLUDING i ^uBZX9YOB

Shapley Values Sampling ^s8VTlnTU

We can calculate the approximation of the shapley value
by uniformly sampling from all subsets 
The accuracy of the approximation scales with T->infinity ^1tZum2bx

Still computationally expensive for large d ^bmw3dwaK

Problem ^apFJKPSM

Shapley values require an
exponentially large
number of evaluations
of the function f
Including all possible
subsets of f multiplied
by the dimensionality
of our input which can be
extremely large in
Neural networks ^CQRKqBhj

Can we exploit the structure
of the neural network in order
to detect the contribution of
the neurons to the output? ^K6hR2yW0

Layer-Wise Relevance Propagation ^lGc9O2fw

Use the structure of the neural network to robustly Propagate
the output of the network backwards by means of propagation rules
(Can be tuned for tuned for different explanations, e.g sensitive in
top-layers, robust in lower layers) ^KSiwGKkt

Notation: ^vgrawXP1

* j, k indicating neurons from 2 layers
  connected to each other j->k
* Wjk is the weight connecting the two
  neurons j and k
* w0k is the bias for neuron k
* Sum(0,j) is the sum over the input
  neurons for neuron k

* Numerator: contribution of aj to the
  activation ak
* Rk: relevance of Neuron k
* Denominator: Normalization term to
  implement conservation
* Sum (k): pool all `relevance' coming 
  from the layer ahead into neuron j ^3Pw4IH8S

* LRP-0: ^vaHIHtSV

* LRP-epsilon: ^rdCumLcn

* LRP-gamma: ^Ae4thelO

Sensitivity of neural network
output to neuron j's activation ^dkbEoECD

LRP rules differ from layer to layer
thus we need to combine different
LRP in different layers in order
to get the best results and
explanations ^bmkYn2o6

This based off of and derived from the RELU
activation function ^uwKhOPRJ

Which ensures that ^9eMH5uXk

that is equivalent to Gradient × Input
the issue is that the gradient becomes
very noisy the further we go back so this
is not very robust ^nFJ0pSYw

The role of epsilon is to absorb some relevance when
the contributions to the activation
of neuron k are weak or contradictory As epsilon
becomes larger, only the most salient
explanation factors survive the absorption.
This typically leads to explanations
that are sparser in terms of input features and less noisy ^fwv9XkN9

We can enhance this further by focusing on the
positive contributions over the negative contributions
The parameter γ controls by how much positive contributions 
are favored ^0P48E8VE

Which LRP Rule for Which Layer? ^TogOaUWj

There are 2 general desirable properties of an explanation
fidelity and understandability 
In other words, an explanation should be
an accurate representation of the output neuron of interest (as in
it has accurately concluded the ground truth of the issue),
and it should also be easy to interpret for a human. ^o7y4clPT

1. Uniform LRP-0 picks many local artifacts of the function the
explanation is overly complex and does not focus sufficiently on the
actual object. it is neither faithful not understandable.

2. Uniform LRP-epsilon removes noise elements in the explanation to
keep only a limited number features that match the actual object, yet
it is still too sparse to be understandable.

3. Uniform LRP-γ is easier for a human to understand because
features are more densely highlighted, but it also picks unrelated
concepts and strays away from the truth

4. Composite LRP overcomes the disadvantages of the approaches
above making it both faithful and understandable ^hig0EtMP

How to use Composite LRP? ^uuCahoW3

Upper layers have only have a few neurons per class,
making it likely that the many concepts forming the different
classes are entangled. Here, a propagation rule close to the
function and its gradient (e.g. LRP-0) will be insensitive to
these entanglements. ^6mhhiTlD

Middle layers have a more disentangled representation, however, the stacking
of many layers and the weight sharing in convolutions introduces spurious
variations. LRP-epsilon filters out these spurious variations and retains only the
most salient explanation factors ^IC1JvgiA

Lower layers are similar to middle layers, however, LRP-γ is more suitable
here, as this rule tends to spread relevance uniformly to the whole feature
rather than capturing the contribution of every individual pixel. This makes
the explanation more understandable for a human. ^eQkeJLMG

PROS ^FFXRU1gu

v.s ^Nt8BdTiC

CONS ^sL386jqb

Good explanation quality on deep networks.

Pretty fast (One needs one pass)

Flexible (Has tunable hyperparameters) ^MfVrWDfp

Need to choose HyperParameters correctly

The propagation strategy needs to be
adapted to new architectures

LRP assumes that the model has sufficiently
disentangled the function to explain ^G1G3ZCsA

global interpretation ^G6hGJ7OU

local interpretation ^2xppjxI9

1. Explanation: Which pixels contribute how much to the classification

2. Sensitivity: Which pixels lead to increase/decrease
of prediction score when changed

3. Deconvolution: Matching input pattern for the classified
object in the image ^2egJm5Np


Image specific explanations: LRP takes into account the activations.
LRP provides different explanations for different input images.

For NNs without pooling layers Sensitvity and
Deconvolution provides the same explanations for
different samples. ^xG4Vd8In

Unlike Deconvolution, and sensitivity
LRP distinguishs between positive evidence, supporting the
classification decision, and negative evidence, speaking against the prediction ^cfHkUqsR

LRP explanations are normalized (conservation of relevance).
This allows to meaningfully aggregate relevance over datasets or regions in an image ^nlVOTCkb

Taylor Expansions ^1BQMR0UM

Many ML models are highly non-linear and really complex
when looked at from a global perspective, but when
we take a close look at each local region of the function
we typically dont find rapid change, thus making it somewhat
locally linear and easily approximated ^ZEcB39im

Approximating the function at root x
Can be done via a Taylor expansion ^i0AFRwmO

value of
function
at root ^Ek3JpLLg

derivative
of function
at root ^lN6pqlas

difference
between
reference point
and root ^ev8jxf9r

first order expansion ^jMbRqf8Q

higher order
terms which
are usually
insignificant ^Z7tfJIin

contribution of
feature i of x ^gy78iLtp

This is quite limited!!

This is highly based on the gradient, and thus cannot deal with plateus
saturation and discontinuities  ^Rh2wWaY7

Can we use this sort of method
for non-supervised models? ^6KDWgTAj

Beyond first order methods ^iBQsMRYb

First order explanations are quite a natural way of describing
input feature's contribution to the result given.
But this is not a faithful explanation for all models, as some models
use a conjunction of features to make their decisions and thus we have
to go to a higher order to give those relations a contribution to our decision. ^7ZzNgt8k

for example:
similarity methods                                         Graph neural
in representation learning                                      networks    ^UgahNJFV

Self-supervised learning ^TK1KsQCd

Self-supervised learning ^KNgX4HE1

How similar
are they? ^uOoNCjnR

Similarity Models
Second-order explanations ^SNQ0wo5U

How similar
are they? ^ITbETUfL

x ^Ua46BgbT

x' ^3AbazGtP

encoded
features
z ^qgnEdKjd

 y (x,x') = dot(z,z') ^ZS7mPZk5

Taylor expansion ^JP0Dp90E

First
order ^6I5zID0C

First
order ^h6C7rtGV

Second order
describing relations
Hessian x product  ^mzqI96jg

We obviously have to assume that the function is piece-wise linear
and we have well chosen root points for this taylor-based approximation
to be accurate ^9qAwGrhT

can be seen
as a second order
variation of Gradient
x input ^vZ8YahAI

Similar to first Order methods
it suffers from
shattered gradients, i.e. the local gradient variations become stronger
with increasing model depth
and
difficulty to robustly select root points, danger of adversarials that do not
meaningfully represent the data ^juXqaw8l

Tranformers ^aFbM7NDj

To ensure that you focus on positive corrolation ^N92NP1Ns

Graph Neural Networks
and higher order explanations ^a6IYhvZI

Graph neural networks learn a representation of the graph through message passing
at each iteration of message passing we use the adjacency matrix to aggregate the information
from all the nodes to their neighbours.

meaning the message not only can passes from one neighbour but partially from all nodes in the graph.
a second order contribution is not enough we need a higher order contribution in order to understand
the effects of each node on other nodes ^ioUlCctv

Walking backwards ^V0I5qP6c

Aggregate:
each node receives information from
the neighboring node ^tgREcFcn

Combine:
extracts new features for each node ^W2xZytxw

Representation of
the graph at layer
t ^bYPzDLxR

Adjacency matrix ^3VybF28Q

the row of Zt
associated to node K ^3cxaYIPk

a ‘combine’ function, typically a one-layer or multi-layer
neural network, that produces the new representation for
each node in the graph. ^bZlOHBt5

the true input Λ of the GNN occurs at
multiple layers and because layers are generally composed
in a multiplicative manner, a first-order
analysis of the GNN function f (Λ) would not be suitable to
identify the multiplicative interactions. These interactions
can however be identified by applying a higher-order Taylor
expansion ^kWQguGQR

The conservation axiom (also known as completeness or efficiency) states that scores assigned to
input variables and forming the explanation must sum to the output of the network, in
other words, each input variable contributes a share of the predicted score at the output
This is an important factor to keep in mind. ^G7YE0mRQ

Gradient x Input Method



and since the input to the attention head is linked to MLP layer afterwards we can derive that: ^zL5SIibE

If it holds that the following condition is true for every component
of the neural network then conservation is met using this methods on transformers



and if we translate this into the transformer architecture we get ^N15uQi1T

Resulting in ^uXecrgaf

softmax ^2GwVpgSN

pre-softmax ^5LztnZr0

Which implies that if the right-most term is not zero then this method is not conservative!
and the right term is a covariance between q which is a function of x and thus has a relation
to x, thus the covariance is often not 0 ^oEoLjW4F

x ^fkwKKqcq

x' ^uFMNtTDM

Attention head ^D1ItH8Xf

y ^sMKFXruL

MLP ^PQsZVsJc

y ^svihJSMk

Detachment Method
for explaining Transformers ^tZv4zL8A

In order to be able to keep conservation we need to make a few assumptions that will make our model
less accurate but not completely wrong like in Gradient x input method.

For both the LayerNorm and the attentionHead, conservation is not met, so lets detach some terms
from them and treat them as weighing constants.

For the attentionHead we treat the probabilities produced by the softmax as constants, I.e we detach
the fact that x' contributes to the output this will in turn destroy the term that contributed to breaking
the conservation in our last method and thus we have a simplified versions:





Similarly in the Normalization Layer the model function has 2 paths going through the actual
input and a softnorm for normalization, and thus those two terms together wont conserve the contribution
but if we detach one of them (The normalization in this case) we can keep conservation. ^RkQQRGHw

Beyond Neural Networks ^pyT89NVJ

There are many non-neural network algorithms that are still quite popular
and while they have more theory than neural networks they can still be seen as
black boxes due to kernels and other reasons, thus we need a way
to be able to explain such models


LRP method is quite a nice way of explaining contribution, if we can reformulate
our algorithm such that its "shaped" like a neural network then we can
just apply a normal LRP method and provide explainability ^MLGCv0Xn

Kernel Density Models ^vc4rqLR0

Kernel density estimation (KDE) and one-class SVMs are non-neural
network models for density estimation/ anomaly detection. The inlier score
can be generically written as a weighted sum of kernel scores: ^P0jrbi9E

The anomaly score can then be seen as the negative log of this score

If we view the inner-exp values as a weighted sum of inputs + bias and the
exponential function as an activation we can easily neuralize this
formula while keeping it the same. ^NLnwcqIf

K-means clustering ^CaZIpnoV

Assign cluster membership of x according to the distance of the closest
cluster centroid mu ^h81T6eeF

We can also Neuralize this by assuming that the minimization function
is the activation and reformulate the rest to be in the form of weights
and biases ^GdroUZzs

# Embedded files
1057e27e8caaf5155a215bba03d57ff9900c024d: $$x^{*} = arg\max_x f(x)$$
6e8f2c9fc467a8a7a5c4148fa7f4bc47bd520f57: $$x^{*} = arg\max_x f(x) - \lambda \|x\|^2$$
e9d31ac7e9520a3411ecf6ae34c7e5973388e847: $$f(x) = log(p(w_c | x))$$
5b6690b5f4aa8648bcd3065194fb091c6fb867ba: $$log (p(x))$$
90cea52d0a607335ca29558b2319aed149e361e2: $$x^{*} = arg\max_x log(p(w_c | x)) + log (p(x))$$
5193f50b29cf370ea452e478f84713b5d0ce868b: $$x^{*} = arg\max_x log(p(x | w_c)) p(w_c)$$
54a136ee96e91423d706748fe9df8491b17b9d0a: $$x^{*} = arg\max_x log(p(x | w_c))$$
fcfe356af748b0b3ad0e721471e8e2ecfafcd884: $$\phi_i = \sum_{S : i \not\in S} \frac{|S|! (d - |S| - 1)! }{d!} [ f(x_{S \cup \{i\}}) - f(x_S)] $$
23b4752a5c67771f34c95cb0756787749d05c05a: $$f(x) = x_1 \cdot (x_2 + x_3)$$
cc056000ddb1cac084b8a0debab4694e165acd4f: $$\frac{2}{6}$$
f1396a6bd9590abbbd0ffabd4e4c2e2e6e8efdc6: $$\frac{1}{6}$$
5ade8a6ac9fe92bf6a8d5e0626037f12f61718f9: $$\frac{1}{6}$$
c73b77695b59f3f835e5c51d0510d5bd792a8471: $$\frac{2}{6}$$
f953ac4204f521d0ed225c111bddf6cd6c6fd945: $$\frac{1}{6}$$
4ef8c161196b6a9dfab5e4858ceeea2936b8064e: $$\frac{1}{6}$$
74866e79cafd90e200302b662c1d58b500de33ad: $$\frac{4}{6}$$
80a8f1878caa3bccc2f7a0ee5d72d288d9b44181: $$\phi_1 = 1$$
6207cc7ea4d800884cd998c1f6dddebffedc0496: $$\frac{2}{6}$$
e963a6c850644e44618007a9544bf3f62b762990: $$\frac{1}{6}$$
4b336c81a45d4dbbc02456fe2b90703d3e44a610: $$\frac{1}{6}$$
55637311ca3570642eb9e966ddfbc5111177c770: $$\frac{2}{6}$$
e0facc82f877771cbe87b5b64ff4a61b416806c9: $$\frac{1}{6}$$
4f0b2afe17e205490a780d6b502244f18f18cd50: $$\frac{2}{6}$$
d8ead9ad8b9f20e2611caaa2a7595bc886e0aa0f: $$\phi_2 = \frac{1}{2}$$
1db460809fd50c98d3d585a8e3e27792df093304: $$\Delta S$$
e0add2362b0353f46b5f7c838af954f84fe7f4ef: $$\alpha_S$$
0a56346bd1d113f21655691d79e1d4d4e436e2bc: $$\alpha_S$$
2d22ec7c05b3d162fdec98a5aad689bfdaa1d375: $$\Delta S$$
4dbd5afe7b20d5ad24e3116e9a29deb4ce07dec1: $$\Delta S$$
63d6178c8dfe8d0f28b21d7c3a0b814b8fb71a9f: $$\alpha_S$$
a0f443f362bc99e6fc58091ccd3a586d0cced23b: $$f(1) - f(0) = 2$$
0c90471c5fe361d4d97e4d758e7f8dacb50f4129: $$\phi_1 = 1$$
6ea1df09ec87a2efb9e0d35885d56d1367b9342b: $$\phi_2 = \frac{1}{2}$$
c005e79e72eeeb46ebbf96e80c11017c2fcc3958: $$\phi_3 = \frac{1}{2}$$
11c5021f9fcb9f0b221ed248334029be54ca29cf: $$\color{black} \phi_i = \frac{1}{d!} \sum_{S\in P} [ f(x_{preceq(S,i)}) - f(x_{prec(S,i)})  ]$$
1a63bac8b79ad337d987cd72a581eb652446c9f8: $$\color{black} \phi_i = \frac{1}{T} \sum_{S \in \{S^{(1)}..... S^{(T)} \}} [ f(x_{preceq(S,i)}) - f(x_{prec(S,i)})  ]$$
9db0182084e56b7690fce3ee4f85d8b3a86118af: $$R_j = \sum_k \frac{a_jw_{jk}}{\sum_{0,j} a_j w_{jk}} R_k$$
f8832583255457590444ecd9e29d2f6031ac6c58: $$R_j = \sum_k \frac{a_jw_{jk}}{\epsilon_k + \sum_{0,j} a_j w_{jk}} R_k$$
23952c6de906fb54e75d4515bf8c0de39e681edf: $$R_j = \sum_k \frac{a_j(w_{jk} + \gamma w_{jk}^+)}{\sum_{0,j} a_j (w_{jk} + \gamma w_{jk}^+)} R_k$$
8502505eb5c4d86f497900c43a14f58633f59120: $$R_j = a_j (\sum_k \frac{w_{jk} + \gamma w_{jk}^+}{\sum_{0,j} a_j (w_{jk} + \gamma w_{jk}^+)} R_k)$$
d9fb76c8fe000ea2110b342942071188105a106c: $$a_k = max(0 , \sum_{0,j} a_j w_{jk} )$$
848fccdc7a849beb8cab9504c9522212a95abbe9: $$(a_j = 0) or (w_j = 0) \rightarrow R_j = 0$$
c190d3954830e3f3049e4eab8be022d9841fd8dd: $$f(x) = f(\hat{x}) + \sum_i^d [\nabla f(\hat{x})]_i \cdot (x_i - \hat{x}_i) + ....$$
6f246287499dad1e7689b52b652913c933edee09: $$y(x,x^{'}) = y(\hat{x},\hat{x^{'}}) + \sum_i [\nabla y (\hat{x},\hat{x^{'}}]_i (x_i - \hat{x_i}) + \sum_{i^{'}} [\nabla y (\hat{x},\hat{x^{'}}]_{i^{'}} (x_{i^{'}}^{'} - \hat{x^{'}_{i^{'}}}) + \sum_{ii^{'}} [\nabla^2 y (\hat{x},\hat{x^{'}}]_{ii^{'}}(x_i - \hat{x_i}) (x_{i^{'}}^{'} - \hat{x^{'}_{i^{'}}}) $$
5fbcbafe4f081a6ebcaf8ed140c8be653ad64528: $$Z_t = \Lambda H_{t-1}$$
1ed1b5248543ad7de09650ef46be19a471858b71: $$H_t = (C(Z_{t,K}))_K$$
681bf9760978509466f706f2de3c8241303df575: $$R(x_i) = x_i \cdot (\frac{\partial f}{\partial x_i})$$
b513ee1331e6eb4af8647f25031b2202ef6f4fdb: $$R(y_i) = y_i \cdot (\frac{\partial f}{\partial y_i})$$
d38b92ad19cf0731494136a4460970874787c52d: $$\frac{\partial f}{\partial x_i} = \sum_j \frac{\partial f}{\partial y_j} \frac{\partial y_j}{\partial x_i}$$
65d551b9a113662bede60f8e955a8351e60dc29c: $$R(x_i) = x_i \cdot \sum_j \frac{\partial y_j}{\partial x_i} \frac{R(y_j)}{y_j}$$
9839c498976482ef7039ac589ec9b7db1763c33d: $$\sum_i R(x_i) = \sum_j R(y_j)$$
b79be707beb5de5348804dbb1b8527a03e05b245: $$\sum_i R(x_i) + \sum_j R(x_j^{'}) = \sum_j R(y_j) + 2\sum_j Cov_j(q_{:j},x)^T \frac{\partial f}{\partial y_j}$$
fae367afebb38dea1f3b121fcdc5a6fd972f70fa: $$R(x_i) = \sum_j \frac{x_i p_{ij}}{\sum_k x_k p_{kj}} R(y_j)$$
6947cf36aff24bcda3e927e5fc45ac08e6f60716: $$R(x_i) = \sum_j \frac{x_i \cdot (\delta_{ij} - \frac{1}{N})}{\sum_k x_k \cdot (\delta_{kj} - \frac{1}{N})} R(y_j)$$
5bb2314e17612e74757424160f3480a4c78b8b80: [[cropped_Pasted Image 20240215191602_590 1]]
2646750f6b6d22acba1c96599d79cde205e3ae60: [[Pasted Image 20240215192235_660.png]]
a94abb57e2925fffb0c1acc67a41ef20cb7b6227: [[cropped_Pasted Image 20240215192355_400 1]]
7f69a0d880f68b5f2bc447904883f3ffc7ea9754: [[Pasted Image 20240216141619_812.png]]
0a1244723d968856aaf3380630be993482a83ed9: [[Pasted Image 20240216141649_827.png]]
cf32ef4a285d2f19ff5d5ba85a7461a7e1e20171: [[Pasted Image 20240216144038_002.png]]
79a2a750811e26419c6d86cf486694eddda9dbc6: [[Pasted Image 20240216144223_008.png]]
2046eabfb19e5a1890fa740b7637ac4280251907: [[Pasted Image 20240216144339_015.png]]
4dbe47bfdca823be02051c7f1bd4e08ec8798d51: [[Pasted Image 20240216154632_695.png]]
1c35a7aa0c07ca0f839c44071245156fff993786: [[Pasted Image 20240228152050_001.png]]
4d8fa2b51d5d1f5c46471dfd2bce7b35f8509c27: [[Pasted Image 20240228155935_270.png]]
00ce334e0731ae23b97d07760b1513042e4daa00: [[Pasted Image 20240416221248_203.png]]
da4dc7fe07f90efe656d5a0b241750dcefc623ff: [[Pasted Image 20240416221218_200.png]]
9444c80b3a42b4f0aa8c0fd6c19faf384cd6adf5: [[Pasted Image 20240416221147_182.png]]
d62494fbdd7b83ce858cbdd806d7d5a2e1065de7: [[Pasted Image 20240524153043_687.png]]
7eea13b18bbdb468327763d4b55c22730dd2d3d0: [[Pasted Image 20240524160611_958.png]]
7d74c227c43362c09d7b59ae027324cd8ee3b5af: [[Pasted Image 20240524171628_367.png]]
2cfdab75206c322ed8074f87e5683f635c16a731: [[Pasted Image 20240524171644_383.png]]
7aee6d037c3fd862cf0f37470c4c4f3135d8809a: [[Pasted Image 20240524175832_785.png]]
e4d8c787bdfe24077481bf55046a06d1ee817966: [[Pasted Image 20240524180113_845.png]]
a81e636ec8658f329103254580d93cbdb6aa354b: [[Pasted Image 20240524180331_876.png]]
1e8381e0c09e174a47abfeb6e5e315baf68a20b8: [[Pasted Image 20240524180502_917.png]]
83d5ca4515803a960b59574b19435bcd7967ae16: [[Pasted Image 20240524180517_920.png]]
1e94bb3264acbbe609d3e45205ef117391874585: [[Pasted Image 20240524180534_924.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "rectangle",
			"version": 1578,
			"versionNonce": 812768451,
			"isDeleted": false,
			"id": "uT9if2bmuygj85losSXtV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3820.9356450300884,
			"y": 2813.865026336123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 1106.7129145027618,
			"height": 1077.9043090976252,
			"seed": 192065581,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"id": "zL5SIibE",
			"type": "text",
			"x": -3771.507295478611,
			"y": 3128.0411146514607,
			"width": 970.4990234375,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 949904909,
			"version": 315,
			"versionNonce": 767132909,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"text": "Gradient x Input Method\n\n\n\nand since the input to the attention head is linked to MLP layer afterwards we can derive that:",
			"rawText": "Gradient x Input Method\n\n\n\nand since the input to the attention head is linked to MLP layer afterwards we can derive that:",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient x Input Method\n\n\n\nand since the input to the attention head is linked to MLP layer afterwards we can derive that:",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 1417,
			"versionNonce": 1212107875,
			"isDeleted": false,
			"id": "IH9DyXZcx4R_rM68M1kQm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1406.6950722058277,
			"y": 3479.0665694951495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 1391.0985911163298,
			"height": 834.7707979091904,
			"seed": 1188012173,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1248,
			"versionNonce": 1467244365,
			"isDeleted": false,
			"id": "dIkU-M9KhzwMbnRTIPLq5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2494.278978834338,
			"y": 2806.5012657854295,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 937.2213890790327,
			"height": 929.5363675653291,
			"seed": 1033784995,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 845,
			"versionNonce": 1342031875,
			"isDeleted": false,
			"id": "j_6bQm56aiDRDvjrKJY5x",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1647.204775138752,
			"y": 1961.9219956780005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 560.0268350796848,
			"height": 219.22407353997974,
			"seed": 680032977,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531067,
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
					-489.045637511584,
					29.455127194989984
				],
				[
					-488.5357065356608,
					-50.933277922583244
				],
				[
					-560.0268350796848,
					48.18823703340189
				],
				[
					-488.2708100717753,
					168.2907956173965
				],
				[
					-487.02577555973676,
					96.6905599440295
				],
				[
					-6.363217423354058,
					111.77388967570926
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 545,
			"versionNonce": 228912557,
			"isDeleted": false,
			"id": "lZ-S4wDxYV0N1LTD7Sz3b",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1249.6008242355924,
			"y": 1960.3898409777669,
			"strokeColor": "transparent",
			"backgroundColor": "#fdf8f6",
			"width": 256.6677162659618,
			"height": 114.01418579452275,
			"seed": 1066417905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 840,
			"versionNonce": 1034669987,
			"isDeleted": false,
			"id": "KVVnMTvHR6U5fB6tYVEt1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1667.7085384009304,
			"y": 1731.6397513094535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 606.3139932825064,
			"height": 601.8497696494023,
			"seed": 1088080241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 686,
			"versionNonce": 527740941,
			"isDeleted": false,
			"id": "4OxcTJfWr_HHpLDAjYlF1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1423.1177949472294,
			"y": 820.7337350238034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 826.3143007140806,
			"height": 725.9100933890113,
			"seed": 1793713841,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 601,
			"versionNonce": 1131930435,
			"isDeleted": false,
			"id": "wr5NT7C2AIue2FCw2kVhn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 389.25521946141356,
			"y": 851.1229129805719,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 745.4552506529132,
			"height": 692.701132146597,
			"seed": 1159410463,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 432,
			"versionNonce": 987571821,
			"isDeleted": false,
			"id": "F-kqvmdImlARDvOCvK2n4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 839.7750543078789,
			"y": 1093.8494871435644,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 192.30307030605172,
			"height": 88.30700431303532,
			"seed": 1265618737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531067,
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
					-150.16673322267434,
					0.448258905142211
				],
				[
					-170.7866428592206,
					-36.30897131652727
				],
				[
					-190.5100346854823,
					-38.10200693709655
				],
				[
					-191.85481140090928,
					49.75673847079656
				],
				[
					-164.51101818722827,
					50.20499737593877
				],
				[
					-147.4771797918204,
					27.79205211882322
				],
				[
					-1.793035620569185,
					26.895534308538576
				],
				[
					0.4482589051424384,
					4.4825890514230196
				]
			]
		},
		{
			"type": "line",
			"version": 676,
			"versionNonce": 1237353187,
			"isDeleted": false,
			"id": "vRE5unLHRMUH24cRydgNZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.5911331085996,
			"y": 1071.1254942252315,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 191.42944046112157,
			"height": 228.91770588475777,
			"seed": 1320964657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531067,
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
					-68.86142372143115,
					0
				],
				[
					-122.0362682939649,
					-86.14324820750458
				],
				[
					-191.16356623825882,
					-85.07975131605392
				],
				[
					-191.1635662382588,
					142.77445767725317
				],
				[
					-116.18703539098624,
					141.97683500866515
				],
				[
					-69.12729794429379,
					71.52016595005783
				],
				[
					0.26587422286274887,
					71.52016595005784
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 375,
			"versionNonce": 312987853,
			"isDeleted": false,
			"id": "ZPUHiQn158KJrsM8juc-M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1533.9878549997359,
			"y": 224.94665831248352,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 897.9741460285975,
			"height": 515.8574881440877,
			"seed": 465584959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 298,
			"versionNonce": 689188483,
			"isDeleted": false,
			"id": "96vLIcXOKIeY45f-tm1TY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 451.0138596910058,
			"y": 435.07416069842617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 580.4738231240334,
			"height": 305.72998513294294,
			"seed": 399397087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false
		},
		{
			"type": "freedraw",
			"version": 279,
			"versionNonce": 1148071725,
			"isDeleted": false,
			"id": "ZXRq9TgJAtu_7Vq3RidAQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -189.99109571650877,
			"y": -217.22087357086804,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 571.6516842813203,
			"height": 0.2521128980965841,
			"seed": 760583391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					571.6516842813203,
					-0.2521128980965841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 284,
			"versionNonce": 607217187,
			"isDeleted": false,
			"id": "Z22P-mPwqkepJ2o5EMNKD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -186.60633812489255,
			"y": -221.16975742775358,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 571.6516842813203,
			"height": 0.2521128980965841,
			"seed": 484894033,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					571.6516842813203,
					-0.2521128980965841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 230,
			"versionNonce": 2124005773,
			"isDeleted": false,
			"id": "okP84GTyZIyyj8xX7bbQR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -188.05208455638535,
			"y": -224.5379139116524,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 571.6516842813203,
			"height": 0.2521128980965841,
			"seed": 287588415,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					571.6516842813203,
					-0.2521128980965841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 880,
			"versionNonce": 570862019,
			"isDeleted": false,
			"id": "OjRmotFOlpgB8xljJ9dea",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1645.4754754527542,
			"y": -2.838120900953953,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 590.2928711784268,
			"height": 353.3753329476045,
			"seed": 105191839,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					1.0717564901752574
				],
				[
					92.46630550312666,
					-9.555798346851162
				],
				[
					139.0604933958914,
					16.44093945276761
				],
				[
					134.49837145783556,
					102.25540312374665
				],
				[
					213.27948944939993,
					185.85335228647097
				],
				[
					375.3804047218089,
					301.2421545460922
				],
				[
					590.2928711784268,
					343.81953460075334
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 497,
			"versionNonce": 1717831661,
			"isDeleted": false,
			"id": "wzlwNhkF0b4JDJy2yTtW8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1497.40062623328,
			"y": -129.64779185547866,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 629.93235008519,
			"height": 278.66567020672306,
			"seed": 1401881512,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					83.30891868876066,
					21.231670110988432
				],
				[
					130.0788379526262,
					145.9677320130454
				],
				[
					347.85127452500046,
					245.4911856583036
				],
				[
					629.93235008519,
					278.66567020672306
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 711,
			"versionNonce": 666007907,
			"isDeleted": false,
			"id": "o0f1GC2cnpHZ-e0fnf9Q4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1402.7767682241729,
			"y": -208.64466123507998,
			"strokeColor": "#9c36b5",
			"backgroundColor": "#be4bdb",
			"width": 496.15867605164317,
			"height": 103.03032734110873,
			"seed": 1617535912,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					82.00969852093274,
					30.90909820233263
				],
				[
					126.0899114759342,
					85.59442579107493
				],
				[
					325.9885516207077,
					103.03032734110874
				],
				[
					496.15867605164317,
					100.65270440246776
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 637,
			"versionNonce": 1037468237,
			"isDeleted": false,
			"id": "5SBkg224",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -813.3734799576446,
			"y": -152.94293074809758,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 102.91842405977484,
			"height": 101.00366268191857,
			"seed": 63549,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5bb2314e17612e74757424160f3480a4c78b8b80",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 389,
			"versionNonce": 310596867,
			"isDeleted": false,
			"id": "aOlT8ogT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.56305845185444,
			"x": -1745.0127916942083,
			"y": -159.33127496088986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 392.7601013183594,
			"height": 45,
			"seed": 1431646936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531067,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Types of explanations",
			"rawText": "Types of explanations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Types of explanations",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 422,
			"versionNonce": 1238020269,
			"isDeleted": false,
			"id": "CjRDg49KaglOgtjpmZz0h",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1324.132601596917,
			"y": -284.2653760205405,
			"strokeColor": "#9c36b5",
			"backgroundColor": "#be4bdb",
			"width": 398.81845192973594,
			"height": 342.67513792254215,
			"seed": 1738388392,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
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
					-398.81845192973594,
					342.67513792254215
				]
			]
		},
		{
			"type": "line",
			"version": 482,
			"versionNonce": 301448355,
			"isDeleted": false,
			"id": "YaCaQ_3CywsXtgxntPcRb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1331.5720724404446,
			"y": -291.5634826644216,
			"strokeColor": "#9c36b5",
			"backgroundColor": "#be4bdb",
			"width": 377.8530098804076,
			"height": 350.52592088784746,
			"seed": 1146354392,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531067,
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
					-377.8530098804076,
					350.52592088784746
				]
			]
		},
		{
			"type": "text",
			"version": 578,
			"versionNonce": 2011829005,
			"isDeleted": false,
			"id": "eFPhTehy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1070.3066972407437,
			"y": -206.33463752763828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 439.3795166015625,
			"height": 50,
			"seed": 572217768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Generate an example of The features that\ndistinguish the current class from all others",
			"rawText": "Generate an example of The features that\ndistinguish the current class from all others",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generate an example of The features that\ndistinguish the current class from all others",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 513,
			"versionNonce": 1639854147,
			"isDeleted": false,
			"id": "FXuTwphC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -997.306970298574,
			"y": -116.09344858707591,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 67.12454223632812,
			"height": 19.286124088529103,
			"seed": 1537878744,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "L2G5tPJA9j6V46fow1Xe6",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 15.428899270823281,
			"fontFamily": 1,
			"text": "Pineapple",
			"rawText": "Pineapple",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Pineapple",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 1798,
			"versionNonce": 1152264557,
			"isDeleted": false,
			"id": "L2G5tPJA9j6V46fow1Xe6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -922.0042520944734,
			"y": -99.65618462769399,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 107.18087824270516,
			"height": 0.018160763297285835,
			"seed": 151634648,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FXuTwphC",
				"focus": 0.7048851852355466,
				"gap": 8.07908695118806
			},
			"endBinding": {
				"elementId": "_l08q0hIw5BRcEwag7FkQ",
				"focus": -0.04667336408066005,
				"gap": 3.5582367327482416
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					107.18087824270516,
					-0.018160763297285835
				]
			]
		},
		{
			"type": "rectangle",
			"version": 686,
			"versionNonce": 1135947747,
			"isDeleted": false,
			"id": "_l08q0hIw5BRcEwag7FkQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -811.26513711902,
			"y": -152.69648781090783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.8898840799461,
			"height": 101.29746998608742,
			"seed": 263445928,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "L2G5tPJA9j6V46fow1Xe6",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 427,
			"versionNonce": 1633711053,
			"isDeleted": false,
			"id": "4dw4FTZN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1063.2103726813664,
			"y": 23.811479901276243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 443.3995361328125,
			"height": 75,
			"seed": 1014537384,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Highlight features for a given input that\nstrongly swayed the output to be what it is\n(LRP Heatmap)",
			"rawText": "Highlight features for a given input that\nstrongly swayed the output to be what it is\n(LRP Heatmap)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Highlight features for a given input that\nstrongly swayed the output to be what it is\n(LRP Heatmap)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 419,
			"versionNonce": 971717507,
			"isDeleted": false,
			"id": "AKlh17-B-z1BXkClBmfIJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1036.3299232501843,
			"y": 115.12251854125356,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 58.98797537180936,
			"height": 78.74338221802853,
			"seed": 1898585768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2646750f6b6d22acba1c96599d79cde205e3ae60",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 967,
			"versionNonce": 437940781,
			"isDeleted": false,
			"id": "bf62TcW2OeO1s9thu-8jy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -977.7675685462002,
			"y": 148.8688628856172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 50.39154018075025,
			"height": 0.4036578629688147,
			"seed": 1435381672,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "H6HyCcjQ0bSAlP0Xu7EpI",
				"focus": -0.12101824628745826,
				"gap": 1
			},
			"endBinding": {
				"elementId": "wFsMbKkY",
				"focus": 0.035574577903870495,
				"gap": 3.437632420543821
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					50.39154018075025,
					0.4036578629688147
				]
			]
		},
		{
			"type": "rectangle",
			"version": 386,
			"versionNonce": 10408739,
			"isDeleted": false,
			"id": "H6HyCcjQ0bSAlP0Xu7EpI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1034.8993562035378,
			"y": 114.6657989600929,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 56.59579644138319,
			"height": 77.36116060332954,
			"seed": 262915496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bf62TcW2OeO1s9thu-8jy",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 446,
			"versionNonce": 2076550285,
			"isDeleted": false,
			"id": "0ChOS4BFV7j9UrcBDYBbj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -926.1868991428807,
			"y": 113.68230045297224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.36567361403334,
			"height": 78.04999179047941,
			"seed": 1944785576,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "bf62TcW2OeO1s9thu-8jy",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 991,
			"versionNonce": 1212053187,
			"isDeleted": false,
			"id": "wFsMbKkY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -923.9383959449061,
			"y": 128.00660744326777,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 152.04898410313797,
			"height": 45.46562759946773,
			"seed": 34175,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bf62TcW2OeO1s9thu-8jy",
					"type": "arrow"
				},
				{
					"id": "bYSK_2tYBmYk8N8uTA3kG",
					"type": "arrow"
				},
				{
					"id": "DRvB_pHVU9iCXuJU5Zohh",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a94abb57e2925fffb0c1acc67a41ef20cb7b6227",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 819,
			"versionNonce": 974883565,
			"isDeleted": false,
			"id": "bYSK_2tYBmYk8N8uTA3kG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -763.5351735654472,
			"y": 124.31847646881016,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 55.688720124382684,
			"height": 1.2317351159490215,
			"seed": 2029864959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wFsMbKkY",
				"focus": -1.159421104200581,
				"gap": 8.354238276321041
			},
			"endBinding": {
				"elementId": "0locD7NIqv5-JTWD3gnlr",
				"focus": -0.1101070777331549,
				"gap": 2.6813144345530304
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					31.32124195189155,
					0.532663260513516
				],
				[
					55.688720124382684,
					1.2317351159490215
				]
			]
		},
		{
			"type": "arrow",
			"version": 737,
			"versionNonce": 795387491,
			"isDeleted": false,
			"id": "DRvB_pHVU9iCXuJU5Zohh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -767.3291121401999,
			"y": 178.1533351837853,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 61.08557408991328,
			"height": 0.8165405985509153,
			"seed": 753376273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wFsMbKkY",
				"focus": 1.2035233820345852,
				"gap": 4.6811001410497965
			},
			"endBinding": {
				"elementId": "Dp1QVQMbURJ-N7L0HfHm2",
				"focus": 0.011997368681510835,
				"gap": 1.805461832205765
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					41.25349111915429,
					-0.20580882924977573
				],
				[
					61.08557408991328,
					0.6107317693011396
				]
			]
		},
		{
			"type": "image",
			"version": 527,
			"versionNonce": 1436919117,
			"isDeleted": false,
			"id": "mtPu2OmSsfvVi_cqUkjk2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -705.2455910725457,
			"y": 95.95080114517057,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 39.636093671600875,
			"height": 53.94560991725871,
			"seed": 473582463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bYSK_2tYBmYk8N8uTA3kG",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7f69a0d880f68b5f2bc447904883f3ffc7ea9754",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 393,
			"versionNonce": 2095833603,
			"isDeleted": false,
			"id": "p3qBRRVm4XZG3p0uVkoen",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -704.2392704140207,
			"y": 154.69064811033329,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 37.96682959506762,
			"height": 51.80635135068905,
			"seed": 2023211999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0a1244723d968856aaf3380630be993482a83ed9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 346,
			"versionNonce": 29193133,
			"isDeleted": false,
			"id": "Dp1QVQMbURJ-N7L0HfHm2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -704.4380762180808,
			"y": 154.0144438950616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.36444120318771,
			"height": 51.86872450670978,
			"seed": 163844177,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DRvB_pHVU9iCXuJU5Zohh",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 344,
			"versionNonce": 432449955,
			"isDeleted": false,
			"id": "0locD7NIqv5-JTWD3gnlr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -705.1651390065115,
			"y": 96.49475205576152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.89901885131522,
			"height": 53.40330215483729,
			"seed": 1406851121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bYSK_2tYBmYk8N8uTA3kG",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 1250719245,
			"isDeleted": false,
			"id": "37xIcnLR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -662.0182866992429,
			"y": 117.73364268972227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.456588745117188,
			"height": 14.320789352920269,
			"seed": 871132095,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 11.456631482336215,
			"fontFamily": 1,
			"text": "Cat",
			"rawText": "Cat",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cat",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 1260879171,
			"isDeleted": false,
			"id": "9qVqkONj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -663.8522375559844,
			"y": 171.9167576536192,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.67131042480469,
			"height": 13.54100989645607,
			"seed": 1499603935,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 10.832807917164855,
			"fontFamily": 1,
			"text": "Person",
			"rawText": "Person",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Person",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 294,
			"versionNonce": 2064395373,
			"isDeleted": false,
			"id": "gGlgagN6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.21774104197895028,
			"x": -1300.0763204419252,
			"y": -182.52285552776524,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 127.65254211425781,
			"height": 35,
			"seed": 875281311,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Generate",
			"rawText": "Generate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generate",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 329,
			"versionNonce": 745331939,
			"isDeleted": false,
			"id": "DwTKgcSG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.38546128348700304,
			"x": -1353.2638861546568,
			"y": -15.68986295863121,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 136.50057983398438,
			"height": 35,
			"seed": 1185129055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Elaborate",
			"rawText": "Elaborate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Elaborate",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 222,
			"versionNonce": 1124472525,
			"isDeleted": false,
			"id": "yejqnjWY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5508735539646032,
			"x": -1459.522782306307,
			"y": 153.42402998575642,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 185.0247802734375,
			"height": 35,
			"seed": 1879116081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Conceptualize",
			"rawText": "Conceptualize",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conceptualize",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 334,
			"versionNonce": 1764051075,
			"isDeleted": false,
			"id": "tHj9Hsgg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1051.5099174343247,
			"y": 270.8966672849025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 369.59954833984375,
			"height": 100,
			"seed": 1111415455,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Generate Concept Activation Vectors\nthat highlight mid-level concepts that\nresult in the prediction for a given\ninput",
			"rawText": "Generate Concept Activation Vectors\nthat highlight mid-level concepts that\nresult in the prediction for a given\ninput",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generate Concept Activation Vectors\nthat highlight mid-level concepts that\nresult in the prediction for a given\ninput",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 477,
			"versionNonce": 487830829,
			"isDeleted": false,
			"id": "tbXCJ89jL_CMXKn6yBkBj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -936.1957786538752,
			"y": 548.5234314342443,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 71.29344882348774,
			"height": 59.64550507204467,
			"seed": 81216511,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cf32ef4a285d2f19ff5d5ba85a7461a7e1e20171",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 445,
			"versionNonce": 923746339,
			"isDeleted": false,
			"id": "CtRJueq1rth8694j_4iwr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -936.6884863952047,
			"y": 548.0525503158196,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 72.81663622967059,
			"height": 59.75318654062664,
			"seed": 1950954353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 353,
			"versionNonce": 1956546445,
			"isDeleted": false,
			"id": "B2HYKTsr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -915.2532814954172,
			"y": 536.7774556165856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.783050537109375,
			"height": 11.275094975224086,
			"seed": 1604851697,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kcuJ_aqIz1JoJX1zn6Zqy",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 9.020075980179268,
			"fontFamily": 1,
			"text": "Input",
			"rawText": "Input",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Input",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 537,
			"versionNonce": 270091203,
			"isDeleted": false,
			"id": "0JYcNOGgALV27m4bPjv1K",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -809.3014222988079,
			"y": 456.91588451749817,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 39.83196775159785,
			"height": 42.299434780457894,
			"seed": 998757617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "79a2a750811e26419c6d86cf486694eddda9dbc6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 552,
			"versionNonce": 199233005,
			"isDeleted": false,
			"id": "714il1rW6dh3cof6JM1mg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -809.8380196449606,
			"y": 456.370033448786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.765540109658716,
			"height": 43.23617890418347,
			"seed": 928802687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "biZ-L771tNs_QVgNuNZ3l",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 622,
			"versionNonce": 744608611,
			"isDeleted": false,
			"id": "VUXJ3ULZMpkE_Ft0MAVoP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -811.6003124269638,
			"y": 401.86284137104565,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 43.278375780087174,
			"height": 37.09575066864615,
			"seed": 1810864017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2046eabfb19e5a1890fa740b7637ac4280251907",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 590,
			"versionNonce": 568445005,
			"isDeleted": false,
			"id": "gtDFzLWt9Ryyxnldpqlbg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -811.8868053030126,
			"y": 402.32802182553087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 43.851361532184654,
			"height": 37.140599081349,
			"seed": 56178175,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2kAY3WdXjpLiDFj8EpbzF",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 372,
			"versionNonce": 1010265859,
			"isDeleted": false,
			"id": "Dz8Abdin",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -809.231133114298,
			"y": 443.5779176136222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 31.60235595703125,
			"height": 11.615480004608074,
			"seed": 1381456497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2kAY3WdXjpLiDFj8EpbzF",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 9.29238400368646,
			"fontFamily": 1,
			"text": "Stripes",
			"rawText": "Stripes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Stripes",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 411,
			"versionNonce": 1484601005,
			"isDeleted": false,
			"id": "E8O9GDnF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -801.235368534632,
			"y": 385.5067565381343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.355484008789062,
			"height": 16.904777987352045,
			"seed": 770610751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 13.523822389881635,
			"fontFamily": 1,
			"text": "Cat",
			"rawText": "Cat",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cat",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1310,
			"versionNonce": 1645778595,
			"isDeleted": false,
			"id": "Fyl3xaww0Cm3pCf0APNpO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -875.7909196054351,
			"y": 449.45623871327064,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 137.52757932855513,
			"height": 58.23550824470397,
			"seed": 812892465,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
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
					-99.21673207251943,
					11.257719392638299
				],
				[
					-64.6586823488064,
					58.23550824470397
				],
				[
					38.310847256035686,
					48.757552904705484
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1550,
			"versionNonce": 1515968781,
			"isDeleted": false,
			"id": "KvEgCL5GHc51iWFzACDxF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -879.351550653764,
			"y": 440.3020097368691,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 118.69712708834285,
			"height": 48.249662359742906,
			"seed": 742043441,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
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
					-85.63185008853475,
					9.327318950374675
				],
				[
					-55.80553277816278,
					48.249662359742906
				],
				[
					33.065276999808106,
					40.39692510717094
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1674,
			"versionNonce": 1823722051,
			"isDeleted": false,
			"id": "hPUOB9RRBxCU7a4-b6ozo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -881.6564778795,
			"y": 432.4596206949334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 102.14915390755023,
			"height": 42.25815482876629,
			"seed": 1587356561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
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
					-73.69362046624515,
					8.169078685016501
				],
				[
					-48.025492246385035,
					42.25815482876629
				],
				[
					28.455533441305075,
					35.38054842865021
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1478,
			"versionNonce": 1089941357,
			"isDeleted": false,
			"id": "G01sNtKyBdj1JBHbfM4J1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -883.6565850419339,
			"y": 422.51465706260126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 85.31587084433012,
			"height": 34.84009788565231,
			"seed": 1962100049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
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
					-61.54955929874365,
					6.735066927906373
				],
				[
					-40.11131308474904,
					34.84009788565231
				],
				[
					23.766311545586476,
					29.169796350481654
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1489,
			"versionNonce": 1357351395,
			"isDeleted": false,
			"id": "k9drywa26Gv7yPEmBj1ie",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -885.817251274747,
			"y": 411.5002425109734,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 66.48541860411781,
			"height": 30.275139766813,
			"seed": 653226879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
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
					-47.96467731475892,
					5.852598154300149
				],
				[
					-31.258163514105398,
					30.275139766813
				],
				[
					18.520741289358885,
					25.347795071608743
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 917,
			"versionNonce": 983087565,
			"isDeleted": false,
			"id": "iwtPJyuS62XrqrD_UFs3W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -899.1381978274542,
			"y": 425.06580623570574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 0,
			"height": 26.323604455015754,
			"seed": 1038757841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "gRTZrrsJ",
				"focus": 0.053781218960057484,
				"gap": 1.0687284634661012
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					-26.323604455015754
				]
			]
		},
		{
			"type": "text",
			"version": 452,
			"versionNonce": 1673680259,
			"isDeleted": false,
			"id": "gRTZrrsJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -914.3959261524196,
			"y": 386.10606584046786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 32.23597717285156,
			"height": 11.56740747675606,
			"seed": 249656607,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iwtPJyuS62XrqrD_UFs3W",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 9.253925981404848,
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
			"type": "arrow",
			"version": 458,
			"versionNonce": 1884944429,
			"isDeleted": false,
			"id": "kcuJ_aqIz1JoJX1zn6Zqy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -901.905308580656,
			"y": 531.9671976094442,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 0,
			"height": 27.462797526063703,
			"seed": 251102737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "B2HYKTsr",
				"focus": 0.12191704808497375,
				"gap": 4.810258007141499
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					-27.462797526063703
				]
			]
		},
		{
			"type": "arrow",
			"version": 490,
			"versionNonce": 1417850147,
			"isDeleted": false,
			"id": "biZ-L771tNs_QVgNuNZ3l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -847.5863828676133,
			"y": 475.84913131869075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 35.29222616109238,
			"height": 1.3786025844176426,
			"seed": 223285215,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "714il1rW6dh3cof6JM1mg",
				"focus": -0.0035276717067666305,
				"gap": 2.4561370615604687
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					21.923609387809776,
					0.8873275586837508
				],
				[
					35.29222616109238,
					1.3786025844176426
				]
			]
		},
		{
			"type": "arrow",
			"version": 561,
			"versionNonce": 740584077,
			"isDeleted": false,
			"id": "2kAY3WdXjpLiDFj8EpbzF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -866.7809358293969,
			"y": 434.4910537861606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 47.52818048850911,
			"height": 5.613089071564389,
			"seed": 622377681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Dz8Abdin",
				"focus": 3.1733054406551213,
				"gap": 14.699952899025988
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					31.0533031215506,
					-4.207791345906344
				],
				[
					47.52818048850911,
					-5.613089071564389
				]
			]
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 1721176259,
			"isDeleted": false,
			"id": "6VyG0BVo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -763.8842414074985,
			"y": 413.8120150198955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 28.553421020507812,
			"height": 15.379563504585922,
			"seed": 1133356369,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 12.303650803668738,
			"fontFamily": 1,
			"text": "58%",
			"rawText": "58%",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "58%",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 1051824365,
			"isDeleted": false,
			"id": "1wrzhvSy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -766.175020973904,
			"y": 470.3347209810199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 28.172225952148438,
			"height": 15.379563504585922,
			"seed": 1775215999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 12.303650803668738,
			"fontFamily": 1,
			"text": "42%",
			"rawText": "42%",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "42%",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 928,
			"versionNonce": 1805516899,
			"isDeleted": false,
			"id": "hzAaX6ZZtLgdzTl8R5ePN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -576.4429488711489,
			"y": -549.7916724282871,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#eebefa",
			"width": 352.61272942742136,
			"height": 257.5405823906474,
			"seed": 774478504,
			"groupIds": [
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 629861197,
			"isDeleted": false,
			"id": "P89AhelJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.5800850603262875,
			"x": -541.3795543021,
			"y": -487.4776007894366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.034698486328125,
			"height": 53.862557201428714,
			"seed": 45882,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "E",
			"rawText": "E",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "E",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 2103835651,
			"isDeleted": false,
			"id": "XEd24d7Z",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.714885102372729,
			"x": -518.0278570556441,
			"y": -504.70839258427037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.209945678710938,
			"height": 53.862557201428714,
			"seed": 1107,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1896479149,
			"isDeleted": false,
			"id": "SCAnYY3J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.827285157304369,
			"x": -496.9289227093956,
			"y": -516.568509693358,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.237548828125,
			"height": 53.862557201428714,
			"seed": 79682,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "p",
			"rawText": "p",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 2012054435,
			"isDeleted": false,
			"id": "4N8gsCgJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.925885163407885,
			"x": -477.4253899328735,
			"y": -524.9666344266848,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.329559326171875,
			"height": 53.862557201428714,
			"seed": 38137,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1784167437,
			"isDeleted": false,
			"id": "nW0y4dmj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.978485176293084,
			"x": -466.709103870422,
			"y": -528.6492081986714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.733154296875,
			"height": 53.862557201428714,
			"seed": 33517,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 862132035,
			"isDeleted": false,
			"id": "GlHDRZ8H",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.111885224443041,
			"x": -438.79890884133647,
			"y": -535.420167853687,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.434127807617188,
			"height": 53.862557201428714,
			"seed": 84227,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 2037330541,
			"isDeleted": false,
			"id": "To1MKy27",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.155685239362746,
			"x": -429.4680514008277,
			"y": -536.8246638695659,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.117507934570312,
			"height": 53.862557201428714,
			"seed": 35282,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 2116368099,
			"isDeleted": false,
			"id": "Ga48Ye6A",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.249085304466912,
			"x": -409.4179281728127,
			"y": -538.4482493436817,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.733154296875,
			"height": 53.862557201428714,
			"seed": 97785,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1259887821,
			"isDeleted": false,
			"id": "8Mkuaecl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.0993000454372829,
			"x": -380.71342330573816,
			"y": -537.5121502316576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.883712768554688,
			"height": 53.862557201428714,
			"seed": 93437,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "b",
			"rawText": "b",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "b",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1455579779,
			"isDeleted": false,
			"id": "D5NbcNG1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.2009000990125867,
			"x": -359.0791022056744,
			"y": -534.2402279140169,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.329559326171875,
			"height": 53.862557201428714,
			"seed": 65389,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 921516845,
			"isDeleted": false,
			"id": "cTyfdkgd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.2535001118977864,
			"x": -348.0389301326224,
			"y": -531.6878295995257,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.563766479492188,
			"height": 53.862557201428714,
			"seed": 74288,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1710823971,
			"isDeleted": false,
			"id": "LIGn1RYT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.3629001193576388,
			"x": -325.5904766664321,
			"y": -524.5414974119767,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.539093017578125,
			"height": 53.862557201428714,
			"seed": 76996,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1700220301,
			"isDeleted": false,
			"id": "ugDhIj99",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.46290011935763875,
			"x": -305.86429861507986,
			"y": -515.8997836938331,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.259292602539062,
			"height": 53.862557201428714,
			"seed": 75018,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 951573955,
			"isDeleted": false,
			"id": "iRAO5FXw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5941001892089842,
			"x": -281.4713565435147,
			"y": -501.65664629051287,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.477615356445312,
			"height": 53.862557201428714,
			"seed": 92120,
			"groupIds": [
				"VuMYhKev",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 43.090045761142974,
			"fontFamily": 1,
			"text": "I",
			"rawText": "I",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "I",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 898634733,
			"isDeleted": false,
			"id": "Py8PA51g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7982683817545573,
			"x": -556.2986002716635,
			"y": -385.5856338210281,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.986770629882812,
			"height": 23.938914311746096,
			"seed": 31414,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "F",
			"rawText": "F",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "F",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 974990691,
			"isDeleted": false,
			"id": "WKEf1JvT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7472460428873697,
			"x": -548.4287532383976,
			"y": -377.9122781192414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.1918182373046875,
			"height": 23.938914311746096,
			"seed": 54816,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1671499341,
			"isDeleted": false,
			"id": "hNDOHdBG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.727779303656684,
			"x": -545.3245566887565,
			"y": -375.09199521188606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.938720703125,
			"height": 23.938914311746096,
			"seed": 74788,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1836550403,
			"isDeleted": false,
			"id": "tHWkQyey",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.6862681070963541,
			"x": -538.5252411005051,
			"y": -369.2828863535309,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.766860961914062,
			"height": 23.938914311746096,
			"seed": 92764,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1852030125,
			"isDeleted": false,
			"id": "lDox6imr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.6269790649414062,
			"x": -528.4091043632974,
			"y": -361.4862900081551,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.0340118408203125,
			"height": 23.938914311746096,
			"seed": 95093,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1749381283,
			"isDeleted": false,
			"id": "vcogVMWH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.6036012437608507,
			"x": -524.2961520730051,
			"y": -358.57916283808873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.0340118408203125,
			"height": 23.938914311746096,
			"seed": 56869,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1031905037,
			"isDeleted": false,
			"id": "4zfLaj7x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5802234225802951,
			"x": -520.1163675332465,
			"y": -355.7689731422939,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.977005004882812,
			"height": 23.938914311746096,
			"seed": 18576,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 204825667,
			"isDeleted": false,
			"id": "9OC4VjFk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5385344611273871,
			"x": -512.5039996434227,
			"y": -351.0029860995143,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.2445526123046875,
			"height": 23.938914311746096,
			"seed": 6451,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": ".",
			"rawText": ".",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ".",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 125056365,
			"isDeleted": false,
			"id": "sbB9WAuY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5141788906521267,
			"x": -507.96697181610324,
			"y": -348.3668216519938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.2445526123046875,
			"height": 23.938914311746096,
			"seed": 67266,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": ".",
			"rawText": ".",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ".",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 19260387,
			"isDeleted": false,
			"id": "bUGfZaSe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.4898233201768663,
			"x": -503.36709064920603,
			"y": -345.8419300205238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.2445526123046875,
			"height": 23.938914311746096,
			"seed": 28418,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": ".",
			"rawText": ".",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ".",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 2005204941,
			"isDeleted": false,
			"id": "Xjj0TeRt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.46546774970160587,
			"x": -498.70708462889996,
			"y": -343.42980888116256,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.570358276367188,
			"height": 23.938914311746096,
			"seed": 37462,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1864724355,
			"isDeleted": false,
			"id": "ePB17FH3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.42102322048611107,
			"x": -490.0575537296488,
			"y": -339.32343194026225,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.766860961914062,
			"height": 23.938914311746096,
			"seed": 52189,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 332234285,
			"isDeleted": false,
			"id": "fIHcq1a2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.36173417833116317,
			"x": -478.25135173351293,
			"y": -334.45139627895503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.938720703125,
			"height": 23.938914311746096,
			"seed": 69731,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 2020771619,
			"isDeleted": false,
			"id": "LalN8Mc9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.3202229817708333,
			"x": -469.82326201082344,
			"y": -331.46078734043545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.570358276367188,
			"height": 23.938914311746096,
			"seed": 22544,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1664561293,
			"isDeleted": false,
			"id": "muas2aKL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.2757784525553385,
			"x": -460.67047134291766,
			"y": -328.64953506656275,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.469970703125,
			"height": 23.938914311746096,
			"seed": 49183,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1937484483,
			"isDeleted": false,
			"id": "Dr6GYyxS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.22715615166558156,
			"x": -450.52526239164024,
			"y": -326.04317531537356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.757080078125,
			"height": 23.938914311746096,
			"seed": 23509,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 1400608493,
			"isDeleted": false,
			"id": "Lff7VskO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.17720048692491316,
			"x": -439.9826247885161,
			"y": -323.8821573691381,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.436370849609375,
			"height": 23.938914311746096,
			"seed": 93416,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "p",
			"rawText": "p",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 1692359267,
			"isDeleted": false,
			"id": "SwfdKQMZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.133378177218967,
			"x": -430.65545607223623,
			"y": -322.4219914647523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.0340118408203125,
			"height": 23.938914311746096,
			"seed": 7181,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 1596207437,
			"isDeleted": false,
			"id": "5UG4PHxD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.11000035603841143,
			"x": -425.65605984669145,
			"y": -321.81059772487174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.766860961914062,
			"height": 23.938914311746096,
			"seed": 21344,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 963384835,
			"isDeleted": false,
			"id": "eLPjqHKQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.05071131388346352,
			"x": -412.9253054992556,
			"y": -320.7853997908818,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.938720703125,
			"height": 23.938914311746096,
			"seed": 29477,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1938456493,
			"isDeleted": false,
			"id": "audeMIsP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.00920011732313366,
			"x": -403.986362988422,
			"y": -320.5175472477354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.766860961914062,
			"height": 23.938914311746096,
			"seed": 87470,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 1075862947,
			"isDeleted": false,
			"id": "a7bmFY1f",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.233096382347772,
			"x": -391.21706522444003,
			"y": -320.7786443051249,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.81451416015625,
			"height": 23.938914311746096,
			"seed": 36877,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "t",
			"rawText": "t",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 383255053,
			"isDeleted": false,
			"id": "ik20hjrS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.182874027882711,
			"x": -380.4283620035059,
			"y": -321.59148869311593,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.1918182373046875,
			"height": 23.938914311746096,
			"seed": 16903,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1680519491,
			"isDeleted": false,
			"id": "XXX9AtUN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.163407288652025,
			"x": -376.2596837774596,
			"y": -322.0520901955149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.603958129882812,
			"height": 23.938914311746096,
			"seed": 75855,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "o",
			"rawText": "o",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1309030509,
			"isDeleted": false,
			"id": "bMnCq3Rl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.1141627682527195,
			"x": -365.76142357915546,
			"y": -323.57866711579203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.938720703125,
			"height": 23.938914311746096,
			"seed": 22625,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 652841187,
			"isDeleted": false,
			"id": "MOSCbfV5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.07265157169239,
			"x": -356.9790297200833,
			"y": -325.265675207352,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.570358276367188,
			"height": 23.938914311746096,
			"seed": 7776,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1121886925,
			"isDeleted": false,
			"id": "6hluPbPm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.028207042476895,
			"x": -347.66242402189323,
			"y": -327.47419838411747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.302383422851562,
			"height": 23.938914311746096,
			"seed": 62951,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "f",
			"rawText": "f",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 1508605059,
			"isDeleted": false,
			"id": "laRRDAp8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.985006952280497,
			"x": -338.7093774535456,
			"y": -330.01555048062966,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.603958129882812,
			"height": 23.938914311746096,
			"seed": 66944,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "o",
			"rawText": "o",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 704299309,
			"isDeleted": false,
			"id": "kqjyVRui",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.935762431881193,
			"x": -328.64863653278803,
			"y": -333.38087311155437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.230514526367188,
			"height": 23.938914311746096,
			"seed": 41387,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 418313251,
			"isDeleted": false,
			"id": "ENmuaWZr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.897540097761183,
			"x": -320.96110374809655,
			"y": -336.3319718840768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.570358276367188,
			"height": 23.938914311746096,
			"seed": 27508,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 1757680525,
			"isDeleted": false,
			"id": "1tv4I3vd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.8530955685456885,
			"x": -312.1717400303865,
			"y": -340.1298399433514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.81451416015625,
			"height": 23.938914311746096,
			"seed": 19718,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "t",
			"rawText": "t",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 65173443,
			"isDeleted": false,
			"id": "TCGbXPhl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.802873214080628,
			"x": -302.4541573782708,
			"y": -344.8864585519624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.455520629882812,
			"height": 23.938914311746096,
			"seed": 32294,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "h",
			"rawText": "h",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 2071206381,
			"isDeleted": false,
			"id": "deNDEtfT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.7589619795428675,
			"x": -294.162597909067,
			"y": -349.44060296025896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.1918182373046875,
			"height": 23.938914311746096,
			"seed": 80863,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 954500963,
			"isDeleted": false,
			"id": "VHcmVfyY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.7394952403121815,
			"x": -290.55236174770187,
			"y": -351.5751349360082,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.393417358398438,
			"height": 23.938914311746096,
			"seed": 82992,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 454317133,
			"isDeleted": false,
			"id": "2JXFD3Q4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.691228469207581,
			"x": -281.78601802908565,
			"y": -357.1672036794763,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.570358276367188,
			"height": 23.938914311746096,
			"seed": 9902,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 239313667,
			"isDeleted": false,
			"id": "rEmTUCrG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.646783939992086,
			"x": -273.9610467703138,
			"y": -362.68504212920027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.393417358398438,
			"height": 23.938914311746096,
			"seed": 16937,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 595477165,
			"isDeleted": false,
			"id": "0Fh6zC84",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.5985171688874855,
			"x": -265.75005669784383,
			"y": -369.0646704141706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.455520629882812,
			"height": 23.938914311746096,
			"seed": 67733,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "h",
			"rawText": "h",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 209603235,
			"isDeleted": false,
			"id": "NLbCIpjf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.554605934349725,
			"x": -258.55523187446175,
			"y": -375.2067128663038,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.1918182373046875,
			"height": 23.938914311746096,
			"seed": 12713,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 962290957,
			"isDeleted": false,
			"id": "wjnav8Mx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.535139195119039,
			"x": -255.45329273950836,
			"y": -378.0294784427145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.81451416015625,
			"height": 23.938914311746096,
			"seed": 17232,
			"groupIds": [
				"8QNctGWb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "t",
			"rawText": "t",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 444,
			"versionNonce": 675479107,
			"isDeleted": false,
			"id": "vElZkaDJuaHQjVHSKB0U5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -334.27176210419964,
			"y": -435.7796175152924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.13746609275459,
			"height": 20.160906620187234,
			"seed": 1564216543,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 481,
			"versionNonce": 807746413,
			"isDeleted": false,
			"id": "Ono3HCLyx-N-s85zJDnlu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.3566864420895,
			"y": -415.21811141253704,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.2015782705878715,
			"height": 29.228849235242315,
			"seed": 1829050623,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					-0.2015782705878715,
					29.228849235242315
				]
			]
		},
		{
			"type": "line",
			"version": 474,
			"versionNonce": 1013988835,
			"isDeleted": false,
			"id": "jcYbePpiJp6JhWVEiRDoy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.53602851868436,
			"y": -386.0927534016215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.690101829271727,
			"height": 15.221861518417654,
			"seed": 337092895,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					-8.690101829271727,
					15.221861518417654
				]
			]
		},
		{
			"type": "line",
			"version": 493,
			"versionNonce": 807749069,
			"isDeleted": false,
			"id": "FZ_SC3ctOyT2stZBvbGPd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.5605502802496,
			"y": -386.0114983712877,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.3894018622002875,
			"height": 14.796468783248939,
			"seed": 602154303,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					7.3894018622002875,
					14.796468783248939
				]
			]
		},
		{
			"type": "line",
			"version": 531,
			"versionNonce": 1142196611,
			"isDeleted": false,
			"id": "b6Dib95cC_6NlRbpWqw-m",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.3675179338463,
			"y": -408.8790054448124,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.969073389375218,
			"height": 12.366347943078857,
			"seed": 1808475487,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					8.79213623842807,
					0.9011456147573188
				],
				[
					10.969073389375218,
					8.738119358166985
				],
				[
					1.1002916384148909,
					12.366347943078857
				]
			]
		},
		{
			"type": "line",
			"version": 497,
			"versionNonce": 477430829,
			"isDeleted": false,
			"id": "UhVomyfS2fjcwSNsyDIST",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.13800115581023,
			"y": -408.558376403641,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.07752690945807,
			"height": 11.90058975851097,
			"seed": 2065506687,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					-14.07752690945807,
					-2.031808007550649
				],
				[
					-7.5467154566167105,
					-11.90058975851097
				]
			]
		},
		{
			"type": "ellipse",
			"version": 457,
			"versionNonce": 1416519971,
			"isDeleted": false,
			"id": "2W8VTNAiLgF9xh79hzDYD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.18173017320071327,
			"x": -320.98440035713975,
			"y": -427.8461671649998,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.5972430783897158,
			"height": 2.6354510793430177,
			"seed": 588945823,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 462,
			"versionNonce": 956167821,
			"isDeleted": false,
			"id": "Kt2acXy4Ho4NAxJLFPqqx",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.2801206661986875,
			"x": -327.69282128637644,
			"y": -429.5695785067895,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.1180701548727878,
			"height": 2.715313233262497,
			"seed": 955518399,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 464,
			"versionNonce": 1458324675,
			"isDeleted": false,
			"id": "kNXGLRvlhCnYMjlaLZjjT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -328.0122699020543,
			"y": -420.7384354661656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.385526161545961,
			"height": 1.5972430783897025,
			"seed": 399113695,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					4.3924184655716845,
					-0.9583458470338228
				],
				[
					8.385526161545961,
					0.6388972313558797
				]
			]
		},
		{
			"type": "line",
			"version": 478,
			"versionNonce": 276405485,
			"isDeleted": false,
			"id": "oPfgr7NjHRsUTOEVNAmZD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -318.24194483360566,
			"y": -428.55217648523364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.1211573944919424,
			"height": 0.8912337581558412,
			"seed": 1655499263,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					-2.1211573944919424,
					-0.8912337581558412
				]
			]
		},
		{
			"type": "line",
			"version": 535,
			"versionNonce": 53261411,
			"isDeleted": false,
			"id": "XsU3-fsJCJvvJ3zQyrwX1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.25977048531880786,
			"x": -324.40572291063603,
			"y": -430.4816182443429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 3.774327213613302,
			"height": 0.8241991125712358,
			"seed": 110973471,
			"groupIds": [
				"vAQ6Q2UZwGVEaXxqbdRix",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531068,
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
					-1.7793380825213367,
					-0.8241991125712358
				],
				[
					-3.774327213613302,
					-0.007978471062609625
				]
			]
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 443643725,
			"isDeleted": false,
			"id": "8eh3jAi0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -310.6564583162964,
			"y": -450.3916231111728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.919570922851562,
			"height": 23.938914311746096,
			"seed": 622107967,
			"groupIds": [
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531068,
			"link": null,
			"locked": false,
			"fontSize": 19.15113144939688,
			"fontFamily": 1,
			"text": "?",
			"rawText": "?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "?",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 1348,
			"versionNonce": 419311619,
			"isDeleted": false,
			"id": "pcbyajo8mocj-A5yJ2awu",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -482.6778729023768,
			"y": -423.61540785581565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.795921668161782,
			"height": 6.7564654457402105,
			"seed": 1748330577,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "Kb1MiUDueptGN74atYvDs",
					"type": "arrow"
				}
			],
			"updated": 1716566531068,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1327,
			"versionNonce": 557778349,
			"isDeleted": false,
			"id": "YrMPX6Za1-FCSj3JOrs--",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -482.80376063004445,
			"y": -414.0524106095373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.795921668161782,
			"height": 6.7564654457402105,
			"seed": 2129016369,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "Kb1MiUDueptGN74atYvDs",
					"type": "arrow"
				}
			],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1400,
			"versionNonce": 1516189603,
			"isDeleted": false,
			"id": "7vx9acJwh-d7UyuzQnHmB",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -482.6778729023768,
			"y": -404.54138617437985,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.795921668161782,
			"height": 6.7564654457402105,
			"seed": 100812817,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1360,
			"versionNonce": 1745602573,
			"isDeleted": false,
			"id": "aleXux65QuzNLUNxi7Hac",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -482.6778729023768,
			"y": -395.03036173922254,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.795921668161782,
			"height": 6.7564654457402105,
			"seed": 1468079601,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1272,
			"versionNonce": 1165904707,
			"isDeleted": false,
			"id": "YM87xzrqTHhkWBBq7OHZW",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -453.85994019043324,
			"y": -438.4755553676237,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 577386449,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1372,
			"versionNonce": 282148461,
			"isDeleted": false,
			"id": "H1ZgG0yMNwOQuj0KUJEBB",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -453.68132556753886,
			"y": -423.8004283566559,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 1221924273,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1378,
			"versionNonce": 247065315,
			"isDeleted": false,
			"id": "jeVq-NMsSMqt_qvbGIubS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -453.5345382085828,
			"y": -408.5309549740512,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 2112436113,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1374,
			"versionNonce": 1113123021,
			"isDeleted": false,
			"id": "WiOp0G15rOFhDdhhRRsJ7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -453.24096369492025,
			"y": -393.7054420340963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 601759089,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1390,
			"versionNonce": 1520473731,
			"isDeleted": false,
			"id": "oq8YZbzV4OXH2uelf8ryF",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -453.24096365959844,
			"y": -378.95639566038665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 1778075473,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1386,
			"versionNonce": 238831405,
			"isDeleted": false,
			"id": "TDFF-ZjkRSfoejTtFhEVD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -434.13526711025855,
			"y": -438.2905349539701,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 714618161,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1489,
			"versionNonce": 938528291,
			"isDeleted": false,
			"id": "RouqXkMf4G_FL1LXQ1P7o",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -434.13526721238327,
			"y": -423.61540794300237,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 152856337,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1491,
			"versionNonce": 384096653,
			"isDeleted": false,
			"id": "IDS_fKeHYYt3OGiUwM5-U",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -433.9884798534272,
			"y": -408.3459345603978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 1342135537,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1491,
			"versionNonce": 1503203779,
			"isDeleted": false,
			"id": "HkKTZPSBQ_ZeqiaPaBqau",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -433.69490533976466,
			"y": -393.5204216204426,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 248026833,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1507,
			"versionNonce": 1972117485,
			"isDeleted": false,
			"id": "UOjM8cLu7hTBEzsxBIgGc",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -433.6949053044428,
			"y": -378.7713752467331,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 2014287025,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1315,
			"versionNonce": 280486243,
			"isDeleted": false,
			"id": "A3M8ovS1fZO9iYfCuXnK_",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -414.58920873303606,
			"y": -438.2905348925901,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 2138822289,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1414,
			"versionNonce": 1614518861,
			"isDeleted": false,
			"id": "dHiqgsrzc0rR1V3IdfU5V",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -414.589208835161,
			"y": -423.7940226066415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 935648369,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1415,
			"versionNonce": 110869763,
			"isDeleted": false,
			"id": "STUMQ_Z8hINTmkA6FpWHU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -414.4424214762049,
			"y": -408.3459344990177,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 1890723409,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1416,
			"versionNonce": 265078957,
			"isDeleted": false,
			"id": "3XKkoDDrCJLbeBO34NMnL",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -414.1488469625424,
			"y": -393.5204215590626,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 354104369,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1441,
			"versionNonce": 918758563,
			"isDeleted": false,
			"id": "UgGRv_osDR6j9uF9usx4p",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -414.02295919955293,
			"y": -378.8972629130206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 1223132689,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 985,
			"versionNonce": 1709779725,
			"isDeleted": false,
			"id": "hznCypl52dhrg77TAr_oi",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.08008264697423,
			"y": -433.65155612726613,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.964686129948861,
			"height": 0.14872665865594847,
			"seed": 1192139761,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.964686129948861,
					-0.14872665865594847
				]
			]
		},
		{
			"type": "line",
			"version": 1017,
			"versionNonce": 685545539,
			"isDeleted": false,
			"id": "7AL9YoetPsHp70nabLNlI",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.9313559883184,
			"y": -433.7011316801514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.766383918407602,
			"height": 15.219694735792558,
			"seed": 2140665297,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.766383918407602,
					15.219694735792558
				]
			]
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 1393181037,
			"isDeleted": false,
			"id": "peFSb35zHwzJkGMdSJhHo",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.1801709323265,
			"y": -433.949926901909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.112264506406008,
			"height": 30.780313892306005,
			"seed": 1973097393,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.112264506406008,
					30.780313892306005
				]
			]
		},
		{
			"type": "line",
			"version": 1024,
			"versionNonce": 1791399907,
			"isDeleted": false,
			"id": "ui9rhRWvhOhN3sIWBq1Ni",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.09146685770895,
			"y": -433.68381467805625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.467080804876396,
			"height": 44.52944545803347,
			"seed": 1564439953,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.467080804876396,
					44.52944545803347
				]
			]
		},
		{
			"type": "line",
			"version": 1031,
			"versionNonce": 2088340429,
			"isDeleted": false,
			"id": "ODFqyjwJE_AT3Bvn9M_Yb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.09146685770895,
			"y": -433.949926901909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.467080804876396,
			"height": 61.20581148614165,
			"seed": 2042403697,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.467080804876396,
					61.20581148614165
				]
			]
		},
		{
			"type": "line",
			"version": 1014,
			"versionNonce": 1250927491,
			"isDeleted": false,
			"id": "E51HZxWemqUUASpqKGWqi",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.09146685770895,
			"y": -419.4911627392408,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.846152282553215,
			"height": 14.458764162668235,
			"seed": 995755345,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.846152282553215,
					-14.458764162668235
				]
			]
		},
		{
			"type": "line",
			"version": 1021,
			"versionNonce": 575703597,
			"isDeleted": false,
			"id": "q4TON502uSEUzLA4n6WYM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.09146685770895,
			"y": -419.31375459000554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.668744133318043,
			"height": 0.266112223852779,
			"seed": 493826865,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.668744133318043,
					0.266112223852779
				]
			]
		},
		{
			"type": "line",
			"version": 1001,
			"versionNonce": 1349925667,
			"isDeleted": false,
			"id": "GSauy8FUaBvNcFPCeK96E",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.9140587084738,
			"y": -419.225050515388,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.846152282553229,
			"height": 15.523213058079403,
			"seed": 1147381009,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.846152282553229,
					15.523213058079403
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 1165540493,
			"isDeleted": false,
			"id": "jycGZRQc_ECdOgLM0jhri",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.1801709323265,
			"y": -419.13634644077035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.378376730258802,
			"height": 29.538456847659674,
			"seed": 1538185969,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.378376730258802,
					29.538456847659674
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 2028527299,
			"isDeleted": false,
			"id": "nkrUgrVApHOQ_zr0VEnbd",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.09146685770895,
			"y": -418.7815301423,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.200968581023616,
			"height": 45.06166990573906,
			"seed": 869815505,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.200968581023616,
					45.06166990573906
				]
			]
		},
		{
			"type": "line",
			"version": 1012,
			"versionNonce": 229352173,
			"isDeleted": false,
			"id": "iTWKkr7mz_1yU7K3j-Cvv",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -403.9679496811614,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.402631909465232,
			"height": 29.804569071512443,
			"seed": 544707249,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.402631909465232,
					-29.804569071512443
				]
			]
		},
		{
			"type": "line",
			"version": 1001,
			"versionNonce": 780537443,
			"isDeleted": false,
			"id": "olJPuUGBsWO1LUM2dWXS2",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.55924241000326,
			"y": -403.70183745730856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.225223760230032,
			"height": 15.345804908844197,
			"seed": 372511889,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.225223760230032,
					-15.345804908844197
				]
			]
		},
		{
			"type": "line",
			"version": 991,
			"versionNonce": 1869790541,
			"isDeleted": false,
			"id": "pXa3wTcCUMCpNCmn2quWi",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -403.87924560654375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.225223760230048,
			"height": 0.26611222385279465,
			"seed": 147151473,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.225223760230048,
					-0.26611222385279465
				]
			]
		},
		{
			"type": "line",
			"version": 1000,
			"versionNonce": 68962819,
			"isDeleted": false,
			"id": "MRYaAjmp-afR6MBBOUISt",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -444.00276278309127,
			"y": -403.4357252334558,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.112264506406008,
			"height": 14.28135601343305,
			"seed": 150135889,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.112264506406008,
					14.28135601343305
				]
			]
		},
		{
			"type": "line",
			"version": 1021,
			"versionNonce": 304581549,
			"isDeleted": false,
			"id": "bx4otvFzWL3oKaXm2drTl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.82535463385614,
			"y": -403.52442930807337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.112264506406026,
			"height": 29.71586499689484,
			"seed": 580137521,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.112264506406026,
					29.71586499689484
				]
			]
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 782897571,
			"isDeleted": false,
			"id": "zjN1ZUOzxAPUCLorW4gmU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -388.5334406976996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.313927834847638,
			"height": 45.15037398035664,
			"seed": 2056307729,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.313927834847638,
					-45.15037398035664
				]
			]
		},
		{
			"type": "line",
			"version": 1010,
			"versionNonce": 1978895885,
			"isDeleted": false,
			"id": "98UekUzwnutN3D8Z6U-px",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -388.79955292155233,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 30.51420166845322,
			"seed": 752884209,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-30.51420166845322
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 1063118147,
			"isDeleted": false,
			"id": "DIkN2evGilykwbkb1c2IH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -388.001216249994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 16.232845655020174,
			"seed": 1787409361,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-16.232845655020174
				]
			]
		},
		{
			"type": "line",
			"version": 1000,
			"versionNonce": 1506821229,
			"isDeleted": false,
			"id": "PEF9itn2ID7zrvqqU2_Gh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -388.79955292155233,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.668744133318025,
			"height": 0.6209285223231821,
			"seed": 1470435761,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.668744133318025,
					-0.6209285223231821
				]
			]
		},
		{
			"type": "line",
			"version": 1024,
			"versionNonce": 496387299,
			"isDeleted": false,
			"id": "bwx8THUJ1tmQFdDWxS6qQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -388.71084884693477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.644488954111582,
			"height": 15.789325281932195,
			"seed": 693744529,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.644488954111582,
					15.789325281932195
				]
			]
		},
		{
			"type": "line",
			"version": 1019,
			"versionNonce": 1636249293,
			"isDeleted": false,
			"id": "foSDZyAq7-EDUpn9rGNWW",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.47053833538587,
			"y": -373.8972683857962,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.313927834847638,
			"height": 59.87525036687768,
			"seed": 64952689,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.313927834847638,
					-59.87525036687768
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 1088532611,
			"isDeleted": false,
			"id": "Z7JWeIE8pgcjE1vH91ZbH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.64794648462095,
			"y": -374.6956050573545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 44.26333323418068,
			"seed": 410829649,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-44.26333323418068
				]
			]
		},
		{
			"type": "line",
			"version": 1010,
			"versionNonce": 2075249965,
			"isDeleted": false,
			"id": "rYQq4ezVJ4SdOm4Ct2GLR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.1157220369154,
			"y": -374.96171728120737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.047815610994862,
			"height": 29.36104869842447,
			"seed": 59388209,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.047815610994862,
					-29.36104869842447
				]
			]
		},
		{
			"type": "line",
			"version": 998,
			"versionNonce": 721332259,
			"isDeleted": false,
			"id": "z7u7nmFn6cbG1sxRvjDJr",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.1157220369154,
			"y": -374.6956050573545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 14.99098861037381,
			"seed": 1785651985,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-14.99098861037381
				]
			]
		},
		{
			"type": "line",
			"version": 1022,
			"versionNonce": 129605517,
			"isDeleted": false,
			"id": "82VSkb1hhImal762SmNtD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -443.0270179622978,
			"y": -374.6069009827369,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.846152282553215,
			"height": 0.35481629847040325,
			"seed": 1503811825,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.846152282553215,
					0.35481629847040325
				]
			]
		},
		{
			"type": "line",
			"version": 1068,
			"versionNonce": 568044483,
			"isDeleted": false,
			"id": "SFyloahKxy8k_5q0qZRZZ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.31751478117474,
			"y": -433.5019120078791,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.964686129948861,
			"height": 0.14872665865594847,
			"seed": 1655444177,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.964686129948861,
					-0.14872665865594847
				]
			]
		},
		{
			"type": "line",
			"version": 1100,
			"versionNonce": 1004021229,
			"isDeleted": false,
			"id": "7q3Q0FguXypvmXHYBclUs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.1687881225188,
			"y": -433.55148756076443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.766383918407602,
			"height": 15.219694735792558,
			"seed": 2049151153,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.766383918407602,
					15.219694735792558
				]
			]
		},
		{
			"type": "line",
			"version": 1085,
			"versionNonce": 697776995,
			"isDeleted": false,
			"id": "AKpZoSxRFyupi76lapznh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.417603066527,
			"y": -433.80028278252195,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.112264506406008,
			"height": 30.780313892306005,
			"seed": 363877009,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.112264506406008,
					30.780313892306005
				]
			]
		},
		{
			"type": "line",
			"version": 1107,
			"versionNonce": 1259790413,
			"isDeleted": false,
			"id": "H5_kFpl80wk9xM41Ua1TK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.32889899190934,
			"y": -433.53417055866913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.467080804876396,
			"height": 44.52944545803347,
			"seed": 168417393,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.467080804876396,
					44.52944545803347
				]
			]
		},
		{
			"type": "line",
			"version": 1114,
			"versionNonce": 1048565507,
			"isDeleted": false,
			"id": "uT9elL8AkxODS7uf0B5QG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.32889899190934,
			"y": -433.80028278252195,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.467080804876396,
			"height": 61.20581148614165,
			"seed": 687317585,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.467080804876396,
					61.20581148614165
				]
			]
		},
		{
			"type": "line",
			"version": 1097,
			"versionNonce": 1263488685,
			"isDeleted": false,
			"id": "q3GuM9n8LE-MzhVf0R9xg",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.32889899190934,
			"y": -419.34151861985373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.846152282553215,
			"height": 14.458764162668235,
			"seed": 525414449,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.846152282553215,
					-14.458764162668235
				]
			]
		},
		{
			"type": "line",
			"version": 1104,
			"versionNonce": 1326710435,
			"isDeleted": false,
			"id": "-7T87aPqJyEEy1oy9EM_J",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.32889899190934,
			"y": -419.16411047061854,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.668744133318043,
			"height": 0.266112223852779,
			"seed": 318636561,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.668744133318043,
					0.266112223852779
				]
			]
		},
		{
			"type": "line",
			"version": 1084,
			"versionNonce": 1529540877,
			"isDeleted": false,
			"id": "Oz9FONX2CWjrAb1GlX6xV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.1514908426743,
			"y": -419.075406396001,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.846152282553229,
			"height": 15.523213058079403,
			"seed": 16095217,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.846152282553229,
					15.523213058079403
				]
			]
		},
		{
			"type": "line",
			"version": 1099,
			"versionNonce": 1979855427,
			"isDeleted": false,
			"id": "O3mV0wCCyIpTwrIvyet2Z",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.417603066527,
			"y": -418.98670232138335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.378376730258802,
			"height": 29.538456847659674,
			"seed": 1530884561,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.378376730258802,
					29.538456847659674
				]
			]
		},
		{
			"type": "line",
			"version": 1099,
			"versionNonce": 136529773,
			"isDeleted": false,
			"id": "Otooy40w06glXI50e6JgP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.32889899190934,
			"y": -418.63188602291297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.200968581023616,
			"height": 45.06166990573906,
			"seed": 1727205297,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.200968581023616,
					45.06166990573906
				]
			]
		},
		{
			"type": "line",
			"version": 1095,
			"versionNonce": 1948840419,
			"isDeleted": false,
			"id": "wx1Vai0_xLftne1v_LBwJ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -403.8183055617743,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.402631909465232,
			"height": 29.804569071512443,
			"seed": 1513615761,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.402631909465232,
					-29.804569071512443
				]
			]
		},
		{
			"type": "line",
			"version": 1084,
			"versionNonce": 1954664909,
			"isDeleted": false,
			"id": "-wLd03q34oO__tB6QXAIM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.7966745442038,
			"y": -403.5521933379215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.225223760230032,
			"height": 15.345804908844197,
			"seed": 977639281,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.225223760230032,
					-15.345804908844197
				]
			]
		},
		{
			"type": "line",
			"version": 1074,
			"versionNonce": 1788263811,
			"isDeleted": false,
			"id": "yOctWaP7i05B7WLls-YQd",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -403.7296014871567,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.225223760230048,
			"height": 0.26611222385279465,
			"seed": 2036564305,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.225223760230048,
					-0.26611222385279465
				]
			]
		},
		{
			"type": "line",
			"version": 1083,
			"versionNonce": 1029705773,
			"isDeleted": false,
			"id": "wwUzFmYztxM9LzGlXTl8Z",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.2401949172919,
			"y": -403.28608111406885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.112264506406008,
			"height": 14.28135601343305,
			"seed": 1424568113,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.112264506406008,
					14.28135601343305
				]
			]
		},
		{
			"type": "line",
			"version": 1104,
			"versionNonce": 1418335523,
			"isDeleted": false,
			"id": "92ttMsghW8Cx8npe573Su",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -424.06278676805664,
			"y": -403.3747851886863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.112264506406026,
			"height": 29.71586499689484,
			"seed": 1933451537,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.112264506406026,
					29.71586499689484
				]
			]
		},
		{
			"type": "line",
			"version": 1085,
			"versionNonce": 547848845,
			"isDeleted": false,
			"id": "C0B6jEUM0QQLMa7iUvn_r",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -388.3837965783125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.313927834847638,
			"height": 45.15037398035664,
			"seed": 1104795377,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.313927834847638,
					-45.15037398035664
				]
			]
		},
		{
			"type": "line",
			"version": 1093,
			"versionNonce": 1097955523,
			"isDeleted": false,
			"id": "PdTvsMi2jEXWY8wD5R4lD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -388.6499088021653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 30.51420166845322,
			"seed": 323211473,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-30.51420166845322
				]
			]
		},
		{
			"type": "line",
			"version": 1099,
			"versionNonce": 1662101741,
			"isDeleted": false,
			"id": "SWIOjHsIHrYIo_E9QnrLC",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -387.851572130607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 16.232845655020174,
			"seed": 2098433713,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-16.232845655020174
				]
			]
		},
		{
			"type": "line",
			"version": 1083,
			"versionNonce": 1324050531,
			"isDeleted": false,
			"id": "qUzJqcJ5Ojjun4avOzcDO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -388.6499088021653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.668744133318025,
			"height": 0.6209285223231821,
			"seed": 1978699921,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.668744133318025,
					-0.6209285223231821
				]
			]
		},
		{
			"type": "line",
			"version": 1107,
			"versionNonce": 1982333773,
			"isDeleted": false,
			"id": "Av-zGA-JU-JZxIMdgvwFU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -388.5612047275477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.644488954111582,
			"height": 15.789325281932195,
			"seed": 865228401,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					10.644488954111582,
					15.789325281932195
				]
			]
		},
		{
			"type": "line",
			"version": 1102,
			"versionNonce": 1657168899,
			"isDeleted": false,
			"id": "ixShg3tumWTC24tDR-OOX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.7079704695863,
			"y": -373.7476242664091,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.313927834847638,
			"height": 59.87525036687768,
			"seed": 1220567121,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.313927834847638,
					-59.87525036687768
				]
			]
		},
		{
			"type": "line",
			"version": 1099,
			"versionNonce": 1581519277,
			"isDeleted": false,
			"id": "NJ0MVDh5C8QkQdkIxdULK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.88537861882145,
			"y": -374.5459609379673,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 44.26333323418068,
			"seed": 55717425,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-44.26333323418068
				]
			]
		},
		{
			"type": "line",
			"version": 1093,
			"versionNonce": 620817315,
			"isDeleted": false,
			"id": "T0RDbXIhK3yKoBWhr2_i8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.3531541711159,
			"y": -374.81207316182025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.047815610994862,
			"height": 29.36104869842447,
			"seed": 170868753,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.047815610994862,
					-29.36104869842447
				]
			]
		},
		{
			"type": "line",
			"version": 1081,
			"versionNonce": 1485788173,
			"isDeleted": false,
			"id": "T3bcdCmw7foLz6NUwhhAV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.3531541711159,
			"y": -374.5459609379673,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.491335984082841,
			"height": 14.99098861037381,
			"seed": 995038705,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.491335984082841,
					-14.99098861037381
				]
			]
		},
		{
			"type": "line",
			"version": 1105,
			"versionNonce": 969506627,
			"isDeleted": false,
			"id": "Wx3iFchEBqnHI3vzZbW0H",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -423.2644500964983,
			"y": -374.4572568633498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.846152282553215,
			"height": 0.35481629847040325,
			"seed": 1236873169,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					9.846152282553215,
					0.35481629847040325
				]
			]
		},
		{
			"type": "line",
			"version": 1004,
			"versionNonce": 1090734701,
			"isDeleted": false,
			"id": "QTwmz7SteBiHTocy0iDB6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -475.0904974094399,
			"y": -420.30532895829805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.60174540786438,
			"height": 14.497171362611214,
			"seed": 461704625,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.60174540786438,
					-14.497171362611214
				]
			]
		},
		{
			"type": "line",
			"version": 1006,
			"versionNonce": 998153955,
			"isDeleted": false,
			"id": "SxupNsmCUqVR2AZCyh8yD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -475.37852068154467,
			"y": -420.6893599877712,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 22.1777919520741,
			"height": 1.2481008457877276,
			"seed": 1742352273,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					22.1777919520741,
					1.2481008457877276
				]
			]
		},
		{
			"type": "line",
			"version": 1021,
			"versionNonce": 946435277,
			"isDeleted": false,
			"id": "AidpmhaP9is-QWIC2kNNn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -475.37852068154467,
			"y": -421.26540653198094,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.697753165232673,
			"height": 17.569419598396355,
			"seed": 351278449,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.697753165232673,
					17.569419598396355
				]
			]
		},
		{
			"type": "line",
			"version": 1009,
			"versionNonce": 1957612163,
			"isDeleted": false,
			"id": "X_IKulbfFmnVnDr9TnmdU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.7064663799666,
			"y": -420.40133671566633,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.409729893127803,
			"height": 31.39453665942956,
			"seed": 1443774289,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.409729893127803,
					31.39453665942956
				]
			]
		},
		{
			"type": "line",
			"version": 1013,
			"versionNonce": 173757229,
			"isDeleted": false,
			"id": "gE6RIMCp_aGt4zMvnKH-8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.99448965207137,
			"y": -420.40133671566633,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.889768679969244,
			"height": 46.371746808882214,
			"seed": 160181553,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.889768679969244,
					46.371746808882214
				]
			]
		},
		{
			"type": "line",
			"version": 1003,
			"versionNonce": 1511555619,
			"isDeleted": false,
			"id": "acGNRuM2Fy19nhuN3TwJu",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -475.0904974094399,
			"y": -410.1285066772598,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.60174540786438,
			"height": 24.770001401017833,
			"seed": 1456561937,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.60174540786438,
					-24.770001401017833
				]
			]
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 1396860301,
			"isDeleted": false,
			"id": "6iDC9eiStMBiP0naqSxUL",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.7064663799666,
			"y": -410.60854546410116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.12170662102295,
			"height": 8.832713677882323,
			"seed": 206918897,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.12170662102295,
					-8.832713677882323
				]
			]
		},
		{
			"type": "line",
			"version": 1015,
			"versionNonce": 1152009667,
			"isDeleted": false,
			"id": "02B3gVzxhI6V4_-w5X6Bs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.99448965207137,
			"y": -410.51253770673276,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.31372213575953,
			"height": 6.912558530516617,
			"seed": 1033866961,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.31372213575953,
					6.912558530516617
				]
			]
		},
		{
			"type": "line",
			"version": 992,
			"versionNonce": 1717054445,
			"isDeleted": false,
			"id": "c-RiRauXNrqkdy8rs7heu",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.8024741373349,
			"y": -410.8005609788377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.409729893127814,
			"height": 21.98577643733753,
			"seed": 558337201,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.409729893127814,
					21.98577643733753
				]
			]
		},
		{
			"type": "line",
			"version": 1013,
			"versionNonce": 1803720035,
			"isDeleted": false,
			"id": "d5YVoRNy-tc6PlxpsuLvl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.99448965207137,
			"y": -410.896568736206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.505737650496098,
			"height": 36.6749633146853,
			"seed": 787795601,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.505737650496098,
					36.6749633146853
				]
			]
		},
		{
			"type": "line",
			"version": 999,
			"versionNonce": 1940268621,
			"isDeleted": false,
			"id": "Xs4jxj3jVrDGREWk3iroV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.7064663799666,
			"y": -401.2957929993774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.02569886365467,
			"height": 33.41069956416358,
			"seed": 2103366769,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.02569886365467,
					-33.41069956416358
				]
			]
		},
		{
			"type": "line",
			"version": 991,
			"versionNonce": 502264067,
			"isDeleted": false,
			"id": "N4XK-7uwgcHC29OyBaUJ0",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.61045862259834,
			"y": -400.9117619699042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.409729893127803,
			"height": 18.433489414710948,
			"seed": 1615666769,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.409729893127803,
					-18.433489414710948
				]
			]
		},
		{
			"type": "line",
			"version": 1007,
			"versionNonce": 1845875885,
			"isDeleted": false,
			"id": "XIacMQcv6TvHbXKLtMjgG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.8024741373349,
			"y": -401.0077697272725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.217714378391232,
			"height": 2.688217206312023,
			"seed": 1184312369,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.217714378391232,
					-2.688217206312023
				]
			]
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 1030805667,
			"isDeleted": false,
			"id": "iL1a0sIFPGwIIo2eKfVrX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.8024741373349,
			"y": -401.10377748464083,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.217714378391232,
			"height": 12.28899294314063,
			"seed": 1478786577,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.217714378391232,
					12.28899294314063
				]
			]
		},
		{
			"type": "line",
			"version": 1018,
			"versionNonce": 824227597,
			"isDeleted": false,
			"id": "MdJgDahC-Sg_xW2otRmOU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.61045862259834,
			"y": -401.0077697272725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.313722135759512,
			"height": 27.170195335224978,
			"seed": 1408013297,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.313722135759512,
					27.170195335224978
				]
			]
		},
		{
			"type": "line",
			"version": 1019,
			"versionNonce": 2008271939,
			"isDeleted": false,
			"id": "vTeVDvFiaWPlyeaRULW4i",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.8984818947033,
			"y": -391.69501726254873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.505737650496098,
			"height": 42.72345202888733,
			"seed": 771157457,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.505737650496098,
					-42.72345202888733
				]
			]
		},
		{
			"type": "line",
			"version": 1003,
			"versionNonce": 1735413101,
			"isDeleted": false,
			"id": "Jg4D2OhbqCesOj0RUmO2k",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.99448965207137,
			"y": -391.59900950518045,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.79376092260096,
			"height": 27.6502341220664,
			"seed": 1834683313,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.79376092260096,
					-27.6502341220664
				]
			]
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 1083657187,
			"isDeleted": false,
			"id": "8CUIeHgv134_7yyUZgkmZ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.8984818947033,
			"y": -391.69501726254873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.505737650496098,
			"height": 12.192985185772324,
			"seed": 1245736337,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.505737650496098,
					-12.192985185772324
				]
			]
		},
		{
			"type": "line",
			"version": 1006,
			"versionNonce": 809375693,
			"isDeleted": false,
			"id": "z6zhIdGlLqrmjH37bFnkS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -474.61045862259834,
			"y": -391.69501726254873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.12170662102295,
			"height": 2.9762404784168663,
			"seed": 199136113,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.12170662102295,
					2.9762404784168663
				]
			]
		},
		{
			"type": "line",
			"version": 999,
			"versionNonce": 204068739,
			"isDeleted": false,
			"id": "JgkJyNr_jXeUxxc6rvY0y",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -475.0904974094399,
			"y": -391.791025019917,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 21.88976867996924,
			"height": 17.665427355764646,
			"seed": 645725521,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					21.88976867996924,
					17.665427355764646
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1459,
			"versionNonce": 94606893,
			"isDeleted": false,
			"id": "GOZnFR9SN2kItseWUmVaw",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -387.67157416921845,
			"y": -408.22162163930176,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 9.687958950861677,
			"height": 9.394384437199184,
			"seed": 426978097,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1005,
			"versionNonce": 1219096355,
			"isDeleted": false,
			"id": "cdsUzgwQSup_mOwUJEloK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -404.99951987640765,
			"y": -434.7981619537936,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 17.788935576127408,
			"height": 31.392239251989523,
			"seed": 220765457,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					17.788935576127408,
					31.392239251989523
				]
			]
		},
		{
			"type": "line",
			"version": 987,
			"versionNonce": 1653229709,
			"isDeleted": false,
			"id": "6f4BxotxQ9jK7HtvUgOI_",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -404.99951987640765,
			"y": -419.1020423277988,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 17.26573158859424,
			"height": 15.565318629111468,
			"seed": 823448305,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					17.26573158859424,
					15.565318629111468
				]
			]
		},
		{
			"type": "line",
			"version": 999,
			"versionNonce": 411439811,
			"isDeleted": false,
			"id": "GVvqwc96XfwoZV5ZypSqd",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -405.130320873291,
			"y": -403.66752469557065,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 17.39653258547753,
			"height": 0.5232039875331669,
			"seed": 1505709265,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					17.39653258547753,
					0.5232039875331669
				]
			]
		},
		{
			"type": "line",
			"version": 996,
			"versionNonce": 682340077,
			"isDeleted": false,
			"id": "79Zzu8YUgsaVQIO-kASzR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -404.08391289822464,
			"y": -388.49460905710896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 16.480925607294516,
			"height": 15.042114641578333,
			"seed": 1589611185,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					16.480925607294516,
					-15.042114641578333
				]
			]
		},
		{
			"type": "line",
			"version": 993,
			"versionNonce": 1281147491,
			"isDeleted": false,
			"id": "BjhLn5tQgLMLJa7aRmo-e",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -404.86871887952435,
			"y": -374.1064993999471,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 17.396532585477544,
			"height": 29.430224298740193,
			"seed": 951913617,
			"groupIds": [
				"5afvsFWPOLC3wRDjQDH4P",
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					17.396532585477544,
					-29.430224298740193
				]
			]
		},
		{
			"type": "text",
			"version": 476,
			"versionNonce": 1183926605,
			"isDeleted": false,
			"id": "KficlfDC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -529.5870760993511,
			"y": -410.36342973247054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.941864013671875,
			"height": 11.969210046997256,
			"seed": 928164145,
			"groupIds": [
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 9.575368037597805,
			"fontFamily": 1,
			"text": "Nerd",
			"rawText": "Nerd",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Nerd",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 779,
			"versionNonce": 486309379,
			"isDeleted": false,
			"id": "Kb1MiUDueptGN74atYvDs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -501.1430167137975,
			"y": -404.1688075935015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.751247869415199,
			"height": 0.22379038699348336,
			"seed": 988059679,
			"groupIds": [
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					12.751247869415199,
					0.22379038699348336
				]
			]
		},
		{
			"type": "text",
			"version": 441,
			"versionNonce": 496277421,
			"isDeleted": false,
			"id": "QOqfq2QY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -351.9793761832386,
			"y": -405.87149482322104,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.495346069335938,
			"height": 7.252442634759885,
			"seed": 1501629183,
			"groupIds": [
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 5.801954107807908,
			"fontFamily": 1,
			"text": "You",
			"rawText": "You",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "You",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 791,
			"versionNonce": 627295651,
			"isDeleted": false,
			"id": "blnAoEGD22-Mf06istOvt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -374.87953429764667,
			"y": -402.71569496745167,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 18.298007211987187,
			"height": 0.1288592057182169,
			"seed": 1368906353,
			"groupIds": [
				"H7JHje9_zowRuTjU0Rvvb",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					18.298007211987187,
					0.1288592057182169
				]
			]
		},
		{
			"type": "line",
			"version": 1363,
			"versionNonce": 668932621,
			"isDeleted": false,
			"id": "OtC5M304mQWx1M2nRUvGw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -348.0789587353722,
			"y": -434.56200914889047,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.65303446783608,
			"height": 45.172986637245245,
			"seed": 1399814719,
			"groupIds": [
				"C38T4UOb2BS9qiQWMNlLN",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531069,
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
					5.526338550417151,
					4.907536506402298
				],
				[
					11.187465845966418,
					9.046422716621112
				],
				[
					8.019930335361467,
					1.3599197547861763
				],
				[
					5.661127295549276,
					-3.547616751616122
				],
				[
					12.130987061891297,
					-5.971821531887127
				],
				[
					14.691973219401675,
					-12.298404738935865
				],
				[
					12.333170179589487,
					-19.393638242168112
				],
				[
					4.7176060796243995,
					-23.118635831365044
				],
				[
					2.5609861575103885,
					-29.681726821854863
				],
				[
					-3.5719017460013234,
					-33.99799386965449
				],
				[
					-13.074508277816165,
					-33.465851356912054
				],
				[
					-20.420494887517048,
					-36.126563920624136
				],
				[
					-28.238242105180337,
					-35.890056137183066
				],
				[
					-35.382045597182966,
					-32.75632800658883
				],
				[
					-41.380144755562554,
					-25.069825044753895
				],
				[
					-48.456553874999145,
					-22.882128047923967
				],
				[
					-51.961061248434405,
					-16.969433461897108
				],
				[
					-50.68056816967923,
					-9.2238035542019
				],
				[
					-43.87373654050687,
					-4.907536506402273
				],
				[
					-40.504017912203736,
					1.3007928089259053
				],
				[
					-31.270988870653145,
					4.9666634522625674
				],
				[
					-21.700987966272255,
					2.069443105109407
				],
				[
					-15.56810006276054,
					5.735313748446069
				],
				[
					-6.200282276077829,
					5.439679019144723
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 568,
			"versionNonce": 482416963,
			"isDeleted": false,
			"id": "ibknqWor",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -391.00758011131416,
			"y": -462.493582466802,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 48.59754943847656,
			"height": 28.671661024939247,
			"seed": 701695953,
			"groupIds": [
				"C38T4UOb2BS9qiQWMNlLN",
				"RkYey8MqbLC9pBsfC4MGJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 5.734332204987849,
			"fontFamily": 1,
			"text": "maybe I should\nkeep changing the\nparameters until\nit says im cool?",
			"rawText": "maybe I should\nkeep changing the\nparameters until\nit says im cool?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "maybe I should\nkeep changing the\nparameters until\nit says im cool?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 132,
			"versionNonce": 1584025709,
			"isDeleted": false,
			"id": "CubllqYm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -90.12339994465405,
			"y": -266.85495510107086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 268.213134765625,
			"height": 35,
			"seed": 1730990609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Why explainable AI?",
			"rawText": "Why explainable AI?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why explainable AI?",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 197,
			"versionNonce": 1349712099,
			"isDeleted": false,
			"id": "A0yHVnfI6xAG9DNltJY3Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -136.9203075423634,
			"y": -198.44158596817124,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 371.91679808862864,
			"height": 92.2174693752358,
			"seed": 1647704113,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 251,
			"versionNonce": 1593817805,
			"isDeleted": false,
			"id": "Tdt5wWu0iNZ_6xhKHNPty",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -136.9203066356967,
			"y": -105.61433389430965,
			"strokeColor": "#000000",
			"backgroundColor": "#eebefa",
			"width": 371.91679808862864,
			"height": 92.2174693752358,
			"seed": 27357855,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 249,
			"versionNonce": 1577575555,
			"isDeleted": false,
			"id": "6dKnqLlQaivae3qvRA2jZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -136.92030662193307,
			"y": -12.393919167398423,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#da77f2",
			"width": 371.91679808862864,
			"height": 92.2174693752358,
			"seed": 1958798641,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 278,
			"versionNonce": 1379457325,
			"isDeleted": false,
			"id": "lV5IRqosKJ_P7pjfg8GEA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -136.92030656253462,
			"y": 80.82649648635052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 371.91679808862864,
			"height": 92.2174693752358,
			"seed": 2024359455,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 759061539,
			"isDeleted": false,
			"id": "HnjDFlkF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 11.788130564674919,
			"y": -198.4415863798761,
			"strokeColor": "#000000",
			"backgroundColor": "#be4bdb",
			"width": 74.49992370605469,
			"height": 25,
			"seed": 5247199,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Improve",
			"rawText": "Improve",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Improve",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 293546893,
			"isDeleted": false,
			"id": "ejGJmkch",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -129.16228601128591,
			"y": -169.52796001313524,
			"strokeColor": "#000000",
			"backgroundColor": "#be4bdb",
			"width": 356.4007568359375,
			"height": 60,
			"seed": 2034112017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Our Model is not working properly, perhaps an\nexplanation will help us improve on making the\nmodel make the right decisions",
			"rawText": "Our Model is not working properly, perhaps an\nexplanation will help us improve on making the\nmodel make the right decisions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our Model is not working properly, perhaps an\nexplanation will help us improve on making the\nmodel make the right decisions",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 704962499,
			"isDeleted": false,
			"id": "zsnI0YD2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 18.348127786324113,
			"y": -105.41775306784187,
			"strokeColor": "#000000",
			"backgroundColor": "#be4bdb",
			"width": 61.37992858886719,
			"height": 25,
			"seed": 1590176415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assist",
			"rawText": "Assist",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assist",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 218903021,
			"isDeleted": false,
			"id": "SywYouQA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -124.75429726466768,
			"y": -87.4448287695536,
			"strokeColor": "#000000",
			"backgroundColor": "#be4bdb",
			"width": 347.58477783203125,
			"height": 60,
			"seed": 406560191,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Assist users in making decisions faster\nby highlighting relevant regions that need to\nbe focused on in complex situtions",
			"rawText": "Assist users in making decisions faster\nby highlighting relevant regions that need to\nbe focused on in complex situtions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assist users in making decisions faster\nby highlighting relevant regions that need to\nbe focused on in complex situtions",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 1048178531,
			"isDeleted": false,
			"id": "LiHQlPM3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 15.588132978834095,
			"y": -12.295627536833848,
			"strokeColor": "#f8f0fc",
			"backgroundColor": "#be4bdb",
			"width": 66.89991760253906,
			"height": 25,
			"seed": 1428286335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Explain",
			"rawText": "Explain",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Explain",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 240,
			"versionNonce": 1911123021,
			"isDeleted": false,
			"id": "LjeewRQq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -128.410287654597,
			"y": 9.838691681537702,
			"strokeColor": "#f8f0fc",
			"backgroundColor": "#be4bdb",
			"width": 354.8967590332031,
			"height": 60,
			"seed": 735320223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "helps scientists discover relations between\ndifferent variables in a complex system that\nis not well-studied",
			"rawText": "helps scientists discover relations between\ndifferent variables in a complex system that\nis not well-studied",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "helps scientists discover relations between\ndifferent variables in a complex system that\nis not well-studied",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 216795907,
			"isDeleted": false,
			"id": "862JxZPc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -13.001839885577908,
			"y": 78.32649691305713,
			"strokeColor": "#f8f0fc",
			"backgroundColor": "#be4bdb",
			"width": 124.07986450195312,
			"height": 25,
			"seed": 1439149233,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Dont sue me",
			"rawText": "Dont sue me",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dont sue me",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 267410093,
			"isDeleted": false,
			"id": "61pJEDjh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -133.83693838739782,
			"y": 103.1705227122909,
			"strokeColor": "#f8f0fc",
			"backgroundColor": "#be4bdb",
			"width": 365.8887634277344,
			"height": 60,
			"seed": 690611857,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Legal obligations demand for an explanation\nof why our AI model makes the decisions that\nit does in order to be publicly available",
			"rawText": "Legal obligations demand for an explanation\nof why our AI model makes the decisions that\nit does in order to be publicly available",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Legal obligations demand for an explanation\nof why our AI model makes the decisions that\nit does in order to be publicly available",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 460,
			"versionNonce": 1775874723,
			"isDeleted": false,
			"id": "5ENRpxKm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -186.6063384577022,
			"y": 255.91603034433587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 470.93402099609375,
			"height": 105,
			"seed": 1310748049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Okay that's cool and all,\nBut how do we actually Generate\nthese explanations?",
			"rawText": "Okay that's cool and all,\nBut how do we actually Generate\nthese explanations?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Okay that's cool and all,\nBut how do we actually Generate\nthese explanations?",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 625,
			"versionNonce": 2143976717,
			"isDeleted": false,
			"id": "Fz0ZXTCcAYQ1Bd4SaKN6C",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 65.98630130076846,
			"y": 374.9327381811865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 148.87881035760896,
			"height": 151.25659434862484,
			"seed": 1633423071,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
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
					-0.7192213060754469,
					98.72090699853004
				],
				[
					51.78393403742916,
					97.56627650731917
				],
				[
					-14.384426121507985,
					150.10196385741398
				],
				[
					-97.0948763201798,
					98.14359175292455
				],
				[
					-36.680286609845744,
					97.5662765073191
				],
				[
					-56.81848317995704,
					-1.1546304912108631
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 368141891,
			"isDeleted": false,
			"id": "60QIpT1p",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -177.7953945965362,
			"y": 550.208679554423,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 453.3121337890625,
			"height": 45,
			"seed": 191156799,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "1. Activation Maximization",
			"rawText": "1. Activation Maximization",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Activation Maximization",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 504,
			"versionNonce": 150033261,
			"isDeleted": false,
			"id": "88140Zy6aWaB5B3sIt0QQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 304.3514893057479,
			"y": 542.7998924307112,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 147.56793348736608,
			"height": 100.88828105768903,
			"seed": 755471665,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
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
					109.17015487585758,
					16.56374763633699
				],
				[
					109.92305249569117,
					-18.069542876003993
				],
				[
					144.55634300803203,
					32.37459765284039
				],
				[
					106.15856439652345,
					82.81873818168503
				],
				[
					105.41518568273928,
					52.50293636131141
				],
				[
					-3.0115904793340427,
					63.24340006601404
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 683,
			"versionNonce": 940680675,
			"isDeleted": false,
			"id": "L3JAlreY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 460.81495555576294,
			"y": 461.01777880172756,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 560.2393798828125,
			"height": 225,
			"seed": 229264081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given a Neural Netowrk, we would like to understand\n what concept is associated with a particular output\nclass and which input x Maximizes our desired output\n\n\n\n\nThink of our model as a function and try to understand\nhow to produce the maximum output from a given input ",
			"rawText": "Given a Neural Netowrk, we would like to understand\n what concept is associated with a particular output\nclass and which input x Maximizes our desired output\n\n\n\n\nThink of our model as a function and try to understand\nhow to produce the maximum output from a given input ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given a Neural Netowrk, we would like to understand\n what concept is associated with a particular output\nclass and which input x Maximizes our desired output\n\n\n\n\nThink of our model as a function and try to understand\nhow to produce the maximum output from a given input ",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 482,
			"versionNonce": 1202609613,
			"isDeleted": false,
			"id": "f-KkW57EZRtJBitkX8tMq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 640.0386170879914,
			"y": 540.1101479058475,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"width": 189.75679968541294,
			"height": 96.92193460854938,
			"seed": 1723581265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4dbe47bfdca823be02051c7f1bd4e08ec8798d51",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 407,
			"versionNonce": 390656387,
			"isDeleted": false,
			"id": "9Q3O4yzIdpDDcZcWOkLMw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 635.4101512454556,
			"y": 537.4482798303218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 195.17063551295598,
			"height": 97.58531775647799,
			"seed": 804210449,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 301,
			"versionNonce": 320543789,
			"isDeleted": false,
			"id": "0y8Xc8zH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 640.038617201854,
			"y": 692.8444459245077,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 184.3708425136471,
			"height": 33.77786427730939,
			"seed": 42844,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1057e27e8caaf5155a215bba03d57ff9900c024d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 448,
			"versionNonce": 349554979,
			"isDeleted": false,
			"id": "DJ7TME9H",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1043.5211545195148,
			"y": 412.4772286624463,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 409.1395263671875,
			"height": 125,
			"seed": 417999647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Problem:\nX can just grow to infinity and maximizing\nthe value of our function\nBUT\ninfinity input does not make much sense",
			"rawText": "Problem:\nX can just grow to infinity and maximizing\nthe value of our function\nBUT\ninfinity input does not make much sense",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nX can just grow to infinity and maximizing\nthe value of our function\nBUT\ninfinity input does not make much sense",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 725,
			"versionNonce": 589368973,
			"isDeleted": false,
			"id": "p-5hGj40zJNDAW_Jq7Ya6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1041.110386527662,
			"y": 540.4818805299003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 492.8774684822438,
			"height": 155.19670376120445,
			"seed": 1190062335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
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
					421.33234819136624,
					10.591540988424043
				],
				[
					420.39476302300955,
					-41.63745326140017
				],
				[
					492.8774684822438,
					41.4367931862588
				],
				[
					418.5524502899709,
					113.55925049980428
				],
				[
					417.7908819939996,
					57.07650816215482
				],
				[
					13.940561511567921,
					84.57273983684559
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 418,
			"versionNonce": 1713810627,
			"isDeleted": false,
			"id": "HbWOT23J",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1702.0918088844785,
			"y": 233.54581959817705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 556.8993530273438,
			"height": 75,
			"seed": 2014299473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Idea:\nLets restrict x into a certain domain where things make\nsense and are plausibly sampled from the real world",
			"rawText": "Idea:\nLets restrict x into a certain domain where things make\nsense and are plausibly sampled from the real world",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea:\nLets restrict x into a certain domain where things make\nsense and are plausibly sampled from the real world",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 456,
			"versionNonce": 1987687661,
			"isDeleted": false,
			"id": "5iECxm3b",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1535.995805952304,
			"y": 350.32202813080886,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 382.819580078125,
			"height": 75,
			"seed": 2032791377,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Approach 1:\nPenalize Large values by adding\nthe negative norm to the max function",
			"rawText": "Approach 1:\nPenalize Large values by adding\nthe negative norm to the max function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 1:\nPenalize Large values by adding\nthe negative norm to the max function",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 511,
			"versionNonce": 249175139,
			"isDeleted": false,
			"id": "ABC1B7dpv3dlbBjmXbRi-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1597.763042920228,
			"y": 433.37376617813123,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 259.28510532840966,
			"height": 35.901014583933645,
			"seed": 732512287,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6e8f2c9fc467a8a7a5c4148fa7f4bc47bd520f57",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 413,
			"versionNonce": 2024705869,
			"isDeleted": false,
			"id": "w6CMsXmV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1991.0058957348365,
			"y": 350.32202809772537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 327.55963134765625,
			"height": 75,
			"seed": 1354120081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Approach 2:\nOnly sample points from the given\ndata distribution!",
			"rawText": "Approach 2:\nOnly sample points from the given\ndata distribution!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 2:\nOnly sample points from the given\ndata distribution!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 369,
			"versionNonce": 448698371,
			"isDeleted": false,
			"id": "AS1zxZtT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2083.171606589799,
			"y": 476.2576839444237,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 141,
			"height": 17,
			"seed": 70860,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531069,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e9d31ac7e9520a3411ecf6ae34c7e5973388e847",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 583,
			"versionNonce": 1746476461,
			"isDeleted": false,
			"id": "KPhFYHhy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1968.1104717780056,
			"y": 424.68339938271055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 369.5187072753906,
			"height": 44.759141552173105,
			"seed": 1262645681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 11.935771080579494,
			"fontFamily": 1,
			"text": "Assume that our model produces a log-probability for class wc\ni.e the function that the model learned to classify class wc\nfrom input x which is where our model is SURE its wc",
			"rawText": "Assume that our model produces a log-probability for class wc\ni.e the function that the model learned to classify class wc\nfrom input x which is where our model is SURE its wc",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assume that our model produces a log-probability for class wc\ni.e the function that the model learned to classify class wc\nfrom input x which is where our model is SURE its wc",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 353,
			"versionNonce": 399679395,
			"isDeleted": false,
			"id": "j02NwSCr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1970.8253232769168,
			"y": 493.2576845802951,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 367.9207763671875,
			"height": 40,
			"seed": 259825823,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can penalize this term by only drawing from\nthe distribution of x,      ",
			"rawText": "We can penalize this term by only drawing from\nthe distribution of x,      ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can penalize this term by only drawing from\nthe distribution of x,      ",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 379,
			"versionNonce": 2078466061,
			"isDeleted": false,
			"id": "RY5ITcat",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2220.117788312067,
			"y": 513.1416918667878,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 70.54575939763028,
			"height": 18.450429380918685,
			"seed": 83031,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b6690b5f4aa8648bcd3065194fb091c6fb867ba",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 289,
			"versionNonce": 1346679619,
			"isDeleted": false,
			"id": "uYav8Cxf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2031.5343884645627,
			"y": 538.8910785626622,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 244.2744358298674,
			"height": 21.553626690870654,
			"seed": 52837,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "90cea52d0a607335ca29558b2319aed149e361e2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 349,
			"versionNonce": 1241863789,
			"isDeleted": false,
			"id": "eKCY-6DNh2mZ8oYZDg9ma",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2043.2082437900217,
			"y": 560.4447049550909,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 223.1549349667177,
			"height": 23.593473300445925,
			"seed": 688568863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "nVaULYs6643k-sil5hl_q",
					"type": "arrow"
				}
			],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5193f50b29cf370ea452e478f84713b5d0ce868b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 743,
			"versionNonce": 1148408547,
			"isDeleted": false,
			"id": "nVaULYs6643k-sil5hl_q",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2285.1892362725393,
			"y": 546.0022384709323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 51.10049288531809,
			"height": 26.50667278008484,
			"seed": 1495812223,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					37.9837888291936,
					1.6395880070155044
				],
				[
					40.98970017538886,
					26.50667278008484
				],
				[
					-10.110792709929228,
					26.50667278008484
				]
			]
		},
		{
			"type": "text",
			"version": 320,
			"versionNonce": 1833566413,
			"isDeleted": false,
			"id": "rfZfFYDu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2335.6187761945976,
			"y": 551.4495765575916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 86.74615478515625,
			"height": 14.552661913340925,
			"seed": 659430463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 11.64212953067274,
			"fontFamily": 1,
			"text": "Bayes Theorem",
			"rawText": "Bayes Theorem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bayes Theorem",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 451,
			"versionNonce": 1693253251,
			"isDeleted": false,
			"id": "oo8kaE83",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1986.4980495254513,
			"y": 584.0381785561483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 349.1207275390625,
			"height": 60,
			"seed": 529848991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The distribution of wc does not have to do\nwith out choice of x! and its constant thus\nwe take it out of the function",
			"rawText": "The distribution of wc does not have to do\nwith out choice of x! and its constant thus\nwe take it out of the function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The distribution of wc does not have to do\nwith out choice of x! and its constant thus\nwe take it out of the function",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 290,
			"versionNonce": 1800036141,
			"isDeleted": false,
			"id": "3zIK070j",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2071.004826317783,
			"y": 652.3646528588899,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 187,
			"height": 24,
			"seed": 42598,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "54a136ee96e91423d706748fe9df8491b17b9d0a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 342,
			"versionNonce": 208680483,
			"isDeleted": false,
			"id": "Zo6FqbVE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1973.3139981120341,
			"y": 680.9820479953275,
			"strokeColor": "#e03131",
			"backgroundColor": "#f8f0fc",
			"width": 375.48883056640625,
			"height": 40,
			"seed": 403620561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which makes sense because it can now be\ninterpreted as the most typical input for class",
			"rawText": "Which makes sense because it can now be\ninterpreted as the most typical input for class",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which makes sense because it can now be\ninterpreted as the most typical input for class",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1517285773,
			"isDeleted": false,
			"id": "NwlRhPuS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -71.60167226853055,
			"y": 1156.9679157191358,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 244.87210083007812,
			"height": 45,
			"seed": 1515328735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "2. Attribution",
			"rawText": "2. Attribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2. Attribution",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 551,
			"versionNonce": 971733443,
			"isDeleted": false,
			"id": "0QRa06qjUzvr9vPQ-0lpy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 240.24909570302526,
			"y": 1154.1224792909243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 147.56793348736608,
			"height": 100.88828105768903,
			"seed": 813843249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					109.17015487585758,
					16.56374763633699
				],
				[
					109.92305249569117,
					-18.069542876003993
				],
				[
					144.55634300803203,
					32.37459765284039
				],
				[
					106.15856439652345,
					82.81873818168503
				],
				[
					106.15856439652356,
					47.55558001294412
				],
				[
					-3.0115904793340427,
					63.24340006601404
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 1207187437,
			"isDeleted": false,
			"id": "wjyw97Vf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 411.08601210594935,
			"y": 863.5968664393985,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 709.64111328125,
			"height": 100,
			"seed": 481789745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The data point X ∈ R is fed to the ML model and we get a prediction\nf (x) ∈ R\nWe try to explain the prediction of this given point by pointing out\nthe additive contribution of each input feature",
			"rawText": "The data point X ∈ R is fed to the ML model and we get a prediction\nf (x) ∈ R\nWe try to explain the prediction of this given point by pointing out\nthe additive contribution of each input feature",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The data point X ∈ R is fed to the ML model and we get a prediction\nf (x) ∈ R\nWe try to explain the prediction of this given point by pointing out\nthe additive contribution of each input feature",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 175982947,
			"isDeleted": false,
			"id": "7TCQJl6q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 633.4284182518987,
			"y": 848.8603998393473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 11.379989624023438,
			"height": 25,
			"seed": 2017824223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 414,
			"versionNonce": 1575006797,
			"isDeleted": false,
			"id": "0d_5CjVOChzDOKXZgMc0d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 613.24304602526,
			"y": 985.5929203642931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 36.10088098766664,
			"height": 228.03723157209456,
			"seed": 337231857,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 643,
			"versionNonce": 1936991491,
			"isDeleted": false,
			"id": "jLrNMSWm5xYN2bKubKIGf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.7058199878784,
			"y": 1071.1603982751756,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 36.10088098766664,
			"height": 72.30855625438592,
			"seed": 1693555889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 315,
			"versionNonce": 1225711789,
			"isDeleted": false,
			"id": "I52zIeb5hmtLm6YxBfka5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 648.1066662710573,
			"y": 1011.0976064880372,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 514140049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 333,
			"versionNonce": 1011780771,
			"isDeleted": false,
			"id": "lphiG1XI-wWC_3kEuQ1O4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.3325052366155,
			"y": 1034.3885468336446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 11256017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 339,
			"versionNonce": 1596474125,
			"isDeleted": false,
			"id": "QeU2pj4OYca1A65C5RD1s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 648.1066662710574,
			"y": 1056.4536482136948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 255582367,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 358,
			"versionNonce": 951779395,
			"isDeleted": false,
			"id": "3oGzKY_oi540gDegysJPN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 648.1066662710575,
			"y": 1076.9864508867965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1687547999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 360,
			"versionNonce": 78010733,
			"isDeleted": false,
			"id": "GiNB4X948cjlN1BeJ3qxo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.9454247193945,
			"y": 1099.9709314910149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 2133337439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 335,
			"versionNonce": 1117257699,
			"isDeleted": false,
			"id": "-bGnaAjKxkjzkOJ8f-G5X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 648.1066662710572,
			"y": 1122.9554120952332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1681743935,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 351,
			"versionNonce": 1389536205,
			"isDeleted": false,
			"id": "AzpPr-7Eh-NKZH2alVoAQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.026045495226,
			"y": 1145.0205134752825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1079735569,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 340,
			"versionNonce": 1945373571,
			"isDeleted": false,
			"id": "OhqDn0BTAQUGigiV2FvXd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 647.493746788278,
			"y": 1168.9243733036699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1207082655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 337,
			"versionNonce": 2110169645,
			"isDeleted": false,
			"id": "LfGVdXTVMlGU5EeixU4N7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.0260454952262,
			"y": 1189.7636357181611,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 191023633,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 432,
			"versionNonce": 554541859,
			"isDeleted": false,
			"id": "tGxuCwi0mReGUgkaBtDPr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 877.2868192529727,
			"y": 1094.0662949327086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1222718865,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 374,
			"versionNonce": 2053887117,
			"isDeleted": false,
			"id": "zjc_gOiznqqap9eLsNlwN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 875.7771770753584,
			"y": 1120.8624435853615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 544372543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-34.93641051841189,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 339,
			"versionNonce": 307447491,
			"isDeleted": false,
			"id": "iNFVYawcHlbPkLxtwXkxh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.5706762291851,
			"y": 1044.6255137683959,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 36.236024562434295,
			"height": 26.796148500098298,
			"seed": 569346833,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 371,
			"versionNonce": 1685830381,
			"isDeleted": false,
			"id": "MJpmFzmJWWDqjlN7h9Znw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.6478394473202,
			"y": 1143.4689550074074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 36.236024562434295,
			"height": 26.796148500098298,
			"seed": 1151588767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 600,
			"versionNonce": 2120447587,
			"isDeleted": false,
			"id": "P_CdElk43YANTP-weN6qK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 650.3177810551072,
			"y": 986.0184995207858,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.97704714180884,
			"height": 86.20778153917502,
			"seed": 950749055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					68.47125232298106,
					-0.4124774236324811
				],
				[
					121.26836254793034,
					85.38282669191028
				],
				[
					190.97704714180884,
					85.79530411554254
				]
			]
		},
		{
			"type": "line",
			"version": 786,
			"versionNonce": 612357453,
			"isDeleted": false,
			"id": "tHv44G781Xc4U_3ZMjAe5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.5858371330298,
			"y": 1010.1521705346584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.97704714180884,
			"height": 84.27330910184162,
			"seed": 8898801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					55.534294706522815,
					0.09485424760123351
				],
				[
					107.82407326023838,
					83.60716584259262
				],
				[
					190.97704714180884,
					84.27330910184162
				]
			]
		},
		{
			"type": "line",
			"version": 511,
			"versionNonce": 1141682691,
			"isDeleted": false,
			"id": "A2sshwM6AYA_FsKF2VwoN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.3577494265468,
			"y": 1093.9791346605991,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 191.63347074104036,
			"height": 59.61930200832376,
			"seed": 1383327711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-115.54788532089401,
					0
				],
				[
					-151.60336796402305,
					-59.61930200832376
				],
				[
					-191.63347074104036,
					-59.61930200832376
				]
			]
		},
		{
			"type": "line",
			"version": 483,
			"versionNonce": 1439802285,
			"isDeleted": false,
			"id": "WoNRMPSe6cNdEuvFD0W-r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.6416508646817,
			"y": 1094.8308389750039,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 191.63347074104036,
			"height": 38.61059558634315,
			"seed": 616050527,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-149.33215645894404,
					-0.4479610956275337
				],
				[
					-171.76037007159914,
					-38.61059558634315
				],
				[
					-191.63347074104036,
					-38.61059558634315
				]
			]
		},
		{
			"type": "line",
			"version": 783,
			"versionNonce": 1682799011,
			"isDeleted": false,
			"id": "uqNvgE0d8ytuPSFgIckkB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.8327465626744,
			"y": 1213.6896722509794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 191.4061782251083,
			"height": 70.77571620006199,
			"seed": 1303721553,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					74.69365303082304,
					-0.44578474296645254
				],
				[
					121.6974936312298,
					-70.36323877642974
				],
				[
					191.4061782251083,
					-70.77571620006199
				]
			]
		},
		{
			"type": "line",
			"version": 979,
			"versionNonce": 1822074381,
			"isDeleted": false,
			"id": "2CgPI2KpgvEE2p5pXs393",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.959064807196,
			"y": 1189.1268701538072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.54791605850937,
			"height": 69.15886693875962,
			"seed": 2134656049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					57.03625349807089,
					0.3342768356981196
				],
				[
					107.39494217693891,
					-68.1584468438125
				],
				[
					190.54791605850937,
					-68.8245901030615
				]
			]
		},
		{
			"type": "line",
			"version": 696,
			"versionNonce": 1012157763,
			"isDeleted": false,
			"id": "gfA4ApW6EMhQ8iUdN9j2E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 840.3018460174134,
			"y": 1120.7486250266468,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.56064303279175,
			"height": 48.03276275923872,
			"seed": 1818662417,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-115.54788532089401,
					0
				],
				[
					-148.8140159225767,
					48.03276275923872
				],
				[
					-190.56064303279175,
					48.03276275923872
				]
			]
		},
		{
			"type": "line",
			"version": 668,
			"versionNonce": 466902125,
			"isDeleted": false,
			"id": "C2SjMIX2buDVDlnGHZtBI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 841.4440096221473,
			"y": 1119.896920712242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 192.06260182433982,
			"height": 25.52209754571004,
			"seed": 1210821617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-149.33215645894404,
					0.4479610956275337
				],
				[
					-165.9671004470565,
					24.878400920760896
				],
				[
					-192.06260182433982,
					25.52209754571004
				]
			]
		},
		{
			"type": "line",
			"version": 632,
			"versionNonce": 2139073763,
			"isDeleted": false,
			"id": "w-BH613VJGPHJmFNHzck6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1148.3808571868226,
			"y": 1137.0201663915616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 262.69350174635133,
			"height": 142.22407353997966,
			"seed": 609773439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					197.33305005157013,
					29.455127194990013
				],
				[
					199.1448216890222,
					-14.93327792258323
				],
				[
					262.69350174635133,
					47.18823703340193
				],
				[
					201.86247914520004,
					127.29079561739641
				],
				[
					200.95659332647398,
					65.6905599440295
				],
				[
					2.5675990254836023,
					111.77388967570926
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 171,
			"versionNonce": 2068334285,
			"isDeleted": false,
			"id": "E0fBXiwg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1148.0004286549213,
			"y": 1077.690220467553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 198.9597625732422,
			"height": 50,
			"seed": 1667078783,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using Game theory's\nShapley Values!",
			"rawText": "Using Game theory's\nShapley Values!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using Game theory's\nShapley Values!",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1901992067,
			"isDeleted": false,
			"id": "9uk3y5Bo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1743.009372358586,
			"y": 836.5921191919117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 200.08883666992188,
			"height": 35,
			"seed": 1817167729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Shapley Values",
			"rawText": "Shapley Values",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Shapley Values",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 523,
			"versionNonce": 1838146861,
			"isDeleted": false,
			"id": "IE047TRc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1441.3764036702246,
			"y": 872.6304565538951,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 790.4991455078125,
			"height": 125,
			"seed": 431708049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A model agnostic commonly used technique to interpret the way the model works\n\nAnswers the question\n\"how much do each of the features contribute to the difference\nbetween our prediction and the average prediction?\"",
			"rawText": "A model agnostic commonly used technique to interpret the way the model works\n\nAnswers the question\n\"how much do each of the features contribute to the difference\nbetween our prediction and the average prediction?\"",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A model agnostic commonly used technique to interpret the way the model works\n\nAnswers the question\n\"how much do each of the features contribute to the difference\nbetween our prediction and the average prediction?\"",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 267,
			"versionNonce": 1605242915,
			"isDeleted": false,
			"id": "k09qtxPm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1627.4175478220563,
			"y": 1005.38027984725,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 431.27248521725227,
			"height": 61.053634955454385,
			"seed": 57132,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fcfe356af748b0b3ad0e721471e8e2ecfafcd884",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 247,
			"versionNonce": 1175762829,
			"isDeleted": false,
			"id": "KcfSssYFOxpip2xCrIwf3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2193.6494236446706,
			"y": 1135.3256592711452,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 717.8853339070745,
			"height": 1.1061407302111093,
			"seed": 694624351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					-717.8853339070745,
					1.1061407302111093
				]
			]
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 1549669315,
			"isDeleted": false,
			"id": "NWCVs3io",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1664.6196243769243,
			"y": 1148.3531031285534,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 358.4595947265625,
			"height": 50,
			"seed": 449625759,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Example:\nCalculate the shapley Values of f(1)",
			"rawText": "Example:\nCalculate the shapley Values of f(1)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example:\nCalculate the shapley Values of f(1)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 268,
			"versionNonce": 789593581,
			"isDeleted": false,
			"id": "PIVWNjxb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1749.1471653340188,
			"y": 1202.6952358807257,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 191.2462396546812,
			"height": 21.820040765970344,
			"seed": 36151,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "23b4752a5c67771f34c95cb0756787749d05c05a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 315,
			"versionNonce": 931963747,
			"isDeleted": false,
			"id": "JGHEejBQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2055.0399042990302,
			"y": 1168.1695669516955,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 156.33636474609375,
			"height": 40,
			"seed": 1325348255,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that Xi\nare binary variables",
			"rawText": "Note that Xi\nare binary variables",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that Xi\nare binary variables",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 190,
			"versionNonce": 1334573133,
			"isDeleted": false,
			"id": "c92i9_VgMSua2ZJHHy1v4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2028.2241326933683,
			"y": 1185.2207845809796,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 50.54985251909602,
			"height": 1.9257086673942467,
			"seed": 285401553,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					50.54985251909602,
					-1.9257086673942467
				]
			]
		},
		{
			"type": "line",
			"version": 520,
			"versionNonce": 965230339,
			"isDeleted": false,
			"id": "sCDbRRdm6qc6XNgr5rHtJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1469.758162062449,
			"y": 1268.5330888494987,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 306.0805238834559,
			"height": 0.8643259219773722,
			"seed": 2008705553,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					306.0805238834559,
					0.8643259219773722
				]
			]
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 828466861,
			"isDeleted": false,
			"id": "rKA-qrtoh_nglb1Kge_Zf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1518.9227111980167,
			"y": 1242.4415843463787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 1.832460032675408,
			"height": 191.18666340914126,
			"seed": 140047295,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					1.832460032675408,
					191.18666340914126
				]
			]
		},
		{
			"type": "line",
			"version": 501,
			"versionNonce": 483354275,
			"isDeleted": false,
			"id": "pEb6icLtcdAy4yJ5CToIS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1606.8807927664395,
			"y": 1244.2740443790542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 3.664920065351193,
			"height": 179.58108320219657,
			"seed": 754095953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					3.664920065351193,
					179.58108320219657
				]
			]
		},
		{
			"type": "line",
			"version": 539,
			"versionNonce": 1731856653,
			"isDeleted": false,
			"id": "KVHnBlBeULQJf0TXKQjD1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1700.9329872346393,
			"y": 1245.1494574680926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 3.664920065351193,
			"height": 179.58108320219657,
			"seed": 1196761201,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					3.664920065351193,
					179.58108320219657
				]
			]
		},
		{
			"type": "text",
			"version": 392,
			"versionNonce": 1209047619,
			"isDeleted": false,
			"id": "4FcItLT4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1488.4715173885727,
			"y": 1243.954147374197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 9.5,
			"height": 19.54999305429166,
			"seed": 650713407,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 1,
			"text": "S",
			"rawText": "S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "S",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 394,
			"versionNonce": 1921998701,
			"isDeleted": false,
			"id": "WJk33SGt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1470.4393429323109,
			"y": 1279.4409257580485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 42.484375,
			"height": 136.84995138004163,
			"seed": 287979953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 1,
			"text": "{}\n\n{2}\n\n{3}\n\n{2,3}",
			"rawText": "{}\n\n{2}\n\n{3}\n\n{2,3}",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "{}\n\n{2}\n\n{3}\n\n{2,3}",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 383,
			"versionNonce": 1210735075,
			"isDeleted": false,
			"id": "xVaDiTts",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1712.8513381723446,
			"y": 1243.5992931810736,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 55.90019226074219,
			"height": 15.639994443433329,
			"seed": 1752174033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 12.511995554746663,
			"fontFamily": 1,
			"text": "Multiplied",
			"rawText": "Multiplied",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multiplied",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 405,
			"versionNonce": 1772808653,
			"isDeleted": false,
			"id": "zpINHeHT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1553.9411623584078,
			"y": 1277.6232346441018,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 20175,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cc056000ddb1cac084b8a0debab4694e165acd4f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 461,
			"versionNonce": 170599811,
			"isDeleted": false,
			"id": "UW6SuDlopzYG4I7nwsg3u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1554.836987540754,
			"y": 1313.751739827973,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 479863217,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f1396a6bd9590abbbd0ffabd4e4c2e2e6e8efdc6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 457,
			"versionNonce": 1571170349,
			"isDeleted": false,
			"id": "2-KySOvjDAIKmryvwD00P",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1554.836987540754,
			"y": 1349.5847471218333,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 1139827313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5ade8a6ac9fe92bf6a8d5e0626037f12f61718f9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 480,
			"versionNonce": 1431403811,
			"isDeleted": false,
			"id": "JW0qFswhXSthD7awacFBZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1555.2351320662415,
			"y": 1393.7787894509286,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 139718079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c73b77695b59f3f835e5c51d0510d5bd792a8471",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 377,
			"versionNonce": 6986381,
			"isDeleted": false,
			"id": "sSWPXB4R",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1645.2525027765037,
			"y": 1282.0104537778827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1249469919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 402,
			"versionNonce": 84664515,
			"isDeleted": false,
			"id": "chDmRHvy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1646.2675315244892,
			"y": 1316.5187703686431,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1218971569,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 397,
			"versionNonce": 179421421,
			"isDeleted": false,
			"id": "tyP4l6Wy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1646.9412020396358,
			"y": 1358.168492960032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1710007871,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 396,
			"versionNonce": 49860707,
			"isDeleted": false,
			"id": "7It7ZHcA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1649.399058961009,
			"y": 1394.4573472936786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1693003601,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "2",
			"rawText": "2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 410,
			"versionNonce": 1644501837,
			"isDeleted": false,
			"id": "CLYHDqqy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1737.452591464272,
			"y": 1282.166083205515,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1707112625,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.15
		},
		{
			"type": "image",
			"version": 509,
			"versionNonce": 15125507,
			"isDeleted": false,
			"id": "cDqrCND_8rd9ktipqXrV_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1736.538963905145,
			"y": 1315.1228247038928,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 1092054001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f953ac4204f521d0ed225c111bddf6cd6c6fd945",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 507,
			"versionNonce": 2126391725,
			"isDeleted": false,
			"id": "0PXxdDgM0Z-tm-CitrzQS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1737.9591842250202,
			"y": 1355.6898997306691,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 1611056593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4ef8c161196b6a9dfab5e4858ceeea2936b8064e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 527,
			"versionNonce": 1926517667,
			"isDeleted": false,
			"id": "Jf3OcW0WD8P-Wfh5x-hAZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1739.379404544895,
			"y": 1395.0556156520252,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 1473147327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "74866e79cafd90e200302b662c1d58b500de33ad",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 1897,
			"versionNonce": 302410765,
			"isDeleted": false,
			"id": "hOuK1iK14LDKK9z9Pb_8m",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1770.0861350388616,
			"y": 1281.045221750061,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 10.416287115776326,
			"height": 149.45928843492527,
			"seed": 769130303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					1.470534651639023,
					0.06387149078415681
				],
				[
					3.3087029661878877,
					0.25548596313662725
				],
				[
					4.166514846310565,
					1.7245302511721892
				],
				[
					4.901782172130076,
					5.620691189005754
				],
				[
					5.14687128073658,
					12.13558324898966
				],
				[
					5.2694158350399185,
					26.187311221504018
				],
				[
					5.2694158350399185,
					42.09131242675889
				],
				[
					5.02432672643332,
					60.55017326337999
				],
				[
					5.146871280736752,
					66.29860743395405
				],
				[
					5.759594052252925,
					70.32251135335588
				],
				[
					6.617405932375603,
					73.77157185570032
				],
				[
					7.842851475408122,
					75.49610210687256
				],
				[
					10.416287115776326,
					76.2625599962824
				],
				[
					7.720306921104784,
					76.83740341333981
				],
				[
					6.127227715162595,
					79.58387751705853
				],
				[
					5.14687128073658,
					93.2523765448679
				],
				[
					5.391960389343085,
					108.58153433306538
				],
				[
					5.759594052252925,
					123.84682063047867
				],
				[
					5.759594052252925,
					138.9204924555395
				],
				[
					5.391960389343085,
					145.56312749709173
				],
				[
					3.6763366290975577,
					149.01218799943618
				],
				[
					0.36763366290984156,
					149.45928843492527
				]
			]
		},
		{
			"type": "image",
			"version": 432,
			"versionNonce": 1223681859,
			"isDeleted": false,
			"id": "ZeOUQ14x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1790.4384338145817,
			"y": 1345.2341839982946,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51.053083083939036,
			"height": 15.95408846373095,
			"seed": 79052,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "80a8f1878caa3bccc2f7a0ee5d72d288d9b44181",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 649,
			"versionNonce": 1809277549,
			"isDeleted": false,
			"id": "CZctu5Uh0mHHQh59k60-H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1855.5515308189545,
			"y": 1267.6124590979618,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 306.0805238834559,
			"height": 0.8643259219773722,
			"seed": 1986928881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					306.0805238834559,
					0.8643259219773722
				]
			]
		},
		{
			"type": "line",
			"version": 580,
			"versionNonce": 1771570915,
			"isDeleted": false,
			"id": "KeUF69O_GXdHARrb1tPFa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1904.7160799545222,
			"y": 1241.5209545948417,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 1.832460032675408,
			"height": 191.18666340914126,
			"seed": 46062289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					1.832460032675408,
					191.18666340914126
				]
			]
		},
		{
			"type": "line",
			"version": 604,
			"versionNonce": 553290957,
			"isDeleted": false,
			"id": "8SCSkZuO-eVx_Fqi_I-Ym",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1992.674161522945,
			"y": 1243.3534146275172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 3.664920065351193,
			"height": 179.58108320219657,
			"seed": 480073905,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					3.664920065351193,
					179.58108320219657
				]
			]
		},
		{
			"type": "line",
			"version": 642,
			"versionNonce": 1801138819,
			"isDeleted": false,
			"id": "F1_fMCaWBarUwXEGGBhPN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2086.7263559911444,
			"y": 1244.2288277165555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 3.664920065351193,
			"height": 179.58108320219657,
			"seed": 1437670033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					3.664920065351193,
					179.58108320219657
				]
			]
		},
		{
			"type": "text",
			"version": 521,
			"versionNonce": 1896442669,
			"isDeleted": false,
			"id": "ArSCcuaC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1874.2648861450782,
			"y": 1243.0335176226602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 9.5,
			"height": 19.54999305429166,
			"seed": 514957425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 1,
			"text": "S",
			"rawText": "S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "S",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 527,
			"versionNonce": 251128355,
			"isDeleted": false,
			"id": "HrgtU4nE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1859.6780241888166,
			"y": 1278.5202960065114,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 35.59375,
			"height": 136.84995138004163,
			"seed": 1701210705,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 1,
			"text": "{}\n\n{1}\n\n{3}\n\n{1,3}",
			"rawText": "{}\n\n{1}\n\n{3}\n\n{1,3}",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "{}\n\n{1}\n\n{3}\n\n{1,3}",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 486,
			"versionNonce": 1819114893,
			"isDeleted": false,
			"id": "4sdJKBf2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2098.6447069288497,
			"y": 1242.6786634295365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 55.90019226074219,
			"height": 15.639994443433329,
			"seed": 1064919025,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 12.511995554746663,
			"fontFamily": 1,
			"text": "Multiplied",
			"rawText": "Multiplied",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multiplied",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 508,
			"versionNonce": 2036116931,
			"isDeleted": false,
			"id": "yP-xPr_ju2IhjxU5eZuTa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1939.7345311149131,
			"y": 1276.7026048925648,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 638204369,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6207cc7ea4d800884cd998c1f6dddebffedc0496",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 564,
			"versionNonce": 1516258285,
			"isDeleted": false,
			"id": "3MFP5IiZD44ALNaZmbw_G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1940.6303562972591,
			"y": 1312.831110076436,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 488953777,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e963a6c850644e44618007a9544bf3f62b762990",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 560,
			"versionNonce": 765984099,
			"isDeleted": false,
			"id": "WnSe3Zgcz7xzpiN25CYfF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1940.6303562972591,
			"y": 1348.6641173702963,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 1995487633,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4b336c81a45d4dbbc02456fe2b90703d3e44a610",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 583,
			"versionNonce": 1592475213,
			"isDeleted": false,
			"id": "kvztY_rUBfcNz0hOb9yUI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1941.0285008227468,
			"y": 1392.8581596993915,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 1420124017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "55637311ca3570642eb9e966ddfbc5111177c770",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 480,
			"versionNonce": 1193826563,
			"isDeleted": false,
			"id": "sBNYH9OJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2031.045871533009,
			"y": 1281.0898240263457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1149913425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 505,
			"versionNonce": 1625812141,
			"isDeleted": false,
			"id": "yhfSU1aA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2032.0609002809942,
			"y": 1315.598140617106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 536278833,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 1935425699,
			"isDeleted": false,
			"id": "55DBKrde",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2032.7345707961415,
			"y": 1357.2478632084951,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 693299473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 500,
			"versionNonce": 805293837,
			"isDeleted": false,
			"id": "PJnJydAD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2035.192427717514,
			"y": 1393.5367175421418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1779801841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 513,
			"versionNonce": 737293379,
			"isDeleted": false,
			"id": "FVJsoIQj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2123.2459602207773,
			"y": 1281.2454534539777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 1355192529,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.15
		},
		{
			"type": "image",
			"version": 612,
			"versionNonce": 1789683053,
			"isDeleted": false,
			"id": "BdrgL1a61Zox69D5Gfr5H",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2122.33233266165,
			"y": 1314.2021949523557,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 251483825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0facc82f877771cbe87b5b64ff4a61b416806c9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 630,
			"versionNonce": 818459619,
			"isDeleted": false,
			"id": "Q1eCwH4aB_7V-hGphCmIN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2125.1727733014004,
			"y": 1394.134985900488,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.511995554746663,
			"height": 26.58799055383666,
			"seed": 464133745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f0b2afe17e205490a780d6b502244f18f18cd50",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 2000,
			"versionNonce": 607596493,
			"isDeleted": false,
			"id": "kFF4ZiInpvZXRNw7Q7Bl8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2155.879503795367,
			"y": 1280.1245919985242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 10.416287115776326,
			"height": 149.45928843492527,
			"seed": 1788815441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					1.470534651639023,
					0.06387149078415681
				],
				[
					3.3087029661878877,
					0.25548596313662725
				],
				[
					4.166514846310565,
					1.7245302511721892
				],
				[
					4.901782172130076,
					5.620691189005754
				],
				[
					5.14687128073658,
					12.13558324898966
				],
				[
					5.2694158350399185,
					26.187311221504018
				],
				[
					5.2694158350399185,
					42.09131242675889
				],
				[
					5.02432672643332,
					60.55017326337999
				],
				[
					5.146871280736752,
					66.29860743395405
				],
				[
					5.759594052252925,
					70.32251135335588
				],
				[
					6.617405932375603,
					73.77157185570032
				],
				[
					7.842851475408122,
					75.49610210687256
				],
				[
					10.416287115776326,
					76.2625599962824
				],
				[
					7.720306921104784,
					76.83740341333981
				],
				[
					6.127227715162595,
					79.58387751705853
				],
				[
					5.14687128073658,
					93.2523765448679
				],
				[
					5.391960389343085,
					108.58153433306538
				],
				[
					5.759594052252925,
					123.84682063047867
				],
				[
					5.759594052252925,
					138.9204924555395
				],
				[
					5.391960389343085,
					145.56312749709173
				],
				[
					3.6763366290975577,
					149.01218799943618
				],
				[
					0.36763366290984156,
					149.45928843492527
				]
			]
		},
		{
			"type": "image",
			"version": 547,
			"versionNonce": 1106132867,
			"isDeleted": false,
			"id": "I1MJJebIUtSdUQ3T3vBvj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2177.7543755171837,
			"y": 1333.949046773046,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51.795194428985,
			"height": 32.018847465190724,
			"seed": 236451377,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d8ead9ad8b9f20e2611caaa2a7595bc886e0aa0f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 525,
			"versionNonce": 1253682733,
			"isDeleted": false,
			"id": "7N5qQmXO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2126.151745995081,
			"y": 1358.3641249041605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 8.68988037109375,
			"height": 17.985993609948327,
			"seed": 2034123359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.639994443433329,
			"fontFamily": 2,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.15
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 430004003,
			"isDeleted": false,
			"id": "TKJmYYl0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1639.8616767542464,
			"y": 1246.5472839317413,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 21.213203435596427,
			"height": 10.182337649086284,
			"seed": 53962,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1db460809fd50c98d3d585a8e3e27792df093304",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 159,
			"versionNonce": 1293770893,
			"isDeleted": false,
			"id": "kK9HauXd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1549.2248059693195,
			"y": 1247.0901531152088,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 10,
			"seed": 26236,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0add2362b0353f46b5f7c838af954f84fe7f4ef",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 185,
			"versionNonce": 642808515,
			"isDeleted": false,
			"id": "QOa6mzXM3Cuaq6VpBeIuH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1935.089837580472,
			"y": 1251.0390023467426,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 10,
			"seed": 1957112721,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0a56346bd1d113f21655691d79e1d4d4e436e2bc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 162,
			"versionNonce": 18597613,
			"isDeleted": false,
			"id": "_nJir4dggzx85b8t8aLX6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2025.2750080064745,
			"y": 1243.2689274204852,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 21.213203435596427,
			"height": 10.182337649086284,
			"seed": 1673832351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2d22ec7c05b3d162fdec98a5aad689bfdaa1d375",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 2110,
			"versionNonce": 77212259,
			"isDeleted": false,
			"id": "3N6XIyZUTnH7P043IwYE1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948948,
			"x": 1963.8769000787797,
			"y": 979.2299956287943,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 10.416287115776326,
			"height": 149.45928843492527,
			"seed": 1449066367,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					1.470534651639023,
					0.06387149078415681
				],
				[
					3.3087029661878877,
					0.25548596313662725
				],
				[
					4.166514846310565,
					1.7245302511721892
				],
				[
					4.901782172130076,
					5.620691189005754
				],
				[
					5.14687128073658,
					12.13558324898966
				],
				[
					5.2694158350399185,
					26.187311221504018
				],
				[
					5.2694158350399185,
					42.09131242675889
				],
				[
					5.02432672643332,
					60.55017326337999
				],
				[
					5.146871280736752,
					66.29860743395405
				],
				[
					5.759594052252925,
					70.32251135335588
				],
				[
					6.617405932375603,
					73.77157185570032
				],
				[
					7.842851475408122,
					75.49610210687256
				],
				[
					10.416287115776326,
					76.2625599962824
				],
				[
					7.720306921104784,
					76.83740341333981
				],
				[
					6.127227715162595,
					79.58387751705853
				],
				[
					5.14687128073658,
					93.2523765448679
				],
				[
					5.391960389343085,
					108.58153433306538
				],
				[
					5.759594052252925,
					123.84682063047867
				],
				[
					5.759594052252925,
					138.9204924555395
				],
				[
					5.391960389343085,
					145.56312749709173
				],
				[
					3.6763366290975577,
					149.01218799943618
				],
				[
					0.36763366290984156,
					149.45928843492527
				]
			]
		},
		{
			"type": "image",
			"version": 192,
			"versionNonce": 1228824909,
			"isDeleted": false,
			"id": "hGmmelthk7Fxvuju9NW2F",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1957.1016283514953,
			"y": 1065.3911840763208,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 21.213203435596427,
			"height": 10.182337649086284,
			"seed": 84899409,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4dbd5afe7b20d5ad24e3116e9a29deb4ce07dec1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 2133,
			"versionNonce": 961340931,
			"isDeleted": false,
			"id": "hq3WmoWl7qTsdOFag0oNp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948948,
			"x": 1797.7319202168546,
			"y": 981.5247376992022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 10.416287115776326,
			"height": 149.45928843492527,
			"seed": 1760622911,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					1.470534651639023,
					0.06387149078415681
				],
				[
					3.3087029661878877,
					0.25548596313662725
				],
				[
					4.166514846310565,
					1.7245302511721892
				],
				[
					4.901782172130076,
					5.620691189005754
				],
				[
					5.14687128073658,
					12.13558324898966
				],
				[
					5.2694158350399185,
					26.187311221504018
				],
				[
					5.2694158350399185,
					42.09131242675889
				],
				[
					5.02432672643332,
					60.55017326337999
				],
				[
					5.146871280736752,
					66.29860743395405
				],
				[
					5.759594052252925,
					70.32251135335588
				],
				[
					6.617405932375603,
					73.77157185570032
				],
				[
					7.842851475408122,
					75.49610210687256
				],
				[
					10.416287115776326,
					76.2625599962824
				],
				[
					7.720306921104784,
					76.83740341333981
				],
				[
					6.127227715162595,
					79.58387751705853
				],
				[
					5.14687128073658,
					93.2523765448679
				],
				[
					5.391960389343085,
					108.58153433306538
				],
				[
					5.759594052252925,
					123.84682063047867
				],
				[
					5.759594052252925,
					138.9204924555395
				],
				[
					5.391960389343085,
					145.56312749709173
				],
				[
					3.6763366290975577,
					149.01218799943618
				],
				[
					0.36763366290984156,
					149.45928843492527
				]
			]
		},
		{
			"type": "image",
			"version": 214,
			"versionNonce": 2061414317,
			"isDeleted": false,
			"id": "NQsM6qxOlXNC2DLStAZqj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1791.1042067686753,
			"y": 1070.530959667549,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 10,
			"seed": 1588598239,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63d6178c8dfe8d0f28b21d7c3a0b814b8fb71a9f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 157,
			"versionNonce": 728182179,
			"isDeleted": false,
			"id": "6RJN04nMDMMpP7iNfj5gS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1783.798507611963,
			"y": 1044.337457934754,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 49.42865849345344,
			"height": 55.81550762463007,
			"seed": 342250417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					-29.712732914603976,
					4.443025482557687
				],
				[
					-29.157354729284407,
					45.54101119621555
				],
				[
					-49.42865849345344,
					55.81550762463007
				]
			]
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 69612045,
			"isDeleted": false,
			"id": "ooZd71mJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1651.8545487751267,
			"y": 1094.791139949147,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 74.31568908691406,
			"height": 19.53195099650284,
			"seed": 133278161,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 15.62556079720227,
			"fontFamily": 1,
			"text": "dimensions",
			"rawText": "dimensions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dimensions",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 134,
			"versionNonce": 1578598723,
			"isDeleted": false,
			"id": "BULYO5HcuJOJGa46QSPbj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1674.9443832893014,
			"y": 1062.664938050304,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 59.98084401452775,
			"height": 24.436640154066936,
			"seed": 658025375,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					-24.71432924672672,
					5.831470945856836
				],
				[
					-28.879665636624395,
					24.436640154066936
				],
				[
					-59.98084401452775,
					20.548992856829045
				]
			]
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 1376675949,
			"isDeleted": false,
			"id": "jwy1zUem",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1547.7904961189065,
			"y": 1067.6403057186299,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 73.41059875488281,
			"height": 41.7118628801459,
			"seed": 1437012031,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 11.123163434705573,
			"fontFamily": 1,
			"text": "all possible\nsubsets that\ndont include i",
			"rawText": "all possible\nsubsets that\ndont include i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all possible\nsubsets that\ndont include i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 1790730467,
			"isDeleted": false,
			"id": "OG5Kr184",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1877.2647003322652,
			"y": 1431.0976076770203,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 303.2413635253906,
			"height": 13.87345836653159,
			"seed": 1793549919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 11.098766693225272,
			"fontFamily": 1,
			"text": "very similar calculation for phi3 so its the same result",
			"rawText": "very similar calculation for phi3 so its the same result",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "very similar calculation for phi3 so its the same result",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 149,
			"versionNonce": 1986056909,
			"isDeleted": false,
			"id": "3vZXbmMw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1770.3560750457389,
			"y": 1465.8106081134372,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 123.42525445230784,
			"height": 18.734190407939582,
			"seed": 56695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a0f443f362bc99e6fc58091ccd3a586d0cced23b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 460,
			"versionNonce": 988040323,
			"isDeleted": false,
			"id": "rzoNYZprSAPACEyAigwQA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1708.0310953717474,
			"y": 1507.0239684254345,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51.053083083939036,
			"height": 15.95408846373095,
			"seed": 340440721,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0c90471c5fe361d4d97e4d758e7f8dacb50f4129",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 2239,
			"versionNonce": 230093101,
			"isDeleted": false,
			"id": "dnXNtu6z-6Qn8W3LpUTw_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948948,
			"x": 1839.9560449319401,
			"y": 1640.0413876255448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 11.940829115361137,
			"height": 286.6701545873297,
			"seed": 1504242175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					-1.6857641104039391,
					-0.12250861307151695
				],
				[
					-3.7929692484089617,
					-0.49003445228603937
				],
				[
					-4.776331646144494,
					-3.3077325529306734
				],
				[
					-5.619213701346464,
					-10.78075795029278
				],
				[
					-5.900174386413786,
					-23.2766364835866
				],
				[
					-6.040654728947548,
					-50.22853135931848
				],
				[
					-6.040654728947548,
					-80.7331760141241
				],
				[
					-5.759694043880116,
					-116.13816519179
				],
				[
					-5.900174386413984,
					-127.1639403682258
				],
				[
					-6.602576099082193,
					-134.8819829917308
				],
				[
					-7.585938496817726,
					-141.49744809759227
				],
				[
					-8.990741922154342,
					-144.80518065052306
				],
				[
					-11.940829115361137,
					-146.27528400738112
				],
				[
					-8.850261579620582,
					-147.3778615250247
				],
				[
					-7.02401712668308,
					-152.64573188709954
				],
				[
					-5.900174386413786,
					-178.8625750844023
				],
				[
					-6.181135071481111,
					-208.26464222156434
				],
				[
					-6.602576099082193,
					-237.54420074565485
				],
				[
					-6.602576099082193,
					-266.45623343053074
				],
				[
					-6.181135071481111,
					-279.19712918996765
				],
				[
					-4.214410276009848,
					-285.8125942958292
				],
				[
					-0.42144102760108315,
					-286.6701545873297
				]
			]
		},
		{
			"type": "image",
			"version": 589,
			"versionNonce": 38650915,
			"isDeleted": false,
			"id": "E5V_6Ens94CxaxhZAs2go",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1815.5939195443186,
			"y": 1498.9915895657623,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51.795194428985,
			"height": 32.018847465190724,
			"seed": 1991458303,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6ea1df09ec87a2efb9e0d35885d56d1367b9342b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 573,
			"versionNonce": 1702511501,
			"isDeleted": false,
			"id": "YfNt7hrAwQHe5Dvy5clJW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1915.9130352867687,
			"y": 1498.9915897452333,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51.795194428985,
			"height": 32.018847465190724,
			"seed": 1473403775,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c005e79e72eeeb46ebbf96e80c11017c2fcc3958",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 1253,
			"versionNonce": 2028423107,
			"isDeleted": false,
			"id": "gLYWeK-qDYvv7VdVZ5if_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2272.6060201992796,
			"y": 1262.139420134669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 499.66628336708345,
			"height": 1107.6519696282908,
			"seed": 94224223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
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
					373.71537010090753,
					12.766674133881963
				],
				[
					355.14566226980617,
					776.4459086879097
				],
				[
					111.72518433579029,
					795.2417126302732
				],
				[
					110.38374822351398,
					710.8117401590756
				],
				[
					13.87745681146231,
					820.2587874943393
				],
				[
					112.50759007683251,
					913.6720094745463
				],
				[
					113.28564263154846,
					837.2060170679554
				],
				[
					438.7303583225408,
					845.6064090546545
				],
				[
					498.8083693307626,
					-62.91071592990781
				],
				[
					-0.8579140363208637,
					-193.9799601537445
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 501,
			"versionNonce": 1642351085,
			"isDeleted": false,
			"id": "LKsZ9mHi",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1735.8130877382648,
			"y": 1777.0015206167106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 464.57904052734375,
			"height": 54.14142336509372,
			"seed": 439124849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 21.65656934603749,
			"fontFamily": 1,
			"text": "We (some nerd) observed that that the\nshapley values formula can be rewritten as",
			"rawText": "We (some nerd) observed that that the\nshapley values formula can be rewritten as",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We (some nerd) observed that that the\nshapley values formula can be rewritten as",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 441,
			"versionNonce": 1422874467,
			"isDeleted": false,
			"id": "6amzfxkV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1722.6133200441184,
			"y": 1865.268505329758,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 480.4356663598636,
			"height": 72.99905884619835,
			"seed": 20415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "11c5021f9fcb9f0b221ed248334029be54ca29cf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 603882573,
			"isDeleted": false,
			"id": "go1cLyfgna1eKEMSidOHE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1854.7343667026396,
			"y": 1940.9992242891833,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 14.172533579913486,
			"height": 57.23523176503547,
			"seed": 2054714655,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					-14.172533579913486,
					57.23523176503547
				]
			]
		},
		{
			"type": "text",
			"version": 405,
			"versionNonce": 72643331,
			"isDeleted": false,
			"id": "0yCbqhkW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1737.8577524936293,
			"y": 2005.4745842321256,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 123.524169921875,
			"height": 54.14142336509372,
			"seed": 371759857,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 21.65656934603749,
			"fontFamily": 1,
			"text": "all possible\npermutation",
			"rawText": "all possible\npermutation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all possible\npermutation",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 525,
			"versionNonce": 1872917165,
			"isDeleted": false,
			"id": "vae8c5MIAmH7OJFhCsFC3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2121.6990504371634,
			"y": 1917.6722885623574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 5.379548135517677,
			"height": 59.34897032886578,
			"seed": 1090073777,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					5.379548135517677,
					59.34897032886578
				]
			]
		},
		{
			"type": "text",
			"version": 557,
			"versionNonce": 670374563,
			"isDeleted": false,
			"id": "ezJROd0j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2065.2365597366033,
			"y": 1983.8087639528642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 140.0853271484375,
			"height": 87.14546109188367,
			"seed": 1714270033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 17.429092218376734,
			"fontFamily": 1,
			"text": "set of features\nthat precede\nfeature i in the\norder of S",
			"rawText": "set of features\nthat precede\nfeature i in the\norder of S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "set of features\nthat precede\nfeature i in the\norder of S",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 551,
			"versionNonce": 1366922509,
			"isDeleted": false,
			"id": "xG8qmSnEuVYsa2XbwRNaF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1945.4660976778048,
			"y": 1927.1841120995934,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 3.7942442126444806,
			"height": 54.59305856024743,
			"seed": 1756324561,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531070,
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
					3.7942442126444806,
					54.59305856024743
				]
			]
		},
		{
			"type": "text",
			"version": 577,
			"versionNonce": 1281347139,
			"isDeleted": false,
			"id": "uBZX9YOB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1888.15606428677,
			"y": 1987.795151093106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 140.0853271484375,
			"height": 108.9318263648546,
			"seed": 1388184511,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 17.429092218376734,
			"fontFamily": 1,
			"text": "set of features\nthat precede\nfeature i in the\norder of S\nINCLUDING i",
			"rawText": "set of features\nthat precede\nfeature i in the\norder of S\nINCLUDING i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "set of features\nthat precede\nfeature i in the\norder of S\nINCLUDING i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 270,
			"versionNonce": 83716973,
			"isDeleted": false,
			"id": "s8VTlnTU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1794.7853884852418,
			"y": 1736.8741413945506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 321.9173583984375,
			"height": 35,
			"seed": 1120479263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Shapley Values Sampling",
			"rawText": "Shapley Values Sampling",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Shapley Values Sampling",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 440,
			"versionNonce": 1685261795,
			"isDeleted": false,
			"id": "1tZum2bx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1684.956316025044,
			"y": 2117.8469819448073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 571.6793212890625,
			"height": 75,
			"seed": 1745489265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can calculate the approximation of the shapley value\nby uniformly sampling from all subsets \nThe accuracy of the approximation scales with T->infinity",
			"rawText": "We can calculate the approximation of the shapley value\nby uniformly sampling from all subsets \nThe accuracy of the approximation scales with T->infinity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can calculate the approximation of the shapley value\nby uniformly sampling from all subsets \nThe accuracy of the approximation scales with T->infinity",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 498,
			"versionNonce": 444036557,
			"isDeleted": false,
			"id": "1XP_Wqb15TYcmzNlwTM6I",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1710.2445117779434,
			"y": 2193.8564390523807,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 505.17328407448764,
			"height": 69.42439868859917,
			"seed": 1947233137,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531070,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1a63bac8b79ad337d987cd72a581eb652446c9f8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 164,
			"versionNonce": 54352259,
			"isDeleted": false,
			"id": "bmw3dwaK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1760.4828575342408,
			"y": 2270.538271692936,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 415.239501953125,
			"height": 25,
			"seed": 334434463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Still computationally expensive for large d",
			"rawText": "Still computationally expensive for large d",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Still computationally expensive for large d",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 638,
			"versionNonce": 1560359981,
			"isDeleted": false,
			"id": "bQjC2EWwrrVue5PlXXWrS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2541.910132277003,
			"y": 1382.1691687247464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 330.3676241451107,
			"height": 423.04414772437354,
			"seed": 1565231505,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 631,
			"versionNonce": 1442656547,
			"isDeleted": false,
			"id": "QVdKgzKi86_5XAPf_zUB4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2532.1807459989213,
			"y": 1386.760428831715,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d2bab0",
			"width": 330.3676241451107,
			"height": 423.04414772437354,
			"seed": 1193684849,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 292,
			"versionNonce": 2021926541,
			"isDeleted": false,
			"id": "4AIuNbGDlgV_aJMm-SJWl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2558.5283239611726,
			"y": 1721.450941384127,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 1316034897,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 346,
			"versionNonce": 1579226307,
			"isDeleted": false,
			"id": "uJXXtDn8o-BUUMhfgLFE0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2498.525423097233,
			"y": 1715.405169440916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1686357809,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 302,
			"versionNonce": 1606012141,
			"isDeleted": false,
			"id": "o0_ufR8nxpxKlyYYtBt24",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2561.0829332321264,
			"y": 1666.668764795868,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 1673902353,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 318,
			"versionNonce": 1799849059,
			"isDeleted": false,
			"id": "frRj1bRqbcFeegjPtAbZ-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2562.2183151303298,
			"y": 1607.6289060893523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 1840148209,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 325,
			"versionNonce": 1915463501,
			"isDeleted": false,
			"id": "_hnXXUCD_dxwfYrdSFkAp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2559.9475513339253,
			"y": 1550.2921202301397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 147155153,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 324,
			"versionNonce": 1430192131,
			"isDeleted": false,
			"id": "mRGzeHeToKlxXZAeWbw59",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2562.7860060794305,
			"y": 1491.8199524727252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 2124555953,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 317,
			"versionNonce": 1647523245,
			"isDeleted": false,
			"id": "Sai8i4eLu_ckGsqjsDzJf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2561.6506241812285,
			"y": 1433.9154756644111,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 2045520017,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 337,
			"versionNonce": 1980106659,
			"isDeleted": false,
			"id": "OebiI-8Uv5PRVFYEEzc-m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2497.883294755186,
			"y": 1427.0895438615178,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1683680881,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 334,
			"versionNonce": 1526331405,
			"isDeleted": false,
			"id": "KQWjtk0JKZdY8UfteMxmE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2499.1675514392823,
			"y": 1486.165351329903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 79034449,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 353,
			"versionNonce": 1674255171,
			"isDeleted": false,
			"id": "2Y3MGJ5LKdVCutfII_2Xb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2497.2411664131378,
			"y": 1542.6726454300965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1557448241,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 347,
			"versionNonce": 1719234157,
			"isDeleted": false,
			"id": "QQUhBNZi34gKhwgAdOdY_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2497.883294755186,
			"y": 1602.3905812405292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1201592337,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 341,
			"versionNonce": 1793899235,
			"isDeleted": false,
			"id": "Zu8qamm-tL9rYeeu1aJyr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2498.525423097233,
			"y": 1660.182132024818,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1460383217,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 487,
			"versionNonce": 326834381,
			"isDeleted": false,
			"id": "apFJKPSM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2669.758713124779,
			"y": 1402.5157266118022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 100.68843078613281,
			"height": 35,
			"seed": 993673567,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Problem",
			"rawText": "Problem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1037,
			"versionNonce": 1207527043,
			"isDeleted": false,
			"id": "CQRKqBhj",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2594.901947278003,
			"y": 1473.2698030139888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 251.45968627929688,
			"height": 250,
			"seed": 1469151647,
			"groupIds": [
				"EMxtfSaFLCYYIek1qseEJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Shapley values require an\nexponentially large\nnumber of evaluations\nof the function f\nIncluding all possible\nsubsets of f multiplied\nby the dimensionality\nof our input which can be\nextremely large in\nNeural networks",
			"rawText": "Shapley values require an\nexponentially large\nnumber of evaluations\nof the function f\nIncluding all possible\nsubsets of f multiplied\nby the dimensionality\nof our input which can be\nextremely large in\nNeural networks",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Shapley values require an\nexponentially large\nnumber of evaluations\nof the function f\nIncluding all possible\nsubsets of f multiplied\nby the dimensionality\nof our input which can be\nextremely large in\nNeural networks",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 546,
			"versionNonce": 1536718637,
			"isDeleted": false,
			"id": "K6hR2yW0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1227.4087956410397,
			"y": 1846.8455790539576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d2bab0",
			"width": 299.2596435546875,
			"height": 100,
			"seed": 1672926833,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Can we exploit the structure\nof the neural network in order\nto detect the contribution of\nthe neurons to the output?",
			"rawText": "Can we exploit the structure\nof the neural network in order\nto detect the contribution of\nthe neurons to the output?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can we exploit the structure\nof the neural network in order\nto detect the contribution of\nthe neurons to the output?",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 618,
			"versionNonce": 565157411,
			"isDeleted": false,
			"id": "P1ppElHUQV7gvtGRK3ui7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1287.3054889135437,
			"y": 2054.934439152928,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 27.945046157500492,
			"height": 76.61338497112506,
			"seed": 1088049233,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-26.37509974415779,
					26.375099744157616
				],
				[
					-27.945046157500485,
					-23.86318548280948
				],
				[
					-0.9419678480056604,
					-50.23828522696745
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 564,
			"versionNonce": 1228605837,
			"isDeleted": false,
			"id": "xNWKtHJ2GgnNLtWyapOh6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1270.2743751390296,
			"y": 2059.3760454400044,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 230.2900133807268,
			"height": 95.3249645551368,
			"seed": 1737152927,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					75.81952626332672,
					27.685138220633764
				],
				[
					143.77395644124599,
					12.269549893235345
				],
				[
					192.8521560141878,
					-12.584153736651775
				],
				[
					230.2900133807268,
					-67.63982633450304
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 550,
			"versionNonce": 1123934659,
			"isDeleted": false,
			"id": "__qQ9KOU1RMQaYOn62dhe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1270.820041431217,
			"y": 2066.3257428184297,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 223.05412498215205,
			"height": 84.31383003556648,
			"seed": 1863643135,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					77.39254548040826,
					22.336872882556726
				],
				[
					137.4818795729203,
					22.966080569389238
				],
				[
					185.61626761561308,
					-12.269549893235522
				],
				[
					223.05412498215205,
					-61.347749466177255
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 670,
			"versionNonce": 1570525165,
			"isDeleted": false,
			"id": "Ba9qMDf0-KepzT_oy9QgL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1272.4704062130434,
			"y": 2075.0230786981247,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 222.11031345190312,
			"height": 88.08907615656224,
			"seed": 1191228927,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					71.41507245549862,
					20.134645978642943
				],
				[
					135.5942565124225,
					-24.224495943054606
				],
				[
					192.85215601418793,
					-67.95443017791929
				],
				[
					222.11031345190312,
					-65.12299558717264
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 608,
			"versionNonce": 352498019,
			"isDeleted": false,
			"id": "RUOBNg4ZdkW-t0FK3GNqj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1269.8762299009682,
			"y": 2062.86510054085,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 223.05412498215205,
			"height": 78.33635701065711,
			"seed": 1723203505,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					67.95443017791938,
					18.247022918145245
				],
				[
					135.5942565124225,
					-23.595288256221924
				],
				[
					188.44770220635974,
					-43.72993423486469
				],
				[
					223.05412498215205,
					-60.089334092511876
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 498,
			"versionNonce": 918932045,
			"isDeleted": false,
			"id": "eZhYRn8yDUi2Bm2s-oYLk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1280.5727605771222,
			"y": 2034.5507546333836,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 211.09917893233288,
			"height": 48.134388042692954,
			"seed": 129119025,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					58.20171103201425,
					-29.57276128113164
				],
				[
					125.21232967968479,
					-48.134388042692954
				],
				[
					177.75117153020574,
					-47.505180355860446
				],
				[
					211.09917893233288,
					-31.460384341629346
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 543,
			"versionNonce": 1493994755,
			"isDeleted": false,
			"id": "LhhSoJTIj7YfC4ywfOc2_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 30,
			"angle": 0,
			"x": 1279.9435528902898,
			"y": 2034.236150789968,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 210.78457508891654,
			"height": 54.1118610676025,
			"seed": 1771281937,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					56.62869181493281,
					-23.909892099638352
				],
				[
					123.95391430601958,
					-54.1118610676025
				],
				[
					178.0657753736221,
					-52.224238007104795
				],
				[
					210.78457508891654,
					-33.34800740212722
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 526,
			"versionNonce": 1972435117,
			"isDeleted": false,
			"id": "CXrRAl_Qbrtymb60M2LDd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1284.6626105415344,
			"y": 2025.7418470177274,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 205.75091359425582,
			"height": 61.6623533095935,
			"seed": 1793643793,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					52.2242380071047,
					-24.53909978647086
				],
				[
					117.66183743769369,
					-61.6623533095935
				],
				[
					173.03211387896133,
					-55.99948412810021
				],
				[
					205.75091359425582,
					-23.280684412805666
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 555,
			"versionNonce": 580514979,
			"isDeleted": false,
			"id": "Dclz-rjn5JVX221jMx9SS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1284.3480066981178,
			"y": 2023.5396201138137,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 206.6947251245048,
			"height": 61.34774946617724,
			"seed": 1104826847,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					49.39280341635806,
					-27.370534377217506
				],
				[
					112.6281759430331,
					-61.34774946617724
				],
				[
					173.0321138789614,
					-57.57250334518165
				],
				[
					206.6947251245048,
					-23.595288256222098
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 729,
			"versionNonce": 1671912205,
			"isDeleted": false,
			"id": "542-vGPHk9nur0QDUNqAE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1358.2722667002931,
			"y": 2008.3543322397347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 19.049094654955315,
			"height": 52.66274631042668,
			"seed": 1217833713,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-17.97892079793537,
					18.129797910146763
				],
				[
					-19.049094654955315,
					-16.403150490132933
				],
				[
					-0.6421043142120126,
					-34.53294840027992
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 739,
			"versionNonce": 291072067,
			"isDeleted": false,
			"id": "j0E_rQQpYbH3b4Cnr5J45",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1360.6673305663628,
			"y": 2049.0704179629224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 19.049094654955315,
			"height": 52.66274631042668,
			"seed": 1371294033,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-17.97892079793537,
					18.129797910146763
				],
				[
					-19.049094654955315,
					-16.403150490132933
				],
				[
					-0.6421043142120126,
					-34.53294840027992
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 759,
			"versionNonce": 1501720941,
			"isDeleted": false,
			"id": "N-FKdcAR9V4jaQurffLJq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1363.4045464132994,
			"y": 2089.4443517052423,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 19.049094654955315,
			"height": 52.66274631042667,
			"seed": 2101703633,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-17.978920797935377,
					18.129797910146756
				],
				[
					-19.04909465495532,
					-16.40315049013293
				],
				[
					-0.6421043142120126,
					-34.53294840027992
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 836,
			"versionNonce": 1261004771,
			"isDeleted": false,
			"id": "gxoxnkSFNQuSlhTibzmhG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1401.135607545892,
			"y": 1978.4633338402914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.313379681812739,
			"height": 32.90464905587508,
			"seed": 406648657,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-11.621616778340115,
					11.327830002842159
				],
				[
					-12.313379681812737,
					-10.248989050190614
				],
				[
					-0.41505774208358837,
					-21.57681905303292
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 859,
			"versionNonce": 1684782029,
			"isDeleted": false,
			"id": "IQM9x4Wk-5hqsRJkYUbuj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1402.0337028805066,
			"y": 2004.1416025197832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.313379681812739,
			"height": 32.90464905587508,
			"seed": 1305140575,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-11.621616778340115,
					11.327830002842159
				],
				[
					-12.313379681812737,
					-10.248989050190614
				],
				[
					-0.41505774208358837,
					-21.57681905303292
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 851,
			"versionNonce": 907572099,
			"isDeleted": false,
			"id": "GQTaICDcrAobnVTGMA4gB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1402.482750589896,
			"y": 2029.656481369375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.313379681812739,
			"height": 32.90464905587508,
			"seed": 641760369,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-11.621616778340115,
					11.327830002842159
				],
				[
					-12.313379681812737,
					-10.248989050190614
				],
				[
					-0.41505774208358837,
					-21.57681905303292
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 870,
			"versionNonce": 746371629,
			"isDeleted": false,
			"id": "PPI7UtvA-gjdqu0TEHP_Y",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1403.9129917120292,
			"y": 2056.3927422492684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.313379681812739,
			"height": 32.90464905587508,
			"seed": 1106710993,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-11.621616778340115,
					11.327830002842159
				],
				[
					-12.313379681812737,
					-10.248989050190614
				],
				[
					-0.41505774208358837,
					-21.57681905303292
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 862,
			"versionNonce": 1919224611,
			"isDeleted": false,
			"id": "u3qyqs681jwadUCSsmrt4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1405.4558935108391,
			"y": 2081.5376176540803,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.313379681812739,
			"height": 32.90464905587508,
			"seed": 625551505,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-11.621616778340115,
					11.327830002842159
				],
				[
					-12.313379681812737,
					-10.248989050190614
				],
				[
					-0.41505774208358837,
					-21.57681905303292
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 864,
			"versionNonce": 446622861,
			"isDeleted": false,
			"id": "jc7CfQuCAayIC_KhkpeP7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1407.0912153750853,
			"y": 2106.06744561777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.313379681812739,
			"height": 32.90464905587508,
			"seed": 1890228031,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
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
					-11.621616778340115,
					11.327830002842159
				],
				[
					-12.313379681812737,
					-10.248989050190614
				],
				[
					-0.41505774208358837,
					-21.57681905303292
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 743,
			"versionNonce": 343781059,
			"isDeleted": false,
			"id": "0EBl64M0ycIqk9JWe2BX5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1432.6021947376519,
			"y": 1970.631772254069,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 1020633585,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 747,
			"versionNonce": 1049350893,
			"isDeleted": false,
			"id": "4MvxiVKSGIila3qNIMPwd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1433.6245879004616,
			"y": 1984.887268750149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 1553904689,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 764,
			"versionNonce": 520150627,
			"isDeleted": false,
			"id": "rcj7ODRsu8L-LIR0tPMV9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.283185296697541,
			"x": 1432.7626733938175,
			"y": 1999.098615087406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 2032866335,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 743,
			"versionNonce": 1959587149,
			"isDeleted": false,
			"id": "sMrbSYcyjynzIH5t25Pzs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1433.1915213273955,
			"y": 2014.1207293126495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 1311403473,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 743,
			"versionNonce": 1019025923,
			"isDeleted": false,
			"id": "ZBjmeo02SxQcZaLZoa5lP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1432.7024003168412,
			"y": 2029.5607065077247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 312066111,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 720,
			"versionNonce": 1287371693,
			"isDeleted": false,
			"id": "Hgdsi1eY5NpHQ4Sxq-iUA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1432.7304275575095,
			"y": 2044.061361776718,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 913420063,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 752,
			"versionNonce": 984670627,
			"isDeleted": false,
			"id": "b_RdSxKvpLGyr4oR-hM1n",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1432.7304273505874,
			"y": 2060.3138746604263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 1615364529,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 561,
			"versionNonce": 780254733,
			"isDeleted": false,
			"id": "hcyiDbGvfFQfXUL77jY0i",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1487.5437716173687,
			"y": 2024.012744723198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 771187007,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 584,
			"versionNonce": 1107998019,
			"isDeleted": false,
			"id": "1SZNoTVpze9Gb6ajvxBz4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1487.5437716173687,
			"y": 2006.1965910505542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 1742300497,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 561,
			"versionNonce": 1092121709,
			"isDeleted": false,
			"id": "90u3C2ycnyIpRgGKMEtPO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1487.5437717646782,
			"y": 1988.3804370956125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.819021713851592,
			"height": 12.212989104313213,
			"seed": 675737777,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 185,
			"versionNonce": 1378424035,
			"isDeleted": false,
			"id": "hShlVKEwdssMLUKv4Dkyn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 384.805439,
			"y": 1601.8896776914341,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 697.6764470050682,
			"height": 715.2420635707981,
			"seed": 1220911153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 273243853,
			"isDeleted": false,
			"id": "lGc9O2fw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 499.8846903501697,
			"y": 1616.4321120021752,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 467.5179443359375,
			"height": 35,
			"seed": 2052503153,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Layer-Wise Relevance Propagation",
			"rawText": "Layer-Wise Relevance Propagation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Layer-Wise Relevance Propagation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 211,
			"versionNonce": 2056945795,
			"isDeleted": false,
			"id": "KSiwGKkt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 393.23402512026854,
			"y": 1651.4321118730193,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 680.8192749023438,
			"height": 100,
			"seed": 931424959,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Use the structure of the neural network to robustly Propagate\nthe output of the network backwards by means of propagation rules\n(Can be tuned for tuned for different explanations, e.g sensitive in\ntop-layers, robust in lower layers)",
			"rawText": "Use the structure of the neural network to robustly Propagate\nthe output of the network backwards by means of propagation rules\n(Can be tuned for tuned for different explanations, e.g sensitive in\ntop-layers, robust in lower layers)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Use the structure of the neural network to robustly Propagate\nthe output of the network backwards by means of propagation rules\n(Can be tuned for tuned for different explanations, e.g sensitive in\ntop-layers, robust in lower layers)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 1924005165,
			"isDeleted": false,
			"id": "vgrawXP1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 794.842767502455,
			"y": 1787.2596999997618,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 89.53990173339844,
			"height": 25,
			"seed": 74617105,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notation:",
			"rawText": "Notation:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notation:",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 238,
			"versionNonce": 1427994659,
			"isDeleted": false,
			"id": "mPb2_it7rsQT-YzpN5N08",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 783.8972502928152,
			"y": 1775.732361777071,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 292.0259016415009,
			"height": 334.404758624152,
			"seed": 2073182321,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 743,
			"versionNonce": 800051085,
			"isDeleted": false,
			"id": "3Pw4IH8S",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 787.7878411281101,
			"y": 1816.2771684924103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 290.0073547363281,
			"height": 283.7055112265001,
			"seed": 84274897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 15.130960598746675,
			"fontFamily": 1,
			"text": "* j, k indicating neurons from 2 layers\n  connected to each other j->k\n* Wjk is the weight connecting the two\n  neurons j and k\n* w0k is the bias for neuron k\n* Sum(0,j) is the sum over the input\n  neurons for neuron k\n\n* Numerator: contribution of aj to the\n  activation ak\n* Rk: relevance of Neuron k\n* Denominator: Normalization term to\n  implement conservation\n* Sum (k): pool all `relevance' coming \n  from the layer ahead into neuron j",
			"rawText": "* j, k indicating neurons from 2 layers\n  connected to each other j->k\n* Wjk is the weight connecting the two\n  neurons j and k\n* w0k is the bias for neuron k\n* Sum(0,j) is the sum over the input\n  neurons for neuron k\n\n* Numerator: contribution of aj to the\n  activation ak\n* Rk: relevance of Neuron k\n* Denominator: Normalization term to\n  implement conservation\n* Sum (k): pool all `relevance' coming \n  from the layer ahead into neuron j",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* j, k indicating neurons from 2 layers\n  connected to each other j->k\n* Wjk is the weight connecting the two\n  neurons j and k\n* w0k is the bias for neuron k\n* Sum(0,j) is the sum over the input\n  neurons for neuron k\n\n* Numerator: contribution of aj to the\n  activation ak\n* Rk: relevance of Neuron k\n* Denominator: Normalization term to\n  implement conservation\n* Sum (k): pool all `relevance' coming \n  from the layer ahead into neuron j",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1067482051,
			"isDeleted": false,
			"id": "vaHIHtSV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 400.20429900844374,
			"y": 1771.2963573130387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 106.771240234375,
			"height": 31.081343112499454,
			"seed": 582087057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 24.865074489999564,
			"fontFamily": 1,
			"text": "* LRP-0:",
			"rawText": "* LRP-0:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* LRP-0:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 191,
			"versionNonce": 1703433709,
			"isDeleted": false,
			"id": "9HxP7csK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 420.2153842664685,
			"y": 1806.6088529811034,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 257.8129871177669,
			"height": 60.6618793218275,
			"seed": 3094,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3AOIg37BUEhKjt2-LZA78",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9db0182084e56b7690fce3ee4f85d8b3a86118af",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 334,
			"versionNonce": 1447168867,
			"isDeleted": false,
			"id": "VjVEIa_QF5JgNmQlingfS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 420.21538451736933,
			"y": 1917.5849262155568,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 283.1113369324981,
			"height": 55.24123647463377,
			"seed": 1000577823,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PWsxrtLFwgjc0V3nYdC91",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f8832583255457590444ecd9e29d2f6031ac6c58",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 214,
			"versionNonce": 792793165,
			"isDeleted": false,
			"id": "rdCumLcn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 395.7340124664854,
			"y": 1876.8871581557194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.3841552734375,
			"height": 31.081343112499454,
			"seed": 1158173439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 24.865074489999564,
			"fontFamily": 1,
			"text": "* LRP-epsilon:",
			"rawText": "* LRP-epsilon:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* LRP-epsilon:",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 760260355,
			"isDeleted": false,
			"id": "Ae4thelO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 395.734012722289,
			"y": 2001.8562627525646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.75704956054688,
			"height": 31.081343112499454,
			"seed": 972927249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 24.865074489999564,
			"fontFamily": 1,
			"text": "* LRP-gamma:",
			"rawText": "* LRP-gamma:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* LRP-gamma:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 291,
			"versionNonce": 179535533,
			"isDeleted": false,
			"id": "nYEhRKKO8mNV0AMwbUvuG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 420.21538435762716,
			"y": 2033.4235469497846,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 355.1053557610194,
			"height": 74.91674172173404,
			"seed": 1150983665,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hGiUKEUI-_MjPB-BGtv7n",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "23952c6de906fb54e75d4515bf8c0de39e681edf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 196,
			"versionNonce": 1263193763,
			"isDeleted": false,
			"id": "7RZgyPzG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 419.8107033655325,
			"y": 2150.167378112668,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 363.9035171742695,
			"height": 68.66104097627726,
			"seed": 55704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0LfxLk09GNoFMl3-vEFDj",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8502505eb5c4d86f497900c43a14f58633f59120",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 2122916109,
			"isDeleted": false,
			"id": "hGiUKEUI-_MjPB-BGtv7n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 601.0533781650753,
			"y": 2119.6231747225183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.7186704290814987,
			"height": 30.90282845050524,
			"seed": 655853809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "nYEhRKKO8mNV0AMwbUvuG",
				"focus": -0.02476594187874808,
				"gap": 11.282886050999991
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.7186704290814987,
					30.90282845050524
				]
			]
		},
		{
			"type": "arrow",
			"version": 66,
			"versionNonce": 1658782275,
			"isDeleted": false,
			"id": "0LfxLk09GNoFMl3-vEFDj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 629.6832825130685,
			"y": 2223.801401857704,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6670542097178895,
			"height": 37.355035744201814,
			"seed": 46358065,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7RZgyPzG",
				"focus": -0.14909211278320647,
				"gap": 4.972982768759039
			},
			"endBinding": {
				"elementId": "dkbEoECD",
				"focus": -0.009376203010816684,
				"gap": 5
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.6670542097178895,
					37.355035744201814
				]
			]
		},
		{
			"type": "text",
			"version": 164,
			"versionNonce": 3897197,
			"isDeleted": false,
			"id": "dkbEoECD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 507.5662551138886,
			"y": 2266.156437601906,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 248.80052185058594,
			"height": 40,
			"seed": 861789073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0LfxLk09GNoFMl3-vEFDj",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sensitivity of neural network\noutput to neuron j's activation",
			"rawText": "Sensitivity of neural network\noutput to neuron j's activation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sensitivity of neural network\noutput to neuron j's activation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 269,
			"versionNonce": 1290519011,
			"isDeleted": false,
			"id": "bmkYn2o6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 792.0732541239317,
			"y": 2212.4737917461557,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 288.0006103515625,
			"height": 100,
			"seed": 1668770207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "LRP rules differ from layer to layer\nthus we need to combine different\nLRP in different layers in order\nto get the best results and\nexplanations",
			"rawText": "LRP rules differ from layer to layer\nthus we need to combine different\nLRP in different layers in order\nto get the best results and\nexplanations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LRP rules differ from layer to layer\nthus we need to combine different\nLRP in different layers in order\nto get the best results and\nexplanations",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 196,
			"versionNonce": 437518797,
			"isDeleted": false,
			"id": "3AOIg37BUEhKjt2-LZA78",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 413.06523430236564,
			"y": 1822.333703417698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 100.2184095432782,
			"height": 1.5428018364855234,
			"seed": 1997266975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9HxP7csK",
				"focus": 0.516800373441969,
				"gap": 7.150149964102951
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-100.2184095432782,
					1.5428018364855234
				]
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 1115655555,
			"isDeleted": false,
			"id": "uwKhOPRJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2.2662828803710795,
			"y": 1742.413917466565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 367.05670166015625,
			"height": 40,
			"seed": 130986463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This based off of and derived from the RELU\nactivation function",
			"rawText": "This based off of and derived from the RELU\nactivation function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This based off of and derived from the RELU\nactivation function",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 264,
			"versionNonce": 1361854509,
			"isDeleted": false,
			"id": "d8NYm42i",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 73.93549041166142,
			"y": 1784.3050635909683,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 217.5986913888825,
			"height": 49.811748631189964,
			"seed": 19886,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d9fb76c8fe000ea2110b342942071188105a106c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 1457055011,
			"isDeleted": false,
			"id": "9eMH5uXk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 106.13390179347076,
			"y": 1831.9759674913983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.25633239746094,
			"height": 20,
			"seed": 1269684159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which ensures that",
			"rawText": "Which ensures that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which ensures that",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 109,
			"versionNonce": 1265480333,
			"isDeleted": false,
			"id": "Dw9e40FB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 75.76206851633094,
			"y": 1856.0573107121613,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 211,
			"height": 17,
			"seed": 17188,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "848fccdc7a849beb8cab9504c9522212a95abbe9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 127,
			"versionNonce": 828786883,
			"isDeleted": false,
			"id": "UE84DH15T_LF-rWhAkb6C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 35.90766865487217,
			"y": 1799.997081648416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 108.6021404722976,
			"height": 0.7757295748021988,
			"seed": 1913141937,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "nFJ0pSYw",
				"focus": -0.16712884692470736,
				"gap": 4.970136258177263
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-108.6021404722976,
					-0.7757295748021988
				]
			]
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 898750701,
			"isDeleted": false,
			"id": "nFJ0pSYw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -407.9053002142746,
			"y": 1764.8886908842796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 330.2406921386719,
			"height": 80,
			"seed": 1668732881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UE84DH15T_LF-rWhAkb6C",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "that is equivalent to Gradient × Input\nthe issue is that the gradient becomes\nvery noisy the further we go back so this\nis not very robust",
			"rawText": "that is equivalent to Gradient × Input\nthe issue is that the gradient becomes\nvery noisy the further we go back so this\nis not very robust",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "that is equivalent to Gradient × Input\nthe issue is that the gradient becomes\nvery noisy the further we go back so this\nis not very robust",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 215,
			"versionNonce": 130431075,
			"isDeleted": false,
			"id": "PWsxrtLFwgjc0V3nYdC91",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 415.9628619448098,
			"y": 1940.8852727294056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 100.2184095432782,
			"height": 1.5428018364855234,
			"seed": 1705887121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "VjVEIa_QF5JgNmQlingfS",
				"focus": 0.2203002910312063,
				"gap": 4.252522572559542
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-100.2184095432782,
					1.5428018364855234
				]
			]
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 1763849037,
			"isDeleted": false,
			"id": "fwv9XkN9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -127.92375130149944,
			"y": 1889.6419294640514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 472.7689514160156,
			"height": 140,
			"seed": 1329555519,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The role of epsilon is to absorb some relevance when\nthe contributions to the activation\nof neuron k are weak or contradictory As epsilon\nbecomes larger, only the most salient\nexplanation factors survive the absorption.\nThis typically leads to explanations\nthat are sparser in terms of input features and less noisy",
			"rawText": "The role of epsilon is to absorb some relevance when\nthe contributions to the activation\nof neuron k are weak or contradictory As epsilon\nbecomes larger, only the most salient\nexplanation factors survive the absorption.\nThis typically leads to explanations\nthat are sparser in terms of input features and less noisy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The role of epsilon is to absorb some relevance when\nthe contributions to the activation\nof neuron k are weak or contradictory As epsilon\nbecomes larger, only the most salient\nexplanation factors survive the absorption.\nThis typically leads to explanations\nthat are sparser in terms of input features and less noisy",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 95,
			"versionNonce": 1472672771,
			"isDeleted": false,
			"id": "CJvuGJzDEZAnOP5Dl4B0P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 390.4525960726614,
			"y": 2139.1755907506117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 92.29504414487121,
			"height": 0.6236151631410394,
			"seed": 771082527,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-92.29504414487121,
					0.6236151631410394
				]
			]
		},
		{
			"type": "text",
			"version": 219,
			"versionNonce": 1383612845,
			"isDeleted": false,
			"id": "0P48E8VE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -159.47020914101847,
			"y": 2111.736523572407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 484.9610595703125,
			"height": 80,
			"seed": 1582224735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can enhance this further by focusing on the\npositive contributions over the negative contributions\nThe parameter γ controls by how much positive contributions \nare favored",
			"rawText": "We can enhance this further by focusing on the\npositive contributions over the negative contributions\nThe parameter γ controls by how much positive contributions \nare favored",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can enhance this further by focusing on the\npositive contributions over the negative contributions\nThe parameter γ controls by how much positive contributions \nare favored",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 496,
			"versionNonce": 1634188195,
			"isDeleted": false,
			"id": "ENa_OB5MdlUYbNgS8aDyX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 788.439772454176,
			"y": 2326.0585612312284,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 161.12684999126125,
			"height": 176.5948382986694,
			"seed": 1480897567,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
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
					-10.554005954599013,
					107.29932290016359
				],
				[
					41.588671661132175,
					105.77587515373762
				],
				[
					-31.600986662005866,
					176.5948382986694
				],
				[
					-119.53817833012909,
					111.51479133046587
				],
				[
					-66.26231500087385,
					108.16503799596741
				],
				[
					-103.75,
					2.4199508818902657
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 321,
			"versionNonce": 381518861,
			"isDeleted": false,
			"id": "79jwXmex4gO8C1FpS_vpF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 395.829841497605,
			"y": 2502.6534001992395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 721.0738717034164,
			"height": 1097.9324028756946,
			"seed": 176362897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 71,
			"versionNonce": 1624657731,
			"isDeleted": false,
			"id": "TogOaUWj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 524.7360456366358,
			"y": 2522.5555231089866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 449.45794677734375,
			"height": 35,
			"seed": 864028223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Which LRP Rule for Which Layer?",
			"rawText": "Which LRP Rule for Which Layer?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which LRP Rule for Which Layer?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 315,
			"versionNonce": 2045475437,
			"isDeleted": false,
			"id": "o7y4clPT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 417.87718306720734,
			"y": 2557.5555228390117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 676.9791870117188,
			"height": 150,
			"seed": 69238225,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "There are 2 general desirable properties of an explanation\nfidelity and understandability \nIn other words, an explanation should be\nan accurate representation of the output neuron of interest (as in\nit has accurately concluded the ground truth of the issue),\nand it should also be easy to interpret for a human.",
			"rawText": "There are 2 general desirable properties of an explanation\nfidelity and understandability \nIn other words, an explanation should be\nan accurate representation of the output neuron of interest (as in\nit has accurately concluded the ground truth of the issue),\nand it should also be easy to interpret for a human.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There are 2 general desirable properties of an explanation\nfidelity and understandability \nIn other words, an explanation should be\nan accurate representation of the output neuron of interest (as in\nit has accurately concluded the ground truth of the issue),\nand it should also be easy to interpret for a human.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 327,
			"versionNonce": 141651683,
			"isDeleted": false,
			"id": "hig0EtMP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 404.55164738636233,
			"y": 2715.045366189073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 706.939208984375,
			"height": 350,
			"seed": 496761713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Uniform LRP-0 picks many local artifacts of the function the\nexplanation is overly complex and does not focus sufficiently on the\nactual object. it is neither faithful not understandable.\n\n2. Uniform LRP-epsilon removes noise elements in the explanation to\nkeep only a limited number features that match the actual object, yet\nit is still too sparse to be understandable.\n\n3. Uniform LRP-γ is easier for a human to understand because\nfeatures are more densely highlighted, but it also picks unrelated\nconcepts and strays away from the truth\n\n4. Composite LRP overcomes the disadvantages of the approaches\nabove making it both faithful and understandable",
			"rawText": "1. Uniform LRP-0 picks many local artifacts of the function the\nexplanation is overly complex and does not focus sufficiently on the\nactual object. it is neither faithful not understandable.\n\n2. Uniform LRP-epsilon removes noise elements in the explanation to\nkeep only a limited number features that match the actual object, yet\nit is still too sparse to be understandable.\n\n3. Uniform LRP-γ is easier for a human to understand because\nfeatures are more densely highlighted, but it also picks unrelated\nconcepts and strays away from the truth\n\n4. Composite LRP overcomes the disadvantages of the approaches\nabove making it both faithful and understandable",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Uniform LRP-0 picks many local artifacts of the function the\nexplanation is overly complex and does not focus sufficiently on the\nactual object. it is neither faithful not understandable.\n\n2. Uniform LRP-epsilon removes noise elements in the explanation to\nkeep only a limited number features that match the actual object, yet\nit is still too sparse to be understandable.\n\n3. Uniform LRP-γ is easier for a human to understand because\nfeatures are more densely highlighted, but it also picks unrelated\nconcepts and strays away from the truth\n\n4. Composite LRP overcomes the disadvantages of the approaches\nabove making it both faithful and understandable",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 80454861,
			"isDeleted": false,
			"id": "uuCahoW3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 566.962445119325,
			"y": 3072.535209030933,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 382.11761474609375,
			"height": 35,
			"seed": 1467324177,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How to use Composite LRP?",
			"rawText": "How to use Composite LRP?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How to use Composite LRP?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 986159747,
			"isDeleted": false,
			"id": "6mhhiTlD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 514.2392391642275,
			"y": 3107.535209458129,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 482.720947265625,
			"height": 100,
			"seed": 703842943,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Od0uybpirvWcKZts4iTjG",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Upper layers have only have a few neurons per class,\nmaking it likely that the many concepts forming the different\nclasses are entangled. Here, a propagation rule close to the\nfunction and its gradient (e.g. LRP-0) will be insensitive to\nthese entanglements.",
			"rawText": "Upper layers have only have a few neurons per class,\nmaking it likely that the many concepts forming the different\nclasses are entangled. Here, a propagation rule close to the\nfunction and its gradient (e.g. LRP-0) will be insensitive to\nthese entanglements.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Upper layers have only have a few neurons per class,\nmaking it likely that the many concepts forming the different\nclasses are entangled. Here, a propagation rule close to the\nfunction and its gradient (e.g. LRP-0) will be insensitive to\nthese entanglements.",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 174,
			"versionNonce": 1794605869,
			"isDeleted": false,
			"id": "Od0uybpirvWcKZts4iTjG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 755.7308385652573,
			"y": 3214.35692045842,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 0.8828792762606099,
			"height": 76.81049703466624,
			"seed": 740892977,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6mhhiTlD",
				"focus": 0.0021575916871060755,
				"gap": 6.821711000291089
			},
			"endBinding": {
				"elementId": "IC1JvgiA",
				"focus": 0.002544556273166536,
				"gap": 9.93849623383312
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.8828792762606099,
					76.81049703466624
				]
			]
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 77025827,
			"isDeleted": false,
			"id": "IC1JvgiA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 434.1981678586605,
			"y": 3301.1059137269194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 644.3372192382812,
			"height": 80,
			"seed": 1915562719,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Od0uybpirvWcKZts4iTjG",
					"type": "arrow"
				},
				{
					"id": "T3Ll7z83whE6zsjDdu9nv",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Middle layers have a more disentangled representation, however, the stacking\nof many layers and the weight sharing in convolutions introduces spurious\nvariations. LRP-epsilon filters out these spurious variations and retains only the\nmost salient explanation factors",
			"rawText": "Middle layers have a more disentangled representation, however, the stacking\nof many layers and the weight sharing in convolutions introduces spurious\nvariations. LRP-epsilon filters out these spurious variations and retains only the\nmost salient explanation factors",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Middle layers have a more disentangled representation, however, the stacking\nof many layers and the weight sharing in convolutions introduces spurious\nvariations. LRP-epsilon filters out these spurious variations and retains only the\nmost salient explanation factors",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 154,
			"versionNonce": 819500429,
			"isDeleted": false,
			"id": "T3Ll7z83whE6zsjDdu9nv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 756.1816402810612,
			"y": 3385.419552697616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 0.9647501041399664,
			"height": 106.12251145539676,
			"seed": 1168443697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "IC1JvgiA",
				"focus": 0.0018230377502824328,
				"gap": 4.313638970696502
			},
			"endBinding": {
				"elementId": "eQkeJLMG",
				"focus": 0.006446422375712058,
				"gap": 4.313638960522894
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.9647501041399664,
					106.12251145539676
				]
			]
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1456412099,
			"isDeleted": false,
			"id": "eQkeJLMG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 453.5431028973374,
			"y": 3495.8557031135356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 604.1132202148438,
			"height": 80,
			"seed": 130830673,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "T3Ll7z83whE6zsjDdu9nv",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lower layers are similar to middle layers, however, LRP-γ is more suitable\nhere, as this rule tends to spread relevance uniformly to the whole feature\nrather than capturing the contribution of every individual pixel. This makes\nthe explanation more understandable for a human.",
			"rawText": "Lower layers are similar to middle layers, however, LRP-γ is more suitable\nhere, as this rule tends to spread relevance uniformly to the whole feature\nrather than capturing the contribution of every individual pixel. This makes\nthe explanation more understandable for a human.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lower layers are similar to middle layers, however, LRP-γ is more suitable\nhere, as this rule tends to spread relevance uniformly to the whole feature\nrather than capturing the contribution of every individual pixel. This makes\nthe explanation more understandable for a human.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 563,
			"versionNonce": 296246253,
			"isDeleted": false,
			"id": "FFXRU1gu",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 451.27962263777545,
			"y": 3634.2418983779544,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#f8f0fc",
			"width": 96.22804260253906,
			"height": 45,
			"seed": 860988095,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "PROS",
			"rawText": "PROS",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PROS",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 624,
			"versionNonce": 9266531,
			"isDeleted": false,
			"id": "Nt8BdTiC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 727.6700655543548,
			"y": 3738.6812148738272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 48.24000549316406,
			"height": 45,
			"seed": 1546905183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "v.s",
			"rawText": "v.s",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "v.s",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 573,
			"versionNonce": 628119117,
			"isDeleted": false,
			"id": "sL386jqb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 958.7114338968554,
			"y": 3634.897605732324,
			"strokeColor": "#e03131",
			"backgroundColor": "#f8f0fc",
			"width": 94.39204406738281,
			"height": 45,
			"seed": 705180241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "CONS",
			"rawText": "CONS",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CONS",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 591,
			"versionNonce": 1763754243,
			"isDeleted": false,
			"id": "MfVrWDfp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 285.523892939568,
			"y": 3706.7791716915067,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#f8f0fc",
			"width": 427.739501953125,
			"height": 125,
			"seed": 829216529,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ra00gpX3QzeDTCGTHV8Tc",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Good explanation quality on deep networks.\n\nPretty fast (One needs one pass)\n\nFlexible (Has tunable hyperparameters)",
			"rawText": "Good explanation quality on deep networks.\n\nPretty fast (One needs one pass)\n\nFlexible (Has tunable hyperparameters)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Good explanation quality on deep networks.\n\nPretty fast (One needs one pass)\n\nFlexible (Has tunable hyperparameters)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 637,
			"versionNonce": 1191838893,
			"isDeleted": false,
			"id": "G1G3ZCsA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 781.0777131991374,
			"y": 3687.978405943805,
			"strokeColor": "#e03131",
			"backgroundColor": "#f8f0fc",
			"width": 449.65948486328125,
			"height": 175,
			"seed": 378558527,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Need to choose HyperParameters correctly\n\nThe propagation strategy needs to be\nadapted to new architectures\n\nLRP assumes that the model has sufficiently\ndisentangled the function to explain",
			"rawText": "Need to choose HyperParameters correctly\n\nThe propagation strategy needs to be\nadapted to new architectures\n\nLRP assumes that the model has sufficiently\ndisentangled the function to explain",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Need to choose HyperParameters correctly\n\nThe propagation strategy needs to be\nadapted to new architectures\n\nLRP assumes that the model has sufficiently\ndisentangled the function to explain",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 129,
			"versionNonce": 168274083,
			"isDeleted": false,
			"id": "G6hGJ7OU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -836.1446880635841,
			"y": -43.718368100644966,
			"strokeColor": "#e03131",
			"backgroundColor": "#f8f0fc",
			"width": 159.8563690185547,
			"height": 20,
			"seed": 366147642,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "global interpretation",
			"rawText": "global interpretation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "global interpretation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 175,
			"versionNonce": 975103757,
			"isDeleted": false,
			"id": "2xppjxI9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -758.3706445028043,
			"y": 211.6238022836334,
			"strokeColor": "#e03131",
			"backgroundColor": "#f8f0fc",
			"width": 151.7443389892578,
			"height": 20,
			"seed": 1483984058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "local interpretation",
			"rawText": "local interpretation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "local interpretation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 686857283,
			"isDeleted": false,
			"id": "2egJm5Np",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 423.113277520773,
			"y": 1288.2015221398335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 677.7391357421875,
			"height": 175,
			"seed": 1832481786,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Explanation: Which pixels contribute how much to the classification\n\n2. Sensitivity: Which pixels lead to increase/decrease\nof prediction score when changed\n\n3. Deconvolution: Matching input pattern for the classified\nobject in the image",
			"rawText": "1. Explanation: Which pixels contribute how much to the classification\n\n2. Sensitivity: Which pixels lead to increase/decrease\nof prediction score when changed\n\n3. Deconvolution: Matching input pattern for the classified\nobject in the image",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Explanation: Which pixels contribute how much to the classification\n\n2. Sensitivity: Which pixels lead to increase/decrease\nof prediction score when changed\n\n3. Deconvolution: Matching input pattern for the classified\nobject in the image",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 229,
			"versionNonce": 287866221,
			"isDeleted": false,
			"id": "tEROPbyea4uawtiksTH7k",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1255.011233629541,
			"y": 2127.736878424685,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f0fc",
			"width": 278.78089517066513,
			"height": 169.19116396564505,
			"seed": 1493101882,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1c35a7aa0c07ca0f839c44071245156fff993786",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 152,
			"versionNonce": 1371151331,
			"isDeleted": false,
			"id": "SBFbmW0rK_xzdfrQtbNwn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 30,
			"angle": 0,
			"x": 1253.56601117216,
			"y": 2125.421900609028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 280.22611782783997,
			"height": 172.91868447090974,
			"seed": 291405114,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1399867341,
			"isDeleted": false,
			"id": "xG4Vd8In",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 244.15579320516724,
			"y": 3926.2594510238214,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#fdf8f6",
			"width": 550.529052734375,
			"height": 140,
			"seed": 53407418,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ot2-YpmtTeWOcEf9A8o4p",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "\nImage specific explanations: LRP takes into account the activations.\nLRP provides different explanations for different input images.\n\nFor NNs without pooling layers Sensitvity and\nDeconvolution provides the same explanations for\ndifferent samples.",
			"rawText": "\nImage specific explanations: LRP takes into account the activations.\nLRP provides different explanations for different input images.\n\nFor NNs without pooling layers Sensitvity and\nDeconvolution provides the same explanations for\ndifferent samples.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\nImage specific explanations: LRP takes into account the activations.\nLRP provides different explanations for different input images.\n\nFor NNs without pooling layers Sensitvity and\nDeconvolution provides the same explanations for\ndifferent samples.",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 75,
			"versionNonce": 275949443,
			"isDeleted": false,
			"id": "Ra00gpX3QzeDTCGTHV8Tc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 504.6098699488059,
			"y": 3848.7619958375208,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#fdf8f6",
			"width": 0,
			"height": 81.39227387432402,
			"seed": 1908584102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MfVrWDfp",
				"focus": -0.024389732577221997,
				"gap": 16.98282414601408
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					81.39227387432402
				]
			]
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1661978157,
			"isDeleted": false,
			"id": "cfHkUqsR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 216.6218972209523,
			"y": 4127.113830117985,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#fdf8f6",
			"width": 606.9453125,
			"height": 60,
			"seed": 1122468966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ot2-YpmtTeWOcEf9A8o4p",
					"type": "arrow"
				},
				{
					"id": "gjZn7-tqikfNS5lg7-mtu",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Unlike Deconvolution, and sensitivity\nLRP distinguishs between positive evidence, supporting the\nclassification decision, and negative evidence, speaking against the prediction",
			"rawText": "Unlike Deconvolution, and sensitivity\nLRP distinguishs between positive evidence, supporting the\nclassification decision, and negative evidence, speaking against the prediction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Unlike Deconvolution, and sensitivity\nLRP distinguishs between positive evidence, supporting the\nclassification decision, and negative evidence, speaking against the prediction",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 1800978211,
			"isDeleted": false,
			"id": "Ot2-YpmtTeWOcEf9A8o4p",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 502.48374955970047,
			"y": 4078.345450056057,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#fdf8f6",
			"width": 0.6773386119712654,
			"height": 48.091041449957174,
			"seed": 558390822,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xG4Vd8In",
				"focus": 0.06549387114918678,
				"gap": 12.085999032235577
			},
			"endBinding": {
				"elementId": "cfHkUqsR",
				"focus": -0.05429960911265614,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.6773386119712654,
					48.091041449957174
				]
			]
		},
		{
			"type": "arrow",
			"version": 67,
			"versionNonce": 586184845,
			"isDeleted": false,
			"id": "gjZn7-tqikfNS5lg7-mtu",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 509.2571356794128,
			"y": 4196.879707151021,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#fdf8f6",
			"width": 1.3546772239424172,
			"height": 79.24861760063413,
			"seed": 1874347558,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cfHkUqsR",
				"focus": 0.03788725861494644,
				"gap": 9.765877033035395
			},
			"endBinding": {
				"elementId": "nlVOTCkb",
				"focus": -0.00040827898018613027,
				"gap": 11.514756403510546
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					1.3546772239424172,
					79.24861760063413
				]
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 484106947,
			"isDeleted": false,
			"id": "nlVOTCkb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 172.0964635270451,
			"y": 4287.643081155165,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#fdf8f6",
			"width": 678.3853759765625,
			"height": 40,
			"seed": 568106490,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "gjZn7-tqikfNS5lg7-mtu",
					"type": "arrow"
				}
			],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "LRP explanations are normalized (conservation of relevance).\nThis allows to meaningfully aggregate relevance over datasets or regions in an image",
			"rawText": "LRP explanations are normalized (conservation of relevance).\nThis allows to meaningfully aggregate relevance over datasets or regions in an image",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LRP explanations are normalized (conservation of relevance).\nThis allows to meaningfully aggregate relevance over datasets or regions in an image",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 750,
			"versionNonce": 1556864749,
			"isDeleted": false,
			"id": "Z4EnC7gOzsKIwdDf8oolx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948966,
			"x": 1868.8185874924454,
			"y": 2416.6923509078565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 262.69350174635133,
			"height": 142.22407353997966,
			"seed": 1637116154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
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
					197.33305005157013,
					29.455127194990013
				],
				[
					199.1448216890222,
					-14.93327792258323
				],
				[
					262.69350174635133,
					47.18823703340193
				],
				[
					201.86247914520004,
					127.29079561739641
				],
				[
					200.95659332647398,
					65.6905599440295
				],
				[
					2.5675990254836023,
					111.77388967570926
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1031,
			"versionNonce": 228037219,
			"isDeleted": false,
			"id": "S7I5sZ2a_Ma4nvLlWyWoV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1704.0688441727734,
			"y": 2597.276700231335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 606.3139932825064,
			"height": 797.4134205165121,
			"seed": 1277341734,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1730902349,
			"isDeleted": false,
			"id": "1BQMR0UM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1885.8194170157499,
			"y": 2619.8215166851414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 248.52902221679688,
			"height": 35,
			"seed": 1387034618,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Taylor Expansions",
			"rawText": "Taylor Expansions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Taylor Expansions",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 337,
			"versionNonce": 240995843,
			"isDeleted": false,
			"id": "ZEcB39im",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1711.9342090728712,
			"y": 2670.4251733632373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 596.2994384765625,
			"height": 125,
			"seed": 1851972838,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Many ML models are highly non-linear and really complex\nwhen looked at from a global perspective, but when\nwe take a close look at each local region of the function\nwe typically dont find rapid change, thus making it somewhat\nlocally linear and easily approximated",
			"rawText": "Many ML models are highly non-linear and really complex\nwhen looked at from a global perspective, but when\nwe take a close look at each local region of the function\nwe typically dont find rapid change, thus making it somewhat\nlocally linear and easily approximated",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Many ML models are highly non-linear and really complex\nwhen looked at from a global perspective, but when\nwe take a close look at each local region of the function\nwe typically dont find rapid change, thus making it somewhat\nlocally linear and easily approximated",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 112,
			"versionNonce": 191416237,
			"isDeleted": false,
			"id": "2FnlaikEEndomf1b6XoAC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1783.37542661771,
			"y": 2811.028829370853,
			"strokeColor": "transparent",
			"backgroundColor": "#fdf8f6",
			"width": 453.41700274914865,
			"height": 229.2557879068729,
			"seed": 1992952678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4d8fa2b51d5d1f5c46471dfd2bce7b35f8509c27",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 96,
			"versionNonce": 1378522531,
			"isDeleted": false,
			"id": "erbNMe6R1ZNJaZh-rhnFa",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1779.5143740349195,
			"y": 2808.451653911153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 459.7116410724298,
			"height": 231.06346933062605,
			"seed": 1512335334,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 161,
			"versionNonce": 732776973,
			"isDeleted": false,
			"id": "i0AFRwmO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1832.9482166743414,
			"y": 3067.9103009161654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 365.799560546875,
			"height": 50,
			"seed": 1566544870,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Approximating the function at root x\nCan be done via a Taylor expansion",
			"rawText": "Approximating the function at root x\nCan be done via a Taylor expansion",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approximating the function at root x\nCan be done via a Taylor expansion",
			"lineHeight": 1.25
		},
		{
			"type": "freedraw",
			"version": 88,
			"versionNonce": 674097475,
			"isDeleted": false,
			"id": "RCyGXMf3c4hM6km-7R-nE",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2185.9861063487656,
			"y": 3073.3687169342343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 18.04423631373038,
			"height": 6.961949443880258,
			"seed": 1644169018,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.14208060089595165
				],
				[
					0,
					-0.28416120179144855
				],
				[
					0.2841612017909938,
					-0.8524836053734361
				],
				[
					0.4262418026864907,
					-1.2787254080599268
				],
				[
					0.5683224035819876,
					-1.7049672107464175
				],
				[
					0.8524836053729814,
					-2.1312090134329083
				],
				[
					1.13664480716443,
					-2.415370215223902
				],
				[
					1.2787254080599268,
					-2.699531417014896
				],
				[
					1.7049672107464175,
					-3.1257732197013866
				],
				[
					1.9891284125374114,
					-3.2678538205968835
				],
				[
					2.273289614328405,
					-3.4099344214923804
				],
				[
					2.557450816119399,
					-3.552015022388332
				],
				[
					3.1257732197013866,
					-3.836176224179326
				],
				[
					3.5520150223878773,
					-3.836176224179326
				],
				[
					4.120337425969865,
					-3.9782568250748227
				],
				[
					4.404498627760859,
					-3.9782568250748227
				],
				[
					4.972821031343301,
					-3.9782568250748227
				],
				[
					5.399062834029792,
					-3.836176224179326
				],
				[
					5.825304636716282,
					-3.552015022388332
				],
				[
					6.39362704029827,
					-3.4099344214923804
				],
				[
					6.819868842984761,
					-3.1257732197013866
				],
				[
					7.388191246566748,
					-2.699531417014896
				],
				[
					7.814433049253239,
					-2.415370215223902
				],
				[
					8.098594251044688,
					-2.273289614328405
				],
				[
					8.382755452835681,
					-1.9891284125374114
				],
				[
					8.666916654626675,
					-1.7049672107464175
				],
				[
					9.093158457313166,
					-1.2787254080599268
				],
				[
					9.519400259999657,
					-0.994564206268933
				],
				[
					9.80356146179065,
					-0.7104030044779392
				],
				[
					10.229803264477141,
					-0.28416120179144855
				],
				[
					10.513964466268135,
					0
				],
				[
					10.798125668059129,
					0.2841612017909938
				],
				[
					11.22436747074562,
					0.7104030044774845
				],
				[
					11.650609273432565,
					0.9945642062684783
				],
				[
					12.076851076119056,
					1.1366448071639752
				],
				[
					12.36101227791005,
					1.278725408059472
				],
				[
					12.78725408059654,
					1.420806008954969
				],
				[
					13.071415282387534,
					1.562886609850466
				],
				[
					13.497657085074025,
					1.8470478116414597
				],
				[
					13.781818286865018,
					1.9891284125369566
				],
				[
					14.065979488656012,
					1.9891284125369566
				],
				[
					14.918463094029448,
					1.8470478116414597
				],
				[
					15.628866098506933,
					1.420806008954969
				],
				[
					15.77094669940243,
					0.9945642062684783
				],
				[
					15.77094669940243,
					0.7104030044774845
				],
				[
					16.055107901193423,
					0.2841612017909938
				],
				[
					16.481349703879914,
					-0.42624180268694545
				],
				[
					16.62343030477541,
					-0.994564206268933
				],
				[
					16.907591506566405,
					-1.4208060089554237
				],
				[
					17.0496721074619,
					-1.7049672107464175
				],
				[
					17.1917527083574,
					-2.1312090134329083
				],
				[
					17.333833309252896,
					-2.557450816119399
				],
				[
					17.61799451104389,
					-3.1257732197013866
				],
				[
					17.902155712834883,
					-3.9782568250748227
				],
				[
					18.04423631373038,
					-4.404498627761313
				],
				[
					18.04423631373038,
					-4.830740430447804
				],
				[
					18.04423631373038,
					-4.972821031343301
				],
				[
					18.04423631373038,
					-4.972821031343301
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 197,
			"versionNonce": 686981229,
			"isDeleted": false,
			"id": "yzAwnGty",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1833.2404790737344,
			"y": 3124.2228067524275,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 363.39929151573006,
			"height": 58.574227908785446,
			"seed": 70374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c190d3954830e3f3049e4eab8be022d9841fd8dd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 58,
			"versionNonce": 1975896291,
			"isDeleted": false,
			"id": "_IADH-Gu-4O9dPLRQnzf7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1917.4426388436368,
			"y": 3169.2447512979193,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 5.7231130190693875,
			"height": 30.1417285670982,
			"seed": 1557246950,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					-5.7231130190693875,
					30.1417285670982
				]
			]
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 151120589,
			"isDeleted": false,
			"id": "Ek3JpLLg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1890.8666993163122,
			"y": 3201.9872153344368,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 40.95164489746094,
			"height": 37.404660174764544,
			"seed": 739552058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 9.974576046603877,
			"fontFamily": 1,
			"text": "value of\nfunction\nat root",
			"rawText": "value of\nfunction\nat root",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "value of\nfunction\nat root",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 67,
			"versionNonce": 1887483011,
			"isDeleted": false,
			"id": "JXdY4OCI5XgnPuyg5vDyQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2029.1286413041307,
			"y": 3163.9208275960646,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 30.48577595468305,
			"seed": 139872294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					0,
					30.48577595468305
				]
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1551173933,
			"isDeleted": false,
			"id": "lN6pqlas",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2000.1721484570342,
			"y": 3200.7272297225613,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 48.56317138671875,
			"height": 33.94269019065282,
			"seed": 244324794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 9.05138405084075,
			"fontFamily": 1,
			"text": "derivative\nof function\nat root",
			"rawText": "derivative\nof function\nat root",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "derivative\nof function\nat root",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 60,
			"versionNonce": 404565027,
			"isDeleted": false,
			"id": "z5RVc4h67mwm4npEO3ZlK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2119.8686567927753,
			"y": 3165.7141085345756,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 3.5865618770217225,
			"height": 35.86561877021495,
			"seed": 1579606694,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					3.5865618770217225,
					35.86561877021495
				]
			]
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 1689607053,
			"isDeleted": false,
			"id": "ev8jxf9r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2092.3049697335,
			"y": 3205.289624646713,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 70.49984741210938,
			"height": 48.3149200173097,
			"seed": 176195046,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 9.66298400346194,
			"fontFamily": 1,
			"text": "difference\nbetween\nreference point\nand root",
			"rawText": "difference\nbetween\nreference point\nand root",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "difference\nbetween\nreference point\nand root",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 84,
			"versionNonce": 1888071619,
			"isDeleted": false,
			"id": "jMbRqf8Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1999.15626306802,
			"y": 3122.6708983480125,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 137.97738647460938,
			"height": 16.776561972985117,
			"seed": 284531942,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 13.421249578388094,
			"fontFamily": 1,
			"text": "first order expansion",
			"rawText": "first order expansion",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "first order expansion",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 53,
			"versionNonce": 2046583277,
			"isDeleted": false,
			"id": "oKmZLAGJkIKy4kUqiGGAj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2190.8825819578014,
			"y": 3164.996796159171,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 27.257870265363636,
			"height": 24.38862076374653,
			"seed": 1357434854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					27.257870265363636,
					24.38862076374653
				]
			]
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 2078588771,
			"isDeleted": false,
			"id": "Z7tfJIin",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2212.231181025877,
			"y": 3191.4883257467277,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 53.75718688964844,
			"height": 47.052659033804936,
			"seed": 2017770598,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 9.410531806760988,
			"fontFamily": 1,
			"text": "higher order\nterms which\nare usually\ninsignificant",
			"rawText": "higher order\nterms which\nare usually\ninsignificant",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "higher order\nterms which\nare usually\ninsignificant",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 67,
			"versionNonce": 827563085,
			"isDeleted": false,
			"id": "RiQ52bGxQ1R9swOa_2l7x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2031.104717889846,
			"y": 3239.28356985929,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.268694512320735,
			"height": 26.655027408709884,
			"seed": 1360372326,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					19.268694512320735,
					26.655027408709884
				]
			]
		},
		{
			"type": "line",
			"version": 67,
			"versionNonce": 1954339587,
			"isDeleted": false,
			"id": "AiMQmQHG3v_9c1yGJd64t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2092.4433954207334,
			"y": 3254.3773805606074,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 28.260751951403563,
			"height": 12.203506524469958,
			"seed": 1087284858,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					-28.260751951403563,
					12.203506524469958
				]
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1117031085,
			"isDeleted": false,
			"id": "gy78iLtp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2020.5011162316791,
			"y": 3271.6032496057974,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 65.09312438964844,
			"height": 22.77413095481009,
			"seed": 535002810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 9.109652381924036,
			"fontFamily": 1,
			"text": "contribution of\nfeature i of x",
			"rawText": "contribution of\nfeature i of x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "contribution of\nfeature i of x",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 285,
			"versionNonce": 1188070051,
			"isDeleted": false,
			"id": "Rh2wWaY7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1730.8953904018447,
			"y": 3306.9662329408293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 569.9052124023438,
			"height": 80,
			"seed": 369246138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is quite limited!!\n\nThis is highly based on the gradient, and thus cannot deal with plateus\nsaturation and discontinuities ",
			"rawText": "This is quite limited!!\n\nThis is highly based on the gradient, and thus cannot deal with plateus\nsaturation and discontinuities ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is quite limited!!\n\nThis is highly based on the gradient, and thus cannot deal with plateus\nsaturation and discontinuities ",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 911,
			"versionNonce": 778611981,
			"isDeleted": false,
			"id": "GPeCUoEaSTSEOIngcUp63",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 238.16813501022614,
			"y": 3005.0220522577924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 673.6002900579151,
			"height": 144.89074020664611,
			"seed": 1899633411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					-506.00261852345943,
					29.455127194989984
				],
				[
					-505.31504114675704,
					-28.266611255916814
				],
				[
					-673.6002900579151,
					47.18823703340195
				],
				[
					-505.6170084150367,
					116.6241289507293
				],
				[
					-505.96079710338785,
					65.69055994402919
				],
				[
					-6.583853185634432,
					111.77388967570917
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "6KDWgTAj",
			"type": "text",
			"x": -172.92122471361654,
			"y": 2956.364817287262,
			"width": 318.1396179199219,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1242199053,
			"version": 204,
			"versionNonce": 1267611203,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"text": "Can we use this sort of method\nfor non-supervised models?",
			"rawText": "Can we use this sort of method\nfor non-supervised models?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can we use this sort of method\nfor non-supervised models?",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 746,
			"versionNonce": 608797549,
			"isDeleted": false,
			"id": "TRn-GEO6Y1_LoPxKhh3Qk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1286.5500572799538,
			"y": 2823.015337271608,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 821.5736982092433,
			"height": 437.0416247684262,
			"seed": 1169779811,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"id": "iBQsMRYb",
			"type": "text",
			"x": -1042.7954466428487,
			"y": 2843.231500052601,
			"width": 378.30963134765625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 943513101,
			"version": 236,
			"versionNonce": 1100248547,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"text": "Beyond first order methods",
			"rawText": "Beyond first order methods",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Beyond first order methods",
			"lineHeight": 1.25
		},
		{
			"id": "7ZzNgt8k",
			"type": "text",
			"x": -1253.810186633083,
			"y": 2886.981500052601,
			"width": 777.839111328125,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1344476909,
			"version": 601,
			"versionNonce": 679513549,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"text": "First order explanations are quite a natural way of describing\ninput feature's contribution to the result given.\nBut this is not a faithful explanation for all models, as some models\nuse a conjunction of features to make their decisions and thus we have\nto go to a higher order to give those relations a contribution to our decision.",
			"rawText": "First order explanations are quite a natural way of describing\ninput feature's contribution to the result given.\nBut this is not a faithful explanation for all models, as some models\nuse a conjunction of features to make their decisions and thus we have\nto go to a higher order to give those relations a contribution to our decision.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "First order explanations are quite a natural way of describing\ninput feature's contribution to the result given.\nBut this is not a faithful explanation for all models, as some models\nuse a conjunction of features to make their decisions and thus we have\nto go to a higher order to give those relations a contribution to our decision.",
			"lineHeight": 1.25
		},
		{
			"id": "UgahNJFV",
			"type": "text",
			"x": -1249.7904417600362,
			"y": 3021.981500052601,
			"width": 739.7996215820312,
			"height": 75,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 926692941,
			"version": 389,
			"versionNonce": 133284227,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"text": "for example:\nsimilarity methods                                         Graph neural\nin representation learning                                      networks   ",
			"rawText": "for example:\nsimilarity methods                                         Graph neural\nin representation learning                                      networks   ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for example:\nsimilarity methods                                         Graph neural\nin representation learning                                      networks   ",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 700,
			"versionNonce": 2049395757,
			"isDeleted": false,
			"id": "oPxzpJo4vMHxK5hecK3yZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1179.5736955265988,
			"y": 3170.3564993746218,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 46.31780551574707,
			"height": 37.24201929982365,
			"seed": 1092454605,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "00ce334e0731ae23b97d07760b1513042e4daa00",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 736,
			"versionNonce": 400857379,
			"isDeleted": false,
			"id": "vT4wdwhsIXdQMGvhtJ67j",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1178.9222566498108,
			"y": 3123.318641847642,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 44.47046295011243,
			"height": 32.84419812655362,
			"seed": 191686445,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "da4dc7fe07f90efe656d5a0b241750dcefc623ff",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 756,
			"versionNonce": 958873229,
			"isDeleted": false,
			"id": "HiUAc0aIOXz7YKlDMaWaS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1276.0179863166325,
			"y": 3141.75043535588,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 54.17140495036872,
			"height": 44.213426099198,
			"seed": 1694595469,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "K3jmEeGPwwZv-aYiiwzc7",
					"type": "arrow"
				},
				{
					"id": "nml3vollG96S5zLUOU2WD",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9444c80b3a42b4f0aa8c0fd6c19faf384cd6adf5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1625,
			"versionNonce": 1054571715,
			"isDeleted": false,
			"id": "K3jmEeGPwwZv-aYiiwzc7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1219.2820221271536,
			"y": 3164.1228319463285,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 42.029360478195144,
			"height": 26.72740884778434,
			"seed": 387235821,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HiUAc0aIOXz7YKlDMaWaS",
				"focus": 0.18052184828755297,
				"gap": 2.564559239110281
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
					23.054940456485667,
					-3.468442369559819
				],
				[
					22.23883636953037,
					-24.687148630396212
				],
				[
					42.029360478195144,
					-26.72740884778434
				]
			]
		},
		{
			"type": "arrow",
			"version": 1679,
			"versionNonce": 1278862573,
			"isDeleted": false,
			"id": "nml3vollG96S5zLUOU2WD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1219.2820221271536,
			"y": 3164.071583899025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 42.02936047819528,
			"height": 26.727408847784424,
			"seed": 128989773,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HiUAc0aIOXz7YKlDMaWaS",
				"focus": -0.16218378293662947,
				"gap": 2.564559239110281
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
					23.05494045648574,
					3.4684423695598308
				],
				[
					22.238836369530443,
					24.68714863039629
				],
				[
					42.02936047819528,
					26.727408847784424
				]
			]
		},
		{
			"type": "arrow",
			"version": 1708,
			"versionNonce": 1019470765,
			"isDeleted": false,
			"id": "VTvB-LFl5OggvXUQY9dv4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1135.749035637641,
			"y": 3139.1447925915536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 25.890117862484658,
			"height": 0.12015808799287697,
			"seed": 531458221,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566735000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "gKqvHlwfSTFYTpVFrWVR8",
				"gap": 1.2945058931242102,
				"focus": -0.17607399365240017
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
					25.890117862484658,
					0.12015808799287697
				]
			]
		},
		{
			"type": "arrow",
			"version": 1688,
			"versionNonce": 1415743181,
			"isDeleted": false,
			"id": "X8-oyGPMTMJFOdbmpaatl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1133.321837088033,
			"y": 3189.6305224233984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 24.271985496079196,
			"height": 0,
			"seed": 1890962189,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566735001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "hnAQd3ccg6Jesqt3e93QG",
				"gap": 1.4563191297642106,
				"focus": -0.12120915032237463
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
					24.271985496079196,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 800,
			"versionNonce": 1216309251,
			"isDeleted": false,
			"id": "gKqvHlwfSTFYTpVFrWVR8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1108.5644118820323,
			"y": 3115.849717601638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 52.4274886715309,
			"height": 40,
			"seed": 457367917,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "VTvB-LFl5OggvXUQY9dv4",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "TK1KsQCd"
				},
				{
					"id": "S47WP6JNJGMJGqBpASOFb",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 785,
			"versionNonce": 260918701,
			"isDeleted": false,
			"id": "TK1KsQCd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1102.1620078782983,
			"y": 3120.912749324882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 39.6226806640625,
			"height": 29.873936553512166,
			"seed": 1956522957,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 7.966383080936577,
			"fontFamily": 1,
			"text": "Self-\nsupervised\nlearning",
			"rawText": "Self-supervised learning",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gKqvHlwfSTFYTpVFrWVR8",
			"originalText": "Self-supervised learning",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 808,
			"versionNonce": 1962504099,
			"isDeleted": false,
			"id": "hnAQd3ccg6Jesqt3e93QG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1107.5935324621896,
			"y": 3167.206339416951,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 52.4274886715309,
			"height": 40,
			"seed": 1826695725,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "KNgX4HE1"
				},
				{
					"id": "X8-oyGPMTMJFOdbmpaatl",
					"type": "arrow"
				},
				{
					"id": "SPJk8xC1d1_theTCpeuuU",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 791,
			"versionNonce": 89198605,
			"isDeleted": false,
			"id": "KNgX4HE1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1101.1911284584555,
			"y": 3172.269371140195,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 39.6226806640625,
			"height": 29.873936553512166,
			"seed": 888495245,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 7.966383080936577,
			"fontFamily": 1,
			"text": "Self-\nsupervised\nlearning",
			"rawText": "Self-supervised learning",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hnAQd3ccg6Jesqt3e93QG",
			"originalText": "Self-supervised learning",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 2340,
			"versionNonce": 456563821,
			"isDeleted": false,
			"id": "S47WP6JNJGMJGqBpASOFb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1055.136923210501,
			"y": 3136.059848048526,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 28.338191008918784,
			"height": 0.2968253327107959,
			"seed": 613696237,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566735000,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gKqvHlwfSTFYTpVFrWVR8",
				"gap": 1.000000000000341,
				"focus": -0.003695120482389068
			},
			"endBinding": {
				"elementId": "rPX3n3VfsgN_o3E_dyLsX",
				"gap": 2.807783138015111,
				"focus": -0.4502667916618462
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
					28.338191008918784,
					0.2968253327107959
				]
			]
		},
		{
			"type": "arrow",
			"version": 2190,
			"versionNonce": 1302263693,
			"isDeleted": false,
			"id": "SPJk8xC1d1_theTCpeuuU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1054.1660437906583,
			"y": 3188.9254865708904,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 27.822765581385283,
			"height": 0.38751651231496,
			"seed": 1615289677,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566735001,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hnAQd3ccg6Jesqt3e93QG",
				"gap": 1.000000000000341,
				"focus": 0.10302824818335315
			},
			"endBinding": {
				"elementId": "3PNU4mlLFiYcbERMSnKi-",
				"gap": 3.9325517143490742,
				"focus": 1.5266844113692823
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
					27.822765581385283,
					-0.38751651231496
				]
			]
		},
		{
			"type": "rectangle",
			"version": 762,
			"versionNonce": 36053731,
			"isDeleted": false,
			"id": "nBYOcr4W_YsklJokLmTkt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.2331690342141,
			"y": 3104.8941797377875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.8251179857995,
			"height": 54.514988634403494,
			"seed": 1063791533,
			"groupIds": [
				"bXv4GiQRofsa6SMXg4QHw",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "S47WP6JNJGMJGqBpASOFb",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 828,
			"versionNonce": 887894221,
			"isDeleted": false,
			"id": "DXLbe9HNRjdZnZxuuoPAC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.2398363560621,
			"y": 3112.13909782573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 7.715506067341811,
			"height": 41.19084690790542,
			"seed": 1914711565,
			"groupIds": [
				"bXv4GiQRofsa6SMXg4QHw",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 841,
			"versionNonce": 63295107,
			"isDeleted": false,
			"id": "VV2PlBcEy9t4iPfELHFKI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.1153927098146,
			"y": 3119.730160246824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.591062421094274,
			"height": 27.0042712356963,
			"seed": 1734927469,
			"groupIds": [
				"bXv4GiQRofsa6SMXg4QHw",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 807,
			"versionNonce": 1596362541,
			"isDeleted": false,
			"id": "rPX3n3VfsgN_o3E_dyLsX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1023.9909490635671,
			"y": 3125.5790116204544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 7.4738515276242365,
			"height": 14.93323754969379,
			"seed": 1930153677,
			"groupIds": [
				"bXv4GiQRofsa6SMXg4QHw",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "S47WP6JNJGMJGqBpASOFb",
					"type": "arrow"
				},
				{
					"id": "ypGP9vHRGK4U2RhsjI_BM",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 759,
			"versionNonce": 2007959075,
			"isDeleted": false,
			"id": "Yz2-Yn_uVTUgQ25tl3sGx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1023.8657767176012,
			"y": 3133.0523581470975,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 7.18439210805203,
			"height": 0,
			"seed": 866282797,
			"groupIds": [
				"bXv4GiQRofsa6SMXg4QHw",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					7.18439210805203,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 769,
			"versionNonce": 1665540493,
			"isDeleted": false,
			"id": "GJTacyWVhG50ZmEL1MBTI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.6173176336756,
			"y": 3171.785689890258,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.8251179857995,
			"height": 54.514988634403494,
			"seed": 949370765,
			"groupIds": [
				"WcX0Y8SCyppI9ScbAkoXY",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SPJk8xC1d1_theTCpeuuU",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 834,
			"versionNonce": 1959807427,
			"isDeleted": false,
			"id": "BzPkribUiq_zGPVkD3yb3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.6239849555234,
			"y": 3179.0306079782004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 7.715506067341811,
			"height": 41.19084690790542,
			"seed": 1746978285,
			"groupIds": [
				"WcX0Y8SCyppI9ScbAkoXY",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 847,
			"versionNonce": 914647021,
			"isDeleted": false,
			"id": "LJ2k4mVGkmi14bPMo22NT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.499541309276,
			"y": 3186.6216703992945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.591062421094274,
			"height": 27.0042712356963,
			"seed": 625705037,
			"groupIds": [
				"WcX0Y8SCyppI9ScbAkoXY",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 813,
			"versionNonce": 810031459,
			"isDeleted": false,
			"id": "3PNU4mlLFiYcbERMSnKi-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.3750976630288,
			"y": 3192.4705217729243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 7.4738515276242365,
			"height": 14.93323754969379,
			"seed": 904916653,
			"groupIds": [
				"WcX0Y8SCyppI9ScbAkoXY",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6PWTmh4iiNjmczkUAKe-t",
					"type": "arrow"
				},
				{
					"id": "SPJk8xC1d1_theTCpeuuU",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 765,
			"versionNonce": 1793778253,
			"isDeleted": false,
			"id": "tFSnbnXH2l05tpU0bwy5v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.2499253170627,
			"y": 3199.943868299568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 7.18439210805203,
			"height": 0,
			"seed": 1756860685,
			"groupIds": [
				"WcX0Y8SCyppI9ScbAkoXY",
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
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
					7.18439210805203,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 1964,
			"versionNonce": 929363203,
			"isDeleted": false,
			"id": "ypGP9vHRGK4U2RhsjI_BM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1014.9542414027774,
			"y": 3134.0750231601282,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.04440533639342,
			"height": 28.666221605366193,
			"seed": 2065426285,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rPX3n3VfsgN_o3E_dyLsX",
				"focus": -0.3650502086331022,
				"gap": 1.5628561331654964
			},
			"endBinding": {
				"elementId": "uOoNCjnR",
				"focus": -0.6402414045827592,
				"gap": 3.0399878672067757
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
					30.04440533639342,
					28.666221605366193
				]
			]
		},
		{
			"type": "arrow",
			"version": 2012,
			"versionNonce": 357765293,
			"isDeleted": false,
			"id": "6PWTmh4iiNjmczkUAKe-t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1013.9895127910584,
			"y": 3198.298385025997,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.044405336393464,
			"height": 28.66622160536624,
			"seed": 1063678413,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3PNU4mlLFiYcbERMSnKi-",
				"focus": 0.4264743944491804,
				"gap": 2.911733344346203
			},
			"endBinding": {
				"elementId": "uOoNCjnR",
				"focus": 0.6208739350865838,
				"gap": 2.075259255487765
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
					30.044405336393464,
					-28.66622160536624
				]
			]
		},
		{
			"type": "text",
			"version": 631,
			"versionNonce": 1772444835,
			"isDeleted": false,
			"id": "uOoNCjnR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -981.8698481991771,
			"y": 3156.4015996027697,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 41.26103210449219,
			"height": 19.915957702341444,
			"seed": 45133869,
			"groupIds": [
				"yI_gFu5nV3DE8e6lLfRGl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ypGP9vHRGK4U2RhsjI_BM",
					"type": "arrow"
				},
				{
					"id": "6PWTmh4iiNjmczkUAKe-t",
					"type": "arrow"
				}
			],
			"updated": 1716566531072,
			"link": null,
			"locked": false,
			"fontSize": 7.966383080936577,
			"fontFamily": 1,
			"text": "How similar\nare they?",
			"rawText": "How similar\nare they?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How similar\nare they?",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 578,
			"versionNonce": 1936093965,
			"isDeleted": false,
			"id": "DaW-bv8Hubg2c9ApUOAm8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -568.0930149676822,
			"y": 3138.357379457704,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.225679022010546,
			"height": 37.3219956137652,
			"seed": 895026755,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531072,
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
					33.225679022010546,
					37.3219956137652
				]
			]
		},
		{
			"type": "ellipse",
			"version": 537,
			"versionNonce": 850907203,
			"isDeleted": false,
			"id": "W6wtvTEAkQkOggZqqL6PR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -537.7349739140849,
			"y": 3172.4933510556602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 22.75731439863733,
			"height": 22.757314398637405,
			"seed": 1233470947,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 544,
			"versionNonce": 1369344365,
			"isDeleted": false,
			"id": "9Oo-v7OHqH_9jHYPMw1Nq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -578.8574893253581,
			"y": 3210.7256392453714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 22.75731439863733,
			"height": 26.83747228407095,
			"seed": 2034798979,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 604,
			"versionNonce": 75157475,
			"isDeleted": false,
			"id": "EvetdIQV_sIf3M5HTcuMP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -634.9883811431299,
			"y": 3200.257274621998,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 22.75731439863733,
			"height": 26.83747228407095,
			"seed": 1440835875,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531072,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 537,
			"versionNonce": 826594253,
			"isDeleted": false,
			"id": "ClDYBI4uvOn3-BoH0GBRv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -641.8267136192675,
			"y": 3148.3705977931054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 22.75731439863733,
			"height": 22.757314398637405,
			"seed": 1153322179,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 571,
			"versionNonce": 285006723,
			"isDeleted": false,
			"id": "F5xeTlAvdsn00f2iyo9Od",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -586.7540127745649,
			"y": 3117.875796498931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 22.75731439863733,
			"height": 22.757314398637405,
			"seed": 2038283363,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 543,
			"versionNonce": 779276845,
			"isDeleted": false,
			"id": "Dtm79-VZdhZaVG9yZzvzE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -584.9334276226738,
			"y": 3131.530185138113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.59772705362911,
			"height": 19.571290382828163,
			"seed": 804141059,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
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
					-39.59772705362911,
					19.571290382828163
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 1149006627,
			"isDeleted": false,
			"id": "fa48_eoMEv7FcYzIvcI8n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -630.4480564199487,
			"y": 3170.2176196157966,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.461755455672997,
			"height": 31.405093870119572,
			"seed": 638468003,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
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
					5.461755455672997,
					31.405093870119572
				]
			]
		},
		{
			"type": "line",
			"version": 518,
			"versionNonce": 638715021,
			"isDeleted": false,
			"id": "go_t83g3M6xXC6_dPVhOU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -534.412189657699,
			"y": 3191.154348862543,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.21246068661011,
			"height": 23.21246068661011,
			"seed": 1443648323,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
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
					-23.21246068661011,
					23.21246068661011
				]
			]
		},
		{
			"type": "line",
			"version": 559,
			"versionNonce": 2137528003,
			"isDeleted": false,
			"id": "LpDIS2SeNnuNnXjnXE1In",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -578.1062333030826,
			"y": 3223.0145890206354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.59111788592882,
			"height": 8.192633183509459,
			"seed": 1883697891,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
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
					-34.59111788592882,
					-8.192633183509459
				]
			]
		},
		{
			"type": "line",
			"version": 526,
			"versionNonce": 467397357,
			"isDeleted": false,
			"id": "6BypNBdUwpP7DO47e8Z3l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -568.0930149676822,
			"y": 3210.7256392453714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.102925759454948,
			"height": 71.45796721172145,
			"seed": 357342851,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
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
					-9.102925759454948,
					-71.45796721172145
				]
			]
		},
		{
			"type": "line",
			"version": 541,
			"versionNonce": 274613859,
			"isDeleted": false,
			"id": "yWVaFasp7DW5KOqg70txp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -616.7936677807662,
			"y": 3202.988152349835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.687434477683475,
			"height": 63.265334028211996,
			"seed": 1339807267,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
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
					38.687434477683475,
					-63.265334028211996
				]
			]
		},
		{
			"type": "line",
			"version": 648,
			"versionNonce": 1393721027,
			"isDeleted": false,
			"id": "4UZLRjAp5CqtiH9mgFhT-",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1361.4276522136918,
			"y": 3122.61665617337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 147.56793348736585,
			"height": 100.88828105768889,
			"seed": 1976196749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566536784,
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
					-109.1701548758574,
					16.563747636336963
				],
				[
					-109.923052495691,
					-18.069542876003965
				],
				[
					-144.55634300803183,
					32.37459765284036
				],
				[
					-106.15856439652327,
					82.81873818168492
				],
				[
					-106.15856439652339,
					47.555580012944056
				],
				[
					3.011590479334025,
					63.24340006601395
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "SNQ0wo5U",
			"type": "text",
			"x": -2220.1700629918723,
			"y": 2823.747919007172,
			"width": 355.6575012207031,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 998690189,
			"version": 138,
			"versionNonce": 1848476163,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Similarity Models\nSecond-order explanations",
			"rawText": "Similarity Models\nSecond-order explanations",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Similarity Models\nSecond-order explanations",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 987,
			"versionNonce": 1994773421,
			"isDeleted": false,
			"id": "Wjv_fS0KHPHIDmgCOsLc_",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2239.745966945728,
			"y": 3029.341607081166,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 65.6518562841388,
			"height": 52.78764120143593,
			"seed": 1958258499,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Y5NFTAtDQ4yjv7i7AduSw",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "00ce334e0731ae23b97d07760b1513042e4daa00",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 1054,
			"versionNonce": 835996067,
			"isDeleted": false,
			"id": "GBWpbeDd7rkXMbCJCPFhh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2238.266528386502,
			"y": 2952.1037076311277,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 63.03339309754884,
			"height": 46.55407464067332,
			"seed": 508085987,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "X9icIjZQP_Z5nF-1hRX_M",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "da4dc7fe07f90efe656d5a0b241750dcefc623ff",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 3227,
			"versionNonce": 1000920589,
			"isDeleted": false,
			"id": "X9icIjZQP_Z5nF-1hRX_M",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2171.8012370769393,
			"y": 2977.9484187145786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 40.167162989563614,
			"height": 0.42072662699996355,
			"seed": 1281496867,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GBWpbeDd7rkXMbCJCPFhh",
				"focus": 0.093260217702274,
				"gap": 3.4318982120137207
			},
			"endBinding": {
				"elementId": "9gQs2chtQRb4ePChqmI-3",
				"focus": -0.4502667916619049,
				"gap": 3.9798123637642675
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
					40.167162989563614,
					0.42072662699996355
				]
			]
		},
		{
			"type": "arrow",
			"version": 3075,
			"versionNonce": 1350638915,
			"isDeleted": false,
			"id": "Y5NFTAtDQ4yjv7i7AduSw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2170.425091652281,
			"y": 3052.8813146925536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 39.436587874513606,
			"height": 0.5492742605336332,
			"seed": 1123629763,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Wjv_fS0KHPHIDmgCOsLc_",
				"focus": -0.08736390246473824,
				"gap": 3.6690190093083856
			},
			"endBinding": {
				"elementId": "1245LNR7kFubY3adBz5H4",
				"focus": 1.5266844113692812,
				"gap": 5.574083597130084
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
					39.436587874513606,
					-0.5492742605336332
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1015,
			"versionNonce": 1234996333,
			"isDeleted": false,
			"id": "FF1M2osmVX8agQb4371UX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2127.997589532971,
			"y": 2933.7735284288096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 11.091490965293684,
			"height": 77.27072039154643,
			"seed": 237693539,
			"groupIds": [
				"I1tZNgpI3snLXHMLVObvx",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "X9icIjZQP_Z5nF-1hRX_M",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1081,
			"versionNonce": 361921763,
			"isDeleted": false,
			"id": "vg3BKlPoyM7lD7cSk5_eu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.007039938725,
			"y": 2944.04263154809,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 10.93612466852113,
			"height": 58.38479460129821,
			"seed": 1388684803,
			"groupIds": [
				"I1tZNgpI3snLXHMLVObvx",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1094,
			"versionNonce": 545945293,
			"isDeleted": false,
			"id": "qssZcI-NPgUP6hsnj-hxX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2127.830650831168,
			"y": 2954.8023671090536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.759735560964213,
			"height": 38.2764363398239,
			"seed": 398978467,
			"groupIds": [
				"I1tZNgpI3snLXHMLVObvx",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1061,
			"versionNonce": 1553393795,
			"isDeleted": false,
			"id": "9gQs2chtQRb4ePChqmI-3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2127.6542617236114,
			"y": 2963.092655164223,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 10.593598313153233,
			"height": 21.166692906815037,
			"seed": 6308163,
			"groupIds": [
				"I1tZNgpI3snLXHMLVObvx",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "X9icIjZQP_Z5nF-1hRX_M",
					"type": "arrow"
				},
				{
					"id": "HkjIz1uo6JI_ENnwFz5Iy",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1012,
			"versionNonce": 185341229,
			"isDeleted": false,
			"id": "1dRIJfSh28gUFX7zn3J3q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2127.47683974136,
			"y": 2973.685537678097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 10.18331229026763,
			"height": 0,
			"seed": 1173168355,
			"groupIds": [
				"I1tZNgpI3snLXHMLVObvx",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					10.18331229026763,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1022,
			"versionNonce": 189587491,
			"isDeleted": false,
			"id": "LtfXlz3RW8ILb1TVkOxhK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.5420900412037,
			"y": 3028.586997293736,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 11.091490965293684,
			"height": 77.27072039154643,
			"seed": 1912409219,
			"groupIds": [
				"-N1ULQP4YA5d86Al2koCo",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Y5NFTAtDQ4yjv7i7AduSw",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1087,
			"versionNonce": 1149953933,
			"isDeleted": false,
			"id": "EJ4dCVmnbk2SpWuSxjH--",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.551540446958,
			"y": 3038.856100413017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 10.93612466852113,
			"height": 58.38479460129821,
			"seed": 1481540643,
			"groupIds": [
				"-N1ULQP4YA5d86Al2koCo",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1100,
			"versionNonce": 1268966339,
			"isDeleted": false,
			"id": "rHivF3hjLUHzdHIISZbdP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.375151339401,
			"y": 3049.6158359739807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.759735560964213,
			"height": 38.2764363398239,
			"seed": 1355810755,
			"groupIds": [
				"-N1ULQP4YA5d86Al2koCo",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1067,
			"versionNonce": 1598057965,
			"isDeleted": false,
			"id": "1245LNR7kFubY3adBz5H4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.1987622318456,
			"y": 3057.90612402915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 10.593598313153233,
			"height": 21.166692906815037,
			"seed": 832575331,
			"groupIds": [
				"-N1ULQP4YA5d86Al2koCo",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Kv5WfysDUyDdeVjGsaQIA",
					"type": "arrow"
				},
				{
					"id": "Y5NFTAtDQ4yjv7i7AduSw",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1018,
			"versionNonce": 95908707,
			"isDeleted": false,
			"id": "1TQKuzzRIysV0MoRb6BAa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.0213402495942,
			"y": 3068.499006543024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 10.18331229026763,
			"height": 0,
			"seed": 151859971,
			"groupIds": [
				"-N1ULQP4YA5d86Al2koCo",
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					10.18331229026763,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 2887,
			"versionNonce": 1781934157,
			"isDeleted": false,
			"id": "HkjIz1uo6JI_ENnwFz5Iy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2114.8454374276016,
			"y": 2975.1350851191883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 42.58558796825372,
			"height": 40.63212063026042,
			"seed": 395696803,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9gQs2chtQRb4ePChqmI-3",
				"focus": -0.36505020863305554,
				"gap": 2.2152259828567367
			},
			"endBinding": {
				"elementId": "ITbETUfL",
				"focus": -0.6402414045827972,
				"gap": 4.308944353928382
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
					42.58558796825372,
					40.63212063026042
				]
			]
		},
		{
			"type": "arrow",
			"version": 2935,
			"versionNonce": 433655555,
			"isDeleted": false,
			"id": "Kv5WfysDUyDdeVjGsaQIA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2113.4780102910067,
			"y": 3066.1666630696764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 42.585587968253776,
			"height": 40.63212063026048,
			"seed": 166235715,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "1245LNR7kFubY3adBz5H4",
				"focus": 0.4264743944491997,
				"gap": 4.127153627685857
			},
			"endBinding": {
				"elementId": "ITbETUfL",
				"focus": 0.6208739350866023,
				"gap": 2.9415172173335122
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
					42.585587968253776,
					-40.63212063026048
				]
			]
		},
		{
			"type": "text",
			"version": 885,
			"versionNonce": 1464178349,
			"isDeleted": false,
			"id": "ITbETUfL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2067.9509051054197,
			"y": 3006.78125599468,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 58.52714538574219,
			"height": 28.229307893064558,
			"seed": 1927532003,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HkjIz1uo6JI_ENnwFz5Iy",
					"type": "arrow"
				},
				{
					"id": "Kv5WfysDUyDdeVjGsaQIA",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"fontSize": 11.291723157225823,
			"fontFamily": 1,
			"text": "How similar\nare they?",
			"rawText": "How similar\nare they?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How similar\nare they?",
			"lineHeight": 1.25
		},
		{
			"id": "Ua46BgbT",
			"type": "text",
			"x": -2212.1229096822226,
			"y": 2922.9599910128336,
			"width": 12.7327880859375,
			"height": 28.348431257961295,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1914527267,
			"version": 293,
			"versionNonce": 1518745251,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "x",
			"rawText": "x",
			"fontSize": 22.678745006369034,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25
		},
		{
			"id": "3AbazGtP",
			"type": "text",
			"x": -2216.8074163913684,
			"y": 3004.637787318251,
			"width": 18.75933837890625,
			"height": 28.348431257961295,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"seed": 795610947,
			"version": 282,
			"versionNonce": 555235597,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "x'",
			"rawText": "x'",
			"fontSize": 22.678745006369034,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x'",
			"lineHeight": 1.25
		},
		{
			"id": "qgnEdKjd",
			"type": "text",
			"x": -2146.9263188850655,
			"y": 2891.4172617980453,
			"width": 49.651123046875,
			"height": 42.86036528706123,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"CpY6f1ds2jz43cLoz5Qj3"
			],
			"frameId": null,
			"roundness": null,
			"seed": 404981987,
			"version": 433,
			"versionNonce": 1181575747,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "encoded\nfeatures\nz",
			"rawText": "encoded\nfeatures\nz",
			"fontSize": 11.429430743216328,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "encoded\nfeatures\nz",
			"lineHeight": 1.25
		},
		{
			"id": "ZS7mPZk5",
			"type": "text",
			"x": -2003.073535282566,
			"y": 3005.9028793161483,
			"width": 153.50433349609375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2061265133,
			"version": 272,
			"versionNonce": 824676205,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": " y (x,x') = dot(z,z')",
			"rawText": " y (x,x') = dot(z,z')",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " y (x,x') = dot(z,z')",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 40708579,
			"isDeleted": false,
			"id": "mZGZx4DGSaE-821u9R5YV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"angle": 0,
			"x": -1948.515471673939,
			"y": 2961.403856433561,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 59.65627168404517,
			"height": 26.165031440370466,
			"seed": 1470869091,
			"groupIds": [
				"d0RLG8mbbAW52iV5W-xDO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					49.713559736704454,
					1.569901886422088
				],
				[
					37.15434464532641,
					26.165031440370466
				],
				[
					-9.942711947340724,
					23.548528296333654
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "a95cMAsXqXJ42ekptp8bF",
			"type": "line",
			"x": -1935.9562565825609,
			"y": 2933.1456224779604,
			"width": 5.756306916881489,
			"height": 40.81744904697828,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"groupIds": [
				"d0RLG8mbbAW52iV5W-xDO"
			],
			"frameId": null,
			"roundness": null,
			"seed": 32382467,
			"version": 211,
			"versionNonce": 96278989,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.756306916881489,
					40.81744904697828
				]
			],
			"lastCommittedPoint": [
				-7.855665910097059,
				55.703812817052494
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "JdpDsLW0EXrVSG8TQbTiP",
			"type": "line",
			"x": -1928.630047779257,
			"y": 2934.715524364383,
			"width": 19.362123265874086,
			"height": 38.72424653174883,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"groupIds": [
				"d0RLG8mbbAW52iV5W-xDO"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1813136227,
			"version": 207,
			"versionNonce": 328463747,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					19.362123265874086,
					38.72424653174883
				]
			],
			"lastCommittedPoint": [
				26.423603515780997,
				52.8472070315629
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "FZV4Ewqd6iV7Y6bMH8GtJ",
			"type": "line",
			"x": -1909.7912251421903,
			"y": 2937.8553281372274,
			"width": 16.74562012183727,
			"height": 32.444638986059815,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"groupIds": [
				"d0RLG8mbbAW52iV5W-xDO"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1792341859,
			"version": 233,
			"versionNonce": 401758253,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-16.74562012183727,
					32.444638986059815
				]
			],
			"lastCommittedPoint": [
				-22.852846283919007,
				44.27738967509322
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Qhy8VDvC4FTsNWp0IRBAK",
			"type": "line",
			"x": -1947.4688704163245,
			"y": 2921.6330086441976,
			"width": 59.65627168404517,
			"height": 26.165031440370466,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"groupIds": [
				"d0RLG8mbbAW52iV5W-xDO"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1947682755,
			"version": 342,
			"versionNonce": 1495289123,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					49.713559736704454,
					1.569901886422088
				],
				[
					37.15434464532641,
					26.165031440370466
				],
				[
					-9.942711947340724,
					23.548528296333654
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				2.1424543391176485,
				-2.1424543391171937
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "image",
			"version": 276,
			"versionNonce": 28363405,
			"isDeleted": false,
			"id": "ZZQNClx0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2405.0742867966396,
			"y": 3151.000674714768,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 761.8283398103608,
			"height": 42.598983890566345,
			"seed": 75952,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IXFcyOQ40kqXQI_NNUahV",
					"type": "arrow"
				},
				{
					"id": "kddXFvPpdBgHfLipruoNl",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6f246287499dad1e7689b52b652913c933edee09",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JP0Dp90E",
			"type": "text",
			"x": -2106.220022693407,
			"y": 3119.8095650748605,
			"width": 164.11981201171875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 453193443,
			"version": 113,
			"versionNonce": 1182838979,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Taylor expansion",
			"rawText": "Taylor expansion",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Taylor expansion",
			"lineHeight": 1.25
		},
		{
			"id": "LPVshn-ZoX5MK7DxE5YCZ",
			"type": "arrow",
			"x": -2170.561163193903,
			"y": 3190.1539524802456,
			"width": 4.999060124606785,
			"height": 41.42078388960317,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 911296835,
			"version": 270,
			"versionNonce": 1672605933,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.4283028927447958,
					17.139634712938914
				],
				[
					-4.999060124606785,
					41.42078388960317
				]
			],
			"lastCommittedPoint": [
				-2.8566057854895917,
				62.84532728077693
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "6I5zID0C",
				"focus": -0.051221361038259965,
				"gap": 7.49906012460724
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "6I5zID0C",
			"type": "text",
			"x": -2198.6568727441368,
			"y": 3239.073796494456,
			"width": 40.48008728027344,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1005798627,
			"version": 97,
			"versionNonce": 1565761635,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "LPVshn-ZoX5MK7DxE5YCZ",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "First\norder",
			"rawText": "First\norder",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "First\norder",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 391,
			"versionNonce": 192891725,
			"isDeleted": false,
			"id": "IXFcyOQ40kqXQI_NNUahV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1992.7374530471593,
			"y": 3199.969540397449,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.999060124606785,
			"height": 41.42078388960317,
			"seed": 463382349,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZZQNClx0",
				"focus": -0.08813536251602148,
				"gap": 6.369881792114484
			},
			"endBinding": {
				"elementId": "h6C7rtGV",
				"focus": -0.05122136103825714,
				"gap": 7.499060124606785
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.4283028927447958,
					17.139634712938914
				],
				[
					-4.999060124606785,
					41.42078388960317
				]
			]
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 1734843395,
			"isDeleted": false,
			"id": "h6C7rtGV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2020.8331625973929,
			"y": 3248.8893844116587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 40.48008728027344,
			"height": 40,
			"seed": 1699100077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IXFcyOQ40kqXQI_NNUahV",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "First\norder",
			"rawText": "First\norder",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "First\norder",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 444,
			"versionNonce": 1500666285,
			"isDeleted": false,
			"id": "kddXFvPpdBgHfLipruoNl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1782.7769278136539,
			"y": 3197.8270860583307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.915896581920833,
			"height": 42.13493533597557,
			"seed": 320857027,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZZQNClx0",
				"focus": -0.6363139551650298,
				"gap": 4.2274274529963805
			},
			"endBinding": {
				"elementId": "mzqI96jg",
				"focus": -0.05122136103826223,
				"gap": 7.499060124607695
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.4283028927447958,
					17.139634712938914
				],
				[
					-5.915896581920833,
					42.13493533597557
				]
			]
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 1891312547,
			"isDeleted": false,
			"id": "mzqI96jg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1865.5869032511778,
			"y": 3247.461081518914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 148.48031616210938,
			"height": 60,
			"seed": 1435792227,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kddXFvPpdBgHfLipruoNl",
					"type": "arrow"
				},
				{
					"id": "Qd3QNG6Q32qOhwv6Dxk7L",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Second order\ndescribing relations\nHessian x product ",
			"rawText": "Second order\ndescribing relations\nHessian x product ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Second order\ndescribing relations\nHessian x product ",
			"lineHeight": 1.25
		},
		{
			"id": "9qAwGrhT",
			"type": "text",
			"x": -2332.9797511620186,
			"y": 3305.846486986602,
			"width": 573.28125,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 882044035,
			"version": 382,
			"versionNonce": 1723112461,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "We obviously have to assume that the function is piece-wise linear\nand we have well chosen root points for this taylor-based approximation\nto be accurate",
			"rawText": "We obviously have to assume that the function is piece-wise linear\nand we have well chosen root points for this taylor-based approximation\nto be accurate",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We obviously have to assume that the function is piece-wise linear\nand we have well chosen root points for this taylor-based approximation\nto be accurate",
			"lineHeight": 1.25
		},
		{
			"id": "Qd3QNG6Q32qOhwv6Dxk7L",
			"type": "arrow",
			"x": -1712.0759346227792,
			"y": 3275.852126044942,
			"width": 51.418904138817425,
			"height": 44.99154112146516,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 1188653315,
			"version": 264,
			"versionNonce": 24950595,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					39.99248099685792,
					7.8556659100972865
				],
				[
					51.418904138817425,
					44.99154112146516
				]
			],
			"lastCommittedPoint": [
				51.418904138817425,
				44.99154112146516
			],
			"startBinding": {
				"elementId": "mzqI96jg",
				"focus": -0.3853498111388407,
				"gap": 5.030652466289212
			},
			"endBinding": {
				"elementId": "vZ8YahAI",
				"focus": 0.052617348494712696,
				"gap": 11.426423141959276
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vZ8YahAI",
			"type": "text",
			"x": -1734.77695025566,
			"y": 3332.2700903083664,
			"width": 169.6643829345703,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1409276621,
			"version": 132,
			"versionNonce": 1799328365,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Qd3QNG6Q32qOhwv6Dxk7L",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "can be seen\nas a second order\nvariation of Gradient\nx input",
			"rawText": "can be seen\nas a second order\nvariation of Gradient\nx input",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can be seen\nas a second order\nvariation of Gradient\nx input",
			"lineHeight": 1.25
		},
		{
			"id": "fhADzMFtdEGFE_d5FN3_a",
			"type": "arrow",
			"x": -1680.6935853527489,
			"y": 3433.679595693257,
			"width": 201.39070787703554,
			"height": 53.5613584779353,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 469718445,
			"version": 304,
			"versionNonce": 403363555,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-28.566057854898645,
					49.990601246072856
				],
				[
					-201.39070787703554,
					53.5613584779353
				]
			],
			"lastCommittedPoint": [
				-201.39070787703554,
				53.5613584779353
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "juXqaw8l",
			"type": "text",
			"x": -2335.0619693748117,
			"y": 3410.1125979629655,
			"width": 613.1532592773438,
			"height": 140,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1988820291,
			"version": 188,
			"versionNonce": 1675410637,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Similar to first Order methods\nit suffers from\nshattered gradients, i.e. the local gradient variations become stronger\nwith increasing model depth\nand\ndifficulty to robustly select root points, danger of adversarials that do not\nmeaningfully represent the data",
			"rawText": "Similar to first Order methods\nit suffers from\nshattered gradients, i.e. the local gradient variations become stronger\nwith increasing model depth\nand\ndifficulty to robustly select root points, danger of adversarials that do not\nmeaningfully represent the data",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Similar to first Order methods\nit suffers from\nshattered gradients, i.e. the local gradient variations become stronger\nwith increasing model depth\nand\ndifficulty to robustly select root points, danger of adversarials that do not\nmeaningfully represent the data",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 661,
			"versionNonce": 1660158595,
			"isDeleted": false,
			"id": "OdhtTbrmbNRzGD8JQGSAy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2551.598686751366,
			"y": 3109.9396774000793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 147.56793348736585,
			"height": 100.88828105768889,
			"seed": 1673270349,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					-109.1701548758574,
					16.563747636336963
				],
				[
					-109.923052495691,
					-18.069542876003965
				],
				[
					-144.55634300803183,
					32.37459765284036
				],
				[
					-106.15856439652327,
					82.81873818168492
				],
				[
					-106.15856439652339,
					47.555580012944056
				],
				[
					3.011590479334025,
					63.24340006601395
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "aFbM7NDj",
			"type": "text",
			"x": -3364.1276221169896,
			"y": 2828.0297982521492,
			"width": 167.74871826171875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 23288397,
			"version": 121,
			"versionNonce": 2015730477,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Tranformers",
			"rawText": "Tranformers",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tranformers",
			"lineHeight": 1.25
		},
		{
			"id": "IkkQWQHTbofVcFDpaAz3-",
			"type": "image",
			"x": -2400.06657843238,
			"y": 3620.205923441226,
			"width": 781,
			"height": 99,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1609619747,
			"version": 188,
			"versionNonce": 989248035,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d62494fbdd7b83ce858cbdd806d7d5a2e1065de7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "6_IpETCu4QFFaDh8WOAo0",
			"type": "rectangle",
			"x": -2399.6792994156367,
			"y": 3616.827157903113,
			"width": 784.2189812881616,
			"height": 102.17253013354366,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1334939725,
			"version": 150,
			"versionNonce": 545500557,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "N92NP1Ns",
			"type": "text",
			"x": -2259.568215191057,
			"y": 3576.298849572518,
			"width": 487.6794128417969,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1143217805,
			"version": 105,
			"versionNonce": 1560378819,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "To ensure that you focus on positive corrolation",
			"rawText": "To ensure that you focus on positive corrolation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To ensure that you focus on positive corrolation",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 696,
			"versionNonce": 204501997,
			"isDeleted": false,
			"id": "bpAODRXDFiX3GKRDZog0N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -532.46936794724,
			"y": 3273.662870828917,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 159.30589483933522,
			"height": 200.2672552737081,
			"seed": 60047171,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					-15.10639383441412,
					131.88221745116522
				],
				[
					37.036283781317074,
					130.35876970473925
				],
				[
					-42.52671757356245,
					200.2672552737081
				],
				[
					-122.26961105801816,
					133.3662531535784
				],
				[
					-70.81470288068911,
					132.747932546969
				],
				[
					-78.25662787303531,
					4.240906033816387
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "a6IYhvZI",
			"type": "text",
			"x": -774.5717028742847,
			"y": 3489.568061572292,
			"width": 404.09771728515625,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1433918595,
			"version": 115,
			"versionNonce": 1681050979,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Graph Neural Networks\nand higher order explanations",
			"rawText": "Graph Neural Networks\nand higher order explanations",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph Neural Networks\nand higher order explanations",
			"lineHeight": 1.25
		},
		{
			"id": "ioUlCctv",
			"type": "text",
			"x": -1078.3231784414797,
			"y": 3578.7713139009684,
			"width": 1013.239013671875,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1589470957,
			"version": 577,
			"versionNonce": 1194683981,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Graph neural networks learn a representation of the graph through message passing\nat each iteration of message passing we use the adjacency matrix to aggregate the information\nfrom all the nodes to their neighbours.\n\nmeaning the message not only can passes from one neighbour but partially from all nodes in the graph.\na second order contribution is not enough we need a higher order contribution in order to understand\nthe effects of each node on other nodes",
			"rawText": "Graph neural networks learn a representation of the graph through message passing\nat each iteration of message passing we use the adjacency matrix to aggregate the information\nfrom all the nodes to their neighbours.\n\nmeaning the message not only can passes from one neighbour but partially from all nodes in the graph.\na second order contribution is not enough we need a higher order contribution in order to understand\nthe effects of each node on other nodes",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph neural networks learn a representation of the graph through message passing\nat each iteration of message passing we use the adjacency matrix to aggregate the information\nfrom all the nodes to their neighbours.\n\nmeaning the message not only can passes from one neighbour but partially from all nodes in the graph.\na second order contribution is not enough we need a higher order contribution in order to understand\nthe effects of each node on other nodes",
			"lineHeight": 1.25
		},
		{
			"id": "f2hUE0FOeIsDsmaV3BbxI",
			"type": "image",
			"x": -787.6316189572585,
			"y": 4082.638424337677,
			"width": 407,
			"height": 208,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1836344493,
			"version": 263,
			"versionNonce": 64563459,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7eea13b18bbdb468327763d4b55c22730dd2d3d0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "V0I5qP6c",
			"type": "text",
			"x": -681.627289165423,
			"y": 4051.730724537389,
			"width": 176.63980102539062,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1756642883,
			"version": 307,
			"versionNonce": 543956141,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Walking backwards",
			"rawText": "Walking backwards",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Walking backwards",
			"lineHeight": 1.25
		},
		{
			"id": "N8d6_QukDnt7dYuxheQ5l",
			"type": "rectangle",
			"x": -787.0335948531663,
			"y": 4080.3564369636297,
			"width": 409.02461807587736,
			"height": 206.12264217997017,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1798581325,
			"version": 206,
			"versionNonce": 24318115,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 296,
			"versionNonce": 1333657357,
			"isDeleted": false,
			"id": "wcdixQdj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -664.1588462887096,
			"y": 3855.638333758323,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 151.91828834662456,
			"height": 26.809109708227865,
			"seed": 34623,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ioDEAnXoF1S1YjiU1GwNZ",
					"type": "arrow"
				},
				{
					"id": "AZ0P0qmH9kn7Q0s2R9oTO",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5fbcbafe4f081a6ebcaf8ed140c8be653ad64528",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 401,
			"versionNonce": 1856963651,
			"isDeleted": false,
			"id": "S0fUELPE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -696.375692822472,
			"y": 3967.668142588656,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 202.01919775317546,
			"height": 27.92135253499173,
			"seed": 8155,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "yEHAGzMN6CeO6rn6aPVxR",
					"type": "arrow"
				},
				{
					"id": "qtUgdE5awH_hudk8MWEqy",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1ed1b5248543ad7de09650ef46be19a471858b71",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "tgREcFcn",
			"type": "text",
			"x": -760.2761255601483,
			"y": 3776.673289796876,
			"width": 351.37957763671875,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1268658285,
			"version": 36,
			"versionNonce": 1524929901,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Aggregate:\neach node receives information from\nthe neighboring node",
			"rawText": "Aggregate:\neach node receives information from\nthe neighboring node",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Aggregate:\neach node receives information from\nthe neighboring node",
			"lineHeight": 1.25
		},
		{
			"id": "W2xZytxw",
			"type": "text",
			"x": -782.0616828921129,
			"y": 3914.0883845835224,
			"width": 373.4795837402344,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 605781069,
			"version": 225,
			"versionNonce": 594248675,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Combine:\nextracts new features for each node",
			"rawText": "Combine:\nextracts new features for each node",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Combine:\nextracts new features for each node",
			"lineHeight": 1.25
		},
		{
			"id": "ioDEAnXoF1S1YjiU1GwNZ",
			"type": "arrow",
			"x": -550.2325630451273,
			"y": 3890.4701651670675,
			"width": 113.07058732158123,
			"height": 18.25044227635135,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1901096045,
			"version": 848,
			"versionNonce": 1038704589,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					45.08932797686839,
					18.25044227635135
				],
				[
					113.07058732158123,
					14.538815318318939
				]
			],
			"lastCommittedPoint": [
				129.90020679050178,
				17.176886848330923
			],
			"startBinding": {
				"elementId": "wcdixQdj",
				"focus": 0.13725109017123627,
				"gap": 8.02272170051674
			},
			"endBinding": {
				"elementId": "bYPzDLxR",
				"focus": 0.08802170563719319,
				"gap": 12.21854852317449
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "bYPzDLxR",
			"type": "text",
			"x": -424.9434272003716,
			"y": 3873.278390322592,
			"width": 148.7843475341797,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1055950637,
			"version": 298,
			"versionNonce": 2008485763,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ioDEAnXoF1S1YjiU1GwNZ",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Representation of\nthe graph at layer\nt",
			"rawText": "Representation of\nthe graph at layer\nt",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Representation of\nthe graph at layer\nt",
			"lineHeight": 1.25
		},
		{
			"id": "AZ0P0qmH9kn7Q0s2R9oTO",
			"type": "arrow",
			"x": -580.336317718527,
			"y": 3885.102388026964,
			"width": 142.57513350355885,
			"height": 18.250442276351805,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1595175427,
			"version": 937,
			"versionNonce": 1319493165,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-69.7811028213439,
					18.250442276351805
				],
				[
					-142.57513350355885,
					6.523880856573214
				]
			],
			"lastCommittedPoint": [
				-231.88797245246587,
				6.4413325681243805
			],
			"startBinding": {
				"elementId": "wcdixQdj",
				"focus": -0.5445039170307124,
				"gap": 2.6549445604132416
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "3VybF28Q",
			"type": "text",
			"x": -875.2235660955711,
			"y": 3867.204834894571,
			"width": 132.52828979492188,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 821099053,
			"version": 303,
			"versionNonce": 1037051683,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "AeKr3JRtD5so-TgdnAzYD",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Adjacency matrix",
			"rawText": "Adjacency matrix",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Adjacency matrix",
			"lineHeight": 1.25
		},
		{
			"id": "yEHAGzMN6CeO6rn6aPVxR",
			"type": "arrow",
			"x": -570.1005457049423,
			"y": 3998.5014391977697,
			"width": 146.24439808114153,
			"height": 28.8218766976006,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 478503693,
			"version": 102,
			"versionNonce": 1677955213,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					69.99598626560203,
					28.8218766976006
				],
				[
					146.24439808114153,
					17.27467571902571
				]
			],
			"lastCommittedPoint": [
				149.25614718400425,
				19.557702044800408
			],
			"startBinding": {
				"elementId": "S0fUELPE",
				"focus": 0.11645050913212326,
				"gap": 2.9119440741217204
			},
			"endBinding": {
				"elementId": "3cxaYIPk",
				"focus": 0.18118671545406484,
				"gap": 3.5172046351184463
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "3cxaYIPk",
			"type": "text",
			"x": -420.33894298868233,
			"y": 3988.2079118057695,
			"width": 171.92034912109375,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 384135149,
			"version": 103,
			"versionNonce": 2082818755,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "yEHAGzMN6CeO6rn6aPVxR",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "the row of Zt\nassociated to node K",
			"rawText": "the row of Zt\nassociated to node K",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the row of Zt\nassociated to node K",
			"lineHeight": 1.25
		},
		{
			"id": "qtUgdE5awH_hudk8MWEqy",
			"type": "arrow",
			"x": -605.0985388377434,
			"y": 3996.4427337193697,
			"width": 157.03228498150918,
			"height": 26.763171219201013,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1222109155,
			"version": 59,
			"versionNonce": 1002174189,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-67.93728078720198,
					26.763171219201013
				],
				[
					-157.03228498150918,
					16.31400936975433
				]
			],
			"lastCommittedPoint": [
				-155.4322636192045,
				16.469643827200343
			],
			"startBinding": {
				"elementId": "S0fUELPE",
				"focus": -0.2042687285800973,
				"gap": 1
			},
			"endBinding": {
				"elementId": "bZlOHBt5",
				"focus": -0.4363090592307225,
				"gap": 6.390625865616357
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "bZlOHBt5",
			"type": "text",
			"x": -1226.0424152610408,
			"y": 3979.9730898921694,
			"width": 457.5209655761719,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1509559757,
			"version": 78,
			"versionNonce": 1733622371,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "qtUgdE5awH_hudk8MWEqy",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "a ‘combine’ function, typically a one-layer or multi-layer\nneural network, that produces the new representation for\neach node in the graph.",
			"rawText": "a ‘combine’ function, typically a one-layer or multi-layer\nneural network, that produces the new representation for\neach node in the graph.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a ‘combine’ function, typically a one-layer or multi-layer\nneural network, that produces the new representation for\neach node in the graph.",
			"lineHeight": 1.25
		},
		{
			"id": "AeKr3JRtD5so-TgdnAzYD",
			"type": "arrow",
			"x": -867.583487333751,
			"y": 3854.392055709765,
			"width": 90.58304104960257,
			"height": 51.46763696000153,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1344523203,
			"version": 56,
			"versionNonce": 542675277,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-22.6457602624007,
					-48.37957874240146
				],
				[
					-90.58304104960257,
					-51.46763696000153
				]
			],
			"lastCommittedPoint": [
				-90.58304104960257,
				-51.46763696000153
			],
			"startBinding": {
				"elementId": "3VybF28Q",
				"focus": -0.6758157261745404,
				"gap": 12.812779184806004
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "kWQguGQR",
			"type": "text",
			"x": -1395.6827169562437,
			"y": 3788.513480400963,
			"width": 479.76092529296875,
			"height": 140,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1143902797,
			"version": 127,
			"versionNonce": 472757763,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "the true input Λ of the GNN occurs at\nmultiple layers and because layers are generally composed\nin a multiplicative manner, a first-order\nanalysis of the GNN function f (Λ) would not be suitable to\nidentify the multiplicative interactions. These interactions\ncan however be identified by applying a higher-order Taylor\nexpansion",
			"rawText": "the true input Λ of the GNN occurs at\nmultiple layers and because layers are generally composed\nin a multiplicative manner, a first-order\nanalysis of the GNN function f (Λ) would not be suitable to\nidentify the multiplicative interactions. These interactions\ncan however be identified by applying a higher-order Taylor\nexpansion",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the true input Λ of the GNN occurs at\nmultiple layers and because layers are generally composed\nin a multiplicative manner, a first-order\nanalysis of the GNN function f (Λ) would not be suitable to\nidentify the multiplicative interactions. These interactions\ncan however be identified by applying a higher-order Taylor\nexpansion",
			"lineHeight": 1.25
		},
		{
			"id": "G7YE0mRQ",
			"type": "text",
			"x": -3772.630632458373,
			"y": 2869.570998683573,
			"width": 984.779052734375,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 610602947,
			"version": 150,
			"versionNonce": 1328734125,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "The conservation axiom (also known as completeness or efficiency) states that scores assigned to\ninput variables and forming the explanation must sum to the output of the network, in\nother words, each input variable contributes a share of the predicted score at the output\nThis is an important factor to keep in mind.",
			"rawText": "The conservation axiom (also known as completeness or efficiency) states that scores assigned to\ninput variables and forming the explanation must sum to the output of the network, in\nother words, each input variable contributes a share of the predicted score at the output\nThis is an important factor to keep in mind.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The conservation axiom (also known as completeness or efficiency) states that scores assigned to\ninput variables and forming the explanation must sum to the output of the network, in\nother words, each input variable contributes a share of the predicted score at the output\nThis is an important factor to keep in mind.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 260,
			"versionNonce": 430833059,
			"isDeleted": false,
			"id": "2ASLptRI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3487.463732501024,
			"y": 3161.462167072514,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 191.18349928876157,
			"height": 52.78947368421028,
			"seed": 45748,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "681bf9760978509466f706f2de3c8241303df575",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 316,
			"versionNonce": 510943757,
			"isDeleted": false,
			"id": "q6ipTer3PXf2f2A9OxLek",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3257.6097505428634,
			"y": 3160.699453471619,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 185.81413460999357,
			"height": 54.31490088599812,
			"seed": 1468162733,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b513ee1331e6eb4af8647f25031b2202ef6f4fdb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 201,
			"versionNonce": 2063880515,
			"isDeleted": false,
			"id": "cIcj1aPT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3365.57029134313,
			"y": 3253.041115177776,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 192.08466819221962,
			"height": 61.789473684210506,
			"seed": 59717,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d38b92ad19cf0731494136a4460970874787c52d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 341,
			"versionNonce": 1662425197,
			"isDeleted": false,
			"id": "cDBcsbNuAVjMD-l6z0ldw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3391.8719833702535,
			"y": 3320.5147989654274,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 234.55354900447028,
			"height": 56.533419503641554,
			"seed": 745244739,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "65d551b9a113662bede60f8e955a8351e60dc29c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 58,
			"versionNonce": 1905209571,
			"isDeleted": false,
			"id": "nYUQNu2v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3343.187485043689,
			"y": 3445.6311604196158,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 159.94999218505765,
			"height": 38.96217758353968,
			"seed": 86652,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9839c498976482ef7039ac589ec9b7db1763c33d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "N15uQi1T",
			"type": "text",
			"x": -3692.378373677436,
			"y": 3384.08134400765,
			"width": 824.0991821289062,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 85520227,
			"version": 286,
			"versionNonce": 383976141,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "PtdiVGVPqqoThQzpinS8k",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "If it holds that the following condition is true for every component\nof the neural network then conservation is met using this methods on transformers\n\n\n\nand if we translate this into the transformer architecture we get",
			"rawText": "If it holds that the following condition is true for every component\nof the neural network then conservation is met using this methods on transformers\n\n\n\nand if we translate this into the transformer architecture we get",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If it holds that the following condition is true for every component\nof the neural network then conservation is met using this methods on transformers\n\n\n\nand if we translate this into the transformer architecture we get",
			"lineHeight": 1.25
		},
		{
			"id": "jWvTuZjodyY2j8lgOh-Tm",
			"type": "image",
			"x": -3649.8232874504465,
			"y": 3541.951835787846,
			"width": 432,
			"height": 162,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 634316995,
			"version": 77,
			"versionNonce": 2128419971,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d74c227c43362c09d7b59ae027324cd8ee3b5af",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JfqqTH1RJjMCC6D1GFBIZ",
			"type": "image",
			"x": -3217.8232865875957,
			"y": 3542.0614837774056,
			"width": 381,
			"height": 158,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1410381507,
			"version": 104,
			"versionNonce": 1047732525,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2cfdab75206c322ed8074f87e5683f635c16a731",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ygD2YLc4z7-MYNMHxEZt8",
			"type": "rectangle",
			"x": -3651.365858120869,
			"y": 3539.098808910874,
			"width": 816.0607107152623,
			"height": 163.4329975451401,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 249836205,
			"version": 50,
			"versionNonce": 1856803875,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "uXecrgaf",
			"type": "text",
			"x": -3317.6418018547065,
			"y": 3714.441215901232,
			"width": 110.7398681640625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1655134605,
			"version": 44,
			"versionNonce": 254833549,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Resulting in",
			"rawText": "Resulting in",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Resulting in",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 129,
			"versionNonce": 283908035,
			"isDeleted": false,
			"id": "3QP88z8U",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3490.654871547479,
			"y": 3743.9456873561294,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 453.46728444253915,
			"height": 48.014183058621796,
			"seed": 45351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b79be707beb5de5348804dbb1b8527a03e05b245",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "PtdiVGVPqqoThQzpinS8k",
			"type": "arrow",
			"x": -3430.702325135683,
			"y": 3602.8652606411065,
			"width": 38.22925854148616,
			"height": 42.28702760212809,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1270996845,
			"version": 87,
			"versionNonce": 1431599597,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.5121006496310656,
					-34.332042211629414
				],
				[
					35.717157891855095,
					-42.28702760212809
				]
			],
			"lastCommittedPoint": [
				33.91335877002439,
				-41.86834416052352
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "N15uQi1T",
				"focus": -0.4830008530737836,
				"gap": 26.49688903132801
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "2GwVpgSN",
			"type": "text",
			"x": -3394.11831120803,
			"y": 3548.8429960244002,
			"width": 64.16014099121094,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1232591757,
			"version": 125,
			"versionNonce": 867837795,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "softmax",
			"rawText": "softmax",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "softmax",
			"lineHeight": 1.25
		},
		{
			"id": "uI3_0qArVqJgp1CBrjWS-",
			"type": "arrow",
			"x": -3373.342693635763,
			"y": 3591.14212427616,
			"width": 102.57744319328367,
			"height": 21.771538963472267,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 772283245,
			"version": 120,
			"versionNonce": 434680909,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.05179058755084,
					-6.6989350656835995
				],
				[
					83.7366883210475,
					-11.30445292334116
				],
				[
					102.57744319328367,
					-21.771538963472267
				]
			],
			"lastCommittedPoint": [
				102.57744319328367,
				-21.771538963472267
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "5LztnZr0",
				"focus": -0.37034018055506435,
				"gap": 5.958373379524801
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "5LztnZr0",
			"type": "text",
			"x": -3313.287837748396,
			"y": 3543.412211933163,
			"width": 94.25621032714844,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 587877795,
			"version": 57,
			"versionNonce": 1566917379,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "uI3_0qArVqJgp1CBrjWS-",
					"type": "arrow"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "pre-softmax",
			"rawText": "pre-softmax",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "pre-softmax",
			"lineHeight": 1.25
		},
		{
			"id": "oEoLjW4F",
			"type": "text",
			"x": -3736.8355879839505,
			"y": 3798.3379424787245,
			"width": 943.3790283203125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2112385443,
			"version": 342,
			"versionNonce": 147235501,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Which implies that if the right-most term is not zero then this method is not conservative!\nand the right term is a covariance between q which is a function of x and thus has a relation\nto x, thus the covariance is often not 0",
			"rawText": "Which implies that if the right-most term is not zero then this method is not conservative!\nand the right term is a covariance between q which is a function of x and thus has a relation\nto x, thus the covariance is often not 0",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which implies that if the right-most term is not zero then this method is not conservative!\nand the right term is a covariance between q which is a function of x and thus has a relation\nto x, thus the covariance is often not 0",
			"lineHeight": 1.25
		},
		{
			"id": "sG6L5RJeppnyCq8sS9glb",
			"type": "rectangle",
			"x": -3516.2456060660757,
			"y": 3059.8173417859143,
			"width": 62.52390973037018,
			"height": 45.07537678236031,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 380701475,
			"version": 156,
			"versionNonce": 1181477539,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "fkwKKqcq"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "fkwKKqcq",
			"type": "text",
			"x": -3490.603646318078,
			"y": 3069.8550301770947,
			"width": 11.239990234375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 72591523,
			"version": 130,
			"versionNonce": 379045133,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "x",
			"rawText": "x",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "sG6L5RJeppnyCq8sS9glb",
			"originalText": "x",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 168,
			"versionNonce": 326934083,
			"isDeleted": false,
			"id": "2_19EICi29pShmxdMtkTa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3517.0611307169434,
			"y": 3003.9207537527145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 62.52390973037018,
			"height": 45.07537678236031,
			"seed": 1341259533,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "uFMNtTDM"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 1725274989,
			"isDeleted": false,
			"id": "uFMNtTDM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3494.0791670016606,
			"y": 3013.958442143895,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 16.559982299804688,
			"height": 25,
			"seed": 752391533,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "x'",
			"rawText": "x'",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "2_19EICi29pShmxdMtkTa",
			"originalText": "x'",
			"lineHeight": 1.25
		},
		{
			"id": "VNkBTwJXV5e2NhvTy5b7P",
			"type": "line",
			"x": -3453.587847517901,
			"y": 3024.8478757272032,
			"width": 78.11247120960115,
			"height": 0.8052832083462818,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1941705741,
			"version": 92,
			"versionNonce": 1333124579,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					78.11247120960115,
					-0.8052832083462818
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "U80O5LYQDC7tmrnrSYvCi",
			"type": "line",
			"x": -3455.198413934594,
			"y": 3086.04939956153,
			"width": 139.31399504392903,
			"height": 29.795478708816972,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1639461251,
			"version": 148,
			"versionNonce": 1909040589,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					139.31399504392857,
					-0.8052832083462818
				],
				[
					139.31399504392903,
					-29.795478708816972
				]
			],
			"lastCommittedPoint": [
				140.9245614606216,
				-30.600761917163254
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "En8uE74BQz5X7ooNY1FQC",
			"type": "rectangle",
			"x": -3373.0595266832597,
			"y": 2986.999564934922,
			"width": 141.72984466896787,
			"height": 67.64378950109813,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1727689357,
			"version": 129,
			"versionNonce": 627452291,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "D1ItH8Xf"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "D1ItH8Xf",
			"type": "text",
			"x": -3348.2445616241666,
			"y": 2995.8214596854714,
			"width": 92.09991455078125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 894176301,
			"version": 113,
			"versionNonce": 1787651117,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Attention\nhead",
			"rawText": "Attention head",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "En8uE74BQz5X7ooNY1FQC",
			"originalText": "Attention head",
			"lineHeight": 1.25
		},
		{
			"id": "E8S0tdj7KkdH_U4DmL7Zz",
			"type": "rectangle",
			"x": -3190.260238388625,
			"y": 3004.715795518543,
			"width": 52.343408542516045,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 478675021,
			"version": 95,
			"versionNonce": 1519124771,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "sMKFXruL"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "sMKFXruL",
			"type": "text",
			"x": -3168.778528929379,
			"y": 3009.715795518543,
			"width": 9.379989624023438,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 241395853,
			"version": 74,
			"versionNonce": 1695176333,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "y",
			"rawText": "y",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "E8S0tdj7KkdH_U4DmL7Zz",
			"originalText": "y",
			"lineHeight": 1.25
		},
		{
			"id": "CXCW22J5HOa5IEqf0UqGe",
			"type": "line",
			"x": -3232.9402484309853,
			"y": 3020.0161764771246,
			"width": 41.069443625666736,
			"height": 0.8052832083467365,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1878246349,
			"version": 79,
			"versionNonce": 139846851,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					41.069443625666736,
					0.8052832083467365
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "RxSzmqH1Ns0axmgntSlOj",
			"type": "line",
			"x": -3318.3002685157044,
			"y": 3085.2441163531835,
			"width": 154.6143760025102,
			"height": 46.70642608409162,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 496287939,
			"version": 160,
			"versionNonce": 1006238957,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					153.80909279416392,
					4.547473508864641e-13
				],
				[
					154.6143760025102,
					-46.70642608409116
				]
			],
			"lastCommittedPoint": [
				153.80909279416392,
				-45.0958596673986
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "gXevjXszTqHXnzNlWOdK4",
			"type": "line",
			"x": -3136.3062634294165,
			"y": 3022.4320261021644,
			"width": 69.2543559177916,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 469313987,
			"version": 126,
			"versionNonce": 375542883,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					69.2543559177916,
					0
				]
			],
			"lastCommittedPoint": [
				80.52832083464091,
				0.8052832083462818
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "COevO0DxcCn6F7OvkkXpw",
			"type": "rectangle",
			"x": -3065.441341094931,
			"y": 2977.3361664347667,
			"width": 34.62717795889557,
			"height": 109.51851633511114,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2023891843,
			"version": 122,
			"versionNonce": 921032525,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "PQsZVsJc"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "PQsZVsJc",
			"type": "text",
			"x": -3055.7877481481983,
			"y": 2994.595424602322,
			"width": 15.319992065429688,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 52195171,
			"version": 84,
			"versionNonce": 1954533379,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "M\nL\nP",
			"rawText": "MLP",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "COevO0DxcCn6F7OvkkXpw",
			"originalText": "MLP",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 138,
			"versionNonce": 1881630125,
			"isDeleted": false,
			"id": "3zx_whteTgGyhcJGDzqEY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2974.041696947617,
			"y": 3009.7637253522425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 52.343408542516045,
			"height": 35,
			"seed": 17290723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "svihJSMk"
				}
			],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 346871715,
			"isDeleted": false,
			"id": "svihJSMk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2952.5599874883706,
			"y": 3014.7637253522425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 9.379989624023438,
			"height": 25,
			"seed": 1106846083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "3zx_whteTgGyhcJGDzqEY",
			"originalText": "y",
			"lineHeight": 1.25
		},
		{
			"id": "2FUYVHe-1q3ApFJjdeS7A",
			"type": "line",
			"x": -3028.3983135109993,
			"y": 3025.65315893555,
			"width": 56.36982458424836,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1369923875,
			"version": 48,
			"versionNonce": 2062034957,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					56.36982458424836,
					0
				]
			],
			"lastCommittedPoint": [
				56.36982458424836,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 778,
			"versionNonce": 622324547,
			"isDeleted": false,
			"id": "4vJ-4wzH9zphOd1eZDuFa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948966,
			"x": -3391.1981276057104,
			"y": 3986.609102787654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 262.69350174635133,
			"height": 142.22407353997966,
			"seed": 309702083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					197.33305005157013,
					29.455127194990013
				],
				[
					199.1448216890222,
					-14.93327792258323
				],
				[
					262.69350174635133,
					47.18823703340193
				],
				[
					201.86247914520004,
					127.29079561739641
				],
				[
					200.95659332647398,
					65.6905599440295
				],
				[
					2.5675990254836023,
					111.77388967570926
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1671,
			"versionNonce": 1226940013,
			"isDeleted": false,
			"id": "jYnoF_xpbpJ0rjjkq7kwI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3809.4941909956756,
			"y": 4188.817756331973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 1106.7129145027618,
			"height": 633.8805331796278,
			"seed": 2136106627,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "tZv4zL8A",
			"type": "text",
			"x": -3442.437081775387,
			"y": 4200.221837986147,
			"width": 375.4535827636719,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 197888685,
			"version": 150,
			"versionNonce": 169839331,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Detachment Method\nfor explaining Transformers",
			"rawText": "Detachment Method\nfor explaining Transformers",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Detachment Method\nfor explaining Transformers",
			"lineHeight": 1.25
		},
		{
			"id": "RkQQRGHw",
			"type": "text",
			"x": -3784.3170553231894,
			"y": 4283.087278136792,
			"width": 1070.5987548828125,
			"height": 425,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 663493165,
			"version": 1124,
			"versionNonce": 1369262285,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "In order to be able to keep conservation we need to make a few assumptions that will make our model\nless accurate but not completely wrong like in Gradient x input method.\n\nFor both the LayerNorm and the attentionHead, conservation is not met, so lets detach some terms\nfrom them and treat them as weighing constants.\n\nFor the attentionHead we treat the probabilities produced by the softmax as constants, I.e we detach\nthe fact that x' contributes to the output this will in turn destroy the term that contributed to breaking\nthe conservation in our last method and thus we have a simplified versions:\n\n\n\n\n\nSimilarly in the Normalization Layer the model function has 2 paths going through the actual\ninput and a softnorm for normalization, and thus those two terms together wont conserve the contribution\nbut if we detach one of them (The normalization in this case) we can keep conservation.",
			"rawText": "In order to be able to keep conservation we need to make a few assumptions that will make our model\nless accurate but not completely wrong like in Gradient x input method.\n\nFor both the LayerNorm and the attentionHead, conservation is not met, so lets detach some terms\nfrom them and treat them as weighing constants.\n\nFor the attentionHead we treat the probabilities produced by the softmax as constants, I.e we detach\nthe fact that x' contributes to the output this will in turn destroy the term that contributed to breaking\nthe conservation in our last method and thus we have a simplified versions:\n\n\n\n\n\nSimilarly in the Normalization Layer the model function has 2 paths going through the actual\ninput and a softnorm for normalization, and thus those two terms together wont conserve the contribution\nbut if we detach one of them (The normalization in this case) we can keep conservation.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In order to be able to keep conservation we need to make a few assumptions that will make our model\nless accurate but not completely wrong like in Gradient x input method.\n\nFor both the LayerNorm and the attentionHead, conservation is not met, so lets detach some terms\nfrom them and treat them as weighing constants.\n\nFor the attentionHead we treat the probabilities produced by the softmax as constants, I.e we detach\nthe fact that x' contributes to the output this will in turn destroy the term that contributed to breaking\nthe conservation in our last method and thus we have a simplified versions:\n\n\n\n\n\nSimilarly in the Normalization Layer the model function has 2 paths going through the actual\ninput and a softnorm for normalization, and thus those two terms together wont conserve the contribution\nbut if we detach one of them (The normalization in this case) we can keep conservation.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 128,
			"versionNonce": 408041091,
			"isDeleted": false,
			"id": "u74QwgCo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3418.7938035675843,
			"y": 4540.7927384741715,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 353.268736757103,
			"height": 73.45191556335806,
			"seed": 18311,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fae367afebb38dea1f3b121fcdc5a6fd972f70fa",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 1978967853,
			"isDeleted": false,
			"id": "4AlQEY5h",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3449.8982892741906,
			"y": 4718.803357792816,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 419.97758282247617,
			"height": 79.5412088678932,
			"seed": 68253,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6947cf36aff24bcda3e927e5fc45ac08e6f60716",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 737,
			"versionNonce": 242118179,
			"isDeleted": false,
			"id": "FRQWLUj1lHhDsLbTWF3BR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -847.8941223958243,
			"y": 2789.412557139768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 159.3058948393356,
			"height": 200.26725527370854,
			"seed": 2111296077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					-15.106393834414149,
					-131.8822174511655
				],
				[
					37.036283781317174,
					-130.35876970473953
				],
				[
					-42.52671757356255,
					-200.26725527370854
				],
				[
					-122.26961105801843,
					-133.3662531535787
				],
				[
					-70.81470288068923,
					-132.7479325469693
				],
				[
					-78.25662787303548,
					-4.240906033816408
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 847,
			"versionNonce": 680606093,
			"isDeleted": false,
			"id": "cPPitEAY0XK0NDYIWuoll",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1285.894431027256,
			"y": 2278.8420731164533,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 821.5736982092433,
			"height": 304.17667122840805,
			"seed": 374554851,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "pyT89NVJ",
			"type": "text",
			"x": -1034.0013317006824,
			"y": 2299.3923577401642,
			"width": 331.2694091796875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1694489133,
			"version": 132,
			"versionNonce": 1331868099,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Beyond Neural Networks",
			"rawText": "Beyond Neural Networks",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Beyond Neural Networks",
			"lineHeight": 1.25
		},
		{
			"id": "MLGCv0Xn",
			"type": "text",
			"x": -1278.6845351087672,
			"y": 2348.408256795566,
			"width": 793.21923828125,
			"height": 225,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1611597603,
			"version": 638,
			"versionNonce": 1387036653,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "There are many non-neural network algorithms that are still quite popular\nand while they have more theory than neural networks they can still be seen as\nblack boxes due to kernels and other reasons, thus we need a way\nto be able to explain such models\n\n\nLRP method is quite a nice way of explaining contribution, if we can reformulate\nour algorithm such that its \"shaped\" like a neural network then we can\njust apply a normal LRP method and provide explainability",
			"rawText": "There are many non-neural network algorithms that are still quite popular\nand while they have more theory than neural networks they can still be seen as\nblack boxes due to kernels and other reasons, thus we need a way\nto be able to explain such models\n\n\nLRP method is quite a nice way of explaining contribution, if we can reformulate\nour algorithm such that its \"shaped\" like a neural network then we can\njust apply a normal LRP method and provide explainability",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There are many non-neural network algorithms that are still quite popular\nand while they have more theory than neural networks they can still be seen as\nblack boxes due to kernels and other reasons, thus we need a way\nto be able to explain such models\n\n\nLRP method is quite a nice way of explaining contribution, if we can reformulate\nour algorithm such that its \"shaped\" like a neural network then we can\njust apply a normal LRP method and provide explainability",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 769,
			"versionNonce": 1548583267,
			"isDeleted": false,
			"id": "-KF1AAW0bhU4yKAK1DGB1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -840.8968474291917,
			"y": 2203.903357809755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 159.3058948393356,
			"height": 200.26725527370854,
			"seed": 1244854637,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566531073,
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
					-15.106393834414149,
					-131.8822174511655
				],
				[
					37.036283781317174,
					-130.35876970473953
				],
				[
					-42.52671757356255,
					-200.26725527370854
				],
				[
					-122.26961105801843,
					-133.3662531535787
				],
				[
					-70.81470288068923,
					-132.7479325469693
				],
				[
					-78.25662787303548,
					-4.240906033816408
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1100,
			"versionNonce": 2052061773,
			"isDeleted": false,
			"id": "TR0VhzoMaxWdA1frG121y",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1272.6124971798467,
			"y": 1442.2710508513758,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 821.5736982092433,
			"height": 547.8454580040715,
			"seed": 1072562317,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566531073,
			"link": null,
			"locked": false
		},
		{
			"id": "vc4rqLR0",
			"type": "text",
			"x": -1005.821350109899,
			"y": 1458.850911889309,
			"width": 299.5732421875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1999631779,
			"version": 135,
			"versionNonce": 243096835,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Kernel Density Models",
			"rawText": "Kernel Density Models",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernel Density Models",
			"lineHeight": 1.25
		},
		{
			"id": "P0jrbi9E",
			"type": "text",
			"x": -1229.72402748427,
			"y": 1507.6644712113427,
			"width": 733.8192749023438,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 305629027,
			"version": 137,
			"versionNonce": 676669613,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"text": "Kernel density estimation (KDE) and one-class SVMs are non-neural\nnetwork models for density estimation/ anomaly detection. The inlier score\ncan be generically written as a weighted sum of kernel scores:",
			"rawText": "Kernel density estimation (KDE) and one-class SVMs are non-neural\nnetwork models for density estimation/ anomaly detection. The inlier score\ncan be generically written as a weighted sum of kernel scores:",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernel density estimation (KDE) and one-class SVMs are non-neural\nnetwork models for density estimation/ anomaly detection. The inlier score\ncan be generically written as a weighted sum of kernel scores:",
			"lineHeight": 1.25
		},
		{
			"id": "lU4q_9dzC2NqzOW6KJu05",
			"type": "image",
			"x": -1030.192735252031,
			"y": 1593.8892471006652,
			"width": 336.9148693684644,
			"height": 86.84916632609304,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1642030477,
			"version": 265,
			"versionNonce": 292603043,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531073,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7aee6d037c3fd862cf0f37470c4c4f3135d8809a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "3Su8AHFfMXW8cEEVc2Sgx",
			"type": "rectangle",
			"x": -1031.8743633848808,
			"y": 1593.0791349794697,
			"width": 336.13848906927296,
			"height": 86.15314215641024,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1469261901,
			"version": 183,
			"versionNonce": 241535757,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531074,
			"link": null,
			"locked": false
		},
		{
			"id": "NLnwcqIf",
			"type": "text",
			"x": -1246.1655751758144,
			"y": 1689.8248765813403,
			"width": 757.6591796875,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 505057059,
			"version": 440,
			"versionNonce": 483801155,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531074,
			"link": null,
			"locked": false,
			"text": "The anomaly score can then be seen as the negative log of this score\n\nIf we view the inner-exp values as a weighted sum of inputs + bias and the\nexponential function as an activation we can easily neuralize this\nformula while keeping it the same.",
			"rawText": "The anomaly score can then be seen as the negative log of this score\n\nIf we view the inner-exp values as a weighted sum of inputs + bias and the\nexponential function as an activation we can easily neuralize this\nformula while keeping it the same.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The anomaly score can then be seen as the negative log of this score\n\nIf we view the inner-exp values as a weighted sum of inputs + bias and the\nexponential function as an activation we can easily neuralize this\nformula while keeping it the same.",
			"lineHeight": 1.25
		},
		{
			"id": "-Z75mmscQ60tsfZevVTdo",
			"type": "image",
			"x": -1002.7514984063474,
			"y": 1829.3123057956163,
			"width": 281.81904857004685,
			"height": 111.70547780108073,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 70811853,
			"version": 130,
			"versionNonce": 1828364653,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531074,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e4d8c787bdfe24077481bf55046a06d1ee817966",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HTCzsPpWJDocMdlH3IRTv",
			"type": "rectangle",
			"x": -1005.4559024943908,
			"y": 1830.4399022878338,
			"width": 287.22785674613294,
			"height": 110.99652769172603,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1631335053,
			"version": 118,
			"versionNonce": 1854683107,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566531074,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 671,
			"versionNonce": 200533443,
			"isDeleted": false,
			"id": "caKtoQvX_l9p_FWEovm2_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1331.6954305964377,
			"y": 2370.1554735652307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 147.56793348736585,
			"height": 100.88828105768889,
			"seed": 1482549763,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566538887,
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
					-109.1701548758574,
					16.563747636336963
				],
				[
					-109.923052495691,
					-18.069542876003965
				],
				[
					-144.55634300803183,
					32.37459765284036
				],
				[
					-106.15856439652327,
					82.81873818168492
				],
				[
					-106.15856439652339,
					47.555580012944056
				],
				[
					3.011590479334025,
					63.24340006601395
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1191,
			"versionNonce": 1670827299,
			"isDeleted": false,
			"id": "U9aaOpj-3wO_kFfVdmT0U",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2383.3794599187745,
			"y": 2143.388355651864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 821.5736982092433,
			"height": 547.8454580040715,
			"seed": 420669795,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716566660830,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 1266053379,
			"isDeleted": false,
			"id": "CaZIpnoV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2092.606211408397,
			"y": 2159.968216689797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 251.60903930664062,
			"height": 35,
			"seed": 1582679299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566580750,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "K-means clustering",
			"rawText": "K-means clustering",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "K-means clustering",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 229,
			"versionNonce": 254579395,
			"isDeleted": false,
			"id": "h81T6eeF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2332.320946277885,
			"y": 2208.7817760118305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 717.4791870117188,
			"height": 50,
			"seed": 435956899,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566595539,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assign cluster membership of x according to the distance of the closest\ncluster centroid mu",
			"rawText": "Assign cluster membership of x according to the distance of the closest\ncluster centroid mu",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assign cluster membership of x according to the distance of the closest\ncluster centroid mu",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 683,
			"versionNonce": 664836803,
			"isDeleted": false,
			"id": "GdroUZzs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2337.972546459664,
			"y": 2390.942181381828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 719.7391967773438,
			"height": 75,
			"seed": 285584259,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566685627,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can also Neuralize this by assuming that the minimization function\nis the activation and reformulate the rest to be in the form of weights\nand biases",
			"rawText": "We can also Neuralize this by assuming that the minimization function\nis the activation and reformulate the rest to be in the form of weights\nand biases",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can also Neuralize this by assuming that the minimization function\nis the activation and reformulate the rest to be in the form of weights\nand biases",
			"lineHeight": 1.25
		},
		{
			"id": "Jg9k8i6N7SUHYHGcErDLi",
			"type": "image",
			"x": -2180.3861320452343,
			"y": 2272.503357209963,
			"width": 450,
			"height": 73,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1326020835,
			"version": 37,
			"versionNonce": 282949709,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566608201,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a81e636ec8658f329103254580d93cbdb6aa354b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 360,
			"versionNonce": 1393230701,
			"isDeleted": false,
			"id": "RIfT-vXwQJqe3DCgWV0QL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2179.6182369526264,
			"y": 2274.680847953637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 449.12349437954987,
			"height": 69.71895956582445,
			"seed": 157130723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716566622928,
			"link": null,
			"locked": false
		},
		{
			"id": "9fZ8ShRqmZl1slBZUyimX",
			"type": "image",
			"x": -2095.4831331072896,
			"y": 2469.7793657064044,
			"width": 235,
			"height": 40,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2098529795,
			"version": 78,
			"versionNonce": 1891353837,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566702340,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1e8381e0c09e174a47abfeb6e5e315baf68a20b8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Sd1LQ5Y1iUE1Zc2MLVXCU",
			"type": "image",
			"x": -2096.655512699274,
			"y": 2509.114632596812,
			"width": 236.17237969927487,
			"height": 44.86428718301637,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1395017709,
			"version": 315,
			"versionNonce": 2110786413,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566764332,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "83d5ca4515803a960b59574b19435bcd7967ae16",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "SymO0YvDAgDXj3b5SUeLa",
			"type": "image",
			"x": -2093.793367052932,
			"y": 2553.9789198083527,
			"width": 230.44808834601605,
			"height": 122.42554693382102,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1005699725,
			"version": 138,
			"versionNonce": 63771405,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566778971,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1e94bb3264acbbe609d3e45205ef117391874585",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Z4RsAr6zZUWVfLuH7UcDO",
			"type": "rectangle",
			"x": -2096.8857719804955,
			"y": 2467.9755738658096,
			"width": 235.6483195544015,
			"height": 207.51120677178596,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1871434531,
			"version": 53,
			"versionNonce": 306924355,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716566789689,
			"link": null,
			"locked": false
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#fdf8f6",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 3463.1280472137855,
		"scrollY": -1334.513071598261,
		"zoom": {
			"value": 0.41117452906201846
		},
		"currentItemRoundness": "sharp",
		"gridSize": null,
		"gridColor": {
			"Bold": "#EAB49EFF",
			"Regular": "#F7E1D9FF"
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