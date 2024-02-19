---

excalidraw-plugin: parsed
tags: [excalidraw]

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
5bb2314e17612e74757424160f3480a4c78b8b80: [[cropped_Pasted Image 20240215191602_590 1]]
2646750f6b6d22acba1c96599d79cde205e3ae60: [[Pasted Image 20240215192235_660.png]]
a94abb57e2925fffb0c1acc67a41ef20cb7b6227: [[cropped_Pasted Image 20240215192355_400 1]]
7f69a0d880f68b5f2bc447904883f3ffc7ea9754: [[Pasted Image 20240216141619_812.png]]
0a1244723d968856aaf3380630be993482a83ed9: [[Pasted Image 20240216141649_827.png]]
cf32ef4a285d2f19ff5d5ba85a7461a7e1e20171: [[Pasted Image 20240216144038_002.png]]
79a2a750811e26419c6d86cf486694eddda9dbc6: [[Pasted Image 20240216144223_008.png]]
2046eabfb19e5a1890fa740b7637ac4280251907: [[Pasted Image 20240216144339_015.png]]
4dbe47bfdca823be02051c7f1bd4e08ec8798d51: [[Pasted Image 20240216154632_695.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.20",
	"elements": [
		{
			"type": "line",
			"version": 816,
			"versionNonce": 766278865,
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
			"updated": 1708107142295,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 516,
			"versionNonce": 788739263,
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
			"updated": 1708107142295,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 811,
			"versionNonce": 495368881,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 657,
			"versionNonce": 1868317919,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 431,
			"versionNonce": 1998470289,
			"isDeleted": false,
			"id": "wr5NT7C2AIue2FCw2kVhn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 391.92512466979423,
			"y": 988.6230312121758,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 745.4552506529132,
			"height": 408.3562274540571,
			"seed": 1159410463,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 1046368511,
			"isDeleted": false,
			"id": "F-kqvmdImlARDvOCvK2n4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 842.4449595162596,
			"y": 1231.3496053751683,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 192.30307030605172,
			"height": 88.30700431303532,
			"seed": 1265618737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142296,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 598,
			"versionNonce": 438993521,
			"isDeleted": false,
			"id": "vRE5unLHRMUH24cRydgNZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 843.2610383169803,
			"y": 1208.6256124568354,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 191.42944046112157,
			"height": 228.91770588475777,
			"seed": 1320964657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142296,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 346,
			"versionNonce": 1435097375,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 269,
			"versionNonce": 57871441,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 1783586111,
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
			"updated": 1708107142296,
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
			"version": 255,
			"versionNonce": 718232113,
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
			"updated": 1708107142296,
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
			"version": 201,
			"versionNonce": 806313311,
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
			"updated": 1708107142296,
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
			"version": 851,
			"versionNonce": 556198929,
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
			"updated": 1708107142296,
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
			"version": 468,
			"versionNonce": 437934463,
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
			"updated": 1708107142296,
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
			"version": 682,
			"versionNonce": 1852916209,
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
			"updated": 1708107142296,
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
			"version": 608,
			"versionNonce": 1571869087,
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
			"updated": 1708107142296,
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
			"version": 360,
			"versionNonce": 800447441,
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
			"updated": 1708107142296,
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
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "line",
			"version": 393,
			"versionNonce": 872629695,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 453,
			"versionNonce": 1963735473,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 549,
			"versionNonce": 1546794463,
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
			"updated": 1708107142296,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 484,
			"versionNonce": 1604049809,
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
			"updated": 1708107142296,
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
			"lineHeight": 1.25,
			"baseline": 13
		},
		{
			"type": "arrow",
			"version": 1769,
			"versionNonce": 1565401599,
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
			"updated": 1708107142296,
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
			"version": 657,
			"versionNonce": 2140946801,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 398,
			"versionNonce": 139954719,
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
			"updated": 1708107142296,
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
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 390,
			"versionNonce": 1918167889,
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
			"updated": 1708107142296,
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
			"version": 938,
			"versionNonce": 977202751,
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
			"updated": 1708107142296,
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
			"version": 357,
			"versionNonce": 1075665201,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 417,
			"versionNonce": 1575276127,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 962,
			"versionNonce": 2052918033,
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
			"updated": 1708107142296,
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
			"version": 790,
			"versionNonce": 773433983,
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
			"updated": 1708107142296,
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
			"version": 708,
			"versionNonce": 428572913,
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
			"updated": 1708107142296,
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
			"version": 498,
			"versionNonce": 933102239,
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
			"updated": 1708107142296,
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
			"version": 364,
			"versionNonce": 456145617,
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
			"updated": 1708107142296,
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
			"version": 317,
			"versionNonce": 455235263,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 315,
			"versionNonce": 1608693937,
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
			"updated": 1708107142296,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 299,
			"versionNonce": 256321247,
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
			"updated": 1708107142296,
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
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 1229617809,
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
			"updated": 1708107142296,
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
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 265,
			"versionNonce": 580711167,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 300,
			"versionNonce": 404684913,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 1034173215,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 170379857,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 448,
			"versionNonce": 1691189055,
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
			"updated": 1708107142297,
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
			"version": 416,
			"versionNonce": 943478833,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 324,
			"versionNonce": 981024607,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "image",
			"version": 508,
			"versionNonce": 876882449,
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
			"updated": 1708107142297,
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
			"version": 523,
			"versionNonce": 1089993599,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 593,
			"versionNonce": 1731641329,
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
			"updated": 1708107142297,
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
			"version": 561,
			"versionNonce": 1552561055,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 790338001,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "text",
			"version": 378,
			"versionNonce": 358639551,
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
			"width": 25.328133817439166,
			"height": 16.90477798735204,
			"seed": 770610751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "line",
			"version": 1281,
			"versionNonce": 1024079793,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1521,
			"versionNonce": 429594591,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1645,
			"versionNonce": 858397073,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1449,
			"versionNonce": 2135606271,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1460,
			"versionNonce": 45268849,
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
			"updated": 1708107142297,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 888,
			"versionNonce": 1181740063,
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
			"updated": 1708107142297,
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
			"version": 423,
			"versionNonce": 166439249,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "arrow",
			"version": 429,
			"versionNonce": 452661311,
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
			"updated": 1708107142297,
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
			"version": 461,
			"versionNonce": 1915508529,
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
			"updated": 1708107142297,
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
			"version": 532,
			"versionNonce": 1456255071,
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
			"updated": 1708107142297,
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
			"version": 255,
			"versionNonce": 1306282257,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 235,
			"versionNonce": 1135955071,
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
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "ellipse",
			"version": 897,
			"versionNonce": 1987247857,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142297,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 494232735,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 712505553,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1404926143,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1803728561,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 204343519,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 473610385,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1683461375,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142297,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1582792305,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1941609759,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 815827025,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 231186751,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1290622513,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1138696543,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 1176856593,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 659660159,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1715486193,
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
			"width": 4.192945692274306,
			"height": 23.938914311746096,
			"seed": 54816,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1264555423,
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
			"width": 8.941114637586805,
			"height": 23.938914311746096,
			"seed": 74788,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1279612881,
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
			"width": 12.770290798611112,
			"height": 23.938914311746096,
			"seed": 92764,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 121211327,
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
			"width": 5.035359700520834,
			"height": 23.938914311746096,
			"seed": 95093,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1246508465,
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
			"width": 5.035359700520834,
			"height": 23.938914311746096,
			"seed": 56869,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 2013264351,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 58480529,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1120101887,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1242381681,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142298,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 377769503,
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
			"width": 9.572930230034723,
			"height": 23.938914311746096,
			"seed": 37462,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1028024145,
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
			"width": 12.770290798611112,
			"height": 23.938914311746096,
			"seed": 52189,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1848848959,
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
			"width": 8.941114637586805,
			"height": 23.938914311746096,
			"seed": 69731,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 662656305,
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
			"width": 9.572930230034723,
			"height": 23.938914311746096,
			"seed": 22544,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 313561695,
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
			"width": 10.472785101996529,
			"height": 23.938914311746096,
			"seed": 49183,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 471828241,
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
			"width": 10.759975857204862,
			"height": 23.938914311746096,
			"seed": 23509,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1556934271,
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
			"width": 9.438910590277779,
			"height": 23.938914311746096,
			"seed": 93416,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1436450033,
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
			"width": 5.035359700520834,
			"height": 23.938914311746096,
			"seed": 7181,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 927516319,
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
			"width": 12.770290798611112,
			"height": 23.938914311746096,
			"seed": 21344,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1401140945,
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
			"width": 8.941114637586805,
			"height": 23.938914311746096,
			"seed": 29477,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1624545983,
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
			"width": 12.770290798611112,
			"height": 23.938914311746096,
			"seed": 87470,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 946255025,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1846602463,
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
			"width": 4.192945692274306,
			"height": 23.938914311746096,
			"seed": 16903,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1743713937,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 193869567,
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
			"width": 8.941114637586805,
			"height": 23.938914311746096,
			"seed": 22625,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1691614321,
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
			"width": 9.572930230034723,
			"height": 23.938914311746096,
			"seed": 7776,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 2144141087,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1859995217,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1832764223,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1625445425,
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
			"width": 9.572930230034723,
			"height": 23.938914311746096,
			"seed": 27508,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1413546847,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1321903633,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1428635519,
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
			"width": 4.192945692274306,
			"height": 23.938914311746096,
			"seed": 80863,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1670233073,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 842069919,
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
			"width": 9.572930230034723,
			"height": 23.938914311746096,
			"seed": 9902,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 2134054353,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 294562751,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 349320113,
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
			"width": 4.192945692274306,
			"height": 23.938914311746096,
			"seed": 12713,
			"groupIds": [
				"8QNctGWb",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 2137054175,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "ellipse",
			"version": 413,
			"versionNonce": 1217566097,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 450,
			"versionNonce": 800589823,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 443,
			"versionNonce": 1303100273,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 462,
			"versionNonce": 9744415,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 500,
			"versionNonce": 73737553,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 466,
			"versionNonce": 1005016127,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 426,
			"versionNonce": 1477858097,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 431,
			"versionNonce": 428897375,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 433,
			"versionNonce": 1562821905,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 447,
			"versionNonce": 23105663,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 504,
			"versionNonce": 789445361,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 293,
			"versionNonce": 219687071,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142299,
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
			"lineHeight": 1.25,
			"baseline": 16
		},
		{
			"type": "ellipse",
			"version": 1317,
			"versionNonce": 240350417,
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
				"HkYyA3GHFMX_shJxgMn8r"
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
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1296,
			"versionNonce": 1248312511,
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
				"HkYyA3GHFMX_shJxgMn8r"
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
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1369,
			"versionNonce": 1049539249,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1329,
			"versionNonce": 1022348511,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1241,
			"versionNonce": 610743441,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1341,
			"versionNonce": 541120767,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1347,
			"versionNonce": 596933233,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1343,
			"versionNonce": 1775984927,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142299,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1359,
			"versionNonce": 1021183057,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1355,
			"versionNonce": 187688255,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1458,
			"versionNonce": 1813729841,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1460,
			"versionNonce": 1939793247,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1460,
			"versionNonce": 1177805841,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1476,
			"versionNonce": 1383653759,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1284,
			"versionNonce": 1461664241,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1383,
			"versionNonce": 419322271,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1384,
			"versionNonce": 1071961041,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1385,
			"versionNonce": 1012911551,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1410,
			"versionNonce": 345780657,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 954,
			"versionNonce": 935181791,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 986,
			"versionNonce": 2053952401,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 971,
			"versionNonce": 1311287807,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 993,
			"versionNonce": 93206897,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1000,
			"versionNonce": 211882527,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 983,
			"versionNonce": 1464329041,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 990,
			"versionNonce": 202864191,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 970,
			"versionNonce": 2079412529,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 985,
			"versionNonce": 1936479839,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 985,
			"versionNonce": 150078225,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 981,
			"versionNonce": 963654271,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 970,
			"versionNonce": 2059499761,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 960,
			"versionNonce": 652446367,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 969,
			"versionNonce": 1390883537,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 990,
			"versionNonce": 410443455,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 971,
			"versionNonce": 1979363505,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 979,
			"versionNonce": 13283039,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 985,
			"versionNonce": 1235448465,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 969,
			"versionNonce": 711949055,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 993,
			"versionNonce": 312014961,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 988,
			"versionNonce": 971359007,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 985,
			"versionNonce": 312656465,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 979,
			"versionNonce": 1872627519,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 967,
			"versionNonce": 1721258033,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 991,
			"versionNonce": 704169823,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1037,
			"versionNonce": 610345489,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1069,
			"versionNonce": 658932607,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1054,
			"versionNonce": 955561969,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1076,
			"versionNonce": 130530207,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1083,
			"versionNonce": 106598865,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1066,
			"versionNonce": 262991807,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1073,
			"versionNonce": 1101672369,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1053,
			"versionNonce": 689348575,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1068,
			"versionNonce": 285938065,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1068,
			"versionNonce": 638929919,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1064,
			"versionNonce": 1773451121,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1053,
			"versionNonce": 1118401567,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1043,
			"versionNonce": 770613585,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1052,
			"versionNonce": 1724094527,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1073,
			"versionNonce": 185618225,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1054,
			"versionNonce": 675559519,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1062,
			"versionNonce": 394346769,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1068,
			"versionNonce": 217830527,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1052,
			"versionNonce": 817428209,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1076,
			"versionNonce": 212528287,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1071,
			"versionNonce": 423555281,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1068,
			"versionNonce": 1392640191,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1062,
			"versionNonce": 1454026417,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1050,
			"versionNonce": 1101107423,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1074,
			"versionNonce": 1336127633,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 973,
			"versionNonce": 840572159,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 975,
			"versionNonce": 702641777,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142300,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 990,
			"versionNonce": 2011964703,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 978,
			"versionNonce": 1747681361,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 982,
			"versionNonce": 579348799,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 972,
			"versionNonce": 1213812273,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 971,
			"versionNonce": 2135861599,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 984,
			"versionNonce": 1632788497,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 961,
			"versionNonce": 1536173439,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 982,
			"versionNonce": 17708529,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 968,
			"versionNonce": 109911455,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 960,
			"versionNonce": 1251233745,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 976,
			"versionNonce": 326504895,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 971,
			"versionNonce": 335293873,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 987,
			"versionNonce": 1533772255,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 988,
			"versionNonce": 74272657,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 972,
			"versionNonce": 1065217535,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 971,
			"versionNonce": 1914647921,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 975,
			"versionNonce": 716035615,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 968,
			"versionNonce": 5857105,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 1428,
			"versionNonce": 1407957567,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 974,
			"versionNonce": 2104708401,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 956,
			"versionNonce": 1075321439,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 968,
			"versionNonce": 13926161,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 965,
			"versionNonce": 67335807,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 962,
			"versionNonce": 1223980273,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 445,
			"versionNonce": 1181634207,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 7
		},
		{
			"type": "arrow",
			"version": 748,
			"versionNonce": 1499115217,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
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
			"version": 410,
			"versionNonce": 34153151,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 5
		},
		{
			"type": "arrow",
			"version": 760,
			"versionNonce": 1486793905,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
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
			"version": 1331,
			"versionNonce": 125072095,
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
			"height": 45.17298663724525,
			"seed": 1399814719,
			"groupIds": [
				"C38T4UOb2BS9qiQWMNlLN",
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 537,
			"versionNonce": 778563217,
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
				"HkYyA3GHFMX_shJxgMn8r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 26
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 1061207807,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "rectangle",
			"version": 168,
			"versionNonce": 1634595953,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 222,
			"versionNonce": 737052447,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 220,
			"versionNonce": 897072721,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 249,
			"versionNonce": 737037119,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 123,
			"versionNonce": 157174833,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 189,
			"versionNonce": 2074119007,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1963433489,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 234,
			"versionNonce": 2002110335,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 661369841,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 211,
			"versionNonce": 491683743,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 76680657,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1337668543,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 431,
			"versionNonce": 59911089,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "line",
			"version": 596,
			"versionNonce": 1455186911,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 234,
			"versionNonce": 1284738449,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "line",
			"version": 475,
			"versionNonce": 576884735,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 654,
			"versionNonce": 382579569,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 218
		},
		{
			"type": "image",
			"version": 453,
			"versionNonce": 1286486047,
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
			"updated": 1708107142301,
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
			"version": 378,
			"versionNonce": 1183325521,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 272,
			"versionNonce": 1536154687,
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
			"updated": 1708107142301,
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
			"version": 419,
			"versionNonce": 1260014385,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "line",
			"version": 696,
			"versionNonce": 1122499679,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 389,
			"versionNonce": 1022082321,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 427,
			"versionNonce": 646387839,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 482,
			"versionNonce": 997454577,
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
			"updated": 1708107142301,
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
			"version": 384,
			"versionNonce": 1546498207,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 340,
			"versionNonce": 188378321,
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
			"updated": 1708107142301,
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
			"version": 554,
			"versionNonce": 764167359,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 40
		},
		{
			"type": "text",
			"version": 324,
			"versionNonce": 1943448241,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 350,
			"versionNonce": 1514362079,
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
			"updated": 1708107142301,
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
			"version": 260,
			"versionNonce": 1576021137,
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
			"updated": 1708107142301,
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
			"version": 320,
			"versionNonce": 1508073727,
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
			"updated": 1708107142301,
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
			"version": 714,
			"versionNonce": 826176113,
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
			"updated": 1708107142301,
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
			"version": 291,
			"versionNonce": 1575807263,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 422,
			"versionNonce": 1921580113,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 261,
			"versionNonce": 332426559,
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
			"updated": 1708107142301,
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
			"version": 313,
			"versionNonce": 564611633,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 653159775,
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
			"updated": 1708107142301,
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
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "line",
			"version": 522,
			"versionNonce": 1468062737,
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
			"updated": 1708107142301,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 298,
			"versionNonce": 43477375,
			"isDeleted": false,
			"id": "wjyw97Vf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 413.75591731433,
			"y": 1001.0969846710024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 709.64111328125,
			"height": 100,
			"seed": 481789745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 176,
			"versionNonce": 604844529,
			"isDeleted": false,
			"id": "7TCQJl6q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 636.0983234602794,
			"y": 986.3605180709512,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f8f0fc",
			"width": 11.379989624023438,
			"height": 25,
			"seed": 2017824223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 336,
			"versionNonce": 1410064799,
			"isDeleted": false,
			"id": "0d_5CjVOChzDOKXZgMc0d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 615.9129512336407,
			"y": 1123.093038595897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 36.10088098766664,
			"height": 228.03723157209456,
			"seed": 337231857,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 565,
			"versionNonce": 743689169,
			"isDeleted": false,
			"id": "jLrNMSWm5xYN2bKubKIGf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 843.375725196259,
			"y": 1208.6605165067795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 36.10088098766664,
			"height": 72.30855625438592,
			"seed": 1693555889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 237,
			"versionNonce": 1283216831,
			"isDeleted": false,
			"id": "I52zIeb5hmtLm6YxBfka5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 650.776571479438,
			"y": 1148.597724719641,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 514140049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 255,
			"versionNonce": 141306289,
			"isDeleted": false,
			"id": "lphiG1XI-wWC_3kEuQ1O4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 652.0024104449961,
			"y": 1171.8886650652485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 11256017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 261,
			"versionNonce": 587810271,
			"isDeleted": false,
			"id": "QeU2pj4OYca1A65C5RD1s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 650.7765714794381,
			"y": 1193.9537664452987,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 255582367,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 280,
			"versionNonce": 1635634065,
			"isDeleted": false,
			"id": "3oGzKY_oi540gDegysJPN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 650.7765714794382,
			"y": 1214.4865691184004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1687547999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 282,
			"versionNonce": 1455632895,
			"isDeleted": false,
			"id": "GiNB4X948cjlN1BeJ3qxo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 652.6153299277752,
			"y": 1237.4710497226188,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 2133337439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 257,
			"versionNonce": 1337995633,
			"isDeleted": false,
			"id": "-bGnaAjKxkjzkOJ8f-G5X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 650.7765714794378,
			"y": 1260.455530326837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1681743935,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 273,
			"versionNonce": 816486943,
			"isDeleted": false,
			"id": "AzpPr-7Eh-NKZH2alVoAQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 651.6959507036066,
			"y": 1282.5206317068864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1079735569,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 262,
			"versionNonce": 2021317457,
			"isDeleted": false,
			"id": "OhqDn0BTAQUGigiV2FvXd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 650.1636519966587,
			"y": 1306.4244915352738,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1207082655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 259,
			"versionNonce": 95419967,
			"isDeleted": false,
			"id": "LfGVdXTVMlGU5EeixU4N7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 651.6959507036069,
			"y": 1327.263753949765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 191023633,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 354,
			"versionNonce": 1812285745,
			"isDeleted": false,
			"id": "tGxuCwi0mReGUgkaBtDPr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 879.9567244613534,
			"y": 1231.5664131643125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 1222718865,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 296,
			"versionNonce": 951311967,
			"isDeleted": false,
			"id": "zjc_gOiznqqap9eLsNlwN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 878.4470822837391,
			"y": 1258.3625618169654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fa5252",
			"width": 34.93641051841189,
			"height": 0,
			"seed": 544372543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 261,
			"versionNonce": 1137113873,
			"isDeleted": false,
			"id": "iNFVYawcHlbPkLxtwXkxh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 843.2405814375658,
			"y": 1182.1256319999998,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 36.236024562434295,
			"height": 26.796148500098298,
			"seed": 569346833,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 293,
			"versionNonce": 2089204351,
			"isDeleted": false,
			"id": "MJpmFzmJWWDqjlN7h9Znw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 843.3177446557008,
			"y": 1280.9690732390113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 36.236024562434295,
			"height": 26.796148500098298,
			"seed": 1151588767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 522,
			"versionNonce": 3633393,
			"isDeleted": false,
			"id": "P_CdElk43YANTP-weN6qK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 652.9876862634878,
			"y": 1123.5186177523897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.97704714180884,
			"height": 86.20778153917502,
			"seed": 950749055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 708,
			"versionNonce": 1441338015,
			"isDeleted": false,
			"id": "tHv44G781Xc4U_3ZMjAe5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 652.2557423414105,
			"y": 1147.6522887662622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.97704714180884,
			"height": 84.27330910184162,
			"seed": 8898801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 433,
			"versionNonce": 652094161,
			"isDeleted": false,
			"id": "A2sshwM6AYA_FsKF2VwoN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 843.0276546349274,
			"y": 1231.479252892203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 191.63347074104036,
			"height": 59.61930200832376,
			"seed": 1383327711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 405,
			"versionNonce": 1569416895,
			"isDeleted": false,
			"id": "WoNRMPSe6cNdEuvFD0W-r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 843.3115560730623,
			"y": 1232.3309572066078,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 191.63347074104036,
			"height": 38.61059558634315,
			"seed": 616050527,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 705,
			"versionNonce": 542288049,
			"isDeleted": false,
			"id": "uqNvgE0d8ytuPSFgIckkB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 652.5026517710551,
			"y": 1351.1897904825832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 191.4061782251083,
			"height": 70.77571620006199,
			"seed": 1303721553,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 901,
			"versionNonce": 1108227807,
			"isDeleted": false,
			"id": "2CgPI2KpgvEE2p5pXs393",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 652.6289700155767,
			"y": 1326.626988385411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.54791605850937,
			"height": 69.15886693875962,
			"seed": 2134656049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 618,
			"versionNonce": 1446800017,
			"isDeleted": false,
			"id": "gfA4ApW6EMhQ8iUdN9j2E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 842.971751225794,
			"y": 1258.2487432582507,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 190.56064303279175,
			"height": 48.03276275923872,
			"seed": 1818662417,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 590,
			"versionNonce": 167903999,
			"isDeleted": false,
			"id": "C2SjMIX2buDVDlnGHZtBI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 844.113914830528,
			"y": 1257.397038943846,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fdf8f6",
			"width": 192.06260182433982,
			"height": 25.52209754571004,
			"seed": 1210821617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 603,
			"versionNonce": 290648177,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 142,
			"versionNonce": 367479583,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 203,
			"versionNonce": 392018513,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 494,
			"versionNonce": 1647218495,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 238,
			"versionNonce": 154421297,
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
			"updated": 1708107142302,
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
			"version": 218,
			"versionNonce": 154685279,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 258,
			"versionNonce": 12458513,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 239,
			"versionNonce": 89459583,
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
			"updated": 1708107142302,
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
			"version": 286,
			"versionNonce": 1861398513,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 161,
			"versionNonce": 851788703,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 491,
			"versionNonce": 970557905,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 422,
			"versionNonce": 297367487,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 472,
			"versionNonce": 445261745,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 510,
			"versionNonce": 1213343711,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 363,
			"versionNonce": 992741777,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 13
		},
		{
			"type": "text",
			"version": 365,
			"versionNonce": 1688196095,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 130
		},
		{
			"type": "text",
			"version": 354,
			"versionNonce": 351711089,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "image",
			"version": 376,
			"versionNonce": 1587739679,
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
			"updated": 1708107142302,
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
			"version": 432,
			"versionNonce": 238131537,
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
			"updated": 1708107142302,
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
			"version": 428,
			"versionNonce": 1514938431,
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
			"updated": 1708107142302,
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
			"version": 451,
			"versionNonce": 1479821105,
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
			"updated": 1708107142302,
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
			"version": 348,
			"versionNonce": 695976031,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 371,
			"versionNonce": 224803089,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 366,
			"versionNonce": 235035775,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 365,
			"versionNonce": 255782641,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 381,
			"versionNonce": 1000371359,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 480,
			"versionNonce": 608561361,
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
			"updated": 1708107142302,
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
			"version": 478,
			"versionNonce": 436635839,
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
			"updated": 1708107142302,
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
			"version": 498,
			"versionNonce": 1444062897,
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
			"updated": 1708107142302,
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
			"version": 1868,
			"versionNonce": 1188370655,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 403,
			"versionNonce": 256682129,
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
			"updated": 1708107142302,
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
			"version": 620,
			"versionNonce": 1469883647,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 551,
			"versionNonce": 2041278065,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 575,
			"versionNonce": 1541254431,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 613,
			"versionNonce": 469137489,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 492,
			"versionNonce": 520663359,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 13
		},
		{
			"type": "text",
			"version": 498,
			"versionNonce": 939869745,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 130
		},
		{
			"type": "text",
			"version": 457,
			"versionNonce": 712913247,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "image",
			"version": 479,
			"versionNonce": 1757370385,
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
			"updated": 1708107142302,
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
			"version": 535,
			"versionNonce": 126791039,
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
			"updated": 1708107142302,
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
			"version": 531,
			"versionNonce": 1846769,
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
			"updated": 1708107142302,
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
			"version": 554,
			"versionNonce": 1098556831,
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
			"updated": 1708107142302,
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
			"version": 451,
			"versionNonce": 623069137,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 474,
			"versionNonce": 661821887,
			"isDeleted": false,
			"id": "yhfSU1aA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2032.0609002809945,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 470,
			"versionNonce": 837559729,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 469,
			"versionNonce": 1318521311,
			"isDeleted": false,
			"id": "PJnJydAD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2035.1924277175142,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 484,
			"versionNonce": 1369327505,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 583,
			"versionNonce": 1408792063,
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
			"updated": 1708107142302,
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
			"version": 601,
			"versionNonce": 1584475505,
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
			"updated": 1708107142302,
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
			"version": 1971,
			"versionNonce": 1586978335,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 518,
			"versionNonce": 2142000977,
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
			"updated": 1708107142302,
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
			"version": 496,
			"versionNonce": 1633960511,
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
			"updated": 1708107142302,
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
			"lineHeight": 1.15,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 115,
			"versionNonce": 128402737,
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
			"updated": 1708107142302,
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
			"version": 130,
			"versionNonce": 490709599,
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
			"updated": 1708107142302,
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
			"version": 156,
			"versionNonce": 298415889,
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
			"updated": 1708107142302,
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
			"version": 133,
			"versionNonce": 1660550783,
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
			"updated": 1708107142302,
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
			"version": 2081,
			"versionNonce": 1619684593,
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
			"updated": 1708107142302,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 163,
			"versionNonce": 357815967,
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
			"updated": 1708107142303,
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
			"version": 2104,
			"versionNonce": 2071045841,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 185,
			"versionNonce": 1795009215,
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
			"updated": 1708107142303,
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
			"version": 128,
			"versionNonce": 219587761,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 96,
			"versionNonce": 1889008351,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 13
		},
		{
			"type": "line",
			"version": 105,
			"versionNonce": 18933393,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 181,
			"versionNonce": 1253263103,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "text",
			"version": 217,
			"versionNonce": 1648880753,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "image",
			"version": 120,
			"versionNonce": 936382239,
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
			"updated": 1708107142303,
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
			"version": 431,
			"versionNonce": 2018719313,
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
			"updated": 1708107142303,
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
			"version": 2210,
			"versionNonce": 1381946175,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 560,
			"versionNonce": 639255601,
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
			"updated": 1708107142303,
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
			"version": 544,
			"versionNonce": 314577759,
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
			"updated": 1708107142303,
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
			"version": 1224,
			"versionNonce": 126129681,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 472,
			"versionNonce": 289689471,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 46
		},
		{
			"type": "image",
			"version": 412,
			"versionNonce": 1334422513,
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
			"updated": 1708107142303,
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
			"version": 426,
			"versionNonce": 137103263,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 376,
			"versionNonce": 1714488785,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 46
		},
		{
			"type": "line",
			"version": 496,
			"versionNonce": 363314111,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 528,
			"versionNonce": 1183982513,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 79
		},
		{
			"type": "line",
			"version": 522,
			"versionNonce": 1037560799,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 548,
			"versionNonce": 483689873,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 101
		},
		{
			"type": "text",
			"version": 241,
			"versionNonce": 751638527,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 411,
			"versionNonce": 607103857,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 469,
			"versionNonce": 948420639,
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
			"updated": 1708107142303,
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
			"version": 135,
			"versionNonce": 1156257105,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 609,
			"versionNonce": 1345096529,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 602,
			"versionNonce": 2133937727,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 263,
			"versionNonce": 1107360049,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 317,
			"versionNonce": 361442911,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 273,
			"versionNonce": 1053600529,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 289,
			"versionNonce": 1643383423,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 296,
			"versionNonce": 1862738161,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 295,
			"versionNonce": 1093427871,
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
			"updated": 1708272847253,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 288,
			"versionNonce": 3660497,
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
			"updated": 1708272847254,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 308,
			"versionNonce": 602191551,
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
			"updated": 1708272847254,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 305,
			"versionNonce": 49698993,
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
			"updated": 1708272847254,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 324,
			"versionNonce": 280856287,
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
			"updated": 1708272847254,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 318,
			"versionNonce": 149559953,
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
			"updated": 1708272847254,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 312,
			"versionNonce": 1715950335,
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
			"updated": 1708272847254,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 458,
			"versionNonce": 46833777,
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
			"updated": 1708272847254,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 1008,
			"versionNonce": 1560451871,
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
			"updated": 1708272847254,
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
			"lineHeight": 1.25,
			"baseline": 243
		},
		{
			"type": "text",
			"version": 517,
			"versionNonce": 70317375,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "line",
			"version": 541,
			"versionNonce": 1265844785,
			"isDeleted": false,
			"id": "P1ppElHUQV7gvtGRK3ui7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1287.184436430997,
			"y": 2055.2050072984857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 27.82399367495381,
			"height": 76.28151074931168,
			"seed": 1088049233,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-26.260847962877772,
					26.260847962877595
				],
				[
					-27.823993674953808,
					-23.759814823556134
				],
				[
					-0.9378874272456592,
					-50.02066278643409
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 501,
			"versionNonce": 1241380191,
			"isDeleted": false,
			"id": "xNWKtHJ2GgnNLtWyapOh6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1270.227098115336,
			"y": 2059.6273734145307,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 229.2924420162593,
			"height": 94.91203542476295,
			"seed": 1737152927,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					75.4910908824023,
					27.56521160851198
				],
				[
					143.15115573965903,
					12.216400599226827
				],
				[
					192.01675813656678,
					-12.529641640232782
				],
				[
					229.2924420162593,
					-67.34682381625096
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
			"version": 487,
			"versionNonce": 1426969617,
			"isDeleted": false,
			"id": "__qQ9KOU1RMQaYOn62dhe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1270.7704006877093,
			"y": 2066.546966061124,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 222.08789807312544,
			"height": 83.94859898955924,
			"seed": 1863643135,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					77.05729608743147,
					22.240113911413015
				],
				[
					136.88633491954283,
					22.866595993424575
				],
				[
					184.81221419343296,
					-12.216400599227004
				],
				[
					222.08789807312544,
					-61.08200299613466
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
			"versionNonce": 712372607,
			"isDeleted": false,
			"id": "Ba9qMDf0-KepzT_oy9QgL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1272.4136164116017,
			"y": 2075.206626780297,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 221.14817495010794,
			"height": 87.7074914816293,
			"seed": 1191228927,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					71.10571630832085,
					20.04742662437256
				],
				[
					135.0068886735079,
					-24.11956015744805
				],
				[
					192.0167581365669,
					-67.66006485725674
				],
				[
					221.14817495010794,
					-64.84089548820437
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
			"version": 545,
			"versionNonce": 1429940721,
			"isDeleted": false,
			"id": "RUOBNg4ZdkW-t0FK3GNqj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1269.8306775646918,
			"y": 2063.1013146100595,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 222.08789807312544,
			"height": 77.9970192104489,
			"seed": 1723203505,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					67.66006485725683,
					18.167980378337703
				],
				[
					135.0068886735079,
					-23.493078075436312
				],
				[
					187.63138356248535,
					-43.54050469980869
				],
				[
					222.08789807312544,
					-59.82903883211119
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
			"version": 436,
			"versionNonce": 249129375,
			"isDeleted": false,
			"id": "eZhYRn8yDUi2Bm2s-oYLk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1280.4808729588897,
			"y": 2034.9096209195359,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 210.18473851490432,
			"height": 47.92587927389032,
			"seed": 129119025,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					57.94959258607642,
					-29.444657854547014
				],
				[
					124.66993432031583,
					-47.92587927389032
				],
				[
					176.9811881682875,
					-47.29939719187876
				],
				[
					210.18473851490432,
					-31.32410410058187
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
			"version": 481,
			"versionNonce": 1963115473,
			"isDeleted": false,
			"id": "LhhSoJTIj7YfC4ywfOc2_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 30,
			"angle": 0,
			"x": 1279.8543908768781,
			"y": 2034.5963798785306,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 209.87149747389844,
			"height": 53.87745905300084,
			"seed": 1771281937,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					56.38338738104735,
					-23.80631911644227
				],
				[
					123.41697015629254,
					-53.87745905300084
				],
				[
					177.29442920929338,
					-51.99801280696599
				],
				[
					209.87149747389844,
					-33.2035503466169
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
			"version": 464,
			"versionNonce": 1683545535,
			"isDeleted": false,
			"id": "CXrRAl_Qbrtymb60M2LDd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1284.5530064919656,
			"y": 2026.138871771373,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 204.85964081780534,
			"height": 61.39524403714044,
			"seed": 1793643793,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					51.998012806965896,
					-24.43280119845383
				],
				[
					117.15214933617614,
					-61.39524403714044
				],
				[
					172.2825725532002,
					-55.7569052990357
				],
				[
					204.85964081780534,
					-23.179837034430534
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
			"version": 493,
			"versionNonce": 1350312369,
			"isDeleted": false,
			"id": "Dclz-rjn5JVX221jMx9SS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1284.2397654509596,
			"y": 2023.9461844843327,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 205.79936394082287,
			"height": 61.08200299613466,
			"seed": 1104826847,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					49.17884343791353,
					-27.251970567506202
				],
				[
					112.14029268008314,
					-61.08200299613466
				],
				[
					172.28257255320028,
					-57.32311050406477
				],
				[
					205.79936394082287,
					-23.49307807543649
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
			"version": 652,
			"versionNonce": 504679903,
			"isDeleted": false,
			"id": "542-vGPHk9nur0QDUNqAE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1357.8437999955258,
			"y": 2008.8266763117786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.96657769702107,
			"height": 52.434621577954466,
			"seed": 1217833713,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-17.90103962415473,
					18.051263166180913
				],
				[
					-18.96657769702107,
					-16.332095245592406
				],
				[
					-0.6393228437198459,
					-34.38335841177355
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 662,
			"versionNonce": 349094801,
			"isDeleted": false,
			"id": "j0E_rQQpYbH3b4Cnr5J45",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1360.2284889126615,
			"y": 2049.3663879030864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.96657769702107,
			"height": 52.434621577954466,
			"seed": 1371294033,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-17.90103962415473,
					18.051263166180913
				],
				[
					-18.96657769702107,
					-16.332095245592406
				],
				[
					-0.6393228437198459,
					-34.38335841177355
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 685,
			"versionNonce": 1998436863,
			"isDeleted": false,
			"id": "N-FKdcAR9V4jaQurffLJq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1362.953847675102,
			"y": 2089.5654296490884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.96657769702107,
			"height": 52.43462157795446,
			"seed": 2101703633,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-17.90103962415473,
					18.051263166180913
				],
				[
					-18.96657769702107,
					-16.332095245592406
				],
				[
					-0.6393228437198459,
					-34.38335841177355
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 761,
			"versionNonce": 1580345713,
			"isDeleted": false,
			"id": "gxoxnkSFNQuSlhTibzmhG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1400.5214652193936,
			"y": 1979.0651598799677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.260040525719656,
			"height": 32.76211254213696,
			"seed": 406648657,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-11.571274204050015,
					11.278760055489691
				],
				[
					-12.260040525719656,
					-10.20459243115743
				],
				[
					-0.4132597930017994,
					-21.48335248664727
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 784,
			"versionNonce": 1953767967,
			"isDeleted": false,
			"id": "IQM9x4Wk-5hqsRJkYUbuj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1401.4156701804081,
			"y": 2004.632195314267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.260040525719656,
			"height": 32.76211254213696,
			"seed": 1305140575,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-11.571274204050015,
					11.278760055489691
				],
				[
					-12.260040525719656,
					-10.20459243115743
				],
				[
					-0.4132597930017994,
					-21.48335248664727
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 776,
			"versionNonce": 1441649489,
			"isDeleted": false,
			"id": "GQTaICDcrAobnVTGMA4gB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1401.8627727028154,
			"y": 2030.0365486915007,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.260040525719656,
			"height": 32.76211254213696,
			"seed": 641760369,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-11.571274204050015,
					11.278760055489691
				],
				[
					-12.260040525719656,
					-10.20459243115743
				],
				[
					-0.4132597930017994,
					-21.48335248664727
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 795,
			"versionNonce": 654870079,
			"isDeleted": false,
			"id": "PPI7UtvA-gjdqu0TEHP_Y",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1403.2868182997204,
			"y": 2056.6569933106057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.260040525719656,
			"height": 32.76211254213696,
			"seed": 1106710993,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-11.571274204050015,
					11.278760055489691
				],
				[
					-12.260040525719656,
					-10.20459243115743
				],
				[
					-0.4132597930017994,
					-21.48335248664727
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 787,
			"versionNonce": 274284849,
			"isDeleted": false,
			"id": "u3qyqs681jwadUCSsmrt4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1404.823036549252,
			"y": 2081.6929460257243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.260040525719656,
			"height": 32.76211254213696,
			"seed": 625551505,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-11.571274204050015,
					11.278760055489691
				],
				[
					-12.260040525719656,
					-10.20459243115743
				],
				[
					-0.4132597930017994,
					-21.48335248664727
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 789,
			"versionNonce": 767256159,
			"isDeleted": false,
			"id": "jc7CfQuCAayIC_KhkpeP7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1406.4512745185455,
			"y": 2106.1165155651224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 12.260040525719656,
			"height": 32.76211254213696,
			"seed": 1890228031,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
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
					-11.571274204050015,
					11.278760055489691
				],
				[
					-12.260040525719656,
					-10.20459243115743
				],
				[
					-0.4132597930017994,
					-21.48335248664727
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 681,
			"versionNonce": 719057681,
			"isDeleted": false,
			"id": "0EBl64M0ycIqk9JWe2BX5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1431.8517453005704,
			"y": 1971.2675230891055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 1020633585,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 685,
			"versionNonce": 2002600575,
			"isDeleted": false,
			"id": "4MvxiVKSGIila3qNIMPwd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1432.8697096558628,
			"y": 1985.4612675583303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 1553904689,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 702,
			"versionNonce": 703424753,
			"isDeleted": false,
			"id": "rcj7ODRsu8L-LIR0tPMV9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.283185296697541,
			"x": 1432.0115287945375,
			"y": 1999.6110531185982,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 2032866335,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 681,
			"versionNonce": 1152293535,
			"isDeleted": false,
			"id": "sMrbSYcyjynzIH5t25Pzs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1432.4385190426174,
			"y": 2014.5680944786973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 1311403473,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 681,
			"versionNonce": 387261137,
			"isDeleted": false,
			"id": "ZBjmeo02SxQcZaLZoa5lP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1431.95151680876,
			"y": 2029.9411887078472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 312066111,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 658,
			"versionNonce": 1784671935,
			"isDeleted": false,
			"id": "Hgdsi1eY5NpHQ4Sxq-iUA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1431.979422640895,
			"y": 2044.3790299700586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 913420063,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 690,
			"versionNonce": 1592434865,
			"isDeleted": false,
			"id": "b_RdSxKvpLGyr4oR-hM1n",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1431.9794224348695,
			"y": 2060.561140141919,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 1615364529,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 499,
			"versionNonce": 1393671903,
			"isDeleted": false,
			"id": "hcyiDbGvfFQfXUL77jY0i",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1486.5553259988233,
			"y": 2024.4172596103058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 771187007,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 522,
			"versionNonce": 1863672465,
			"isDeleted": false,
			"id": "1SZNoTVpze9Gb6ajvxBz4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1486.5553259988233,
			"y": 2006.6782820360427,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 1742300497,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 499,
			"versionNonce": 1096059647,
			"isDeleted": false,
			"id": "90u3C2ycnyIpRgGKMEtPO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1486.5553261454947,
			"y": 1988.9393041807048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.767824019932204,
			"height": 12.160084820596513,
			"seed": 675737777,
			"groupIds": [
				"AZAf4m7OJiox47iAULD-w"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 156,
			"versionNonce": 340584561,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 72,
			"versionNonce": 1370018591,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 408466001,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 1014961983,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 209,
			"versionNonce": 537935921,
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
			"updated": 1708107142303,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 714,
			"versionNonce": 1480054623,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 277
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1230705169,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 22
		},
		{
			"type": "image",
			"version": 162,
			"versionNonce": 1529058175,
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
			"updated": 1708107142303,
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
			"version": 305,
			"versionNonce": 154183665,
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
			"updated": 1708107142303,
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
			"version": 185,
			"versionNonce": 1568852895,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 22
		},
		{
			"type": "text",
			"version": 222,
			"versionNonce": 1234731473,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 22
		},
		{
			"type": "image",
			"version": 262,
			"versionNonce": 461766591,
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
			"updated": 1708107142303,
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
			"version": 167,
			"versionNonce": 1202331569,
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
			"updated": 1708107142303,
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
			"version": 21,
			"versionNonce": 2001579999,
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
			"updated": 1708107142303,
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
			"version": 37,
			"versionNonce": 831324561,
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
			"updated": 1708107142303,
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
			"version": 135,
			"versionNonce": 988437503,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 240,
			"versionNonce": 75016049,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 167,
			"versionNonce": 442270751,
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
			"updated": 1708107142303,
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
			"version": 218,
			"versionNonce": 716476753,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 235,
			"versionNonce": 1972676671,
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
			"updated": 1708107142303,
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
			"version": 77,
			"versionNonce": 1503149873,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 80,
			"versionNonce": 1517504607,
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
			"updated": 1708107142303,
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
			"version": 98,
			"versionNonce": 797651217,
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
			"updated": 1708107142303,
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
			"version": 199,
			"versionNonce": 1187570815,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 186,
			"versionNonce": 302311153,
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
			"updated": 1708107142303,
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
			"version": 161,
			"versionNonce": 710278303,
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
			"updated": 1708107142303,
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
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "arrow",
			"version": 66,
			"versionNonce": 1267523793,
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
			"updated": 1708107142303,
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
			"version": 190,
			"versionNonce": 1773838001,
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
			"updated": 1708107142304,
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
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 467,
			"versionNonce": 466133215,
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
			"updated": 1708107142304,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 292,
			"versionNonce": 1310981905,
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
			"updated": 1708107295934,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 468794929,
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
			"updated": 1708107142304,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 286,
			"versionNonce": 1164818783,
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
			"updated": 1708107142304,
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
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 298,
			"versionNonce": 1550602257,
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
			"updated": 1708107142304,
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
			"lineHeight": 1.25,
			"baseline": 343
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 820257137,
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
			"updated": 1708107145192,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 1573600113,
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
			"updated": 1708107292553,
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
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 145,
			"versionNonce": 215528063,
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
			"updated": 1708107292986,
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
			"version": 107,
			"versionNonce": 1121636913,
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
			"updated": 1708107292640,
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
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 125,
			"versionNonce": 197091007,
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
			"updated": 1708107292986,
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
			"version": 157,
			"versionNonce": 1996697311,
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
			"updated": 1708107292986,
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
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 534,
			"versionNonce": 1940591903,
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
			"updated": 1708107584210,
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
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 595,
			"versionNonce": 686364991,
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
			"updated": 1708107584210,
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
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 544,
			"versionNonce": 1813092703,
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
			"updated": 1708107584210,
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
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 561,
			"versionNonce": 309663103,
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
			"boundElements": [],
			"updated": 1708107584210,
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
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 608,
			"versionNonce": 1934888351,
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
			"updated": 1708107584210,
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
			"lineHeight": 1.25,
			"baseline": 168
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#fdf8f6",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#f8f0fc",
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
		"scrollX": -1342.159876748879,
		"scrollY": -105.1649555163927,
		"zoom": {
			"value": 0.8178922769539732
		},
		"currentItemRoundness": "round",
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
		}
	},
	"files": {}
}
```
%%