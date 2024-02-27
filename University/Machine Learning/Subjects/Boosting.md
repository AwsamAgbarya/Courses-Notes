---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
How to Boost your ELO 101 ^Xlh4Th5L

Ensemble classification ^8jDORmHK

Consider the following hypothesis/concept h(x), given the feature x
the hypothesis h will classify into +1 or -1.

H represents all our Hypotheses (basis functions for decisions)
from 1 till T

We also have weights alpha_i i=1...T such that theyre >=0
to represent the importance of each hypothesis

Our ensemble classifier's decision is based off of the weighted
sum of our Hypotheses ^tporNjsB

We have previously used this in random forests (Bagging)
but now we are using it to boost our trees ^NL1IluLC

Adaboost ^mJMDlc8g

0 theory, 0 effort, straight ass ^YbUgxZ7m

Given:
N samples (xi, yi) such that xi consists of k features ^iO5kSDsP

We define:
We initialize a weight per sample as 1/N
We iterate for T iterations ^UewiUgyB

Weight of sample
=
How important is that
sample to consider ^7MmUBfxe

Training:
 1) Train a weak base learner (e.g Tree stump) to obtain an initial
hypothesis h

2) This hypothesis is quite naive and bad thus we calculate its
weighted error via




3) We compute the hypothesis weight via the following formula




4)  Update the weights now by multiplying each weight with


5) This will obviously scale our weights, we want our weights to
sum up to one such that they represent the ratio of attention
that needs to be paid to them, thus we scale them down




6) Make a new learner and repeat ^c3ChPFy1

Hypothesis weight
indicates how much
attention we should pay
to its results ^0eo4s3ab

error ^FyvQH6SS

hypothesis
weight ^qXdgOO7A

+ small error term to
    prevent math issues ^hTbS1pwF

In order to emphasize the incorrectly
classified points we multiply the weights with
exponential of the importance of our current
hypothesis.
the -yh term is there to make sure we increase
the incorrectly classified (since yh will be negative)
and decrease the correctly classified ^Bc6Ga9Oc

Adaboost
classifier and Error ^9l5niICP

We built a bunch of models that classify based on
the previous models mistakes, thus our classifier's
overall decision is ^ICtByBgz

Thus given our classification we can compute our error
at point i


In order to minimize such function and be able to take
steps down gradient descent we turn it into a function
that keeps its minima




By deriving this error we can see that



Our gradient descent step is exactly what our weight
actually are if we assume that we choose alpha
such that the error is minimized ^JoCP4ccU

We can always apply a softmargin
to this classifier instead of a
hard margin to deal with outliers
by adding a small epsilon buffer
to the missclassification threshold
(Very similar to slack in SVM)
this is a good regularization
tactic for adaboost ^6slpUtmh

How do we actually quantify our trust with
a certain pattern? how do we know which pattern to
trust and which pattern is just a misclassification/outlier? ^Z3KVHOyF

We can quantify the influence of a pattern n over t hypotheses
 the following:
 ^ak5aaqvy

Sum over
all hypotheses ^t0Qzr0qH

how much
say (weight) that
hypothesis
has, normalized ^d97dYrM9

the weight
of that sample
w.r.t that
hypothesis ^TWvGix3N

The soft margin for that point is then identified by
the influence of the point and the scale


This means that points that are difficult to learn, will have 
high weights dn for most hypotheses which means its influence
will be large and its margin for error will also be large
such that we can disregard trying to classify it properly! ^JlTwcGHk

Adaboost can be interpreted as minimizing the function ^YDWmvW59

Final ensemble
prediction for
xi ^QNUigDVA

true
label ^sKKNtOIv

And then the next hypothesis coeffecient is chosen
such that G(a) is minimized



Which can be seen as a coordinate Gradient descent algorithm
(Gradient descent algorithm except it only minimizes 1 direction at a
time then checks the errors of the previous point we ended up and
minimizes in the other direction from there, kindof how each
consecutive hypothesis looks at previous predictions, sees the incorrect
ones and tries to correct those from that point, without affecting the correct ones) ^02xK0Xsp

check errors of previous prediction
and minimize it ^bNqnFttI

check errors of previous prediction
and minimize it ^rW5HlCV2

check errors of previous prediction
and minimize it ^E7YRTPsB

Reemember how in SVMS the model
focused on the closest point to the decision
boundary to base its support vectors
here we have a similar method
where we use the points closest to the decision boundary
 as the "hardest to classify" and thus theyre
called support patterns ^4mMcqnXB

Support
patterns ^24DOhCM0

Work in Progress Note!
 Sorry ^tssJn4Jy


# Embedded files
9c68f4363cef56173feec5c886971d28efb21bec: $$f_{ens} = \sum_{i=1}^T \alpha_i h_i(x)$$
891735c9eca69c31c7d5414a6851bed9b96a4c94: $$\color{red} \epsilon_t = \sum_{i=1}^{\text{wrong}} W_i^t $$
5ab890c01db696f3b297533e61f25886984f112f: $$\color{red} \alpha_t = \frac{1}{2} log \frac{1-\epsilon_t}{\epsilon_t}$$
3506aa15dd8968fc35f6d990f0cde2c7adc4fd4e: $$\color{red} W_i^{t+1} = W_i^{t} e^{-\alpha_i y_i h_t(x_i)}$$
dec3507a0679fd458a3a551379ecda16e2a3c02b: $$\color{red} W_i^{t+1} = \frac{W_i^{t+1}}{\sum_i W_i^{t+1}}$$
fad805714165df2aec2c3828da1b921a9cd2358f: $$f_\alpha(x_i) = \sum_{t=1}^T \alpha_t h_t (x_i)$$
34a4f5243745d5ac384c7846a21c075f228ed318: $$y_i f_\alpha(x_i)$$
86baa40f6b3d3c909ee24e846c159b23ac483190: $$\sum_{i=1}^N exp^{-y_i f_\alpha(x_i)}$$
a896931ed2f6d6804fdbf490041b08abf9f81a98: $$\frac{\partial Err(\alpha)}{\partial f(x_I)} \approx e^{-y_i f_\alpha(x_i)} \approx W_i^{t+1}$$
5320e081cfc81726423ee95c32eeb05a6894c9b6: $$\mu_n^t = \sum_{r=1}^t \frac{\alpha_r}{\|\alpha\|_1} W_n^r$$
4469659c652750859ec1c717123eb1625264e15f: $$C_n = C ( \mu_n^t)^2$$
d38c60aa3acf98bf66fe26425c9fc5f185a2aa68: $$G(\alpha) = \sum_{i=1}^N exp(-y_i \sum_t \alpha_t h_t(x_i) )$$
fb6a3109cd416616ce9a4972bda0184800cb36bc: $$\frac{\partial G(\alpha^t)}{\partial \text{Prediction of xi}} = exp(-y_i \sum_t \alpha_t h_t(x_i) ) \approx W_i^{t+1}$$
5dfe2e8546722970a72d08fda88226f41cf18708: $$\alpha_t = \frac{1}{2} log \frac{1-\epsilon_t}{\epsilon_t}$$
bfe0549b50d340aaf9e0147f97b35b6c358d22e8: [[Pasted Image 20240226215714_358.png]]
227b8b63286d3972565eddac89d2492294d27013: [[Pasted Image 20240226220159_544.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"type": "ellipse",
			"version": 177,
			"versionNonce": 1743883133,
			"isDeleted": false,
			"id": "vAlGRq7MXDvsqz_L--CNj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -245.17857142857156,
			"y": -357.68638392857144,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 486,
			"height": 144,
			"seed": 514318185,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794785,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 223,
			"versionNonce": 1918678739,
			"isDeleted": false,
			"id": "Xlh4Th5L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -187.54726954868875,
			"y": -302.68638392857144,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 378.7296142578125,
			"height": 35,
			"seed": 798279017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794785,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How to Boost your ELO 101",
			"rawText": "How to Boost your ELO 101",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How to Boost your ELO 101",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 2014122973,
			"isDeleted": false,
			"id": "8jDORmHK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.1226348876953,
			"y": -179.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 310.7452697753906,
			"height": 35,
			"seed": 1387924457,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794785,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Ensemble classification",
			"rawText": "Ensemble classification",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ensemble classification",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 572,
			"versionNonce": 702833779,
			"isDeleted": false,
			"id": "tporNjsB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -331.2196350097656,
			"y": -131.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 656.9392700195312,
			"height": 275,
			"seed": 2125728935,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Consider the following hypothesis/concept h(x), given the feature x\nthe hypothesis h will classify into +1 or -1.\n\nH represents all our Hypotheses (basis functions for decisions)\nfrom 1 till T\n\nWe also have weights alpha_i i=1...T such that theyre >=0\nto represent the importance of each hypothesis\n\nOur ensemble classifier's decision is based off of the weighted\nsum of our Hypotheses",
			"rawText": "Consider the following hypothesis/concept h(x), given the feature x\nthe hypothesis h will classify into +1 or -1.\n\nH represents all our Hypotheses (basis functions for decisions)\nfrom 1 till T\n\nWe also have weights alpha_i i=1...T such that theyre >=0\nto represent the importance of each hypothesis\n\nOur ensemble classifier's decision is based off of the weighted\nsum of our Hypotheses",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider the following hypothesis/concept h(x), given the feature x\nthe hypothesis h will classify into +1 or -1.\n\nH represents all our Hypotheses (basis functions for decisions)\nfrom 1 till T\n\nWe also have weights alpha_i i=1...T such that theyre >=0\nto represent the importance of each hypothesis\n\nOur ensemble classifier's decision is based off of the weighted\nsum of our Hypotheses",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "image",
			"version": 117,
			"versionNonce": 542675005,
			"isDeleted": false,
			"id": "HELLpai8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -81.90557861936304,
			"y": 147.82367395200123,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 177.82366140327662,
			"height": 67.02584160585042,
			"seed": 34735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c68f4363cef56173feec5c886971d28efb21bec",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 160,
			"versionNonce": 459628051,
			"isDeleted": false,
			"id": "NL1IluLC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -220.81594085067252,
			"y": 223.70095319773077,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 451.056884765625,
			"height": 40,
			"seed": 1300863337,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We have previously used this in random forests (Bagging)\nbut now we are using it to boost our trees",
			"rawText": "We have previously used this in random forests (Bagging)\nbut now we are using it to boost our trees",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We have previously used this in random forests (Bagging)\nbut now we are using it to boost our trees",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 229,
			"versionNonce": 1052082333,
			"isDeleted": false,
			"id": "rA1d8EIg6sT8H5n5jc5qe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -338.82000245990696,
			"y": 307.33616412138406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 687.0650086940065,
			"height": 936.4476644796973,
			"seed": 1139784905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "QJrBReJYERCd4nW78V3-U",
					"type": "arrow"
				},
				{
					"id": "7kTRAvCNeF-744I3kDpB2",
					"type": "arrow"
				}
			],
			"updated": 1708981794786,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 71,
			"versionNonce": 1372988339,
			"isDeleted": false,
			"id": "mJMDlc8g",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -39.15369804676229,
			"y": 321.2891875918396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 92.31990051269531,
			"height": 25,
			"seed": 1500925577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Adaboost",
			"rawText": "Adaboost",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Adaboost",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 2027250941,
			"isDeleted": false,
			"id": "YbUgxZ7m",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -28.018098667214502,
			"y": 345.4285043392191,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 66.79388427734375,
			"height": 5.1401231730633885,
			"seed": 812607367,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 4.112098538450711,
			"fontFamily": 1,
			"text": "0 theory, 0 effort, straight ass",
			"rawText": "0 theory, 0 effort, straight ass",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0 theory, 0 effort, straight ass",
			"lineHeight": 1.25,
			"baseline": 3
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 895300947,
			"isDeleted": false,
			"id": "iO5kSDsP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -261.0634501023686,
			"y": 381.8223499477387,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 536.139404296875,
			"height": 50,
			"seed": 1070984617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given:\nN samples (xi, yi) such that xi consists of k features",
			"rawText": "Given:\nN samples (xi, yi) such that xi consists of k features",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given:\nN samples (xi, yi) such that xi consists of k features",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1111080285,
			"isDeleted": false,
			"id": "UewiUgyB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -188.92349680169713,
			"y": 454.6071186193168,
			"strokeColor": "#f08c00",
			"backgroundColor": "#b2f2bb",
			"width": 391.8594970703125,
			"height": 75,
			"seed": 150092839,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We define:\nWe initialize a weight per sample as 1/N\nWe iterate for T iterations",
			"rawText": "We define:\nWe initialize a weight per sample as 1/N\nWe iterate for T iterations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We define:\nWe initialize a weight per sample as 1/N\nWe iterate for T iterations",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 210,
			"versionNonce": 1699812083,
			"isDeleted": false,
			"id": "_AQ99PFCm2EydPe-8uach",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 216.30952261745952,
			"y": 490.036332198949,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 219.15316022474573,
			"height": 49.94943822786229,
			"seed": 697613033,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					199.7977529114489,
					1.2487359556965885
				],
				[
					219.15316022474573,
					-48.7007022721657
				]
			]
		},
		{
			"type": "text",
			"version": 112,
			"versionNonce": 573835709,
			"isDeleted": false,
			"id": "7MmUBfxe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 351.079951506528,
			"y": 353.30227313878294,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 173.76040649414062,
			"height": 80,
			"seed": 482263591,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Weight of sample\n=\nHow important is that\nsample to consider",
			"rawText": "Weight of sample\n=\nHow important is that\nsample to consider",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weight of sample\n=\nHow important is that\nsample to consider",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 640,
			"versionNonce": 1379417235,
			"isDeleted": false,
			"id": "c3ChPFy1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -330.2496958665936,
			"y": 567.0033252051421,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 666.9192504882812,
			"height": 650,
			"seed": 1301805543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Training:\n 1) Train a weak base learner (e.g Tree stump) to obtain an initial\nhypothesis h\n\n2) This hypothesis is quite naive and bad thus we calculate its\nweighted error via\n\n\n\n\n3) We compute the hypothesis weight via the following formula\n\n\n\n\n4)  Update the weights now by multiplying each weight with\n\n\n5) This will obviously scale our weights, we want our weights to\nsum up to one such that they represent the ratio of attention\nthat needs to be paid to them, thus we scale them down\n\n\n\n\n6) Make a new learner and repeat",
			"rawText": "Training:\n 1) Train a weak base learner (e.g Tree stump) to obtain an initial\nhypothesis h\n\n2) This hypothesis is quite naive and bad thus we calculate its\nweighted error via\n\n\n\n\n3) We compute the hypothesis weight via the following formula\n\n\n\n\n4)  Update the weights now by multiplying each weight with\n\n\n5) This will obviously scale our weights, we want our weights to\nsum up to one such that they represent the ratio of attention\nthat needs to be paid to them, thus we scale them down\n\n\n\n\n6) Make a new learner and repeat",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Training:\n 1) Train a weak base learner (e.g Tree stump) to obtain an initial\nhypothesis h\n\n2) This hypothesis is quite naive and bad thus we calculate its\nweighted error via\n\n\n\n\n3) We compute the hypothesis weight via the following formula\n\n\n\n\n4)  Update the weights now by multiplying each weight with\n\n\n5) This will obviously scale our weights, we want our weights to\nsum up to one such that they represent the ratio of attention\nthat needs to be paid to them, thus we scale them down\n\n\n\n\n6) Make a new learner and repeat",
			"lineHeight": 1.25,
			"baseline": 643
		},
		{
			"type": "image",
			"version": 170,
			"versionNonce": 971360797,
			"isDeleted": false,
			"id": "suIHKPVJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -64.05467392933143,
			"y": 719.2343862149348,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 139.9460090418626,
			"height": 72.23019821515489,
			"seed": 87209,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "891735c9eca69c31c7d5414a6851bed9b96a4c94",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 152,
			"versionNonce": 399061555,
			"isDeleted": false,
			"id": "R0V6BHRYLLRIwOFhAEZE2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 313.66866886559046,
			"y": 834.7483294577105,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 137.29560608412498,
			"height": 65.44661015409065,
			"seed": 1057387751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					130.18184411085429,
					-2.845504789308279
				],
				[
					137.29560608412498,
					-65.44661015409065
				]
			]
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 171998845,
			"isDeleted": false,
			"id": "0eo4s3ab",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 345.15743203863747,
			"y": 677.1886850591193,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 190.27239990234375,
			"height": 80,
			"seed": 137223241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0Q3bzDXMNmThw2yAYXF-K",
					"type": "arrow"
				}
			],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Hypothesis weight\nindicates how much\nattention we should pay\nto its results",
			"rawText": "Hypothesis weight\nindicates how much\nattention we should pay\nto its results",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hypothesis weight\nindicates how much\nattention we should pay\nto its results",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 90,
			"versionNonce": 384463827,
			"isDeleted": false,
			"id": "1yjNhkUg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -71.50750091822732,
			"y": 849.6277902853885,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 173.50771001022227,
			"height": 50.78274439323579,
			"seed": 28664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5ab890c01db696f3b297533e61f25886984f112f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 719,
			"versionNonce": 2047190749,
			"isDeleted": false,
			"id": "0Q3bzDXMNmThw2yAYXF-K",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 545.7920044357043,
			"y": 730.8063032692661,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 99.85479388468178,
			"height": 0,
			"seed": 1823815943,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0eo4s3ab",
				"focus": 0.34044045525367034,
				"gap": 10.36217249472304
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
					99.85479388468178,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 813,
			"versionNonce": 1337098611,
			"isDeleted": false,
			"id": "7vOfxIKIi5SUzhc3ucUBK",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": 489.0842265659529,
			"y": 723.9531834599642,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 114.47707465919413,
			"height": 0,
			"seed": 1071022119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "qXdgOO7A",
				"focus": -0.08710155067201039,
				"gap": 3.936887699299632
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
					114.47707465919413,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 827,
			"versionNonce": 466010941,
			"isDeleted": false,
			"id": "4S0WiHtkQZQGmzVidvxdR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 553.0233677790749,
			"y": 671.1062838621838,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 70.23125765940068,
			"height": 120.96614095278466,
			"seed": 353579177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.3232456305710514,
					36.99880135369055
				],
				[
					9.083538056894115,
					49.18403533245085
				],
				[
					21.04722232694969,
					57.159824845821205
				],
				[
					39.21429844073792,
					58.26757338934495
				],
				[
					54.94432775877406,
					66.90801202882956
				],
				[
					63.80631610696337,
					80.64409396852305
				],
				[
					68.01576057235324,
					101.69131629547282
				],
				[
					70.23125765940068,
					120.96614095278466
				]
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 2070403859,
			"isDeleted": false,
			"id": "FyvQH6SS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 644.3158915486866,
			"y": 729.7277484116057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.48504638671875,
			"height": 15.94868662526735,
			"seed": 611735975,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 12.75894930021388,
			"fontFamily": 1,
			"text": "error",
			"rawText": "error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "error",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 367,
			"versionNonce": 870667165,
			"isDeleted": false,
			"id": "qXdgOO7A",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 512.1948796926471,
			"y": 630.8803851805328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.74232482910156,
			"height": 31.8973732505347,
			"seed": 871309129,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7vOfxIKIi5SUzhc3ucUBK",
					"type": "arrow"
				}
			],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 12.75894930021388,
			"fontFamily": 1,
			"text": "hypothesis\nweight",
			"rawText": "hypothesis\nweight",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "hypothesis\nweight",
			"lineHeight": 1.25,
			"baseline": 26
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 1719730355,
			"isDeleted": false,
			"id": "hTbS1pwF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 100.68465711281254,
			"y": 870.2027194668957,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 136.40811157226562,
			"height": 28.708132887192196,
			"seed": 518325927,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 11.483253154876879,
			"fontFamily": 1,
			"text": "+ small error term to\n    prevent math issues",
			"rawText": "+ small error term to\n    prevent math issues",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "+ small error term to\n    prevent math issues",
			"lineHeight": 1.25,
			"baseline": 24
		},
		{
			"type": "image",
			"version": 123,
			"versionNonce": 2123552765,
			"isDeleted": false,
			"id": "NEsSIqsb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -62.05617949143255,
			"y": 980.9073658703406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 154.6050665635917,
			"height": 20.946492889260806,
			"seed": 50991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YQLXvrWOON-7uXAyF967U",
					"type": "arrow"
				}
			],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3506aa15dd8968fc35f6d990f0cde2c7adc4fd4e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 82,
			"versionNonce": 178549331,
			"isDeleted": false,
			"id": "byiyiWwuHFqkJ_B4Z2qz4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 307.1419971303683,
			"y": 954.5128548283523,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 126.79254072333038,
			"height": 1.378179790470881,
			"seed": 710668007,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					126.79254072333038,
					1.378179790470881
				]
			]
		},
		{
			"type": "text",
			"version": 451,
			"versionNonce": 902877277,
			"isDeleted": false,
			"id": "Bc6Ga9Oc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 425.7822018763536,
			"y": 884.2256855143321,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 400.81683349609375,
			"height": 140,
			"seed": 1867141257,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "In order to emphasize the incorrectly\nclassified points we multiply the weights with\nexponential of the importance of our current\nhypothesis.\nthe -yh term is there to make sure we increase\nthe incorrectly classified (since yh will be negative)\nand decrease the correctly classified",
			"rawText": "In order to emphasize the incorrectly\nclassified points we multiply the weights with\nexponential of the importance of our current\nhypothesis.\nthe -yh term is there to make sure we increase\nthe incorrectly classified (since yh will be negative)\nand decrease the correctly classified",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In order to emphasize the incorrectly\nclassified points we multiply the weights with\nexponential of the importance of our current\nhypothesis.\nthe -yh term is there to make sure we increase\nthe incorrectly classified (since yh will be negative)\nand decrease the correctly classified",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "image",
			"version": 152,
			"versionNonce": 1755885555,
			"isDeleted": false,
			"id": "skzHwzci",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -68.12173139577047,
			"y": 1105.144077797194,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 142.6633213131639,
			"height": 49.34220135643262,
			"seed": 51993,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dec3507a0679fd458a3a551379ecda16e2a3c02b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 351,
			"versionNonce": 1467006141,
			"isDeleted": false,
			"id": "QJrBReJYERCd4nW78V3-U",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.25657475833805,
			"y": 407.83935057448804,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 408.38814663376206,
			"height": 157.69243573848456,
			"seed": 638933831,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rA1d8EIg6sT8H5n5jc5qe",
				"focus": 0.7938085725079242,
				"gap": 1
			},
			"endBinding": {
				"elementId": "9l5niICP",
				"focus": -0.16438617129653926,
				"gap": 10.265638875226387
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
					-360.688775667031,
					20.038265314835087
				],
				[
					-408.38814663376206,
					157.69243573848456
				]
			]
		},
		{
			"type": "rectangle",
			"version": 190,
			"versionNonce": 580139411,
			"isDeleted": false,
			"id": "PLhvx5E1ua7UmjqBWaac6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1029.2698847300485,
			"y": 570.7591598733641,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 575.8823205698245,
			"height": 721.7394400562104,
			"seed": 133896967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "QJrBReJYERCd4nW78V3-U",
					"type": "arrow"
				}
			],
			"updated": 1708981794786,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 722738461,
			"isDeleted": false,
			"id": "9l5niICP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -874.1112234173688,
			"y": 575.797425188199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 269.921142578125,
			"height": 70,
			"seed": 1388180327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QJrBReJYERCd4nW78V3-U",
					"type": "arrow"
				}
			],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Adaboost\nclassifier and Error",
			"rawText": "Adaboost\nclassifier and Error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Adaboost\nclassifier and Error",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 1436389171,
			"isDeleted": false,
			"id": "ICtByBgz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -991.9828316614579,
			"y": 667.2381971802196,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 502.179443359375,
			"height": 75,
			"seed": 172029255,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We built a bunch of models that classify based on\nthe previous models mistakes, thus our classifier's\noverall decision is",
			"rawText": "We built a bunch of models that classify based on\nthe previous models mistakes, thus our classifier's\noverall decision is",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We built a bunch of models that classify based on\nthe previous models mistakes, thus our classifier's\noverall decision is",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 156,
			"versionNonce": 137130365,
			"isDeleted": false,
			"id": "04cvSZqM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -868.0866115550557,
			"y": 742.8854515643445,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 241.29309068311628,
			"height": 77.27687217956012,
			"seed": 63723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fad805714165df2aec2c3828da1b921a9cd2358f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 436,
			"versionNonce": 875245779,
			"isDeleted": false,
			"id": "JoCP4ccU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1010.1867151039693,
			"y": 827.7716932592916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 547.2994995117188,
			"height": 450,
			"seed": 2004103657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Thus given our classification we can compute our error\nat point i\n\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat keeps its minima\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"rawText": "Thus given our classification we can compute our error\nat point i\n\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat keeps its minima\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thus given our classification we can compute our error\nat point i\n\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat keeps its minima\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"lineHeight": 1.25,
			"baseline": 443
		},
		{
			"type": "image",
			"version": 77,
			"versionNonce": 1543191005,
			"isDeleted": false,
			"id": "qiZimXzM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -783.1793511144322,
			"y": 888.0079472225589,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 100.69021740986608,
			"height": 29.51264993047799,
			"seed": 16449,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "34a4f5243745d5ac384c7846a21c075f228ed318",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 104,
			"versionNonce": 1607704179,
			"isDeleted": false,
			"id": "YZs6AUtI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -811.7195060141764,
			"y": 1001.8969849174061,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 174.3238768172619,
			"height": 82.13336503890224,
			"seed": 56519,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "86baa40f6b3d3c909ee24e846c159b23ac483190",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 64,
			"versionNonce": 1871836733,
			"isDeleted": false,
			"id": "pyuSn1iL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -875.802867552219,
			"y": 1134.4379877017088,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 257.8898989879208,
			"height": 48.88908037685703,
			"seed": 52768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a896931ed2f6d6804fdbf490041b08abf9f81a98",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 271,
			"versionNonce": 56449043,
			"isDeleted": false,
			"id": "YQLXvrWOON-7uXAyF967U",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 100.45494387046244,
			"y": 991.8290394484079,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 389.6342362726889,
			"height": 159.2216468209831,
			"seed": 1188656595,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794786,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NEsSIqsb",
				"focus": 0.039958722502600956,
				"gap": 13.06549647593718
			},
			"endBinding": {
				"elementId": "6slpUtmh",
				"focus": -0.12794718188675183,
				"gap": 8.332645313376247
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
					271.5632555839953,
					0
				],
				[
					309.1983806785164,
					137.25751505060634
				],
				[
					389.6342362726889,
					159.2216468209831
				]
			]
		},
		{
			"type": "text",
			"version": 332,
			"versionNonce": 1842488989,
			"isDeleted": false,
			"id": "6slpUtmh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 498.4218254565276,
			"y": 1095.5478803700585,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 272.6086120605469,
			"height": 160,
			"seed": 2121276179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YQLXvrWOON-7uXAyF967U",
					"type": "arrow"
				},
				{
					"id": "DDfIw8v6Z61PkhyoMMm8h",
					"type": "arrow"
				}
			],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can always apply a softmargin\nto this classifier instead of a\nhard margin to deal with outliers\nby adding a small epsilon buffer\nto the missclassification threshold\n(Very similar to slack in SVM)\nthis is a good regularization\ntactic for adaboost",
			"rawText": "We can always apply a softmargin\nto this classifier instead of a\nhard margin to deal with outliers\nby adding a small epsilon buffer\nto the missclassification threshold\n(Very similar to slack in SVM)\nthis is a good regularization\ntactic for adaboost",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can always apply a softmargin\nto this classifier instead of a\nhard margin to deal with outliers\nby adding a small epsilon buffer\nto the missclassification threshold\n(Very similar to slack in SVM)\nthis is a good regularization\ntactic for adaboost",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "arrow",
			"version": 163,
			"versionNonce": 750706099,
			"isDeleted": false,
			"id": "DDfIw8v6Z61PkhyoMMm8h",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 778.0038789316538,
			"y": 1164.0495545119977,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 138.3632286063605,
			"height": 117.15680412146594,
			"seed": 1142192925,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6slpUtmh",
				"focus": -0.08234049723637651,
				"gap": 6.9734414145793835
			},
			"endBinding": {
				"elementId": "Z3KVHOyF",
				"focus": 0.003893200032582535,
				"gap": 9.603926207173345
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
					134.19147296998779,
					-4.2655089484856035
				],
				[
					138.3632286063605,
					112.89129517298034
				]
			]
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 695028477,
			"isDeleted": false,
			"id": "Z3KVHOyF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 682.6046391614229,
			"y": 1286.5447758921514,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 468.5130615234375,
			"height": 60,
			"seed": 830524253,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DDfIw8v6Z61PkhyoMMm8h",
					"type": "arrow"
				}
			],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How do we actually quantify our trust with\na certain pattern? how do we know which pattern to\ntrust and which pattern is just a misclassification/outlier?",
			"rawText": "How do we actually quantify our trust with\na certain pattern? how do we know which pattern to\ntrust and which pattern is just a misclassification/outlier?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we actually quantify our trust with\na certain pattern? how do we know which pattern to\ntrust and which pattern is just a misclassification/outlier?",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 1730064211,
			"isDeleted": false,
			"id": "ak5aaqvy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 662.3908611795671,
			"y": 1351.9945017650125,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 509.8250732421875,
			"height": 60,
			"seed": 309295443,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can quantify the influence of a pattern n over t hypotheses\n the following:\n",
			"rawText": "We can quantify the influence of a pattern n over t hypotheses\n the following:\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can quantify the influence of a pattern n over t hypotheses\n the following:\n",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 67,
			"versionNonce": 585425757,
			"isDeleted": false,
			"id": "9Csqm4XX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 845.111398825433,
			"y": 1400.281675399749,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 143.81464991082208,
			"height": 52.58893914649464,
			"seed": 18964,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5320e081cfc81726423ee95c32eeb05a6894c9b6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 28,
			"versionNonce": 349392115,
			"isDeleted": false,
			"id": "rCALlFmh3udoreFafvBhr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 894.0075776497135,
			"y": 1458.1785940979864,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 5.453245356785601,
			"height": 21.085882046237657,
			"seed": 1901440467,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.453245356785601,
					21.085882046237657
				]
			]
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 1317695421,
			"isDeleted": false,
			"id": "t0Qzr0qH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 823.2023730970029,
			"y": 1488.3532184055337,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 111.07223510742188,
			"height": 40,
			"seed": 529400381,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sum over\nall hypotheses",
			"rawText": "Sum over\nall hypotheses",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sum over\nall hypotheses",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 43,
			"versionNonce": 157496979,
			"isDeleted": false,
			"id": "cQYrB-9Rm_DubKWfhE65y",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 967.8081648115455,
			"y": 1448.3627524557721,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 24.721378950761505,
			"height": 46.53436037790402,
			"seed": 1677525309,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24.721378950761505,
					46.53436037790402
				]
			]
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 444559389,
			"isDeleted": false,
			"id": "d97dYrM9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 944.3512656522946,
			"y": 1494.8971128336761,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 138.5283203125,
			"height": 80,
			"seed": 979022771,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "how much\nsay (weight) that\nhypothesis\nhas, normalized",
			"rawText": "how much\nsay (weight) that\nhypothesis\nhas, normalized",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how much\nsay (weight) that\nhypothesis\nhas, normalized",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 30,
			"versionNonce": 1669655603,
			"isDeleted": false,
			"id": "ETxJEaVXnvDQDHd5WRNUk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 995.437941285926,
			"y": 1423.2778238145584,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 72.34638840002253,
			"height": 19.995232974880537,
			"seed": 1401098163,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					72.34638840002253,
					19.995232974880537
				]
			]
		},
		{
			"type": "text",
			"version": 96,
			"versionNonce": 884302973,
			"isDeleted": false,
			"id": "TWvGix3N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1068.317446709246,
			"y": 1425.4591219572724,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 119.63226318359375,
			"height": 80,
			"seed": 821898109,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the weight\nof that sample\nw.r.t that\nhypothesis",
			"rawText": "the weight\nof that sample\nw.r.t that\nhypothesis",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the weight\nof that sample\nw.r.t that\nhypothesis",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 524,
			"versionNonce": 656338387,
			"isDeleted": false,
			"id": "JlTwcGHk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 677.740869245696,
			"y": 1596.9972534197457,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 491.13714599609375,
			"height": 160,
			"seed": 882938941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The soft margin for that point is then identified by\nthe influence of the point and the scale\n\n\nThis means that points that are difficult to learn, will have \nhigh weights dn for most hypotheses which means its influence\nwill be large and its margin for error will also be large\nsuch that we can disregard trying to classify it properly!",
			"rawText": "The soft margin for that point is then identified by\nthe influence of the point and the scale\n\n\nThis means that points that are difficult to learn, will have \nhigh weights dn for most hypotheses which means its influence\nwill be large and its margin for error will also be large\nsuch that we can disregard trying to classify it properly!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The soft margin for that point is then identified by\nthe influence of the point and the scale\n\n\nThis means that points that are difficult to learn, will have \nhigh weights dn for most hypotheses which means its influence\nwill be large and its margin for error will also be large\nsuch that we can disregard trying to classify it properly!",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "image",
			"version": 81,
			"versionNonce": 284019933,
			"isDeleted": false,
			"id": "YkoJuW6g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 896.4148769507277,
			"y": 1640.1938163497339,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 94,
			"height": 19,
			"seed": 77276,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4469659c652750859ec1c717123eb1625264e15f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 60,
			"versionNonce": 390577011,
			"isDeleted": false,
			"id": "7kTRAvCNeF-744I3kDpB2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 19.32249435474543,
			"y": 1249.2676710591443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.60149590988172,
			"height": 148.6104538519919,
			"seed": 829186493,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rA1d8EIg6sT8H5n5jc5qe",
				"focus": -0.06511396357076864,
				"gap": 5.483842458062725
			},
			"endBinding": {
				"elementId": "YDWmvW59",
				"focus": 0.0015510157925822216,
				"gap": 10.044346712312517
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
					-2.60149590988172,
					148.6104538519919
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 783952189,
			"isDeleted": false,
			"id": "YDWmvW59",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199.7973462698621,
			"y": 1407.9224716234487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 431.66485595703125,
			"height": 20,
			"seed": 666224339,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7kTRAvCNeF-744I3kDpB2",
					"type": "arrow"
				}
			],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Adaboost can be interpreted as minimizing the function",
			"rawText": "Adaboost can be interpreted as minimizing the function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Adaboost can be interpreted as minimizing the function",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 77,
			"versionNonce": 1346753811,
			"isDeleted": false,
			"id": "a8hs93ER",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.86085315266766,
			"y": 1433.2573089918114,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 267.14237476246905,
			"height": 54.76977557891625,
			"seed": 62858,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d38c60aa3acf98bf66fe26425c9fc5f185a2aa68",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 31,
			"versionNonce": 528218525,
			"isDeleted": false,
			"id": "6ZeBPVKkbKFSQefHtXGmR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 73.28167948701272,
			"y": 1485.3241028116931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 9.51001109134043,
			"height": 36.68147135231311,
			"seed": 1530361021,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.51001109134043,
					36.68147135231311
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 563067571,
			"isDeleted": false,
			"id": "QNUigDVA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 35.62444211820571,
			"y": 1531.855228508609,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 107.92022705078125,
			"height": 60,
			"seed": 1438006451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Final ensemble\nprediction for\nxi",
			"rawText": "Final ensemble\nprediction for\nxi",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Final ensemble\nprediction for\nxi",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 27,
			"versionNonce": 1281670653,
			"isDeleted": false,
			"id": "Xh_cl7DFJXtYTMxbAxmKz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 22.674834750951163,
			"y": 1486.0033893182174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 20.03895194246732,
			"height": 63.17364510676157,
			"seed": 1877624381,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.03895194246732,
					63.17364510676157
				]
			]
		},
		{
			"type": "text",
			"version": 20,
			"versionNonce": 667675731,
			"isDeleted": false,
			"id": "sKKNtOIv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -22.48066481666217,
			"y": 1556.9888292500084,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 35.96807861328125,
			"height": 40,
			"seed": 155120637,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "true\nlabel",
			"rawText": "true\nlabel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "true\nlabel",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 47,
			"versionNonce": 2088105565,
			"isDeleted": false,
			"id": "45jQmEeS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -115.34135871001874,
			"y": 1603.7450801284965,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 309.05274630716355,
			"height": 38.20707028522626,
			"seed": 56578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fb6a3109cd416616ce9a4972bda0184800cb36bc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 634,
			"versionNonce": 651225587,
			"isDeleted": false,
			"id": "02xK0Xsp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -292.52099641527127,
			"y": 1648.6472168804623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 680.2894287109375,
			"height": 220,
			"seed": 1990474941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "And then the next hypothesis coeffecient is chosen\nsuch that G(a) is minimized\n\n\n\nWhich can be seen as a coordinate Gradient descent algorithm\n(Gradient descent algorithm except it only minimizes 1 direction at a\ntime then checks the errors of the previous point we ended up and\nminimizes in the other direction from there, kindof how each\nconsecutive hypothesis looks at previous predictions, sees the incorrect\nones and tries to correct those from that point, without affecting the correct ones)",
			"rawText": "And then the next hypothesis coeffecient is chosen\nsuch that G(a) is minimized\n\n\n\nWhich can be seen as a coordinate Gradient descent algorithm\n(Gradient descent algorithm except it only minimizes 1 direction at a\ntime then checks the errors of the previous point we ended up and\nminimizes in the other direction from there, kindof how each\nconsecutive hypothesis looks at previous predictions, sees the incorrect\nones and tries to correct those from that point, without affecting the correct ones)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And then the next hypothesis coeffecient is chosen\nsuch that G(a) is minimized\n\n\n\nWhich can be seen as a coordinate Gradient descent algorithm\n(Gradient descent algorithm except it only minimizes 1 direction at a\ntime then checks the errors of the previous point we ended up and\nminimizes in the other direction from there, kindof how each\nconsecutive hypothesis looks at previous predictions, sees the incorrect\nones and tries to correct those from that point, without affecting the correct ones)",
			"lineHeight": 1.25,
			"baseline": 214
		},
		{
			"type": "image",
			"version": 169,
			"versionNonce": 444670653,
			"isDeleted": false,
			"id": "_-GWeOxKE7bbcHSC1eBNn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -24.699861559945532,
			"y": 1693.9586652319117,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 135.767957625393,
			"height": 39.7369632074321,
			"seed": 1858198301,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5dfe2e8546722970a72d08fda88226f41cf18708",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 253,
			"versionNonce": 598029203,
			"isDeleted": false,
			"id": "2-axPBWT3YueVcPxPtKxM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -85.73710759517493,
			"y": 1877.1525826836753,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 273.0555505455843,
			"height": 223.5091804869097,
			"seed": 1077178739,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bfe0549b50d340aaf9e0147f97b35b6c358d22e8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 417,
			"versionNonce": 992461597,
			"isDeleted": false,
			"id": "bNqnFttI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 102.41423028566031,
			"y": 2036.258466843213,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 101.15939331054688,
			"height": 14.93789060186209,
			"seed": 699937363,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 5.975156240744836,
			"fontFamily": 1,
			"text": "check errors of previous prediction\nand minimize it",
			"rawText": "check errors of previous prediction\nand minimize it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "check errors of previous prediction\nand minimize it",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 632,
			"versionNonce": 18000865,
			"isDeleted": false,
			"id": "rW5HlCV2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.737628846562739,
			"x": 61.659657959090296,
			"y": 2020.3458203784737,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 61.255772077220485,
			"height": 9.045447902332535,
			"seed": 595347667,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709039082048,
			"link": null,
			"locked": false,
			"fontSize": 3.6181791609330136,
			"fontFamily": 1,
			"text": "check errors of previous prediction\nand minimize it",
			"rawText": "check errors of previous prediction\nand minimize it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "check errors of previous prediction\nand minimize it",
			"lineHeight": 1.25,
			"baseline": 7
		},
		{
			"type": "text",
			"version": 490,
			"versionNonce": 1336360623,
			"isDeleted": false,
			"id": "E7YRTPsB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 66.8089759555851,
			"y": 1978.5558401891747,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 62.13391363543199,
			"height": 9.17512031435702,
			"seed": 1419883997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709039082048,
			"link": null,
			"locked": false,
			"fontSize": 3.6700481257428077,
			"fontFamily": 1,
			"text": "check errors of previous prediction\nand minimize it",
			"rawText": "check errors of previous prediction\nand minimize it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "check errors of previous prediction\nand minimize it",
			"lineHeight": 1.25,
			"baseline": 7
		},
		{
			"type": "arrow",
			"version": 30,
			"versionNonce": 1288022739,
			"isDeleted": false,
			"id": "A1X5Y6hb1R4iKb1KfAuAQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -243.09793472164836,
			"y": 1810.9190937252606,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 167.33364597021927,
			"height": 0.4822295272915653,
			"seed": 1775677021,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
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
					-167.33364597021927,
					-0.4822295272915653
				]
			]
		},
		{
			"type": "text",
			"version": 344,
			"versionNonce": 199057373,
			"isDeleted": false,
			"id": "4mMcqnXB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -821.5352463752129,
			"y": 1752.0870913956735,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 455.712890625,
			"height": 140,
			"seed": 1321117779,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Reemember how in SVMS the model\nfocused on the closest point to the decision\nboundary to base its support vectors\nhere we have a similar method\nwhere we use the points closest to the decision boundary\n as the \"hardest to classify\" and thus theyre\ncalled support patterns",
			"rawText": "Reemember how in SVMS the model\nfocused on the closest point to the decision\nboundary to base its support vectors\nhere we have a similar method\nwhere we use the points closest to the decision boundary\n as the \"hardest to classify\" and thus theyre\ncalled support patterns",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reemember how in SVMS the model\nfocused on the closest point to the decision\nboundary to base its support vectors\nhere we have a similar method\nwhere we use the points closest to the decision boundary\n as the \"hardest to classify\" and thus theyre\ncalled support patterns",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "image",
			"version": 37,
			"versionNonce": 856610931,
			"isDeleted": false,
			"id": "sYUVTVJWqnZzjReCTrIJI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -734.7454627812962,
			"y": 1894.8270314740162,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 265.7375195092492,
			"height": 233.39909120918185,
			"seed": 2068868755,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "227b8b63286d3972565eddac89d2492294d27013",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 36,
			"versionNonce": 1816091709,
			"isDeleted": false,
			"id": "sL0krMXAgBl1EA3kadS61",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -572.1892080442436,
			"y": 1998.2201949779444,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 76.17371207460383,
			"height": 5.314445028460796,
			"seed": 458642323,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					76.17371207460383,
					-5.314445028460796
				]
			]
		},
		{
			"type": "line",
			"version": 60,
			"versionNonce": 2132890131,
			"isDeleted": false,
			"id": "Q0x03s2Uqtq0wrBIDgy1u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -577.5036530727043,
			"y": 2007.963344196789,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 82.07865099511571,
			"height": 15.64808813935656,
			"seed": 1898985341,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794787,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					82.07865099511571,
					-15.64808813935656
				]
			]
		},
		{
			"type": "line",
			"version": 28,
			"versionNonce": 2078461085,
			"isDeleted": false,
			"id": "qPKECA4PfSQWwJma3fqjg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -563.922293555527,
			"y": 2012.9825422792242,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 66.72580980178475,
			"height": 19.191051491663757,
			"seed": 1509350675,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					66.72580980178475,
					-19.191051491663757
				]
			]
		},
		{
			"type": "line",
			"version": 45,
			"versionNonce": 1106483123,
			"isDeleted": false,
			"id": "oeiEK4qhROojBdZlc3jv-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -619.497696884737,
			"y": 1969.926531685675,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 123.9369158500765,
			"height": 20.800601261551265,
			"seed": 1349822301,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					123.9369158500765,
					20.800601261551265
				]
			]
		},
		{
			"type": "line",
			"version": 38,
			"versionNonce": 981020925,
			"isDeleted": false,
			"id": "L-BGvF9PoODAkmLLg9gQb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -555.1458367318127,
			"y": 1944.7924718279671,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 60.668420346191226,
			"height": 44.63462354041212,
			"seed": 707959507,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					60.668420346191226,
					44.63462354041212
				]
			]
		},
		{
			"type": "line",
			"version": 21,
			"versionNonce": 699148627,
			"isDeleted": false,
			"id": "ynDZvfTcmkCUQpvY_N2Vq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -554.9291638020048,
			"y": 1959.0928851952835,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 57.41832639907386,
			"height": 31.20090189232701,
			"seed": 850979571,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					57.41832639907386,
					31.20090189232701
				]
			]
		},
		{
			"type": "line",
			"version": 52,
			"versionNonce": 897845597,
			"isDeleted": false,
			"id": "InEcax4DjXdQntkfWxbtt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -568.3628854500901,
			"y": 1992.4605163856888,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 68.90199167888863,
			"height": 0.21667292980782804,
			"seed": 1522562269,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					68.90199167888863,
					-0.21667292980782804
				]
			]
		},
		{
			"type": "line",
			"version": 44,
			"versionNonce": 1537312499,
			"isDeleted": false,
			"id": "lBeDS3RC9LiVGIHHYzOhi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -569.0129042395135,
			"y": 2003.9441816655035,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 69.98535632792778,
			"height": 12.350356999045971,
			"seed": 23707827,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					69.98535632792778,
					-12.350356999045971
				]
			]
		},
		{
			"type": "line",
			"version": 42,
			"versionNonce": 1314182589,
			"isDeleted": false,
			"id": "rGLrHXRfRUt_5J61Qkjc1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -554.9291638020048,
			"y": 2016.5112115943575,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 59.15170983753649,
			"height": 21.23394712116692,
			"seed": 42367933,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					59.15170983753649,
					-21.23394712116692
				]
			]
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 240791699,
			"isDeleted": false,
			"id": "24DOhCM0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -488.8256770128955,
			"y": 1969.9265316856747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 68.43215942382812,
			"height": 40,
			"seed": 1023531923,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708981794788,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Support\npatterns",
			"rawText": "Support\npatterns",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Support\npatterns",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"id": "tssJn4Jy",
			"type": "text",
			"x": -754.734281453424,
			"y": 1456.020314641551,
			"width": 314.1053466796875,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1896901007,
			"version": 63,
			"versionNonce": 1566652271,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709039180312,
			"link": null,
			"locked": false,
			"text": "Work in Progress Note!\n Sorry",
			"rawText": "Work in Progress Note!\n Sorry",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Work in Progress Note!\n Sorry",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#ffc9c9",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 28,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 403.80913271701877,
		"scrollY": -1579.5055781559213,
		"zoom": {
			"value": 1.452061626639029
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