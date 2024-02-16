---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Structured Prediction and EBMs ^yCpBWxEM

Motivation ^hOaqEBcX

So far we have trained neural networks to output something quite
uniform and simple i.e Class index/probability, Number prediction

In other cases we want to output a structure that is much more complex
or even a sequence of complex structures (e.g machine translation does not have a fixed
length uniform output, Question/answer etc...)
Those outputs are not random, theyre structured and follow certain constraints, rules or
underlying dynamics such as energy functions ^GVkCGxZL

Forward v.s Inverse ^fCpDv9uO

Consider the following situation where we are trying to predict a possible value
and there are multiple plausible outputs that can be the outcome of such
prediction (this is quite often the case when dealing with inverse problems) ^iENRjiog

Solution 1 ^nOWBrkfv

Solution 2 ^MSKDdkuK

What we get
from NN ^oyVdMWC4

averaged over
both solutions ^xj4FtRsr

f(x) + noise ^N9B5MDMl

f is not invertible ^xFn3xWm4

We need to change our view of the task
such that it is now 
learning the conditional probability model
p(t | x)

such that we need to minimize the divergence between
the true probability and the learned probability model ^d4r5sUnr

Mixture density networks ^ShSOvj4S

Networks that are based off of a bunch of distributions that represent the outputs
such that we want to learn more about those distributions and the likelihood
of our point belonging to it ^jZrpKEuC

%%***>>>text element-link:[[Expectation Maximization]]<<<***%%Think GMM in
Expectation Maximization ^q3BX2cRo

Vector x ^ldQLf7N6

NN ^4I0cI0eU

Parameter
vector ^NqL7sPZh

Mixture model ^SGOpfTXn

Conditional
probability
density ^hTt9iiAI

Prior of
distribution ^9yptzKys

Optimize the Likelihood
of this model ^7qY3W80C

These parameters are subject
to certain constraints which can be
modeled in the output layer ^k3mwOHSn

The problem with GMMs ^lFPIGqLQ

Gaussian mixture models capture localized
high density spots in our space and identify them
as a distribution, but this gets rather out of
hand with global effects and spaces where
our data is distributed across every possible
corner of our space IN HIGH DIMENSIONAL space
for example when using pictures ^kz26hJV9

Thus it is better to use Boltzmann machines
BMs or rather RBMs are quite good at understanding
global effects by drawing conclusions between inputs and outputs
without learning features specific to that input... only the transitions that
lead to the output aka Global effects ^2rJtXctP

Conditional Restricted Boltzmann Machines
(CRBM) ^EfWErfAq

CRBMs is a system of binary vairables composed of an input x, an output
y and a latent state h.
Usually it involves a visible layers (as inputs) and a hidden layer (as latent variables)
 "restricted" indicates no two nodes from the same layer have a connection between them
CRBMs try to learn global effects and patterns by taking in an input and its output
and trying to draw a conclusion on how to transition from one to another by
updating the weights and learning the latent variable

CRBMs are governed by an energy function:
 ^yno6CSSB

Energy functions are functions
that get as an input the current
state of a system and output its energy
theyre often used in order to control
the system to head in a specific direction ^c6UkSlVr

and the system associates each state of x,y,h to
a probability ^mY4dmr91

Z being a normalization term like in softmax
aka the sum of all configurations and is generally intractable in this form ^XCfNnU1I

problem:
h is a latent variable that we need to learn
we do not have h in order to use these functions ^4O1uJepR

Solution:
Marginalize these functions over h ^TOvu25ld

Free energy
function describing how present (well aligned) the
features in W are in x and how present the features
described in U are in y ^LYFgxpDw

Can be interpreted as a two-layer neural network.
The lower the free energy the more likely the joint configuration
(x,y) is to occur in the wild!

Thus we perform coordinate gradient descent where we set x to a certain
value and minimize according to y then set y to a certain value and minimize
according to x ^NsnRldnX

We would like to proceed with a stochastic gradient descent procedure

the gradient of our objective is given by ^97FLdIse

(soft on/off value
indicating how well
present the feature
in W is in x) ^Bwex73Og

Expectation
over the observations ^823kxVcE

expectation over
the probability distribution
built by the model ^NIYGEezX

aka take h out of the context
and only give in possible values of
x and y given their joint distribution ^G2vpdjAp

This can be approximated by using methods like Gibbs sampling
which is a method to sample from multivariate distributions ^IilxecgA

Sampling from p(x,y) is difficult whereas
sampling from p(x | y) and p(x | y) is quite easy
Gibbs sampling allows us to infer the joint from the latter ^4XWmxNpK

1) initialize the values

2) sample x from the constant y from the last step

3) sample y from the constant x from the last step

4) repeat 2 and 3 ^zIqKHY4M

Standard CRBM ^hMX9RftN

Higher order CRBM ^IDNhkZTU

Additive ^T6yNUCsn

Multiplicative ^IsGKaqfi

p(hj | x) ^2oRRUKNl

Energy Based learning ^JVhQxCK7

Energy-based learning is a general framework for performing structured
predictions with neural networks it associates to each
input-output pair a score, The predicted output is the one that
yields the highest score aka lowest energy ^wfItyR5N

These models are trained via the Push pull model ^rhybqslE

More on this later! ^qyAhYdf0

high energy is associated
with low probability ^mBQ9FikD

We notice that we can represent the
conditional distributions in a much
easier way than the joint distribution
of the latent and in the input ^4urkPr8F

the hidden units are
conditionally independent
given x due to a local markov
property (the restriction) ^d3sokiXG

Since h and x are given via bernoulli distributions, we can
derive the following ^9ezLqFic

note that the conditional relation is symmetric between
the latent and the input ^sRuClUB7

derivation over x
can be done similarly to y ^URNrxPjD

softplus which is a smooth version
of relu ^gOtDtMCU

Contrastive divergence
(Training CRBM) ^G8Dtv27s

Our training objective is to maximization of the average data Log-likelihood ^iy0rUwLi

The same can be done for y
We are trying to minimize the difference between them ^RytkxhGN

positive phase ^s05ZMlzx

negative phase ^fSvKvZmn

This term is generally hard to compute
over all values of x and y ^RGwPqEYv

What this really is doing is the push pull approach ^9xlWtFLJ

Since we want to associate low energy with high probability and we want
to increase the probability of observing xi given our parameters
and decrease the chance of finding random unrelated points samples from
our model x,y given our parameters ^OV9uivBc

This gradient is the direction of the steepest ascent on the loss function

the first term represents how apparent the features of xi are in the dataset
the second term represents how apparent the features of xi are in our models probability distribution

if this term is very high, it means that this point is very likely to appear in the datset
but is not very likely to appear in our model! which is bad because we want our model
to represent the dataset well THUS steepest ascent ^JTE59MnD

Increasing the energy of things we dont want to sample from our probability distribution
that we built (aka lowering their prob)
Decreasing the energy of things we do want to sample from our models probability
distribution (aka increasing their prob) ^1K61umkF


# Embedded files
0edd9c2d94201837a21fb4a0d69930b86e0f8193: $$p(h|x) = \Pi_j p(h_j|x)$$
d68fab0532591d3932daafad444bb1016db263c2: $$p(h_j | x) = \text{ sigmoid}(W_{j:}x)$$
ebf34d15c595014e0cea4549b73b2b759ff83303: $$p(x_k | h) = \text{ sigmoid}(h^TW_{:k})$$
5d22dcd633d309a4aa25ea8331373349eb1c3330: $$p(x)$$
3e3265aacc4691dfd3d08c74a861d55d6aa4a0a1: [[Pasted Image 20240127190909_702.png]]
a5b0374752dfb54041fdf8d5c93d765cb549e4a3: [[Pasted Image 20240127191951_013.png]]
a124003092c327e18715bd3c4334e4d1e470bcfb: [[Pasted Image 20240127192041_658.png]]
9e9a0b97f4802026311d1788a9a338107a233460: [[Pasted Image 20240127192144_068.png]]
a222ab9a8e5d7bd8c568f9f71ddb8bef5ec0da2b: [[Pasted Image 20240127192229_080.png]]
1aed2ca66ab831139587a32ac46cfbc96a0ace5d: [[Pasted Image 20240127192555_100.png]]
0732dc9282a0e9f4feaef8974b644bb34c458fa9: [[Pasted Image 20240127192642_116.png]]
f0b64e743b0df6337ecd066100b51279963b67c8: [[Pasted Image 20240127192845_127.png]]
63e2c0de5a6dd97eadbd7e56eca4a80e06666d03: [[Pasted Image 20240127192957_160.png]]
3f0c6a98da54be803ba992476fda0eca5f7393b5: [[Pasted Image 20240127193013_174.png]]
d0d1d36cc01a3c23754ae18d7782b8b99eb0a196: [[Pasted Image 20240127193507_205.png]]
0cc2d4da6a9879d99c6f2320990680238d585b86: [[Pasted Image 20240127195937_384.png]]
e0dea364c7011de73d9677b23a6e3b6be647868d: [[Pasted Image 20240127200037_389.png]]
6d5ecdc71557037be5b1a79e541cbffd92613064: [[Pasted Image 20240127200528_467.png]]
bbb32d99227583705b743363c020f83d9727deab: [[Pasted Image 20240127200836_494.png]]
a0ee93c7c23aa945852fa7391fb107d5e49eb93c: [[Pasted Image 20240127200906_496.png]]
50c36a584ee9647a13762db7081bdb75ade49b1b: [[Pasted Image 20240127201130_542.png]]
d7e7a54e673a3f3a9b8fbb07703258013bbcb761: [[Pasted Image 20240127201357_571.png]]
6fa4af893c110fe256a85c5e2c3b5f9e4b29fcf1: [[Pasted Image 20240127201442_585.png]]
fe2b3efcf3c0208afe36ddc82f95c97868a12728: [[Pasted Image 20240127201800_635.png]]
5399d3937af064035d71662a3745b46f3012d035: [[Pasted Image 20240127203437_789.png]]
e0afc5abe8fa25061d8fd314a8a40f61b3f3ea83: [[Pasted Image 20240127203501_810.png]]
cd4eb941ea5c5764e065c0b5c14bfd4c65721171: [[Pasted Image 20240127203516_811.png]]
8a49189668af2e76c9370ae00b59946c8340461f: [[Pasted Image 20240127203531_813.png]]
0fb9e45d1795c97223225c72c522896dd707a6e2: [[Pasted Image 20240127203546_814.png]]
384f2051841dbda422d4792a1acc47c67bca0684: [[Pasted Image 20240131173532_290.png]]
1a0b42c9e99c729659c286778394c8840c120f8e: [[Pasted Image 20240131181242_851.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.18",
	"elements": [
		{
			"id": "ONz85rxAuNY08-OnoJVOq",
			"type": "image",
			"x": 256.5692031194028,
			"y": 1903.4757373196837,
			"width": 506.1705424460592,
			"height": 254.1216564450731,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 689328760,
			"version": 424,
			"versionNonce": 2021533192,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "384f2051841dbda422d4792a1acc47c67bca0684",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 180,
			"versionNonce": 1919229560,
			"isDeleted": false,
			"id": "kLHxcnE0I3gvyr4yvZK52",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 736.845595213609,
			"y": 1200.4036188172684,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 352.85834247275113,
			"height": 233.3302629738679,
			"seed": 419488272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0dea364c7011de73d9677b23a6e3b6be647868d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 368,
			"versionNonce": 685516040,
			"isDeleted": false,
			"id": "MJc9csI5-Cawplqq2EcM8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 978.7409578088791,
			"y": 158.97763789270834,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 139,
			"height": 154,
			"seed": 891767024,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9e9a0b97f4802026311d1788a9a338107a233460",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 178,
			"versionNonce": 2116718456,
			"isDeleted": false,
			"id": "pLpmxmawcv6MJb2WwSdZE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1087.4144950795617,
			"y": 552.181663717298,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 307.9423180575037,
			"height": 53.62179667667975,
			"seed": 176024080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e3265aacc4691dfd3d08c74a861d55d6aa4a0a1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 59,
			"versionNonce": 992101384,
			"isDeleted": false,
			"id": "afUXP3smGWzx7gKHB0aMm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -185.75,
			"y": -416.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 361,
			"height": 133,
			"seed": 1419555856,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yCpBWxEM"
				}
			],
			"updated": 1706720437555,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 840556664,
			"isDeleted": false,
			"id": "yCpBWxEM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -111.23265803737496,
			"y": -374.7804134489054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 211.69976806640625,
			"height": 50,
			"seed": 1049304592,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Structured Prediction\nand EBMs",
			"rawText": "Structured Prediction and EBMs",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "afUXP3smGWzx7gKHB0aMm",
			"originalText": "Structured Prediction and EBMs",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 2102166280,
			"isDeleted": false,
			"id": "hOaqEBcX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -78.14634704589844,
			"y": -245.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 142.7725830078125,
			"height": 35,
			"seed": 2093223952,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Motivation",
			"rawText": "Motivation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Motivation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 655,
			"versionNonce": 771166584,
			"isDeleted": false,
			"id": "GVkCGxZL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -464.6195373535156,
			"y": -213.1068455063164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 897.7390747070312,
			"height": 200,
			"seed": 2119433744,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mFNLB_miad-yx4tlk69Hz",
					"type": "arrow"
				},
				{
					"id": "aIjQqKtfT31UjZtlQbJ8P",
					"type": "arrow"
				}
			],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So far we have trained neural networks to output something quite\nuniform and simple i.e Class index/probability, Number prediction\n\nIn other cases we want to output a structure that is much more complex\nor even a sequence of complex structures (e.g machine translation does not have a fixed\nlength uniform output, Question/answer etc...)\nThose outputs are not random, theyre structured and follow certain constraints, rules or\nunderlying dynamics such as energy functions",
			"rawText": "So far we have trained neural networks to output something quite\nuniform and simple i.e Class index/probability, Number prediction\n\nIn other cases we want to output a structure that is much more complex\nor even a sequence of complex structures (e.g machine translation does not have a fixed\nlength uniform output, Question/answer etc...)\nThose outputs are not random, theyre structured and follow certain constraints, rules or\nunderlying dynamics such as energy functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So far we have trained neural networks to output something quite\nuniform and simple i.e Class index/probability, Number prediction\n\nIn other cases we want to output a structure that is much more complex\nor even a sequence of complex structures (e.g machine translation does not have a fixed\nlength uniform output, Question/answer etc...)\nThose outputs are not random, theyre structured and follow certain constraints, rules or\nunderlying dynamics such as energy functions",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 283,
			"versionNonce": 500621832,
			"isDeleted": false,
			"id": "mFNLB_miad-yx4tlk69Hz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -482.61902783050743,
			"y": -128.41928803810703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 463.9001966303174,
			"height": 122.10639906327151,
			"seed": 327094800,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"customData": {},
			"startBinding": {
				"elementId": "GVkCGxZL",
				"focus": 0.09169289759716182,
				"gap": 17.99949047699181
			},
			"endBinding": {
				"elementId": "fCpDv9uO",
				"focus": -0.2647624156764151,
				"gap": 15.508894092035575
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
					-401.6420664500141,
					-4.856725562604595
				],
				[
					-463.9001966303174,
					117.24967350066692
				]
			]
		},
		{
			"type": "text",
			"version": 146,
			"versionNonce": 2030445176,
			"isDeleted": false,
			"id": "fCpDv9uO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1061.6047009781232,
			"y": 4.339279554595464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 273.701171875,
			"height": 35,
			"seed": 729315344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mFNLB_miad-yx4tlk69Hz",
					"type": "arrow"
				}
			],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Forward v.s Inverse",
			"rawText": "Forward v.s Inverse",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Forward v.s Inverse",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 527,
			"versionNonce": 465395976,
			"isDeleted": false,
			"id": "iENRjiog",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1320.721230368766,
			"y": 48.81296302433992,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 785.7791748046875,
			"height": 75,
			"seed": 799011344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8tzjjTI9e2LuWREJEm_I3",
					"type": "arrow"
				},
				{
					"id": "riZkc_MTqS68J_FZUu8dJ",
					"type": "arrow"
				}
			],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Consider the following situation where we are trying to predict a possible value\nand there are multiple plausible outputs that can be the outcome of such\nprediction (this is quite often the case when dealing with inverse problems)",
			"rawText": "Consider the following situation where we are trying to predict a possible value\nand there are multiple plausible outputs that can be the outcome of such\nprediction (this is quite often the case when dealing with inverse problems)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider the following situation where we are trying to predict a possible value\nand there are multiple plausible outputs that can be the outcome of such\nprediction (this is quite often the case when dealing with inverse problems)",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 255,
			"versionNonce": 302715768,
			"isDeleted": false,
			"id": "wxsgsFVEogIEN0tj_-y3p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1331.8163885167203,
			"y": 309.80698843013835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 201.0278782869441,
			"height": 0.6490248859049643,
			"seed": 616934640,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437555,
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
					201.0278782869441,
					0.6490248859049643
				]
			]
		},
		{
			"type": "arrow",
			"version": 303,
			"versionNonce": 914096136,
			"isDeleted": false,
			"id": "riZkc_MTqS68J_FZUu8dJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1332.6719805045277,
			"y": 313.2293563813677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 0.8555919878073155,
			"height": 175.39635750050553,
			"seed": 1545058320,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iENRjiog",
				"focus": 1.0271220034080628,
				"gap": 14.02003585652227
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
					0.8555919878073155,
					-175.39635750050553
				]
			]
		},
		{
			"type": "text",
			"version": 189,
			"versionNonce": 2135549048,
			"isDeleted": false,
			"id": "nOWBrkfv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1281.3444246604213,
			"y": 322.3046378540729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 73.10415649414062,
			"height": 20,
			"seed": 1849479696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Solution 1",
			"rawText": "Solution 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Solution 1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1578024712,
			"isDeleted": false,
			"id": "kKy2CQuSO27KxhuiLM12x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1324.008997379386,
			"y": 299.1555286667688,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 374619664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1585878392,
			"isDeleted": false,
			"id": "Jr9dBLxkR3NVxd9VhG1zx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1307.7309602422747,
			"y": 301.3259336183836,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1054750736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 586259976,
			"isDeleted": false,
			"id": "H5_QelyZXGhXJ3dPP-z4t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1312.3430707644563,
			"y": 277.99408038852425,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1613918736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1963271800,
			"isDeleted": false,
			"id": "RbQuYbhypYU6FlgryTn0l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1296.6076348652489,
			"y": 296.44252247725024,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 460909584,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 639671560,
			"isDeleted": false,
			"id": "Y73X7RSL2oThHwaG3dfAt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1309.358763955986,
			"y": 287.2183014328873,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0,
			"seed": 1121560080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.271300618951841,
					0
				],
				[
					-0.271300618951841,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1065981816,
			"isDeleted": false,
			"id": "VWi_ey5rImRSEeiHK5qoU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1278.9730946333784,
			"y": 289.38870638450214,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 252583440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 143,
			"versionNonce": 152550408,
			"isDeleted": false,
			"id": "PT7t6G9RpdGH-KGlUr7IU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1269.7488735890156,
			"y": 299.42682928572066,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.8139018568556367,
			"height": 1.3565030947592618,
			"seed": 1734613008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.271300618951841
				],
				[
					0.5426012379037388,
					-1.3565030947592618
				],
				[
					0.8139018568556367,
					-1.3565030947592618
				],
				[
					0.8139018568556367,
					-1.3565030947592618
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 39315576,
			"isDeleted": false,
			"id": "UonZV0Ay0eonVCnROx88G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1293.0807268188748,
			"y": 273.6532704852947,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1578552336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 142,
			"versionNonce": 1574107912,
			"isDeleted": false,
			"id": "OT0q1-rRE7mFTM5S7rm7g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1286.0269107261265,
			"y": 299.42682928572066,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.0852024758074208,
			"height": 0.8139018568555798,
			"seed": 1338213904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5426012379037388,
					-0.271300618951841
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 144,
			"versionNonce": 1496586616,
			"isDeleted": false,
			"id": "NW6-5iHY2yEWlJYcipv9G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1251.3004315002895,
			"y": 302.1398354752392,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.085202475807364,
			"height": 0.542601237903682,
			"seed": 276675600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					0.271300618951841
				],
				[
					0.542601237903682,
					0
				],
				[
					0.813901856855523,
					0
				],
				[
					1.085202475807364,
					-0.271300618951841
				],
				[
					1.085202475807364,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 382622216,
			"isDeleted": false,
			"id": "40P79xiRbg6GLnkk4-HRf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1273.0044810164377,
			"y": 274.19587172319837,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 278720016,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 1197615736,
			"isDeleted": false,
			"id": "k3jXJYiciNuTqQahklK0F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1244.7892166454449,
			"y": 276.63757729376505,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0,
			"seed": 598009872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					0
				],
				[
					0.271300618951841,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 143,
			"versionNonce": 1996871944,
			"isDeleted": false,
			"id": "tBgHBF45ye0HrGwZFEb7Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1249.4013271676265,
			"y": 286.1330989570799,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.8991043326630006,
			"height": 0.8139018568555798,
			"seed": 925392912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					0
				],
				[
					0.8139018568555798,
					-0.5426012379037388
				],
				[
					1.8991043326630006,
					-0.8139018568555798
				],
				[
					1.8991043326630006,
					-0.8139018568555798
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1202068344,
			"isDeleted": false,
			"id": "WuKnQScjECETe-acRotE3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1221.4573634155856,
			"y": 293.7295162877317,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1879381008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 32864264,
			"isDeleted": false,
			"id": "IxH9_WKqPobUzs_wUwXhU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1264.0515605910266,
			"y": 284.5052952433688,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.271300618951841,
			"seed": 167169552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					-0.271300618951841
				],
				[
					0.271300618951841,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1547955320,
			"isDeleted": false,
			"id": "APzmsrnxs9poRllZB9fL5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1227.6972776514783,
			"y": 277.45147915062057,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1784104464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1805203208,
			"isDeleted": false,
			"id": "B-_t1AAAL6H5XmwljxUIL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1239.9058055043117,
			"y": 255.2048283965687,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1918779408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 520068472,
			"isDeleted": false,
			"id": "Bh9h9fy9Y9RroN_uqO3L-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1204.365424421619,
			"y": 263.07254634617243,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1750039056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 141366792,
			"isDeleted": false,
			"id": "lEbrKG67Pf-OgQvf8_7-R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1218.4730566071153,
			"y": 245.7093067332538,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.5426012379037388,
			"seed": 22213648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.5426012379037388
				],
				[
					0,
					0.5426012379037388
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1360866936,
			"isDeleted": false,
			"id": "gGfJHpMmeoIC0S3TRT46X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1203.8228231837152,
			"y": 292.3730131929725,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 930114576,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 142,
			"versionNonce": 1030558984,
			"isDeleted": false,
			"id": "WMi5dekR8bL67ZLzE71eq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.9304553692116,
			"y": 268.4985587252095,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.0852024758074208,
			"height": 0.8139018568555798,
			"seed": 2013341200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.542601237903682,
					-0.5426012379037388
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1801494392,
			"isDeleted": false,
			"id": "joB5toDrIKm0iv8MEPSBp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1201.6524182321004,
			"y": 251.13531911229086,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1043815440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 1880437768,
			"isDeleted": false,
			"id": "XeW11n9Qce1L3xVkeLUun",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1233.665891268419,
			"y": 232.95817764251672,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.542601237903682,
			"seed": 921572880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					-0.542601237903682
				],
				[
					0.271300618951841,
					-0.542601237903682
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 772665464,
			"isDeleted": false,
			"id": "MYOSTHLMbYPmp7lZx3Jw8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1210.3340380385598,
			"y": 227.26086464452783,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1567264272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 140,
			"versionNonce": 1986097928,
			"isDeleted": false,
			"id": "ZYftmE91_yZRU64etDbqt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1231.495486316804,
			"y": 213.42453307798337,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 64391184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 820584824,
			"isDeleted": false,
			"id": "RWSSbAo5txk9l5Bw24IWz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.387854131308,
			"y": 206.64201760418706,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.271300618951841,
			"seed": 374129168,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.271300618951841
				],
				[
					0,
					0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 114151944,
			"isDeleted": false,
			"id": "PGHm8NDqjZXUZId-q701J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1197.8542095667744,
			"y": 233.2294782614686,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 998608624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 1932931704,
			"isDeleted": false,
			"id": "4oAE8dqLgE3yI8ueq8t9q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1194.3273015204004,
			"y": 216.95144112435742,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.271300618951841,
			"seed": 1070773488,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.271300618951841,
					-0.271300618951841
				],
				[
					-0.271300618951841,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 676745480,
			"isDeleted": false,
			"id": "wFgBKW1ixMlLmb1Myw5Td",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1240.7197073611671,
			"y": 194.1621891324018,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.813901856855523,
			"height": 0.271300618951841,
			"seed": 689487088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.813901856855523,
					-0.271300618951841
				],
				[
					0.813901856855523,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 1807295352,
			"isDeleted": false,
			"id": "UtdaVr0_UdYkNJxc7xR6a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.6591547502599,
			"y": 195.51869222716107,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1528481008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437555,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 578220040,
			"isDeleted": false,
			"id": "WJE2opXveMbbV0gC8Nkpg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1202.7376207079078,
			"y": 189.82137922917218,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 581675760,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 414577784,
			"isDeleted": false,
			"id": "r5Oe9amDtwbeRFmlpDpp0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1227.4259770325264,
			"y": 177.07025013843509,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.271300618951841,
			"seed": 1893617904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					-0.271300618951841
				],
				[
					0.271300618951841,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 1831579400,
			"isDeleted": false,
			"id": "5AzQgH4PonUH73xe6UJUu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1204.365424421619,
			"y": 172.18683899730178,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1500928240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 142,
			"versionNonce": 267429240,
			"isDeleted": false,
			"id": "oIR7tpgi9J5-dJzalD_bu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1190.8003934740264,
			"y": 199.04560027353517,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.542601237903682,
			"height": 1.6278037137111028,
			"seed": 4177648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.5426012379037388
				],
				[
					0,
					-0.8139018568555798
				],
				[
					0.271300618951841,
					-1.0852024758074208
				],
				[
					0.542601237903682,
					-1.6278037137111028
				],
				[
					0.542601237903682,
					-1.6278037137111028
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 552635912,
			"isDeleted": false,
			"id": "afHzz1Vp52-qIkaBU9cn2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1187.0021848087003,
			"y": 181.41106004166477,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 505998576,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 246232696,
			"isDeleted": false,
			"id": "QcpfDBQMKyHyB4wQ38FrD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.387854131308,
			"y": 157.80790619285358,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 260756208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 1723960584,
			"isDeleted": false,
			"id": "QGDio6qpUEYTQehGztezJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1201.1098169941968,
			"y": 154.00969752752763,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.27130061895189783,
			"height": 0,
			"seed": 758020336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.27130061895189783,
					0
				],
				[
					-0.27130061895189783,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 162506616,
			"isDeleted": false,
			"id": "lbl-lZfMkhv7FweVaWFZf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1224.1703696051043,
			"y": 151.56799195696095,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.3565030947592618,
			"height": 0,
			"seed": 2020770032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.3565030947592618,
					0
				],
				[
					1.3565030947592618,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 1746578440,
			"isDeleted": false,
			"id": "4HIf6TVK1LmYiZRTsDAH_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1205.7219275163782,
			"y": 144.5141758642128,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0,
			"seed": 494045424,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.271300618951841,
					0
				],
				[
					-0.271300618951841,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 1027340408,
			"isDeleted": false,
			"id": "qjxYzJN5VVXUJdsToaprO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1228.511179508334,
			"y": 159.97831114446836,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1580110064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 1056434952,
			"isDeleted": false,
			"id": "BDPH3LgtToFIaqSt6xGcZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1176.1501600506263,
			"y": 165.13302290455357,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 541259504,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 138,
			"versionNonce": 1024862584,
			"isDeleted": false,
			"id": "Tsy0MGVHtF4whuRZgHNhl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1188.3586879034597,
			"y": 164.86172228560173,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2108234992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 298,
			"versionNonce": 1708476936,
			"isDeleted": false,
			"id": "VtRfCRuZHefalqUjg_hEK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -714.6513855069493,
			"y": 309.1543921871067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 192.32561990988972,
			"height": 2.0262134057894627,
			"seed": 1368324336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437556,
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
					192.32561990988972,
					2.0262134057894627
				]
			]
		},
		{
			"type": "arrow",
			"version": 319,
			"versionNonce": 75643512,
			"isDeleted": false,
			"id": "8tzjjTI9e2LuWREJEm_I3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -714.8089002220368,
			"y": 313.274837411056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 0.8555919878073155,
			"height": 175.39635750050553,
			"seed": 1763859184,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iENRjiog",
				"focus": -0.5447592138502519,
				"gap": 14.06551688621056
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
					0.8555919878073155,
					-175.39635750050553
				]
			]
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 665766152,
			"isDeleted": false,
			"id": "MSKDdkuK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -666.3112746125345,
			"y": 318.16165524744173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 80.16017150878906,
			"height": 20,
			"seed": 1006206192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Solution 2",
			"rawText": "Solution 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Solution 2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 105130872,
			"isDeleted": false,
			"id": "E7VHvYRHKOC9BUg6ofVhY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -702.6770274225223,
			"y": 293.6726594521053,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1052496624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 268462088,
			"isDeleted": false,
			"id": "iG8vEvQ_WiHio8FQxZQ-a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -691.0193354303889,
			"y": 294.9679585623423,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2113894640,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1017117816,
			"isDeleted": false,
			"id": "OVOdvTJD355LsncYTzV_F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -682.2760664362888,
			"y": 298.85385589305344,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 937221872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1522935560,
			"isDeleted": false,
			"id": "4Ld8L5XrBnxzRD7QPW2Ja",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -699.7626044244889,
			"y": 275.53847190878656,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1437336816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 962178424,
			"isDeleted": false,
			"id": "66Ti5CnID1gsbgFg21mpy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -663.4942293378515,
			"y": 274.2431727985495,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 532998896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 1685849608,
			"isDeleted": false,
			"id": "zTF3NB6sojyjr5gzi_Sl6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -682.9237159914073,
			"y": 270.6811002453976,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.32382477755925265,
			"seed": 494899440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.32382477755925265
				],
				[
					0,
					-0.32382477755925265
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 157,
			"versionNonce": 901070456,
			"isDeleted": false,
			"id": "xk1KzHqSQo9oSePEwD6ob",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -691.0193354303889,
			"y": 244.7751180406566,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 2.590598220474078,
			"height": 0,
			"seed": 192387312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6476495551185053,
					0
				],
				[
					-0.971474332677758,
					0
				],
				[
					-1.2952991102370106,
					0
				],
				[
					-1.9429486653555728,
					0
				],
				[
					-2.590598220474078,
					0
				],
				[
					-2.590598220474078,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 438174984,
			"isDeleted": false,
			"id": "VFB7qFvK688nVKF7evO4S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -690.0478610977111,
			"y": 255.13751092255296,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1218160880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 578203512,
			"isDeleted": false,
			"id": "lzzUL0tZ8wCNkGGNLzi2w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -700.0864292020483,
			"y": 257.0804595879086,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.3238247775593095,
			"height": 0.9714743326778148,
			"seed": 329715440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3238247775593095,
					-0.9714743326778148
				],
				[
					0.3238247775593095,
					-0.9714743326778148
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1764238344,
			"isDeleted": false,
			"id": "Zx-9mgmqX3PKBgYxW27ZS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -658.9606824520218,
			"y": 243.15599415286027,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1257248496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 155,
			"versionNonce": 937558136,
			"isDeleted": false,
			"id": "-4DYdmCazWJK79WHXJ0H6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -695.8767070937778,
			"y": 227.28858005245638,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 2.2667734429148254,
			"height": 0.6476495551185621,
			"seed": 1038761200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32382477755925265,
					0
				],
				[
					1.9429486653555728,
					0.6476495551185621
				],
				[
					2.2667734429148254,
					0.6476495551185621
				],
				[
					2.2667734429148254,
					0.6476495551185621
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 798384904,
			"isDeleted": false,
			"id": "VFjAOccPyeVh5auBUnrRQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -668.6754257787998,
			"y": 253.84221181231595,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2142488816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 96153976,
			"isDeleted": false,
			"id": "GOYMnJyC3T1PcWCypDjjG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -672.8851478870702,
			"y": 228.58387916269345,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.32382477755925265,
			"height": 0.6476495551185053,
			"seed": 338898672,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.32382477755925265,
					0.6476495551185053
				],
				[
					-0.32382477755925265,
					0.6476495551185053
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 736412168,
			"isDeleted": false,
			"id": "v-HsqWf3Ykj0ihtNvQPu4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -705.2676256429964,
			"y": 239.59392159970838,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 342636272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 54936184,
			"isDeleted": false,
			"id": "yy9nvwiOshBLSdVL3nsxO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -668.9992505563589,
			"y": 208.18291817645985,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.6476495551185053,
			"height": 0.3238247775593095,
			"seed": 995777776,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6476495551185053,
					0.3238247775593095
				],
				[
					0.6476495551185053,
					0.3238247775593095
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 1829716232,
			"isDeleted": false,
			"id": "hIJRFa8AxE6BtOlcFg2CO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -657.9892081193441,
			"y": 229.23152871781195,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.32382477755925265,
			"seed": 1871471856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.32382477755925265
				],
				[
					0,
					-0.32382477755925265
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 524759928,
			"isDeleted": false,
			"id": "RqDXscrTfxeCLkbcRlyNs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -686.4857885445592,
			"y": 210.12586684181548,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 377122032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1116856328,
			"isDeleted": false,
			"id": "odPuxZjN0Es3jEF5Rv5Ub",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -633.7023498023993,
			"y": 200.0872987374783,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 122442480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1342309496,
			"isDeleted": false,
			"id": "V9Z8dW1iPmgCteQqnRDM3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -634.9976489126364,
			"y": 221.1359092788304,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 442497264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 156,
			"versionNonce": 745053960,
			"isDeleted": false,
			"id": "La5FOv4UQsa9dPHpjunWp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -644.388567461855,
			"y": 214.01176417252663,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.6476495551185053,
			"height": 1.9429486653555728,
			"seed": 2047696624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.32382477755925265,
					0
				],
				[
					-0.6476495551185053,
					0.6476495551185053
				],
				[
					-0.6476495551185053,
					1.61912388779632
				],
				[
					-0.6476495551185053,
					1.9429486653555728
				],
				[
					-0.6476495551185053,
					1.9429486653555728
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 591050104,
			"isDeleted": false,
			"id": "8OYoX7irL2aojDpwHEgPD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -637.9120719106697,
			"y": 239.59392159970838,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1435143408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1259306504,
			"isDeleted": false,
			"id": "R_5OflIH-FKPd_L0f0zuI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -623.3399569205029,
			"y": 214.98323850520438,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1926263536,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1312114296,
			"isDeleted": false,
			"id": "gdUy3GBKYf3Yuxo-BACe1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -605.8534189323027,
			"y": 236.35567382411574,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 383260912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1333951752,
			"isDeleted": false,
			"id": "7WreC7VCk3aY1E92LL1Kr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -607.4725428200991,
			"y": 218.86913583591553,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1006206704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1035319160,
			"isDeleted": false,
			"id": "ddCrIUa2W_BqZHjJ8AQOy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -608.4440171527768,
			"y": 204.2970208457487,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1535943920,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1799199752,
			"isDeleted": false,
			"id": "aTSbR3yZNHxrRJjtqfp8g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -617.5111109244363,
			"y": 233.44125082608235,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1307151088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 637536376,
			"isDeleted": false,
			"id": "aU4zZGgcXZYUbA7QbLK0q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -577.3568385070876,
			"y": 213.04028983984887,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 711471344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 1077730056,
			"isDeleted": false,
			"id": "CrQ9cJ3F8uXhWfTxW90K2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -593.2242526074915,
			"y": 208.18291817645985,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.32382477755925265,
			"height": 1.2952991102371243,
			"seed": 660641520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437556,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32382477755925265,
					1.2952991102371243
				],
				[
					0.32382477755925265,
					1.2952991102371243
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 316160376,
			"isDeleted": false,
			"id": "KqmWn2d0AlZl8NHxgIbYv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -575.413889841732,
			"y": 246.71806670601217,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 296066800,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 1358707208,
			"isDeleted": false,
			"id": "tauHNbz08WR4E5bq_f5ZO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -557.6035270759726,
			"y": 213.36411461740812,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.32382477755925265,
			"height": 0.32382477755925265,
			"seed": 321701104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.32382477755925265,
					0.32382477755925265
				],
				[
					-0.32382477755925265,
					0.32382477755925265
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 2005027448,
			"isDeleted": false,
			"id": "cG8maxXJH_SQahbCOb6v8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -588.6907057216617,
			"y": 230.85065260560827,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 921357552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1886894344,
			"isDeleted": false,
			"id": "yHFZdRbaiEsrw_tK6qUK7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -566.6706208476319,
			"y": 228.2600543851342,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1964552944,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 155,
			"versionNonce": 1052916600,
			"isDeleted": false,
			"id": "edVTgG4a0BDuE8P-kqzoS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -572.4994668436987,
			"y": 202.67789695795244,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.9714743326778148,
			"seed": 50878704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.32382477755925265
				],
				[
					0,
					-0.6476495551185053
				],
				[
					0,
					-0.9714743326778148
				],
				[
					0,
					-0.9714743326778148
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 153,
			"versionNonce": 841701384,
			"isDeleted": false,
			"id": "hmuoCWPFS3s6qT4Mlw24z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -556.6320527432948,
			"y": 237.6509729343528,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.3238247775593095,
			"height": 0,
			"seed": 1988945136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3238247775593095,
					0
				],
				[
					0.3238247775593095,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1524370552,
			"isDeleted": false,
			"id": "dDGtC5744duIkD6jv9a7R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -544.9743607511614,
			"y": 214.01176417252663,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1497033968,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1511200520,
			"isDeleted": false,
			"id": "oI7taBz4l-DZdzkSqIcbq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -539.7931643102131,
			"y": 228.58387916269345,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 199021296,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1435745656,
			"isDeleted": false,
			"id": "bx9X8tziL-xIz7PAh14XX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -537.2025660897391,
			"y": 209.47821728669697,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1925216496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1286272520,
			"isDeleted": false,
			"id": "_-jPJrNXmzy2U-zI61prK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -530.0784209834353,
			"y": 234.08890038120092,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2017320688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1613581944,
			"isDeleted": false,
			"id": "kU_byxG6aJFMfbQuBCf72",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -549.1840828594318,
			"y": 203.97319606818945,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 95225072,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 2129589512,
			"isDeleted": false,
			"id": "rh_TcUV-UR852HGFgHuWI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -541.4122881980095,
			"y": 248.01336581624918,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1667623664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1668071288,
			"isDeleted": false,
			"id": "ZXTnUH3t5Q3HY1SRBMD1q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -655.7224346764292,
			"y": 200.41112351503756,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 415273200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 152,
			"versionNonce": 1717244936,
			"isDeleted": false,
			"id": "zTAXb_C40pZgJXB0hiC1k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -599.3769233811174,
			"y": 191.6678545209375,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1276442352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 363,
			"versionNonce": 261492856,
			"isDeleted": false,
			"id": "Garo4KnQLzkHe3aN65_Hc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -695.3286598935833,
			"y": 299.73180957416145,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 161.53655927512813,
			"height": 79.8935329266879,
			"seed": 1573304848,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.538036189224727,
					-48.98581580906409
				],
				[
					32.65721053937608,
					-79.8935329266879
				],
				[
					74.35347042447233,
					-79.0187862158117
				],
				[
					132.08675334229792,
					-78.4356217418943
				],
				[
					161.53655927512813,
					-76.68612832014202
				]
			]
		},
		{
			"type": "line",
			"version": 334,
			"versionNonce": 1760252680,
			"isDeleted": false,
			"id": "yk24uY2KCXh1culhv5RKD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1319.1049529639147,
			"y": 289.4501147190446,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 110.72582127453643,
			"height": 132.51471833693813,
			"seed": 593146608,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.862181895324,
					0.9729286263689687
				],
				[
					90.23913009572397,
					-6.8105003845829515
				],
				[
					99.72518420282165,
					-36.48482348883721
				],
				[
					108.07832828784387,
					-69.45587962841716
				],
				[
					110.72582127453643,
					-131.54178971056916
				]
			]
		},
		{
			"type": "arrow",
			"version": 126,
			"versionNonce": 1819099512,
			"isDeleted": false,
			"id": "KER7QJLChPqrkcthVh9Kp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1136.682366544363,
			"y": 223.15534037048212,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 68.51060077010538,
			"height": 0,
			"seed": 333315600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
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
					68.51060077010538,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 118,
			"versionNonce": 1293660680,
			"isDeleted": false,
			"id": "i3qnYzbMqaNGHvAo9J1up",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -739.0762013607159,
			"y": 217.03832244457988,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 79.11343184166924,
			"height": 0.40780119506018764,
			"seed": 448533232,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
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
					-79.11343184166924,
					0.40780119506018764
				]
			]
		},
		{
			"type": "arrow",
			"version": 123,
			"versionNonce": 1765167736,
			"isDeleted": false,
			"id": "w0MnWrqDm5D0WAZGaEBxJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1031.8774594139043,
			"y": 308.79359133311385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 196.1523748239327,
			"height": 2.0390059753007677,
			"seed": 191548944,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
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
					196.1523748239327,
					2.0390059753007677
				]
			]
		},
		{
			"type": "arrow",
			"version": 153,
			"versionNonce": 703082760,
			"isDeleted": false,
			"id": "4IrBmxsv9uHHjMY0HLSv3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1031.8774594139043,
			"y": 309.201392528174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 4.893614340721854,
			"height": 164.75168280430097,
			"seed": 316412432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
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
					4.893614340721854,
					-164.75168280430097
				]
			]
		},
		{
			"type": "text",
			"version": 140,
			"versionNonce": 1823818616,
			"isDeleted": false,
			"id": "oyVdMWC4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -992.5156093016708,
			"y": 316.92806789983297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 99.85621643066406,
			"height": 40,
			"seed": 482830064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What we get\nfrom NN",
			"rawText": "What we get\nfrom NN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What we get\nfrom NN",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 197,
			"versionNonce": 1456263176,
			"isDeleted": false,
			"id": "Op3JQp9x-aEUssJ5Y2QED",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1028.615049853423,
			"y": 305.53118177263264,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 148.439635001895,
			"height": 123.56376210322571,
			"seed": 1461518864,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					148.439635001895,
					-123.56376210322571
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 1697518712,
			"isDeleted": false,
			"id": "xj4FtRsr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -938.6623373783343,
			"y": 137.62347506712865,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 112.08023071289062,
			"height": 40,
			"seed": 1006959856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "averaged over\nboth solutions",
			"rawText": "averaged over\nboth solutions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "averaged over\nboth solutions",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 156,
			"versionNonce": 1539673864,
			"isDeleted": false,
			"id": "N9B5MDMl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -622.2893102008416,
			"y": 160.9188635460893,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 92.09617614746094,
			"height": 20,
			"seed": 675646704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "f(x) + noise",
			"rawText": "f(x) + noise",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f(x) + noise",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1482999160,
			"isDeleted": false,
			"id": "xFn3xWm4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1197.8017072915027,
			"y": 129.15942329165614,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 137.95230102539062,
			"height": 20,
			"seed": 2115783184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "f is not invertible",
			"rawText": "f is not invertible",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f is not invertible",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 461,
			"versionNonce": 1632529928,
			"isDeleted": false,
			"id": "d4r5sUnr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1199.9486759717215,
			"y": 377.1816645148332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 531.1994018554688,
			"height": 175,
			"seed": 1564124688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We need to change our view of the task\nsuch that it is now \nlearning the conditional probability model\np(t | x)\n\nsuch that we need to minimize the divergence between\nthe true probability and the learned probability model",
			"rawText": "We need to change our view of the task\nsuch that it is now \nlearning the conditional probability model\np(t | x)\n\nsuch that we need to minimize the divergence between\nthe true probability and the learned probability model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We need to change our view of the task\nsuch that it is now \nlearning the conditional probability model\np(t | x)\n\nsuch that we need to minimize the divergence between\nthe true probability and the learned probability model",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "arrow",
			"version": 276,
			"versionNonce": 1939691128,
			"isDeleted": false,
			"id": "aIjQqKtfT31UjZtlQbJ8P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 461.1428194412597,
			"y": -113.40212531899596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 409.7002731576472,
			"height": 135.52324674412267,
			"seed": 78329072,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GVkCGxZL",
				"focus": -0.12480778621995965,
				"gap": 28.023282087744064
			},
			"endBinding": {
				"elementId": "ShSOvj4S",
				"focus": -0.14661110525680862,
				"gap": 14.444017606170178
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
					360.59690868076405,
					10.44039480282754
				],
				[
					409.7002731576472,
					135.52324674412267
				]
			]
		},
		{
			"type": "text",
			"version": 134,
			"versionNonce": 543386888,
			"isDeleted": false,
			"id": "ShSOvj4S",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 738.177005125837,
			"y": 36.565139031296894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 342.66546630859375,
			"height": 35,
			"seed": 606791696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aIjQqKtfT31UjZtlQbJ8P",
					"type": "arrow"
				}
			],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Mixture density networks",
			"rawText": "Mixture density networks",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mixture density networks",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 419,
			"versionNonce": 463193976,
			"isDeleted": false,
			"id": "jZrpKEuC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 488.2699361118073,
			"y": 75.41373561153978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 855.01904296875,
			"height": 75,
			"seed": 389381648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Networks that are based off of a bunch of distributions that represent the outputs\nsuch that we want to learn more about those distributions and the likelihood\nof our point belonging to it",
			"rawText": "Networks that are based off of a bunch of distributions that represent the outputs\nsuch that we want to learn more about those distributions and the likelihood\nof our point belonging to it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Networks that are based off of a bunch of distributions that represent the outputs\nsuch that we want to learn more about those distributions and the likelihood\nof our point belonging to it",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 223,
			"versionNonce": 1384156168,
			"isDeleted": false,
			"id": "6sLQLwr_aXXenKcp1_MWw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1242.1576159858048,
			"y": 145.25216349760035,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 287.57397904084587,
			"height": 67.19693480100182,
			"seed": 1546243600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "q3BX2cRo",
				"focus": -0.22899412761956003,
				"gap": 5.636171824485018
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
					119.22036819532548,
					59.24891025464672
				],
				[
					287.57397904084587,
					-7.9480245463551
				]
			]
		},
		{
			"type": "text",
			"version": 148,
			"versionNonce": 2091128952,
			"isDeleted": false,
			"id": "q3BX2cRo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1439.4414812286636,
			"y": 81.66796712676023,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 248.4997100830078,
			"height": 50,
			"seed": 1247116528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6sLQLwr_aXXenKcp1_MWw",
					"type": "arrow"
				}
			],
			"updated": 1706720437557,
			"link": "[[Expectation Maximization]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Think GMM in\nExpectation Maximization",
			"rawText": "Think GMM in\nExpectation Maximization",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Think GMM in\nExpectation Maximization",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 487,
			"versionNonce": 564251400,
			"isDeleted": false,
			"id": "gXU4LCNgK-xTHfEIb7x9M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5537766937367596,
			"x": 699.2770374803059,
			"y": 165.59288676298593,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 168,
			"height": 140,
			"seed": 1436977680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a5b0374752dfb54041fdf8d5c93d765cb549e4a3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 478,
			"versionNonce": 444221816,
			"isDeleted": false,
			"id": "vFyMwVtP8VCMi_zWKPbNP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 847.9083541506321,
			"y": 221.63910338366577,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 104.91701062479781,
			"height": 22.98182137495571,
			"seed": 161726704,
			"groupIds": [
				"FArwQRR-GyK8sdberTIPH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a124003092c327e18715bd3c4334e4d1e470bcfb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 709,
			"versionNonce": 407054856,
			"isDeleted": false,
			"id": "oXFzKOOaj3MS7rH_hZ391",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 843.8845258553384,
			"y": 214.26958722038967,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 113.44858767452934,
			"height": 36.5963186046869,
			"seed": 341848080,
			"groupIds": [
				"FArwQRR-GyK8sdberTIPH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 737,
			"versionNonce": 1617058424,
			"isDeleted": false,
			"id": "KHUYV3oflO4KD3uQUPvaI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 953.6734816693995,
			"y": 261.84480140648225,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 32.93668674421821,
			"height": 58.554109767499035,
			"seed": 654290448,
			"groupIds": [
				"FArwQRR-GyK8sdberTIPH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.93668674421821,
					-29.277054883749518
				],
				[
					0,
					-58.554109767499035
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 325,
			"versionNonce": 291547400,
			"isDeleted": false,
			"id": "8EfPGa1eDDlamkQIDM20O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1131.9411748051207,
			"y": 217.63505352201992,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 65.41121473811074,
			"height": 30.423820808423603,
			"seed": 1564576496,
			"groupIds": [
				"hy0dE0lkIL4X1afd7OCNm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a222ab9a8e5d7bd8c568f9f71ddb8bef5ec0da2b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 823,
			"versionNonce": 824200056,
			"isDeleted": false,
			"id": "eVc_Eynw-4PnKlqtZXS75",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1108.8575292341577,
			"y": 215.03989073627713,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 113.44858767452934,
			"height": 36.5963186046869,
			"seed": 2051721456,
			"groupIds": [
				"hy0dE0lkIL4X1afd7OCNm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 790,
			"versionNonce": 678840328,
			"isDeleted": false,
			"id": "xM0mYHt_qOaxaS9McsMqo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1220.7581553314894,
			"y": 262.61510492237016,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 32.93668674421821,
			"height": 58.554109767499035,
			"seed": 702819056,
			"groupIds": [
				"hy0dE0lkIL4X1afd7OCNm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.93668674421821,
					-29.277054883749518
				],
				[
					0,
					-58.554109767499035
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 923,
			"versionNonce": 1995971704,
			"isDeleted": false,
			"id": "e2wgwThfWegfFI2pnbkQ1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 575.3691437710494,
			"y": 221.25994700840556,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 113.44858767452934,
			"height": 36.5963186046869,
			"seed": 1367577840,
			"groupIds": [
				"HRSeC_bKHvOvH_RXBdkTl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 800,
			"versionNonce": 696256264,
			"isDeleted": false,
			"id": "2BGKGNxFFpcdt4YcsSAdd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 687.2697698683812,
			"y": 269.2601189338782,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 32.93668674421821,
			"height": 58.554109767499035,
			"seed": 941848304,
			"groupIds": [
				"HRSeC_bKHvOvH_RXBdkTl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.93668674421821,
					-29.277054883749518
				],
				[
					0,
					-58.554109767499035
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 867028344,
			"isDeleted": false,
			"id": "ldQLf7N6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 598.2459230966444,
			"y": 230.08189310117996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 66.83213806152344,
			"height": 20,
			"seed": 1716724752,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vector x",
			"rawText": "Vector x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector x",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 16377352,
			"isDeleted": false,
			"id": "4I0cI0eU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 771.6922703785735,
			"y": 324.165207771184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 20.6080322265625,
			"height": 20,
			"seed": 94060784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "NN",
			"rawText": "NN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "NN",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 277175928,
			"isDeleted": false,
			"id": "NqL7sPZh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 864.7949308410507,
			"y": 254.32028472646743,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 82.35218811035156,
			"height": 40,
			"seed": 1882933488,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3J5nS5RmT-g8rZOX0zVVl",
					"type": "arrow"
				},
				{
					"id": "wGbBChvFsE_KpD3E3IXIV",
					"type": "arrow"
				}
			],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Parameter\nvector",
			"rawText": "Parameter\nvector",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parameter\nvector",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 736093448,
			"isDeleted": false,
			"id": "SGOpfTXn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 992.3132907317396,
			"y": 307.14050777903435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 107.56822204589844,
			"height": 20,
			"seed": 755107568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Mixture model",
			"rawText": "Mixture model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mixture model",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 138,
			"versionNonce": 1849872248,
			"isDeleted": false,
			"id": "hTt9iiAI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1131.623766186798,
			"y": 253.01069241937898,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 83.0081787109375,
			"height": 60,
			"seed": 1519154416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Conditional\nprobability\ndensity",
			"rawText": "Conditional\nprobability\ndensity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conditional\nprobability\ndensity",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 416,
			"versionNonce": 665715720,
			"isDeleted": false,
			"id": "3J5nS5RmT-g8rZOX0zVVl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 905.4952594659401,
			"y": 306.30264480246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 2.1321995947154875,
			"height": 78.0771639454656,
			"seed": 2000276208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NqL7sPZh",
				"focus": 0.03233687158680035,
				"gap": 11.982360075992574
			},
			"endBinding": {
				"elementId": "IkzIsbhjUqInvVT1cn5gb",
				"focus": 0.0003190490171834176,
				"gap": 11.182048451759101
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
					2.1321995947154875,
					78.0771639454656
				]
			]
		},
		{
			"type": "image",
			"version": 168,
			"versionNonce": 1965695096,
			"isDeleted": false,
			"id": "IkzIsbhjUqInvVT1cn5gb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 778.3796140886047,
			"y": 395.5618571996847,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 260.62637883940045,
			"height": 58.721375479247634,
			"seed": 1532588784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3J5nS5RmT-g8rZOX0zVVl",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1aed2ca66ab831139587a32ac46cfbc96a0ace5d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 267,
			"versionNonce": 1650475784,
			"isDeleted": false,
			"id": "JgUk7bph8IfLx6VscK61h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 928.8470544575689,
			"y": 447.6092513244673,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 71.29678986965371,
			"height": 39.67821349267683,
			"seed": 1535389712,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "9yptzKys",
				"focus": 0.0557744707179253,
				"gap": 13.00935586702883
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
					1.8599162574691945,
					34.71843680609231
				],
				[
					-69.43687361218451,
					39.67821349267683
				]
			]
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 620712312,
			"isDeleted": false,
			"id": "9yptzKys",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 759.5846170926134,
			"y": 469.9282464140981,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 86.81620788574219,
			"height": 40,
			"seed": 907439856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JgUk7bph8IfLx6VscK61h",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Prior of\ndistribution",
			"rawText": "Prior of\ndistribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prior of\ndistribution",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 441,
			"versionNonce": 712155656,
			"isDeleted": false,
			"id": "av_aTHQNKkTQywM94nekO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 974.1050167226534,
			"y": 446.3693071528212,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 0.9744019446403911,
			"height": 64.10143500187223,
			"seed": 1015812336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zx12srK0fL1f8yxRtuMh_",
				"focus": 0.16531132306610125,
				"gap": 5.0613773755536045
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
					39.67821349267683
				],
				[
					0.9744019446403911,
					64.10143500187223
				]
			]
		},
		{
			"type": "image",
			"version": 314,
			"versionNonce": 1694917240,
			"isDeleted": false,
			"id": "Zx12srK0fL1f8yxRtuMh_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 725.0570983566076,
			"y": 515.532119530247,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 431.97406447950954,
			"height": 88.15797234275705,
			"seed": 1738840304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "av_aTHQNKkTQywM94nekO",
					"type": "arrow"
				},
				{
					"id": "AKfB9SMMzOWyqFtT4jY8E",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0732dc9282a0e9f4feaef8974b644bb34c458fa9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 302,
			"versionNonce": 518070536,
			"isDeleted": false,
			"id": "yAtiAFhu7tEOIUP3phd4A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1248.8632244704795,
			"y": 299.2152810884056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 84.75392782742273,
			"height": 65.24319061798474,
			"seed": 1699128848,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "B4WVK16c2L_E2hJVc3bRN",
				"focus": -0.13660720476501195,
				"gap": 16.00097981587149
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
					71.93374375229189,
					19.896567420846623
				],
				[
					84.75392782742273,
					65.24319061798474
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 335762296,
			"isDeleted": false,
			"id": "7qY3W80C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1294.1022295952066,
			"y": 270.9009351433542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 177.3603973388672,
			"height": 40,
			"seed": 1691415280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Optimize the Likelihood\nof this model",
			"rawText": "Optimize the Likelihood\nof this model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Optimize the Likelihood\nof this model",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 172,
			"versionNonce": 522698760,
			"isDeleted": false,
			"id": "B4WVK16c2L_E2hJVc3bRN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1223.1670786649906,
			"y": 380.4594515222618,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 290.1511006611386,
			"height": 64.00391926348647,
			"seed": 173352976,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "yAtiAFhu7tEOIUP3phd4A",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f0b64e743b0df6337ecd066100b51279963b67c8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 684,
			"versionNonce": 406463608,
			"isDeleted": false,
			"id": "wGbBChvFsE_KpD3E3IXIV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 905.8802066479277,
			"y": 304.2277138446457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 281.71921486373185,
			"height": 84.74420353746996,
			"seed": 1783021072,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NqL7sPZh",
				"focus": -0.6357178121008368,
				"gap": 9.907429118178243
			},
			"endBinding": {
				"elementId": "k3mwOHSn",
				"focus": -0.7274305939986818,
				"gap": 4.443037401383322
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
					-115.43571349490367,
					75.55792156030066
				],
				[
					-234.2469665278495,
					84.74420353746996
				],
				[
					-281.71921486373185,
					62.88901309994549
				]
			]
		},
		{
			"type": "text",
			"version": 359,
			"versionNonce": 994213640,
			"isDeleted": false,
			"id": "k3mwOHSn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 338.9653298710938,
			"y": 339.27904192572623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 280.75262451171875,
			"height": 60,
			"seed": 1901392624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "wGbBChvFsE_KpD3E3IXIV",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "These parameters are subject\nto certain constraints which can be\nmodeled in the output layer",
			"rawText": "These parameters are subject\nto certain constraints which can be\nmodeled in the output layer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "These parameters are subject\nto certain constraints which can be\nmodeled in the output layer",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 301,
			"versionNonce": 1869534584,
			"isDeleted": false,
			"id": "re2nIJXGdmUk62rhvgX2B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 329.2603436557084,
			"y": 402.5123977110338,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 150.44597459152348,
			"height": 63.92339692944561,
			"seed": 400176368,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63e2c0de5a6dd97eadbd7e56eca4a80e06666d03",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 301,
			"versionNonce": 598564360,
			"isDeleted": false,
			"id": "YCUS3WUpglh9wRx2FteOO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 515.1746283155798,
			"y": 411.8282320152607,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 112.33155882977462,
			"height": 43.20444570375947,
			"seed": 783391472,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3f0c6a98da54be803ba992476fda0eca5f7393b5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 1055221368,
			"isDeleted": false,
			"id": "lFPIGqLQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 849.3533540003034,
			"y": 716.6361015065935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 230.47975158691406,
			"height": 25,
			"seed": 1410952208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AKfB9SMMzOWyqFtT4jY8E",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The problem with GMMs",
			"rawText": "The problem with GMMs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The problem with GMMs",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 426007816,
			"isDeleted": false,
			"id": "AKfB9SMMzOWyqFtT4jY8E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 970.1241256450058,
			"y": 607.9083827619365,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 0,
			"height": 93.7242938334607,
			"seed": 668134928,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Zx12srK0fL1f8yxRtuMh_",
				"focus": -0.1346376898052076,
				"gap": 4.218290888932472
			},
			"endBinding": {
				"elementId": "lFPIGqLQ",
				"focus": 0.04799463565162439,
				"gap": 15.003424911196248
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
					93.7242938334607
				]
			]
		},
		{
			"type": "image",
			"version": 174,
			"versionNonce": 1667356536,
			"isDeleted": false,
			"id": "J1OYSHSiLmAFPc3QeJGXN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 514.4471905402555,
			"y": 706.6458290471032,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 269.76263828244845,
			"height": 193.52537094175648,
			"seed": 1006113008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d0d1d36cc01a3c23754ae18d7782b8b99eb0a196",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 372,
			"versionNonce": 1575189512,
			"isDeleted": false,
			"id": "kz26hJV9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 760.9272931549317,
			"y": 751.0094552395901,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 405.4088134765625,
			"height": 140,
			"seed": 167311600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gaussian mixture models capture localized\nhigh density spots in our space and identify them\nas a distribution, but this gets rather out of\nhand with global effects and spaces where\nour data is distributed across every possible\ncorner of our space IN HIGH DIMENSIONAL space\nfor example when using pictures",
			"rawText": "Gaussian mixture models capture localized\nhigh density spots in our space and identify them\nas a distribution, but this gets rather out of\nhand with global effects and spaces where\nour data is distributed across every possible\ncorner of our space IN HIGH DIMENSIONAL space\nfor example when using pictures",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gaussian mixture models capture localized\nhigh density spots in our space and identify them\nas a distribution, but this gets rather out of\nhand with global effects and spaces where\nour data is distributed across every possible\ncorner of our space IN HIGH DIMENSIONAL space\nfor example when using pictures",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "text",
			"version": 424,
			"versionNonce": 19409016,
			"isDeleted": false,
			"id": "2rJtXctP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 659.6266921764015,
			"y": 905.424758946913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 598.9132080078125,
			"height": 100,
			"seed": 379362320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Thus it is better to use Boltzmann machines\nBMs or rather RBMs are quite good at understanding\nglobal effects by drawing conclusions between inputs and outputs\nwithout learning features specific to that input... only the transitions that\nlead to the output aka Global effects",
			"rawText": "Thus it is better to use Boltzmann machines\nBMs or rather RBMs are quite good at understanding\nglobal effects by drawing conclusions between inputs and outputs\nwithout learning features specific to that input... only the transitions that\nlead to the output aka Global effects",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thus it is better to use Boltzmann machines\nBMs or rather RBMs are quite good at understanding\nglobal effects by drawing conclusions between inputs and outputs\nwithout learning features specific to that input... only the transitions that\nlead to the output aka Global effects",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 251,
			"versionNonce": 589740808,
			"isDeleted": false,
			"id": "pnG9iGKxMJMfiwtV2MaYj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 28.581204762370703,
			"y": 19.377815785238056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 337.09834697027975,
			"height": 1105.4281642157478,
			"seed": 775143664,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
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
					19.081038507751714,
					381.62077015503377
				],
				[
					291.3038545516757,
					767.0577480116178
				],
				[
					337.09834697027975,
					1105.4281642157478
				]
			]
		},
		{
			"type": "text",
			"version": 79,
			"versionNonce": 335305080,
			"isDeleted": false,
			"id": "EfWErfAq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 71.19601229430788,
			"y": 1147.4695328472387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 587.2463989257812,
			"height": 70,
			"seed": 877016304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Conditional Restricted Boltzmann Machines\n(CRBM)",
			"rawText": "Conditional Restricted Boltzmann Machines\n(CRBM)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conditional Restricted Boltzmann Machines\n(CRBM)",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "arrow",
			"version": 62,
			"versionNonce": 2074745352,
			"isDeleted": false,
			"id": "r6XS_6XFn5ixpwbUjzi-2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 939.382776199051,
			"y": 1035.7611336314778,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 259.5021237054227,
			"height": 147.560031126613,
			"seed": 1838907120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
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
					-1.2720692338500612,
					139.92761572351242
				],
				[
					-259.5021237054227,
					147.560031126613
				]
			]
		},
		{
			"type": "text",
			"version": 754,
			"versionNonce": 2132961912,
			"isDeleted": false,
			"id": "yno6CSSB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -80.64029164987363,
			"y": 1218.0594021388958,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 890.9190063476562,
			"height": 250,
			"seed": 1077273104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CRBMs is a system of binary vairables composed of an input x, an output\ny and a latent state h.\nUsually it involves a visible layers (as inputs) and a hidden layer (as latent variables)\n \"restricted\" indicates no two nodes from the same layer have a connection between them\nCRBMs try to learn global effects and patterns by taking in an input and its output\nand trying to draw a conclusion on how to transition from one to another by\nupdating the weights and learning the latent variable\n\nCRBMs are governed by an energy function:\n",
			"rawText": "CRBMs is a system of binary vairables composed of an input x, an output\ny and a latent state h.\nUsually it involves a visible layers (as inputs) and a hidden layer (as latent variables)\n \"restricted\" indicates no two nodes from the same layer have a connection between them\nCRBMs try to learn global effects and patterns by taking in an input and its output\nand trying to draw a conclusion on how to transition from one to another by\nupdating the weights and learning the latent variable\n\nCRBMs are governed by an energy function:\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CRBMs is a system of binary vairables composed of an input x, an output\ny and a latent state h.\nUsually it involves a visible layers (as inputs) and a hidden layer (as latent variables)\n \"restricted\" indicates no two nodes from the same layer have a connection between them\nCRBMs try to learn global effects and patterns by taking in an input and its output\nand trying to draw a conclusion on how to transition from one to another by\nupdating the weights and learning the latent variable\n\nCRBMs are governed by an energy function:\n",
			"lineHeight": 1.25,
			"baseline": 243
		},
		{
			"type": "image",
			"version": 225,
			"versionNonce": 1248434440,
			"isDeleted": false,
			"id": "ckwEFBccd56MeL9djDZay",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 156.0397416589147,
			"y": 1447.451773564825,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 403.2719901871189,
			"height": 62.23333181899982,
			"seed": 86413552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0cc2d4da6a9879d99c6f2320990680238d585b86",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 907,
			"versionNonce": 492723064,
			"isDeleted": false,
			"id": "OQM4MJp5O9Gex9mMbXZp8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 134.86025776767025,
			"y": 1433.304118219597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 324.8364256872418,
			"height": 49.22372835156398,
			"seed": 2029416976,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
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
					-171.59738499344547,
					-13.540476946592435
				],
				[
					-312.4631007518039,
					-11.086695637362936
				],
				[
					-324.8364256872418,
					35.68325140497154
				]
			]
		},
		{
			"type": "text",
			"version": 488,
			"versionNonce": 853620744,
			"isDeleted": false,
			"id": "c6UkSlVr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -395.6936031706989,
			"y": 1468.2268938163884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 414.7594909667969,
			"height": 125,
			"seed": 1796442864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Energy functions are functions\nthat get as an input the current\nstate of a system and output its energy\ntheyre often used in order to control\nthe system to head in a specific direction",
			"rawText": "Energy functions are functions\nthat get as an input the current\nstate of a system and output its energy\ntheyre often used in order to control\nthe system to head in a specific direction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Energy functions are functions\nthat get as an input the current\nstate of a system and output its energy\ntheyre often used in order to control\nthe system to head in a specific direction",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 129,
			"versionNonce": 1358179448,
			"isDeleted": false,
			"id": "mY4dmr91",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 120.70345364450318,
			"y": 1507.135311420231,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 505.0794982910156,
			"height": 50,
			"seed": 1006893808,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "and the system associates each state of x,y,h to\na probability",
			"rawText": "and the system associates each state of x,y,h to\na probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and the system associates each state of x,y,h to\na probability",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 60,
			"versionNonce": 151844616,
			"isDeleted": false,
			"id": "NaAXZ1jJclcEAmzb9BUB9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 108.51951715593646,
			"y": 1562.6044631484926,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 542,
			"height": 80,
			"seed": 1168876272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d5ecdc71557037be5b1a79e541cbffd92613064",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 216,
			"versionNonce": 329768312,
			"isDeleted": false,
			"id": "XCfNnU1I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 31.613685995517443,
			"y": 1631.4100148214059,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 735.4991455078125,
			"height": 50,
			"seed": 1714794736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Z being a normalization term like in softmax\naka the sum of all configurations and is generally intractable in this form",
			"rawText": "Z being a normalization term like in softmax\naka the sum of all configurations and is generally intractable in this form",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z being a normalization term like in softmax\naka the sum of all configurations and is generally intractable in this form",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 1097389576,
			"isDeleted": false,
			"id": "4O1uJepR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 150.2340233057182,
			"y": 1690.8537178371184,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 492.99945068359375,
			"height": 75,
			"seed": 1108579568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "problem:\nh is a latent variable that we need to learn\nwe do not have h in order to use these functions",
			"rawText": "problem:\nh is a latent variable that we need to learn\nwe do not have h in order to use these functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "problem:\nh is a latent variable that we need to learn\nwe do not have h in order to use these functions",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 113077880,
			"isDeleted": false,
			"id": "TOvu25ld",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 236.11029277704904,
			"y": 1773.0806222462584,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
			"width": 338.65966796875,
			"height": 50,
			"seed": 1729506832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PIXdGRbsQ6vkoLAwgjA5f",
					"type": "arrow"
				},
				{
					"id": "zYSzKBhwukbxu1wchen4_",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Solution:\nMarginalize these functions over h",
			"rawText": "Solution:\nMarginalize these functions over h",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Solution:\nMarginalize these functions over h",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 259,
			"versionNonce": 1626395912,
			"isDeleted": false,
			"id": "Ga7ph4bkgS4XJ3OARaELE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 127.20229651627051,
			"y": 2383.8743046784425,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 486,
			"height": 54,
			"seed": 812441840,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bbb32d99227583705b743363c020f83d9727deab",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 265,
			"versionNonce": 49864568,
			"isDeleted": false,
			"id": "2muNzVq7tPy9PAlDIjdla",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 164.58393600191505,
			"y": 2216.8210844302935,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 662,
			"height": 109,
			"seed": 480664304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "y5qQ3D7fdqdYrBgnuzNAA",
					"type": "arrow"
				},
				{
					"id": "IvG28RyTeo3FnrdV1cU1f",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a0ee93c7c23aa945852fa7391fb107d5e49eb93c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1145,
			"versionNonce": 1830876168,
			"isDeleted": false,
			"id": "y5qQ3D7fdqdYrBgnuzNAA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 144.76816327858455,
			"y": 2287.854023983517,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
			"width": 216.2181319261081,
			"height": 46.12964309087283,
			"seed": 1647301360,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2muNzVq7tPy9PAlDIjdla",
				"focus": -0.7336303501588882,
				"gap": 19.815772723330497
			},
			"endBinding": {
				"elementId": "LYFgxpDw",
				"focus": -0.04525307638630625,
				"gap": 3.1659047188859404
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
					-126.06662286835503,
					-27.37672302810961
				],
				[
					-216.2181319261081,
					18.752920062763224
				]
			]
		},
		{
			"type": "text",
			"version": 586,
			"versionNonce": 681455736,
			"isDeleted": false,
			"id": "LYFgxpDw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -424.77837162277126,
			"y": 2309.772848765166,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
			"width": 531.7593383789062,
			"height": 100,
			"seed": 654722800,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "y5qQ3D7fdqdYrBgnuzNAA",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Free energy\nfunction describing how present (well aligned) the\nfeatures in W are in x and how present the features\ndescribed in U are in y",
			"rawText": "Free energy\nfunction describing how present (well aligned) the\nfeatures in W are in x and how present the features\ndescribed in U are in y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Free energy\nfunction describing how present (well aligned) the\nfeatures in W are in x and how present the features\ndescribed in U are in y",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 489,
			"versionNonce": 1542796040,
			"isDeleted": false,
			"id": "NsnRldnX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5.829520097585828,
			"y": 2439.071866773967,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 758.779296875,
			"height": 175,
			"seed": 1683543280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Can be interpreted as a two-layer neural network.\nThe lower the free energy the more likely the joint configuration\n(x,y) is to occur in the wild!\n\nThus we perform coordinate gradient descent where we set x to a certain\nvalue and minimize according to y then set y to a certain value and minimize\naccording to x",
			"rawText": "Can be interpreted as a two-layer neural network.\nThe lower the free energy the more likely the joint configuration\n(x,y) is to occur in the wild!\n\nThus we perform coordinate gradient descent where we set x to a certain\nvalue and minimize according to y then set y to a certain value and minimize\naccording to x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can be interpreted as a two-layer neural network.\nThe lower the free energy the more likely the joint configuration\n(x,y) is to occur in the wild!\n\nThus we perform coordinate gradient descent where we set x to a certain\nvalue and minimize according to y then set y to a certain value and minimize\naccording to x",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "image",
			"version": 283,
			"versionNonce": 1869701496,
			"isDeleted": false,
			"id": "oHHTvwAfvqtvjb12e2v2d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 210.05202552415687,
			"y": 2616.7290301971047,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 364,
			"height": 72,
			"seed": 2105540112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EziFciCN9eqpUr6heLHdU",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "50c36a584ee9647a13762db7081bdb75ade49b1b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 620,
			"versionNonce": 37520136,
			"isDeleted": false,
			"id": "97FLdIse",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1147.1236234907965,
			"y": 2067.154501834266,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 703.71923828125,
			"height": 75,
			"seed": 1100692208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We would like to proceed with a stochastic gradient descent procedure\n\nthe gradient of our objective is given by",
			"rawText": "We would like to proceed with a stochastic gradient descent procedure\n\nthe gradient of our objective is given by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We would like to proceed with a stochastic gradient descent procedure\n\nthe gradient of our objective is given by",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 430,
			"versionNonce": 1240814088,
			"isDeleted": false,
			"id": "DR6BKjaIKjdSOJGv5Cske",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1159.0883204327727,
			"y": 2151.649174713657,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 645.2232780331811,
			"height": 57.01326379172506,
			"seed": 50366704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MaAhoAksC9Cq50PMEJW4t",
					"type": "arrow"
				},
				{
					"id": "nCuJYs49yS7j8SVakYiP1",
					"type": "arrow"
				}
			],
			"updated": 1706721635690,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6fa4af893c110fe256a85c5e2c3b5f9e4b29fcf1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 635,
			"versionNonce": 560726024,
			"isDeleted": false,
			"id": "Bwex73Og",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1697.4275430865237,
			"y": 2258.9096487057686,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 160.1283416748047,
			"height": 80,
			"seed": 693800464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(soft on/off value\nindicating how well\npresent the feature\nin W is in x)",
			"rawText": "(soft on/off value\nindicating how well\npresent the feature\nin W is in x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(soft on/off value\nindicating how well\npresent the feature\nin W is in x)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 383,
			"versionNonce": 1795079944,
			"isDeleted": false,
			"id": "GZMroF0OVhUAvkKBI8F2t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1301.5306217688644,
			"y": 2219.937555230819,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 0.596162520214989,
			"height": 39.34672633418609,
			"seed": 1773522448,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.596162520214989,
					39.34672633418609
				]
			]
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 299998728,
			"isDeleted": false,
			"id": "823kxVcE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1215.886603319841,
			"y": 2259.284281565005,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 172.48036193847656,
			"height": 40,
			"seed": 1715867664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Expectation\nover the observations",
			"rawText": "Expectation\nover the observations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Expectation\nover the observations",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 463,
			"versionNonce": 923835656,
			"isDeleted": false,
			"id": "DL6D0Y2pzxnA7VSq_zDFL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1577.5834896912002,
			"y": 2210.244443600817,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 1.7884875606448531,
			"height": 36.96207625332636,
			"seed": 1906935536,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7884875606448531,
					36.96207625332636
				]
			]
		},
		{
			"type": "text",
			"version": 494,
			"versionNonce": 2080881672,
			"isDeleted": false,
			"id": "NIYGEezX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1471.6624196428447,
			"y": 2252.0273237847177,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 206.83248901367188,
			"height": 60,
			"seed": 708191984,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "expectation over\nthe probability distribution\nbuilt by the model",
			"rawText": "expectation over\nthe probability distribution\nbuilt by the model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "expectation over\nthe probability distribution\nbuilt by the model",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 208,
			"versionNonce": 676914552,
			"isDeleted": false,
			"id": "PIXdGRbsQ6vkoLAwgjA5f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 222.6319254112948,
			"y": 1804.4431901144458,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
			"width": 176.32076524207366,
			"height": 7.841492211937293,
			"seed": 996726800,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "TOvu25ld",
				"focus": 0.033119345282775985,
				"gap": 13.478367365754252
			},
			"endBinding": {
				"elementId": "G2vpdjAp",
				"focus": 0.3736311607768471,
				"gap": 7.399704885942015
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
					-126.30495469742027,
					5.125291915266644
				],
				[
					-176.32076524207366,
					7.841492211937293
				]
			]
		},
		{
			"type": "text",
			"version": 188,
			"versionNonce": 1378635272,
			"isDeleted": false,
			"id": "G2vpdjAp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -245.96919046867401,
			"y": 1776.3228674900258,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
			"width": 284.8806457519531,
			"height": 60,
			"seed": 1493733904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PIXdGRbsQ6vkoLAwgjA5f",
					"type": "arrow"
				},
				{
					"id": "iyHPZ_gbXBYUAH4dqE3rO",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "aka take h out of the context\nand only give in possible values of\nx and y given their joint distribution",
			"rawText": "aka take h out of the context\nand only give in possible values of\nx and y given their joint distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "aka take h out of the context\nand only give in possible values of\nx and y given their joint distribution",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 752,
			"versionNonce": 1925380872,
			"isDeleted": false,
			"id": "IilxecgA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1965.5074050608205,
			"y": 2216.627755822775,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 613.9793090820312,
			"height": 50,
			"seed": 1887433232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This can be approximated by using methods like Gibbs sampling\nwhich is a method to sample from multivariate distributions",
			"rawText": "This can be approximated by using methods like Gibbs sampling\nwhich is a method to sample from multivariate distributions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This can be approximated by using methods like Gibbs sampling\nwhich is a method to sample from multivariate distributions",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 721,
			"versionNonce": 230578696,
			"isDeleted": false,
			"id": "4XWmxNpK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1980.262968397467,
			"y": 2269.5765163887186,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 582.3192749023438,
			"height": 75,
			"seed": 532933872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sampling from p(x,y) is difficult whereas\nsampling from p(x | y) and p(x | y) is quite easy\nGibbs sampling allows us to infer the joint from the latter",
			"rawText": "Sampling from p(x,y) is difficult whereas\nsampling from p(x | y) and p(x | y) is quite easy\nGibbs sampling allows us to infer the joint from the latter",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sampling from p(x,y) is difficult whereas\nsampling from p(x | y) and p(x | y) is quite easy\nGibbs sampling allows us to infer the joint from the latter",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 720,
			"versionNonce": 267770120,
			"isDeleted": false,
			"id": "zIqKHY4M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2028.9652270829401,
			"y": 2354.2887537610636,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 523.2194213867188,
			"height": 175,
			"seed": 1511853072,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) initialize the values\n\n2) sample x from the constant y from the last step\n\n3) sample y from the constant x from the last step\n\n4) repeat 2 and 3",
			"rawText": "1) initialize the values\n\n2) sample x from the constant y from the last step\n\n3) sample y from the constant x from the last step\n\n4) repeat 2 and 3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) initialize the values\n\n2) sample x from the constant y from the last step\n\n3) sample y from the constant x from the last step\n\n4) repeat 2 and 3",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "arrow",
			"version": 238,
			"versionNonce": 1298557960,
			"isDeleted": false,
			"id": "9w6a2mwwTgMxJIwO5rlD-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 182.44536883290846,
			"y": 2699.5718393669003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 91.16538053648492,
			"height": 79.34764602249606,
			"seed": 1403773456,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
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
					-91.16538053648492,
					79.34764602249606
				]
			]
		},
		{
			"type": "text",
			"version": 239,
			"versionNonce": 1938569336,
			"isDeleted": false,
			"id": "hMX9RftN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -15.146023601714546,
			"y": 2795.801963266523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 157.1398468017578,
			"height": 25,
			"seed": 905922288,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Standard CRBM",
			"rawText": "Standard CRBM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Standard CRBM",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 669,
			"versionNonce": 80456456,
			"isDeleted": false,
			"id": "EziFciCN9eqpUr6heLHdU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 520.9390502693012,
			"y": 2695.3512198976186,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 99.60661947504832,
			"height": 81.88001770406527,
			"seed": 297898736,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oHHTvwAfvqtvjb12e2v2d",
				"focus": -0.34118450441139486,
				"gap": 6.6221897005139
			},
			"endBinding": {
				"elementId": "IDNhkZTU",
				"focus": 0.21866289255116805,
				"gap": 13.505982301701351
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
					99.60661947504832,
					81.88001770406527
				]
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 1063151992,
			"isDeleted": false,
			"id": "IDNhkZTU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 538.1170051184596,
			"y": 2790.7372199033853,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 181.73980712890625,
			"height": 25,
			"seed": 1127695888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EziFciCN9eqpUr6heLHdU",
					"type": "arrow"
				}
			],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Higher order CRBM",
			"rawText": "Higher order CRBM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Higher order CRBM",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 292,
			"versionNonce": 993069576,
			"isDeleted": false,
			"id": "TEqvlnWD9vKQwQuR9vKIr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -158.40932144686712,
			"y": 2835.5476354561206,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 149.06720353619977,
			"height": 44.93413312335208,
			"seed": 727511056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5399d3937af064035d71662a3745b46f3012d035",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 282,
			"versionNonce": 331512440,
			"isDeleted": false,
			"id": "T_TcU-YXGhbCR0it7eiIx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -13.698542669832364,
			"y": 2833.786805560085,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 250.47500883761612,
			"height": 55.90960018696788,
			"seed": 2045591568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0afc5abe8fa25061d8fd314a8a40f61b3f3ea83",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 269,
			"versionNonce": 1536329992,
			"isDeleted": false,
			"id": "T6yNUCsn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 7.871461900064901,
			"y": 2897.096830529284,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 77.33992004394531,
			"height": 25,
			"seed": 1189708528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Additive",
			"rawText": "Additive",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Additive",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 280,
			"versionNonce": 1132227448,
			"isDeleted": false,
			"id": "ZmrmBhQ0NLBL70NY2Qxet",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -60.34351612815112,
			"y": 2925.5655208032927,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 170.43818288241812,
			"height": 123.70513273723896,
			"seed": 329000176,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cd4eb941ea5c5764e065c0b5c14bfd4c65721171",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 265,
			"versionNonce": 292300808,
			"isDeleted": false,
			"id": "n4K8q7DKzM2XvxioskCb0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 446.6642538228008,
			"y": 2823.4094612467175,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 384.0601592789203,
			"height": 67.09869671262335,
			"seed": 885246992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8a49189668af2e76c9370ae00b59946c8340461f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 240,
			"versionNonce": 684735608,
			"isDeleted": false,
			"id": "IsGKaqfi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 560.9763645920492,
			"y": 2901.317449998566,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 127.57984924316406,
			"height": 25,
			"seed": 397742832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Multiplicative",
			"rawText": "Multiplicative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multiplicative",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 293,
			"versionNonce": 951707400,
			"isDeleted": false,
			"id": "a7YqVxFbiz-Jq-VTCORhe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 546.2578467388681,
			"y": 2938.1541933732374,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 150.95405798862123,
			"height": 184.62842477069827,
			"seed": 1629162000,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0fb9e45d1795c97223225c72c522896dd707a6e2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 460,
			"versionNonce": 2095413256,
			"isDeleted": false,
			"id": "2oRRUKNl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1726.0017584605116,
			"y": 2230.371249310277,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 75.95991516113281,
			"height": 25,
			"seed": 360255216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p(hj | x)",
			"rawText": "p(hj | x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p(hj | x)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 487,
			"versionNonce": 143210248,
			"isDeleted": false,
			"id": "Op5Zsh7qFOqKY_TGE9BgU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1742.8742867040878,
			"y": 2200.824545171267,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 4.968686014116884,
			"height": 26.067676077461783,
			"seed": 530975760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.968686014116884,
					26.067676077461783
				]
			]
		},
		{
			"type": "arrow",
			"version": 201,
			"versionNonce": 47545976,
			"isDeleted": false,
			"id": "a0qF0pCmViL5xZ6N8CnFm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -204.20655351465507,
			"y": 42.14649008851734,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 430.52580033313825,
			"height": 873.3523378186519,
			"seed": 622774000,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437559,
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
					-114.8068800888368,
					179.04406299568603
				],
				[
					5.466994289944523,
					515.2642118272797
				],
				[
					-164.00982869833842,
					755.8119605848428
				],
				[
					-425.0588060431937,
					873.3523378186519
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1579271432,
			"isDeleted": false,
			"id": "JVhQxCK7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1086.6124016484835,
			"y": 902.5318336172245,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 299.6572265625,
			"height": 35,
			"seed": 344418832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Energy Based learning",
			"rawText": "Energy Based learning",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Energy Based learning",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 84,
			"versionNonce": 1636757368,
			"isDeleted": false,
			"id": "wfItyR5N",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1276.691542651064,
			"y": 946.435308295574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 702.0991821289062,
			"height": 100,
			"seed": 1941305872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Energy-based learning is a general framework for performing structured\npredictions with neural networks it associates to each\ninput-output pair a score, The predicted output is the one that\nyields the highest score aka lowest energy",
			"rawText": "Energy-based learning is a general framework for performing structured\npredictions with neural networks it associates to each\ninput-output pair a score, The predicted output is the one that\nyields the highest score aka lowest energy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Energy-based learning is a general framework for performing structured\npredictions with neural networks it associates to each\ninput-output pair a score, The predicted output is the one that\nyields the highest score aka lowest energy",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 1991500808,
			"isDeleted": false,
			"id": "rhybqslE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1168.1735008942928,
			"y": 1063.229706501439,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 491.7193603515625,
			"height": 25,
			"seed": 402950160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "These models are trained via the Push pull model",
			"rawText": "These models are trained via the Push pull model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "These models are trained via the Push pull model",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 22,
			"versionNonce": 1777483896,
			"isDeleted": false,
			"id": "qyAhYdf0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1021.7504583260841,
			"y": 1130.8506900272612,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 188.13978576660156,
			"height": 25,
			"seed": 1879930384,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "More on this later!",
			"rawText": "More on this later!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "More on this later!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "mBQ9FikD",
			"type": "text",
			"x": 712.6317193080961,
			"y": 1585.3518498650672,
			"width": 246.1396942138672,
			"height": 50,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1124418168,
			"version": 178,
			"versionNonce": 363471624,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "high energy is associated\nwith low probability",
			"rawText": "high energy is associated\nwith low probability",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "high energy is associated\nwith low probability",
			"lineHeight": 1.25
		},
		{
			"id": "7AJTJQ1CN03zNKBdB6Opn",
			"type": "line",
			"x": 661.1643898494988,
			"y": 1599.5138677543234,
			"width": 26.858294917492913,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
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
			"seed": 1048971128,
			"version": 11,
			"versionNonce": 197357944,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					26.858294917492913,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 37,
			"versionNonce": 427852296,
			"isDeleted": false,
			"id": "pFIZbSl0nulkhQcsJRVNB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 661.5509774762103,
			"y": 1615.7045256033707,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 26.858294917492913,
			"height": 0,
			"seed": 1250713720,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.858294917492913,
					0
				]
			]
		},
		{
			"id": "iyHPZ_gbXBYUAH4dqE3rO",
			"type": "arrow",
			"x": -115.28724000980756,
			"y": 1844.2019634024805,
			"width": 0.41944484695373774,
			"height": 38.75619329047572,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
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
			"seed": 454125688,
			"version": 155,
			"versionNonce": 507937400,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.41944484695373774,
					38.75619329047572
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "G2vpdjAp",
				"focus": 0.08531498655309475,
				"gap": 7.879095912454659
			},
			"endBinding": {
				"elementId": "4urkPr8F",
				"focus": -0.004481570178757832,
				"gap": 6.061726001493071
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "4urkPr8F",
			"type": "text",
			"x": -298.9868029605685,
			"y": 1889.0198826944493,
			"width": 371.1195373535156,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 579328888,
			"version": 320,
			"versionNonce": 825426184,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "iyHPZ_gbXBYUAH4dqE3rO",
					"type": "arrow"
				}
			],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "We notice that we can represent the\nconditional distributions in a much\neasier way than the joint distribution\nof the latent and in the input",
			"rawText": "We notice that we can represent the\nconditional distributions in a much\neasier way than the joint distribution\nof the latent and in the input",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "We notice that we can represent the\nconditional distributions in a much\neasier way than the joint distribution\nof the latent and in the input",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 183,
			"versionNonce": 1883206520,
			"isDeleted": false,
			"id": "tE438Fon",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -214.2196614336783,
			"y": 2023.6335130192235,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 199.31635315999242,
			"height": 24.732686158539202,
			"seed": 94065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0edd9c2d94201837a21fb4a0d69930b86e0f8193",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XFSz3JRt59hOlnrNzUiVZ",
			"type": "line",
			"x": -115.12927686241557,
			"y": 2015.9278556347947,
			"width": 233.45798569499385,
			"height": 27.744282357955825,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 826768760,
			"version": 212,
			"versionNonce": 1279107080,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-88.64636558273685,
					-14.21048608578234
				],
				[
					-145.48830992586574,
					13.533796272173484
				],
				[
					-233.45798569499385,
					-6.090208322477886
				]
			],
			"lastCommittedPoint": [
				233.45798569499027,
				-6.0902083224777925
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "d3sokiXG",
			"type": "text",
			"x": -569.4913168177598,
			"y": 1985.23145530013,
			"width": 237.31248474121094,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1654776584,
			"version": 165,
			"versionNonce": 1475495032,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "the hidden units are\nconditionally independent\ngiven x due to a local markov\nproperty (the restriction)",
			"rawText": "the hidden units are\nconditionally independent\ngiven x due to a local markov\nproperty (the restriction)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "the hidden units are\nconditionally independent\ngiven x due to a local markov\nproperty (the restriction)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 173,
			"versionNonce": 178020104,
			"isDeleted": false,
			"id": "SfQcp7md",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -214.62383779983793,
			"y": 2102.09959065564,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 243.34469698142664,
			"height": 22.855579274498634,
			"seed": 35757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d68fab0532591d3932daafad444bb1016db263c2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 216,
			"versionNonce": 1126364536,
			"isDeleted": false,
			"id": "gYpDm3EJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -229.3761037383515,
			"y": 2177.5291020334635,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 264.3764294723075,
			"height": 26.026695129398146,
			"seed": 92621,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ebf34d15c595014e0cea4549b73b2b759ff83303",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "9ezLqFic",
			"type": "text",
			"x": -327.05259227673366,
			"y": 2055.5214079350426,
			"width": 451.9849548339844,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 179246600,
			"version": 172,
			"versionNonce": 751517192,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "Since h and x are given via bernoulli distributions, we can\nderive the following",
			"rawText": "Since h and x are given via bernoulli distributions, we can\nderive the following",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Since h and x are given via bernoulli distributions, we can\nderive the following",
			"lineHeight": 1.25
		},
		{
			"id": "sRuClUB7",
			"type": "text",
			"x": -323.5756072889019,
			"y": 2133.182891473234,
			"width": 438.096923828125,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2085665656,
			"version": 157,
			"versionNonce": 1192593016,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "note that the conditional relation is symmetric between\nthe latent and the input",
			"rawText": "note that the conditional relation is symmetric between\nthe latent and the input",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "note that the conditional relation is symmetric between\nthe latent and the input",
			"lineHeight": 1.25
		},
		{
			"id": "zYSzKBhwukbxu1wchen4_",
			"type": "arrow",
			"x": 378.5190421496665,
			"y": 1836.2082400254,
			"width": 2.507406692968118,
			"height": 60.07345679493005,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
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
			"seed": 1236836728,
			"version": 479,
			"versionNonce": 63323400,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.507406692968118,
					60.07345679493005
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "TOvu25ld",
				"focus": 0.14867161793562592,
				"gap": 13.127617779141701
			},
			"endBinding": {
				"elementId": "8fcnKNrIrMQISWOX0_YPu",
				"focus": -0.39332683267842455,
				"gap": 3.8721887811175293
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "8fcnKNrIrMQISWOX0_YPu",
			"type": "rectangle",
			"x": 200.80408281744906,
			"y": 1900.1538856014477,
			"width": 566.574091606471,
			"height": 251.42482732755525,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 30,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 631791480,
			"version": 470,
			"versionNonce": 814610296,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "zYSzKBhwukbxu1wchen4_",
					"type": "arrow"
				},
				{
					"id": "IvG28RyTeo3FnrdV1cU1f",
					"type": "arrow"
				}
			],
			"updated": 1706720437559,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 129,
			"versionNonce": 1628003336,
			"isDeleted": false,
			"id": "w9jMNV2R",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 60,
			"angle": 0,
			"x": 225.9709841615031,
			"y": 1912.5234528896403,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 31,
			"height": 17,
			"seed": 75518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5d22dcd633d309a4aa25ea8331373349eb1c3330",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "URNrxPjD",
			"type": "text",
			"x": 548.1593676415187,
			"y": 1853.471038972838,
			"width": 201.95242309570312,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 409826824,
			"version": 135,
			"versionNonce": 332417144,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "derivation over x\ncan be done similarly to y",
			"rawText": "derivation over x\ncan be done similarly to y",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "derivation over x\ncan be done similarly to y",
			"lineHeight": 1.25
		},
		{
			"id": "IvG28RyTeo3FnrdV1cU1f",
			"type": "arrow",
			"x": 369.289795403257,
			"y": 2152.9317786580077,
			"width": 0,
			"height": 52.158343747710205,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
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
			"seed": 2101698056,
			"version": 34,
			"versionNonce": 110140168,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					52.158343747710205
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "8fcnKNrIrMQISWOX0_YPu",
				"focus": 0.4052473804155728,
				"gap": 1.3530657290048111
			},
			"endBinding": {
				"elementId": "2muNzVq7tPy9PAlDIjdla",
				"focus": -0.381553294859994,
				"gap": 11.730962024575547
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "gOtDtMCU",
			"type": "text",
			"x": 416.65060014251856,
			"y": 2342.5488186166835,
			"width": 270.20855712890625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1139147528,
			"version": 67,
			"versionNonce": 1554020728,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"text": "softplus which is a smooth version\nof relu",
			"rawText": "softplus which is a smooth version\nof relu",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "softplus which is a smooth version\nof relu",
			"lineHeight": 1.25
		},
		{
			"id": "-sUyQGJlRryTTlfAC90cz",
			"type": "line",
			"x": 466.89241200392416,
			"y": 2301.307246013333,
			"width": 75.34518071765899,
			"height": 32.517393783410625,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
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
			"seed": 1759425544,
			"version": 61,
			"versionNonce": 383253000,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					56.31060874688205,
					17.44835763987885
				],
				[
					75.34518071765899,
					32.517393783410625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "rectangle",
			"version": 348,
			"versionNonce": 1581419128,
			"isDeleted": false,
			"id": "zWrrxYGOlF0XSJYw1yRyR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 895.9258967613939,
			"y": 2282.64030020124,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 199.74895397489533,
			"height": 64.43514644351465,
			"seed": 1756551032,
			"groupIds": [
				"P_NI0DN-KxUFS5OHdEMNh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 372,
			"versionNonce": 81492232,
			"isDeleted": false,
			"id": "O0Wcc7-GoShrLxQVhn7ni",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1089.2313360919386,
			"y": 2366.405990577808,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 57.99163179916319,
			"height": 103.09623430962344,
			"seed": 878258296,
			"groupIds": [
				"P_NI0DN-KxUFS5OHdEMNh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706720437559,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					57.99163179916319,
					-51.54811715481172
				],
				[
					0,
					-103.09623430962344
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "G8Dtv27s",
			"type": "text",
			"x": 1329.032679079024,
			"y": 1859.9105992479,
			"width": 310.1293029785156,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1248030072,
			"version": 136,
			"versionNonce": 123541000,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"text": "Contrastive divergence\n(Training CRBM)",
			"rawText": "Contrastive divergence\n(Training CRBM)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Contrastive divergence\n(Training CRBM)",
			"lineHeight": 1.25
		},
		{
			"id": "iy0rUwLi",
			"type": "text",
			"x": 1117.9769010300515,
			"y": 1941.8762049862278,
			"width": 752.7991333007812,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 486531080,
			"version": 220,
			"versionNonce": 1583158536,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"text": "Our training objective is to maximization of the average data Log-likelihood",
			"rawText": "Our training objective is to maximization of the average data Log-likelihood",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Our training objective is to maximization of the average data Log-likelihood",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 319,
			"versionNonce": 1929720840,
			"isDeleted": false,
			"id": "HS9Z3Ih5YMnP3Lf_Jf7T5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1341.5103992826828,
			"y": 1968.2234391350696,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 278.52071537846575,
			"height": 76.41465780896368,
			"seed": 1588951672,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d7e7a54e673a3f3a9b8fbb07703258013bbcb761",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 425,
			"versionNonce": 458322696,
			"isDeleted": false,
			"id": "RytkxhGN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1278.96130840365,
			"y": 2326.704092025733,
			"strokeColor": "#1971c2",
			"backgroundColor": "#2f9e44",
			"width": 426.41693115234375,
			"height": 40,
			"seed": 101779832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The same can be done for y\nWe are trying to minimize the difference between them",
			"rawText": "The same can be done for y\nWe are trying to minimize the difference between them",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The same can be done for y\nWe are trying to minimize the difference between them",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 402,
			"versionNonce": 230543880,
			"isDeleted": false,
			"id": "0LKLUL8bzQLFmU3dmmcNb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1175.9409527617804,
			"y": 2371.6425976972882,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 615.0088752719657,
			"height": 59.21310834128335,
			"seed": 723589752,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe2b3efcf3c0208afe36ddc82f95c97868a12728",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 304,
			"versionNonce": 1363562760,
			"isDeleted": false,
			"id": "gvZdGJf3Hu0qYmo5dbhGi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1511.8997976182332,
			"y": 2421.752150932675,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 233.50302231004912,
			"height": 18.026265636144217,
			"seed": 906431352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.6768619196413965,
					0.41921547991023544
				],
				[
					-5.869016718744433,
					1.2576464397307063
				],
				[
					-9.641956037937462,
					2.934508359372103
				],
				[
					-14.253326316950961,
					4.611370279013499
				],
				[
					-18.445481116054225,
					5.44980123883397
				],
				[
					-21.79920495533679,
					6.288232198654896
				],
				[
					-25.991359754440055,
					7.126663158475367
				],
				[
					-28.087437153991687,
					7.545878638385602
				],
				[
					-30.602730033453554,
					7.965094118295838
				],
				[
					-33.11802291291542,
					8.384309598206528
				],
				[
					-35.633315792377516,
					8.803525078116763
				],
				[
					-39.40625511157032,
					10.06117151784747
				],
				[
					-42.75997895085288,
					10.48038699775816
				],
				[
					-47.37134922986638,
					10.899602477668395
				],
				[
					-51.98271950887988,
					11.31881795757863
				],
				[
					-58.27095170753478,
					12.576464397309792
				],
				[
					-63.30153746645851,
					12.995679877220027
				],
				[
					-68.75133870529294,
					13.414895357130263
				],
				[
					-74.62035542403737,
					13.414895357130263
				],
				[
					-80.07015666287157,
					14.253326316950734
				],
				[
					-85.1007424217953,
					15.09175727677166
				],
				[
					-90.5505436606295,
					15.09175727677166
				],
				[
					-95.58112941955346,
					15.93018823659213
				],
				[
					-100.19249969856696,
					15.93018823659213
				],
				[
					-106.0615164173114,
					16.349403716502366
				],
				[
					-111.5113176561456,
					16.7686191964126
				],
				[
					-115.70347245524886,
					16.7686191964126
				],
				[
					-121.57248917399329,
					16.7686191964126
				],
				[
					-125.76464397309655,
					17.18783467632329
				],
				[
					-130.37601425211005,
					17.18783467632329
				],
				[
					-134.98738453112355,
					17.18783467632329
				],
				[
					-139.59875481013705,
					17.18783467632329
				],
				[
					-143.37169412933008,
					17.18783467632329
				],
				[
					-146.72541796861265,
					17.18783467632329
				],
				[
					-150.9175727677159,
					17.18783467632329
				],
				[
					-155.10972756681895,
					17.18783467632329
				],
				[
					-159.72109784583267,
					16.349403716502366
				],
				[
					-165.17089908466664,
					15.510972756681895
				],
				[
					-171.87834676323178,
					14.672541796861424
				],
				[
					-178.16657896188667,
					13.414895357130263
				],
				[
					-184.45481116054157,
					12.576464397309792
				],
				[
					-189.06618143955507,
					12.576464397309792
				],
				[
					-194.0967671984788,
					11.738033437488866
				],
				[
					-197.4504910377616,
					11.31881795757863
				],
				[
					-199.96578391722346,
					11.31881795757863
				],
				[
					-201.2234303569544,
					11.31881795757863
				],
				[
					-201.64264583686463,
					11.31881795757863
				],
				[
					-202.0618613167751,
					11.31881795757863
				],
				[
					-202.90029227659556,
					10.899602477668395
				],
				[
					-204.15793871632673,
					10.48038699775816
				],
				[
					-205.41558515605766,
					10.48038699775816
				],
				[
					-205.8348006359679,
					10.06117151784747
				],
				[
					-207.09244707569883,
					9.641956037937234
				],
				[
					-208.76930899534023,
					9.641956037937234
				],
				[
					-210.4461709149814,
					9.222740558026999
				],
				[
					-212.1230328346228,
					8.803525078116763
				],
				[
					-212.96146379444338,
					8.384309598206528
				],
				[
					-213.79989475426407,
					7.965094118295838
				],
				[
					-214.63832571408466,
					7.545878638385602
				],
				[
					-215.47675667390536,
					7.126663158475367
				],
				[
					-217.572834073457,
					6.288232198654896
				],
				[
					-218.41126503327757,
					6.288232198654896
				],
				[
					-219.6689114730085,
					5.8690167187446605
				],
				[
					-220.92655791273955,
					5.44980123883397
				],
				[
					-221.76498887256014,
					5.030585758923735
				],
				[
					-222.60341983238072,
					4.192154799103264
				],
				[
					-223.86106627211177,
					3.7729393191930285
				],
				[
					-224.28028175202212,
					3.7729393191930285
				],
				[
					-225.1187127118427,
					3.3537238392823383
				],
				[
					-225.53792819175305,
					2.934508359372103
				],
				[
					-225.9571436716633,
					2.5152928794618674
				],
				[
					-226.37635915157364,
					2.096077399551632
				],
				[
					-227.21479011139434,
					1.6768619196413965
				],
				[
					-227.63400559130469,
					1.2576464397307063
				],
				[
					-228.47243655112527,
					0.8384309598204709
				],
				[
					-228.89165203103562,
					0.41921547991023544
				],
				[
					-229.73008299085632,
					0.41921547991023544
				],
				[
					-230.14929847076655,
					0
				],
				[
					-230.98772943058725,
					-0.41921547991023544
				],
				[
					-231.4069449104975,
					-0.41921547991023544
				],
				[
					-231.82616039040784,
					-0.41921547991023544
				],
				[
					-232.24537587031818,
					-0.41921547991023544
				],
				[
					-232.66459135022853,
					-0.8384309598209256
				],
				[
					-233.50302231004912,
					-0.8384309598209256
				],
				[
					-233.50302231004912,
					-0.8384309598209256
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 286,
			"versionNonce": 761720840,
			"isDeleted": false,
			"id": "_og1UbSCidBsd63q1s6fT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1547.1138979306997,
			"y": 2421.752150932675,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 236.0183151895112,
			"height": 8.384309598206528,
			"seed": 822533240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4192154799104628,
					0
				],
				[
					1.257646439731161,
					0.8384309598204709
				],
				[
					2.9345083593723302,
					1.2576464397307063
				],
				[
					4.192154799103264,
					1.6768619196413965
				],
				[
					5.8690167187446605,
					2.096077399551632
				],
				[
					7.54587863838583,
					2.5152928794618674
				],
				[
					9.641956037937462,
					2.934508359372103
				],
				[
					12.576464397309792,
					2.934508359372103
				],
				[
					15.09175727677166,
					3.7729393191930285
				],
				[
					18.02626563614399,
					4.192154799103264
				],
				[
					23.895282354888423,
					5.44980123883397
				],
				[
					31.02194551336379,
					6.707447678565131
				],
				[
					36.89096223210845,
					7.126663158475367
				],
				[
					42.75997895085288,
					7.965094118295838
				],
				[
					47.37134922986638,
					7.965094118295838
				],
				[
					51.14428854905941,
					8.384309598206528
				],
				[
					52.401934988790345,
					8.384309598206528
				],
				[
					55.33644334816245,
					8.384309598206528
				],
				[
					58.69016718744524,
					8.384309598206528
				],
				[
					62.88232198654828,
					8.384309598206528
				],
				[
					67.07447678565154,
					8.384309598206528
				],
				[
					70.84741610484434,
					8.384309598206528
				],
				[
					75.45878638385784,
					8.384309598206528
				],
				[
					77.97407926331994,
					8.384309598206528
				],
				[
					81.3278031026025,
					8.384309598206528
				],
				[
					85.10074242179553,
					8.384309598206528
				],
				[
					88.8736817409881,
					8.384309598206528
				],
				[
					93.48505202000183,
					8.384309598206528
				],
				[
					98.93485325883603,
					8.384309598206528
				],
				[
					103.12700805793929,
					8.384309598206528
				],
				[
					106.48073189722163,
					8.384309598206528
				],
				[
					111.09210217623536,
					8.384309598206528
				],
				[
					115.70347245524886,
					8.384309598206528
				],
				[
					120.31484273426236,
					8.384309598206528
				],
				[
					127.02229041282749,
					8.384309598206528
				],
				[
					132.89130713157192,
					8.384309598206528
				],
				[
					140.8564012498682,
					8.384309598206528
				],
				[
					160.9787442855636,
					8.384309598206528
				],
				[
					174.8128551226041,
					7.126663158475367
				],
				[
					186.97010404000366,
					7.126663158475367
				],
				[
					195.35441363820996,
					6.288232198654896
				],
				[
					199.96578391722346,
					5.8690167187446605
				],
				[
					201.64264583686463,
					5.8690167187446605
				],
				[
					202.48107679668556,
					5.8690167187446605
				],
				[
					202.9002922765958,
					5.8690167187446605
				],
				[
					204.57715419623696,
					5.8690167187446605
				],
				[
					206.25401611587813,
					5.8690167187446605
				],
				[
					207.93087803551953,
					5.8690167187446605
				],
				[
					210.02695543507116,
					5.8690167187446605
				],
				[
					212.1230328346228,
					5.8690167187446605
				],
				[
					213.38067927435372,
					5.8690167187446605
				],
				[
					215.47675667390536,
					5.8690167187446605
				],
				[
					217.99204955336745,
					5.8690167187446605
				],
				[
					223.0226353122912,
					5.44980123883397
				],
				[
					225.53792819175305,
					5.030585758923735
				],
				[
					228.47243655112516,
					4.611370279013499
				],
				[
					230.98772943058725,
					3.7729393191930285
				],
				[
					232.24537587031818,
					3.3537238392823383
				],
				[
					233.50302231004935,
					2.934508359372103
				],
				[
					233.92223778995958,
					2.5152928794618674
				],
				[
					234.34145326986982,
					2.5152928794618674
				],
				[
					234.76066874978005,
					2.5152928794618674
				],
				[
					235.17988422969051,
					2.096077399551632
				],
				[
					235.59909970960075,
					1.6768619196413965
				],
				[
					236.0183151895112,
					1.6768619196413965
				],
				[
					236.0183151895112,
					1.2576464397307063
				],
				[
					236.0183151895112,
					1.2576464397307063
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 438021896,
			"isDeleted": false,
			"id": "s05ZMlzx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1327.106095551529,
			"y": 2446.889786847832,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 110.51223754882812,
			"height": 20,
			"seed": 1038388600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "positive phase",
			"rawText": "positive phase",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "positive phase",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 803245576,
			"isDeleted": false,
			"id": "fSvKvZmn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1612.1231214608579,
			"y": 2434.3286153299846,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 116.48025512695312,
			"height": 20,
			"seed": 635707000,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "negative phase",
			"rawText": "negative phase",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "negative phase",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"id": "MaAhoAksC9Cq50PMEJW4t",
			"type": "arrow",
			"x": 1808.8404066411063,
			"y": 2177.525102378523,
			"width": 228.54986675010286,
			"height": 5.646227205762443,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 2074738440,
			"version": 252,
			"versionNonce": 145751160,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706721625397,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					228.54986675010286,
					5.646227205762443
				]
			],
			"lastCommittedPoint": [
				204.60957458489156,
				-2.861672371816894
			],
			"startBinding": {
				"elementId": "DR6BKjaIKjdSOJGv5Cske",
				"focus": -0.2936832194353017,
				"gap": 4.528808175152449
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "RGwPqEYv",
			"type": "text",
			"x": 2075.7458390141555,
			"y": 2155.665202993227,
			"width": 385.83953857421875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 747732232,
			"version": 408,
			"versionNonce": 2064296968,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"text": "This term is generally hard to compute\nover all values of x and y",
			"rawText": "This term is generally hard to compute\nover all values of x and y",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "This term is generally hard to compute\nover all values of x and y",
			"lineHeight": 1.25
		},
		{
			"id": "9xlWtFLJ",
			"type": "text",
			"x": 1250.4135714250403,
			"y": 2493.149613750977,
			"width": 497.13934326171875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1374710280,
			"version": 143,
			"versionNonce": 1944578824,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"text": "What this really is doing is the push pull approach",
			"rawText": "What this really is doing is the push pull approach",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "What this really is doing is the push pull approach",
			"lineHeight": 1.25
		},
		{
			"id": "7V3nmUpWTUMXoex9wdriH",
			"type": "image",
			"x": 1180.4775742524462,
			"y": 2535.262070969474,
			"width": 620.2192735135363,
			"height": 218.24015833852766,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1682946824,
			"version": 158,
			"versionNonce": 2093304328,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1a0b42c9e99c729659c286778394c8840c120f8e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "OV9uivBc",
			"type": "text",
			"x": 1133.7796864901256,
			"y": 2770.433849433834,
			"width": 727.67919921875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1595808776,
			"version": 388,
			"versionNonce": 1621018888,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721625195,
			"link": null,
			"locked": false,
			"text": "Since we want to associate low energy with high probability and we want\nto increase the probability of observing xi given our parameters\nand decrease the chance of finding random unrelated points samples from\nour model x,y given our parameters",
			"rawText": "Since we want to associate low energy with high probability and we want\nto increase the probability of observing xi given our parameters\nand decrease the chance of finding random unrelated points samples from\nour model x,y given our parameters",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Since we want to associate low energy with high probability and we want\nto increase the probability of observing xi given our parameters\nand decrease the chance of finding random unrelated points samples from\nour model x,y given our parameters",
			"lineHeight": 1.25
		},
		{
			"id": "nCuJYs49yS7j8SVakYiP1",
			"type": "arrow",
			"x": 1815.6794419323126,
			"y": 2166.145273432205,
			"width": 1135.6860022890298,
			"height": 295.54401813954314,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1036336760,
			"version": 166,
			"versionNonce": 237818376,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706721643643,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					762.1050804834283,
					-295.54401813954314
				],
				[
					1135.6860022890298,
					-147.77200906977168
				]
			],
			"lastCommittedPoint": [
				1079.2337741050726,
				-328.75121118893003
			],
			"startBinding": {
				"elementId": "DR6BKjaIKjdSOJGv5Cske",
				"focus": 0.7519210386755287,
				"gap": 11.36784346635875
			},
			"endBinding": {
				"elementId": "8V-IcxqjbCgPz6IC0A4fU",
				"focus": -0.2641814329852796,
				"gap": 13.00235941587107
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 472,
			"versionNonce": 1809142024,
			"isDeleted": false,
			"id": "8V-IcxqjbCgPz6IC0A4fU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2837.9591214158895,
			"y": 2031.3756237783045,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 645.2232780331811,
			"height": 57.01326379172506,
			"seed": 951249528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "nCuJYs49yS7j8SVakYiP1",
					"type": "arrow"
				}
			],
			"updated": 1706721643643,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6fa4af893c110fe256a85c5e2c3b5f9e4b29fcf1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JTE59MnD",
			"type": "text",
			"x": 2654.1191964063596,
			"y": 2106.259327299925,
			"width": 1013.0589599609375,
			"height": 200,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 485142280,
			"version": 572,
			"versionNonce": 1869688952,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721774363,
			"link": null,
			"locked": false,
			"text": "This gradient is the direction of the steepest ascent on the loss function\n\nthe first term represents how apparent the features of xi are in the dataset\nthe second term represents how apparent the features of xi are in our models probability distribution\n\nif this term is very high, it means that this point is very likely to appear in the datset\nbut is not very likely to appear in our model! which is bad because we want our model\nto represent the dataset well THUS steepest ascent",
			"rawText": "This gradient is the direction of the steepest ascent on the loss function\n\nthe first term represents how apparent the features of xi are in the dataset\nthe second term represents how apparent the features of xi are in our models probability distribution\n\nif this term is very high, it means that this point is very likely to appear in the datset\nbut is not very likely to appear in our model! which is bad because we want our model\nto represent the dataset well THUS steepest ascent",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 193,
			"containerId": null,
			"originalText": "This gradient is the direction of the steepest ascent on the loss function\n\nthe first term represents how apparent the features of xi are in the dataset\nthe second term represents how apparent the features of xi are in our models probability distribution\n\nif this term is very high, it means that this point is very likely to appear in the datset\nbut is not very likely to appear in our model! which is bad because we want our model\nto represent the dataset well THUS steepest ascent",
			"lineHeight": 1.25
		},
		{
			"id": "1K61umkF",
			"type": "text",
			"x": 1079.2035743879098,
			"y": 2905.7580079628337,
			"width": 872.879150390625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2090275080,
			"version": 335,
			"versionNonce": 576696696,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706721921260,
			"link": null,
			"locked": false,
			"text": "Increasing the energy of things we dont want to sample from our probability distribution\nthat we built (aka lowering their prob)\nDecreasing the energy of things we do want to sample from our models probability\ndistribution (aka increasing their prob)",
			"rawText": "Increasing the energy of things we dont want to sample from our probability distribution\nthat we built (aka lowering their prob)\nDecreasing the energy of things we do want to sample from our models probability\ndistribution (aka increasing their prob)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Increasing the energy of things we dont want to sample from our probability distribution\nthat we built (aka lowering their prob)\nDecreasing the energy of things we do want to sample from our models probability\ndistribution (aka increasing their prob)",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#a5d8ff",
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
		"scrollX": 919.9918681549241,
		"scrollY": -1720.8658381274706,
		"zoom": {
			"value": 1.2201920208555466
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
		}
	},
	"files": {}
}
```
%%