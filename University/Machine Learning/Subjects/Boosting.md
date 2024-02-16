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


# Embedded files
9c68f4363cef56173feec5c886971d28efb21bec: $$f_{ens} = \sum_{i=1}^T \alpha_i h_i(x)$$
891735c9eca69c31c7d5414a6851bed9b96a4c94: $$\color{red} \epsilon_t = \sum_{i=1}^{\text{wrong}} W_i^t $$
5ab890c01db696f3b297533e61f25886984f112f: $$\color{red} \alpha_t = \frac{1}{2} log \frac{1-\epsilon_t}{\epsilon_t}$$
3506aa15dd8968fc35f6d990f0cde2c7adc4fd4e: $$\color{red} d_i^{t+1} = d_i^{t} e^{-\alpha_i y_i h_t(x_i)}$$
dec3507a0679fd458a3a551379ecda16e2a3c02b: $$\color{red} d_i^{t+1} = \frac{d_i^{t+1}}{\sum_i d_i^{t+1}}$$
fad805714165df2aec2c3828da1b921a9cd2358f: $$f_\alpha(x_i) = \sum_{t=1}^T \alpha_t h_t (x_i)$$
34a4f5243745d5ac384c7846a21c075f228ed318: $$y_i f_\alpha(x_i)$$
86baa40f6b3d3c909ee24e846c159b23ac483190: $$\sum_{i=1}^N exp^{-y_i f_\alpha(x_i)}$$
a896931ed2f6d6804fdbf490041b08abf9f81a98: $$\frac{\partial Err(\alpha)}{\partial f(x_I)} = e^{y_i f_\alpha(x_i)} = d_i^{t+1}$$

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.14",
	"elements": [
		{
			"id": "vAlGRq7MXDvsqz_L--CNj",
			"type": "ellipse",
			"x": -253.75,
			"y": -466.2578125,
			"width": 486,
			"height": 144,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 514318185,
			"version": 125,
			"versionNonce": 1350672489,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false
		},
		{
			"id": "Xlh4Th5L",
			"type": "text",
			"x": -196.1186981201172,
			"y": -411.2578125,
			"width": 378.7296142578125,
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
			"seed": 798279017,
			"version": 171,
			"versionNonce": 708163239,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "How to Boost your ELO 101",
			"rawText": "How to Boost your ELO 101",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "How to Boost your ELO 101",
			"lineHeight": 1.25
		},
		{
			"id": "8jDORmHK",
			"type": "text",
			"x": -151.1226348876953,
			"y": -179.2578125,
			"width": 310.7452697753906,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1387924457,
			"version": 110,
			"versionNonce": 103000905,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "Ensemble classification",
			"rawText": "Ensemble classification",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Ensemble classification",
			"lineHeight": 1.25
		},
		{
			"id": "tporNjsB",
			"type": "text",
			"x": -331.2196350097656,
			"y": -131.2578125,
			"width": 656.9392700195312,
			"height": 275,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2125728935,
			"version": 571,
			"versionNonce": 532040135,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "Consider the following hypothesis/concept h(x), given the feature x\nthe hypothesis h will classify into +1 or -1.\n\nH represents all our Hypotheses (basis functions for decisions)\nfrom 1 till T\n\nWe also have weights alpha_i i=1...T such that theyre >=0\nto represent the importance of each hypothesis\n\nOur ensemble classifier's decision is based off of the weighted\nsum of our Hypotheses",
			"rawText": "Consider the following hypothesis/concept h(x), given the feature x\nthe hypothesis h will classify into +1 or -1.\n\nH represents all our Hypotheses (basis functions for decisions)\nfrom 1 till T\n\nWe also have weights alpha_i i=1...T such that theyre >=0\nto represent the importance of each hypothesis\n\nOur ensemble classifier's decision is based off of the weighted\nsum of our Hypotheses",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 268,
			"containerId": null,
			"originalText": "Consider the following hypothesis/concept h(x), given the feature x\nthe hypothesis h will classify into +1 or -1.\n\nH represents all our Hypotheses (basis functions for decisions)\nfrom 1 till T\n\nWe also have weights alpha_i i=1...T such that theyre >=0\nto represent the importance of each hypothesis\n\nOur ensemble classifier's decision is based off of the weighted\nsum of our Hypotheses",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 116,
			"versionNonce": 352410153,
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
			"updated": 1705686458893,
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
			"id": "NL1IluLC",
			"type": "text",
			"x": -220.81594085067252,
			"y": 223.70095319773077,
			"width": 451.056884765625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1300863337,
			"version": 159,
			"versionNonce": 972519655,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "We have previously used this in random forests (Bagging)\nbut now we are using it to boost our trees",
			"rawText": "We have previously used this in random forests (Bagging)\nbut now we are using it to boost our trees",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "We have previously used this in random forests (Bagging)\nbut now we are using it to boost our trees",
			"lineHeight": 1.25
		},
		{
			"id": "rA1d8EIg6sT8H5n5jc5qe",
			"type": "rectangle",
			"x": -338.82000245990696,
			"y": 307.33616412138406,
			"width": 687.0650086940065,
			"height": 936.4476644796973,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1139784905,
			"version": 227,
			"versionNonce": 503721225,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "QJrBReJYERCd4nW78V3-U",
					"type": "arrow"
				}
			],
			"updated": 1705686458893,
			"link": null,
			"locked": false
		},
		{
			"id": "mJMDlc8g",
			"type": "text",
			"x": -39.15369804676229,
			"y": 321.2891875918396,
			"width": 92.31990051269531,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1500925577,
			"version": 70,
			"versionNonce": 1317389319,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "Adaboost",
			"rawText": "Adaboost",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Adaboost",
			"lineHeight": 1.25
		},
		{
			"id": "YbUgxZ7m",
			"type": "text",
			"x": -28.018098667214502,
			"y": 345.4285043392191,
			"width": 66.79388427734375,
			"height": 5.1401231730633885,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 812607367,
			"version": 263,
			"versionNonce": 414032873,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "0 theory, 0 effort, straight ass",
			"rawText": "0 theory, 0 effort, straight ass",
			"fontSize": 4.112098538450711,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 3,
			"containerId": null,
			"originalText": "0 theory, 0 effort, straight ass",
			"lineHeight": 1.25
		},
		{
			"id": "iO5kSDsP",
			"type": "text",
			"x": -261.0634501023686,
			"y": 381.8223499477387,
			"width": 536.139404296875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1070984617,
			"version": 196,
			"versionNonce": 1297984295,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "Given:\nN samples (xi, yi) such that xi consists of k features",
			"rawText": "Given:\nN samples (xi, yi) such that xi consists of k features",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Given:\nN samples (xi, yi) such that xi consists of k features",
			"lineHeight": 1.25
		},
		{
			"id": "UewiUgyB",
			"type": "text",
			"x": -188.92349680169713,
			"y": 454.6071186193168,
			"width": 391.8594970703125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 150092839,
			"version": 64,
			"versionNonce": 16989897,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "We define:\nWe initialize a weight per sample as 1/N\nWe iterate for T iterations",
			"rawText": "We define:\nWe initialize a weight per sample as 1/N\nWe iterate for T iterations",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "We define:\nWe initialize a weight per sample as 1/N\nWe iterate for T iterations",
			"lineHeight": 1.25
		},
		{
			"id": "_AQ99PFCm2EydPe-8uach",
			"type": "line",
			"x": 216.30952261745952,
			"y": 490.036332198949,
			"width": 219.15316022474573,
			"height": 49.94943822786229,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 697613033,
			"version": 209,
			"versionNonce": 1928048199,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				172.9499298639731,
				-48.07633429431746
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "7MmUBfxe",
			"type": "text",
			"x": 351.079951506528,
			"y": 353.30227313878294,
			"width": 173.76040649414062,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 482263591,
			"version": 111,
			"versionNonce": 1168276905,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "Weight of sample\n=\nHow important is that\nsample to consider",
			"rawText": "Weight of sample\n=\nHow important is that\nsample to consider",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Weight of sample\n=\nHow important is that\nsample to consider",
			"lineHeight": 1.25
		},
		{
			"id": "c3ChPFy1",
			"type": "text",
			"x": -330.2496958665936,
			"y": 567.0033252051421,
			"width": 666.9192504882812,
			"height": 650,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1301805543,
			"version": 639,
			"versionNonce": 973884775,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458893,
			"link": null,
			"locked": false,
			"text": "Training:\n 1) Train a weak base learner (e.g Tree stump) to obtain an initial\nhypothesis h\n\n2) This hypothesis is quite naive and bad thus we calculate its\nweighted error via\n\n\n\n\n3) We compute the hypothesis weight via the following formula\n\n\n\n\n4)  Update the weights now by multiplying each weight with\n\n\n5) This will obviously scale our weights, we want our weights to\nsum up to one such that they represent the ratio of attention\nthat needs to be paid to them, thus we scale them down\n\n\n\n\n6) Make a new learner and repeat",
			"rawText": "Training:\n 1) Train a weak base learner (e.g Tree stump) to obtain an initial\nhypothesis h\n\n2) This hypothesis is quite naive and bad thus we calculate its\nweighted error via\n\n\n\n\n3) We compute the hypothesis weight via the following formula\n\n\n\n\n4)  Update the weights now by multiplying each weight with\n\n\n5) This will obviously scale our weights, we want our weights to\nsum up to one such that they represent the ratio of attention\nthat needs to be paid to them, thus we scale them down\n\n\n\n\n6) Make a new learner and repeat",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 643,
			"containerId": null,
			"originalText": "Training:\n 1) Train a weak base learner (e.g Tree stump) to obtain an initial\nhypothesis h\n\n2) This hypothesis is quite naive and bad thus we calculate its\nweighted error via\n\n\n\n\n3) We compute the hypothesis weight via the following formula\n\n\n\n\n4)  Update the weights now by multiplying each weight with\n\n\n5) This will obviously scale our weights, we want our weights to\nsum up to one such that they represent the ratio of attention\nthat needs to be paid to them, thus we scale them down\n\n\n\n\n6) Make a new learner and repeat",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 169,
			"versionNonce": 1974919305,
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
			"updated": 1705686458893,
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
			"id": "R0V6BHRYLLRIwOFhAEZE2",
			"type": "line",
			"x": 313.66866886559046,
			"y": 834.7483294577105,
			"width": 137.29560608412498,
			"height": 65.44661015409065,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1057387751,
			"version": 151,
			"versionNonce": 235669639,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				82.51963888994032,
				-63.31248156210938
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "0eo4s3ab",
			"type": "text",
			"x": 345.15743203863747,
			"y": 677.1886850591193,
			"width": 190.27239990234375,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 137223241,
			"version": 136,
			"versionNonce": 788260713,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "0Q3bzDXMNmThw2yAYXF-K",
					"type": "arrow"
				}
			],
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "Hypothesis weight\nindicates how much\nattention we should pay\nto its results",
			"rawText": "Hypothesis weight\nindicates how much\nattention we should pay\nto its results",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Hypothesis weight\nindicates how much\nattention we should pay\nto its results",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 89,
			"versionNonce": 1017601959,
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
			"updated": 1705686458894,
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
			"version": 718,
			"versionNonce": 1270682185,
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
			"updated": 1705686458894,
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
			"version": 812,
			"versionNonce": 671797959,
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
			"updated": 1705686458894,
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
			"id": "4S0WiHtkQZQGmzVidvxdR",
			"type": "line",
			"x": 553.0233677790749,
			"y": 671.1062838621838,
			"width": 70.23125765940068,
			"height": 120.96614095278466,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 353579177,
			"version": 826,
			"versionNonce": 1356194089,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				103.13201098071511,
				150.73140066412202
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "FyvQH6SS",
			"type": "text",
			"x": 644.3158915486866,
			"y": 729.7277484116057,
			"width": 30.48504638671875,
			"height": 15.94868662526735,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 611735975,
			"version": 99,
			"versionNonce": 953344487,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "error",
			"rawText": "error",
			"fontSize": 12.75894930021388,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 10,
			"containerId": null,
			"originalText": "error",
			"lineHeight": 1.25
		},
		{
			"id": "qXdgOO7A",
			"type": "text",
			"x": 512.1948796926471,
			"y": 630.8803851805328,
			"width": 62.74232482910156,
			"height": 31.8973732505347,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 871309129,
			"version": 366,
			"versionNonce": 464638985,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "7vOfxIKIi5SUzhc3ucUBK",
					"type": "arrow"
				}
			],
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "hypothesis\nweight",
			"rawText": "hypothesis\nweight",
			"fontSize": 12.75894930021388,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 26,
			"containerId": null,
			"originalText": "hypothesis\nweight",
			"lineHeight": 1.25
		},
		{
			"id": "hTbS1pwF",
			"type": "text",
			"x": 100.68465711281254,
			"y": 870.2027194668957,
			"width": 136.40811157226562,
			"height": 28.708132887192196,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 518325927,
			"version": 193,
			"versionNonce": 269225223,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "+ small error term to\n    prevent math issues",
			"rawText": "+ small error term to\n    prevent math issues",
			"fontSize": 11.483253154876879,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 24,
			"containerId": null,
			"originalText": "+ small error term to\n    prevent math issues",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 121,
			"versionNonce": 1347185385,
			"isDeleted": false,
			"id": "NEsSIqsb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -56.89673981379868,
			"y": 980.1583533098792,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 144.28618720832395,
			"height": 22.44451801018372,
			"seed": 50991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705686458894,
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
			"id": "byiyiWwuHFqkJ_B4Z2qz4",
			"type": "line",
			"x": 307.1419971303683,
			"y": 954.5128548283523,
			"width": 126.79254072333038,
			"height": 1.378179790470881,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 710668007,
			"version": 81,
			"versionNonce": 2033374247,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					126.79254072333038,
					1.378179790470881
				]
			],
			"lastCommittedPoint": [
				121.9689114566819,
				-3.4454494761776004
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Bc6Ga9Oc",
			"type": "text",
			"x": 425.7822018763536,
			"y": 884.2256855143321,
			"width": 400.81683349609375,
			"height": 140,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1867141257,
			"version": 450,
			"versionNonce": 120661449,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "In order to emphasize the incorrectly\nclassified points we multiply the weights with\nexponential of the importance of our current\nhypothesis.\nthe -yh term is there to make sure we increase\nthe incorrectly classified (since yh will be negative)\nand decrease the correctly classified",
			"rawText": "In order to emphasize the incorrectly\nclassified points we multiply the weights with\nexponential of the importance of our current\nhypothesis.\nthe -yh term is there to make sure we increase\nthe incorrectly classified (since yh will be negative)\nand decrease the correctly classified",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 134,
			"containerId": null,
			"originalText": "In order to emphasize the incorrectly\nclassified points we multiply the weights with\nexponential of the importance of our current\nhypothesis.\nthe -yh term is there to make sure we increase\nthe incorrectly classified (since yh will be negative)\nand decrease the correctly classified",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 151,
			"versionNonce": 473151303,
			"isDeleted": false,
			"id": "skzHwzci",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -62.830355925206995,
			"y": 1103.1673441021046,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 132.08057037203696,
			"height": 53.2956687466114,
			"seed": 51993,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705686458894,
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
			"id": "QJrBReJYERCd4nW78V3-U",
			"type": "arrow",
			"x": -339.25657475833805,
			"y": 407.83935057448804,
			"width": 408.38814663376206,
			"height": 157.69243573848456,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 638933831,
			"version": 350,
			"versionNonce": 997950633,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1705686458894,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-393.79547488284516,
				168.147182859268
			],
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
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "PLhvx5E1ua7UmjqBWaac6",
			"type": "rectangle",
			"x": -1029.2698847300485,
			"y": 570.7591598733641,
			"width": 575.8823205698245,
			"height": 721.7394400562104,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 133896967,
			"version": 189,
			"versionNonce": 567998825,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "QJrBReJYERCd4nW78V3-U",
					"type": "arrow"
				}
			],
			"updated": 1705686902965,
			"link": null,
			"locked": false
		},
		{
			"id": "9l5niICP",
			"type": "text",
			"x": -874.1112234173688,
			"y": 575.797425188199,
			"width": 269.921142578125,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1388180327,
			"version": 60,
			"versionNonce": 2027358089,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "QJrBReJYERCd4nW78V3-U",
					"type": "arrow"
				}
			],
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "Adaboost\nclassifier and Error",
			"rawText": "Adaboost\nclassifier and Error",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Adaboost\nclassifier and Error",
			"lineHeight": 1.25
		},
		{
			"id": "ICtByBgz",
			"type": "text",
			"x": -991.9828316614579,
			"y": 667.2381971802196,
			"width": 502.179443359375,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 172029255,
			"version": 166,
			"versionNonce": 1772474759,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686458894,
			"link": null,
			"locked": false,
			"text": "We built a bunch of models that classify based on\nthe previous models mistakes, thus our classifier's\noverall decision is",
			"rawText": "We built a bunch of models that classify based on\nthe previous models mistakes, thus our classifier's\noverall decision is",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "We built a bunch of models that classify based on\nthe previous models mistakes, thus our classifier's\noverall decision is",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 155,
			"versionNonce": 1233071721,
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
			"updated": 1705686458894,
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
			"id": "JoCP4ccU",
			"type": "text",
			"x": -1010.1867151039693,
			"y": 827.7716932592916,
			"width": 547.2994995117188,
			"height": 450,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2004103657,
			"version": 435,
			"versionNonce": 1191051271,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705686896160,
			"link": null,
			"locked": false,
			"text": "Thus given our classification we can compute our error\nat point i\n\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat keeps its minima\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"rawText": "Thus given our classification we can compute our error\nat point i\n\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat keeps its minima\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 443,
			"containerId": null,
			"originalText": "Thus given our classification we can compute our error\nat point i\n\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat keeps its minima\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 76,
			"versionNonce": 1224642409,
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
			"updated": 1705686545442,
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
			"version": 103,
			"versionNonce": 1819240745,
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
			"updated": 1705686664266,
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
			"version": 63,
			"versionNonce": 1442533321,
			"isDeleted": false,
			"id": "pyuSn1iL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -869.860357058467,
			"y": 1133.257019765094,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 246.0048780004169,
			"height": 51.25101625008685,
			"seed": 52768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705686843843,
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
			"id": "gX1q0csV",
			"type": "text",
			"x": -747.7605459165992,
			"y": 1168.0467226251583,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1024584807,
			"version": 2,
			"versionNonce": 348231785,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1705686845606,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#a5d8ff",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1199.7142529614252,
		"scrollY": -669.7413474326738,
		"zoom": {
			"value": 1.2813114342853866
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