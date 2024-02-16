---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Recurrent Neural Networks ^IIQAHb7n

To Dive deeper into RNN technology, we first need to explain
a few concepts ^fanhF9TY

Stateless Predictor ^3rMf77Mc

Stateful Predictor ^2MbfN8T0

V.S ^xO52lTlR

A stateless predictor is a predictor that
solely relies on the input in order to provide
an output, in other words its a function
of the input. ^j1lpYzW4

A stateful predictor is a predictor that
requires an input alongside the current
state of the machine, and will output a
result and an update to the state ^Ut4J6o6X

So far we have only been dealing
with stateless predictors like the multi-layer
perceptron and CNNs ^fVQDkTrO

We are currently intrested in modelling things
using a stateful predictor in order to try and
find a more optimal way of calculating events
in a time series ^cGXqzSx9

Lets take some
example ^ItYmHqZo

Moving Average ^rhPktFzp

Consider a sliding window over a time series, we are trying to find the 
average of the values in this window over an infinite horizon ^ZnuRzDrB

In a stateless model this calculation needs to be done from the start
of the input until our windows end with redundant calculations. ^WkLPrjUO

Consider the following stateful model ^KpywrPT3

such that ht indicates the state at stage t
and yt indicates the output at stage t ^ZzMCeCe1

This has potentially less parameters to tune, one only needs to input
the initial state h0 ^FCbqgX5T

Oscillator ^KOihc72v

A harmonic oscillator lets a particle accelerate in a way that is
proportional but of opposite sign to its offset from the origin ^xD5PYoWA

We define our state accordingly ^74tJhqNd

It is often useful to be able to model applied force to such oscillation ^v4ux9k9u

note that this is an approximation therefore its not entirely accurate ^LcwB6wmb

such that x1 can be interpreted
as the force applied at time t ^V8gUfZ4C

Building and Generalizing RNN ^3LkTcVMJ

Is the general equation for a staetful model such that the paremeters
A B C D are parameters that we need to learn to minimize the divergence
between y and the ground truth
 ^mVkvqof3

This can be seen a a big Neural network composed of sub neural networks each with their own
outputs and inputs, those sub neural networks have shared parameters theta between us
if each NN has depth of L, the entire network's depth is LT ^xWcJ5o6O

Unidirectional RNN: ^GFUamAqW

Bidirectional RNN: ^7OGIgW9E

Generate the output at the same
time as the input is received
enable a strong coupling between
the two sequences.
BUT
Cannot use information about
later time steps when generating
the output sequence ^ETxKsPi3

Add a RNN in reverse direction
in order to incorporate
information from future values in
the sequence ^Fpwuax6G

Encoder-Decoder: ^5w8dDvCt

This is required sometimes for reading and writing model, such that
you need to read the entire model and process it and produce your own
output after youve seen the entire model!
e.g Chatbot
Note that RNN's have quite a short term memory and cannot connect things
globally thus transformers are much better for this task ^1YBrWLvw

Global representation
of y ^I3BToJj4

h0 ^rvOLviuY

How do we initialize h0? ^iwszsNzt

Unlike the input data, the RNN's initial state (at time t = 0) is not
given and must be initialized to some value:


1) Set it to some arbitrary value (e.g. h0 = 0)
this is often not ideal

2) Set it at random (the RNN will then learn to desensitize itself to the
initial state, because we are giving it randomized noise data in each
iteration of training with the same result)

3) Use one of the two approaches above and simulate the RNN for a few
time steps in order to generate an initial state that is more plausible ^II47Apm9

Training RNNs... and why its difficult ^EVUrGEBS

The error of the entire model can be expressed as individual errors of sub-NN ^6bghgXfZ

And the Gradient w.r.t to the parameter theta (which is shared) can be
expressed via the chain rule: ^CleIyG0v

error gradient
w.r.t the output ^hPc1qd07

Direct derivative
of yt w.r.t theta ^R5LbjERg

Derivative of yt
w.r.t theta using
previous stages ^zCDoX4oC

Direct derivative of Hs-1
w.r.t theta ^AXj5rs9E

Matrix describing the
effect of previous time
onto the next ^zT5aFyl3

Gradient ^9xHbgegV

On one extreme, P corresponding to indices s = 2 and
t = T features a very large product structure of T − 2 terms
on the other extreme where s = t − 1, the product structure
totally vanishes ^2xo2sqqa

If we compute Pst in closed form and perform eigenvalue
decomposition on it by diagonalizing the resulting matrix:  ^wa7ru7bK

If max Eigenvalue > 1


If max Eigenvalue < 1 ^L0ZPXNer

The norm of the matrix D will increase
and thus the gradient will explode

The norm of the matrix D will decrease
and thus the gradient will vanish ^brkGfobl

In either cases we are left with a disbalance between
the different terms of the gradient!
But there are hueristics that can help us overcome these issues ^0TrtsWCg

Training the RNN with an appropriate level of noise applied to the
hidden states so that the model has incentive to desentisize itself from
the lower layers (thereby avoiding the exploding gradient problem ^rv4jMEtI

Choosing a particular class of functions for the RNN that is shown to
be more robust to the vanishing/exploding gradient problem ^YQeA3rii

Long Short-Term Memory ^mcm8r41Z

The LSTM is an enhanced RNN architecture where the building blocks
(cells) are equipped with special functions to stabilize learning,
specifically, mitigate the vanishing/exploding gradient problem.
This is done by evaluating previous values different or so called
short term memory and long term memory. ^YMkPojxQ

Tanh Activation
a function that turns our values
between -1 and 1 to give off
a normalization effect ^WAI4EWfQ

Sigmoid Activation
a smooth way to simulate on and off
switch (returns value between 0 
and 1) ^twrQV6jN

long term memory ^xEZ5DIv2

Gradient is always
the same between
these points ^S08RJGu9

short term memory ^zt6S7lKq

(aka weights and biases) ^IuiIlRYi

fg = What precentage of the long term memory is remembered
     (also called a forget gate)

ig = What precentage of the short term memory is remembered
     (also called the input gate)

ct = potential short term memory values at 100%

og = What precentage of short term memory should we save into the next stm
     this is multiplied of our long term memory value "normalized by tanh" also
     called the output gate ^Yuw7npOo

Gradient here can be
dampened but never 
amplified ^OrtVgqxW


# Embedded files
5bc22cfb4f7f138d5f7ce00f4e5556537fa46528: $$D = U \Lambda U^{-1}$$
dd5630d63cf3b35a9a8dd9ab6eb60e832a21f06a: $$D^{T-2} = U \Lambda ^{T-2} U^{-1}$$
c0094550dc71545262f63ce6a425c12bc3893c9e: [[Pasted Image 20240114130812_347.png]]
56043ece3989636c2b8bb1d1e1f6602268800ea7: [[Pasted Image 20240114131514_406.png]]
e8e4f75b66398207b8988a8164e847fa7baa2683: [[Pasted Image 20240114131529_420.png]]
4617d8f3e5634f01d0c69d88d0d2a0ea09f97ab4: [[Pasted Image 20240114131944_488.png]]
8b948909b72010b2665e7d416ac6e02f8d69d655: [[Pasted Image 20240114133042_840.png]]
453bef5dca6d10db66a4c5e2cd01527060e70e09: [[Pasted Image 20240114133352_579.png]]
3ebb4b45ac10f5f2bcf0d541e3b4caf3ff4514a4: [[Pasted Image 20240114133525_597.png]]
61b5bd97d95fa4fff7c90e523b2e63bda01cba5f: [[Pasted Image 20240114133645_619.png]]
cf9987ab3023ec24ca40ebd16f7ee2ec6fd5b044: [[Pasted Image 20240114133824_647.png]]
a4163f5d1f0d710221859ba300f59c3c308617bc: [[Pasted Image 20240114134239_676.png]]
482b24e9634de3085bcfea1f7287258f313aa22a: [[Pasted Image 20240114135329_780.png]]
49d28e029368e7b64ace5e7debee477977ba6b92: [[Pasted Image 20240114135527_817.png]]
5bd18bebabe17f44e79fac15137049ce101f1ab3: [[Pasted Image 20240114135649_855.png]]
38f429ebdc1bee7a904a643079f74ab59d40ef44: [[Pasted Image 20240114135704_880.png]]
5e0cc8bf61778350960895bd502fdebcdfb0a164: [[Pasted Image 20240114135729_435.png]]
9d96a6b671edfc3fc089f36e5426fe14ab7e3226: [[Pasted Image 20240114140554_910.png]]
d50466e58c8f7e2f08ff13f1925de67fee290086: [[Pasted Image 20240114140824_931.png]]
8efa8d4645b982bb3e6743d5fdcee75531689ade: [[Pasted Image 20240114140754_929.png]]
5e234b5ee84521f3a51b58b4b3a1455a447c744b: [[Pasted Image 20240114145633_192.png]]
cfe8f9be84fdd833d8f2436bf4ae8a6002bc5b6c: [[Pasted Image 20240114145742_202.png]]
ded46c190714600c007a13a9b9e89128709bf27f: [[Pasted Image 20240114151304_271.png]]
99b7ce87ee5ff6d49660e14184a5b1d9a5e437cc: [[Pasted Image 20240114153126_361.png]]
e7687db46744e5fc4c9b16e1ffbe325aaf2045e6: [[Pasted Image 20240114153312_374.png]]
83cca31824d8bf6f5d84a972d351c83946fd11f3: [[Pasted Image 20240114153807_404.png]]
e0738bf93a9c61df5858271c5b1f61bb87821e93: [[Pasted Image 20240114154206_424.png]]
b717f066ca2eb2e23c7a360fc605594c7a1f40f2: [[Pasted Image 20240114155720_493.png]]
f854c9168982a068e53af0ad27cbfd58da938ac0: [[Pasted Image 20240114160816_608.png]]
5b30c6f881444c87bdf3541f883d7714cb3d2ddd: [[Pasted Image 20240114162039_698.png]]
30784b82e4d5748453db10016257c16111c8cc99: [[Pasted Image 20240114162137_733.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.14",
	"elements": [
		{
			"type": "image",
			"version": 247,
			"versionNonce": 1466364343,
			"isDeleted": false,
			"id": "0C8f5PCb4RsjEaf_D-_YO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.6148200409651,
			"y": 553.8489110857165,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 309,
			"height": 102,
			"seed": 1756366918,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768672,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8efa8d4645b982bb3e6743d5fdcee75531689ade",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 434,
			"versionNonce": 1812162873,
			"isDeleted": false,
			"id": "m_sJCvvHv-jPHN9X8wPgS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -10.911214815334006,
			"y": -638.4117182083718,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 170.79039339826198,
			"height": 170.79039339826198,
			"seed": 1546008986,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c0094550dc71545262f63ce6a425c12bc3893c9e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 263,
			"versionNonce": 1462608599,
			"isDeleted": false,
			"id": "47k9kl8zEqgvYf717JVNt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1666.8224454024594,
			"y": 192.32788787449647,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 319.0785175956024,
			"height": 123.12268885482486,
			"seed": 1057302810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e0cc8bf61778350960895bd502fdebcdfb0a164",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 151,
			"versionNonce": 907270681,
			"isDeleted": false,
			"id": "SSoiXlcXnKdbop41edLXL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.18987681451887,
			"y": -494.8166120542479,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 399.3633147957681,
			"height": 57.05190211368114,
			"seed": 1227037062,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1229008887,
			"isDeleted": false,
			"id": "IIQAHb7n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -111.17439723675432,
			"y": -482.8011324764834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 370.49761962890625,
			"height": 35,
			"seed": 1190317638,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Recurrent Neural Networks",
			"rawText": "Recurrent Neural Networks",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recurrent Neural Networks",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1252208377,
			"isDeleted": false,
			"id": "fanhF9TY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -244.2955021686771,
			"y": -429.7619782503731,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 607.3993530273438,
			"height": 50,
			"seed": 2131193670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "To Dive deeper into RNN technology, we first need to explain\na few concepts",
			"rawText": "To Dive deeper into RNN technology, we first need to explain\na few concepts",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To Dive deeper into RNN technology, we first need to explain\na few concepts",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 128325911,
			"isDeleted": false,
			"id": "3rMf77Mc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -228.3180259513655,
			"y": -329.58303495242956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 196.49977111816406,
			"height": 25,
			"seed": 849658758,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Stateless Predictor",
			"rawText": "Stateless Predictor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Stateless Predictor",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 1077209049,
			"isDeleted": false,
			"id": "2MbfN8T0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 176.83528280636241,
			"y": -329.5830351210733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 184.91978454589844,
			"height": 25,
			"seed": 1456170650,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Stateful Predictor",
			"rawText": "Stateful Predictor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Stateful Predictor",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 132,
			"versionNonce": 936435255,
			"isDeleted": false,
			"id": "xO52lTlR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 58.20616019408696,
			"y": -277.0830348805963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 27.97998046875,
			"height": 25,
			"seed": 1489691098,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 293,
			"versionNonce": 282887353,
			"isDeleted": false,
			"id": "j1lpYzW4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -310.8374993276223,
			"y": -304.58303513362216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 348.752685546875,
			"height": 80,
			"seed": 1794064006,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A stateless predictor is a predictor that\nsolely relies on the input in order to provide\nan output, in other words its a function\nof the input.",
			"rawText": "A stateless predictor is a predictor that\nsolely relies on the input in order to provide\nan output, in other words its a function\nof the input.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A stateless predictor is a predictor that\nsolely relies on the input in order to provide\nan output, in other words its a function\nof the input.",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 302,
			"versionNonce": 1554382679,
			"isDeleted": false,
			"id": "Ut4J6o6X",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 106.47711522760498,
			"y": -304.58303518562263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 323.1687316894531,
			"height": 80,
			"seed": 1582305306,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A stateful predictor is a predictor that\nrequires an input alongside the current\nstate of the machine, and will output a\nresult and an update to the state",
			"rawText": "A stateful predictor is a predictor that\nrequires an input alongside the current\nstate of the machine, and will output a\nresult and an update to the state",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A stateful predictor is a predictor that\nrequires an input alongside the current\nstate of the machine, and will output a\nresult and an update to the state",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 65,
			"versionNonce": 675120537,
			"isDeleted": false,
			"id": "KzooWwYe9ARcyvxClmEOK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -272.961157122665,
			"y": -224.58303476749822,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 273,
			"height": 65,
			"seed": 1062160070,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "56043ece3989636c2b8bb1d1e1f6602268800ea7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 80,
			"versionNonce": 679083127,
			"isDeleted": false,
			"id": "Mc1KTwSS-YyIE_GVxegg0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136.17343786792972,
			"y": -224.58303512018793,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 270,
			"height": 155,
			"seed": 552715142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DxLRQhxf6KvpusKzW7C-R",
					"type": "arrow"
				}
			],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e8e4f75b66398207b8988a8164e847fa7baa2683",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 78,
			"versionNonce": 831220345,
			"isDeleted": false,
			"id": "DQ7B7ODwb5SO7RpzZHNJG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.72911491766843,
			"y": -142.827304068035,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 0,
			"height": 59.12116729120055,
			"seed": 956457370,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "fVQDkTrO",
				"focus": -0.005744894675721899,
				"gap": 4.07732188215175
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
					59.12116729120055
				]
			]
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 252794263,
			"isDeleted": false,
			"id": "fVQDkTrO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -315.1421880115836,
			"y": -79.6288148946827,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 354.86480712890625,
			"height": 60,
			"seed": 1179935174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DQ7B7ODwb5SO7RpzZHNJG",
					"type": "arrow"
				}
			],
			"updated": 1705343768673,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "So far we have only been dealing\nwith stateless predictors like the multi-layer\nperceptron and CNNs",
			"rawText": "So far we have only been dealing\nwith stateless predictors like the multi-layer\nperceptron and CNNs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So far we have only been dealing\nwith stateless predictors like the multi-layer\nperceptron and CNNs",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 72,
			"versionNonce": 629781337,
			"isDeleted": false,
			"id": "DxLRQhxf6KvpusKzW7C-R",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 265.9670289885247,
			"y": -59.85500749013329,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 0,
			"height": 69.8326656803863,
			"seed": 359272090,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Mc1KTwSS-YyIE_GVxegg0",
				"focus": 0.03856599169929621,
				"gap": 9.72802763005464
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
					69.8326656803863
				]
			]
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 396397239,
			"isDeleted": false,
			"id": "cGXqzSx9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 73.39755271207014,
			"y": 21.61643580365069,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 367.6807861328125,
			"height": 80,
			"seed": 128630470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ngwkmef4XSI0WvPzMwmbW",
					"type": "arrow"
				}
			],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We are currently intrested in modelling things\nusing a stateful predictor in order to try and\nfind a more optimal way of calculating events\nin a time series",
			"rawText": "We are currently intrested in modelling things\nusing a stateful predictor in order to try and\nfind a more optimal way of calculating events\nin a time series",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We are currently intrested in modelling things\nusing a stateful predictor in order to try and\nfind a more optimal way of calculating events\nin a time series",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 293,
			"versionNonce": 411820089,
			"isDeleted": false,
			"id": "ngwkmef4XSI0WvPzMwmbW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 457.71561895298123,
			"y": 50.739662989965154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 410.250626155042,
			"height": 441.36513993646383,
			"seed": 252427334,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cGXqzSx9",
				"focus": 0.2680669155540863,
				"gap": 16.637280108098594
			},
			"endBinding": {
				"elementId": "lq6hR5NTeOO8n_DXyO_83",
				"focus": 0.7959827323340606,
				"gap": 3.193290291518565
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
					209.73487067476867,
					-29.96212438210989
				],
				[
					197.0585872823376,
					-409.0982367557302
				],
				[
					410.250626155042,
					-441.36513993646383
				]
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 1858870231,
			"isDeleted": false,
			"id": "ItYmHqZo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 709.7944268506973,
			"y": -444.43347708870544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 124.75225830078125,
			"height": 40,
			"seed": 836590918,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets take some\nexample",
			"rawText": "Lets take some\nexample",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take some\nexample",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 108,
			"versionNonce": 1215656217,
			"isDeleted": false,
			"id": "lq6hR5NTeOO8n_DXyO_83",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 871.1595353995419,
			"y": -443.1309905176721,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 595.2363629617564,
			"height": 419.8886201467484,
			"seed": 1321485786,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "ngwkmef4XSI0WvPzMwmbW",
					"type": "arrow"
				},
				{
					"id": "BBSW0K5QE-V_7yC2e8Snd",
					"type": "arrow"
				}
			],
			"updated": 1705343768674,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 950569207,
			"isDeleted": false,
			"id": "rhPktFzp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1094.7677912053696,
			"y": -424.27721069233854,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 148.0198516845703,
			"height": 25,
			"seed": 664068870,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Moving Average",
			"rawText": "Moving Average",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Moving Average",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 152,
			"versionNonce": 1790567929,
			"isDeleted": false,
			"id": "7kz5Jbaek-JlbrLaH9FYK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 999.6092206034,
			"y": -376.78277321892176,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 338.3369929247197,
			"height": 30.148840953687895,
			"seed": 300168326,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4617d8f3e5634f01d0c69d88d0d2a0ea09f97ab4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 225,
			"versionNonce": 582636055,
			"isDeleted": false,
			"id": "ZnuRzDrB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 886.7107586054042,
			"y": -332.4432043269857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 562.1771240234375,
			"height": 40,
			"seed": 1553549126,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Consider a sliding window over a time series, we are trying to find the \naverage of the values in this window over an infinite horizon",
			"rawText": "Consider a sliding window over a time series, we are trying to find the \naverage of the values in this window over an infinite horizon",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider a sliding window over a time series, we are trying to find the \naverage of the values in this window over an infinite horizon",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 236,
			"versionNonce": 979156697,
			"isDeleted": false,
			"id": "WkLPrjUO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 877.8962708231691,
			"y": -289.2850104985116,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 568.78515625,
			"height": 40,
			"seed": 1797060762,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "In a stateless model this calculation needs to be done from the start\nof the input until our windows end with redundant calculations.",
			"rawText": "In a stateless model this calculation needs to be done from the start\nof the input until our windows end with redundant calculations.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In a stateless model this calculation needs to be done from the start\nof the input until our windows end with redundant calculations.",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 905312055,
			"isDeleted": false,
			"id": "KpywrPT3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1022.6574167941367,
			"y": -218.46974080211257,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 292.2406005859375,
			"height": 20,
			"seed": 180044614,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Consider the following stateful model",
			"rawText": "Consider the following stateful model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider the following stateful model",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 98,
			"versionNonce": 1173453753,
			"isDeleted": false,
			"id": "_wiFcchalzKqVQHWFsGZI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1021.2777167166083,
			"y": -189.02321863573093,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 295,
			"height": 75,
			"seed": 592435738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8b948909b72010b2665e7d416ac6e02f8d69d655",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 1757411415,
			"isDeleted": false,
			"id": "ZzMCeCe1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 992.7270264060447,
			"y": -114.02321918461516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 365.8887939453125,
			"height": 40,
			"seed": 68575430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "such that ht indicates the state at stage t\nand yt indicates the output at stage t",
			"rawText": "such that ht indicates the state at stage t\nand yt indicates the output at stage t",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "such that ht indicates the state at stage t\nand yt indicates the output at stage t",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 132,
			"versionNonce": 2107350169,
			"isDeleted": false,
			"id": "FCbqgX5T",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 891.4483336020439,
			"y": -70.30554973349945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 555.2330932617188,
			"height": 40,
			"seed": 2130397466,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This has potentially less parameters to tune, one only needs to input\nthe initial state h0",
			"rawText": "This has potentially less parameters to tune, one only needs to input\nthe initial state h0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This has potentially less parameters to tune, one only needs to input\nthe initial state h0",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 433,
			"versionNonce": 1894569335,
			"isDeleted": false,
			"id": "K8RMArc8jw7baN41ZkZbm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1528.74352281231,
			"y": -443.1309901266611,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 595.2363629617564,
			"height": 758.5815667835524,
			"seed": 2106311558,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 17736057,
			"isDeleted": false,
			"id": "KOihc72v",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1779.0417581713602,
			"y": -424.2772103013276,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 94.639892578125,
			"height": 25,
			"seed": 798319302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Oscillator",
			"rawText": "Oscillator",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Oscillator",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 136,
			"versionNonce": 1438715543,
			"isDeleted": false,
			"id": "SmZ2PO1hRhoaX2R8Fe4Pj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1675.2491972821263,
			"y": -391.46160379902636,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 302.225013812455,
			"height": 79.01839983775778,
			"seed": 182018182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "453bef5dca6d10db66a4c5e2cd01527060e70e09",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 764283481,
			"isDeleted": false,
			"id": "xD5PYoWA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1567.6331574304309,
			"y": -309.2850103689779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 517.4570922851562,
			"height": 40,
			"seed": 734655706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768674,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A harmonic oscillator lets a particle accelerate in a way that is\nproportional but of opposite sign to its offset from the origin",
			"rawText": "A harmonic oscillator lets a particle accelerate in a way that is\nproportional but of opposite sign to its offset from the origin",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A harmonic oscillator lets a particle accelerate in a way that is\nproportional but of opposite sign to its offset from the origin",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 230,
			"versionNonce": 1106322359,
			"isDeleted": false,
			"id": "uDpvm-TCerPQVVlYIFNkQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1663.2252676247715,
			"y": -254.92109654037154,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 173.1258719439088,
			"height": 21.73441682412708,
			"seed": 1865078234,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3ebb4b45ac10f5f2bcf0d541e3b4caf3ff4514a4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 513,
			"versionNonce": 1810716473,
			"isDeleted": false,
			"id": "LpLP3FhdG75BtkjBjGWWm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1862.3636567992555,
			"y": -254.92109700000003,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 97.12567722290491,
			"height": 21.734417280650053,
			"seed": 1491610374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "61b5bd97d95fa4fff7c90e523b2e63bda01cba5f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 362910935,
			"isDeleted": false,
			"id": "74tJhqNd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1700.6814444261306,
			"y": -233.18668006754706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 251.3605194091797,
			"height": 20,
			"seed": 898008602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We define our state accordingly",
			"rawText": "We define our state accordingly",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We define our state accordingly",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 414,
			"versionNonce": 1049626649,
			"isDeleted": false,
			"id": "RgJL5OtxX9DT_iqgSYeTP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1631.5433597554693,
			"y": -198.46974112971316,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 103.90526904231677,
			"height": 56.45246900724297,
			"seed": 417760090,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "J3f78BskPadoVplk6mP2D",
					"type": "arrow"
				}
			],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cf9987ab3023ec24ca40ebd16f7ee2ec6fd5b044",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 309,
			"versionNonce": 946266615,
			"isDeleted": false,
			"id": "Bv8uNFbQWopc6sjeb2v2J",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1810.9150559045509,
			"y": -196.83343716181815,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 210.2649932588615,
			"height": 54.816165557757664,
			"seed": 2108627162,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a4163f5d1f0d710221859ba300f59c3c308617bc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 330,
			"versionNonce": 258579705,
			"isDeleted": false,
			"id": "J3f78BskPadoVplk6mP2D",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1740.488457304239,
			"y": -171.37170265362766,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 68.50736925937417,
			"height": 0.9678752724861965,
			"seed": 155655962,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RgJL5OtxX9DT_iqgSYeTP",
				"focus": -0.06672954269011909,
				"gap": 5.039828506452977
			},
			"endBinding": {
				"elementId": "uSQkxZT-9wf88Nt4TRL5Q",
				"focus": 1.3861401551643204,
				"gap": 28.38655493787101
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
					68.50736925937417,
					0.9678752724861965
				]
			]
		},
		{
			"type": "image",
			"version": 168,
			"versionNonce": 725977879,
			"isDeleted": false,
			"id": "uSQkxZT-9wf88Nt4TRL5Q",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1625.8272214569479,
			"y": -142.01727244327046,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 370.17566972865825,
			"height": 128.1129709147878,
			"seed": 434720794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "J3f78BskPadoVplk6mP2D",
					"type": "arrow"
				}
			],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "482b24e9634de3085bcfea1f7287258f313aa22a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 1040029145,
			"isDeleted": false,
			"id": "v4ux9k9u",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1543.0861479058976,
			"y": 17.390972215202737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 569.953125,
			"height": 20,
			"seed": 1918108486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "It is often useful to be able to model applied force to such oscillation",
			"rawText": "It is often useful to be able to model applied force to such oscillation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "It is often useful to be able to model applied force to such oscillation",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 1521618999,
			"isDeleted": false,
			"id": "LcwB6wmb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1625.8619954201727,
			"y": -13.904302107675441,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 400.7220764160156,
			"height": 14.267569100343282,
			"seed": 317893318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 11.414055280274626,
			"fontFamily": 1,
			"text": "note that this is an approximation therefore its not entirely accurate",
			"rawText": "note that this is an approximation therefore its not entirely accurate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "note that this is an approximation therefore its not entirely accurate",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "image",
			"version": 152,
			"versionNonce": 1834971833,
			"isDeleted": false,
			"id": "lSeZlvrRhapgQU7Uu-sSv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1687.0601175720194,
			"y": 50.402008302008,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 251.31422077574004,
			"height": 51.97756804956671,
			"seed": 2121641862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "49d28e029368e7b64ace5e7debee477977ba6b92",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 814805335,
			"isDeleted": false,
			"id": "V8gUfZ4C",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1940.005817200171,
			"y": 64.16040869133212,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 161.71299743652344,
			"height": 25.603868468750754,
			"seed": 1396621318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 10.241547387500301,
			"fontFamily": 1,
			"text": "such that x1 can be interpreted\nas the force applied at time t",
			"rawText": "such that x1 can be interpreted\nas the force applied at time t",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "such that x1 can be interpreted\nas the force applied at time t",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "arrow",
			"version": 191,
			"versionNonce": 305312665,
			"isDeleted": false,
			"id": "HbHJ6NBcgp5Xk88eL5Vpf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1826.3617036357284,
			"y": 113.50327459857203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.3942651961219781,
			"height": 29.175624513027543,
			"seed": 2068960154,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
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
					-0.3942651961219781,
					29.175624513027543
				]
			]
		},
		{
			"type": "image",
			"version": 111,
			"versionNonce": 1714859639,
			"isDeleted": false,
			"id": "oIzX-IZDdWR5mQnlSTG7A",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1606.4127659664653,
			"y": 143.08171535979452,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188.53735652405942,
			"height": 44.26529240130091,
			"seed": 1442459718,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5bd18bebabe17f44e79fac15137049ce101f1ab3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 139,
			"versionNonce": 1084938361,
			"isDeleted": false,
			"id": "NQHKtRDV0rKZyVdMAV9LZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1851.9048729293543,
			"y": 153.56141884887552,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 220.2676770110626,
			"height": 27.90453051083542,
			"seed": 1453607450,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "38f429ebdc1bee7a904a643079f74ab59d40ef44",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 257,
			"versionNonce": 375900055,
			"isDeleted": false,
			"id": "BBSW0K5QE-V_7yC2e8Snd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1468.8984577386796,
			"y": -399.5847991678075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.622713083171675,
			"height": 304.9007505852796,
			"seed": 237552006,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "lq6hR5NTeOO8n_DXyO_83",
				"focus": -0.9094663857720515,
				"gap": 2.502559377381317
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
					30.798055614674695,
					25.665046345562303
				],
				[
					29.771453760852182,
					275.1292968244273
				],
				[
					62.622713083171675,
					304.9007505852796
				]
			]
		},
		{
			"type": "arrow",
			"version": 336,
			"versionNonce": 982212953,
			"isDeleted": false,
			"id": "rzaR9y-CX3WmBT67cnQw2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 273.5811335847953,
			"y": 113.02534756575183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 214.17695924465556,
			"height": 183.0167563463358,
			"seed": 742382854,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
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
					-24.10093503367125,
					84.35327261784914
				],
				[
					-195.2169775650476,
					85.42549040916049
				],
				[
					-214.17695924465556,
					183.0167563463358
				]
			]
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 257473719,
			"isDeleted": false,
			"id": "3LkTcVMJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -142.6762961572067,
			"y": 307.90353853466297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 402.921630859375,
			"height": 35,
			"seed": 1164623174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Building and Generalizing RNN",
			"rawText": "Building and Generalizing RNN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Building and Generalizing RNN",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 69,
			"versionNonce": 1026018873,
			"isDeleted": false,
			"id": "lOB1eFS9WxSXTm27xz6fH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -137.04975704625923,
			"y": 357.8499680519053,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 377,
			"height": 97,
			"seed": 1868858182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9d96a6b671edfc3fc089f36e5426fe14ab7e3226",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 220,
			"versionNonce": 1689128407,
			"isDeleted": false,
			"id": "mVkvqof3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -331.56705367610294,
			"y": 469.2206554157094,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 742.579345703125,
			"height": 100,
			"seed": 1505084422,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Is the general equation for a staetful model such that the paremeters\nA B C D are parameters that we need to learn to minimize the divergence\nbetween y and the ground truth\n",
			"rawText": "Is the general equation for a staetful model such that the paremeters\nA B C D are parameters that we need to learn to minimize the divergence\nbetween y and the ground truth\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Is the general equation for a staetful model such that the paremeters\nA B C D are parameters that we need to learn to minimize the divergence\nbetween y and the ground truth\n",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 103,
			"versionNonce": 258187033,
			"isDeleted": false,
			"id": "woL_k-hnDmLgTaSN6qe2r",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -349.83148444404037,
			"y": 569.2206548786168,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 779.1082061915818,
			"height": 278.6591394407847,
			"seed": 1892244250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "idWiFXBWmtBeb6w1LIBtG",
					"type": "arrow"
				},
				{
					"id": "XksYOUigITKVM7sEvfg1Q",
					"type": "arrow"
				},
				{
					"id": "p5ZTP8sgoQekA56-BE98Q",
					"type": "arrow"
				}
			],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d50466e58c8f7e2f08ff13f1925de67fee290086",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 312,
			"versionNonce": 1098660599,
			"isDeleted": false,
			"id": "1xZOx2xGRaDM25Ofd36Nf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -236.81585771951168,
			"y": 657.8096166498032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 108.93054212613268,
			"height": 58.076228260617654,
			"seed": 999902662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
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
					-0.6018261995919261,
					-58.076228260617654
				],
				[
					-87.56571204062047,
					-57.474402061025785
				],
				[
					-108.93054212613268,
					-57.474402061025785
				]
			]
		},
		{
			"type": "text",
			"version": 364,
			"versionNonce": 1337086969,
			"isDeleted": false,
			"id": "xWcJ5o6O",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.5504281160557,
			"y": 847.8797936721154,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 750.0013427734375,
			"height": 60,
			"seed": 315894918,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This can be seen a a big Neural network composed of sub neural networks each with their own\noutputs and inputs, those sub neural networks have shared parameters theta between us\nif each NN has depth of L, the entire network's depth is LT",
			"rawText": "This can be seen a a big Neural network composed of sub neural networks each with their own\noutputs and inputs, those sub neural networks have shared parameters theta between us\nif each NN has depth of L, the entire network's depth is LT",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This can be seen a a big Neural network composed of sub neural networks each with their own\noutputs and inputs, those sub neural networks have shared parameters theta between us\nif each NN has depth of L, the entire network's depth is LT",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 676,
			"versionNonce": 2051523607,
			"isDeleted": false,
			"id": "idWiFXBWmtBeb6w1LIBtG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 451.4645631097943,
			"y": 667.5736742843766,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 302.92523707613134,
			"height": 162.04865348037822,
			"seed": 1149308038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "woL_k-hnDmLgTaSN6qe2r",
				"focus": -0.028541894942123003,
				"gap": 22.187841362252925
			},
			"endBinding": {
				"elementId": "giNHjAmvN9m1rpUvnxtkw",
				"focus": -0.23601926147456453,
				"gap": 16.710810973182788
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
					272.5634225921682,
					-23.848991151912173
				],
				[
					302.92523707613134,
					-162.04865348037822
				]
			]
		},
		{
			"type": "arrow",
			"version": 220,
			"versionNonce": 35089625,
			"isDeleted": false,
			"id": "XksYOUigITKVM7sEvfg1Q",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 451.26773529990294,
			"y": 668.4980415922226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 315.4828917366434,
			"height": 144.45187350578897,
			"seed": 1248614534,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "woL_k-hnDmLgTaSN6qe2r",
				"focus": -0.39377177132504954,
				"gap": 21.99101355236155
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
					281.9700570833003,
					16.17860983264825
				],
				[
					315.4828917366434,
					144.45187350578897
				]
			]
		},
		{
			"type": "image",
			"version": 188,
			"versionNonce": 1594173751,
			"isDeleted": false,
			"id": "giNHjAmvN9m1rpUvnxtkw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 588.886754886057,
			"y": 314.8075930943554,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 297.36951666156256,
			"height": 174.0066167364602,
			"seed": 1168806554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "idWiFXBWmtBeb6w1LIBtG",
					"type": "arrow"
				}
			],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e234b5ee84521f3a51b58b4b3a1455a447c744b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 66,
			"versionNonce": 1579575737,
			"isDeleted": false,
			"id": "GFUamAqW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 651.3984152086392,
			"y": 286.9394093461847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.19979858398438,
			"height": 25,
			"seed": 1163033670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Unidirectional RNN:",
			"rawText": "Unidirectional RNN:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Unidirectional RNN:",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 1293478487,
			"isDeleted": false,
			"id": "9a6wvMojqiKb-KsTomNJw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 618.4512287062084,
			"y": 881.7133801252121,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 296.0164930314372,
			"height": 224.88631630786372,
			"seed": 280361478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cfe8f9be84fdd833d8f2436bf4ae8a6002bc5b6c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 43,
			"versionNonce": 1560464025,
			"isDeleted": false,
			"id": "7OGIgW9E",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 680.1431891091246,
			"y": 842.8573882232265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 173.11981201171875,
			"height": 25,
			"seed": 1502086342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bidirectional RNN:",
			"rawText": "Bidirectional RNN:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bidirectional RNN:",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 22513527,
			"isDeleted": false,
			"id": "ETxKsPi3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 882.5036122939914,
			"y": 305.55834205023126,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 275.29656982421875,
			"height": 160,
			"seed": 1035620998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Generate the output at the same\ntime as the input is received\nenable a strong coupling between\nthe two sequences.\nBUT\nCannot use information about\nlater time steps when generating\nthe output sequence",
			"rawText": "Generate the output at the same\ntime as the input is received\nenable a strong coupling between\nthe two sequences.\nBUT\nCannot use information about\nlater time steps when generating\nthe output sequence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generate the output at the same\ntime as the input is received\nenable a strong coupling between\nthe two sequences.\nBUT\nCannot use information about\nlater time steps when generating\nthe output sequence",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 123735929,
			"isDeleted": false,
			"id": "Fpwuax6G",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 930.3648526495922,
			"y": 946.3163380438737,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 261.2005615234375,
			"height": 80,
			"seed": 178216602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Add a RNN in reverse direction\nin order to incorporate\ninformation from future values in\nthe sequence",
			"rawText": "Add a RNN in reverse direction\nin order to incorporate\ninformation from future values in\nthe sequence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Add a RNN in reverse direction\nin order to incorporate\ninformation from future values in\nthe sequence",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 163,
			"versionNonce": 705003671,
			"isDeleted": false,
			"id": "p5ZTP8sgoQekA56-BE98Q",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 448.38093727171326,
			"y": 668.246264743847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 611.0952716429588,
			"height": 7.2750056213868675,
			"seed": 1904875866,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "woL_k-hnDmLgTaSN6qe2r",
				"focus": -0.24615988086222226,
				"gap": 19.104215524171877
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
					611.0952716429588,
					-7.2750056213868675
				]
			]
		},
		{
			"type": "image",
			"version": 118,
			"versionNonce": 58832985,
			"isDeleted": false,
			"id": "pdlZTVM9iytgjZSnFOHmY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1088.3081285528986,
			"y": 603.9148282809449,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 407.29305330273814,
			"height": 106.62624744482059,
			"seed": 1159118214,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768675,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ded46c190714600c007a13a9b9e89128709bf27f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 953636279,
			"isDeleted": false,
			"id": "5w8dDvCt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1194.688919564054,
			"y": 569.2632120447819,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.4998321533203,
			"height": 25,
			"seed": 1165479174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Encoder-Decoder:",
			"rawText": "Encoder-Decoder:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Encoder-Decoder:",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 465,
			"versionNonce": 1664828729,
			"isDeleted": false,
			"id": "1YBrWLvw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 990.6962473769086,
			"y": 733.9616467856207,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 609.0252685546875,
			"height": 120,
			"seed": 298772998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is required sometimes for reading and writing model, such that\nyou need to read the entire model and process it and produce your own\noutput after youve seen the entire model!\ne.g Chatbot\nNote that RNN's have quite a short term memory and cannot connect things\nglobally thus transformers are much better for this task",
			"rawText": "This is required sometimes for reading and writing model, such that\nyou need to read the entire model and process it and produce your own\noutput after youve seen the entire model!\ne.g Chatbot\nNote that RNN's have quite a short term memory and cannot connect things\nglobally thus transformers are much better for this task",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is required sometimes for reading and writing model, such that\nyou need to read the entire model and process it and produce your own\noutput after youve seen the entire model!\ne.g Chatbot\nNote that RNN's have quite a short term memory and cannot connect things\nglobally thus transformers are much better for this task",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 193,
			"versionNonce": 1961985751,
			"isDeleted": false,
			"id": "vQSspEj2nQrKyItu-KYtT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1292.94569415357,
			"y": 682.1353257294804,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 324.1441549576234,
			"height": 33.26010174631233,
			"seed": 674158106,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
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
					33.848681668141126,
					30.406442854431816
				],
				[
					324.1441549576234,
					33.26010174631233
				]
			]
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 837826073,
			"isDeleted": false,
			"id": "I3BToJj4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1593.2225514094132,
			"y": 683.2827386673835,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 169.36036682128906,
			"height": 40,
			"seed": 1590958726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Global representation\nof y",
			"rawText": "Global representation\nof y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Global representation\nof y",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 1290310647,
			"isDeleted": false,
			"id": "rvOLviuY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -361.7567109499746,
			"y": 703.2543499075032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.09614562988281,
			"height": 35,
			"seed": 1451345542,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "h0",
			"rawText": "h0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h0",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 83,
			"versionNonce": 1116998393,
			"isDeleted": false,
			"id": "iRpUJ-82qD3TgG4611yQL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -401.1487968662226,
			"y": 725.427244509549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 508.4903317921222,
			"height": 1.8626019479564775,
			"seed": 1450587098,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
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
					-508.4903317921222,
					-1.8626019479564775
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 1757478167,
			"isDeleted": false,
			"id": "iwszsNzt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -773.2364307380723,
			"y": 691.3126036024628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 231.95973205566406,
			"height": 25,
			"seed": 1229755078,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we initialize h0?",
			"rawText": "How do we initialize h0?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we initialize h0?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 1034568665,
			"isDeleted": false,
			"id": "II47Apm9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1647.6849110608528,
			"y": 700.4926853905232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 740.2590942382812,
			"height": 325,
			"seed": 918218246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Unlike the input data, the RNN's initial state (at time t = 0) is not\ngiven and must be initialized to some value:\n\n\n1) Set it to some arbitrary value (e.g. h0 = 0)\nthis is often not ideal\n\n2) Set it at random (the RNN will then learn to desensitize itself to the\ninitial state, because we are giving it randomized noise data in each\niteration of training with the same result)\n\n3) Use one of the two approaches above and simulate the RNN for a few\ntime steps in order to generate an initial state that is more plausible",
			"rawText": "Unlike the input data, the RNN's initial state (at time t = 0) is not\ngiven and must be initialized to some value:\n\n\n1) Set it to some arbitrary value (e.g. h0 = 0)\nthis is often not ideal\n\n2) Set it at random (the RNN will then learn to desensitize itself to the\ninitial state, because we are giving it randomized noise data in each\niteration of training with the same result)\n\n3) Use one of the two approaches above and simulate the RNN for a few\ntime steps in order to generate an initial state that is more plausible",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Unlike the input data, the RNN's initial state (at time t = 0) is not\ngiven and must be initialized to some value:\n\n\n1) Set it to some arbitrary value (e.g. h0 = 0)\nthis is often not ideal\n\n2) Set it at random (the RNN will then learn to desensitize itself to the\ninitial state, because we are giving it randomized noise data in each\niteration of training with the same result)\n\n3) Use one of the two approaches above and simulate the RNN for a few\ntime steps in order to generate an initial state that is more plausible",
			"lineHeight": 1.25,
			"baseline": 318
		},
		{
			"type": "arrow",
			"version": 89,
			"versionNonce": 2079277623,
			"isDeleted": false,
			"id": "mGxQ1PfXifFj5RCVJbtGw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 54.70527283626291,
			"y": 927.061150882283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.4299353678125044,
			"height": 283.0874703501514,
			"seed": 1793643098,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
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
					2.4299353678125044,
					283.0874703501514
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1866883257,
			"isDeleted": false,
			"id": "EVUrGEBS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -183.90456217224062,
			"y": 1233.4980439284238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 506.35406494140625,
			"height": 35,
			"seed": 520001370,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Training RNNs... and why its difficult",
			"rawText": "Training RNNs... and why its difficult",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Training RNNs... and why its difficult",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 46,
			"versionNonce": 1465377623,
			"isDeleted": false,
			"id": "v5cn5AU8AO9zPiGZ11z3C",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -290.7374523782767,
			"y": 1288.7026392404487,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 697,
			"height": 224,
			"seed": 1342490522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "99b7ce87ee5ff6d49660e14184a5b1d9a5e437cc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 123,
			"versionNonce": 1426842009,
			"isDeleted": false,
			"id": "6bghgXfZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -320.52712150513554,
			"y": 1513.3299779088982,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 779.5991821289062,
			"height": 25,
			"seed": 8851334,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The error of the entire model can be expressed as individual errors of sub-NN",
			"rawText": "The error of the entire model can be expressed as individual errors of sub-NN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The error of the entire model can be expressed as individual errors of sub-NN",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 82,
			"versionNonce": 995057783,
			"isDeleted": false,
			"id": "uyYlX5uumOZNdRUEpk5rk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -152.2275302008959,
			"y": 1549.979065642959,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 443,
			"height": 63,
			"seed": 1265888262,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e7687db46744e5fc4c9b16e1ffbe325aaf2045e6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 1814972025,
			"isDeleted": false,
			"id": "CleIyG0v",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -303.05442872182357,
			"y": 1624.6281537162024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 720.3792724609375,
			"height": 50,
			"seed": 1354888838,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And the Gradient w.r.t to the parameter theta (which is shared) can be\nexpressed via the chain rule:",
			"rawText": "And the Gradient w.r.t to the parameter theta (which is shared) can be\nexpressed via the chain rule:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And the Gradient w.r.t to the parameter theta (which is shared) can be\nexpressed via the chain rule:",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 64,
			"versionNonce": 1771714967,
			"isDeleted": false,
			"id": "9i603o4K1Pj44RH94Qbu_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -233.2275300360999,
			"y": 1686.2772417618405,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 605,
			"height": 115,
			"seed": 98116442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "83cca31824d8bf6f5d84a972d351c83946fd11f3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 60,
			"versionNonce": 1064374105,
			"isDeleted": false,
			"id": "CIecG-MDVc5qp0K6dbcwV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -41.46822415074405,
			"y": 1800.838708993493,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.5177620229706861,
			"height": 62.64920477945361,
			"seed": 837853382,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5177620229706861,
					62.64920477945361
				]
			]
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 2003627703,
			"isDeleted": false,
			"id": "hPc1qd07",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -106.03635464390811,
			"y": 1870.218820071566,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 129.13626098632812,
			"height": 40,
			"seed": 981987034,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "error gradient\nw.r.t the output",
			"rawText": "error gradient\nw.r.t the output",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "error gradient\nw.r.t the output",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 33,
			"versionNonce": 891796537,
			"isDeleted": false,
			"id": "3FInXILZ26Azh1eKPvcQv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 69.26842821003129,
			"y": 1794.1535661980763,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 22.469760803539657,
			"height": 52.7550905822236,
			"seed": 1491675738,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					22.469760803539657,
					52.7550905822236
				]
			]
		},
		{
			"type": "text",
			"version": 71,
			"versionNonce": 1600913367,
			"isDeleted": false,
			"id": "R5LbjERg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 37.88023484587268,
			"y": 1849.3510220850326,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 137.0242919921875,
			"height": 40,
			"seed": 437896218,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Direct derivative\nof yt w.r.t theta",
			"rawText": "Direct derivative\nof yt w.r.t theta",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Direct derivative\nof yt w.r.t theta",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 46,
			"versionNonce": 490065177,
			"isDeleted": false,
			"id": "SgT7STZJvJgXI19W6DeJc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 249.0265146383487,
			"y": 1801.480662112274,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 31.262275900576896,
			"height": 66.43233628872599,
			"seed": 1254258010,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					31.262275900576896,
					66.43233628872599
				]
			]
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 1403776247,
			"isDeleted": false,
			"id": "zCDoX4oC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 223.75410594486755,
			"y": 1868.4014714619466,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 132.60829162597656,
			"height": 60,
			"seed": 811631834,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Derivative of yt\nw.r.t theta using\nprevious stages",
			"rawText": "Derivative of yt\nw.r.t theta using\nprevious stages",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Derivative of yt\nw.r.t theta using\nprevious stages",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 46,
			"versionNonce": 2131673593,
			"isDeleted": false,
			"id": "VVXLgeUJZwW6F9YSxqkeW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 368.6136784287063,
			"y": 1745.9233602430277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 178.74843283691064,
			"height": 0,
			"seed": 1370531846,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "vXHgBfy5WHn0pILEFjRz5",
				"focus": 0.10683028498500634,
				"gap": 26.69833347482904
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
					178.74843283691064,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 44,
			"versionNonce": 1337013783,
			"isDeleted": false,
			"id": "vXHgBfy5WHn0pILEFjRz5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 574.060444740446,
			"y": 1661.9654070316183,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 519,
			"height": 188,
			"seed": 266664262,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VVXLgeUJZwW6F9YSxqkeW",
					"type": "arrow"
				}
			],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0738bf93a9c61df5858271c5b1f61bb87821e93",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 46,
			"versionNonce": 666245849,
			"isDeleted": false,
			"id": "1fbWjZ-8Tlgebp1uoTXMN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1030.4277254648377,
			"y": 1663.8282180088993,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 32.619478396550676,
			"height": 89.70356559051402,
			"seed": 1044150534,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.619478396550676,
					-89.70356559051402
				]
			]
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 1785748279,
			"isDeleted": false,
			"id": "AXj5rs9E",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 968.5051595561533,
			"y": 1524.3885106046807,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 194.6884307861328,
			"height": 40,
			"seed": 542670470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Direct derivative of Hs-1\nw.r.t theta",
			"rawText": "Direct derivative of Hs-1\nw.r.t theta",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Direct derivative of Hs-1\nw.r.t theta",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 37,
			"versionNonce": 2009028537,
			"isDeleted": false,
			"id": "v-7wRahxoKuxyPUmOxAnd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 854.0026149769334,
			"y": 1674.0846438343092,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 10.692580944973429,
			"height": 103.58437790443031,
			"seed": 331480838,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.692580944973429,
					-103.58437790443031
				]
			]
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 1749933143,
			"isDeleted": false,
			"id": "zT5aFyl3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 771.9147269956585,
			"y": 1500.3302034784904,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 184.224365234375,
			"height": 60,
			"seed": 761919322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Matrix describing the\neffect of previous time\nonto the next",
			"rawText": "Matrix describing the\neffect of previous time\nonto the next",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Matrix describing the\neffect of previous time\nonto the next",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "rectangle",
			"version": 773,
			"versionNonce": 1900935321,
			"isDeleted": false,
			"id": "ei_BsJDkOnixwvqOIvLfj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -150.99978160909848,
			"y": 1371.62082806686,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 479.0264631108685,
			"height": 20.901429726249052,
			"seed": 1985088026,
			"groupIds": [
				"ZKLlQkPjikwHuH-4Xyv5C"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 588,
			"versionNonce": 220084599,
			"isDeleted": false,
			"id": "8fAleuoUPe427DWW3hPQa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -148.72143689591977,
			"y": 1399.3572919326457,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 20.505102418610914,
			"height": 36.453515410863844,
			"seed": 1316861658,
			"groupIds": [
				"ZKLlQkPjikwHuH-4Xyv5C"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.505102418610914,
					-18.226757705431922
				],
				[
					0,
					-36.453515410863844
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 102071673,
			"isDeleted": false,
			"id": "9xHbgegV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 211.13075484787652,
			"y": 1348.9021171774057,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 68.04815673828125,
			"height": 20,
			"seed": 123486086,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gradient",
			"rawText": "Gradient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 774238871,
			"isDeleted": false,
			"id": "2xo2sqqa",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 608.2175315470114,
			"y": 1844.566214008225,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 515.968994140625,
			"height": 80,
			"seed": 320686790,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "On one extreme, P corresponding to indices s = 2 and\nt = T features a very large product structure of T − 2 terms\non the other extreme where s = t − 1, the product structure\ntotally vanishes",
			"rawText": "On one extreme, P corresponding to indices s = 2 and\nt = T features a very large product structure of T − 2 terms\non the other extreme where s = t − 1, the product structure\ntotally vanishes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "On one extreme, P corresponding to indices s = 2 and\nt = T features a very large product structure of T − 2 terms\non the other extreme where s = t − 1, the product structure\ntotally vanishes",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 626615897,
			"isDeleted": false,
			"id": "wa7ru7bK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 584.1023587448517,
			"y": 1958.7770153891715,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 564.1993408203125,
			"height": 50,
			"seed": 1302437574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If we compute Pst in closed form and perform eigenvalue\ndecomposition on it by diagonalizing the resulting matrix: ",
			"rawText": "If we compute Pst in closed form and perform eigenvalue\ndecomposition on it by diagonalizing the resulting matrix: ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we compute Pst in closed form and perform eigenvalue\ndecomposition on it by diagonalizing the resulting matrix: ",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 117,
			"versionNonce": 68782007,
			"isDeleted": false,
			"id": "26z7jqLKEgU6ltvTRZwAM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 664.6862227868515,
			"y": 2011.7857391703178,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 393,
			"height": 105,
			"seed": 1658621254,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b717f066ca2eb2e23c7a360fc605594c7a1f40f2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 178,
			"versionNonce": 166540089,
			"isDeleted": false,
			"id": "CRCGNwF6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 760.2722410554786,
			"y": 2184.170232120786,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 189.21645055975273,
			"height": 33.6384800995116,
			"seed": 68522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "91Is8XGGwn1QVX64ZyMqU",
					"type": "arrow"
				}
			],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5bc22cfb4f7f138d5f7ce00f4e5556537fa46528",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 49,
			"versionNonce": 1025341655,
			"isDeleted": false,
			"id": "91Is8XGGwn1QVX64ZyMqU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 857.6585269510274,
			"y": 2113.67348365293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 0.7055392039803792,
			"height": 60.676371542318975,
			"seed": 560956998,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "CRCGNwF6",
				"focus": 0.018593753244025183,
				"gap": 9.82037692553672
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
					-0.7055392039803792,
					60.676371542318975
				]
			]
		},
		{
			"type": "image",
			"version": 89,
			"versionNonce": 1211393049,
			"isDeleted": false,
			"id": "WENNzdrq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 707.5417166624981,
			"y": 2238.524317155005,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 294.4570949683498,
			"height": 33.65223942495426,
			"seed": 15172,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dd5630d63cf3b35a9a8dd9ab6eb60e832a21f06a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 37,
			"versionNonce": 1321616887,
			"isDeleted": false,
			"id": "BtwJ7LNOBJuLMHbmr8CiU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 677.7400381251803,
			"y": 2257.0134414013323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 145.90947939992975,
			"height": 2.069638005672914,
			"seed": 1899649158,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
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
					-145.90947939992975,
					2.069638005672914
				]
			]
		},
		{
			"type": "text",
			"version": 196,
			"versionNonce": 472021241,
			"isDeleted": false,
			"id": "L0ZPXNer",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -267.9132290502174,
			"y": 2216.655500290714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 214.89974975585938,
			"height": 100,
			"seed": 1460712922,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VX8ETu9gltJLZgBR2IMEl",
					"type": "arrow"
				}
			],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If max Eigenvalue > 1\n\n\nIf max Eigenvalue < 1",
			"rawText": "If max Eigenvalue > 1\n\n\nIf max Eigenvalue < 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If max Eigenvalue > 1\n\n\nIf max Eigenvalue < 1",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 211,
			"versionNonce": 135819031,
			"isDeleted": false,
			"id": "VX8ETu9gltJLZgBR2IMEl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -33.18061682341295,
			"y": 2255.978622398496,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 130.38719435738403,
			"height": 0,
			"seed": 2068621830,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "L0ZPXNer",
				"focus": -0.21353755784435635,
				"gap": 19.832862470945088
			},
			"endBinding": {
				"elementId": "brkGfobl",
				"focus": 0.15558769368551292,
				"gap": 8.524381067462741
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
					130.38719435738403,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 2000351705,
			"isDeleted": false,
			"id": "brkGfobl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 105.73095860143383,
			"y": 2203.2028532538407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 392.73956298828125,
			"height": 125,
			"seed": 1167592282,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VX8ETu9gltJLZgBR2IMEl",
					"type": "arrow"
				}
			],
			"updated": 1705343768676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The norm of the matrix D will increase\nand thus the gradient will explode\n\nThe norm of the matrix D will decrease\nand thus the gradient will vanish",
			"rawText": "The norm of the matrix D will increase\nand thus the gradient will explode\n\nThe norm of the matrix D will decrease\nand thus the gradient will vanish",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The norm of the matrix D will increase\nand thus the gradient will explode\n\nThe norm of the matrix D will decrease\nand thus the gradient will vanish",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "rectangle",
			"version": 73,
			"versionNonce": 1669887031,
			"isDeleted": false,
			"id": "SmYv3-mZKlQWJBLXQ-LlZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -297.05946254669004,
			"y": 2176.2975591800946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 812.3329172265591,
			"height": 192.4763345275669,
			"seed": 1001245894,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "ssborpOv8f1Gg4Iz80IPi",
					"type": "arrow"
				}
			],
			"updated": 1705343768677,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 78,
			"versionNonce": 1318145721,
			"isDeleted": false,
			"id": "ssborpOv8f1Gg4Iz80IPi",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -302.2585380323028,
			"y": 2272.363372695783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.7040708611686,
			"height": 0,
			"seed": 1772345222,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "SmYv3-mZKlQWJBLXQ-LlZ",
				"focus": 0.0017909084617419545,
				"gap": 5.199075485612752
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
					-244.7040708611686,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 223,
			"versionNonce": 419091799,
			"isDeleted": false,
			"id": "0TrtsWCg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1176.6980765394253,
			"y": 2240.043967110345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 650.019287109375,
			"height": 75,
			"seed": 621696602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In either cases we are left with a disbalance between\nthe different terms of the gradient!\nBut there are hueristics that can help us overcome these issues",
			"rawText": "In either cases we are left with a disbalance between\nthe different terms of the gradient!\nBut there are hueristics that can help us overcome these issues",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In either cases we are left with a disbalance between\nthe different terms of the gradient!\nBut there are hueristics that can help us overcome these issues",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 86,
			"versionNonce": 684265369,
			"isDeleted": false,
			"id": "OfMqpuU1vPSbrPpycvkaC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -871.8884963701144,
			"y": 2346.537078844488,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 167.11214567403658,
			"seed": 998396614,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
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
					0,
					167.11214567403658
				]
			]
		},
		{
			"type": "text",
			"version": 18,
			"versionNonce": 1875120759,
			"isDeleted": false,
			"id": "rv4jMEtI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1228.3783185629156,
			"y": 2541.2308407948217,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 725.959228515625,
			"height": 75,
			"seed": 1241825370,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Training the RNN with an appropriate level of noise applied to the\nhidden states so that the model has incentive to desentisize itself from\nthe lower layers (thereby avoiding the exploding gradient problem",
			"rawText": "Training the RNN with an appropriate level of noise applied to the\nhidden states so that the model has incentive to desentisize itself from\nthe lower layers (thereby avoiding the exploding gradient problem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Training the RNN with an appropriate level of noise applied to the\nhidden states so that the model has incentive to desentisize itself from\nthe lower layers (thereby avoiding the exploding gradient problem",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 1813361785,
			"isDeleted": false,
			"id": "Hg8i1TwZq6gijW_PtpCCN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -870.2660483538615,
			"y": 2210.2514454792545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 214.1631381453667,
			"seed": 1508586138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
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
					0,
					-214.1631381453667
				]
			]
		},
		{
			"type": "text",
			"version": 45,
			"versionNonce": 1353231255,
			"isDeleted": false,
			"id": "YQeA3rii",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1219.5907934346371,
			"y": 1913.343458504996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 705.1392822265625,
			"height": 50,
			"seed": 1974957658,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Choosing a particular class of functions for the RNN that is shown to\nbe more robust to the vanishing/exploding gradient problem",
			"rawText": "Choosing a particular class of functions for the RNN that is shown to\nbe more robust to the vanishing/exploding gradient problem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Choosing a particular class of functions for the RNN that is shown to\nbe more robust to the vanishing/exploding gradient problem",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 273,
			"versionNonce": 1815788889,
			"isDeleted": false,
			"id": "E4KNvYE63yXINLJkT8G3u",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -876.751050628819,
			"y": 1882.083904249973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 475.72413703160623,
			"height": 574.7708027858207,
			"seed": 2018429574,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
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
					-33.015555251404976,
					-528.2488840224776
				],
				[
					-475.72413703160623,
					-574.7708027858207
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 400367799,
			"isDeleted": false,
			"id": "mcm8r41Z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1895.5966845469532,
			"y": 1287.3060308953327,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 335.88946533203125,
			"height": 35,
			"seed": 826389338,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Long Short-Term Memory",
			"rawText": "Long Short-Term Memory",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Long Short-Term Memory",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 224,
			"versionNonce": 948677177,
			"isDeleted": false,
			"id": "YMkPojxQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2057.4859255528345,
			"y": 1344.8237073173832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 683.6792602539062,
			"height": 125,
			"seed": 1767456390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The LSTM is an enhanced RNN architecture where the building blocks\n(cells) are equipped with special functions to stabilize learning,\nspecifically, mitigate the vanishing/exploding gradient problem.\nThis is done by evaluating previous values different or so called\nshort term memory and long term memory.",
			"rawText": "The LSTM is an enhanced RNN architecture where the building blocks\n(cells) are equipped with special functions to stabilize learning,\nspecifically, mitigate the vanishing/exploding gradient problem.\nThis is done by evaluating previous values different or so called\nshort term memory and long term memory.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The LSTM is an enhanced RNN architecture where the building blocks\n(cells) are equipped with special functions to stabilize learning,\nspecifically, mitigate the vanishing/exploding gradient problem.\nThis is done by evaluating previous values different or so called\nshort term memory and long term memory.",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 85,
			"versionNonce": 654701015,
			"isDeleted": false,
			"id": "lv_v2AzW-pGwHyNIpHvJu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2025.625294176566,
			"y": 1479.6105766209525,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 626,
			"height": 449,
			"seed": 584756550,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AIiNEmW7s5RxhnQ6AK026",
					"type": "arrow"
				}
			],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f854c9168982a068e53af0ad27cbfd58da938ac0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 56,
			"versionNonce": 703331097,
			"isDeleted": false,
			"id": "63EhBBt4im1oxIWpQ95pg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2021.621868350655,
			"y": 1545.8641142831564,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 187.63024228670974,
			"height": 3.092806191539239,
			"seed": 1024171610,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
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
					-187.63024228670974,
					-3.092806191539239
				]
			]
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 926392055,
			"isDeleted": false,
			"id": "WAI4EWfQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2567.2568175076303,
			"y": 1496.3792152185297,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 330.4395751953125,
			"height": 100,
			"seed": 837145350,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Tanh Activation\na function that turns our values\nbetween -1 and 1 to give off\na normalization effect",
			"rawText": "Tanh Activation\na function that turns our values\nbetween -1 and 1 to give off\na normalization effect",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tanh Activation\na function that turns our values\nbetween -1 and 1 to give off\na normalization effect",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 105,
			"versionNonce": 818884601,
			"isDeleted": false,
			"id": "AIiNEmW7s5RxhnQ6AK026",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2029.6999373618892,
			"y": 1750.5047906233317,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 187.63024228670974,
			"height": 3.092806191539239,
			"seed": 368452614,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "lv_v2AzW-pGwHyNIpHvJu",
				"focus": -0.22477082343626462,
				"gap": 4.0746431853231115
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
					-187.63024228670974,
					-3.092806191539239
				]
			]
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 1794549783,
			"isDeleted": false,
			"id": "twrQV6jN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2615.9926358719194,
			"y": 1686.586795998189,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 372.57952880859375,
			"height": 100,
			"seed": 2095035206,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sigmoid Activation\na smooth way to simulate on and off\nswitch (returns value between 0 \nand 1)",
			"rawText": "Sigmoid Activation\na smooth way to simulate on and off\nswitch (returns value between 0 \nand 1)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sigmoid Activation\na smooth way to simulate on and off\nswitch (returns value between 0 \nand 1)",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 85,
			"versionNonce": 1664665817,
			"isDeleted": false,
			"id": "o0a2qp6xyigG3I4ce3Pa2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2816.914755374121,
			"y": 1664.7943725056737,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 183.35895689660782,
			"height": 171.6373797434,
			"seed": 1997757530,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b30c6f881444c87bdf3541f883d7714cb3d2ddd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 110,
			"versionNonce": 540511543,
			"isDeleted": false,
			"id": "3pbBQXU16UX49V6zJGm4i",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2784.481659813606,
			"y": 1453.8337512061908,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 157.66831086840523,
			"height": 149.03969684078106,
			"seed": 150937286,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "30784b82e4d5748453db10016257c16111c8cc99",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1253852601,
			"isDeleted": false,
			"id": "xEZ5DIv2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1437.7871603682715,
			"y": 1583.3418241220502,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 131.61627197265625,
			"height": 20,
			"seed": 764011590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "long term memory",
			"rawText": "long term memory",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "long term memory",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 245,
			"versionNonce": 39767639,
			"isDeleted": false,
			"id": "BwNH1ralIPUNt7MWY9xah",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1724.7122937678312,
			"y": 1585.1586355093723,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 363.0882718611954,
			"height": 74.43381449078765,
			"seed": 939050458,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "S08RJGu9",
				"focus": 0.21479144536582828,
				"gap": 6.570365104180155
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
					66.83996268271608,
					-32.85354097964023
				],
				[
					180.12803502630277,
					-62.87488015069084
				],
				[
					318.90592364719646,
					-74.2036873850493
				],
				[
					363.0882718611954,
					-74.43381449078765
				]
			]
		},
		{
			"type": "arrow",
			"version": 153,
			"versionNonce": 1920804505,
			"isDeleted": false,
			"id": "nVoYy2PtUwqbj93gFx06M",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1618.2215057648596,
			"y": 1586.2915162328081,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 256.03104349650584,
			"height": 77.0558605671431,
			"seed": 972192582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "S08RJGu9",
				"focus": 0.6561181693613418,
				"gap": 7.136805465898078
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
					88.93113678971531,
					-32.85354097964023
				],
				[
					181.26091574973861,
					-49.28031146946023
				],
				[
					256.03104349650584,
					-77.0558605671431
				]
			]
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1547758455,
			"isDeleted": false,
			"id": "S08RJGu9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1355.0536568024556,
			"y": 1486.83225112358,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 147.72833251953125,
			"height": 60,
			"seed": 1406313990,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "BwNH1ralIPUNt7MWY9xah",
					"type": "arrow"
				},
				{
					"id": "nVoYy2PtUwqbj93gFx06M",
					"type": "arrow"
				}
			],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gradient is always\nthe same between\nthese points",
			"rawText": "Gradient is always\nthe same between\nthese points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient is always\nthe same between\nthese points",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 47,
			"versionNonce": 892267385,
			"isDeleted": false,
			"id": "zt6S7lKq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1772.57151421982,
			"y": 1759.6222669184954,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 144.43231201171875,
			"height": 20,
			"seed": 1311859846,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "short term memory",
			"rawText": "short term memory",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "short term memory",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 706897047,
			"isDeleted": false,
			"id": "IuiIlRYi",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1459.4782056612207,
			"y": 1853.7649774914994,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 196.512451171875,
			"height": 20,
			"seed": 2054140634,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(aka weights and biases)",
			"rawText": "(aka weights and biases)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(aka weights and biases)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 576,
			"versionNonce": 1259672665,
			"isDeleted": false,
			"id": "Yuw7npOo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1971.3533919189913,
			"y": 1921.1348207648252,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 783.939208984375,
			"height": 275,
			"seed": 865726170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "fg = What precentage of the long term memory is remembered\n     (also called a forget gate)\n\nig = What precentage of the short term memory is remembered\n     (also called the input gate)\n\nct = potential short term memory values at 100%\n\nog = What precentage of short term memory should we save into the next stm\n     this is multiplied of our long term memory value \"normalized by tanh\" also\n     called the output gate",
			"rawText": "fg = What precentage of the long term memory is remembered\n     (also called a forget gate)\n\nig = What precentage of the short term memory is remembered\n     (also called the input gate)\n\nct = potential short term memory values at 100%\n\nog = What precentage of short term memory should we save into the next stm\n     this is multiplied of our long term memory value \"normalized by tanh\" also\n     called the output gate",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fg = What precentage of the long term memory is remembered\n     (also called a forget gate)\n\nig = What precentage of the short term memory is remembered\n     (also called the input gate)\n\nct = potential short term memory values at 100%\n\nog = What precentage of short term memory should we save into the next stm\n     this is multiplied of our long term memory value \"normalized by tanh\" also\n     called the output gate",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "freedraw",
			"version": 52,
			"versionNonce": 1807202743,
			"isDeleted": false,
			"id": "JTursSmOePvxdsk0DXPih",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1970.929752913326,
			"y": 2076.621810097391,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 9.288112383990665,
			"height": 3.84793227336786,
			"seed": 67162970,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2653746395426424
				],
				[
					0.2653746395426424,
					-0.5307492790852848
				],
				[
					0.5307492790852848,
					-0.9288112383992484
				],
				[
					0.7961239186279272,
					-1.1941858779418908
				],
				[
					0.9288112383992484,
					-1.5922478372558544
				],
				[
					1.3268731977129846,
					-1.990309796569818
				],
				[
					1.592247837255627,
					-2.1229971163406844
				],
				[
					1.8576224767982694,
					-2.388371755883327
				],
				[
					1.9903097965693632,
					-2.521059075654648
				],
				[
					2.2556844361120056,
					-2.521059075654648
				],
				[
					2.521059075654648,
					-2.521059075654648
				],
				[
					2.6537463954259692,
					-2.521059075654648
				],
				[
					2.9191210349686116,
					-2.521059075654648
				],
				[
					3.051808354739933,
					-2.521059075654648
				],
				[
					3.317182994282348,
					-2.2556844361120056
				],
				[
					3.5825576338249903,
					-1.990309796569818
				],
				[
					3.7152449535963115,
					-1.7249351570271756
				],
				[
					3.980619593138954,
					-1.5922478372558544
				],
				[
					4.113306912910048,
					-1.326873197713212
				],
				[
					4.37868155245269,
					-1.0614985581705696
				],
				[
					4.511368872224011,
					-1.0614985581705696
				],
				[
					4.776743511766654,
					-0.9288112383992484
				],
				[
					4.909430831537975,
					-0.7961239186279272
				],
				[
					5.042118151309296,
					-0.7961239186279272
				],
				[
					5.440180110623032,
					-0.663436598856606
				],
				[
					5.5728674303943535,
					-0.663436598856606
				],
				[
					5.838242069936996,
					-0.663436598856606
				],
				[
					5.970929389708317,
					-0.663436598856606
				],
				[
					6.236304029250732,
					-0.663436598856606
				],
				[
					6.5016786687933745,
					-0.663436598856606
				],
				[
					6.767053308336017,
					-0.7961239186279272
				],
				[
					6.899740628107338,
					-0.9288112383992484
				],
				[
					7.1651152676499805,
					-0.9288112383992484
				],
				[
					7.563177226963717,
					-1.1941858779418908
				],
				[
					7.695864546735038,
					-1.326873197713212
				],
				[
					7.96123918627768,
					-1.5922478372558544
				],
				[
					8.093926506049002,
					-1.8576224767984968
				],
				[
					8.359301145591417,
					-2.1229971163406844
				],
				[
					8.491988465362738,
					-2.388371755883327
				],
				[
					8.624675785134059,
					-2.6537463954259692
				],
				[
					8.75736310490538,
					-3.051808354739933
				],
				[
					8.890050424676701,
					-3.184495674511254
				],
				[
					9.022737744448023,
					-3.5825576338252176
				],
				[
					9.155425064219344,
					-3.5825576338252176
				],
				[
					9.155425064219344,
					-3.715244953596539
				],
				[
					9.288112383990665,
					-3.715244953596539
				],
				[
					9.288112383990665,
					-3.84793227336786
				],
				[
					9.288112383990665,
					-3.84793227336786
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 255,
			"versionNonce": 402858297,
			"isDeleted": false,
			"id": "RTR53J_GqAkwyBLww8NTK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1817.7500270580392,
			"y": 1577.164863542274,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 615.8000978281034,
			"height": 126.00891681535904,
			"seed": 1864306246,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "OrtVgqxW",
				"focus": 0.4339229288310849,
				"gap": 13.40640004459624
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
					25.201783363071854,
					-65.74378268627424
				],
				[
					270.6452387251627,
					-82.1797283578428
				],
				[
					615.8000978281034,
					-126.00891681535904
				]
			]
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 908421847,
			"isDeleted": false,
			"id": "OrtVgqxW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1188.5435291853396,
			"y": 1426.4549184316888,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 167.39236450195312,
			"height": 60,
			"seed": 577577242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RTR53J_GqAkwyBLww8NTK",
					"type": "arrow"
				}
			],
			"updated": 1705343768677,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gradient here can be\ndampened but never \namplified",
			"rawText": "Gradient here can be\ndampened but never \namplified",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient here can be\ndampened but never \namplified",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 4082,
			"versionNonce": 1575699897,
			"isDeleted": true,
			"id": "8q1lMK2oXXS-dDDlFUdIz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -596.092760027244,
			"y": 1163.9079776057215,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 106.30473242754128,
			"height": 129.39335334659216,
			"seed": 915851193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.651839019628923,
					-3.2913804901236174
				],
				[
					22.22962723665713,
					-9.36107002460484
				],
				[
					30.566832594835,
					-16.577724141644772
				],
				[
					35.49743122259586,
					-23.435479338441546
				],
				[
					41.73030877672145,
					-38.61936263263189
				],
				[
					46.81800753043724,
					-60.66833365335167
				],
				[
					50.17827591982045,
					-91.04331371932174
				],
				[
					46.30147816105553,
					-88.20813563071285
				],
				[
					46.36044144073602,
					-92.73171392077842
				],
				[
					48.028280795905424,
					-95.93353743613403
				],
				[
					43.832964439307005,
					-98.89689680280752
				],
				[
					39.86594680179468,
					-93.24961509553812
				],
				[
					36.45173696859213,
					-95.37771544801521
				],
				[
					36.466742950104084,
					-97.5588859990814
				],
				[
					35.03196981121209,
					-106.18776910824852
				],
				[
					32.966945448819054,
					-107.62472306594657
				],
				[
					32.872677797200616,
					-110.28298966966977
				],
				[
					29.92844253390367,
					-110.52717643841999
				],
				[
					27.3111731591507,
					-109.88313140068381
				],
				[
					22.81897322602597,
					-102.68177007259182
				],
				[
					20.09929195076332,
					-101.55172712875932
				],
				[
					17.170068080439346,
					-103.10017883008226
				],
				[
					16.85055918523237,
					-109.41722624949331
				],
				[
					19.237316553326995,
					-112.91483752051117
				],
				[
					15.194587164161659,
					-113.32642783706939
				],
				[
					12.863524553268942,
					-107.79005131843908
				],
				[
					11.142490535906164,
					-119.90997347916996
				],
				[
					6.343752979728839,
					-121.23037538861556
				],
				[
					5.506838058448917,
					-116.16162757152252
				],
				[
					4.505614945085776,
					-121.8068583350512
				],
				[
					1.1871122121428948,
					-122.12432169797853
				],
				[
					-0.6678067632388822,
					-113.6991746861582
				],
				[
					-1.1166658120988644,
					-120.69879133457243
				],
				[
					0.5600808079709043,
					-128.16270593024316
				],
				[
					-3.561298756201412,
					-128.44786287065833
				],
				[
					-3.958564935340916,
					-126.24371525594277
				],
				[
					-4.338059876368218,
					-129.2514918949747
				],
				[
					-6.848544890077233,
					-129.39335334659216
				],
				[
					-6.815865076752115,
					-127.52789013934022
				],
				[
					-8.648380603356662,
					-120.7243171963798
				],
				[
					-10.345008931350938,
					-114.81985039090048
				],
				[
					-11.964275012069885,
					-107.84363290009806
				],
				[
					-10.402024085050794,
					-115.97765412995699
				],
				[
					-12.24308972012588,
					-116.39803265927232
				],
				[
					-15.842555511164477,
					-110.60904102129501
				],
				[
					-16.056026826953406,
					-104.90630807257129
				],
				[
					-17.551235162933455,
					-118.40367976521398
				],
				[
					-18.716522952632236,
					-120.02705043914493
				],
				[
					-18.450327771761913,
					-122.63236048496125
				],
				[
					-21.522392568154725,
					-122.9983592421116
				],
				[
					-21.25563459533441,
					-119.3971671949957
				],
				[
					-23.980949201557724,
					-120.0444022890252
				],
				[
					-26.4489109542784,
					-113.97003454645993
				],
				[
					-28.359935957902405,
					-120.98653765910352
				],
				[
					-38.5097156086886,
					-117.50700878520868
				],
				[
					-36.00676064304085,
					-116.2702464178649
				],
				[
					-38.482993813987584,
					-114.34534101662888
				],
				[
					-38.42676061641054,
					-111.76734802622985
				],
				[
					-39.786709483262996,
					-97.93426822970514
				],
				[
					-40.91548343947757,
					-104.90164880460095
				],
				[
					-46.82372744477488,
					-103.52783036305858
				],
				[
					-47.002917154765704,
					-101.15618720569705
				],
				[
					-48.57654297292724,
					-89.03938475226575
				],
				[
					-51.35247638588073,
					-77.23292959047139
				],
				[
					-54.16163075826497,
					-67.21411812019427
				],
				[
					-55.78736894640849,
					-60.56940943949344
				],
				[
					-56.12645650772084,
					-50.64792850779318
				],
				[
					-54.855818394158256,
					-39.829173218179726
				],
				[
					-53.25623379730477,
					-33.47626404634186
				],
				[
					-49.10239087824965,
					-22.644597010645665
				],
				[
					-44.38001444905211,
					-14.914936385372386
				],
				[
					-36.573938582188504,
					-8.314837083897492
				],
				[
					-23.38773942899401,
					-2.837480665288796
				],
				[
					-20.135044011412017,
					-2.0408359358732517
				],
				[
					-16.299741921057432,
					-1.798128982338669
				],
				[
					-9.028955935271323,
					-0.7989505237209339
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 421,
			"versionNonce": 1033883223,
			"isDeleted": true,
			"id": "RhhqJLaIFqmz1izmjMV6B",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -621.4696069707953,
			"y": 1118.1328101282968,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.729219590138477,
			"height": 3.043996039839521,
			"seed": 1136093337,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.10487608309477242
				],
				[
					-0.01878465718294741,
					0.1612339902516527
				],
				[
					-0.16326082839311856,
					0.41950826798707935
				],
				[
					-0.4502965296971805,
					0.8859407906551541
				],
				[
					-0.8174257902575164,
					1.3640463267748744
				],
				[
					-1.729219590138477,
					2.9876381326826404
				],
				[
					-1.729219590138477,
					3.043996039839521
				],
				[
					-1.729219590138477,
					3.043996039839521
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 430,
			"versionNonce": 1204561561,
			"isDeleted": true,
			"id": "SFYAbRniJmeHPfep-WC_E",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -608.6652085329895,
			"y": 1119.1942632951789,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6521118046970007,
			"height": 3.637780903128435,
			"seed": 701558137,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.014734916508029461,
					0.01473885211611586
				],
				[
					-0.014734916508029461,
					0.05895540846441506
				],
				[
					-0.014734916508029461,
					0.14479101985352702
				],
				[
					-0.014734916508029461,
					0.23062663124261482
				],
				[
					0.004045805066855741,
					0.7221643976085954
				],
				[
					0.034727805359833594,
					0.8755625922492497
				],
				[
					0.06540193443668703,
					1.1823550459225443
				],
				[
					0.08419052722769664,
					1.3435890361742213
				],
				[
					0.5471597148190985,
					2.305408349873014
				],
				[
					0.8253048775569815,
					2.688964838399347
				],
				[
					1.4777263650589167,
					3.2582702196689572
				],
				[
					1.6311206240915086,
					3.3196263490387876
				],
				[
					1.9379091421567898,
					3.4730206080714283
				],
				[
					2.1962030979324307,
					3.577904562382253
				],
				[
					2.6078991839567878,
					3.637780903128435
				],
				[
					2.6373768881889714,
					3.637780903128435
				],
				[
					2.6373768881889714,
					3.637780903128435
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 507,
			"versionNonce": 123857783,
			"isDeleted": true,
			"id": "QaM88eKNSFuZt3EHWTwKg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -621.6652578533714,
			"y": 1119.5294196760085,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.933789423392156,
			"height": 2.8774765279878998,
			"seed": 539416153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.01473885211611586
				],
				[
					0.014738852116091671,
					0.02947770423220753
				],
				[
					0.058955408464366685,
					0.07369426058050674
				],
				[
					0.14479101985350284,
					0.1407452147866713
				],
				[
					0.1742687240856862,
					0.1849617711349705
				],
				[
					0.2332280681581151,
					0.24392111520742357
				],
				[
					0.5962682319631529,
					0.49829126976550825
				],
				[
					0.6526222035120435,
					0.5170798625564937
				],
				[
					1.1451674855366518,
					0.8733625873539659
				],
				[
					1.2973613841165599,
					0.9801395691328425
				],
				[
					1.521998019919724,
					1.133549570597635
				],
				[
					1.9024768629574493,
					1.3973848624959815
				],
				[
					2.0546707615373574,
					1.504161844274858
				],
				[
					2.3393136131520795,
					1.7028392094350921
				],
				[
					2.500547603403756,
					1.7740619081654259
				],
				[
					2.7102997695932523,
					1.852718970486493
				],
				[
					2.968574047328679,
					1.9665170770117486
				],
				[
					3.1783301491262863,
					2.071393160106521
				],
				[
					3.646356593051209,
					2.242084416482335
				],
				[
					3.866545991767301,
					2.3206155393460888
				],
				[
					3.9523816031563888,
					2.3394001965290365
				],
				[
					4.057257686251162,
					2.3918382380764225
				],
				[
					4.21849167650279,
					2.4180572588501037
				],
				[
					4.428247778300397,
					2.4675199807179666
				],
				[
					4.562601565627353,
					2.549439662105599
				],
				[
					4.675317379941113,
					2.5870089764714934
				],
				[
					4.76115299133025,
					2.6205364213785947
				],
				[
					4.970905157519746,
					2.672974462925981
				],
				[
					5.120001732570856,
					2.7024521671581887
				],
				[
					5.205837343959992,
					2.71719101927428
				],
				[
					5.335889511697355,
					2.7359756764572274
				],
				[
					5.365367215929587,
					2.7359756764572274
				],
				[
					5.4364639752025825,
					2.754760333640199
				],
				[
					5.52229958659167,
					2.754760333640199
				],
				[
					5.690432697740402,
					2.8161203986180685
				],
				[
					5.900188799537961,
					2.846798463302984
				],
				[
					6.034542586864966,
					2.846798463302984
				],
				[
					6.35701056736827,
					2.8774765279878998
				],
				[
					6.491364354695226,
					2.8774765279878998
				],
				[
					6.663035577473451,
					2.8774765279878998
				],
				[
					6.7488711888625375,
					2.8774765279878998
				],
				[
					6.861587003176347,
					2.8774765279878998
				],
				[
					7.079178900584879,
					2.8774765279878998
				],
				[
					7.240412890836557,
					2.8774765279878998
				],
				[
					7.401646881088185,
					2.8774765279878998
				],
				[
					7.514358759793932,
					2.8774765279878998
				],
				[
					7.67559275004561,
					2.8774765279878998
				],
				[
					7.809950472980626,
					2.8774765279878998
				],
				[
					7.992822436245451,
					2.8774765279878998
				],
				[
					8.154056426497128,
					2.8774765279878998
				],
				[
					8.266772240810887,
					2.8399072136220047
				],
				[
					8.401126028137893,
					2.8399072136220047
				],
				[
					9.003510194997833,
					2.756787171781665
				],
				[
					9.318138444282102,
					2.6954310424118337
				],
				[
					9.452492231609106,
					2.6692120216381285
				],
				[
					9.53833571421427,
					2.6544731695220367
				],
				[
					9.624163454387283,
					2.6544731695220367
				],
				[
					9.78539744463896,
					2.5832504707917034
				],
				[
					9.89811325895272,
					2.5644618780006936
				],
				[
					10.010829073266528,
					2.5268925636347985
				],
				[
					10.328062695074431,
					2.4667328591096376
				],
				[
					10.462416482401387,
					2.4257789218278787
				],
				[
					10.648822621687641,
					2.3627737726885942
				],
				[
					10.783184280230673,
					2.3480349205724784
				],
				[
					10.869019891619809,
					2.3104656062065834
				],
				[
					10.988630891222611,
					2.2695037977087487
				],
				[
					11.047594170903103,
					2.254768881200695
				],
				[
					11.106549579367517,
					2.2252911769684873
				],
				[
					11.1360272835997,
					2.2105483892443334
				],
				[
					11.349313625810675,
					2.12066697278839
				],
				[
					11.393534117767013,
					2.1059320562803365
				],
				[
					11.479369729156101,
					2.0536199541902875
				],
				[
					11.535719765096928,
					2.0348352970073402
				],
				[
					11.621563247702142,
					2.001307852100239
				],
				[
					11.759010422949833,
					1.8945348059293758
				],
				[
					11.817973702630324,
					1.8797959538132847
				],
				[
					11.874331609787228,
					1.8422227038393273
				],
				[
					11.94542443345221,
					1.8086991945402884
				],
				[
					12.065043304271088,
					1.7562611529929022
				],
				[
					12.10925592501135,
					1.7267834487606948
				],
				[
					12.153476416967736,
					1.712044596644603
				],
				[
					12.239312028356824,
					1.6637822352294478
				],
				[
					12.29826743682124,
					1.6343045309972404
				],
				[
					12.44046095536723,
					1.5672535767910758
				],
				[
					12.526296566756319,
					1.5337261318839988
				],
				[
					12.570517058712657,
					1.4895095755356753
				],
				[
					12.656352670101791,
					1.4747707234195837
				],
				[
					12.685830374333975,
					1.4600318713034677
				],
				[
					12.730042995074237,
					1.4305541670712845
				],
				[
					12.815878606463325,
					1.3970306577722214
				],
				[
					12.86009909841971,
					1.3822918056561295
				],
				[
					12.889576802651893,
					1.3675529535400137
				],
				[
					12.90431171915997,
					1.352814101423922
				],
				[
					12.933789423392156,
					1.3380752493078063
				],
				[
					12.933789423392156,
					1.3380752493078063
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 559,
			"versionNonce": 144567161,
			"isDeleted": true,
			"id": "0F0uuSE84P2yFY0en-WZI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -593.9747151565676,
			"y": 1129.5637525499287,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.799827200411749,
			"height": 23.826359993533426,
			"seed": 697082681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.6263090303695025,
					12.10510182724585
				],
				[
					-7.668402013288228,
					19.737880366957008
				],
				[
					-7.799827200411749,
					23.826359993533426
				]
			]
		},
		{
			"type": "line",
			"version": 508,
			"versionNonce": 1227056279,
			"isDeleted": true,
			"id": "t9KhUQIAkjSmLS3tg77oD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -607.124615800059,
			"y": 1136.5289900116827,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.0997868385731726,
			"height": 10.04277795848364,
			"seed": 577098777,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.069789590262176,
					4.405253290063833
				],
				[
					-3.0997868385731726,
					7.179108178281465
				],
				[
					-3.055717296228479,
					10.04277795848364
				]
			]
		},
		{
			"type": "line",
			"version": 486,
			"versionNonce": 1487148121,
			"isDeleted": true,
			"id": "ZKznQ6VssGlyLQKIzdm-a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -571.2002845393207,
			"y": 1139.3095565081176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.428049947433589,
			"height": 15.043588024140822,
			"seed": 245754105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.886862953167305,
					5.810870175032011
				],
				[
					-7.069024397061896,
					12.56354404994854
				],
				[
					-9.428049947433589,
					15.043588024140822
				]
			]
		},
		{
			"type": "line",
			"version": 537,
			"versionNonce": 43563447,
			"isDeleted": true,
			"id": "kNVyG-ulP5CpiKYDfoer8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -560.424148171362,
			"y": 1123.6146073254545,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.994650559331086,
			"height": 32.652451581506156,
			"seed": 667967961,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.106830014185935,
					14.168850132208936
				],
				[
					-9.984275525809325,
					25.00015826584275
				],
				[
					-15.994650559331086,
					32.652451581506156
				]
			]
		},
		{
			"type": "line",
			"version": 466,
			"versionNonce": 464658745,
			"isDeleted": true,
			"id": "wDjfg822zvP34QYkvK5OT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -613.5517054546337,
			"y": 1144.7095773876297,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0437221100583658,
			"height": 3.627603293777541,
			"seed": 720944825,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.0437221100583658,
					1.510694191893475
				],
				[
					-1.015811539557353,
					3.627603293777541
				]
			]
		},
		{
			"type": "line",
			"version": 495,
			"versionNonce": 1223060183,
			"isDeleted": true,
			"id": "IjgguFCvTKCzO5M59Oynj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -633.2967289501864,
			"y": 1122.8773317164269,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.7099018923157803,
			"height": 22.868711535673114,
			"seed": 1724022681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.14163504306937974,
					9.27880254972591
				],
				[
					0.3742245270839714,
					18.399052781737723
				],
				[
					2.5682668492464003,
					22.868711535673114
				]
			]
		},
		{
			"type": "line",
			"version": 622,
			"versionNonce": 1865126425,
			"isDeleted": true,
			"id": "75_aBtx7PHWDOzR8FY2c-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -607.5793335410481,
			"y": 1095.8711692754941,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.563926508351893,
			"height": 8.593246543345595,
			"seed": 157361273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.0529225898362933,
					3.896176549937647
				],
				[
					-2.563926508351893,
					8.593246543345595
				]
			]
		},
		{
			"type": "line",
			"version": 576,
			"versionNonce": 413202423,
			"isDeleted": true,
			"id": "Pwb9-FTcpq0hY7begyXVL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -557.0791739674328,
			"y": 1087.308314544826,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.887732862989528,
			"height": 32.39963405605928,
			"seed": 781725017,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.8878896828629927,
					10.861438101421385
				],
				[
					-9.55532751150161,
					24.80087440444004
				],
				[
					-11.52053834750882,
					29.06600925703662
				],
				[
					-11.887732862989528,
					32.39963405605928
				]
			]
		},
		{
			"type": "line",
			"version": 953,
			"versionNonce": 2013521657,
			"isDeleted": true,
			"id": "FTJ_eEN7f6UvH4zUb49kI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -556.4879617222522,
			"y": 1070.8080802561994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.188087804502581,
			"height": 19.23004372422925,
			"seed": 767236665,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.7121600426460204,
					3.7911997914500875
				],
				[
					-5.9719152560976685,
					6.714396341535749
				],
				[
					-7.470832712224335,
					7.663806111781204
				],
				[
					-8.483162762126002,
					9.900690447444598
				],
				[
					-12.188087804502581,
					19.23004372422925
				]
			]
		},
		{
			"type": "line",
			"version": 487,
			"versionNonce": 1741480215,
			"isDeleted": true,
			"id": "okAm9FUfLvaUnKtyg03yx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -569.774055224622,
			"y": 1069.2623093228592,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.423159886467587,
			"height": 18.20269006192641,
			"seed": 665676569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.8468401877129874,
					5.919655205597849
				],
				[
					-6.423159886467587,
					18.20269006192641
				]
			]
		},
		{
			"type": "line",
			"version": 483,
			"versionNonce": 1891540953,
			"isDeleted": true,
			"id": "b146nWe_l-W5_DlevWYLE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -595.9692526202402,
			"y": 1076.703744185608,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.176949980934043,
			"height": 12.94092328426568,
			"seed": 1424138233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.5173306865097396,
					4.5944686917612545
				],
				[
					-5.176949980934043,
					12.94092328426568
				]
			]
		},
		{
			"type": "line",
			"version": 472,
			"versionNonce": 2011080247,
			"isDeleted": true,
			"id": "8NaMrofqCB9GOtRCSamTZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -615.1281876514173,
			"y": 1062.9014894677716,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.024131625050396285,
			"height": 7.260414158724805,
			"seed": 324942041,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.024131625050396285,
					7.260414158724805
				]
			]
		},
		{
			"type": "line",
			"version": 429,
			"versionNonce": 2003778745,
			"isDeleted": true,
			"id": "oZ_g2lgYUkBo2yeL-HNWl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -615.3903593237098,
			"y": 1075.1925807676719,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.1335073776877877,
			"height": 5.828658869470225,
			"seed": 884192697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.1335073776877877,
					5.828658869470225
				]
			]
		},
		{
			"type": "line",
			"version": 465,
			"versionNonce": 1740293975,
			"isDeleted": true,
			"id": "oSTcpnul9gKQfiYsrUdyV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -624.8022125936357,
			"y": 1069.678931774511,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.335015123622746,
			"height": 15.142741352277653,
			"seed": 201758361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.180220803768049,
					6.022269075799221
				],
				[
					-1.335015123622746,
					15.142741352277653
				]
			]
		},
		{
			"type": "line",
			"version": 456,
			"versionNonce": 465124761,
			"isDeleted": true,
			"id": "vpP_2SKX79L3kdEb8fYC-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -639.3136396321594,
			"y": 1066.9851972330753,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.505099388014189,
			"height": 11.019036256356804,
			"seed": 1007311737,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5376136436037526,
					5.707824784452124
				],
				[
					-2.505099388014189,
					11.019036256356804
				]
			]
		},
		{
			"type": "line",
			"version": 605,
			"versionNonce": 95798391,
			"isDeleted": true,
			"id": "V-MbZWMGLDiAEhlnsxjAi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -607.9251657030336,
			"y": 1055.760443062682,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.0514146609981023,
			"height": 15.189578071418495,
			"seed": 1157792857,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.0514146609981023,
					15.189578071418495
				]
			]
		},
		{
			"type": "line",
			"version": 435,
			"versionNonce": 751837817,
			"isDeleted": true,
			"id": "r1oc0UfHvzClP3-tiQG7M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -556.4541054688816,
			"y": 1111.7096950366558,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9149698355706163,
			"height": 3.2239786613236174,
			"seed": 1388482873,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.9149698355706163,
					3.2239786613236174
				]
			]
		},
		{
			"type": "line",
			"version": 494,
			"versionNonce": 1637096855,
			"isDeleted": true,
			"id": "FPZYDC1p9UVoNhiog8gpx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -633.968085117092,
			"y": 1084.4139574457718,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.4844789506041114,
			"height": 5.13084433272573,
			"seed": 1252917785,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.4844789506041114,
					2.2889681041265786
				],
				[
					-0.33482291373293377,
					5.13084433272573
				]
			]
		},
		{
			"type": "ellipse",
			"version": 596,
			"versionNonce": 1199008601,
			"isDeleted": true,
			"id": "mRu-a8_ZsvuE1238bLmGM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -647.5168017929119,
			"y": 1096.1499703701843,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 21.040659725903986,
			"height": 21.25492111500728,
			"seed": 431511289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 761,
			"versionNonce": 512381623,
			"isDeleted": true,
			"id": "HFe27OZo8iKLUUNCErT8p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -600.8980671532479,
			"y": 1099.6362754339884,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 23.32060650818175,
			"height": 22.665793911740234,
			"seed": 1113919449,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 550,
			"versionNonce": 604149817,
			"isDeleted": true,
			"id": "2FfMd9NPKWS2Phh1t4XC3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -593.0644577725247,
			"y": 1122.8162834423104,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.94446382307691,
			"height": 1.7300757362571026,
			"seed": 717728953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.163209079284523,
					1.104582435824077
				],
				[
					5.183423753423561,
					1.7300757362571026
				],
				[
					8.114004651674176,
					1.4892723794664
				],
				[
					9.94446382307691,
					0.6958905810613784
				]
			]
		},
		{
			"type": "line",
			"version": 525,
			"versionNonce": 87876567,
			"isDeleted": true,
			"id": "FhKCvzrjYvd2MgYFo5OoG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -637.6191579309029,
			"y": 1119.3598084331854,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.084860726914837,
			"height": 4.0955002923312795,
			"seed": 713272729,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.151540304179984,
					-0.08569756236856753
				],
				[
					-5.030965412257133,
					-0.7705137965092745
				],
				[
					-9.084860726914837,
					-4.0955002923312795
				]
			]
		},
		{
			"type": "line",
			"version": 898,
			"versionNonce": 609560857,
			"isDeleted": true,
			"id": "6yyFhek8bCVsteUfmI6ED",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -647.3466404812959,
			"y": 1112.4314032821555,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18.37115768022712,
			"height": 44.72305820466346,
			"seed": 1489801849,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.04516655158169989,
					4.55219596933468
				],
				[
					0.1853417086805122,
					10.25629385504356
				],
				[
					1.187317847663105,
					17.0954448649915
				],
				[
					2.7498997063391775,
					23.85065662114828
				],
				[
					3.5300542288551777,
					26.886226524170567
				],
				[
					5.0263548474363,
					30.164682780224403
				],
				[
					6.984151525244928,
					33.333244750191234
				],
				[
					10.924935648350127,
					38.60325021546684
				],
				[
					13.52616337119812,
					41.38547382750004
				],
				[
					16.443961565898874,
					43.43534693146508
				],
				[
					18.37115768022712,
					44.72305820466346
				]
			]
		},
		{
			"type": "line",
			"version": 569,
			"versionNonce": 1438666999,
			"isDeleted": true,
			"id": "u2jLnkhXhBpMHiVySu4et",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -613.3135393410577,
			"y": 1162.005178132291,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.56608692638363,
			"height": 21.662166860868957,
			"seed": 442882905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.1419184800917042,
					3.351331153313955
				],
				[
					0.949186920102254,
					6.484951735499953
				],
				[
					3.4766555962065273,
					10.204863329154849
				],
				[
					6.584241222979546,
					14.205305064020893
				],
				[
					9.61746837963026,
					17.775605577557993
				],
				[
					12.56608692638363,
					21.662166860868957
				]
			]
		},
		{
			"type": "line",
			"version": 724,
			"versionNonce": 568499705,
			"isDeleted": true,
			"id": "P_MukMEK10xr6SaOrc6TR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -620.8194821543458,
			"y": 1160.7025162409898,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 23.032579162340333,
			"height": 36.70499214624829,
			"seed": 1872955449,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2112863090403125,
					5.136548825187004
				],
				[
					2.326741103595548,
					11.215443412615961
				],
				[
					5.947736315509422,
					15.46077291034681
				],
				[
					12.630178312200584,
					21.976850276771934
				],
				[
					17.653160629318677,
					26.261178496840692
				],
				[
					20.72218278056826,
					28.764778444536315
				],
				[
					22.575570843105005,
					33.46432953211292
				],
				[
					23.032579162340333,
					36.70499214624829
				]
			]
		},
		{
			"type": "line",
			"version": 885,
			"versionNonce": 1503205911,
			"isDeleted": true,
			"id": "QgAMQPfrGbIuJVcpshm3V",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -621.193763879861,
			"y": 1160.5073215105226,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 21.788315363989724,
			"height": 37.32758940902435,
			"seed": 40343833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.892179798625,
					1.9481909181656536
				],
				[
					-2.803418223663525,
					4.946469194243264
				],
				[
					-2.4392385499608586,
					8.675142359616194
				],
				[
					-1.3861715583374867,
					12.3437682880322
				],
				[
					0.48721132217186064,
					15.688625668856684
				],
				[
					6.65645175932839,
					21.00082054960004
				],
				[
					9.874161451150181,
					24.023537816345012
				],
				[
					12.097512676093205,
					26.365889567535724
				],
				[
					15.979273577180134,
					29.194653409726786
				],
				[
					18.100448092036316,
					33.31480998370013
				],
				[
					18.984897140326197,
					37.32758940902435
				]
			]
		},
		{
			"type": "line",
			"version": 578,
			"versionNonce": 2075031257,
			"isDeleted": true,
			"id": "bcU2Vylg_5yhZQGU-bE1g",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -624.016098906316,
			"y": 1167.8824344465093,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.219734703891767,
			"height": 4.564918730546668,
			"seed": 1948716537,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1629662729051928,
					0.5188708669545053
				],
				[
					-2.219734703891767,
					2.0105209591562305
				],
				[
					-1.6822017890817513,
					4.564918730546668
				]
			]
		},
		{
			"type": "line",
			"version": 799,
			"versionNonce": 901496631,
			"isDeleted": true,
			"id": "yy3dqM9DVdXoM7STB1d_V",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -625.7920405214298,
			"y": 1171.6934583937198,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 19.71369944397818,
			"height": 26.725477041104373,
			"seed": 1810163417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3788186315593256,
					0.5794625801470052
				],
				[
					-1.9625770792534014,
					2.3786018800149784
				],
				[
					-1.7880799385317458,
					4.769611823968135
				],
				[
					-0.433358126794396,
					7.095684235233525
				],
				[
					0.11882569442898154,
					9.633682782022893
				],
				[
					2.7938973823325464,
					12.209330112186676
				],
				[
					7.614794871539571,
					14.741319439604968
				],
				[
					12.811755602931077,
					18.284311223049457
				],
				[
					15.953314284276907,
					21.98639254224544
				],
				[
					17.75112236472478,
					26.725477041104373
				]
			]
		},
		{
			"type": "line",
			"version": 632,
			"versionNonce": 1682715577,
			"isDeleted": true,
			"id": "ftQYjGcvft89nMoBb9Axk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -619.0004187902144,
			"y": 1186.0589893268555,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.97441980687058,
			"height": 10.785644640734967,
			"seed": 1681171385,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2127653282540564,
					1.7793932947360775
				],
				[
					1.1156867539136848,
					3.9590265745957423
				],
				[
					2.9031822546512407,
					6.011082578698069
				],
				[
					4.189185171220442,
					7.183759510337491
				],
				[
					4.97441980687058,
					10.785644640734967
				]
			]
		},
		{
			"type": "line",
			"version": 556,
			"versionNonce": 2089599063,
			"isDeleted": true,
			"id": "_VftJNdmDzkb4DD-1YDKL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -623.7854638562557,
			"y": 1183.5193241480056,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.953780935883312,
			"height": 15.164421403007061,
			"seed": 960087193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.21512306021007468,
					1.8407143063725386
				],
				[
					0.15824277677045517,
					4.687885441483174
				],
				[
					1.2989704423274955,
					7.6801470053975365
				],
				[
					3.069137612227047,
					11.252440601668699
				],
				[
					5.738657875673237,
					15.164421403007061
				]
			]
		},
		{
			"type": "line",
			"version": 789,
			"versionNonce": 1876907161,
			"isDeleted": true,
			"id": "tUvOeqLYrQANXGNhbIKKC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -627.9906767800065,
			"y": 1175.240507914959,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.46409268562655,
			"height": 23.392275776973108,
			"seed": 1990707577,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3622828383318322,
					2.4092362110124252
				],
				[
					-2.244039623530064,
					7.548142788181068
				],
				[
					-0.7813459411247885,
					14.195607383978155
				],
				[
					7.220053062096486,
					23.392275776973108
				]
			]
		},
		{
			"type": "line",
			"version": 575,
			"versionNonce": 2145426807,
			"isDeleted": true,
			"id": "84Xo5UOsihRwsN0H6_scS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -630.0201115307805,
			"y": 1186.5321541611875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.462810850136131,
			"height": 12.022824082360088,
			"seed": 1707225689,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6655078588426431,
					2.8194226482570937
				],
				[
					-0.6951885251927826,
					5.114460290830677
				],
				[
					-0.2789514522758065,
					7.48279260475831
				],
				[
					3.767622324943349,
					12.022824082360088
				]
			]
		},
		{
			"type": "line",
			"version": 631,
			"versionNonce": 1645959545,
			"isDeleted": true,
			"id": "XcpQscrsdN5KmBeEyKvSs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -606.2532910178923,
			"y": 1162.8403097690193,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.893697658099475,
			"height": 15.378746260468077,
			"seed": 1532788537,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.20911202795504624,
					3.2735476524459295
				],
				[
					1.4603365851842895,
					7.18168018736817
				],
				[
					3.062081972943853,
					10.654140882278336
				],
				[
					6.521593955826299,
					14.16014098808429
				],
				[
					9.893697658099475,
					15.378746260468077
				]
			]
		},
		{
			"type": "line",
			"version": 814,
			"versionNonce": 1660671639,
			"isDeleted": true,
			"id": "JGIBy5_kB2AhmT2nV4Szq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -596.2011307944501,
			"y": 1175.0781874196146,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.7844644963413505,
			"height": 21.612299830959614,
			"seed": 1171927065,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.05422783498909891,
					6.601864270312053
				],
				[
					3.4778394573793996,
					14.919393139819315
				],
				[
					3.7844644963413505,
					21.612299830959614
				]
			]
		},
		{
			"type": "line",
			"version": 529,
			"versionNonce": 1011073625,
			"isDeleted": true,
			"id": "Lll_RyfVIjF-QK89AEJAa",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -599.8302347414335,
			"y": 1177.1512232419698,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.71611854241865,
			"height": 4.861387889059918,
			"seed": 2066662649,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0606847201839318,
					2.0431443036201657
				],
				[
					2.460261208233211,
					3.5893217359647434
				],
				[
					3.71611854241865,
					4.861387889059918
				]
			]
		},
		{
			"type": "line",
			"version": 476,
			"versionNonce": 1821567927,
			"isDeleted": true,
			"id": "gb8-XFgk99RQQrFE_9_TR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -593.4084622300438,
			"y": 1175.1269155451043,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.753873683531888,
			"height": 3.793667643281662,
			"seed": 1188937177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.7730762763889981,
					1.9985270072164436
				],
				[
					-2.753873683531888,
					3.793667643281662
				]
			]
		},
		{
			"type": "line",
			"version": 1510,
			"versionNonce": 187436857,
			"isDeleted": true,
			"id": "lWyFEhqHr3nBTSx0ZFsEp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -596.091830936547,
			"y": 1174.9886485524278,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 40.68158593952846,
			"height": 12.257608670142622,
			"seed": 939170489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					30.143383269502866,
					0.22094246217785177
				],
				[
					39.23852410736163,
					-0.6235651552316758
				],
				[
					35.51991126436049,
					-1.6176738623694193
				],
				[
					40.462706492812124,
					-2.800925621447317
				],
				[
					39.40002874635091,
					-4.293220093781105
				],
				[
					35.398028510700364,
					-4.206083915303753
				],
				[
					37.91781457716822,
					-5.433138537776956
				],
				[
					40.68158593952846,
					-7.33700209709094
				],
				[
					39.11677122876688,
					-8.563941830083259
				],
				[
					32.5243229006946,
					-7.836761348655983
				],
				[
					33.09311574470156,
					-11.071000140144267
				],
				[
					31.403241336373018,
					-12.03666620796477
				],
				[
					27.854135434466205,
					-8.639783873067755
				],
				[
					15.70056668207906,
					-8.337459696847592
				],
				[
					5.119964798403171,
					-9.558475128780831
				],
				[
					1.501445669247997,
					-11.476574993337929
				]
			]
		},
		{
			"type": "line",
			"version": 525,
			"versionNonce": 415915223,
			"isDeleted": true,
			"id": "rmtV2_rB8et7TCUzkRapI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -601.1353143070282,
			"y": 1165.8359480846334,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.276327423753421,
			"height": 9.139872807491052,
			"seed": 791206809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5840631545782072,
					1.9491849619352772
				],
				[
					2.891943066301394,
					5.69194457670659
				],
				[
					6.276327423753421,
					9.139872807491052
				]
			]
		},
		{
			"type": "line",
			"version": 731,
			"versionNonce": 1966587929,
			"isDeleted": true,
			"id": "ULG9-ZKlZ3BjOlfBn0lTS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -598.3095725577048,
			"y": 1163.7577672116113,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 16.270643291155228,
			"height": 11.521017516089167,
			"seed": 748421241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.7478774165233442,
					1.451115422485328
				],
				[
					3.358729141653021,
					3.68499617284198
				],
				[
					6.643669529402688,
					6.224497827889893
				],
				[
					9.563029523348543,
					8.535023653402831
				],
				[
					14.328266248320052,
					11.437840795888608
				],
				[
					16.270643291155228,
					11.521017516089167
				]
			]
		},
		{
			"type": "line",
			"version": 602,
			"versionNonce": 1798744567,
			"isDeleted": true,
			"id": "yxi2I8qOlj9bgYvB1dNty",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -589.7342566690115,
			"y": 1165.665734323472,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.722695395141097,
			"height": 9.692313881247724,
			"seed": 1578600793,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.3079717833969733,
					1.8208509141623528
				],
				[
					2.9620306448508487,
					3.404392610312081
				],
				[
					7.105534759422807,
					6.089859298640502
				],
				[
					11.524723676228547,
					8.802939423945716
				],
				[
					13.918431025385654,
					9.692313881247724
				],
				[
					15.722695395141097,
					9.590272041421123
				]
			]
		},
		{
			"type": "line",
			"version": 519,
			"versionNonce": 140137721,
			"isDeleted": true,
			"id": "1NPZBLku8bmhQF0xYoaat",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -581.4851120166193,
			"y": 1166.5474011951633,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.338846402841131,
			"height": 6.090498683577751,
			"seed": 1827599929,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.515336426742151,
					3.384631619595742
				],
				[
					9.338846402841131,
					6.090498683577751
				]
			]
		},
		{
			"type": "line",
			"version": 627,
			"versionNonce": 14439191,
			"isDeleted": true,
			"id": "2Q5nM3xQQVTCWPm3nOMuE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -563.7889550127074,
			"y": 1166.8413659128487,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.7082747478862714,
			"height": 4.25136036117157,
			"seed": 201705241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.26960065494029534,
					1.6480945988361821
				],
				[
					-1.1287841547373063,
					3.2889261844010123
				],
				[
					-2.7082747478862714,
					4.25136036117157
				]
			]
		},
		{
			"type": "line",
			"version": 1400,
			"versionNonce": 1209486809,
			"isDeleted": true,
			"id": "JIDfE_1E4NdimCT-78zw3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -622.1734988290685,
			"y": 1160.0734857061007,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 35.334281401500185,
			"height": 22.063199025124412,
			"seed": 1171225593,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.746640979093125,
					0.8218328609919447
				],
				[
					-8.003115440312582,
					1.0857720992438555
				],
				[
					-11.5857675035249,
					0.8728763082544553
				],
				[
					-13.057007523518383,
					-0.26788005518657043
				],
				[
					-15.50444710598226,
					-0.8006785047551976
				],
				[
					-17.39681848502049,
					-0.9453886131374926
				],
				[
					-19.491390061428948,
					-2.012056344921583
				],
				[
					-20.468440178249068,
					-3.697262988551348
				],
				[
					-22.15816825675283,
					-4.003565690529806
				],
				[
					-26.495463207184503,
					-7.628951743390481
				],
				[
					-28.123762926335537,
					-9.763675087559253
				],
				[
					-30.15731868771663,
					-9.63746962942307
				],
				[
					-29.667457953389103,
					-7.481446774532685
				],
				[
					-33.55506430981288,
					-10.233726054562132
				],
				[
					-33.6570493415415,
					-7.495618436078083
				],
				[
					-35.203777333357046,
					-8.416292588245588
				],
				[
					-35.334281401500185,
					-4.6088102341638315
				],
				[
					-30.687532368827256,
					-1.6008056771250128
				],
				[
					-28.476325344001815,
					-1.0738108603797447
				],
				[
					-27.960912327204184,
					0.610205261817395
				],
				[
					-24.006244598788243,
					0.7373784165191393
				],
				[
					-24.21445979428434,
					2.461495375078389
				],
				[
					-23.007217583650682,
					3.8965690092196383
				],
				[
					-20.70970985116817,
					4.3281744103014566
				],
				[
					-20.449440220155605,
					6.113156936263486
				],
				[
					-16.973270431131755,
					6.4243274066236
				],
				[
					-14.521201184572753,
					8.943873116069996
				],
				[
					-11.651132859957432,
					9.349806545895904
				],
				[
					-9.601846936246488,
					11.220600838092423
				],
				[
					-4.52333461515734,
					11.82947297056228
				]
			]
		},
		{
			"type": "line",
			"version": 552,
			"versionNonce": 1647302711,
			"isDeleted": true,
			"id": "QYV9HnQ1oWHtynnyJkONg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -643.3907604357241,
			"y": 1164.2035700828656,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.23415672237651,
			"height": 3.146340600938054,
			"seed": 172987609,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.41277508738703,
					-0.6501087390115393
				],
				[
					10.977122015777013,
					-1.8066487427505462
				],
				[
					13.439059220734656,
					-3.0902702246745593
				],
				[
					15.23415672237651,
					-3.146340600938054
				]
			]
		},
		{
			"type": "line",
			"version": 551,
			"versionNonce": 2072128185,
			"isDeleted": true,
			"id": "75Ju_bJ_9w98XBqNdsE_6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -639.3080995570957,
			"y": 1166.3326476815453,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.311694682975604,
			"height": 2.248962470301065,
			"seed": 2098827705,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.5566331729775795,
					-0.4488533190776407
				],
				[
					10.468658588261905,
					-1.5447340275765664
				],
				[
					13.475072812392314,
					-2.247719744185314
				],
				[
					15.311694682975604,
					-2.248962470301065
				]
			]
		},
		{
			"type": "line",
			"version": 553,
			"versionNonce": 353745239,
			"isDeleted": true,
			"id": "xLal7N3zhmDM_NubOZDwQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -646.0159582375686,
			"y": 1160.7973412042484,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.534418858187465,
			"height": 1.2881690236291017,
			"seed": 55636633,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.9050118631054715,
					-0.014816612355132661
				],
				[
					6.547155938879775,
					-0.3549722854927523
				],
				[
					9.534418858187465,
					-1.2881690236291017
				]
			]
		},
		{
			"type": "line",
			"version": 541,
			"versionNonce": 993946521,
			"isDeleted": true,
			"id": "Orh_YA78z37-2s11YIiQK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -642.40792451207,
			"y": 1156.604078333471,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.120000842894752,
			"height": 0.9016640077944053,
			"seed": 296302457,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.2584002535420602,
					0.597626479750287
				],
				[
					-6.120000842894752,
					0.9016640077944053
				]
			]
		},
		{
			"type": "line",
			"version": 509,
			"versionNonce": 1860335223,
			"isDeleted": true,
			"id": "t9B0j81XLXJXY-AV9yQJT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -651.6495922400514,
			"y": 1152.647780800313,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7515589910592203,
			"height": 4.571641773052281,
			"seed": 979755097,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4008912214054327,
					1.0166938438835131
				],
				[
					0.7515589910592203,
					2.8157168830405883
				],
				[
					0.25195253368872483,
					4.571641773052281
				]
			]
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 1065324665,
			"isDeleted": true,
			"id": "y2_AKCSzmCRHQITCOkJvQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -655.6833131381625,
			"y": 1152.6245688155896,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0526781499872189,
			"height": 1.0527672799340548,
			"seed": 2069523769,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0526781499872189,
					1.0527672799340548
				]
			]
		},
		{
			"type": "line",
			"version": 479,
			"versionNonce": 643469207,
			"isDeleted": true,
			"id": "kqNM562dZvGeChDLFRTjo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -603.5956565851611,
			"y": 1158.8156323703065,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.8510192321553038,
			"height": 4.03350476825844,
			"seed": 1273650713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.020974823058148264,
					1.2208298040482501
				],
				[
					-0.3505893599447781,
					2.9061033156749483
				],
				[
					-1.8300444090971555,
					4.03350476825844
				]
			]
		},
		{
			"type": "line",
			"version": 985,
			"versionNonce": 1846090073,
			"isDeleted": true,
			"id": "uRgmIDTRgH9KIsdrBYTsV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -631.3424726566926,
			"y": 1190.6570523823427,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 79.73398713317582,
			"height": 8.090098517984963,
			"seed": 1795764985,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.576925655096859,
					0.9528933546602713
				],
				[
					-14.921558013818721,
					3.580678139371267
				],
				[
					-16.823431530952103,
					5.609928038557172
				],
				[
					-11.586154582151126,
					7.3932115041477395
				],
				[
					12.055009214898774,
					8.090098517984963
				],
				[
					33.85233106207028,
					7.492261005093492
				],
				[
					56.67492620251004,
					4.890688396620453
				],
				[
					62.91055560222372,
					2.727401783225019
				],
				[
					60.60894357409035,
					1.0948383310027547
				],
				[
					54.87903638546512,
					0.9806696784247153
				],
				[
					39.20130903720713,
					0.21800094397478592
				]
			]
		},
		{
			"type": "line",
			"version": 911,
			"versionNonce": 632456375,
			"isDeleted": true,
			"id": "KYW2b8a4l8iR7mnGWoowP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -648.4952842936631,
			"y": 1196.587209981551,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 80.5844711754165,
			"height": 59.00502039715443,
			"seed": 1832545241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.7251995538556164,
					18.07998125857334
				],
				[
					5.774812904164405,
					32.17111528100996
				],
				[
					11.514957635986468,
					46.59436807932168
				],
				[
					23.291198493169635,
					54.457140058963695
				],
				[
					43.091934020097156,
					56.06632599941836
				],
				[
					58.66035173724465,
					54.955826429553895
				],
				[
					72.42442081787188,
					50.76501217327428
				],
				[
					73.32382258582338,
					47.404088291260344
				],
				[
					75.74194948782444,
					31.263983123297674
				],
				[
					78.40600329622706,
					19.612264220099778
				],
				[
					80.5844711754165,
					2.7192055372514568
				],
				[
					80.34621254461409,
					-2.9386943977360804
				]
			]
		},
		{
			"type": "ellipse",
			"version": 781,
			"versionNonce": 674137657,
			"isDeleted": true,
			"id": "Rpnf176Nh5G-2mK9fwqqQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -643.1912278222679,
			"y": 1100.464146555043,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 5.00459078359627,
			"height": 4.8336801927568755,
			"seed": 177309881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 850,
			"versionNonce": 479122903,
			"isDeleted": true,
			"id": "ZPZA75eBDpGICbcq992AG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -631.7387934423141,
			"y": 1106.544318704926,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 13.795249045338915,
			"height": 8.443346013044673,
			"seed": 749865369,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1949845995382542,
					1.7315850779814335
				],
				[
					-2.4770947528536698,
					3.0101906660407307
				],
				[
					-5.436865032403082,
					3.5622318467008167
				],
				[
					-9.213001111777373,
					3.581412126196925
				],
				[
					-10.551891406769661,
					4.891979349392437
				],
				[
					-10.529587941177624,
					6.786058749248406
				],
				[
					-8.803212296374017,
					7.790465090156353
				],
				[
					-2.907706870405603,
					7.662773162784514
				],
				[
					0.8196848292734189,
					5.23073268856232
				],
				[
					2.747170982056561,
					2.915948783284482
				],
				[
					3.2433576385692553,
					0.2972366099381794
				],
				[
					1.7570055451424602,
					-0.6528809228883206
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 848,
			"versionNonce": 1490245401,
			"isDeleted": true,
			"id": "76tUfHOlE1MS61jr6WdjK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -594.4907682188555,
			"y": 1103.7134995572644,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 5.00459078359627,
			"height": 4.8336801927568755,
			"seed": 1020227193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 886,
			"versionNonce": 1375994615,
			"isDeleted": true,
			"id": "MmcVw6m_VO_-60FN9SbNt",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -582.928573394994,
			"y": 1110.9373794143708,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 13.795249045338915,
			"height": 8.443346013044673,
			"seed": 833435481,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1949845995382542,
					1.7315850779814335
				],
				[
					-2.4770947528536698,
					3.0101906660407307
				],
				[
					-5.436865032403082,
					3.5622318467008167
				],
				[
					-9.213001111777373,
					3.581412126196925
				],
				[
					-10.551891406769661,
					4.891979349392437
				],
				[
					-10.529587941177624,
					6.786058749248406
				],
				[
					-8.803212296374017,
					7.790465090156353
				],
				[
					-2.907706870405603,
					7.662773162784514
				],
				[
					0.8196848292734189,
					5.23073268856232
				],
				[
					2.747170982056561,
					2.915948783284482
				],
				[
					3.2433576385692553,
					0.2972366099381794
				],
				[
					1.7570055451424602,
					-0.6528809228883206
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 808,
			"versionNonce": 1114311673,
			"isDeleted": true,
			"id": "jjv9lPzA6-FUMXcAOgiFz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -525.9683527502574,
			"y": 1028.7876585149338,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 191.08223985220368,
			"height": 101.25408594768493,
			"seed": 1570694201,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.893881494994436,
					11.010017969223147
				],
				[
					10.311755503153725,
					7.219787352992116
				],
				[
					32.94465022926295,
					14.141911879065612
				],
				[
					92.89692853258876,
					21.404222493046117
				],
				[
					156.54064581908324,
					5.492026889535081
				],
				[
					174.4200265690711,
					-29.92666757467693
				],
				[
					167.53218906025668,
					-70.45502591303634
				],
				[
					77.56928977541085,
					-77.85941984853764
				],
				[
					-0.6080967019324334,
					-79.84986345463881
				],
				[
					-16.662213283132573,
					-22.355254305102687
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 462,
			"versionNonce": 915835927,
			"isDeleted": true,
			"id": "UhqhYGGRD3EkPi-cS9Ytd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -507.3850287369953,
			"y": 980.47339648425,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.7087114706336255,
			"height": 29.185506137608588,
			"seed": 2089284889,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.7087114706336255,
					29.185506137608588
				]
			]
		},
		{
			"type": "line",
			"version": 615,
			"versionNonce": 217654489,
			"isDeleted": true,
			"id": "9fQ6Jw3ZEeaEG3GfxEGa1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -490.72662203018365,
			"y": 1009.9047190134529,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.321466510225626,
			"height": 28.6132023852409,
			"seed": 31189497,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.550264787105517,
					-27.7446350551709
				],
				[
					6.748865004335597,
					-14.69072525204937
				],
				[
					8.321466510225626,
					0.868567330070002
				]
			]
		},
		{
			"type": "line",
			"version": 681,
			"versionNonce": 909832503,
			"isDeleted": true,
			"id": "aVNya7jTr9uzEMEMoLOUs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -474.7290196560025,
			"y": 1010.9402500168537,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 10.39397569632685,
			"height": 31.030975155852534,
			"seed": 647906009,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.18770657662919207,
					-29.22283594211366
				],
				[
					2.1477254025344306,
					-22.792276169432697
				],
				[
					4.655928325808962,
					-13.460882597266165
				],
				[
					10.39397569632685,
					-27.25290950407839
				],
				[
					9.493050921397517,
					-17.87401876514596
				],
				[
					8.963661601346127,
					1.8081392137388699
				]
			]
		},
		{
			"type": "line",
			"version": 428,
			"versionNonce": 336667065,
			"isDeleted": true,
			"id": "TFEqXTa54KiOGYgMPNVyY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -488.9099667228721,
			"y": 997.5142295978503,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.681236306206456,
			"height": 0.3044457068210196,
			"seed": 929202105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.681236306206456,
					-0.3044457068210196
				]
			]
		},
		{
			"type": "line",
			"version": 808,
			"versionNonce": 1247130199,
			"isDeleted": true,
			"id": "GNXq1JKSR6qQyylBZlo9E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -441.97872884602407,
			"y": 987.4611004039218,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.57898931505449,
			"height": 26.66163257457771,
			"seed": 575414425,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.015544166980382,
					-0.8296294296318314
				],
				[
					-4.989645160688454,
					0.7165282284690269
				],
				[
					-6.282111859357495,
					9.034181977846849
				],
				[
					-7.44514806499019,
					16.64193362468723
				],
				[
					-5.338839249924643,
					25.200615514622733
				],
				[
					-1.637270011656632,
					25.83200314494588
				],
				[
					-0.700965699000726,
					23.029454085181413
				],
				[
					0.13384125006429945,
					14.138691643470308
				],
				[
					-3.5403043686302156,
					13.038859637922068
				]
			]
		},
		{
			"type": "line",
			"version": 857,
			"versionNonce": 1960215193,
			"isDeleted": true,
			"id": "iU3pCkO-4HI0Lal167Xs8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -434.05847281591616,
			"y": 1011.6115311543335,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.968923134399217,
			"height": 31.022872236251814,
			"seed": 1158587769,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.5315966651943789,
					-27.47541974383113
				],
				[
					5.968923134399217,
					-19.74646219222906
				],
				[
					3.8498216253941795,
					-12.63273781089535
				],
				[
					0.45078636152883894,
					-11.48163512569271
				],
				[
					3.5004826755080742,
					-9.896679789408344
				],
				[
					5.360633284933659,
					-6.453931575654459
				],
				[
					5.550550592071202,
					3.5474524924206845
				]
			]
		},
		{
			"type": "ellipse",
			"version": 560,
			"versionNonce": 1270566775,
			"isDeleted": true,
			"id": "fLkXr257_4mzqwkd9Slmb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.06135700878540096,
			"x": -422.5931946482182,
			"y": 987.2461702782574,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.400776035354855,
			"height": 27.19970333406569,
			"seed": 2062388825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343807270,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 623,
			"versionNonce": 1543292793,
			"isDeleted": true,
			"id": "pExDBaAthhsLeG_infQie",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.06135700878540096,
			"x": -409.5553864492414,
			"y": 987.9281194692065,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.400776035354855,
			"height": 27.19970333406569,
			"seed": 1790729017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705343807270,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 427,
			"versionNonce": 78661783,
			"isDeleted": true,
			"id": "RsYlkRuab3bI177FL7uG8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -396.29195769471573,
			"y": 989.9828770555262,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.018624443573364,
			"height": 0.45097118373724865,
			"seed": 350129177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.018624443573364,
					0.45097118373724865
				]
			]
		},
		{
			"type": "line",
			"version": 460,
			"versionNonce": 331837529,
			"isDeleted": true,
			"id": "2C2Q-fkStG-wvhufim4_I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -392.3870340752385,
			"y": 990.0515160275771,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.8737095263398117,
			"height": 24.928684601297878,
			"seed": 558342393,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705343807270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.8737095263398117,
					24.928684601297878
				]
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#0c8599",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "cross-hatch",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1873.4388988040132,
		"scrollY": -165.43652332599055,
		"zoom": {
			"value": 0.6154001140516812
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