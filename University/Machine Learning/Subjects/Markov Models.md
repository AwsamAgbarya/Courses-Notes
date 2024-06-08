---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
M ^AymeaBtp

a ^IswjrA8z

r ^KJiUJDdr

k ^E8l5PzPt

o ^xKAccrIc

v ^4fm8znTl

M ^WE6NMQsL

o ^Ne1NQ7EM

d ^PHc2oCA0

e ^ZTsnUVso

l ^xO8M4zbL

s ^PKGH12YQ

Typically in ML Our goal is to learn an estimate of the true distribution of our data
in certain scenarios this is simply unfeasible because the parameter domain is incredibly large.

often times we tackle these issues by enforcing constraints and structure upon our models such that
it reduces the amount of possibilities that we have to consider.
(e.g in image data we assume that nearby pixels are dependent while pixels far away are not)

This dependence relation is quite hard to keep track of for very large systems, but can be simplified
and modeled in other ways.
One way to describe dependence is through directed graphs such that each node is a distribution ^DMVGzXdA

= ^mFwxxVmh

Markov Chains ^u4WBpKEI

Motivation ^vyGYxD5T

a markvo chain is a directed graph of dependence that imposes 2 important properties ^APLDB1kG

This model allows us to sample and perform a forward pass quite easily
The parameters would act as the transition counts obtained from the data ^yRzIfHsd

1. The markov property:
The history of the path leading up to a certain state has no influence
on said state, i.e ONLY the last node/state that we were at influenced
the fact that we are at the current state.

2. Stationarity:
The stationarity property says that the markov model probability distributions
remain unchanged with time. ^NSL0GElL

Discrete Markov Model ^TAe54sGP

a discrete markov model is a system that is fully described
with a finite distinct amount of states S1...Sn

we denote the current state at time t as qt
and thus we denote the set of transitions from state j to state i as ^ewV6GeyZ

Hidden Markov Models ^xmh2r78O

Hidden Markov models are an extension of markov models over unobserved states
Thus the states in the markov chain are completely hidden form us, and we know have
a few observable variables that are dependent on those states.

Our job is to infer the probability of the sequence of states taken
only from our observed data sequence! ^ZDnmQNPg

observation probability
at state j ^bS4TVGIk

We denote pi as the initial state distribution ^a91iiSKl

To indicate the complete parameter set of a HMM we denote ^XQS0hOn8

initial state distribution ^I6lzKzjb

observation state
distribution ^YqDmmVO9

state transition distribution ^RUikAeD7

Given an observation sequence O1...On
and a model distribution how do we efficiently compute
the probability of our observation sequence given our model? ^mHon4U4Y

Given an observation sequence O1...On
and a model distribution how do we efficiently compute
the most likely sequence of states (one that best explains
our observable results)? ^YlxINjkM

How do we adjust our model parameters in such
a way that maximizes the our observable? ^9WmcU2g2

The simplest approach is to enumerate over every single possible sequence
and add the probability of them casing our observation.
To calculate the probability of our observation sequence to occur as a consequence
of our state sequence we can compute: ^5Ky51kem

Subsequently to sum up over all possible sequences we compute: ^3Ww0Esnf

This will clearly get out of hand very quickly and will scale exponentially with
the amount of states and sequences ^sUnzK78y

The forward-Backward Procedure ^VvZgsFNR

Given the following variable ^zZmNM0uw

that indicates the occurrence of our observation such that
we end on state Si given our model.

By definition we can compute this term recursively

1. Base case





2. Recursive definition








3. Final computation ^CB5RXnsl

distribution being at
state i and generating
first observable ^u8dtxaAZ

distribution
of starting at state i ^J6Wcnim6

probability of
being at the previous
state i according
to our observations ^vAOxocBR

probability of
transitioning to j ^WBUyioVV

distribution of being at
state j and generating
t+1 observable ^VfJR4rHA

iterating over all state's probability
potential of generating our sequence ^ZAhBXSb0

Problem 1 ^45grEjAT

Problem 2 ^iIwUsMXX

Problem 3 ^3c6iOLQv

Just like Problem 1 we can formulate this problem in an inductive/recursive manner
and take the maximum potential of each sequence while walking along the observations ^kVB25M8M

1. Base case





2. Recursive definition








3. Final computation ^nLRt34k8

distribution being at
state i and generating
first observable ^laLvBUCF

distribution
of starting at state i ^sYRRqJtq

Optimal previous sequence
that got us to state i ^RUnAlIlZ

probability of
transitioning to j ^I1nB94Ki

distribution of being at
state j and generating
t observable ^qPUFoOKV

Optimal sequence
that gets us our observation ^vvvOJBJc

Not that this gets us the maximum potential but not the maximum sequence of states
thus we also need to have a pointer around to keep track of things ^Nm3sQHzm

Which can be recursively updated at each iteration to save the
index of the current best state in the sequence ^0Kana1TL

In order to learn our optimal model parameters we must perform
Expectation maximization style of updating parameters

1. Given our observation and our current model parameters
compute the probability of being in state i and the probability
of transitioning from state i to state j




2. update our parameters such that they properly reflect
the probabilities we calculated inferred from our observations ^Ib9weSka

probabaility of being at state i
at time t ^Z2y6ofte

probability of being at state
i at time t and state j at time
t+1 ^Dr2ELl7t

probability of being at
state i at time 1 ^kh036E8R

probability of being
at state i at time t
and transitioning to state j
in next t ^9H24XUZy

divided by the probability of
being at state i at time t ^MF2G4fWQ

divided by the probability of
being at state i at time t ^jn0P42lp

probability of being at state i
at time t given by the
observation k ^EPP9BqdU

How do we actually compute Gamma? ^qUHpM5x5

forward variable ^QKstW3s0

backward variable ^IWBOsobY

The probability of our observation occuring such
that we end on state i at time t times the probability
of our future observation (the rest of the observation)
occuring given we are now at state t
divided by the probability of our
observation sequence as a whole occurring in our model ^aPFYoo39

Generalizing HMMs ^IZZEPRR8

HMMs are directed graphical models that match prior knowledge
about the modeled task (latent states generate observations,
current latent state generates next latent state).

we cant always know the causality and for a more general formulation
of the problem we have to infer the causality and not make it biased ^zxAEFHB7

Types of independence ^yR1xtQH4

Conditional dependence ^vgEQqAfh

States a and b are not independent because
they are conditionally dependent as they
do not depend on each other but depend on the
same condition ^WHLrHBWd

Reverse Causality ^DciGuRvy

States a and b are not longer conditionally
dependent when we reverse the order.
this effect is called "explaining away" ^UIBS3YXC

Remove Causality ^OAJ4ZxNN

Probabilities are replaced by more general
potential functions.
We introduce a normalization term Z (which is often
intractable) ^xs3wVRtx

# Embedded files
38b6ed46bbc4d19b1fdf983f36418251e3b10eb8: $$\gamma_t (i)$$
e85c50a32dde90ff671a8378739d7f78215a0674: [[Pasted Image 20240608204755_633.png]]
435e1fdf7ad1a755f130ecff2601a6b402cd53eb: [[Pasted Image 20240608204815_647.png]]
899c81093db47f6e8e3f6dc45bd998a79ad84ad3: [[Pasted Image 20240608205206_682.png]]
c1c346a690e44cd00a05b48e3ef77d8b692ededf: [[Pasted Image 20240608205221_691.png]]
115dd5c6c9960a6bcdaeae70d87a45a02bbf775d: [[Pasted Image 20240608210459_785.png]]
37fc4b3f1494f8c1528743f04c6394b68d13d9a3: [[Pasted Image 20240608211831_844.png]]
22044f9bea61c085e1c4264de11dde79e05e1dbe: [[Pasted Image 20240608213619_898.png]]
03c02edc2cc06dfb9f3f40a127d44cc81ba69fc9: [[Pasted Image 20240608213812_922.png]]
c2d04d56e0797060f13aaea8cb02a2b06dbd2a51: [[Pasted Image 20240608214016_940.png]]
9c3f692890ea060545d8794373b3f1855b45dab2: [[Pasted Image 20240608214833_011.png]]
98ecfba6d59b27ae2823aa6da76386ea7c0b31dd: [[Pasted Image 20240608215235_036.png]]
b70e30ea0d7e8e8022125b2628146eb4331869d4: [[Pasted Image 20240608215822_062.png]]
c7faf564e421a4ec70d7d20905a77a524fba3b9c: [[Pasted Image 20240608220010_091.png]]
95c589ded0729bfd643f3eb337c2e32901e71e7a: [[Pasted Image 20240608220147_137.png]]
1150556832a47ca9f105bdebb7b69b0726e71cfe: [[Pasted Image 20240608220346_196.png]]
9d0161f63d17c1ab33f295c6d470c17dc0296b34: [[Pasted Image 20240608220533_215.png]]
cdedc08ef3f5ff2c70270c0ab6da0d6147211200: [[Pasted Image 20240608220852_235.png]]
dc1c8c6b5df730de5d52f4c7a2c8be00b4efbc02: [[Pasted Image 20240608220918_251.png]]
ed04a77d2af532b28626065fdeb8934c0c9ec315: [[Pasted Image 20240608221014_283.png]]
4f0a9f13903e7dd246d509bee9b79708c9e89a4c: [[Pasted Image 20240608221707_510.png]]
de372540639a535194ffa8b57425c68ede342491: [[Pasted Image 20240608221737_525.png]]
7ddbe71c4c434f150a7253a397a5e6345934e014: [[Pasted Image 20240608223004_633.png]]
ed3daef6432c0da37c7a4c40da0dfbf4d5499097: [[Pasted Image 20240608223019_642.png]]
13172cd39e22b3746ff7a421b11eda9b94c69041: [[Pasted Image 20240608223034_643.png]]
02587022afd5f49a87b7a686d7bb81be590e7b4f: [[Pasted Image 20240608223119_646.png]]
efab28de9560a7a8ac773444a64e164e6db98098: [[Pasted Image 20240608223831_731.png]]
0dbb91c52c64202fb1829676291430b1a40f0d62: [[Pasted Image 20240608224204_764.png]]
ab20293488e3e270d65ac56990e3b6b1c632ccab: [[Pasted Image 20240608224434_834.png]]
e6ed19bba51d6e8fd893a7a4a6747ea8869d7476: [[Pasted Image 20240608224434_847.png]]
f4530f7f4cd9348fc9842d9e17fee59b212726f7: [[Pasted Image 20240608224952_888.png]]
6a96b265f1205601488c34cb5687c454d5bf18e6: [[Pasted Image 20240608225008_896.png]]
06f0f2ab366bf9756a62776f5b4e355a22ae23e6: [[Pasted Image 20240608225211_905.png]]
e849a0a0f1a9060d727f427e9ab1bd257e27c872: [[Pasted Image 20240608225322_942.png]]
cbdb9dc24523718051356e13dae707934c726dab: [[Pasted Image 20240608225422_955.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"id": "dCpvJ4ROWSXI9chmYjShn",
			"type": "ellipse",
			"x": -267.04943803396026,
			"y": -192.64773672959464,
			"width": 58.461491699358305,
			"height": 64,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 425579694,
			"version": 423,
			"versionNonce": 760345710,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "AymeaBtp"
				},
				{
					"id": "vOS3yxMLSS_u0GT-dAma4",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"id": "AymeaBtp",
			"type": "text",
			"x": -248.71199559353445,
			"y": -178.27515372756417,
			"width": 21.448089599609375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1165415854,
			"version": 305,
			"versionNonce": 4739442,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"text": "M",
			"rawText": "M",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "dCpvJ4ROWSXI9chmYjShn",
			"originalText": "M",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 370,
			"versionNonce": 1144338094,
			"isDeleted": false,
			"id": "a-jlgyG6hSnNlb9WyQJKJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -208.54621814988977,
			"y": -263.7926557826297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 748890222,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "IswjrA8z"
				},
				{
					"id": "vOS3yxMLSS_u0GT-dAma4",
					"type": "arrow"
				},
				{
					"id": "ULNkDq1nmirzK5FQ10-RY",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 253,
			"versionNonce": 769741618,
			"isDeleted": false,
			"id": "IswjrA8z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -188.82276649315537,
			"y": -249.42007278059924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 18.676071166992188,
			"height": 35,
			"seed": 725609134,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "a-jlgyG6hSnNlb9WyQJKJ",
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 403,
			"versionNonce": 435564782,
			"isDeleted": false,
			"id": "KTnKsbcsK2LEOZpbUhH3i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.63674431024114,
			"y": -332.287907468191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 1056467442,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "KJiUJDdr"
				},
				{
					"id": "ULNkDq1nmirzK5FQ10-RY",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 289,
			"versionNonce": 1282678002,
			"isDeleted": false,
			"id": "KJiUJDdr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -115.59528423065518,
			"y": -317.91532446616054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.040054321289062,
			"height": 35,
			"seed": 1073372082,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "KTnKsbcsK2LEOZpbUhH3i",
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 429,
			"versionNonce": 2048779054,
			"isDeleted": false,
			"id": "Zo3EWfRGlVIQyKN2LDswX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -74.91289930481483,
			"y": -263.7926562193081,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 955690542,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "E8l5PzPt"
				},
				{
					"id": "t0nE6X9cMfo-c4r7Sc_OQ",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 317,
			"versionNonce": 696757938,
			"isDeleted": false,
			"id": "E8l5PzPt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -52.669443375619494,
			"y": -249.42007321727766,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.636062622070312,
			"height": 35,
			"seed": 1989982318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "k",
			"rawText": "k",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Zo3EWfRGlVIQyKN2LDswX",
			"originalText": "k",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 507,
			"versionNonce": 1461013870,
			"isDeleted": false,
			"id": "12pvfj0cuWhD3bS2Ehi45",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -9.687717048712429,
			"y": -192.64773694977066,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 1261103726,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xKAccrIc"
				},
				{
					"id": "WfETEqjdLUjHnGSQuI6t4",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 396,
			"versionNonce": 1237518450,
			"isDeleted": false,
			"id": "xKAccrIc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 11.617735340443845,
			"y": -178.2751539477402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.512069702148438,
			"height": 35,
			"seed": 1736404142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "o",
			"rawText": "o",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "12pvfj0cuWhD3bS2Ehi45",
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 502,
			"versionNonce": 1847947182,
			"isDeleted": false,
			"id": "g2KzM5LxTmqLOU52wCZ25",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -79.52568004080413,
			"y": -126.42897384039438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 734255410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "4fm8znTl"
				},
				{
					"id": "WfETEqjdLUjHnGSQuI6t4",
					"type": "arrow"
				},
				{
					"id": "peUiyntHLbDHr1FtIR19p",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 386,
			"versionNonce": 82651698,
			"isDeleted": false,
			"id": "4fm8znTl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -57.78622191434317,
			"y": -112.0563908383639,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.644058227539062,
			"height": 35,
			"seed": 940958450,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "v",
			"rawText": "v",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "g2KzM5LxTmqLOU52wCZ25",
			"originalText": "v",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 447,
			"versionNonce": 1802979822,
			"isDeleted": false,
			"id": "_SlP2F-r_cgUTW1UGFQhc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -147.23017754856818,
			"y": -59.14573147050956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 1894858478,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "WE6NMQsL"
				},
				{
					"id": "peUiyntHLbDHr1FtIR19p",
					"type": "arrow"
				},
				{
					"id": "gqWHROlySuFA0NkuZ2UG3",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 331,
			"versionNonce": 569185266,
			"isDeleted": false,
			"id": "WE6NMQsL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.89273510814238,
			"y": -44.77314846847908,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.448089599609375,
			"height": 35,
			"seed": 445067566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "M",
			"rawText": "M",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "_SlP2F-r_cgUTW1UGFQhc",
			"originalText": "M",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 544,
			"versionNonce": 236182574,
			"isDeleted": false,
			"id": "LNjsTIcueHckLx_gWHl7R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -78.83438037677635,
			"y": 5.481869727161552,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 1956735726,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Ne1NQ7EM"
				},
				{
					"id": "gqWHROlySuFA0NkuZ2UG3",
					"type": "arrow"
				},
				{
					"id": "ktyophd-HB5oMDWRu0TnL",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"id": "Ne1NQ7EM",
			"type": "text",
			"x": -57.52892798762008,
			"y": 19.85445272919203,
			"width": 15.512069702148438,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1921718514,
			"version": 161,
			"versionNonce": 1925825970,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"text": "o",
			"rawText": "o",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LNjsTIcueHckLx_gWHl7R",
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 574,
			"versionNonce": 1273243246,
			"isDeleted": false,
			"id": "_djaJVWidUc8Hf3x8TH9N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -11.529167403564585,
			"y": -54.23519895430441,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 701146546,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PHc2oCA0"
				},
				{
					"id": "ktyophd-HB5oMDWRu0TnL",
					"type": "arrow"
				},
				{
					"id": "ta6_4_dkGZRtN2J07IDMu",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 1890205554,
			"isDeleted": false,
			"id": "PHc2oCA0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.566285901119032,
			"y": -39.86261595227393,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.93206787109375,
			"height": 35,
			"seed": 1418665842,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "_djaJVWidUc8Hf3x8TH9N",
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 588,
			"versionNonce": 1974544558,
			"isDeleted": false,
			"id": "IIxMni0hZoxWltXO1Puzp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 52.472479030060555,
			"y": 6.69571760905518,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 1633445742,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ZTsnUVso"
				},
				{
					"id": "ta6_4_dkGZRtN2J07IDMu",
					"type": "arrow"
				},
				{
					"id": "s3qeIrZn-IYpyhUJ-M3JU",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 205,
			"versionNonce": 1473610034,
			"isDeleted": false,
			"id": "ZTsnUVso",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 73.87593099197073,
			"y": 21.068300611085657,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.316070556640625,
			"height": 35,
			"seed": 343493038,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "IIxMni0hZoxWltXO1Puzp",
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 593,
			"versionNonce": 1529078510,
			"isDeleted": false,
			"id": "5Xpk75kITGQTkdeWjcr0E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 112.75961574877542,
			"y": -57.30428209420279,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 2003711346,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xO8M4zbL"
				},
				{
					"id": "s3qeIrZn-IYpyhUJ-M3JU",
					"type": "arrow"
				},
				{
					"id": "UXH1JDhih1eyxU-Dyc_bi",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 212,
			"versionNonce": 1135774450,
			"isDeleted": false,
			"id": "xO8M4zbL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 138.13908852367388,
			"y": -42.93169909217231,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.3640289306640625,
			"height": 35,
			"seed": 246069042,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "5Xpk75kITGQTkdeWjcr0E",
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 593,
			"versionNonce": 1858426158,
			"isDeleted": false,
			"id": "dcXESeBnvckZitcHyEU0F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 181.65598993277473,
			"y": 5.481869377125918,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.461491699358305,
			"height": 64,
			"seed": 463075826,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PKGH12YQ"
				},
				{
					"id": "UXH1JDhih1eyxU-Dyc_bi",
					"type": "arrow"
				}
			],
			"updated": 1717873238153,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 212,
			"versionNonce": 1254644914,
			"isDeleted": false,
			"id": "PKGH12YQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 203.11544927993882,
			"y": 19.854452379156395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.204055786132812,
			"height": 35,
			"seed": 837413810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "dcXESeBnvckZitcHyEU0F",
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"id": "vOS3yxMLSS_u0GT-dAma4",
			"type": "arrow",
			"x": -219.71318318034878,
			"y": -189.43596727245372,
			"width": 17.56337774530175,
			"height": 19.31524362171521,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 238247154,
			"version": 260,
			"versionNonce": 1068850542,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063024,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					17.56337774530175,
					-19.31524362171521
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "dCpvJ4ROWSXI9chmYjShn",
				"gap": 2.8651574053328233,
				"focus": -0.19570287848107942
			},
			"endBinding": {
				"elementId": "a-jlgyG6hSnNlb9WyQJKJ",
				"gap": 1.8999296035842121,
				"focus": 0.04564766398747563
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ULNkDq1nmirzK5FQ10-RY",
			"type": "arrow",
			"x": -157.0963170603011,
			"y": -258.44570137993037,
			"width": 22.715322084095078,
			"height": 20.873539212411742,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1786839150,
			"version": 174,
			"versionNonce": 469513838,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063024,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					22.715322084095078,
					-20.873539212411742
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "a-jlgyG6hSnNlb9WyQJKJ",
				"gap": 3.916719117078088,
				"focus": -0.1492477753212078
			},
			"endBinding": {
				"elementId": "KTnKsbcsK2LEOZpbUhH3i",
				"gap": 2.318249584015234,
				"focus": 0.04742390558038806
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "t0nE6X9cMfo-c4r7Sc_OQ",
			"type": "arrow",
			"x": -85.89098098469196,
			"y": -281.7731301720497,
			"width": 20.975944119273237,
			"height": 24.143207852728096,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 581457198,
			"version": 86,
			"versionNonce": 675756206,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063025,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					20.975944119273237,
					24.143207852728096
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zo3EWfRGlVIQyKN2LDswX",
				"gap": 1.281512635601917,
				"focus": 0.07969282113869451
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "1xWg7kKfDWZ8Q4GHFxWRP",
			"type": "arrow",
			"x": -24.509319784443846,
			"y": -209.9565865677594,
			"width": 26.39411431610671,
			"height": 23.938847868096786,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1132388334,
			"version": 33,
			"versionNonce": 341465138,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					26.39411431610671,
					23.938847868096786
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "WfETEqjdLUjHnGSQuI6t4",
			"type": "arrow",
			"x": -3.5780086803062865,
			"y": -136.84530248184814,
			"width": 23.174688857409077,
			"height": 21.71435246116836,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 953001966,
			"version": 222,
			"versionNonce": 1613132206,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063025,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-23.174688857409077,
					21.71435246116836
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "12pvfj0cuWhD3bS2Ehi45",
				"gap": 2.6143818220786272,
				"focus": -0.05076736818866424
			},
			"endBinding": {
				"elementId": "g2KzM5LxTmqLOU52wCZ25",
				"gap": 1,
				"focus": 0.032211387150470255
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "peUiyntHLbDHr1FtIR19p",
			"type": "arrow",
			"x": -75.25887273292642,
			"y": -71.90581312763476,
			"width": 20.566762782919255,
			"height": 20.224067840555726,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1921441262,
			"version": 208,
			"versionNonce": 102836910,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063025,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-20.566762782919255,
					20.224067840555726
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "g2KzM5LxTmqLOU52wCZ25",
				"gap": 3.232767596268225,
				"focus": 0.04707344656903124
			},
			"endBinding": {
				"elementId": "_SlP2F-r_cgUTW1UGFQhc",
				"gap": 2.4027034439091217,
				"focus": -0.06350707476081778
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "gqWHROlySuFA0NkuZ2UG3",
			"type": "arrow",
			"x": -94.72367907615795,
			"y": -2.9078379053707977,
			"width": 20.75391923274455,
			"height": 17.435702255934014,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1147402546,
			"version": 201,
			"versionNonce": 1886872494,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063025,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					20.75391923274455,
					17.435702255934014
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "_SlP2F-r_cgUTW1UGFQhc",
				"gap": 3.01819866753803,
				"focus": 0.11611131481351543
			},
			"endBinding": {
				"elementId": "LNjsTIcueHckLx_gWHl7R",
				"gap": 3.027220459984754,
				"focus": 0.06157233063688338
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ktyophd-HB5oMDWRu0TnL",
			"type": "arrow",
			"x": -26.426537299852036,
			"y": 12.168152510870723,
			"width": 17.937395125305645,
			"height": 13.9530337623039,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 289244082,
			"version": 202,
			"versionNonce": 1432951982,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063025,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					17.937395125305645,
					-13.9530337623039
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "LNjsTIcueHckLx_gWHl7R",
				"gap": 3.667946104498718,
				"focus": -0.1855745014650379
			},
			"endBinding": {
				"elementId": "_djaJVWidUc8Hf3x8TH9N",
				"gap": 3.0284743793910067,
				"focus": -0.0019675213340139075
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ta6_4_dkGZRtN2J07IDMu",
			"type": "arrow",
			"x": 41.09791910469534,
			"y": -0.8395581193644546,
			"width": 19.44644479272656,
			"height": 15.96571491258267,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 996248690,
			"version": 249,
			"versionNonce": 1261852078,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063026,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					19.44644479272656,
					15.96571491258267
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "_djaJVWidUc8Hf3x8TH9N",
				"gap": 1.3010852529254606,
				"focus": 0.05467665338997979
			},
			"endBinding": {
				"elementId": "IIxMni0hZoxWltXO1Puzp",
				"gap": 1,
				"focus": 0.15495137924108118
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "s3qeIrZn-IYpyhUJ-M3JU",
			"type": "arrow",
			"x": 102.78628244767046,
			"y": 13.059953821673624,
			"width": 16.148921121106525,
			"height": 16.39554155593675,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1543774898,
			"version": 225,
			"versionNonce": 1209994926,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063026,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					16.148921121106525,
					-16.39554155593675
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "IIxMni0hZoxWltXO1Puzp",
				"gap": 2.393918461589969,
				"focus": -0.09693901538254775
			},
			"endBinding": {
				"elementId": "5Xpk75kITGQTkdeWjcr0E",
				"gap": 1.3865979402603905,
				"focus": 0.03296165420617027
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "UXH1JDhih1eyxU-Dyc_bi",
			"type": "arrow",
			"x": 167.9593836379559,
			"y": -4.837838015516255,
			"width": 20.120883122058842,
			"height": 18.143362094239965,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 692146482,
			"version": 216,
			"versionNonce": 576931758,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880063026,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					20.120883122058842,
					18.143362094239965
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "5Xpk75kITGQTkdeWjcr0E",
				"gap": 2.8526701225501796,
				"focus": -0.07116391493190599
			},
			"endBinding": {
				"elementId": "dcXESeBnvckZitcHyEU0F",
				"gap": 2.626417457550893,
				"focus": 0.08710914523393185
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "DMVGzXdA",
			"type": "text",
			"x": -467.25790215691603,
			"y": 125.71896344122716,
			"width": 1014.1189575195312,
			"height": 250,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1694092914,
			"version": 856,
			"versionNonce": 1211871026,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"text": "Typically in ML Our goal is to learn an estimate of the true distribution of our data\nin certain scenarios this is simply unfeasible because the parameter domain is incredibly large.\n\noften times we tackle these issues by enforcing constraints and structure upon our models such that\nit reduces the amount of possibilities that we have to consider.\n(e.g in image data we assume that nearby pixels are dependent while pixels far away are not)\n\nThis dependence relation is quite hard to keep track of for very large systems, but can be simplified\nand modeled in other ways.\nOne way to describe dependence is through directed graphs such that each node is a distribution",
			"rawText": "Typically in ML Our goal is to learn an estimate of the true distribution of our data\nin certain scenarios this is simply unfeasible because the parameter domain is incredibly large.\n\noften times we tackle these issues by enforcing constraints and structure upon our models such that\nit reduces the amount of possibilities that we have to consider.\n(e.g in image data we assume that nearby pixels are dependent while pixels far away are not)\n\nThis dependence relation is quite hard to keep track of for very large systems, but can be simplified\nand modeled in other ways.\nOne way to describe dependence is through directed graphs such that each node is a distribution",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Typically in ML Our goal is to learn an estimate of the true distribution of our data\nin certain scenarios this is simply unfeasible because the parameter domain is incredibly large.\n\noften times we tackle these issues by enforcing constraints and structure upon our models such that\nit reduces the amount of possibilities that we have to consider.\n(e.g in image data we assume that nearby pixels are dependent while pixels far away are not)\n\nThis dependence relation is quite hard to keep track of for very large systems, but can be simplified\nand modeled in other ways.\nOne way to describe dependence is through directed graphs such that each node is a distribution",
			"lineHeight": 1.25
		},
		{
			"id": "zzo1MyzpMJdJ4golk_j9P",
			"type": "image",
			"x": -227.510117557453,
			"y": 384.98097664973045,
			"width": 119.77254139067047,
			"height": 142.36309190207805,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 237604846,
			"version": 244,
			"versionNonce": 771724526,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e85c50a32dde90ff671a8378739d7f78215a0674",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "mFwxxVmh",
			"type": "text",
			"x": -78.5499274135176,
			"y": 431.28660184339634,
			"width": 22.212005615234375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2066936690,
			"version": 95,
			"versionNonce": 1663236338,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
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
			"id": "eKGwHx48JGN6683YzyrWs",
			"type": "image",
			"x": -34.31503966222857,
			"y": 432.28163863245993,
			"width": 411.58927783013377,
			"height": 42.17322042617453,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1347835314,
			"version": 186,
			"versionNonce": 257607470,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "435e1fdf7ad1a755f130ecff2601a6b402cd53eb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Wwjstdmz62oDT7tr9Z82X",
			"type": "line",
			"x": -381.02333968395027,
			"y": 533.3166746786848,
			"width": 855.379684263218,
			"height": 7.332706648688372,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1898338866,
			"version": 210,
			"versionNonce": 1039862450,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238153,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					855.379684263218,
					-7.332706648688372
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "u4WBpKEI",
			"type": "text",
			"x": -104.79977652462992,
			"y": 545.7323950294128,
			"width": 250.59608459472656,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1361485682,
			"version": 27,
			"versionNonce": 2065019246,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238154,
			"link": null,
			"locked": false,
			"text": "Markov Chains",
			"rawText": "Markov Chains",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Markov Chains",
			"lineHeight": 1.25
		},
		{
			"id": "vyGYxD5T",
			"type": "text",
			"x": -71.28376261353051,
			"y": 80.71896254322529,
			"width": 183.56405639648438,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 116277810,
			"version": 167,
			"versionNonce": 795534450,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238154,
			"link": null,
			"locked": false,
			"text": "Motivation",
			"rawText": "Motivation",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Motivation",
			"lineHeight": 1.25
		},
		{
			"id": "APLDB1kG",
			"type": "text",
			"x": -409.66124985061197,
			"y": 603.6269017670747,
			"width": 860.3190307617188,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 800528174,
			"version": 131,
			"versionNonce": 2088326062,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238154,
			"link": null,
			"locked": false,
			"text": "a markvo chain is a directed graph of dependence that imposes 2 important properties",
			"rawText": "a markvo chain is a directed graph of dependence that imposes 2 important properties",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a markvo chain is a directed graph of dependence that imposes 2 important properties",
			"lineHeight": 1.25
		},
		{
			"id": "3tyHsg4voqIsbRdjUZbh9",
			"type": "image",
			"x": -243.33642376471636,
			"y": 635.3872755847086,
			"width": 527.6693800321718,
			"height": 31.3137132089799,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1314087538,
			"version": 143,
			"versionNonce": 557418034,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238154,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "899c81093db47f6e8e3f6dc45bd998a79ad84ad3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "0QwrzSQ810uVqSpBi0QPu",
			"type": "image",
			"x": -229.39866759483525,
			"y": 666.7009892171869,
			"width": 499.7938669788199,
			"height": 58.54100930937861,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 708694002,
			"version": 176,
			"versionNonce": 1303293422,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873238154,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c1c346a690e44cd00a05b48e3ef77d8b692ededf",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "yRzIfHsd",
			"type": "text",
			"x": -362.38205365763986,
			"y": 930.4439379672847,
			"width": 762.9590454101562,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2028920686,
			"version": 246,
			"versionNonce": 1142540658,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873296353,
			"link": null,
			"locked": false,
			"text": "This model allows us to sample and perform a forward pass quite easily\nThe parameters would act as the transition counts obtained from the data",
			"rawText": "This model allows us to sample and perform a forward pass quite easily\nThe parameters would act as the transition counts obtained from the data",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This model allows us to sample and perform a forward pass quite easily\nThe parameters would act as the transition counts obtained from the data",
			"lineHeight": 1.25
		},
		{
			"id": "NSL0GElL",
			"type": "text",
			"x": -370.4912967931025,
			"y": 725.241999351007,
			"width": 781.9791259765625,
			"height": 200,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 911304814,
			"version": 441,
			"versionNonce": 392379570,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717873271029,
			"link": null,
			"locked": false,
			"text": "1. The markov property:\nThe history of the path leading up to a certain state has no influence\non said state, i.e ONLY the last node/state that we were at influenced\nthe fact that we are at the current state.\n\n2. Stationarity:\nThe stationarity property says that the markov model probability distributions\nremain unchanged with time.",
			"rawText": "1. The markov property:\nThe history of the path leading up to a certain state has no influence\non said state, i.e ONLY the last node/state that we were at influenced\nthe fact that we are at the current state.\n\n2. Stationarity:\nThe stationarity property says that the markov model probability distributions\nremain unchanged with time.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. The markov property:\nThe history of the path leading up to a certain state has no influence\non said state, i.e ONLY the last node/state that we were at influenced\nthe fact that we are at the current state.\n\n2. Stationarity:\nThe stationarity property says that the markov model probability distributions\nremain unchanged with time.",
			"lineHeight": 1.25
		},
		{
			"id": "TAe54sGP",
			"type": "text",
			"x": 718.3848084094641,
			"y": 750.3637694246876,
			"width": 315.25335693359375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1421465842,
			"version": 259,
			"versionNonce": 442273586,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "mPCLIcUMC5jkhO2CWilgS",
					"type": "arrow"
				}
			],
			"updated": 1717874316791,
			"link": null,
			"locked": false,
			"text": "Discrete Markov Model",
			"rawText": "Discrete Markov Model",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Discrete Markov Model",
			"lineHeight": 1.25
		},
		{
			"id": "mPCLIcUMC5jkhO2CWilgS",
			"type": "arrow",
			"x": 403.3693841145646,
			"y": 681.9481999996782,
			"width": 477.2336278293783,
			"height": 56.061017894021234,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 840391406,
			"version": 481,
			"versionNonce": 2116540658,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717874316791,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					431.76432834994444,
					19.579379440266507
				],
				[
					477.2336278293783,
					56.061017894021234
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "TAe54sGP",
				"focus": 0.23295556363511186,
				"gap": 12.354551530988147
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ewV6GeyZ",
			"type": "text",
			"x": 516.8011057765326,
			"y": 792.3594981720292,
			"width": 711.4192504882812,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1912450094,
			"version": 476,
			"versionNonce": 1701046962,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717874316791,
			"link": null,
			"locked": false,
			"text": "a discrete markov model is a system that is fully described\nwith a finite distinct amount of states S1...Sn\n\nwe denote the current state at time t as qt\nand thus we denote the set of transitions from state j to state i as",
			"rawText": "a discrete markov model is a system that is fully described\nwith a finite distinct amount of states S1...Sn\n\nwe denote the current state at time t as qt\nand thus we denote the set of transitions from state j to state i as",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a discrete markov model is a system that is fully described\nwith a finite distinct amount of states S1...Sn\n\nwe denote the current state at time t as qt\nand thus we denote the set of transitions from state j to state i as",
			"lineHeight": 1.25
		},
		{
			"id": "IYAgPpplvIrAHlwmJzbak",
			"type": "image",
			"x": 698.1212884191616,
			"y": 917.3594982818261,
			"width": 395.23271579097036,
			"height": 29.115889721278382,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 468929326,
			"version": 239,
			"versionNonce": 1107313138,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717874323558,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "115dd5c6c9960a6bcdaeae70d87a45a02bbf775d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "S5q10lsG7uGyrMBXq_OUj",
			"type": "arrow",
			"x": 905.2769167058598,
			"y": 1057.6254114223855,
			"width": 914.3507930080566,
			"height": 99.91007196290684,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 964837746,
			"version": 325,
			"versionNonce": 2058836914,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717874328834,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-106.98231441134112,
					37.170880565860216
				],
				[
					-796.5830257719638,
					-2.080003980077663
				],
				[
					-914.3507930080566,
					97.83006798282918
				]
			],
			"lastCommittedPoint": [
				-889.6102298067043,
				153.28668575130916
			],
			"startBinding": {
				"elementId": "fwLS6IDK-QXprpwWTBwHQ",
				"focus": -0.6829160903392644,
				"gap": 1
			},
			"endBinding": {
				"elementId": "xmh2r78O",
				"focus": -0.20997038683040684,
				"gap": 9.160835718913404
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "xmh2r78O",
			"type": "text",
			"x": -191.43466041190493,
			"y": 1164.616315124128,
			"width": 381.276123046875,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1479423602,
			"version": 43,
			"versionNonce": 1460360690,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "S5q10lsG7uGyrMBXq_OUj",
					"type": "arrow"
				}
			],
			"updated": 1717873888173,
			"link": null,
			"locked": false,
			"text": "Hidden Markov Models",
			"rawText": "Hidden Markov Models",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hidden Markov Models",
			"lineHeight": 1.25
		},
		{
			"id": "ZDnmQNPg",
			"type": "text",
			"x": -434.7912244216706,
			"y": 1219.1618289997825,
			"width": 858.0591430664062,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2124401906,
			"version": 415,
			"versionNonce": 31307310,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875324791,
			"link": null,
			"locked": false,
			"text": "Hidden Markov models are an extension of markov models over unobserved states\nThus the states in the markov chain are completely hidden form us, and we know have\na few observable variables that are dependent on those states.\n\nOur job is to infer the probability of the sequence of states taken\nonly from our observed data sequence!",
			"rawText": "Hidden Markov models are an extension of markov models over unobserved states\nThus the states in the markov chain are completely hidden form us, and we know have\na few observable variables that are dependent on those states.\n\nOur job is to infer the probability of the sequence of states taken\nonly from our observed data sequence!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hidden Markov models are an extension of markov models over unobserved states\nThus the states in the markov chain are completely hidden form us, and we know have\na few observable variables that are dependent on those states.\n\nOur job is to infer the probability of the sequence of states taken\nonly from our observed data sequence!",
			"lineHeight": 1.25
		},
		{
			"id": "fwLS6IDK-QXprpwWTBwHQ",
			"type": "image",
			"x": 755.3446277538803,
			"y": 946.4753883501502,
			"width": 241.3337188919327,
			"height": 110.15002307223533,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 483274802,
			"version": 121,
			"versionNonce": 1546141746,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "S5q10lsG7uGyrMBXq_OUj",
					"type": "arrow"
				}
			],
			"updated": 1717874328819,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "37fc4b3f1494f8c1528743f04c6394b68d13d9a3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HsN5PzJ89BjN6z-GkLX4-",
			"type": "image",
			"x": -157.75056797120126,
			"y": 1378.707343275244,
			"width": 313.90793867965726,
			"height": 63.71398755379182,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1870284146,
			"version": 83,
			"versionNonce": 1410993518,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875378348,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "22044f9bea61c085e1c4264de11dde79e05e1dbe",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "O7QMedNgXkHZINF5x37PW",
			"type": "arrow",
			"x": -155.4154530133533,
			"y": 1401.328026440745,
			"width": 39.2951525271846,
			"height": 27.849962470723085,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 1972262066,
			"version": 50,
			"versionNonce": 236455282,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717875416545,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-33.19105116373845,
					7.24862036909235
				],
				[
					-39.2951525271846,
					27.849962470723085
				]
			],
			"lastCommittedPoint": [
				-39.2951525271846,
				27.849962470723085
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "bS4TVGIk",
				"focus": -0.08939370605689934,
				"gap": 4.407531676076815
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "bS4TVGIk",
			"type": "text",
			"x": -281.34228587571204,
			"y": 1433.5855205875448,
			"width": 175.55239868164062,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 376245358,
			"version": 75,
			"versionNonce": 1335527218,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "O7QMedNgXkHZINF5x37PW",
					"type": "arrow"
				}
			],
			"updated": 1717875416546,
			"link": null,
			"locked": false,
			"text": "observation probability\nat state j",
			"rawText": "observation probability\nat state j",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "observation probability\nat state j",
			"lineHeight": 1.25
		},
		{
			"id": "a91iiSKl",
			"type": "text",
			"x": -180.81301743467466,
			"y": 1491.4415056579526,
			"width": 360.0328369140625,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 119953774,
			"version": 89,
			"versionNonce": 543445934,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875477315,
			"link": null,
			"locked": false,
			"text": "We denote pi as the initial state distribution",
			"rawText": "We denote pi as the initial state distribution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We denote pi as the initial state distribution",
			"lineHeight": 1.25
		},
		{
			"id": "syYO_rJKJmXQmaPquPkDG",
			"type": "image",
			"x": -132.75403616228647,
			"y": 1516.9497257235384,
			"width": 253.98476714460992,
			"height": 29.612573747802053,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1625931822,
			"version": 79,
			"versionNonce": 386413614,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875483047,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "03c02edc2cc06dfb9f3f40a127d44cc81ba69fc9",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XQS0hOn8",
			"type": "text",
			"x": -246.013075604685,
			"y": 1552.0705194785598,
			"width": 490.4329528808594,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1131631538,
			"version": 86,
			"versionNonce": 251614254,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875592810,
			"link": null,
			"locked": false,
			"text": "To indicate the complete parameter set of a HMM we denote",
			"rawText": "To indicate the complete parameter set of a HMM we denote",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To indicate the complete parameter set of a HMM we denote",
			"lineHeight": 1.25
		},
		{
			"id": "boMQ3onmBzw6wgGR45NvD",
			"type": "image",
			"x": -54.975309559792606,
			"y": 1577.578738758654,
			"width": 108.35742077269872,
			"height": 17.61475313053723,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1545511086,
			"version": 100,
			"versionNonce": 1359939058,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "oSt36lgh7ASu9QVB3Necl",
					"type": "arrow"
				},
				{
					"id": "Oh2IfkDzuD5YPw0E7tnRF",
					"type": "arrow"
				},
				{
					"id": "orFTJS2S-90fdbxLrqFZ_",
					"type": "arrow"
				}
			],
			"updated": 1717875647620,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c2d04d56e0797060f13aaea8cb02a2b06dbd2a51",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "oSt36lgh7ASu9QVB3Necl",
			"type": "arrow",
			"x": 41.99117392209334,
			"y": 1597.8896740333107,
			"width": 44.03942411400311,
			"height": 15.330179280191032,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 2010548274,
			"version": 48,
			"versionNonce": 17678578,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717875620772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					7.804454906279034,
					15.330179280191032
				],
				[
					44.03942411400311,
					13.657796085988366
				]
			],
			"lastCommittedPoint": [
				44.03942411400311,
				13.657796085988366
			],
			"startBinding": {
				"elementId": "boMQ3onmBzw6wgGR45NvD",
				"focus": -0.6295578522937114,
				"gap": 2.696182144119348
			},
			"endBinding": {
				"elementId": "I6lzKzjb",
				"focus": 0.3054116691777568,
				"gap": 12.691216394863801
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "I6lzKzjb",
			"type": "text",
			"x": 98.72181443096025,
			"y": 1600.955709889349,
			"width": 190.91246032714844,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 9685550,
			"version": 73,
			"versionNonce": 1665979058,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "oSt36lgh7ASu9QVB3Necl",
					"type": "arrow"
				}
			],
			"updated": 1717875620772,
			"link": null,
			"locked": false,
			"text": "initial state distribution",
			"rawText": "initial state distribution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "initial state distribution",
			"lineHeight": 1.25
		},
		{
			"id": "Oh2IfkDzuD5YPw0E7tnRF",
			"type": "arrow",
			"x": 17.18415654142072,
			"y": 1595.659829774374,
			"width": 0.27873053236712053,
			"height": 39.301005063762204,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1464052850,
			"version": 43,
			"versionNonce": 2036367022,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717875626195,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.27873053236712053,
					39.301005063762204
				]
			],
			"lastCommittedPoint": [
				-0.27873053236712053,
				39.301005063762204
			],
			"startBinding": {
				"elementId": "boMQ3onmBzw6wgGR45NvD",
				"focus": -0.3327089993059913,
				"gap": 1
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "YqDmmVO9",
			"type": "text",
			"x": -48.674660481995005,
			"y": 1648.0611698593902,
			"width": 143.42431640625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1161511026,
			"version": 39,
			"versionNonce": 1925211438,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875641692,
			"link": null,
			"locked": false,
			"text": "observation state\ndistribution",
			"rawText": "observation state\ndistribution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "observation state\ndistribution",
			"lineHeight": 1.25
		},
		{
			"id": "orFTJS2S-90fdbxLrqFZ_",
			"type": "arrow",
			"x": -4.8355555155808645,
			"y": 1600.3982488246147,
			"width": 47.38419050240839,
			"height": 19.232406733330436,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1569681838,
			"version": 53,
			"versionNonce": 1754139694,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717875683116,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-6.1320717120763675,
					19.232406733330436
				],
				[
					-47.38419050240839,
					18.9536762009634
				]
			],
			"lastCommittedPoint": [
				-47.38419050240839,
				18.9536762009634
			],
			"startBinding": {
				"elementId": "boMQ3onmBzw6wgGR45NvD",
				"focus": -0.007522443427143247,
				"gap": 5.204756935423347
			},
			"endBinding": {
				"elementId": "RUikAeD7",
				"focus": 0.18475218536733254,
				"gap": 4.421519495714932
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "RUikAeD7",
			"type": "text",
			"x": -280.7857967637042,
			"y": 1606.5773803265402,
			"width": 224.14453125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1790501170,
			"version": 59,
			"versionNonce": 932730478,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "orFTJS2S-90fdbxLrqFZ_",
					"type": "arrow"
				}
			],
			"updated": 1717875683116,
			"link": null,
			"locked": false,
			"text": "state transition distribution",
			"rawText": "state transition distribution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "state transition distribution",
			"lineHeight": 1.25
		},
		{
			"id": "TIz-cJIlKr_vTesDFHwas",
			"type": "line",
			"x": 459.5926890159353,
			"y": 1405.6057612440304,
			"width": 264.51313923094244,
			"height": 258.19371269641493,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 995917426,
			"version": 363,
			"versionNonce": 1014506546,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875736217,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					128.19408112898918,
					159.79121380162724
				],
				[
					186.87447037817432,
					106.52747586775173
				],
				[
					184.1661447205196,
					258.19371269641493
				],
				[
					29.79158223420164,
					257.2909374771966
				],
				[
					85.7636458257322,
					200.41609866644788
				],
				[
					-77.63866885276809,
					70.41646709902216
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				0.9027752192181424,
				-2.7083256576547683
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 1782784302,
			"isDeleted": false,
			"id": "C4CqKMC6eLKpvEN8DV_4f",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -470.7110419041892,
			"y": 1406.0919697067002,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 288.271285299296,
			"height": 258.1937126964149,
			"seed": 1801338802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717875746833,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-128.19408112898918,
					159.79121380162724
				],
				[
					-186.87447037817432,
					106.5274758677517
				],
				[
					-184.16614472051964,
					258.1937126964149
				],
				[
					-29.79158223420164,
					257.2909374771966
				],
				[
					-85.76364582573223,
					200.41609866644785
				],
				[
					101.39681492112163,
					95.05454450324056
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "n108UCdPg-AQODpc2NNew",
			"type": "line",
			"x": -55.27700441781383,
			"y": 1715.800102213067,
			"width": 218.68357536337743,
			"height": 269.8280244840564,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1664803054,
			"version": 413,
			"versionNonce": 347830638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875915118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					125.90852133692977,
					0.5763759701107958
				],
				[
					110.63934520713428,
					187.85638821628027
				],
				[
					185.55140185779814,
					189.00888139552123
				],
				[
					77.94206837047727,
					269.8280244840564
				],
				[
					-33.132173505579274,
					184.11085007399242
				],
				[
					45.812962369976646,
					186.7041537980199
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				1.152493179240992,
				4.609972716963966
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "mHon4U4Y",
			"type": "text",
			"x": 530.5941235234102,
			"y": 1658.8645709977927,
			"width": 833.78759765625,
			"height": 105,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1300303534,
			"version": 253,
			"versionNonce": 1082913838,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717875841225,
			"link": null,
			"locked": false,
			"text": "Given an observation sequence O1...On\nand a model distribution how do we efficiently compute\nthe probability of our observation sequence given our model?",
			"rawText": "Given an observation sequence O1...On\nand a model distribution how do we efficiently compute\nthe probability of our observation sequence given our model?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given an observation sequence O1...On\nand a model distribution how do we efficiently compute\nthe probability of our observation sequence given our model?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 404,
			"versionNonce": 80485678,
			"isDeleted": false,
			"id": "YlxINjkM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1377.847704728842,
			"y": 1652.3629949242782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 828.35546875,
			"height": 140,
			"seed": 1853029102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717875900381,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Given an observation sequence O1...On\nand a model distribution how do we efficiently compute\nthe most likely sequence of states (one that best explains\nour observable results)?",
			"rawText": "Given an observation sequence O1...On\nand a model distribution how do we efficiently compute\nthe most likely sequence of states (one that best explains\nour observable results)?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given an observation sequence O1...On\nand a model distribution how do we efficiently compute\nthe most likely sequence of states (one that best explains\nour observable results)?",
			"lineHeight": 1.25
		},
		{
			"id": "9WmcU2g2",
			"type": "text",
			"x": -307.8145476041533,
			"y": 2043.3947988119612,
			"width": 662.65087890625,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2038081522,
			"version": 154,
			"versionNonce": 1402473458,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877233951,
			"link": null,
			"locked": false,
			"text": "How do we adjust our model parameters in such\na way that maximizes the our observable?",
			"rawText": "How do we adjust our model parameters in such\na way that maximizes the our observable?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we adjust our model parameters in such\na way that maximizes the our observable?",
			"lineHeight": 1.25
		},
		{
			"id": "5Ky51kem",
			"type": "text",
			"x": 530.3299307316754,
			"y": 1770.7495393473207,
			"width": 843.6190185546875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1600330286,
			"version": 281,
			"versionNonce": 2072766322,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876319620,
			"link": null,
			"locked": false,
			"text": "The simplest approach is to enumerate over every single possible sequence\nand add the probability of them casing our observation.\nTo calculate the probability of our observation sequence to occur as a consequence\nof our state sequence we can compute:",
			"rawText": "The simplest approach is to enumerate over every single possible sequence\nand add the probability of them casing our observation.\nTo calculate the probability of our observation sequence to occur as a consequence\nof our state sequence we can compute:",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The simplest approach is to enumerate over every single possible sequence\nand add the probability of them casing our observation.\nTo calculate the probability of our observation sequence to occur as a consequence\nof our state sequence we can compute:",
			"lineHeight": 1.25
		},
		{
			"id": "uDkOeAk5a42whIgBi6ElG",
			"type": "image",
			"x": 772.3223198424292,
			"y": 1873.137192455713,
			"width": 363.54166157526606,
			"height": 93.6307618047585,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 897975538,
			"version": 129,
			"versionNonce": 1945749678,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876321974,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c3f692890ea060545d8794373b3f1855b45dab2",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "3Ww0Esnf",
			"type": "text",
			"x": 636.0397700428878,
			"y": 1966.767954239401,
			"width": 632.1993408203125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 503430322,
			"version": 78,
			"versionNonce": 701655342,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876337646,
			"link": null,
			"locked": false,
			"text": "Subsequently to sum up over all possible sequences we compute:",
			"rawText": "Subsequently to sum up over all possible sequences we compute:",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Subsequently to sum up over all possible sequences we compute:",
			"lineHeight": 1.25
		},
		{
			"id": "wIpYm5SKKR9QvvJ5gbATQ",
			"type": "image",
			"x": 748.4155332128753,
			"y": 1991.7679537556617,
			"width": 483.53060600610456,
			"height": 80.67867894166807,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 854619566,
			"version": 149,
			"versionNonce": 290379954,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876360485,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "98ecfba6d59b27ae2823aa6da76386ea7c0b31dd",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "sUnzK78y",
			"type": "text",
			"x": 570.4999133863948,
			"y": 2081.088080993985,
			"width": 763.279052734375,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1800175090,
			"version": 167,
			"versionNonce": 1936360434,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876416425,
			"link": null,
			"locked": false,
			"text": "This will clearly get out of hand very quickly and will scale exponentially with\nthe amount of states and sequences",
			"rawText": "This will clearly get out of hand very quickly and will scale exponentially with\nthe amount of states and sequences",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This will clearly get out of hand very quickly and will scale exponentially with\nthe amount of states and sequences",
			"lineHeight": 1.25
		},
		{
			"id": "VvZgsFNR",
			"type": "text",
			"x": 716.9489205204413,
			"y": 2150.1074273196336,
			"width": 461.0780029296875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1594421554,
			"version": 47,
			"versionNonce": 298926962,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876660864,
			"link": null,
			"locked": false,
			"text": "The forward-Backward Procedure",
			"rawText": "The forward-Backward Procedure",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The forward-Backward Procedure",
			"lineHeight": 1.25
		},
		{
			"id": "zZmNM0uw",
			"type": "text",
			"x": 813.5780713606209,
			"y": 2193.4897776686803,
			"width": 267.8197021484375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 463331506,
			"version": 77,
			"versionNonce": 1664782194,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876700264,
			"link": null,
			"locked": false,
			"text": "Given the following variable",
			"rawText": "Given the following variable",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given the following variable",
			"lineHeight": 1.25
		},
		{
			"id": "r0ktHuRPDvDIhUZ08XBNY",
			"type": "image",
			"x": 795.1982676101287,
			"y": 2220.4082078798774,
			"width": 304.5793091635247,
			"height": 33.90493237441834,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1701483246,
			"version": 96,
			"versionNonce": 451206962,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876709973,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b70e30ea0d7e8e8022125b2628146eb4331869d4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "CB5RXnsl",
			"type": "text",
			"x": 662.138274824792,
			"y": 2254.3131400072884,
			"width": 596.2193603515625,
			"height": 525,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 308417650,
			"version": 321,
			"versionNonce": 126909102,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717877021195,
			"link": null,
			"locked": false,
			"text": "that indicates the occurrence of our observation such that\nwe end on state Si given our model.\n\nBy definition we can compute this term recursively\n\n1. Base case\n\n\n\n\n\n2. Recursive definition\n\n\n\n\n\n\n\n\n3. Final computation",
			"rawText": "that indicates the occurrence of our observation such that\nwe end on state Si given our model.\n\nBy definition we can compute this term recursively\n\n1. Base case\n\n\n\n\n\n2. Recursive definition\n\n\n\n\n\n\n\n\n3. Final computation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "that indicates the occurrence of our observation such that\nwe end on state Si given our model.\n\nBy definition we can compute this term recursively\n\n1. Base case\n\n\n\n\n\n2. Recursive definition\n\n\n\n\n\n\n\n\n3. Final computation",
			"lineHeight": 1.25
		},
		{
			"id": "SF4ohVcz9RW_O_2NAaqSG",
			"type": "image",
			"x": 826.1738252635067,
			"y": 2404.3131395115884,
			"width": 268.1482589642952,
			"height": 23.491620977641247,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1335619762,
			"version": 120,
			"versionNonce": 1511687278,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "G5D26s5OY8481xvxP85kf",
					"type": "arrow"
				},
				{
					"id": "RvcsZmG8wwJQvii_1fSV3",
					"type": "arrow"
				}
			],
			"updated": 1717876847779,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c7faf564e421a4ec70d7d20905a77a524fba3b9c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "G5D26s5OY8481xvxP85kf",
			"type": "arrow",
			"x": 932.1606828093581,
			"y": 2433.173125764133,
			"width": 58.33510278880033,
			"height": 26.46685219121491,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1260341618,
			"version": 52,
			"versionNonce": 1498699054,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717876842997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.240839043822234,
					24.306292828666756
				],
				[
					58.33510278880033,
					26.46685219121491
				]
			],
			"lastCommittedPoint": [
				58.33510278880033,
				26.46685219121491
			],
			"startBinding": {
				"elementId": "SF4ohVcz9RW_O_2NAaqSG",
				"focus": 0.22389493403482577,
				"gap": 5.368365274903681
			},
			"endBinding": {
				"elementId": "u8dtxaAZ",
				"focus": 0.0655722244428334,
				"gap": 8.251317213524999
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "u8dtxaAZ",
			"type": "text",
			"x": 998.7471028116834,
			"y": 2443.34628099343,
			"width": 122.85344445730675,
			"height": 41.06069178267365,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 534761906,
			"version": 164,
			"versionNonce": 716013422,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "G5D26s5OY8481xvxP85kf",
					"type": "arrow"
				}
			],
			"updated": 1717876842997,
			"link": null,
			"locked": false,
			"text": "distribution being at\nstate i and generating\nfirst observable",
			"rawText": "distribution being at\nstate i and generating\nfirst observable",
			"fontSize": 10.94951780871298,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distribution being at\nstate i and generating\nfirst observable",
			"lineHeight": 1.25
		},
		{
			"id": "RvcsZmG8wwJQvii_1fSV3",
			"type": "arrow",
			"x": 901.3727118930469,
			"y": 2434.7935452860443,
			"width": 72.46870831137448,
			"height": 27.745466717130967,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1509644338,
			"version": 274,
			"versionNonce": 846118706,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717876876535,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-11.883076494014858,
					21.06545378484452
				],
				[
					-72.46870831137448,
					27.745466717130967
				]
			],
			"lastCommittedPoint": [
				-59.41538247007429,
				30.247831075674185
			],
			"startBinding": {
				"elementId": "SF4ohVcz9RW_O_2NAaqSG",
				"focus": 0.3433334717091624,
				"gap": 6.988784796814798
			},
			"endBinding": {
				"elementId": "J6Wcnim6",
				"focus": 0.6179515400995258,
				"gap": 9.077812880308159
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "J6Wcnim6",
			"type": "text",
			"x": 688.6371277002069,
			"y": 2442.8956428956,
			"width": 131.18906300115748,
			"height": 28.93454621515533,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1974731566,
			"version": 166,
			"versionNonce": 1421085550,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "RvcsZmG8wwJQvii_1fSV3",
					"type": "arrow"
				}
			],
			"updated": 1717876873877,
			"link": null,
			"locked": false,
			"text": "distribution\nof starting at state i",
			"rawText": "distribution\nof starting at state i",
			"fontSize": 11.573818486062123,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distribution\nof starting at state i",
			"lineHeight": 1.25
		},
		{
			"id": "7T7PVfpAXtOG3p_kd_dqv",
			"type": "image",
			"x": 784.7051629018318,
			"y": 2564.1789835720556,
			"width": 413.31427918341257,
			"height": 77.80033490511295,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 103990446,
			"version": 108,
			"versionNonce": 1528549938,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717876905195,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "95c589ded0729bfd643f3eb337c2e32901e71e7a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "EXZ_V3HzU4LmE2Yzw3AhJ",
			"type": "arrow",
			"x": 927.3485579072482,
			"y": 2607.2573051008344,
			"width": 71.4483895240528,
			"height": 29.189281086045867,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1073938862,
			"version": 66,
			"versionNonce": 161870578,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717876940873,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					23.09002832179749
				],
				[
					-71.4483895240528,
					29.189281086045867
				]
			],
			"lastCommittedPoint": [
				-71.4483895240528,
				29.189281086045867
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "vAOxocBR",
				"focus": -0.13707899413214206,
				"gap": 2.1670533792298556
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "vAOxocBR",
			"type": "text",
			"x": 744.7953847120979,
			"y": 2619.444621418933,
			"width": 108.93773029186764,
			"height": 52.08848891987455,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1213497138,
			"version": 150,
			"versionNonce": 1309590706,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "EXZ_V3HzU4LmE2Yzw3AhJ",
					"type": "arrow"
				}
			],
			"updated": 1717876940873,
			"link": null,
			"locked": false,
			"text": "probability of\nbeing at the previous\nstate i according\nto our observations",
			"rawText": "probability of\nbeing at the previous\nstate i according\nto our observations",
			"fontSize": 10.417697783974909,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of\nbeing at the previous\nstate i according\nto our observations",
			"lineHeight": 1.25
		},
		{
			"id": "Xnd_FdAUXvuBOJUm-3HkP",
			"type": "arrow",
			"x": 959.1518044636863,
			"y": 2606.3859832773705,
			"width": 65.34913675980442,
			"height": 91.72101588664964,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2072607150,
			"version": 98,
			"versionNonce": 827730866,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717876959601,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					77.11198137656902
				],
				[
					-65.34913675980442,
					91.72101588664964
				]
			],
			"lastCommittedPoint": [
				-52.714970319575514,
				97.15238331624232
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "WBUyioVV",
				"focus": 0.6075308701095676,
				"gap": 8.188887594097253
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "WBUyioVV",
			"type": "text",
			"x": 792.2050055415076,
			"y": 2681.5027362480055,
			"width": 93.40877456827694,
			"height": 28.033878260672793,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 353219890,
			"version": 90,
			"versionNonce": 1027280946,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Xnd_FdAUXvuBOJUm-3HkP",
					"type": "arrow"
				}
			],
			"updated": 1717876959586,
			"link": null,
			"locked": false,
			"text": "probability of\ntransitioning to j",
			"rawText": "probability of\ntransitioning to j",
			"fontSize": 11.213551304269114,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of\ntransitioning to j",
			"lineHeight": 1.25
		},
		{
			"id": "HHDRobWaiU-mikZRw7QUk",
			"type": "arrow",
			"x": 1000.975251989961,
			"y": 2615.534862423743,
			"width": 49.665343937451325,
			"height": 73.62669408271267,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2130732850,
			"version": 81,
			"versionNonce": 908299630,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717876983384,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7426436469281725,
					64.47781493634011
				],
				[
					49.665343937451325,
					73.62669408271267
				]
			],
			"lastCommittedPoint": [
				49.665343937451325,
				73.62669408271267
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "VfJR4rHA",
				"focus": -0.2263108769140455,
				"gap": 3.2285896002651953
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "VfJR4rHA",
			"type": "text",
			"x": 1053.8691855276775,
			"y": 2675.220407331031,
			"width": 114.50102140095994,
			"height": 37.53316159104541,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1621921710,
			"version": 122,
			"versionNonce": 1366011822,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "HHDRobWaiU-mikZRw7QUk",
					"type": "arrow"
				}
			],
			"updated": 1717876983384,
			"link": null,
			"locked": false,
			"text": "distribution of being at\nstate j and generating\nt+1 observable",
			"rawText": "distribution of being at\nstate j and generating\nt+1 observable",
			"fontSize": 10.00884309094545,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distribution of being at\nstate j and generating\nt+1 observable",
			"lineHeight": 1.25
		},
		{
			"id": "x5EjKjTZss0O2qlys3jrk",
			"type": "image",
			"x": 864.5964427801191,
			"y": 2780.263805064235,
			"width": 192.41743377627836,
			"height": 57.65818573087087,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1698064814,
			"version": 98,
			"versionNonce": 1753577006,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877024503,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1150556832a47ca9f105bdebb7b69b0726e71cfe",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZAhBXSb0",
			"type": "text",
			"x": 869.1541183153606,
			"y": 2839.5755391748116,
			"width": 208.52452105293992,
			"height": 28.785858641366044,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1806512562,
			"version": 139,
			"versionNonce": 1630720562,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877083225,
			"link": null,
			"locked": false,
			"text": "iterating over all state's probability\npotential of generating our sequence",
			"rawText": "iterating over all state's probability\npotential of generating our sequence",
			"fontSize": 11.51434345654642,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "iterating over all state's probability\npotential of generating our sequence",
			"lineHeight": 1.25
		},
		{
			"id": "_QG2iiBflPnY6WHrX_MZx",
			"type": "image",
			"x": -1360.5855302899354,
			"y": 1801.66124597525,
			"width": 823,
			"height": 79,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1233715374,
			"version": 50,
			"versionNonce": 303023858,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877131834,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9d0161f63d17c1ab33f295c6d470c17dc0296b34",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "45grEjAT",
			"type": "text",
			"x": 873.5334215768559,
			"y": 1610.9557099396256,
			"width": 157.2120361328125,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1213010734,
			"version": 46,
			"versionNonce": 1588204206,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877218955,
			"link": null,
			"locked": false,
			"text": "Problem 1",
			"rawText": "Problem 1",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem 1",
			"lineHeight": 1.25
		},
		{
			"id": "iIwUsMXX",
			"type": "text",
			"x": -1050.2139916775595,
			"y": 1604.0773802899246,
			"width": 173.08804321289062,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 82291054,
			"version": 20,
			"versionNonce": 1351870638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877225934,
			"link": null,
			"locked": false,
			"text": "Problem 2",
			"rawText": "Problem 2",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem 2",
			"lineHeight": 1.25
		},
		{
			"id": "3c6iOLQv",
			"type": "text",
			"x": -62.94852514447999,
			"y": 1998.3947986433136,
			"width": 171.9720458984375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1775218862,
			"version": 34,
			"versionNonce": 1825900594,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877239782,
			"link": null,
			"locked": false,
			"text": "Problem 3",
			"rawText": "Problem 3",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem 3",
			"lineHeight": 1.25
		},
		{
			"id": "kVB25M8M",
			"type": "text",
			"x": -1388.0530348818452,
			"y": 1887.9215455249735,
			"width": 857.3991088867188,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1710677362,
			"version": 224,
			"versionNonce": 120644978,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877299649,
			"link": null,
			"locked": false,
			"text": "Just like Problem 1 we can formulate this problem in an inductive/recursive manner\nand take the maximum potential of each sequence while walking along the observations",
			"rawText": "Just like Problem 1 we can formulate this problem in an inductive/recursive manner\nand take the maximum potential of each sequence while walking along the observations",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Just like Problem 1 we can formulate this problem in an inductive/recursive manner\nand take the maximum potential of each sequence while walking along the observations",
			"lineHeight": 1.25
		},
		{
			"id": "nLRt34k8",
			"type": "text",
			"x": -1063.796729005067,
			"y": 1961.5885353694853,
			"width": 217.09974670410156,
			"height": 400,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1455346546,
			"version": 92,
			"versionNonce": 1147644782,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877884620,
			"link": null,
			"locked": false,
			"text": "1. Base case\n\n\n\n\n\n2. Recursive definition\n\n\n\n\n\n\n\n\n3. Final computation",
			"rawText": "1. Base case\n\n\n\n\n\n2. Recursive definition\n\n\n\n\n\n\n\n\n3. Final computation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Base case\n\n\n\n\n\n2. Recursive definition\n\n\n\n\n\n\n\n\n3. Final computation",
			"lineHeight": 1.25
		},
		{
			"id": "YCxQ-iN4vVnjc77Tk2ZUN",
			"type": "image",
			"x": -1092.9739665779853,
			"y": 1988.853014287714,
			"width": 299.1902968224671,
			"height": 41.690451196573285,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1976084978,
			"version": 149,
			"versionNonce": 776964978,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717877885553,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cdedc08ef3f5ff2c70270c0ab6da0d6147211200",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 1403812530,
			"isDeleted": false,
			"id": "HpPmWAKEiKR910Qm5xGUu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -965.0419914559583,
			"y": 2030.735804794481,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 58.33510278880033,
			"height": 26.46685219121491,
			"seed": 1189461870,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717877885553,
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
					3.240839043822234,
					24.306292828666756
				],
				[
					58.33510278880033,
					26.46685219121491
				]
			]
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 760149554,
			"isDeleted": false,
			"id": "laLvBUCF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -898.4555714536331,
			"y": 2040.9089600237778,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 122.85344445730675,
			"height": 41.06069178267365,
			"seed": 790077870,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717877885553,
			"link": null,
			"locked": false,
			"fontSize": 10.94951780871298,
			"fontFamily": 1,
			"text": "distribution being at\nstate i and generating\nfirst observable",
			"rawText": "distribution being at\nstate i and generating\nfirst observable",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distribution being at\nstate i and generating\nfirst observable",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 506,
			"versionNonce": 1848152498,
			"isDeleted": false,
			"id": "408-rzndgN1FOzPtM2jZW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -995.8299623722695,
			"y": 2032.3562243163917,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 72.46870831137448,
			"height": 27.745466717130967,
			"seed": 1934834670,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717877885553,
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
					-11.883076494014858,
					21.06545378484452
				],
				[
					-72.46870831137448,
					27.745466717130967
				]
			]
		},
		{
			"type": "text",
			"version": 234,
			"versionNonce": 1257327922,
			"isDeleted": false,
			"id": "sYRRqJtq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1208.5655465651096,
			"y": 2040.4583219259478,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 131.18906300115748,
			"height": 28.93454621515533,
			"seed": 1503759918,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717877885553,
			"link": null,
			"locked": false,
			"fontSize": 11.573818486062123,
			"fontFamily": 1,
			"text": "distribution\nof starting at state i",
			"rawText": "distribution\nof starting at state i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distribution\nof starting at state i",
			"lineHeight": 1.25
		},
		{
			"id": "wOBkQiBa3aKn812gHEtSn",
			"type": "image",
			"x": -1167.9832423736461,
			"y": 2144.9175797949747,
			"width": 449.2088480332358,
			"height": 73.98733967606238,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 313033650,
			"version": 144,
			"versionNonce": 382786030,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877884620,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dc1c8c6b5df730de5d52f4c7a2c8be00b4efbc02",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 2037700338,
			"isDeleted": false,
			"id": "fKSAhfLLe0hBg20_43wTK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -975.3455227925097,
			"y": 2179.5868617419555,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 59.785510285220994,
			"height": 23.235776734650244,
			"seed": 1972026222,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717877885553,
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
					0,
					23.09002832179749
				],
				[
					-59.785510285220994,
					23.235776734650244
				]
			]
		},
		{
			"type": "text",
			"version": 275,
			"versionNonce": 711010482,
			"isDeleted": false,
			"id": "RUnAlIlZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1169.5615752264916,
			"y": 2191.7741780600536,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 132.26348876953125,
			"height": 26.04424445993727,
			"seed": 935140782,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717877885553,
			"link": null,
			"locked": false,
			"fontSize": 10.417697783974909,
			"fontFamily": 1,
			"text": "Optimal previous sequence\nthat got us to state i",
			"rawText": "Optimal previous sequence\nthat got us to state i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Optimal previous sequence\nthat got us to state i",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 260,
			"versionNonce": 626868850,
			"isDeleted": false,
			"id": "TKfAYwfzhJ6l-EH6gRF5m",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -943.5422762360715,
			"y": 2178.7155399184912,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 65.34913675980442,
			"height": 91.72101588664964,
			"seed": 1105803246,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717877885553,
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
					0,
					77.11198137656902
				],
				[
					-65.34913675980442,
					91.72101588664964
				]
			]
		},
		{
			"type": "text",
			"version": 159,
			"versionNonce": 623911986,
			"isDeleted": false,
			"id": "I1nB94Ki",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1110.4454010699126,
			"y": 2253.8322928891257,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 93.32142639160156,
			"height": 28.033878260672786,
			"seed": 1545079342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717877885553,
			"link": null,
			"locked": false,
			"fontSize": 11.213551304269114,
			"fontFamily": 1,
			"text": "probability of\ntransitioning to j",
			"rawText": "probability of\ntransitioning to j",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of\ntransitioning to j",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 245,
			"versionNonce": 1942015474,
			"isDeleted": false,
			"id": "tSIy9gShtrg08mppGA5uJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -901.7188287097969,
			"y": 2187.864419064864,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 49.715880577872554,
			"height": 73.63524467399293,
			"seed": 1697813614,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717877885553,
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
					1.7426436469281725,
					64.47781493634011
				],
				[
					49.715880577872554,
					73.63524467399293
				]
			]
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 102121394,
			"isDeleted": false,
			"id": "qPUFoOKV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -848.7743585316589,
			"y": 2247.549963972152,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 114.39994812011719,
			"height": 37.53316159104544,
			"seed": 1996609198,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717877885553,
			"link": null,
			"locked": false,
			"fontSize": 10.00884309094545,
			"fontFamily": 1,
			"text": "distribution of being at\nstate j and generating\nt observable",
			"rawText": "distribution of being at\nstate j and generating\nt observable",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distribution of being at\nstate j and generating\nt observable",
			"lineHeight": 1.25
		},
		{
			"id": "nl1PPlbdkV0t1ANnUeGdX",
			"type": "image",
			"x": -1040.8624346821098,
			"y": 2368.6351770858337,
			"width": 187.75739759215983,
			"height": 53.26450995522266,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 267471342,
			"version": 158,
			"versionNonce": 1665788014,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877884620,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ed04a77d2af532b28626065fdeb8934c0c9ec315",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 357,
			"versionNonce": 1594796718,
			"isDeleted": false,
			"id": "vvvOJBJc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1018.7244455483096,
			"y": 2420.586777843585,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 152.83665466308594,
			"height": 26.04424445993727,
			"seed": 241107758,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717877884620,
			"link": null,
			"locked": false,
			"fontSize": 10.417697783974909,
			"fontFamily": 1,
			"text": "Optimal sequence\nthat gets us our observation",
			"rawText": "Optimal sequence\nthat gets us our observation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Optimal sequence\nthat gets us our observation",
			"lineHeight": 1.25
		},
		{
			"id": "Nm3sQHzm",
			"type": "text",
			"x": -1398.5495174910436,
			"y": 2468.367804178073,
			"width": 869.7590942382812,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1917445166,
			"version": 232,
			"versionNonce": 1735100274,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877874035,
			"link": null,
			"locked": false,
			"text": "Not that this gets us the maximum potential but not the maximum sequence of states\nthus we also need to have a pointer around to keep track of things",
			"rawText": "Not that this gets us the maximum potential but not the maximum sequence of states\nthus we also need to have a pointer around to keep track of things",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Not that this gets us the maximum potential but not the maximum sequence of states\nthus we also need to have a pointer around to keep track of things",
			"lineHeight": 1.25
		},
		{
			"id": "rH4WA182_9CvyCDTGTVPS",
			"type": "image",
			"x": -1123.5191255971142,
			"y": 2527.5583121686595,
			"width": 303.17207132036026,
			"height": 48.23192043733004,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 415976686,
			"version": 105,
			"versionNonce": 1999489330,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877874035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f0a9f13903e7dd246d509bee9b79708c9e89a4c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "0Kana1TL",
			"type": "text",
			"x": -1296.3357299227355,
			"y": 2596.89272593066,
			"width": 636.8994140625,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1594265006,
			"version": 151,
			"versionNonce": 1623315186,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877874035,
			"link": null,
			"locked": false,
			"text": "Which can be recursively updated at each iteration to save the\nindex of the current best state in the sequence",
			"rawText": "Which can be recursively updated at each iteration to save the\nindex of the current best state in the sequence",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which can be recursively updated at each iteration to save the\nindex of the current best state in the sequence",
			"lineHeight": 1.25
		},
		{
			"id": "-79Vutx8-3P7v1VRJER7G",
			"type": "image",
			"x": -1059.9208367241008,
			"y": 2654.655314946924,
			"width": 164.069627061338,
			"height": 46.276048658326104,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1191963506,
			"version": 105,
			"versionNonce": 380544178,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717877874035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "de372540639a535194ffa8b57425c68ede342491",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Ib9weSka",
			"type": "text",
			"x": -299.37263064046095,
			"y": 2113.394799147614,
			"width": 642.1392822265625,
			"height": 300,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1719882290,
			"version": 538,
			"versionNonce": 1774353266,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878589014,
			"link": null,
			"locked": false,
			"text": "In order to learn our optimal model parameters we must perform\nExpectation maximization style of updating parameters\n\n1. Given our observation and our current model parameters\ncompute the probability of being in state i and the probability\nof transitioning from state i to state j\n\n\n\n\n2. update our parameters such that they properly reflect\nthe probabilities we calculated inferred from our observations",
			"rawText": "In order to learn our optimal model parameters we must perform\nExpectation maximization style of updating parameters\n\n1. Given our observation and our current model parameters\ncompute the probability of being in state i and the probability\nof transitioning from state i to state j\n\n\n\n\n2. update our parameters such that they properly reflect\nthe probabilities we calculated inferred from our observations",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In order to learn our optimal model parameters we must perform\nExpectation maximization style of updating parameters\n\n1. Given our observation and our current model parameters\ncompute the probability of being in state i and the probability\nof transitioning from state i to state j\n\n\n\n\n2. update our parameters such that they properly reflect\nthe probabilities we calculated inferred from our observations",
			"lineHeight": 1.25
		},
		{
			"id": "S39oWcaSgNosnVdLf7x84",
			"type": "image",
			"x": -135.39374958780354,
			"y": 2274.6092354036286,
			"width": 335.02035444022283,
			"height": 82.969393594952,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1223411442,
			"version": 137,
			"versionNonce": 1092693998,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "u3jOPgeTKMajn4_vm8_jx",
					"type": "arrow"
				}
			],
			"updated": 1717879049691,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7ddbe71c4c434f150a7253a397a5e6345934e014",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "qdGPZySSvo1-auFb6RDTL",
			"type": "image",
			"x": -34.37323949312281,
			"y": 2460.3693677173765,
			"width": 103.83908363111392,
			"height": 32.00519700958991,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2112440690,
			"version": 112,
			"versionNonce": 100514542,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "4pLE-6G8XjiqvmHUZi4jp",
					"type": "arrow"
				}
			],
			"updated": 1717878750570,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ed3daef6432c0da37c7a4c40da0dfbf4d5499097",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YbtSjwKiYTdsyTI-HIJ4t",
			"type": "image",
			"x": -235.25322826496404,
			"y": 2422.3588662959382,
			"width": 160.77702772692533,
			"height": 113.55998240935247,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 285349746,
			"version": 93,
			"versionNonce": 280532590,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "NkGsqZensQIbMnAYqFUzu",
					"type": "arrow"
				}
			],
			"updated": 1717878892482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "13172cd39e22b3746ff7a421b11eda9b94c69041",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "6gzOxql33k2qV2ZCVMYx8",
			"type": "image",
			"x": 109.02352103259746,
			"y": 2411.5106323473383,
			"width": 172.17236851274083,
			"height": 119.79630818847663,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1353584690,
			"version": 104,
			"versionNonce": 1404146990,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "s5Om2SEvO9s2tzivMKt4e",
					"type": "arrow"
				},
				{
					"id": "YbrVRrDu7Xt_lkr6T1bCO",
					"type": "arrow"
				}
			],
			"updated": 1717878970973,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "02587022afd5f49a87b7a686d7bb81be590e7b4f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "VWLoqfTVm4KR6cqMUPros",
			"type": "arrow",
			"x": 121.8058501441987,
			"y": 2290.870957470311,
			"width": 73.36296294595729,
			"height": 1.7061154173479736,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 180826290,
			"version": 61,
			"versionNonce": 162859694,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878730364,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					73.36296294595729,
					1.7061154173479736
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "Z2y6ofte",
				"focus": 0.12074805701859628,
				"gap": 13.876467884676856
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Z2y6ofte",
			"type": "text",
			"x": 209.04528097483285,
			"y": 2278.5846238532968,
			"width": 250.91258239746094,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1817661170,
			"version": 86,
			"versionNonce": 1213957358,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VWLoqfTVm4KR6cqMUPros",
					"type": "arrow"
				}
			],
			"updated": 1717878730364,
			"link": null,
			"locked": false,
			"text": "probabaility of being at state i\nat time t",
			"rawText": "probabaility of being at state i\nat time t",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probabaility of being at state i\nat time t",
			"lineHeight": 1.25
		},
		{
			"id": "u3jOPgeTKMajn4_vm8_jx",
			"type": "arrow",
			"x": -136.39374958780357,
			"y": 2335.869982538532,
			"width": 77.33643234640718,
			"height": 0.07131907806069648,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1488500526,
			"version": 40,
			"versionNonce": 563151406,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879049691,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-77.33643234640718,
					-0.07131907806069648
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "S39oWcaSgNosnVdLf7x84",
				"focus": -0.47867062477536315,
				"gap": 1
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Dr2ELl7t",
			"type": "text",
			"x": -468.73501163631005,
			"y": 2318.168804147877,
			"width": 257.50457763671875,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 346790766,
			"version": 148,
			"versionNonce": 959042610,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878888015,
			"link": null,
			"locked": false,
			"text": "probability of being at state\ni at time t and state j at time\nt+1",
			"rawText": "probability of being at state\ni at time t and state j at time\nt+1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of being at state\ni at time t and state j at time\nt+1",
			"lineHeight": 1.25
		},
		{
			"id": "4pLE-6G8XjiqvmHUZi4jp",
			"type": "arrow",
			"x": 29.67561760741563,
			"y": 2496.7422178302836,
			"width": 0.5687051391159343,
			"height": 69.38202697214592,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1036920818,
			"version": 52,
			"versionNonce": 753270958,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878750570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5687051391159343,
					69.38202697214592
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "qdGPZySSvo1-auFb6RDTL",
				"focus": -0.2298209930046621,
				"gap": 4.367653103317025
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "kh036E8R",
			"type": "text",
			"x": -59.8714044871341,
			"y": 2575.2235270282845,
			"width": 174.54440307617188,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1514297198,
			"version": 42,
			"versionNonce": 519235122,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878757914,
			"link": null,
			"locked": false,
			"text": "probability of being at\nstate i at time 1",
			"rawText": "probability of being at\nstate i at time 1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of being at\nstate i at time 1",
			"lineHeight": 1.25
		},
		{
			"id": "r-6VoS9tf9WlILg010Was",
			"type": "arrow",
			"x": -179.03916844813733,
			"y": 2453.5206272574715,
			"width": 118.29066893611724,
			"height": 25.023026121101793,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1536197042,
			"version": 61,
			"versionNonce": 202998702,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717878789841,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-46.63382140750775,
					-18.198564451710354
				],
				[
					-118.29066893611724,
					6.8244616693914395
				]
			],
			"lastCommittedPoint": [
				-118.29066893611724,
				6.8244616693914395
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "9H24XUZy",
			"type": "text",
			"x": -500.25162479168785,
			"y": 2464.3260249006744,
			"width": 222.72052001953125,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 434158190,
			"version": 103,
			"versionNonce": 27219442,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878805973,
			"link": null,
			"locked": false,
			"text": "probability of being\nat state i at time t\nand transitioning to state j\nin next t",
			"rawText": "probability of being\nat state i at time t\nand transitioning to state j\nin next t",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of being\nat state i at time t\nand transitioning to state j\nin next t",
			"lineHeight": 1.25
		},
		{
			"id": "NkGsqZensQIbMnAYqFUzu",
			"type": "arrow",
			"x": -171.64600163963001,
			"y": 2540.5325135422117,
			"width": 92.13023253678358,
			"height": 65.96979613744998,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1264840626,
			"version": 44,
			"versionNonce": 557818926,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717878906795,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-32.41619292960905,
					64.832385859218
				],
				[
					-92.13023253678358,
					65.96979613744998
				]
			],
			"lastCommittedPoint": [
				-92.13023253678358,
				65.96979613744998
			],
			"startBinding": {
				"elementId": "YbtSjwKiYTdsyTI-HIJ4t",
				"focus": -0.12792545927506943,
				"gap": 4.613664836921089
			},
			"endBinding": {
				"elementId": "MF2G4fWQ",
				"focus": -0.2909068564307082,
				"gap": 5.582900686826463
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "MF2G4fWQ",
			"type": "text",
			"x": -489.08761997066193,
			"y": 2595.1282068973424,
			"width": 219.72848510742188,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1622148018,
			"version": 85,
			"versionNonce": 374795886,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "NkGsqZensQIbMnAYqFUzu",
					"type": "arrow"
				}
			],
			"updated": 1717878906795,
			"link": null,
			"locked": false,
			"text": "divided by the probability of\nbeing at state i at time t",
			"rawText": "divided by the probability of\nbeing at state i at time t",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "divided by the probability of\nbeing at state i at time t",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 131,
			"versionNonce": 132171118,
			"isDeleted": false,
			"id": "s5Om2SEvO9s2tzivMKt4e",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 214.94397567340343,
			"y": 2538.404267577096,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 92.130232536784,
			"height": 65.96979613745029,
			"seed": 33302510,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717878958978,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6gzOxql33k2qV2ZCVMYx8",
				"focus": 0.11775274196683426,
				"gap": 7.097327041280778
			},
			"endBinding": {
				"elementId": "jn0P42lp",
				"focus": 0.29041767247362704,
				"gap": 6.150287666650456
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
					32.4161929296092,
					64.83238585921829
				],
				[
					92.130232536784,
					65.96979613745029
				]
			]
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 2018793842,
			"isDeleted": false,
			"id": "jn0P42lp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 313.22449587683786,
			"y": 2592.9999609322267,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 219.7284851074229,
			"height": 40.000000000000185,
			"seed": 2085419566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "s5Om2SEvO9s2tzivMKt4e",
					"type": "arrow"
				}
			],
			"updated": 1717878958788,
			"link": null,
			"locked": false,
			"fontSize": 16.000000000000075,
			"fontFamily": 1,
			"text": "divided by the probability of\nbeing at state i at time t",
			"rawText": "divided by the probability of\nbeing at state i at time t",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "divided by the probability of\nbeing at state i at time t",
			"lineHeight": 1.25
		},
		{
			"id": "YbrVRrDu7Xt_lkr6T1bCO",
			"type": "arrow",
			"x": 292.98609701809943,
			"y": 2447.833575866312,
			"width": 117.72196379700131,
			"height": 34.1223083469572,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1282683442,
			"version": 40,
			"versionNonce": 255757870,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717878971456,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					60.28274474629052,
					-12.511513060550897
				],
				[
					117.72196379700131,
					21.6107952864063
				]
			],
			"lastCommittedPoint": [
				117.72196379700131,
				21.6107952864063
			],
			"startBinding": {
				"elementId": "6gzOxql33k2qV2ZCVMYx8",
				"focus": -0.04193709729120462,
				"gap": 11.790207472761153
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "EPP9BqdU",
			"type": "text",
			"x": 316.7482198096492,
			"y": 2470.58178143095,
			"width": 240.2405548095703,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1664341230,
			"version": 73,
			"versionNonce": 1917884146,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717878989089,
			"link": null,
			"locked": false,
			"text": "probability of being at state i\nat time t given by the\nobservation k",
			"rawText": "probability of being at state i\nat time t given by the\nobservation k",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of being at state i\nat time t given by the\nobservation k",
			"lineHeight": 1.25
		},
		{
			"id": "qUHpM5x5",
			"type": "text",
			"x": -150.25444615792856,
			"y": 2679.7711055775994,
			"width": 363.4796142578125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 296405230,
			"version": 68,
			"versionNonce": 1343583598,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879071714,
			"link": null,
			"locked": false,
			"text": "How do we actually compute Gamma?",
			"rawText": "How do we actually compute Gamma?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we actually compute Gamma?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 151,
			"versionNonce": 1462845934,
			"isDeleted": false,
			"id": "F008A1k9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -104.70321570790372,
			"y": 2728.494943841133,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 45.757313938855475,
			"height": 23.571949604864944,
			"seed": 69185,
			"groupIds": [
				"0793pDrld5W-ywNEc4CIg"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717879115676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "38b6ed46bbc4d19b1fdf983f36418251e3b10eb8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "I3D7G3-EMYeo8Jc0PHuBc",
			"type": "image",
			"x": -58.15148717094712,
			"y": 2711.3744541619053,
			"width": 239.96247300782989,
			"height": 81.25140169565346,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"0793pDrld5W-ywNEc4CIg"
			],
			"frameId": null,
			"roundness": null,
			"seed": 2027365362,
			"version": 97,
			"versionNonce": 1607390254,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879115676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "efab28de9560a7a8ac773444a64e164e6db98098",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "OEPxR50IiBX0Wn8u5pjT_",
			"type": "arrow",
			"x": 107.82375279064587,
			"y": 2783.2835333805797,
			"width": 66.254011084609,
			"height": 71.50585342668137,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1594761390,
			"version": 68,
			"versionNonce": 1695961138,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717879150268,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8079757449342537,
					39.59081150177826
				],
				[
					-50.09449618592387,
					43.63069022644959
				],
				[
					-66.254011084609,
					71.50585342668137
				]
			],
			"lastCommittedPoint": [
				-66.254011084609,
				71.50585342668137
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "QKstW3s0",
			"type": "text",
			"x": -22.98240520558423,
			"y": 2873.4489017059464,
			"width": 129.1042938232422,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 679977646,
			"version": 20,
			"versionNonce": 346578610,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879154844,
			"link": null,
			"locked": false,
			"text": "forward variable",
			"rawText": "forward variable",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "forward variable",
			"lineHeight": 1.25
		},
		{
			"id": "foSZD2bit_6zVDW-nzV1P",
			"type": "arrow",
			"x": 173.2697881303206,
			"y": 2770.7599093340987,
			"width": 181.984193865485,
			"height": 73.35417866635999,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1134680626,
			"version": 148,
			"versionNonce": 307475890,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717879333418,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					109.48071343859164,
					3.635890852204284
				],
				[
					181.984193865485,
					73.35417866635999
				]
			],
			"lastCommittedPoint": [
				121.6003496126055,
				71.90984129914887
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "IWBOsobY",
				"focus": 0.0774744364395315,
				"gap": 14.543563408816226
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "IWBOsobY",
			"type": "text",
			"x": 304.43690256583534,
			"y": 2858.657651409275,
			"width": 140.2083282470703,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1963776238,
			"version": 81,
			"versionNonce": 1744110578,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "foSZD2bit_6zVDW-nzV1P",
					"type": "arrow"
				}
			],
			"updated": 1717879333418,
			"link": null,
			"locked": false,
			"text": "backward variable",
			"rawText": "backward variable",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "backward variable",
			"lineHeight": 1.25
		},
		{
			"id": "GPk1rfDP52qcC1V7K5BvO",
			"type": "arrow",
			"x": -28.577634992482388,
			"y": 2765.367328260266,
			"width": 126.8655510843052,
			"height": 81.34320628346632,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 20570482,
			"version": 111,
			"versionNonce": 1281892462,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717879175481,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-63.18401955963435,
					73.3830148428824
				],
				[
					-126.8655510843052,
					81.34320628346632
				]
			],
			"lastCommittedPoint": [
				-126.8655510843052,
				81.34320628346632
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "aPFYoo39",
			"type": "text",
			"x": -571.6659091116342,
			"y": 2776.83671137753,
			"width": 448.0008544921875,
			"height": 120,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 101746610,
			"version": 531,
			"versionNonce": 1824628786,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879443697,
			"link": null,
			"locked": false,
			"text": "The probability of our observation occuring such\nthat we end on state i at time t times the probability\nof our future observation (the rest of the observation)\noccuring given we are now at state t\ndivided by the probability of our\nobservation sequence as a whole occurring in our model",
			"rawText": "The probability of our observation occuring such\nthat we end on state i at time t times the probability\nof our future observation (the rest of the observation)\noccuring given we are now at state t\ndivided by the probability of our\nobservation sequence as a whole occurring in our model",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The probability of our observation occuring such\nthat we end on state i at time t times the probability\nof our future observation (the rest of the observation)\noccuring given we are now at state t\ndivided by the probability of our\nobservation sequence as a whole occurring in our model",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 172,
			"versionNonce": 1737536558,
			"isDeleted": false,
			"id": "ffoSGvYOe5g6_B1kWM-v4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -113.74575340765585,
			"y": 2896.4862013146308,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"width": 304.5793091635247,
			"height": 33.90493237441834,
			"seed": 1330032302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717879337113,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b70e30ea0d7e8e8022125b2628146eb4331869d4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "jac4xoL-yfTncHdZNSI2R",
			"type": "image",
			"x": 200.13362556032348,
			"y": 2879.5557512836967,
			"width": 347.416154220891,
			"height": 27.132670788049207,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1149343854,
			"version": 152,
			"versionNonce": 1510147954,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879332052,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0dbb91c52c64202fb1829676291430b1a40f0d62",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "FuSGTh_E7HrJDl0_gjWWM",
			"type": "image",
			"x": -113.67492519359138,
			"y": 2927.257855153533,
			"width": 328.3375149884068,
			"height": 79.70198253016734,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2088287154,
			"version": 89,
			"versionNonce": 748206254,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879466304,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ab20293488e3e270d65ac56990e3b6b1c632ccab",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "PNxAA_Dt_P1lI_XdPwqmX",
			"type": "image",
			"x": 226.25300064980144,
			"y": 2907.88075131586,
			"width": 325.35077918425606,
			"height": 76.07277135483928,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 487122222,
			"version": 76,
			"versionNonce": 1547644334,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879477716,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e6ed19bba51d6e8fd893a7a4a6747ea8869d7476",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "B4xOqb7k60O1hd9XKIe-U",
			"type": "line",
			"x": -526.7029533943617,
			"y": 3043.278485074922,
			"width": 1204.9999999999998,
			"height": 7.5,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 818848114,
			"version": 74,
			"versionNonce": 798976174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879535222,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1204.9999999999998,
					7.5
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "IZZEPRR8",
			"type": "text",
			"x": -68.84946065754548,
			"y": 3060.778485074922,
			"width": 246.7930145263672,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 841192750,
			"version": 39,
			"versionNonce": 1361091822,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879543783,
			"link": null,
			"locked": false,
			"text": "Generalizing HMMs",
			"rawText": "Generalizing HMMs",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generalizing HMMs",
			"lineHeight": 1.25
		},
		{
			"id": "zxAEFHB7",
			"type": "text",
			"x": -296.38257985920563,
			"y": 3105.672535074922,
			"width": 701.8592529296875,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 314587250,
			"version": 248,
			"versionNonce": 1688931570,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879652452,
			"link": null,
			"locked": false,
			"text": "HMMs are directed graphical models that match prior knowledge\nabout the modeled task (latent states generate observations,\ncurrent latent state generates next latent state).\n\nwe cant always know the causality and for a more general formulation\nof the problem we have to infer the causality and not make it biased",
			"rawText": "HMMs are directed graphical models that match prior knowledge\nabout the modeled task (latent states generate observations,\ncurrent latent state generates next latent state).\n\nwe cant always know the causality and for a more general formulation\nof the problem we have to infer the causality and not make it biased",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "HMMs are directed graphical models that match prior knowledge\nabout the modeled task (latent states generate observations,\ncurrent latent state generates next latent state).\n\nwe cant always know the causality and for a more general formulation\nof the problem we have to infer the causality and not make it biased",
			"lineHeight": 1.25
		},
		{
			"id": "yR1xtQH4",
			"type": "text",
			"x": -97.17161096229619,
			"y": 3302.3413656881357,
			"width": 303.43731689453125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1011974062,
			"version": 40,
			"versionNonce": 187695154,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717879734656,
			"link": null,
			"locked": false,
			"text": "Types of independence",
			"rawText": "Types of independence",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Types of independence",
			"lineHeight": 1.25
		},
		{
			"id": "vgEQqAfh",
			"type": "text",
			"x": -109.31665906469652,
			"y": 3384.0101971252143,
			"width": 306.4052734375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 383972014,
			"version": 62,
			"versionNonce": 2010037998,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880027331,
			"link": null,
			"locked": false,
			"text": "Conditional dependence",
			"rawText": "Conditional dependence",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conditional dependence",
			"lineHeight": 1.25
		},
		{
			"id": "r8QDtg4Xl5O_9H64zXENl",
			"type": "image",
			"x": -47.81876672013442,
			"y": 3433.2583061542086,
			"width": 183.40948980965732,
			"height": 156.28878830898117,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1130520622,
			"version": 115,
			"versionNonce": 1773449518,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880027331,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f4530f7f4cd9348fc9842d9e17fee59b212726f7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "WHLrHBWd",
			"type": "text",
			"x": -182.27270110176357,
			"y": 3601.047017488259,
			"width": 473.6394958496094,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1512790446,
			"version": 300,
			"versionNonce": 111303534,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880027331,
			"link": null,
			"locked": false,
			"text": "States a and b are not independent because\nthey are conditionally dependent as they\ndo not depend on each other but depend on the\nsame condition",
			"rawText": "States a and b are not independent because\nthey are conditionally dependent as they\ndo not depend on each other but depend on the\nsame condition",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "States a and b are not independent because\nthey are conditionally dependent as they\ndo not depend on each other but depend on the\nsame condition",
			"lineHeight": 1.25
		},
		{
			"id": "FQfN2gG2aEAsdBGJ0PORG",
			"type": "image",
			"x": -120.32546888030163,
			"y": 3709.614015318831,
			"width": 365.1443535631391,
			"height": 247.3322475036894,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 655046130,
			"version": 105,
			"versionNonce": 81837486,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880027331,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a96b265f1205601488c34cb5687c454d5bf18e6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "DciGuRvy",
			"type": "text",
			"x": -592.428846117068,
			"y": 3384.0101972360562,
			"width": 249.7610321044922,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 565075378,
			"version": 184,
			"versionNonce": 2035386350,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880031009,
			"link": null,
			"locked": false,
			"text": "Reverse Causality",
			"rawText": "Reverse Causality",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reverse Causality",
			"lineHeight": 1.25
		},
		{
			"id": "1d06fSME9KwBJ-r1YdXrz",
			"type": "image",
			"x": -565.6552119508485,
			"y": 3433.25830603144,
			"width": 196.21376469392413,
			"height": 181.27363032636646,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1301961394,
			"version": 252,
			"versionNonce": 569793070,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880031009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "06f0f2ab366bf9756a62776f5b4e355a22ae23e6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "UIBS3YXC",
			"type": "text",
			"x": -692.2462400570863,
			"y": 3640.3440511760323,
			"width": 432.8594970703125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 179333426,
			"version": 286,
			"versionNonce": 2059854958,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880031009,
			"link": null,
			"locked": false,
			"text": "States a and b are not longer conditionally\ndependent when we reverse the order.\nthis effect is called \"explaining away\"",
			"rawText": "States a and b are not longer conditionally\ndependent when we reverse the order.\nthis effect is called \"explaining away\"",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "States a and b are not longer conditionally\ndependent when we reverse the order.\nthis effect is called \"explaining away\"",
			"lineHeight": 1.25
		},
		{
			"id": "jtsJw1UFd7EIpEw2y6QSa",
			"type": "image",
			"x": -642.8555492081997,
			"y": 3716.789625262844,
			"width": 350.6144379448357,
			"height": 240.1566373727838,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1476688946,
			"version": 309,
			"versionNonce": 1972119214,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880031009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e849a0a0f1a9060d727f427e9ab1bd257e27c872",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "OAJ4ZxNN",
			"type": "text",
			"x": 465.05040676456116,
			"y": 3384.0101972020007,
			"width": 240.43699645996094,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 177356142,
			"version": 39,
			"versionNonce": 725366638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880043204,
			"link": null,
			"locked": false,
			"text": "Remove Causality",
			"rawText": "Remove Causality",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Remove Causality",
			"lineHeight": 1.25
		},
		{
			"id": "ovgmtWxrPefIk6AzlQvwx",
			"type": "image",
			"x": 478.53554059886903,
			"y": 3419.01019724971,
			"width": 214.2552814369892,
			"height": 184.93613766140123,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 510374894,
			"version": 80,
			"versionNonce": 1764005362,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880060891,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cbdb9dc24523718051356e13dae707934c726dab",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xs3wVRtx",
			"type": "text",
			"x": 346.80983826854407,
			"y": 3603.9463347309456,
			"width": 514.8794555664062,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 5230830,
			"version": 77,
			"versionNonce": 1113381554,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717880107655,
			"link": null,
			"locked": false,
			"text": "Probabilities are replaced by more general\npotential functions.\nWe introduce a normalization term Z (which is often\nintractable)",
			"rawText": "Probabilities are replaced by more general\npotential functions.\nWe introduce a normalization term Z (which is often\nintractable)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Probabilities are replaced by more general\npotential functions.\nWe introduce a normalization term Z (which is often\nintractable)",
			"lineHeight": 1.25
		},
		{
			"id": "YtaoasfL",
			"type": "text",
			"x": 76.76327306905503,
			"y": 2812.904376033409,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 104324398,
			"version": 2,
			"versionNonce": 771848690,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879150269,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "OEPxR50IiBX0Wn8u5pjT_",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "2eDkbrHS",
			"type": "text",
			"x": 278.7504939395177,
			"y": 2764.395800186303,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1858335346,
			"version": 2,
			"versionNonce": 712154222,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879160554,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "foSZD2bit_6zVDW-nzV1P",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "2ytcMQmG",
			"type": "text",
			"x": -95.76166218151127,
			"y": 2828.750343103148,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1054609458,
			"version": 2,
			"versionNonce": 2007360174,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879175482,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "GPk1rfDP52qcC1V7K5BvO",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "u2AaXtlS",
			"type": "text",
			"x": -267.2972133632326,
			"y": 2827.7083069267,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 970113714,
			"version": 10,
			"versionNonce": 1516703150,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879185882,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "W8fgyvod",
			"type": "text",
			"x": -303.84461599201813,
			"y": 3164.528485074922,
			"width": 766.7833251953125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 735533998,
			"version": 2,
			"versionNonce": 147882802,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879567177,
			"link": null,
			"locked": false,
			"text": "HMMsaredirectedgraphicalmodelsthatmatchpriorknowledge",
			"rawText": "HMMsaredirectedgraphicalmodelsthatmatchpriorknowledge",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "HMMsaredirectedgraphicalmodelsthatmatchpriorknowledge",
			"lineHeight": 1.25
		},
		{
			"id": "CYXMDuhw",
			"type": "text",
			"x": -319.7626762947525,
			"y": 3209.528485074922,
			"width": 798.6194458007812,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 614465074,
			"version": 2,
			"versionNonce": 215089390,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879567177,
			"link": null,
			"locked": false,
			"text": "aboutthemodeledtask(latentstatesgeneratesobservations,",
			"rawText": "aboutthemodeledtask(latentstatesgeneratesobservations,",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "aboutthemodeledtask(latentstatesgeneratesobservations,",
			"lineHeight": 1.25
		},
		{
			"id": "vOtpDXQm",
			"type": "text",
			"x": -242.42634206623688,
			"y": 3254.528485074922,
			"width": 643.94677734375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1946924526,
			"version": 2,
			"versionNonce": 1643990258,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879567177,
			"link": null,
			"locked": false,
			"text": "currentlatentstategeneratesnextlatentstate).",
			"rawText": "currentlatentstategeneratesnextlatentstate).",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "currentlatentstategeneratesnextlatentstate).",
			"lineHeight": 1.25
		},
		{
			"id": "CB6FpDlh",
			"type": "text",
			"x": 438.1465729224549,
			"y": 3457.195578894945,
			"width": 14.00006103515625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 294428462,
			"version": 2,
			"versionNonce": 1722649714,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717879742457,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "FmWU9cK4",
			"type": "text",
			"x": 383.4236690316849,
			"y": 3649.5541482688973,
			"width": 382.5595397949219,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 590048690,
			"version": 9,
			"versionNonce": 781781550,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717880082202,
			"link": null,
			"locked": false,
			"text": "Probabilities are replacedbymoregeneral",
			"rawText": "Probabilities are replacedbymoregeneral",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Probabilities are replacedbymoregeneral",
			"lineHeight": 1.25
		},
		{
			"id": "KKuv0moj",
			"type": "text",
			"x": 445.55985994122943,
			"y": 3689.5541482688973,
			"width": 251.58103942871094,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 164691566,
			"version": 2,
			"versionNonce": 1794537394,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717880082202,
			"link": null,
			"locked": false,
			"text": "potentialfunctions.",
			"rawText": "potentialfunctions.",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "potentialfunctions.",
			"lineHeight": 1.25
		},
		{
			"id": "vAts4vQk",
			"type": "text",
			"x": 345.5294262864443,
			"y": 3734.5541482688973,
			"width": 451.64190673828125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1989601138,
			"version": 2,
			"versionNonce": 1066636398,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717880082202,
			"link": null,
			"locked": false,
			"text": "Weintroduceanormalizationterm Z",
			"rawText": "Weintroduceanormalizationterm Z",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weintroduceanormalizationterm Z",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#868e96",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 173.91862153045668,
		"scrollY": -3339.5656507293534,
		"zoom": {
			"value": 1.2104670226519072
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