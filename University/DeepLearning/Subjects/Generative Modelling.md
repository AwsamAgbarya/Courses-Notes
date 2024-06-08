---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Generative ^g8ShhcXe

Modelling ^2nxJ0dn9

Unlike Traditional Machine learning models
Generative Models do not produce a conditional
probability but instead produce the joint probability of
our latent representation further allowing us to sample
from it and to estimate probabilities for a given sample ^MnA1mhFI

Implicit Likelihood
models ^3f3yTsna

Explicit Likelihood
models ^FHamFapj

the likelihood of data samples is
only used indirectly
gives direct access to an approximation of
the likelihood and
often generate more diverse examples
Example:
Generative Adversarial Networks
and diffusion models ^bLbyvSfV

the likelihood of data samples
is modelled directly.
tends to generate higher quality data
points of more complicated distributions
Example:
Auto-regressive models, Variational
auto encoders and Normalizing flows
 ^xc8nvuMJ

Auto-regressive Models ^mdmXaYIo

These models model the probability distribution by making
use of the chain rule for probability densities: ^TbRMe3QO

This chain conditional dependency is often fitted to the
data by fitting neural networks to model the conditional
densities similar to discriminative machine learning.
Which is very slow in training and inference but produces good
estimates. ^yRdNQiLz

Examples: ^QtJlhWCZ

PixelCNN ^UETXSD8S

A CNN based Generative model that generates pixels according to the
previously generated pixels. This is done by masking a filter over the pixels
to only take in the previous pixels. ^VrvGjhXo

PixelCNNs have a blind spot
in the receptive field that can not be used
to make prediction ^wVPkAhh0

Two convolutional stacks (blue and purple)
allow to capture the whole receptive field ^OZFe65Yr

Generative Pre-Trained Transformer
(GPT) ^SiE3CIFt

A model based on transformer architecture
with self attention heads, trained on large amount of self-
supervised data in an auto-regressive manner (given the previous words
generate the most likely upcoming word) ^iYyAP5ej

Vartional Auto-Encoder ^PUGt8dXh

Before we explain this we need to detour real quick
to Bayesian Inference ^gfAQoLV7

Let Z be a latent variable, P(Z ) the distribution of it
Let X be an observation and P(X ) be the distribution over it
Using Bayes theorem we can infer that ^gccK7tRD

So if P(X|z) and P(z) are known or learnt we can uncover the probability
of a realization z given an observation X
Problem:
P(X|z) is generally intractable

Solutions?

1) Monte Carlo estimation:
sample from the distributions and approximate the integral

2) Variational Inference:
 approximate the intractable posterior distribution P(z|X )
with a tractable distribution Q(z|X ) by minimizing the KL divergence
between them. ^1ymxKjgR

The KL-divergence can be simplified to this form ^KA5Ifigo

We dont really know
This term
but can approximate it with
Evidence lower bound ^CCwcksB6

a tractable 
approximation of
the posterior ^EmPZbbCm

+ ^WWyhZ65O

a tractable
lower bound
approximation of
P(x) ^HOnkWzcW

Variational Auto-encoder ^hX4RgScC

We want to be able to:
▶ sample from the dataset distribution P(X)
▶ calculate datapoint posteriors P(z|X)
▶ find a latent representation Z given a dataset. ^7fnWu53G

To do this we need to calculate the following:
P(z) which can be random and only include prior info about the problem
Note that we want to be able to sample easily from our choice of P(z)
Usually Isotropic Multi-dimensional Gaussian

P(X |z) which is seen as the decoder here, modelled as a Neural network

Q(z|X) which is seen as the encoder here, modelled as a Neural network ^QdwAW89s

Generative models usually fail at Outlier detection even tho
they try to estimate the evidence distribution.
This is because The
lowest latent variables in a generative model learn generic
low-level features that can describe a wide range of data
which are quite similar across models (edge detectors)
and  do not carry much information for OOD detection.
yet theyre seen as features that would suggest that it is
part of the distribution that we have. ^ghifQPuc

So in order to make OOD detection we need to not rely on the information
given by the lower latent vairables as much
More on the methods in the paper
Hierarchical VAEs Know What They Don’t Know ^WIMWk5mW

Normalizing Flows ^bKJiqpmv

Very similar to the encoder-decoder Architecture
except the functions are the inverse of each other ^qyp0Ec6c

Since encoder and decoder are perfectly invertible
no reconstruction loss has to be minimized. ^u8j8Wq90

Motivation:
We want to learn the distribution of our data, such distribution
is extremely complex to the point of even if we learned it we wouldnt
be able to sample from it, so what if we learn a simple sampleable distirbution
and learn how to convert bijectively from our simple distribution to the real complex one? ^ke76VHSf

Each transformation must be invertible and differentiable, but can be a learned neural network. ^hc5CId2U

an important note here is all the step by step transformations we do to our
simple distribution have to be invertible in order to ensure bijectiveness.

another note is that we allow those transformations to perform affine transformations
on our distribution (which includes scaling), but because we want to keep the rule of change of Variables
(i.e we want our distribution to sum up to 1) We have to divide by the determinant of the inverse jacobian of
this particular transformation ^aKaXDFoa

Jacobian tells us how the function
moves given a certain input

determinant of a matrix gives us
the change of scale of the output
linear space

dividing by the determinant of the jacobian
ensure we dont expand beyond 1 ^WEf0SKxQ

must be tractable
to ensure ^zmyR9ZUT

exact log
likelihood
evaluation ^UA1Rd1sk

In Order to ensure that the determinant of our
Jacobian is tractable we can try to set up our architecture
such that our jacobian is triangluar, because for any triangular matrix
its determinant is just the main diagonal ^CkJs0kSi

This is achieve by the design of coupling layers ^i1QfcNut

z1:d ^5vqo4kUo

zd+1:n ^dTL011gn

y1:d ^XB2H86hO

Id ^thBwUiAO

m ^lZo7L3Nk

g ^MKHs9WPG

yd+1:n ^TDZ3RHcI

= ^3BU7Q1aN

J= ^nlOx3Kfz

0 ^tylC7Igz

because zd+1:n
doesnt contribute
to y1:d ^l5q7jqmH

Id ^m3BioOUu

because z1:d
goes through no
transformations
to y1:d ^xY9coyhm

need to make sure
this is lower triangular to make
sure the Jacobian is
lower triangular ^vqnSFw57

What about inveritbility?
The identity is already invertible
y1:d is recoverable
we need to make sure that g is invertible! ^CdRktSnc

Example of a coupling layer
S-T-layer ^e42gu7jH

learned
neural networks ^PikIZTYC

seperation of
latent data is
done through masking
or in an autoregressive
manner ^2w9mZMWI

Can be used to generate counterfactual explanations!

I.e if we take one class and tell it what information is required
to be altered for that sample to be classified as another class we 
would get proper explanations.

This method has been done before through adversarial attacks, the issue
with adversarial attacks is they do not learn the true distribution of the data
manifold thus the "adversarial attack" they preform to make our sample
generate a different class is usually a bunch of meticulous noise.
whereas in generative models like this, the model only samples changes from the data manifold
itself ^dkdMwt9C

generative model
changing 4 to 9 ^omvgjGT9

normal MLP
changing 4 to 9 ^p7Ih1mDb

# Embedded files
3dd757a87e5824caf60941dffa78316dfcdcfdd1: $$p_{\theta}(x) = p_{\theta}(f^{-1}(x)) |det(\frac{\partial f^{-1}(x)}{\partial x}) |$$
e5f6a8d7bad602d6b91abd9c003cadb918363958: $$p_{\theta}(x) = p_{\theta}(z) |det(\frac{\partial z}{\partial x}) |$$
91b7248cc1c5ef87f7ba0032aff56526e4200c45: $$log p_{\theta}(x) = log p_{\theta}(z) + \sum_i log|det(\frac{\partial f_i^{-1}}{\partial x}) |$$
07e267c8f693e6113e9b22221a824d8c83124af3: $$\frac{\partial y_{d+1:n} }{\partial z_{1:d}}$$
4653f84054ebcc204e89e476666dce1da79d8e23: $$\frac{\partial y_{d+1:n} }{\partial z_{d+1:n}}$$
3589ead6f7fea11b71f11e3574df36e01678fe10: [[Pasted Image 20240601175157_254.png]]
413b35f55ff0bb46f4feabec37a6e06ae351029e: [[Pasted Image 20240601180303_371.png]]
0f1da85a77840fcdd5b669cad7f33d3ff7fa0ae3: [[Pasted Image 20240601181003_420.png]]
d4bacc8e3cddeeabe52a8eb15d2541458b878f24: [[Pasted Image 20240601181020_432.png]]
b82a8a9ff0075a10d23a08e3b18e0595a14b1cf1: [[Pasted Image 20240601181435_472.png]]
6c57605868bd4fb54ff2f5e381b0a406e99ce174: [[Pasted Image 20240601181701_500.png]]
f5b6f7ecda3937c0dd135ff4c1169b0df98d80c0: [[Pasted Image 20240601182623_599.png]]
5b03706b66bb93ef7a6458fc67c7837a7bfb074d: [[Pasted Image 20240601183428_744.png]]
3f1ac6e1d987f9f1f277b7d10ff93dca1c1bd519: [[Pasted Image 20240601190752_907.png]]
2b32e7f50caa321735315b985323f40c7f9bf69d: [[Pasted Image 20240601192354_019.png]]
4c1637c1a34c2cfedc8fb7374c5558e7086a4b6a: [[Pasted Image 20240601192909_175.png]]
91f2ee018d383cf8c8a97ea084faceef8701b77e: [[Pasted Image 20240601193126_208.png]]
25b10389db2e63805bd4c4f11cb89622e7c6a20b: [[Pasted Image 20240601194918_283.png]]
8fbb3c27deba2407893ac028deb69fed9fdf9cd0: [[Pasted Image 20240601200218_798.png]]
a486d3b25ed5f4c21faadcf8746642416896886b: [[Pasted Image 20240601200842_966.png]]

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
			"version": 156,
			"versionNonce": 1342807040,
			"isDeleted": false,
			"id": "ZCEO4lE8ScZ-SbbkDx9Uj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 224.84443292465517,
			"y": -500.7152932396347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 189.53409147358877,
			"height": 77.49423444486635,
			"seed": 1164483584,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 204,
			"versionNonce": 1139680256,
			"isDeleted": false,
			"id": "WuiGVOynN1C0x2qjWZxAp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.46364760900080615,
			"x": -128.0811167158205,
			"y": -720.1266799208829,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 470230016,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 215,
			"versionNonce": 1417026560,
			"isDeleted": false,
			"id": "16wdI_70Py0U3Y0ClLbsS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.46364760900080615,
			"x": -65.52552987478383,
			"y": -750.0039751285422,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 198515712,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 249,
			"versionNonce": 1787405312,
			"isDeleted": false,
			"id": "NcBXBSZHPW2kLKfMdr3LL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -127.14745124058118,
			"y": -777.0802739104834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 1983781888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 224,
			"versionNonce": 391289856,
			"isDeleted": false,
			"id": "6ehZJSUF3jBBfAjKpgZCf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.46364760900080615,
			"x": -8.571935885183251,
			"y": -751.8713060790208,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 442964992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 235,
			"versionNonce": 833954816,
			"isDeleted": false,
			"id": "GVWbaaiKfSr0jctFe1pxi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.6593100683328581,
			"x": -1.1026120832684398,
			"y": -694.9177120894203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 139467776,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 240,
			"versionNonce": 1251941376,
			"isDeleted": false,
			"id": "E-tvAcHYISbC7WJ27ICHm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.9380474917927133,
			"x": -72.06118820145932,
			"y": -676.2444025846332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 1341725696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 276,
			"versionNonce": 124822528,
			"isDeleted": false,
			"id": "9y6EcgudJtI7iPe7454dG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -59.92353702334772,
			"y": -548.3322324768417,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 245.55401998795003,
			"height": 108.30519512776502,
			"seed": 904537088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-58.82092494007928,
					-105.50419870204696
				],
				[
					186.73309504787073,
					-104.57053322680761
				],
				[
					113.90718797920114,
					2.800996425718061
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 214,
			"versionNonce": 1616616448,
			"isDeleted": false,
			"id": "EFYOcFGrqLi5Ghg1PE4BV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -107.60829356167147,
			"y": -548.71369817608,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 384.63637107374393,
			"height": 174.83471412442907,
			"seed": 1661934592,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 215,
			"versionNonce": 431760384,
			"isDeleted": false,
			"id": "FiBdvJjl66gJBfnIhtjya",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -82.354390410365,
			"y": -512.451683394717,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 229.22773629647364,
			"height": 69.93388564977158,
			"seed": 1146987520,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 228,
			"versionNonce": 176692224,
			"isDeleted": false,
			"id": "9zzInRXQJOjX3y-txX9VV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 6.358038608326723,
			"y": -583.0331050227271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 157.99877869022475,
			"height": 157.9987786902248,
			"seed": 796861440,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 134,
			"versionNonce": 1452778496,
			"isDeleted": false,
			"id": "4Tu2kQWgo5G9pnYC5d1e9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 227.81534316593678,
			"y": -530.5826907853984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 24.606367173067827,
			"height": 21.368687281874685,
			"seed": 1039934464,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 152,
			"versionNonce": 992254976,
			"isDeleted": false,
			"id": "u2ISKlzjjhLByor4sMvNK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 228.46287914417542,
			"y": -488.8166201890072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 24.606367173067827,
			"height": 21.368687281874685,
			"seed": 1757813760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 163,
			"versionNonce": 1812145152,
			"isDeleted": false,
			"id": "hoL4Ej5ybszAMe08jyLPz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 228.46287914417542,
			"y": -442.8415657340647,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 24.606367173067827,
			"height": 21.368687281874685,
			"seed": 993467392,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 190,
			"versionNonce": 607198208,
			"isDeleted": false,
			"id": "attLeyd7lToN-8n8lWIPJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -87.53467823627398,
			"y": -200.33934188369923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#343a40",
			"width": 67.3437417368171,
			"height": 62.810989889146754,
			"seed": 1858249728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9426079347158949,
					-60.220845976192265
				],
				[
					67.3437417368171,
					-58.925774019714964
				],
				[
					44.679982498465215,
					2.5901439129544914
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 208,
			"versionNonce": 1207870464,
			"isDeleted": false,
			"id": "cuLW0cer9pcAOH1OYJ1OA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -107.60829356167142,
			"y": -403.0181030723892,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 383.98883509550524,
			"height": 144.4005231472136,
			"seed": 482059264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 143,
			"versionNonce": 934124544,
			"isDeleted": false,
			"id": "Li0pgJRM7waTPVlcyuGz4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 140.8691118994338,
			"y": -373.414702132946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 110.32159968325645,
			"height": 1.212325271244588,
			"seed": 1747459072,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					110.32159968325645,
					1.212325271244588
				]
			]
		},
		{
			"type": "line",
			"version": 163,
			"versionNonce": 411706368,
			"isDeleted": false,
			"id": "l3LRnvcLq34agk80E9H30",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 143.18642449190145,
			"y": -347.6844277885813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 110.32159968325645,
			"height": 1.212325271244588,
			"seed": 803052544,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					110.32159968325645,
					1.212325271244588
				]
			]
		},
		{
			"type": "rectangle",
			"version": 179,
			"versionNonce": 664411136,
			"isDeleted": false,
			"id": "oDc0dsX3Y7bYdH3b4RRNc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -85.59207030155808,
			"y": -373.878984051651,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 204.62136912340577,
			"height": 31.081726955454002,
			"seed": 1613863936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 220,
			"versionNonce": 1269146624,
			"isDeleted": false,
			"id": "2odHo_lfgT4MGb_lECKTw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -85.59207030155808,
			"y": -318.19088992312913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 204.62136912340577,
			"height": 31.081726955454002,
			"seed": 248488960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 251,
			"versionNonce": 1710660608,
			"isDeleted": false,
			"id": "mrQmIQl5D6z8X5yf27fRP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 140.8691118994339,
			"y": -330.98331763938586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#343a40",
			"width": 132.1434545656589,
			"height": 134.56810510814822,
			"seed": 1088431104,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 309,
			"versionNonce": 256975872,
			"isDeleted": false,
			"id": "3PGEWexAPqSGeWEW_buBc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 170.57108104492613,
			"y": -300.06902322264904,
			"strokeColor": "#ced4da",
			"backgroundColor": "#ced4da",
			"width": 75.16416681716372,
			"height": 72.73951627467476,
			"seed": 739908608,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 351,
			"versionNonce": 616766464,
			"isDeleted": false,
			"id": "5qJqpJVb-_anxyeF9aSsC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 101.60059019306047,
			"y": -567.0055419816288,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 56.95359398960057,
			"height": 125.11117368207339,
			"seed": 36445184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-44.81594281148897,
					51.35160113816445
				],
				[
					-17.73964402954772,
					72.82590706866958
				],
				[
					-42.948611861010264,
					125.11117368207339
				],
				[
					12.137651178111597,
					58.82092494007928
				],
				[
					-19.606974980026425,
					45.749608286728325
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 162,
			"versionNonce": 1368171520,
			"isDeleted": false,
			"id": "jpDjDX8nAa0-mdoXA9MdH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 355.55759945816465,
			"y": -500.7152932396347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 56.953593989600556,
			"height": 74.69323801914828,
			"seed": 1773544448,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 461,
			"versionNonce": 1442814976,
			"isDeleted": false,
			"id": "B7ER55mD1V6c2doHwG3E2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 363.02692326007946,
			"y": -485.77664563580504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 59.75459041531863,
			"height": 54.15259756388251,
			"seed": 1331207168,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 1079518208,
			"isDeleted": false,
			"id": "g8ShhcXe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -59.589597720577956,
			"y": -375.53043504048617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 148.42861938476562,
			"height": 35,
			"seed": 919804928,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Generative",
			"rawText": "Generative",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generative",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 732699648,
			"isDeleted": false,
			"id": "2nxJ0dn9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -43.957355327411676,
			"y": -320.3788795988765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 116.1724853515625,
			"height": 35,
			"seed": 958702592,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Modelling",
			"rawText": "Modelling",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Modelling",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 360,
			"versionNonce": 1236509696,
			"isDeleted": false,
			"id": "MnA1mhFI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -193.47938897921665,
			"y": -169.69662368410133,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 555.3993530273438,
			"height": 125,
			"seed": 636036096,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mTFTMm06BdXaP5oQbF74G",
					"type": "arrow"
				},
				{
					"id": "CyEjfGkbVZOLu7-gmDGmE",
					"type": "arrow"
				}
			],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Unlike Traditional Machine learning models\nGenerative Models do not produce a conditional\nprobability but instead produce the joint probability of\nour latent representation further allowing us to sample\nfrom it and to estimate probabilities for a given sample",
			"rawText": "Unlike Traditional Machine learning models\nGenerative Models do not produce a conditional\nprobability but instead produce the joint probability of\nour latent representation further allowing us to sample\nfrom it and to estimate probabilities for a given sample",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Unlike Traditional Machine learning models\nGenerative Models do not produce a conditional\nprobability but instead produce the joint probability of\nour latent representation further allowing us to sample\nfrom it and to estimate probabilities for a given sample",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 129,
			"versionNonce": 399023104,
			"isDeleted": false,
			"id": "mTFTMm06BdXaP5oQbF74G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 63.69772604010001,
			"y": -27.764005579263483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 276.66618729961317,
			"height": 164.43446197342877,
			"seed": 1602626560,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MnA1mhFI",
				"focus": 0.07390200000231131,
				"gap": 16.932618104837843
			},
			"endBinding": {
				"elementId": "3f3yTsna",
				"focus": -0.1364949660872972,
				"gap": 11.15531089716626
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
					87.50605871100595
				],
				[
					-249.05570556209392,
					85.58284862944538
				],
				[
					-276.66618729961317,
					164.43446197342877
				]
			]
		},
		{
			"type": "arrow",
			"version": 186,
			"versionNonce": 463414272,
			"isDeleted": false,
			"id": "CyEjfGkbVZOLu7-gmDGmE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 61.018261722361565,
			"y": -26.271913919497294,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 276.69075998119376,
			"height": 164.43446197342877,
			"seed": 465511424,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MnA1mhFI",
				"focus": 0.08355078444231236,
				"gap": 18.42470976460403
			},
			"endBinding": {
				"elementId": "FHamFapj",
				"focus": 0.11774441369061317,
				"gap": 1.0105049306650926
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
					87.50605871100595
				],
				[
					249.05570556209392,
					85.58284862944538
				],
				[
					276.69075998119376,
					164.43446197342877
				]
			]
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 1280646144,
			"isDeleted": false,
			"id": "3f3yTsna",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -329.53781495167493,
			"y": 147.82576729133154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 236.43299865722656,
			"height": 70,
			"seed": 1731271680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mTFTMm06BdXaP5oQbF74G",
					"type": "arrow"
				}
			],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Implicit Likelihood\nmodels",
			"rawText": "Implicit Likelihood\nmodels",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Implicit Likelihood\nmodels",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 605725696,
			"isDeleted": false,
			"id": "FHamFapj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 215.84184412217172,
			"y": 139.17305298459655,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 238.0570068359375,
			"height": 70,
			"seed": 2726912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CyEjfGkbVZOLu7-gmDGmE",
					"type": "arrow"
				}
			],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Explicit Likelihood\nmodels",
			"rawText": "Explicit Likelihood\nmodels",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Explicit Likelihood\nmodels",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 995204096,
			"isDeleted": false,
			"id": "bLbyvSfV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -427.6044663294291,
			"y": 217.85687671239202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 425.69952392578125,
			"height": 200,
			"seed": 1466833920,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "the likelihood of data samples is\nonly used indirectly\ngives direct access to an approximation of\nthe likelihood and\noften generate more diverse examples\nExample:\nGenerative Adversarial Networks\nand diffusion models",
			"rawText": "the likelihood of data samples is\nonly used indirectly\ngives direct access to an approximation of\nthe likelihood and\noften generate more diverse examples\nExample:\nGenerative Adversarial Networks\nand diffusion models",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the likelihood of data samples is\nonly used indirectly\ngives direct access to an approximation of\nthe likelihood and\noften generate more diverse examples\nExample:\nGenerative Adversarial Networks\nand diffusion models",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 287712256,
			"isDeleted": false,
			"id": "xc8nvuMJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 134.74002003631134,
			"y": 210.9476897906749,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 390.5595397949219,
			"height": 200,
			"seed": 1997446144,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "the likelihood of data samples\nis modelled directly.\ntends to generate higher quality data\npoints of more complicated distributions\nExample:\nAuto-regressive models, Variational\nauto encoders and Normalizing flows\n",
			"rawText": "the likelihood of data samples\nis modelled directly.\ntends to generate higher quality data\npoints of more complicated distributions\nExample:\nAuto-regressive models, Variational\nauto encoders and Normalizing flows\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the likelihood of data samples\nis modelled directly.\ntends to generate higher quality data\npoints of more complicated distributions\nExample:\nAuto-regressive models, Variational\nauto encoders and Normalizing flows\n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 31,
			"versionNonce": 381557760,
			"isDeleted": false,
			"id": "mdmXaYIo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 378.0908654166294,
			"y": 596.701664857002,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 317.12933349609375,
			"height": 35,
			"seed": 1542495232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Auto-regressive Models",
			"rawText": "Auto-regressive Models",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Auto-regressive Models",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 1354867712,
			"isDeleted": false,
			"id": "TbRMe3QO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 259.3101729924615,
			"y": 637.113385063862,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 559.7593383789062,
			"height": 50,
			"seed": 1678580736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "These models model the probability distribution by making\nuse of the chain rule for probability densities:",
			"rawText": "These models model the probability distribution by making\nuse of the chain rule for probability densities:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "These models model the probability distribution by making\nuse of the chain rule for probability densities:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 154,
			"versionNonce": 1352309760,
			"isDeleted": false,
			"id": "0qcPl16oH2Yj4tJTV1WH9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 241.75287313017986,
			"y": 695.4692956793272,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 584.5885902413547,
			"height": 29.853642027181532,
			"seed": 1016929280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3589ead6f7fea11b71f11e3574df36e01678fe10",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 183,
			"versionNonce": 283976704,
			"isDeleted": false,
			"id": "yRdNQiLz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 230.5841771278387,
			"y": 727.5253205454594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 606.3193359375,
			"height": 125,
			"seed": 1152523264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977417,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This chain conditional dependency is often fitted to the\ndata by fitting neural networks to model the conditional\ndensities similar to discriminative machine learning.\nWhich is very slow in training and inference but produces good\nestimates.",
			"rawText": "This chain conditional dependency is often fitted to the\ndata by fitting neural networks to model the conditional\ndensities similar to discriminative machine learning.\nWhich is very slow in training and inference but produces good\nestimates.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This chain conditional dependency is often fitted to the\ndata by fitting neural networks to model the conditional\ndensities similar to discriminative machine learning.\nWhich is very slow in training and inference but produces good\nestimates.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 451353600,
			"isDeleted": false,
			"id": "QtJlhWCZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 487.4352549796829,
			"y": 870.6123537254076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 92.47988891601562,
			"height": 25,
			"seed": 55518208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Examples:",
			"rawText": "Examples:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Examples:",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1068016640,
			"isDeleted": false,
			"id": "UETXSD8S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 473.5394680376164,
			"y": 898.2126836850108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 117.15248107910156,
			"height": 35,
			"seed": 736404480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "PixelCNN",
			"rawText": "PixelCNN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PixelCNN",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 236,
			"versionNonce": 1738775552,
			"isDeleted": false,
			"id": "VrvGjhXo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 161.7873068814847,
			"y": 932.8008467549978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 745.3392333984375,
			"height": 75,
			"seed": 191800320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A CNN based Generative model that generates pixels according to the\npreviously generated pixels. This is done by masking a filter over the pixels\nto only take in the previous pixels.",
			"rawText": "A CNN based Generative model that generates pixels according to the\npreviously generated pixels. This is done by masking a filter over the pixels\nto only take in the previous pixels.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A CNN based Generative model that generates pixels according to the\npreviously generated pixels. This is done by masking a filter over the pixels\nto only take in the previous pixels.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 105,
			"versionNonce": 183772160,
			"isDeleted": false,
			"id": "BGZc8-KOBLHy-eIt1Luez",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 320.54534493673117,
			"y": 1021.2848151247258,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 427.82315804460035,
			"height": 139.4685557147492,
			"seed": 1511693312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "413b35f55ff0bb46f4feabec37a6e06ae351029e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 71,
			"versionNonce": 1758469120,
			"isDeleted": false,
			"id": "xkFt_VGQZitlyCYPMq5dj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 720.6921523064279,
			"y": 1049.1678745855372,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 93.86997530526855,
			"height": 20.06381151563005,
			"seed": 1748704256,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "wVPkAhh0",
				"focus": 0.08309861741403435,
				"gap": 8.404940947788077
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
					54.10063462250207,
					-7.165646969868021
				],
				[
					93.86997530526855,
					12.898164545762029
				]
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 1624220672,
			"isDeleted": false,
			"id": "wVPkAhh0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 742.8870810637302,
			"y": 1070.4709800790874,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 230.25340270996094,
			"height": 40.10609458206207,
			"seed": 1896752128,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xkFt_VGQZitlyCYPMq5dj",
					"type": "arrow"
				}
			],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 10.694958555216553,
			"fontFamily": 1,
			"text": "PixelCNNs have a blind spot\nin the receptive field that can not be used\nto make prediction",
			"rawText": "PixelCNNs have a blind spot\nin the receptive field that can not be used\nto make prediction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PixelCNNs have a blind spot\nin the receptive field that can not be used\nto make prediction",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 185,
			"versionNonce": 275553280,
			"isDeleted": false,
			"id": "YaNjAg_7QQ5pBGz5DIzzV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 662.3123651613823,
			"y": 1139.2304179005678,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 118.3026008677632,
			"height": 33.18341266705875,
			"seed": 2097652736,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "OZFe65Yr",
				"focus": -0.7965271982569019,
				"gap": 3.268379600613798
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
					31.77733585913245,
					33.18341266705875
				],
				[
					118.3026008677632,
					31.551233408957387
				]
			]
		},
		{
			"type": "text",
			"version": 202,
			"versionNonce": 1866146816,
			"isDeleted": false,
			"id": "OZFe65Yr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 783.678712010206,
			"y": 1143.361385315839,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 221.29705810546875,
			"height": 26.281948912533302,
			"seed": 973839360,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YaNjAg_7QQ5pBGz5DIzzV",
					"type": "arrow"
				}
			],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 10.512779565013322,
			"fontFamily": 1,
			"text": "Two convolutional stacks (blue and purple)\nallow to capture the whole receptive field",
			"rawText": "Two convolutional stacks (blue and purple)\nallow to capture the whole receptive field",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Two convolutional stacks (blue and purple)\nallow to capture the whole receptive field",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 276372480,
			"isDeleted": false,
			"id": "SiE3CIFt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 281.8398589128585,
			"y": 1202.6985134932256,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 505.234130859375,
			"height": 70,
			"seed": 1319214080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Generative Pre-Trained Transformer\n(GPT)",
			"rawText": "Generative Pre-Trained Transformer\n(GPT)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generative Pre-Trained Transformer\n(GPT)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 270,
			"versionNonce": 607560704,
			"isDeleted": false,
			"id": "iYyAP5ej",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 178.32090211017726,
			"y": 1280.43178949059,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 708.71923828125,
			"height": 100,
			"seed": 1405164544,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A model based on transformer architecture\nwith self attention heads, trained on large amount of self-\nsupervised data in an auto-regressive manner (given the previous words\ngenerate the most likely upcoming word)",
			"rawText": "A model based on transformer architecture\nwith self attention heads, trained on large amount of self-\nsupervised data in an auto-regressive manner (given the previous words\ngenerate the most likely upcoming word)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A model based on transformer architecture\nwith self attention heads, trained on large amount of self-\nsupervised data in an auto-regressive manner (given the previous words\ngenerate the most likely upcoming word)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 1321575424,
			"isDeleted": false,
			"id": "PUGt8dXh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1303.9157447720497,
			"y": 581.952482433021,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 317.6893310546875,
			"height": 35,
			"seed": 1241783296,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Vartional Auto-Encoder",
			"rawText": "Vartional Auto-Encoder",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vartional Auto-Encoder",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 779166720,
			"isDeleted": false,
			"id": "gfAQoLV7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1202.2555429272,
			"y": 618.5060764627751,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 517.0593872070312,
			"height": 50,
			"seed": 2104861696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Before we explain this we need to detour real quick\nto Bayesian Inference",
			"rawText": "Before we explain this we need to detour real quick\nto Bayesian Inference",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Before we explain this we need to detour real quick\nto Bayesian Inference",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 212640768,
			"isDeleted": false,
			"id": "gccK7tRD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1156.1481907546588,
			"y": 675.4846024307147,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 614.2993774414062,
			"height": 75,
			"seed": 2142247936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Let Z be a latent variable, P(Z ) the distribution of it\nLet X be an observation and P(X ) be the distribution over it\nUsing Bayes theorem we can infer that",
			"rawText": "Let Z be a latent variable, P(Z ) the distribution of it\nLet X be an observation and P(X ) be the distribution over it\nUsing Bayes theorem we can infer that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let Z be a latent variable, P(Z ) the distribution of it\nLet X be an observation and P(X ) be the distribution over it\nUsing Bayes theorem we can infer that",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 130,
			"versionNonce": 393749504,
			"isDeleted": false,
			"id": "Yfw0f3ss5FQ1kUSgukrHf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1341.6732410521934,
			"y": 757.4631287023485,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 243.24927653214397,
			"height": 69.061308794615,
			"seed": 2032999424,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "59b-t__wAN5opyfYTu0bL",
					"type": "arrow"
				}
			],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0f1da85a77840fcdd5b669cad7f33d3ff7fa0ae3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 462,
			"versionNonce": 240589824,
			"isDeleted": false,
			"id": "59b-t__wAN5opyfYTu0bL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1537.8396201665325,
			"y": 828.6220694476574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 173.6632110034459,
			"height": 31.12301559044556,
			"seed": 2104140800,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008512,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Yfw0f3ss5FQ1kUSgukrHf",
				"focus": 0.02201521606017642,
				"gap": 2.0976319506939376
			},
			"endBinding": {
				"elementId": "1ymxKjgR",
				"focus": 0.5368448911942185,
				"gap": 31.826810632185243
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
					67.003811857232,
					31.12301559044556
				],
				[
					173.6632110034459,
					3.483943199337318
				]
			]
		},
		{
			"type": "image",
			"version": 214,
			"versionNonce": 1329243136,
			"isDeleted": false,
			"id": "5WKl3TZwFr-BvuvQjcgWO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1660.1816782276464,
			"y": 780.8929885166251,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 209.87492833601053,
			"height": 49.66054642316868,
			"seed": 1052320768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "59b-t__wAN5opyfYTu0bL",
					"type": "arrow"
				}
			],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d4bacc8e3cddeeabe52a8eb15d2541458b878f24",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 321,
			"versionNonce": 1480991744,
			"isDeleted": false,
			"id": "1ymxKjgR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1109.8935388998104,
			"y": 863.93282327918,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 716.8592529296875,
			"height": 350,
			"seed": 74750976,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "59b-t__wAN5opyfYTu0bL",
					"type": "arrow"
				}
			],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So if P(X|z) and P(z) are known or learnt we can uncover the probability\nof a realization z given an observation X\nProblem:\nP(X|z) is generally intractable\n\nSolutions?\n\n1) Monte Carlo estimation:\nsample from the distributions and approximate the integral\n\n2) Variational Inference:\n approximate the intractable posterior distribution P(z|X )\nwith a tractable distribution Q(z|X ) by minimizing the KL divergence\nbetween them.",
			"rawText": "So if P(X|z) and P(z) are known or learnt we can uncover the probability\nof a realization z given an observation X\nProblem:\nP(X|z) is generally intractable\n\nSolutions?\n\n1) Monte Carlo estimation:\nsample from the distributions and approximate the integral\n\n2) Variational Inference:\n approximate the intractable posterior distribution P(z|X )\nwith a tractable distribution Q(z|X ) by minimizing the KL divergence\nbetween them.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So if P(X|z) and P(z) are known or learnt we can uncover the probability\nof a realization z given an observation X\nProblem:\nP(X|z) is generally intractable\n\nSolutions?\n\n1) Monte Carlo estimation:\nsample from the distributions and approximate the integral\n\n2) Variational Inference:\n approximate the intractable posterior distribution P(z|X )\nwith a tractable distribution Q(z|X ) by minimizing the KL divergence\nbetween them.",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 339,
			"versionNonce": 1830001664,
			"isDeleted": false,
			"id": "EBkdcvH8rRXPuMZgTMOUR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1800.423466164977,
			"y": 1146.6836648814965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 163.00298540335825,
			"height": 0.8968928755355137,
			"seed": 1498586112,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008513,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "jKiJqPLdNuV4yXZDjG_t7",
				"focus": -0.46663219470876854,
				"gap": 10.68838403167706
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
					163.00298540335825,
					0.8968928755355137
				]
			]
		},
		{
			"type": "image",
			"version": 222,
			"versionNonce": 1523098624,
			"isDeleted": false,
			"id": "jKiJqPLdNuV4yXZDjG_t7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1974.1148356000122,
			"y": 1130.292465037591,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 638.1500215274278,
			"height": 24.932372934094854,
			"seed": 1369480192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EBkdcvH8rRXPuMZgTMOUR",
					"type": "arrow"
				},
				{
					"id": "EdX2ybMHvLkfR4tiU0qHN",
					"type": "arrow"
				}
			],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b82a8a9ff0075a10d23a08e3b18e0595a14b1cf1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 132,
			"versionNonce": 1583031296,
			"isDeleted": false,
			"id": "KA5Ifigo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2055.740139429664,
			"y": 1105.2924649367349,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 474.8994140625,
			"height": 25,
			"seed": 1450482688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The KL-divergence can be simplified to this form",
			"rawText": "The KL-divergence can be simplified to this form",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The KL-divergence can be simplified to this form",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 207,
			"versionNonce": 1077943296,
			"isDeleted": false,
			"id": "EdX2ybMHvLkfR4tiU0qHN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2592.809597815101,
			"y": 1157.3999864774678,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 42.642159713679575,
			"height": 70.15323049669837,
			"seed": 5315584,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008513,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jKiJqPLdNuV4yXZDjG_t7",
				"focus": -0.8902698053047209,
				"gap": 2.1751485057818627
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
					25.218481551100467,
					41.72512402091206
				],
				[
					-17.423678162579108,
					70.15323049669837
				]
			]
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 1424106496,
			"isDeleted": false,
			"id": "CCwcksB6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2390.726509234169,
			"y": 1224.3286033684442,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 190.953125,
			"height": 69.36698565210594,
			"seed": 746660864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 13.873397130421187,
			"fontFamily": 1,
			"text": "We dont really know\nThis term\nbut can approximate it with\nEvidence lower bound",
			"rawText": "We dont really know\nThis term\nbut can approximate it with\nEvidence lower bound",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We dont really know\nThis term\nbut can approximate it with\nEvidence lower bound",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 205,
			"versionNonce": 1023255552,
			"isDeleted": false,
			"id": "mgiHO-ZPihDICK_B9EvJH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1960.8864684415607,
			"y": 1305.0536695171452,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 683.6640300108589,
			"height": 28.077892350016175,
			"seed": 2057608192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "I7Cwr7jt0eADXLuzGcAvO",
					"type": "arrow"
				},
				{
					"id": "lCx-CdsgzLh3oe4D77IzC",
					"type": "arrow"
				}
			],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6c57605868bd4fb54ff2f5e381b0a406e99ce174",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 137,
			"versionNonce": 2044500992,
			"isDeleted": false,
			"id": "I7Cwr7jt0eADXLuzGcAvO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2279.6419087350687,
			"y": 1180.523203458618,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 0.8980024548532128,
			"height": 108.65829703721715,
			"seed": 1025909760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008513,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "mgiHO-ZPihDICK_B9EvJH",
				"focus": -0.0641365658927542,
				"gap": 15.872169021310128
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
					0.8980024548532128,
					108.65829703721715
				]
			]
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 1326162944,
			"isDeleted": false,
			"id": "EmPZbbCm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2132.766880682389,
			"y": 1369.4162453156011,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 161.25979614257812,
			"height": 75,
			"seed": 833002496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a tractable \napproximation of\nthe posterior",
			"rawText": "a tractable \napproximation of\nthe posterior",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a tractable \napproximation of\nthe posterior",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 905389056,
			"isDeleted": false,
			"id": "WWyhZ65O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2314.2891194418844,
			"y": 1388.4783781910955,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 12.499984741210938,
			"height": 25,
			"seed": 693541888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "+",
			"rawText": "+",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "+",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 863151104,
			"isDeleted": false,
			"id": "HOnkWzcW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2330.6186736314835,
			"y": 1357.58457663426,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 161.25979614257812,
			"height": 100,
			"seed": 347022336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a tractable\nlower bound\napproximation of\nP(x)",
			"rawText": "a tractable\nlower bound\napproximation of\nP(x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a tractable\nlower bound\napproximation of\nP(x)",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 135,
			"versionNonce": 1971201024,
			"isDeleted": false,
			"id": "7Fg7gW2C0vVf5kbnjtM3N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1174.0490397369638,
			"y": 1221.26984293791,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 604.7282866324936,
			"height": 2.829138183076111,
			"seed": 1566907392,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					604.7282866324936,
					-2.829138183076111
				]
			]
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 1780065280,
			"isDeleted": false,
			"id": "hX4RgScC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1305.881553109557,
			"y": 1231.830102944828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 338.94140625,
			"height": 35,
			"seed": 625157120,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Variational Auto-encoder",
			"rawText": "Variational Auto-encoder",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Variational Auto-encoder",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 271,
			"versionNonce": 1273568256,
			"isDeleted": false,
			"id": "lCx-CdsgzLh3oe4D77IzC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1953.7357289031634,
			"y": 1316.7859818655772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 188.99057917085656,
			"height": 2.2737367544323206e-13,
			"seed": 943004672,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008514,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mgiHO-ZPihDICK_B9EvJH",
				"focus": 0.1643024909292505,
				"gap": 7.150739538397147
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
					-188.99057917085656,
					-2.2737367544323206e-13
				]
			]
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 1660986368,
			"isDeleted": false,
			"id": "7fnWu53G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1215.3302884493448,
			"y": 1273.8219252316353,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 508.2003173828125,
			"height": 100,
			"seed": 1826464768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We want to be able to:\n▶ sample from the dataset distribution P(X)\n▶ calculate datapoint posteriors P(z|X)\n▶ find a latent representation Z given a dataset.",
			"rawText": "We want to be able to:\n▶ sample from the dataset distribution P(X)\n▶ calculate datapoint posteriors P(z|X)\n▶ find a latent representation Z given a dataset.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to be able to:\n▶ sample from the dataset distribution P(X)\n▶ calculate datapoint posteriors P(z|X)\n▶ find a latent representation Z given a dataset.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 451,
			"versionNonce": 55321600,
			"isDeleted": false,
			"id": "QdwAW89s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1117.1847500962426,
			"y": 1390.090836105961,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 716.8992309570312,
			"height": 200,
			"seed": 768941056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "To do this we need to calculate the following:\nP(z) which can be random and only include prior info about the problem\nNote that we want to be able to sample easily from our choice of P(z)\nUsually Isotropic Multi-dimensional Gaussian\n\nP(X |z) which is seen as the decoder here, modelled as a Neural network\n\nQ(z|X) which is seen as the encoder here, modelled as a Neural network",
			"rawText": "To do this we need to calculate the following:\nP(z) which can be random and only include prior info about the problem\nNote that we want to be able to sample easily from our choice of P(z)\nUsually Isotropic Multi-dimensional Gaussian\n\nP(X |z) which is seen as the decoder here, modelled as a Neural network\n\nQ(z|X) which is seen as the encoder here, modelled as a Neural network",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To do this we need to calculate the following:\nP(z) which can be random and only include prior info about the problem\nNote that we want to be able to sample easily from our choice of P(z)\nUsually Isotropic Multi-dimensional Gaussian\n\nP(X |z) which is seen as the decoder here, modelled as a Neural network\n\nQ(z|X) which is seen as the encoder here, modelled as a Neural network",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 124,
			"versionNonce": 237478912,
			"isDeleted": false,
			"id": "e4wNNTdyVle4ntNYpDN_g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1223.1857036762008,
			"y": 1606.3597473219236,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 490.27492496935014,
			"height": 125.88139965429261,
			"seed": 1032920064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f5b6f7ecda3937c0dd135ff4c1169b0df98d80c0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 83,
			"versionNonce": 831726592,
			"isDeleted": false,
			"id": "zfNHbaGTOnnWoLjJHwBWb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1243.230837531415,
			"y": 1741.3023701285056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 443.97251507538226,
			"height": 0,
			"seed": 2063145984,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					443.97251507538226,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 647,
			"versionNonce": 1536074752,
			"isDeleted": false,
			"id": "ghifQPuc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1149.9290851341825,
			"y": 1750.6581127833504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 603.3593139648438,
			"height": 225,
			"seed": 578364416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Generative models usually fail at Outlier detection even tho\nthey try to estimate the evidence distribution.\nThis is because The\nlowest latent variables in a generative model learn generic\nlow-level features that can describe a wide range of data\nwhich are quite similar across models (edge detectors)\nand  do not carry much information for OOD detection.\nyet theyre seen as features that would suggest that it is\npart of the distribution that we have.",
			"rawText": "Generative models usually fail at Outlier detection even tho\nthey try to estimate the evidence distribution.\nThis is because The\nlowest latent variables in a generative model learn generic\nlow-level features that can describe a wide range of data\nwhich are quite similar across models (edge detectors)\nand  do not carry much information for OOD detection.\nyet theyre seen as features that would suggest that it is\npart of the distribution that we have.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generative models usually fail at Outlier detection even tho\nthey try to estimate the evidence distribution.\nThis is because The\nlowest latent variables in a generative model learn generic\nlow-level features that can describe a wide range of data\nwhich are quite similar across models (edge detectors)\nand  do not carry much information for OOD detection.\nyet theyre seen as features that would suggest that it is\npart of the distribution that we have.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 194,
			"versionNonce": 974791680,
			"isDeleted": false,
			"id": "U748UJ23tJZF0mXigiTj4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1268.7292590053385,
			"y": 1982.0001129758875,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 381.75989136502034,
			"height": 274.718625228637,
			"seed": 1684644864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b03706b66bb93ef7a6458fc67c7837a7bfb074d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 993371136,
			"isDeleted": false,
			"id": "WIMWk5mW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1094.7456179395936,
			"y": 2254.780759235225,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 743.71923828125,
			"height": 100,
			"seed": 501423104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263008429,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So in order to make OOD detection we need to not rely on the information\ngiven by the lower latent vairables as much\nMore on the methods in the paper\nHierarchical VAEs Know What They Don’t Know",
			"rawText": "So in order to make OOD detection we need to not rely on the information\ngiven by the lower latent vairables as much\nMore on the methods in the paper\nHierarchical VAEs Know What They Don’t Know",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So in order to make OOD detection we need to not rely on the information\ngiven by the lower latent vairables as much\nMore on the methods in the paper\nHierarchical VAEs Know What They Don’t Know",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 2064098304,
			"isDeleted": false,
			"id": "bKJiqpmv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1358.7598893327295,
			"y": -353.4764764398185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 229.93695068359375,
			"height": 35,
			"seed": 394042368,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Normalizing Flows",
			"rawText": "Normalizing Flows",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normalizing Flows",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 562,
			"versionNonce": 923444224,
			"isDeleted": false,
			"id": "HkCDx8XlA15cyGmqL1bRG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3694.184574273785,
			"y": -15.162919556355632,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 661,
			"height": 171,
			"seed": 411378688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717265112025,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3f1ac6e1d987f9f1f277b7d10ff93dca1c1bd519",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 607,
			"versionNonce": 1175856128,
			"isDeleted": false,
			"id": "qyp0Ec6c",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3772.0874525291474,
			"y": -60.824828051333725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 511.17938232421875,
			"height": 50,
			"seed": 1142955008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717265112025,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Very similar to the encoder-decoder Architecture\nexcept the functions are the inverse of each other",
			"rawText": "Very similar to the encoder-decoder Architecture\nexcept the functions are the inverse of each other",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Very similar to the encoder-decoder Architecture\nexcept the functions are the inverse of each other",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 514,
			"versionNonce": 1739695104,
			"isDeleted": false,
			"id": "u8j8Wq90",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3782.6403047222525,
			"y": 133.05907515259025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 492.27947998046875,
			"height": 50,
			"seed": 398500864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717265112025,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Since encoder and decoder are perfectly invertible\nno reconstruction loss has to be minimized.",
			"rawText": "Since encoder and decoder are perfectly invertible\nno reconstruction loss has to be minimized.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since encoder and decoder are perfectly invertible\nno reconstruction loss has to be minimized.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 524,
			"versionNonce": 275686400,
			"isDeleted": false,
			"id": "ke76VHSf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1015.119849440186,
			"y": -281.40400558700185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 882.5989990234375,
			"height": 125,
			"seed": 548346880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Motivation:\nWe want to learn the distribution of our data, such distribution\nis extremely complex to the point of even if we learned it we wouldnt\nbe able to sample from it, so what if we learn a simple sampleable distirbution\nand learn how to convert bijectively from our simple distribution to the real complex one?",
			"rawText": "Motivation:\nWe want to learn the distribution of our data, such distribution\nis extremely complex to the point of even if we learned it we wouldnt\nbe able to sample from it, so what if we learn a simple sampleable distirbution\nand learn how to convert bijectively from our simple distribution to the real complex one?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Motivation:\nWe want to learn the distribution of our data, such distribution\nis extremely complex to the point of even if we learned it we wouldnt\nbe able to sample from it, so what if we learn a simple sampleable distirbution\nand learn how to convert bijectively from our simple distribution to the real complex one?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 156,
			"versionNonce": 1849531392,
			"isDeleted": false,
			"id": "lUa3VQ1x2eaB15n9cz6pK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1146.3157419515762,
			"y": -141.09715304049578,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 588.1184675961177,
			"height": 169.03039898976013,
			"seed": 1006806016,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2b32e7f50caa321735315b985323f40c7f9bf69d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1392124928,
			"isDeleted": false,
			"id": "hc5CId2U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1082.0427803804248,
			"y": 35.142068927789836,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 761.2813720703125,
			"height": 20,
			"seed": 383624192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Each transformation must be invertible and differentiable, but can be a learned neural network.",
			"rawText": "Each transformation must be invertible and differentiable, but can be a learned neural network.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Each transformation must be invertible and differentiable, but can be a learned neural network.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 448,
			"versionNonce": 204086272,
			"isDeleted": false,
			"id": "aKaXDFoa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 910.957427142957,
			"y": 73.56387003264098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 1089.418701171875,
			"height": 175,
			"seed": 514366464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717262977418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "an important note here is all the step by step transformations we do to our\nsimple distribution have to be invertible in order to ensure bijectiveness.\n\nanother note is that we allow those transformations to perform affine transformations\non our distribution (which includes scaling), but because we want to keep the rule of change of Variables\n(i.e we want our distribution to sum up to 1) We have to divide by the determinant of the inverse jacobian of\nthis particular transformation",
			"rawText": "an important note here is all the step by step transformations we do to our\nsimple distribution have to be invertible in order to ensure bijectiveness.\n\nanother note is that we allow those transformations to perform affine transformations\non our distribution (which includes scaling), but because we want to keep the rule of change of Variables\n(i.e we want our distribution to sum up to 1) We have to divide by the determinant of the inverse jacobian of\nthis particular transformation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "an important note here is all the step by step transformations we do to our\nsimple distribution have to be invertible in order to ensure bijectiveness.\n\nanother note is that we allow those transformations to perform affine transformations\non our distribution (which includes scaling), but because we want to keep the rule of change of Variables\n(i.e we want our distribution to sum up to 1) We have to divide by the determinant of the inverse jacobian of\nthis particular transformation",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 240,
			"versionNonce": 512205824,
			"isDeleted": false,
			"id": "3auDBzy6ti8N6brf6Kid1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2001.7017639116857,
			"y": 187.5954740255596,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 144.50039779317876,
			"height": 33.74440701955211,
			"seed": 806493184,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262985890,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "WEf0SKxQ",
				"focus": -1.180432804425653,
				"gap": 29.458484643895645
			},
			"endBinding": {
				"elementId": "WEf0SKxQ",
				"focus": 0.07971314447565125,
				"gap": 3.3740973313291818
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
					76.38235089709542,
					-27.08855728245271
				],
				[
					144.50039779317876,
					6.655849737099402
				]
			]
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 137372672,
			"isDeleted": false,
			"id": "WEf0SKxQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2031.1602485555813,
			"y": 197.62542109398817,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 255.5421142578125,
			"height": 136.3033497735888,
			"seed": 823403520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3auDBzy6ti8N6brf6Kid1",
					"type": "arrow"
				}
			],
			"updated": 1717262980794,
			"link": null,
			"locked": false,
			"fontSize": 12.115853313207893,
			"fontFamily": 1,
			"text": "Jacobian tells us how the function\nmoves given a certain input\n\ndeterminant of a matrix gives us\nthe change of scale of the output\nlinear space\n\ndividing by the determinant of the jacobian\nensure we dont expand beyond 1",
			"rawText": "Jacobian tells us how the function\nmoves given a certain input\n\ndeterminant of a matrix gives us\nthe change of scale of the output\nlinear space\n\ndividing by the determinant of the jacobian\nensure we dont expand beyond 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Jacobian tells us how the function\nmoves given a certain input\n\ndeterminant of a matrix gives us\nthe change of scale of the output\nlinear space\n\ndividing by the determinant of the jacobian\nensure we dont expand beyond 1",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 398,
			"versionNonce": 73112576,
			"isDeleted": false,
			"id": "c9vaZNcJVm18conEc6-2z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2048.4376663457856,
			"y": 388.1975656992479,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 229.63667577533005,
			"height": 202.65234254673666,
			"seed": 1653152768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263009545,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4c1637c1a34c2cfedc8fb7374c5558e7086a4b6a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 89,
			"versionNonce": 241574912,
			"isDeleted": false,
			"id": "MwhFMiP11G3J1CpnFgY-E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1865.9390878281413,
			"y": -57.181509456394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 379.49795329019366,
			"height": 5.105353631706691,
			"seed": 699997184,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717262993771,
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
					379.49795329019366,
					5.105353631706691
				]
			]
		},
		{
			"type": "image",
			"version": 298,
			"versionNonce": 1516116992,
			"isDeleted": false,
			"id": "I0tkP1Q80SPYKTYSmFXes",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1659.528219755858,
			"y": 443.905993221098,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 233.30907139215105,
			"height": 53.275299766711655,
			"seed": 1413782528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263959479,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "91f2ee018d383cf8c8a97ea084faceef8701b77e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 380,
			"versionNonce": 183116800,
			"isDeleted": false,
			"id": "mHh4dt4_c2dU6C4nyMk4P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1602.3349263394525,
			"y": 418.6845271647477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 73.50839487630401,
			"height": 23.037394876142457,
			"seed": 668115968,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263958640,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ImeO-U5HkassJtvgs301P",
				"focus": -0.6094706833887884,
				"gap": 3.097012746366886
			},
			"endBinding": {
				"elementId": "zmyR9ZUT",
				"focus": 0.5789205115341911,
				"gap": 2.7528020315564845
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
					13.078670899614963,
					23.037394876142457
				],
				[
					73.50839487630401,
					2.3336079636721934
				]
			]
		},
		{
			"type": "text",
			"version": 134,
			"versionNonce": 1899469824,
			"isDeleted": false,
			"id": "zmyR9ZUT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1678.596123247313,
			"y": 396.4515822454012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 181.55978393554688,
			"height": 50,
			"seed": 759962624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mHh4dt4_c2dU6C4nyMk4P",
					"type": "arrow"
				}
			],
			"updated": 1717263953883,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "must be tractable\nto ensure",
			"rawText": "must be tractable\nto ensure",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "must be tractable\nto ensure",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 99,
			"versionNonce": 1293067264,
			"isDeleted": false,
			"id": "bRmUI8iE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1300.6350062273957,
			"y": 248.22704291356465,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 324.09692031995763,
			"height": 48.54893138396127,
			"seed": 50651,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263757637,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3dd757a87e5824caf60941dffa78316dfcdcfdd1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 199,
			"versionNonce": 424158208,
			"isDeleted": false,
			"id": "QgWOg9O0HmlB8YjK_ksLi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1341.270177445755,
			"y": 301.5197180849031,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 231.61662798937368,
			"height": 48.83483120257879,
			"seed": 346037248,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263793944,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e5f6a8d7bad602d6b91abd9c003cadb918363958",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 270,
			"versionNonce": 1210131456,
			"isDeleted": false,
			"id": "ImeO-U5HkassJtvgs301P",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1275.5512120900837,
			"y": 356.2071012202081,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 370.1800227035023,
			"height": 59.38041319817272,
			"seed": 330408960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mHh4dt4_c2dU6C4nyMk4P",
					"type": "arrow"
				},
				{
					"id": "WW3DW8JFdfAjNWzLC8QvY",
					"type": "arrow"
				}
			],
			"updated": 1717263979781,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "91b7248cc1c5ef87f7ba0032aff56526e4200c45",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 26,
			"versionNonce": 1819223040,
			"isDeleted": false,
			"id": "WW3DW8JFdfAjNWzLC8QvY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1309.9846728385319,
			"y": 416.3372268399667,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 65.16654426038349,
			"height": 46.34065369627274,
			"seed": 1988566016,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717263980077,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ImeO-U5HkassJtvgs301P",
				"focus": 0.7995677144374187,
				"gap": 1
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
					-2.1722181420127527,
					44.16843555425993
				],
				[
					-65.16654426038349,
					46.34065369627274
				]
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 1296442368,
			"isDeleted": false,
			"id": "UA1Rd1sk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1130.6997892550507,
			"y": 429.3705356920434,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 100.79988098144531,
			"height": 75,
			"seed": 328311808,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717263999985,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "exact log\nlikelihood\nevaluation",
			"rawText": "exact log\nlikelihood\nevaluation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "exact log\nlikelihood\nevaluation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 306,
			"versionNonce": 1044128768,
			"isDeleted": false,
			"id": "CkJs0kSi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2326.5493235360364,
			"y": -318.47647631010847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 709.3192138671875,
			"height": 100,
			"seed": 1875420160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717264108656,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In Order to ensure that the determinant of our\nJacobian is tractable we can try to set up our architecture\nsuch that our jacobian is triangluar, because for any triangular matrix\nits determinant is just the main diagonal",
			"rawText": "In Order to ensure that the determinant of our\nJacobian is tractable we can try to set up our architecture\nsuch that our jacobian is triangluar, because for any triangular matrix\nits determinant is just the main diagonal",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In Order to ensure that the determinant of our\nJacobian is tractable we can try to set up our architecture\nsuch that our jacobian is triangluar, because for any triangular matrix\nits determinant is just the main diagonal",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 104,
			"versionNonce": 310451200,
			"isDeleted": false,
			"id": "NeFjIKrKBAonvUhvj1kDU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2436.2901194056385,
			"y": -214.43643486895016,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 498.9641861726994,
			"height": 108.598087578764,
			"seed": 1523426304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717264165931,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "25b10389db2e63805bd4c4f11cb89622e7c6a20b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "i1QfcNut",
			"type": "text",
			"x": 2448.449194996821,
			"y": -90.5407944379278,
			"width": 465.51947021484375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1450320896,
			"version": 61,
			"versionNonce": 1877548032,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264209475,
			"link": null,
			"locked": false,
			"text": "This is achieve by the design of coupling layers",
			"rawText": "This is achieve by the design of coupling layers",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is achieve by the design of coupling layers",
			"lineHeight": 1.25
		},
		{
			"id": "5vqo4kUo",
			"type": "text",
			"x": 2480.099726567144,
			"y": -42.43263652069021,
			"width": 33.07997131347656,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1982536704,
			"version": 168,
			"versionNonce": 1882825728,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "SynIc7vzgNZyRSnUKz-7L",
					"type": "arrow"
				},
				{
					"id": "IFe55Bx8EO6fycjddEzzP",
					"type": "arrow"
				}
			],
			"updated": 1717264395162,
			"link": null,
			"locked": false,
			"text": "z1:d",
			"rawText": "z1:d",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "z1:d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 1030497280,
			"isDeleted": false,
			"id": "dTL011gn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2627.8186885815935,
			"y": -41.192254803414585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 54.919952392578125,
			"height": 25,
			"seed": 501750784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "44429Y8L2nYftT2T_90aJ",
					"type": "arrow"
				}
			],
			"updated": 1717264395162,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "zd+1:n",
			"rawText": "zd+1:n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "zd+1:n",
			"lineHeight": 1.25
		},
		{
			"id": "SynIc7vzgNZyRSnUKz-7L",
			"type": "arrow",
			"x": 2497.29817142324,
			"y": -4.958868200847519,
			"width": 1.8926363165373914,
			"height": 193.6144696525207,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1451729920,
			"version": 185,
			"versionNonce": 823237632,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264799787,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.8926363165373914,
					193.6144696525207
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "5vqo4kUo",
				"focus": -0.022980748296134286,
				"gap": 12.47376831984269
			},
			"endBinding": {
				"elementId": "XB2H86hO",
				"focus": -0.05972736965216875,
				"gap": 14.364944522606379
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "XB2H86hO",
			"type": "text",
			"x": 2484.8771021784246,
			"y": 203.02054597427957,
			"width": 31.019973754882812,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2092440576,
			"version": 54,
			"versionNonce": 2106104832,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "SynIc7vzgNZyRSnUKz-7L",
					"type": "arrow"
				}
			],
			"updated": 1717264799783,
			"link": null,
			"locked": false,
			"text": "y1:d",
			"rawText": "y1:d",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y1:d",
			"lineHeight": 1.25
		},
		{
			"id": "thBwUiAO",
			"type": "text",
			"x": 2465.5137106930456,
			"y": 73.11148246549149,
			"width": 22.279983520507812,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2058200064,
			"version": 116,
			"versionNonce": 559260672,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264395162,
			"link": null,
			"locked": false,
			"text": "Id",
			"rawText": "Id",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Id",
			"lineHeight": 1.25
		},
		{
			"id": "IFe55Bx8EO6fycjddEzzP",
			"type": "arrow",
			"x": 2500.694175497578,
			"y": -5.583431006178248,
			"width": 63.577991971387746,
			"height": 57.92280690806493,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1050549248,
			"version": 277,
			"versionNonce": 1454711808,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265323058,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					63.577991971387746,
					57.92280690806493
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "5vqo4kUo",
				"gap": 11.849205514511961,
				"focus": 0.7492310605432969
			},
			"endBinding": {
				"elementId": "-oWfe0JBZQx7neXjEL1_z",
				"gap": 2.0988004101303943,
				"focus": -0.04239908125646449
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "-oWfe0JBZQx7neXjEL1_z",
			"type": "ellipse",
			"x": 2556.5977415356297,
			"y": 46.87984464160161,
			"width": 60.582592117079,
			"height": 49,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1181787136,
			"version": 132,
			"versionNonce": 2067571712,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "lZo7L3Nk"
				},
				{
					"id": "IFe55Bx8EO6fycjddEzzP",
					"type": "arrow"
				},
				{
					"id": "qvwx69IlSFzLsC5walmyS",
					"type": "arrow"
				}
			],
			"updated": 1717264395162,
			"link": null,
			"locked": false
		},
		{
			"id": "lZo7L3Nk",
			"type": "text",
			"x": 2580.6398625385864,
			"y": 59.055728502531196,
			"width": 12.659988403320312,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 122856448,
			"version": 111,
			"versionNonce": 872948736,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264395162,
			"link": null,
			"locked": false,
			"text": "m",
			"rawText": "m",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "-oWfe0JBZQx7neXjEL1_z",
			"originalText": "m",
			"lineHeight": 1.25
		},
		{
			"id": "44429Y8L2nYftT2T_90aJ",
			"type": "arrow",
			"x": 2658.7800939738977,
			"y": -8.70624503283178,
			"width": 1.281766929439982,
			"height": 121.179143661524,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 177808384,
			"version": 387,
			"versionNonce": 285418496,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265323058,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.281766929439982,
					121.179143661524
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "dTL011gn",
				"gap": 7.486009770582797,
				"focus": -0.11923763775264332
			},
			"endBinding": {
				"elementId": "13hu1dPnc89wLCd-kGWOv",
				"gap": 1.1070536461914813,
				"focus": 0.04313059126964614
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "qvwx69IlSFzLsC5walmyS",
			"type": "arrow",
			"x": 2607.2423085029823,
			"y": 90.98045221940033,
			"width": 32.12822532349446,
			"height": 27.244130329267435,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 816782336,
			"version": 331,
			"versionNonce": 2106205184,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265323058,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					32.12822532349446,
					27.244130329267435
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "-oWfe0JBZQx7neXjEL1_z",
				"gap": 1.1914638119302836,
				"focus": 0.06596080732584773
			},
			"endBinding": {
				"elementId": "13hu1dPnc89wLCd-kGWOv",
				"gap": 1,
				"focus": 0.08941382853500585
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "ellipse",
			"version": 240,
			"versionNonce": 1987159040,
			"isDeleted": false,
			"id": "13hu1dPnc89wLCd-kGWOv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2628.7347455513273,
			"y": 113.56601421988552,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 60.582592117079,
			"height": 49,
			"seed": 44669952,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "MKHs9WPG"
				},
				{
					"id": "44429Y8L2nYftT2T_90aJ",
					"type": "arrow"
				},
				{
					"id": "qvwx69IlSFzLsC5walmyS",
					"type": "arrow"
				},
				{
					"id": "VtJxA8zP-SSyLyGYCjvcD",
					"type": "arrow"
				}
			],
			"updated": 1717264395162,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 10298368,
			"isDeleted": false,
			"id": "MKHs9WPG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2654.096866249108,
			"y": 125.7418980808151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 10.019989013671875,
			"height": 25,
			"seed": 857086976,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717264395162,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "g",
			"rawText": "g",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "13hu1dPnc89wLCd-kGWOv",
			"originalText": "g",
			"lineHeight": 1.25
		},
		{
			"id": "VtJxA8zP-SSyLyGYCjvcD",
			"type": "arrow",
			"x": 2660.3356023408833,
			"y": 163.54367311445822,
			"width": 2.5157488426011696,
			"height": 40.10143566515205,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 272966656,
			"version": 177,
			"versionNonce": 877732864,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265323059,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.5157488426011696,
					40.10143566515205
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "13hu1dPnc89wLCd-kGWOv",
				"gap": 1,
				"focus": 0.00950449118188828
			},
			"endBinding": {
				"elementId": "TDZ3RHcI",
				"gap": 1.2491256106615083,
				"focus": -0.10314107470505728
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "TDZ3RHcI",
			"type": "text",
			"x": 2640.0908178568434,
			"y": 204.89423439027178,
			"width": 52.859954833984375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1522672640,
			"version": 63,
			"versionNonce": 770221056,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VtJxA8zP-SSyLyGYCjvcD",
					"type": "arrow"
				}
			],
			"updated": 1717264802702,
			"link": null,
			"locked": false,
			"text": "yd+1:n",
			"rawText": "yd+1:n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "yd+1:n",
			"lineHeight": 1.25
		},
		{
			"id": "3BU7Q1aN",
			"type": "text",
			"x": 2727.9050300154536,
			"y": 60.19343947126799,
			"width": 22.212005615234375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 53582848,
			"version": 21,
			"versionNonce": 1391991808,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264401226,
			"link": null,
			"locked": false,
			"text": "=",
			"rawText": "=",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "=",
			"lineHeight": 1.25
		},
		{
			"id": "nlOx3Kfz",
			"type": "text",
			"x": 2815.522070616651,
			"y": 61.6236184281712,
			"width": 45.0360107421875,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 371039232,
			"version": 59,
			"versionNonce": 120333312,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264409642,
			"link": null,
			"locked": false,
			"text": "J=",
			"rawText": "J=",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "J=",
			"lineHeight": 1.25
		},
		{
			"id": "P5_BZ3cG4XZAYdIsS6IP2",
			"type": "line",
			"x": 2888.22557054293,
			"y": 9.346385826617052,
			"width": 26.508124947474798,
			"height": 144.15981185594472,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1030956032,
			"version": 181,
			"versionNonce": 1863787520,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264447753,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.07056085568543,
					0.4953945424603381
				],
				[
					-19.711169832737983,
					143.66441731348442
				],
				[
					5.437564091789369,
					144.15981185594472
				]
			],
			"lastCommittedPoint": [
				8.836129567861917,
				216.4851744126243
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 238,
			"versionNonce": 1217569792,
			"isDeleted": false,
			"id": "gZlwv6vfXyB6-IMV4o70s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3019.668965785368,
			"y": 10.547021475456575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 28.733484032090683,
			"height": 144.19923877785564,
			"seed": 469965824,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717264447753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0.003294961341215874,
					0
				],
				[
					22.842730986849553,
					0.49553003016449926
				],
				[
					21.369218985203855,
					143.70370874769117
				],
				[
					-5.8907530452411265,
					144.19923877785564
				]
			]
		},
		{
			"id": "tylC7Igz",
			"type": "text",
			"x": 2987.312686763519,
			"y": 21.824641993764033,
			"width": 24.76800537109375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 384769024,
			"version": 26,
			"versionNonce": 513055744,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xThT4utMLFZdwC05lPhSB",
					"type": "arrow"
				}
			],
			"updated": 1717264458580,
			"link": null,
			"locked": false,
			"text": "0",
			"rawText": "0",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.25
		},
		{
			"id": "xThT4utMLFZdwC05lPhSB",
			"type": "arrow",
			"x": 2999.696689449066,
			"y": 10.779480033936295,
			"width": 41.97161544734536,
			"height": 39.026238924724794,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1090692096,
			"version": 44,
			"versionNonce": 1605639168,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717264811727,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.6817206532759883,
					-35.34451827144886
				],
				[
					41.97161544734536,
					-39.026238924724794
				]
			],
			"lastCommittedPoint": [
				41.97161544734536,
				-39.026238924724794
			],
			"startBinding": {
				"elementId": "tylC7Igz",
				"focus": -0.23725871684265204,
				"gap": 11.045161959827738
			},
			"endBinding": {
				"elementId": "l5q7jqmH",
				"focus": 0.5060004755467545,
				"gap": 10.901364672567524
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "l5q7jqmH",
			"type": "text",
			"x": 3052.569669568979,
			"y": -47.40955650896149,
			"width": 138.7202911376953,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1462707200,
			"version": 53,
			"versionNonce": 1795660800,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xThT4utMLFZdwC05lPhSB",
					"type": "arrow"
				}
			],
			"updated": 1717264811726,
			"link": null,
			"locked": false,
			"text": "because zd+1:n\ndoesnt contribute\nto y1:d",
			"rawText": "because zd+1:n\ndoesnt contribute\nto y1:d",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "because zd+1:n\ndoesnt contribute\nto y1:d",
			"lineHeight": 1.25
		},
		{
			"id": "m3BioOUu",
			"type": "text",
			"x": 2888.3380076653034,
			"y": 17.42442743097115,
			"width": 40.10401916503906,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1919853568,
			"version": 25,
			"versionNonce": 1325278208,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-TXpKnxu6M57cgoIQdcCA",
					"type": "arrow"
				}
			],
			"updated": 1717264501896,
			"link": null,
			"locked": false,
			"text": "Id",
			"rawText": "Id",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Id",
			"lineHeight": 1.25
		},
		{
			"id": "-TXpKnxu6M57cgoIQdcCA",
			"type": "arrow",
			"x": 2917.2261468156853,
			"y": 10.779480033936295,
			"width": 138.4326965631749,
			"height": 110.45161959827772,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2073435136,
			"version": 164,
			"versionNonce": 1161405440,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717264816239,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.6817206532759883,
					-52.280433276518124
				],
				[
					55.225809799138915,
					-92.04301633189809
				],
				[
					138.4326965631749,
					-110.45161959827772
				]
			],
			"lastCommittedPoint": [
				138.4326965631749,
				-110.45161959827772
			],
			"startBinding": {
				"elementId": "m3BioOUu",
				"focus": 0.3135286793714769,
				"gap": 6.644947397034855
			},
			"endBinding": {
				"elementId": "xY9coyhm",
				"focus": 0.2173043639127419,
				"gap": 6.15985949761216
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "xY9coyhm",
			"type": "text",
			"x": 3061.8187028764723,
			"y": -143.13429349413542,
			"width": 124.64028930664062,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1695458304,
			"version": 86,
			"versionNonce": 882779136,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-TXpKnxu6M57cgoIQdcCA",
					"type": "arrow"
				}
			],
			"updated": 1717264816237,
			"link": null,
			"locked": false,
			"text": "because z1:d\ngoes through no\ntransformations\nto y1:d",
			"rawText": "because z1:d\ngoes through no\ntransformations\nto y1:d",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "because z1:d\ngoes through no\ntransformations\nto y1:d",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 85,
			"versionNonce": 1539480576,
			"isDeleted": false,
			"id": "Vouy1Sgy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2878.5599710440765,
			"y": 84.94645555372138,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 72.4229668653449,
			"height": 46.200858172720025,
			"seed": 43472,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717264675475,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "07e267c8f693e6113e9b22221a824d8c83124af3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 93,
			"versionNonce": 1768367104,
			"isDeleted": false,
			"id": "io0yIdXVGCoJ8hWVmbyVJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2964.311403767527,
			"y": 90.06541139369189,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 68.71652574953045,
			"height": 45.021172042795804,
			"seed": 1376918528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lvkErYWh-Im7GGUlwF7CS",
					"type": "arrow"
				}
			],
			"updated": 1717264679088,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4653f84054ebcc204e89e476666dce1da79d8e23",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "lvkErYWh-Im7GGUlwF7CS",
			"type": "arrow",
			"x": 2993.8649232143093,
			"y": 143.49674521238092,
			"width": 119.74899005125963,
			"height": 36.95956483063571,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1221303296,
			"version": 29,
			"versionNonce": 984949760,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717264679361,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.174339076289016,
					36.95956483063571
				],
				[
					119.74899005125963,
					33.26360834757213
				]
			],
			"lastCommittedPoint": [
				119.74899005125963,
				33.26360834757213
			],
			"startBinding": {
				"elementId": "io0yIdXVGCoJ8hWVmbyVJ",
				"focus": 0.2417725799149165,
				"gap": 8.601744715417738
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vqnSFw57",
			"type": "text",
			"x": 3072.8926256328673,
			"y": 163.4549102209242,
			"width": 251.45657348632812,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2140644352,
			"version": 132,
			"versionNonce": 926915584,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264698496,
			"link": null,
			"locked": false,
			"text": "need to make sure\nthis is lower triangular to make\nsure the Jacobian is\nlower triangular",
			"rawText": "need to make sure\nthis is lower triangular to make\nsure the Jacobian is\nlower triangular",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "need to make sure\nthis is lower triangular to make\nsure the Jacobian is\nlower triangular",
			"lineHeight": 1.25
		},
		{
			"id": "CdRktSnc",
			"type": "text",
			"x": 2536.3664804991467,
			"y": 263.9272861128045,
			"width": 419.2995300292969,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 898964480,
			"version": 247,
			"versionNonce": 658873344,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264827770,
			"link": null,
			"locked": false,
			"text": "What about inveritbility?\nThe identity is already invertible\ny1:d is recoverable\nwe need to make sure that g is invertible!",
			"rawText": "What about inveritbility?\nThe identity is already invertible\ny1:d is recoverable\nwe need to make sure that g is invertible!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What about inveritbility?\nThe identity is already invertible\ny1:d is recoverable\nwe need to make sure that g is invertible!",
			"lineHeight": 1.25
		},
		{
			"id": "tcD2HDZd65v705yYD9tsD",
			"type": "line",
			"x": 2434.6452539154297,
			"y": 388.1150139991854,
			"width": 659.7404745590666,
			"height": 1.0340759789327194,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1334746112,
			"version": 50,
			"versionNonce": 1625367552,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264907637,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					659.7404745590666,
					-1.0340759789327194
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "e42gu7jH",
			"type": "text",
			"x": 2621.353051820533,
			"y": 399.4898497674452,
			"width": 269.7796630859375,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1843930112,
			"version": 75,
			"versionNonce": 1987189760,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264924285,
			"link": null,
			"locked": false,
			"text": "Example of a coupling layer\nS-T-layer",
			"rawText": "Example of a coupling layer\nS-T-layer",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example of a coupling layer\nS-T-layer",
			"lineHeight": 1.25
		},
		{
			"id": "rlYdtGo2EKkDcUTGM2Sn6",
			"type": "image",
			"x": 2523.8420883894323,
			"y": 460.9832793042199,
			"width": 452.5498950267487,
			"height": 285.409437036308,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 620307456,
			"version": 82,
			"versionNonce": 770448384,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264935641,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8fbb3c27deba2407893ac028deb69fed9fdf9cd0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "TiKzpypCOrHpirTCTP1NB",
			"type": "arrow",
			"x": 2878.715602050963,
			"y": 626.0555030989312,
			"width": 83.57397509935754,
			"height": 106.43855319257773,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 463315968,
			"version": 67,
			"versionNonce": 2102664192,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717264949416,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-30.748915366744768,
					81.20867391730008
				],
				[
					-83.57397509935754,
					106.43855319257773
				]
			],
			"lastCommittedPoint": [
				-83.57397509935754,
				106.43855319257773
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "HfNA_ISC-BebDxBUajezK",
			"type": "arrow",
			"x": 2866.8890961406764,
			"y": 559.0386362739748,
			"width": 100.13108337375843,
			"height": 140.34120346873215,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1409096704,
			"version": 56,
			"versionNonce": 1471587328,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717264951818,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-86.72771000876719,
					25.229879275277654
				],
				[
					-100.13108337375843,
					140.34120346873215
				]
			],
			"lastCommittedPoint": [
				-100.13108337375843,
				140.34120346873215
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "PikIZTYC",
			"type": "text",
			"x": 2676.91472088386,
			"y": 717.5138154718129,
			"width": 152.8798370361328,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 436806656,
			"version": 37,
			"versionNonce": 474883072,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717264957333,
			"link": null,
			"locked": false,
			"text": "learned\nneural networks",
			"rawText": "learned\nneural networks",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "learned\nneural networks",
			"lineHeight": 1.25
		},
		{
			"id": "E-Bh4Tty2J_jW7JTDnGaj",
			"type": "arrow",
			"x": 2841.6592168653992,
			"y": 480.9836972660843,
			"width": 213.6655401125081,
			"height": 48.09445736849807,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1077877760,
			"version": 61,
			"versionNonce": 825107456,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717264999031,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					113.53445673874967,
					-48.09445736849807
				],
				[
					213.6655401125081,
					-28.383614184687417
				]
			],
			"lastCommittedPoint": [
				213.6655401125081,
				-28.383614184687417
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "xHmtOzCuPbcAktnxGRmy4",
			"type": "arrow",
			"x": 2959.135842240911,
			"y": 480.9836972660843,
			"width": 89.88144491817684,
			"height": 15.768674547048477,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1324688384,
			"version": 37,
			"versionNonce": 217947136,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717265002868,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					32.32578282144959,
					-13.40337336499124
				],
				[
					89.88144491817684,
					-15.768674547048477
				]
			],
			"lastCommittedPoint": [
				89.88144491817684,
				-15.768674547048477
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "2w9mZMWI",
			"type": "text",
			"x": 3030.4374261099924,
			"y": 430.40899907789014,
			"width": 183.8083953857422,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1007885312,
			"version": 103,
			"versionNonce": 917021696,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265017686,
			"link": null,
			"locked": false,
			"text": "seperation of\nlatent data is\ndone through masking\nor in an autoregressive\nmanner",
			"rawText": "seperation of\nlatent data is\ndone through masking\nor in an autoregressive\nmanner",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "seperation of\nlatent data is\ndone through masking\nor in an autoregressive\nmanner",
			"lineHeight": 1.25
		},
		{
			"id": "DY3zHbLnyyjLCpYE5TqIM",
			"type": "arrow",
			"x": 3257.8720902580953,
			"y": 66.9246511837348,
			"width": 372.6535618265334,
			"height": 3.0297037546872616,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 399483904,
			"version": 51,
			"versionNonce": 266249216,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265107636,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					372.6535618265334,
					3.0297037546872616
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dkdMwt9C",
			"type": "text",
			"x": 3552.439195753981,
			"y": 236.81849289099287,
			"width": 932.1790161132812,
			"height": 300,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 853548032,
			"version": 632,
			"versionNonce": 1297032192,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265306730,
			"link": null,
			"locked": false,
			"text": "Can be used to generate counterfactual explanations!\n\nI.e if we take one class and tell it what information is required\nto be altered for that sample to be classified as another class we \nwould get proper explanations.\n\nThis method has been done before through adversarial attacks, the issue\nwith adversarial attacks is they do not learn the true distribution of the data\nmanifold thus the \"adversarial attack\" they preform to make our sample\ngenerate a different class is usually a bunch of meticulous noise.\nwhereas in generative models like this, the model only samples changes from the data manifold\nitself",
			"rawText": "Can be used to generate counterfactual explanations!\n\nI.e if we take one class and tell it what information is required\nto be altered for that sample to be classified as another class we \nwould get proper explanations.\n\nThis method has been done before through adversarial attacks, the issue\nwith adversarial attacks is they do not learn the true distribution of the data\nmanifold thus the \"adversarial attack\" they preform to make our sample\ngenerate a different class is usually a bunch of meticulous noise.\nwhereas in generative models like this, the model only samples changes from the data manifold\nitself",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can be used to generate counterfactual explanations!\n\nI.e if we take one class and tell it what information is required\nto be altered for that sample to be classified as another class we \nwould get proper explanations.\n\nThis method has been done before through adversarial attacks, the issue\nwith adversarial attacks is they do not learn the true distribution of the data\nmanifold thus the \"adversarial attack\" they preform to make our sample\ngenerate a different class is usually a bunch of meticulous noise.\nwhereas in generative models like this, the model only samples changes from the data manifold\nitself",
			"lineHeight": 1.25
		},
		{
			"id": "3U98TW8HrSQXN9fpCxdVk",
			"type": "image",
			"x": 3640.0876510107455,
			"y": 555.3495607791889,
			"width": 757.9135120811093,
			"height": 308.02902095275033,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 383132672,
			"version": 77,
			"versionNonce": 1124932608,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717265319072,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a486d3b25ed5f4c21faadcf8746642416896886b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "-pQNalE5PSsVwv9JbBvdD",
			"type": "arrow",
			"x": 3774.2060946410775,
			"y": 569.6568845271545,
			"width": 211.76729745092416,
			"height": 34.94509858926142,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1452057600,
			"version": 51,
			"versionNonce": 971938816,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717265336805,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-29.353882814979897,
					-28.654980843194267
				],
				[
					-211.76729745092416,
					6.290117746067153
				]
			],
			"lastCommittedPoint": [
				-211.76729745092416,
				6.290117746067153
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "omvgjGT9",
				"focus": 0.29987910508775045,
				"gap": 7.271739082144904
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "omvgjGT9",
			"type": "text",
			"x": 3393.5872393824225,
			"y": 555.67884509145,
			"width": 161.57981872558594,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 678011904,
			"version": 55,
			"versionNonce": 968563712,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-pQNalE5PSsVwv9JbBvdD",
					"type": "arrow"
				}
			],
			"updated": 1717265336805,
			"link": null,
			"locked": false,
			"text": "generative model\nchanging 4 to 9",
			"rawText": "generative model\nchanging 4 to 9",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "generative model\nchanging 4 to 9",
			"lineHeight": 1.25
		},
		{
			"id": "ff5EIQo5YFW3H2_b14oK8",
			"type": "arrow",
			"x": 3773.5071926692926,
			"y": 640.9448856492478,
			"width": 246.01349406840018,
			"height": 34.94509858926142,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1654922240,
			"version": 65,
			"versionNonce": 1178049536,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717265348370,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-121.60894309062951,
					22.364863097127227
				],
				[
					-246.01349406840018,
					34.94509858926142
				]
			],
			"lastCommittedPoint": [
				-246.01349406840018,
				34.94509858926142
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "p7Ih1mDb",
				"focus": 0.19778867955055265,
				"gap": 13.298437673282478
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "p7Ih1mDb",
			"type": "text",
			"x": 3360.4754275535865,
			"y": 653.5251211413819,
			"width": 153.71983337402344,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1737368576,
			"version": 58,
			"versionNonce": 1424235520,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ff5EIQo5YFW3H2_b14oK8",
					"type": "arrow"
				}
			],
			"updated": 1717265348370,
			"link": null,
			"locked": false,
			"text": "normal MLP\nchanging 4 to 9",
			"rawText": "normal MLP\nchanging 4 to 9",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "normal MLP\nchanging 4 to 9",
			"lineHeight": 1.25
		},
		{
			"id": "5K4k4SjJ",
			"type": "text",
			"x": 2842.9666943136126,
			"y": 694.7641770162313,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1562977280,
			"version": 2,
			"versionNonce": 1953537024,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717264949416,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "TiKzpypCOrHpirTCTP1NB",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "SW6ji4tQ",
			"type": "text",
			"x": 2775.1613937613038,
			"y": 571.7685155492525,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1565531136,
			"version": 2,
			"versionNonce": 1900160000,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717264951819,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "HfNA_ISC-BebDxBUajezK",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "etlWGUZQ",
			"type": "text",
			"x": 2950.1936812335434,
			"y": 420.3892398975862,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 155229184,
			"version": 2,
			"versionNonce": 801743872,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717264999032,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "E-Bh4Tty2J_jW7JTDnGaj",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "PG5sGiZD",
			"type": "text",
			"x": 2986.4616326917553,
			"y": 455.08032390109304,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 541565952,
			"version": 2,
			"versionNonce": 1391074304,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717265002869,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "xHmtOzCuPbcAktnxGRmy4",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "hAiwyixz",
			"type": "text",
			"x": 3739.852219455492,
			"y": 528.5019036839602,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 120890368,
			"version": 2,
			"versionNonce": 875371520,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717265326991,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "-pQNalE5PSsVwv9JbBvdD",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "9wTJGu0v",
			"type": "text",
			"x": 3646.8982572080577,
			"y": 650.809748746375,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 987438080,
			"version": 2,
			"versionNonce": 1812407296,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717265340795,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ff5EIQo5YFW3H2_b14oK8",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#ffffff",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 822.254645595503,
		"scrollY": 2371.7885877201293,
		"zoom": {
			"value": 0.20044064543985562
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