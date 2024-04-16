---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - MachineLearning
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


This can also be thought of as the "margin" to the error
as we want both our prediction and the true label to
be of the same sign to be correct, and the higher the
prediction*label the more confident we are with the
prediction and the further we are away from the margin

In order to minimize such function and be able to take
steps down gradient descent we turn it into a function
that gives minimal values for confident answers
and bigger values for misclassified/ things near the margin




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

Theoretically this converges to a solution exponentially with the amount of iterations
all you really need to guarantee is that your weak learner is SLIGHTLY smarter than guessing
and perform the algorithm to make a stronger learner ^tMDSEBnq

Its complexity (VC dimension) grows linearly with every iteration as we keep adding models
to it, but the solution converges so much faster that this model is not very prone to overfitting ^9kk6Xuxt

Small VC implies little deviation from the empirical risk ^S3dYEAMZ

BUt this does not explain
a weird phenomena with boosting
such that even at very high complexity
the test error does not shoot up! ^0lHwTIOD

test ^yoF9LoIF

train ^0BuWYrpZ

defeats the whole concept
of occam's razor where the training
error goes to zero but the test error
keeps going down ^fdf412IT

Hard-margin Boosting does overfit but that dataset
was just uniquely non-messy which caused this result ^S4a1p1YC

Correctly classifying every point where there exists an outlier is
literally overfitting!!!
thus Boosting can overfit and that graph is just an odd
coincidence  ^WIek8J10

Lets mathematically prove that 



is true ^IaFw5o5Y

Firstly we would need to rewrite the objective function in
a different way to help us simplify, then we will compute the gradient
and try to find the minima of the function ^e4Dx9919


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
5dfe2e8546722970a72d08fda88226f41cf18708: $$\alpha_t = \arg\min_{\alpha_t \geq0} G(\alpha^t)= \frac{1}{2} log \frac{1-\epsilon_t}{\epsilon_t}$$
b3c844f070af544f0d4b450f7f99d4d3cddd93b4: $$\alpha_t = \arg\min_{\alpha_t \geq0} G(\alpha^t)= \frac{1}{2} log \frac{1-\epsilon_t}{\epsilon_t}$$
e8e50f552e6cc662d6ba9c18ae03e1e8a3360d0a: $$\color{white} p_i^{(1)} = \frac{1}{N}$$
bbb4307723475d60c528a637ed8813a268aa124b: $$\color{white} p_i^{(2)} = \frac{1}{N} \frac{1}{Z_1} exp(-\alpha_1y_i h_1(x_i))$$
3d26e6632cc38bcc916ec0c560a08e8759dc0c32: $$\color{white} p_i^{(t)} = \frac{1}{N} \left( \prod_{k=1}^{t-1} \frac{1}{Z_k} \right) exp(\sum_{k=1}^{t-1}-\alpha_ky_i h_k(x_i))$$
d9cc354bd639ae8a5c152c23dc0dfe708282a4e3: $$\color{white} p_i^{(t)} N \left( \prod_{k=1}^{t-1} Z_k \right) = exp(\sum_{k=1}^{t-1}-\alpha_ky_i h_k(x_i))$$
d38d65d325246d6f1203f7d3eb040d6b28250bf9: $$\color{white} G(\alpha^t) = \sum_{i=1}^N exp^{-y_i f_\alpha(x_i)} =  \sum_{i=1}^N exp(\sum_{k=1}^{t}-\alpha_ky_i h_k(x_i)) =  \sum_{i=1}^N exp(\sum_{k=1}^{t-1}-\alpha_ky_i h_k(x_i)) \cdot exp(-\alpha_ty_i h_t(x_i))$$
e78a2aa95efba5137be8393208a60853df47bb57: $$\color{white} G(\alpha^t) = \sum_{i=1}^N  p_i^{(t)} N \left( \prod_{k=1}^{t-1}Z_k \right) exp(-\alpha_ty_i h_t(x_i))$$
81047ef2c59328975cc77eef6e42a628fb3eed4d: $$\color{white} \frac{\partial G(\alpha^t)}{\partial \alpha^t} =  N \left( \prod_{k=1}^{t-1} Z_k \right) \sum_{i=1}^N  p_i^{(t)}  exp(-\alpha_ty_i h_t(x_i)) \cdot (-y_i h_t(x_i))= 0$$
1fb55b89cae454c0fc9f64501d4d590fea3d27b0: $$\color{white} \sum_{i=1}^N  p_i^{(t)}  exp(-\alpha_ty_i h_t(x_i)) \cdot (-y_i h_t(x_i))= 0$$
7d346b725860c04b0b4c62808ad09743c1858d37: $$\color{white} \sum_{classified}  p_i^{(t)}  exp(-\alpha_t) \cdot (-1) +  \color{white} \sum_{misclassified}  p_i^{(t)}  exp(\alpha_t)= 0$$
bf272e86152d7c7c651df1b6992101469a2bad33: $$\color{white} (1-\epsilon) exp(-\alpha_t) = \epsilon  \cdot exp(\alpha_t)$$
310bc8e0f146056c50a68e873145de4fdd6ad085: $$\color{white}\frac{ (1-\epsilon) }{\epsilon }= \frac{ exp(\alpha_t)}{exp(-\alpha_t) }$$
7d24ff7f5a4fdc0f4b607f015cec1325f961335a: $$\color{white} log \frac{ (1-\epsilon) }{\epsilon }= log \frac{ exp(\alpha_t)}{exp(-\alpha_t) }$$
8476b552a6502fccd43cd3a7e622dc8257cdebfb: $$\color{white} log \frac{ (1-\epsilon) }{\epsilon }= \alpha_t + \alpha_t$$
2e71367acd6baecb5a956e33ef69fab7df2f85d3: $$\color{white}\frac{1}{2} log \frac{ (1-\epsilon) }{\epsilon }= \alpha_t $$
bfe0549b50d340aaf9e0147f97b35b6c358d22e8: [[Pasted Image 20240226215714_358.png]]
227b8b63286d3972565eddac89d2492294d27013: [[Pasted Image 20240226220159_544.png]]
396e5731d9c09f9dbccfc9cc883348c8caacf0e8: [[Pasted Image 20240228165319_646.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"type": "ellipse",
			"version": 179,
			"versionNonce": 1052415270,
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
			"updated": 1709145733027,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 225,
			"versionNonce": 264321082,
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
			"updated": 1709145733027,
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
			"version": 113,
			"versionNonce": 842596454,
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
			"updated": 1709145733027,
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
			"version": 574,
			"versionNonce": 1780621562,
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
			"updated": 1709145733027,
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
			"version": 119,
			"versionNonce": 1497891750,
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
			"updated": 1709145733027,
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
			"version": 162,
			"versionNonce": 1105719738,
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
			"updated": 1709145733027,
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
			"version": 231,
			"versionNonce": 638885606,
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
			"updated": 1709145733027,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 1781901946,
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
			"updated": 1709145733027,
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
			"version": 266,
			"versionNonce": 1026282022,
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
			"updated": 1709145733027,
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
			"version": 199,
			"versionNonce": 1506691898,
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
			"updated": 1709145733027,
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
			"version": 67,
			"versionNonce": 695901542,
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
			"updated": 1709145733027,
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
			"version": 212,
			"versionNonce": 924111866,
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
			"updated": 1709145733027,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 114,
			"versionNonce": 273547430,
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
			"updated": 1709145733028,
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
			"version": 642,
			"versionNonce": 1678525626,
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
			"updated": 1709145733028,
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
			"version": 172,
			"versionNonce": 1699937254,
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
			"updated": 1709145733028,
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
			"version": 154,
			"versionNonce": 173514106,
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
			"updated": 1709145733028,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 139,
			"versionNonce": 513183526,
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
			"updated": 1709145733028,
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
			"version": 92,
			"versionNonce": 658103866,
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
			"updated": 1709145733028,
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
			"version": 721,
			"versionNonce": 1753594470,
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
			"updated": 1709145733028,
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
			"version": 815,
			"versionNonce": 395708154,
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
			"updated": 1709145733028,
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
			"version": 829,
			"versionNonce": 1508736422,
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
			"updated": 1709145733028,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 102,
			"versionNonce": 602871738,
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
			"updated": 1709145733028,
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
			"version": 369,
			"versionNonce": 670750950,
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
			"updated": 1709145733028,
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
			"version": 196,
			"versionNonce": 208146554,
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
			"updated": 1709145733028,
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
			"version": 125,
			"versionNonce": 1513802790,
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
			"updated": 1709145733028,
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
			"version": 84,
			"versionNonce": 348385594,
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
			"updated": 1709145733028,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 453,
			"versionNonce": 2124044134,
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
			"updated": 1709145733028,
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
			"version": 154,
			"versionNonce": 275102202,
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
			"updated": 1709145733028,
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
			"version": 353,
			"versionNonce": 1566997158,
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
			"updated": 1709145733028,
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
			"version": 338,
			"versionNonce": 1850763962,
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
			"height": 964.0105601873069,
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
				},
				{
					"id": "M37Mq3Xc07HKP55IoOWcw",
					"type": "arrow"
				},
				{
					"id": "l1NoAsWMc6r2DdsU-7owI",
					"type": "arrow"
				}
			],
			"updated": 1709145733028,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 759969254,
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
			"updated": 1709145733028,
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
			"version": 169,
			"versionNonce": 1160184698,
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
			"updated": 1709145733028,
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
			"version": 158,
			"versionNonce": 1196984614,
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
			"updated": 1709145733028,
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
			"version": 938,
			"versionNonce": 1596752954,
			"isDeleted": false,
			"id": "JoCP4ccU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1025.1966333168598,
			"y": 827.7716932592916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 577.3193359375,
			"height": 625,
			"seed": 2004103657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "A1X5Y6hb1R4iKb1KfAuAQ",
					"type": "arrow"
				}
			],
			"updated": 1709145733028,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Thus given our classification we can compute our error\nat point i\n\n\nThis can also be thought of as the \"margin\" to the error\nas we want both our prediction and the true label to\nbe of the same sign to be correct, and the higher the\nprediction*label the more confident we are with the\nprediction and the further we are away from the margin\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat gives minimal values for confident answers\nand bigger values for misclassified/ things near the margin\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"rawText": "Thus given our classification we can compute our error\nat point i\n\n\nThis can also be thought of as the \"margin\" to the error\nas we want both our prediction and the true label to\nbe of the same sign to be correct, and the higher the\nprediction*label the more confident we are with the\nprediction and the further we are away from the margin\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat gives minimal values for confident answers\nand bigger values for misclassified/ things near the margin\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thus given our classification we can compute our error\nat point i\n\n\nThis can also be thought of as the \"margin\" to the error\nas we want both our prediction and the true label to\nbe of the same sign to be correct, and the higher the\nprediction*label the more confident we are with the\nprediction and the further we are away from the margin\n\nIn order to minimize such function and be able to take\nsteps down gradient descent we turn it into a function\nthat gives minimal values for confident answers\nand bigger values for misclassified/ things near the margin\n\n\n\n\nBy deriving this error we can see that\n\n\n\nOur gradient descent step is exactly what our weight\nactually are if we assume that we choose alpha\nsuch that the error is minimized",
			"lineHeight": 1.25,
			"baseline": 618
		},
		{
			"type": "image",
			"version": 79,
			"versionNonce": 1526232166,
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
			"updated": 1709145733028,
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
			"version": 163,
			"versionNonce": 1178856698,
			"isDeleted": false,
			"id": "YZs6AUtI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -816.4702024352622,
			"y": 1187.8865205339998,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 174.3238768172619,
			"height": 82.13336503890224,
			"seed": 56519,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733028,
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
			"version": 123,
			"versionNonce": 569964454,
			"isDeleted": false,
			"id": "pyuSn1iL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -880.5535639733048,
			"y": 1320.4275233183025,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 257.8898989879208,
			"height": 48.88908037685703,
			"seed": 52768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733028,
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
			"version": 273,
			"versionNonce": 1341144506,
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
			"updated": 1709145733028,
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
			"version": 336,
			"versionNonce": 344396518,
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
			"updated": 1709145733028,
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
			"version": 165,
			"versionNonce": 693401210,
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
			"updated": 1709145733028,
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
			"version": 206,
			"versionNonce": 489670182,
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
			"updated": 1709145733028,
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
			"version": 143,
			"versionNonce": 1664325434,
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
			"updated": 1709145733028,
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
			"version": 69,
			"versionNonce": 1289752934,
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
			"updated": 1709145733029,
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
			"version": 30,
			"versionNonce": 2112921594,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 38,
			"versionNonce": 249885862,
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
			"updated": 1709145733029,
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
			"version": 45,
			"versionNonce": 1972277434,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 92,
			"versionNonce": 1558933478,
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
			"updated": 1709145733029,
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
			"version": 32,
			"versionNonce": 1303406970,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 98,
			"versionNonce": 1929413414,
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
			"updated": 1709145733029,
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
			"version": 526,
			"versionNonce": 496577082,
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
			"updated": 1709145733029,
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
			"version": 83,
			"versionNonce": 59846246,
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
			"updated": 1709145733029,
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
			"version": 141,
			"versionNonce": 472634106,
			"isDeleted": false,
			"id": "7kTRAvCNeF-744I3kDpB2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 14.257636531607808,
			"y": 1256.080493818977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.6819189599425073,
			"height": 116.81728097277278,
			"seed": 829186493,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rA1d8EIg6sT8H5n5jc5qe",
				"focus": 0.015630360610552552,
				"gap": 12.296665217895395
			},
			"endBinding": {
				"elementId": "4mMcqnXB",
				"focus": -0.034399034174688994,
				"gap": 15.838769412848706
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
					3.6819189599425073,
					116.81728097277278
				]
			]
		},
		{
			"type": "text",
			"version": 858,
			"versionNonce": 1802138022,
			"isDeleted": false,
			"id": "02xK0Xsp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1838.7244977757318,
			"y": 1072.6869117422018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 680.2894287109375,
			"height": 120,
			"seed": 1990474941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which can be seen as a coordinate Gradient descent algorithm\n(Gradient descent algorithm except it only minimizes 1 direction at a\ntime then checks the errors of the previous point we ended up and\nminimizes in the other direction from there, kindof how each\nconsecutive hypothesis looks at previous predictions, sees the incorrect\nones and tries to correct those from that point, without affecting the correct ones)",
			"rawText": "Which can be seen as a coordinate Gradient descent algorithm\n(Gradient descent algorithm except it only minimizes 1 direction at a\ntime then checks the errors of the previous point we ended up and\nminimizes in the other direction from there, kindof how each\nconsecutive hypothesis looks at previous predictions, sees the incorrect\nones and tries to correct those from that point, without affecting the correct ones)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which can be seen as a coordinate Gradient descent algorithm\n(Gradient descent algorithm except it only minimizes 1 direction at a\ntime then checks the errors of the previous point we ended up and\nminimizes in the other direction from there, kindof how each\nconsecutive hypothesis looks at previous predictions, sees the incorrect\nones and tries to correct those from that point, without affecting the correct ones)",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "image",
			"version": 267,
			"versionNonce": 736846778,
			"isDeleted": false,
			"id": "_-GWeOxKE7bbcHSC1eBNn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -914.8999676292048,
			"y": 1460.0026187007077,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 376.24825014822216,
			"height": 55.51203690711475,
			"seed": 1858198301,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733029,
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
			"version": 544,
			"versionNonce": 1706642662,
			"isDeleted": false,
			"id": "2-axPBWT3YueVcPxPtKxM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1631.9406089556353,
			"y": 1204.7932526624184,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 273.0555505455843,
			"height": 223.5091804869097,
			"seed": 1077178739,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733029,
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
			"version": 667,
			"versionNonce": 1727716474,
			"isDeleted": false,
			"id": "bNqnFttI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1443.7892710748001,
			"y": 1363.899136821956,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 101.15939331054688,
			"height": 14.93789060186209,
			"seed": 699937363,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733029,
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
			"version": 883,
			"versionNonce": 1022041409,
			"isDeleted": false,
			"id": "rW5HlCV2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.737628846562739,
			"x": -1484.5438434013702,
			"y": 1347.9864903572168,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 61.255772077220485,
			"height": 9.045447902332535,
			"seed": 595347667,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710773657960,
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
			"version": 741,
			"versionNonce": 819008335,
			"isDeleted": false,
			"id": "E7YRTPsB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1479.3945254048754,
			"y": 1306.1965101679177,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 62.13391363543199,
			"height": 9.17512031435702,
			"seed": 1419883997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710773657960,
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
			"version": 238,
			"versionNonce": 239848294,
			"isDeleted": false,
			"id": "A1X5Y6hb1R4iKb1KfAuAQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1037.7302774810491,
			"y": 1119.7918119568722,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JoCP4ccU",
				"focus": 0.06259142712838395,
				"gap": 12.533644164189354
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
					-167.33364597021927,
					-0.4822295272915653
				]
			]
		},
		{
			"type": "text",
			"version": 529,
			"versionNonce": 632653306,
			"isDeleted": false,
			"id": "4mMcqnXB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199.29743431049496,
			"y": 1388.7365442045984,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 455.712890625,
			"height": 140,
			"seed": 1321117779,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7kTRAvCNeF-744I3kDpB2",
					"type": "arrow"
				}
			],
			"updated": 1709145733029,
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
			"version": 221,
			"versionNonce": 1590259366,
			"isDeleted": false,
			"id": "sYUVTVJWqnZzjReCTrIJI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -112.50765071657827,
			"y": 1531.476484282941,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 265.7375195092492,
			"height": 233.39909120918185,
			"seed": 2068868755,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733029,
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
			"version": 220,
			"versionNonce": 1606858426,
			"isDeleted": false,
			"id": "sL0krMXAgBl1EA3kadS61",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 50.04860402047427,
			"y": 1634.8696477868693,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 244,
			"versionNonce": 1848682982,
			"isDeleted": false,
			"id": "Q0x03s2Uqtq0wrBIDgy1u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 44.73415899201359,
			"y": 1644.612797005714,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 212,
			"versionNonce": 1240715130,
			"isDeleted": false,
			"id": "qPKECA4PfSQWwJma3fqjg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 58.31551850919095,
			"y": 1649.631995088149,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 229,
			"versionNonce": 1536064806,
			"isDeleted": false,
			"id": "oeiEK4qhROojBdZlc3jv-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2.740115179980876,
			"y": 1606.5759844945999,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 222,
			"versionNonce": 1216335930,
			"isDeleted": false,
			"id": "L-BGvF9PoODAkmLLg9gQb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 67.09197533290524,
			"y": 1581.441924636892,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 205,
			"versionNonce": 1548740710,
			"isDeleted": false,
			"id": "ynDZvfTcmkCUQpvY_N2Vq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 67.30864826271306,
			"y": 1595.7423380042085,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 236,
			"versionNonce": 1062058234,
			"isDeleted": false,
			"id": "InEcax4DjXdQntkfWxbtt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 53.87492661462784,
			"y": 1629.1099691946138,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 228,
			"versionNonce": 1883368358,
			"isDeleted": false,
			"id": "lBeDS3RC9LiVGIHHYzOhi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 53.224907825204355,
			"y": 1640.5936344744284,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 226,
			"versionNonce": 501254586,
			"isDeleted": false,
			"id": "rGLrHXRfRUt_5J61Qkjc1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 67.30864826271306,
			"y": 1653.1606644032825,
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
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 228,
			"versionNonce": 361858790,
			"isDeleted": false,
			"id": "24DOhCM0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 133.41213505182242,
			"y": 1606.5759844945997,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 68.43215942382812,
			"height": 40,
			"seed": 1023531923,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733029,
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
			"type": "arrow",
			"version": 84,
			"versionNonce": 1801142906,
			"isDeleted": false,
			"id": "M37Mq3Xc07HKP55IoOWcw",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -738.8292106269577,
			"y": 1538.856993808525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 2.7426785579584703,
			"height": 156.332677803631,
			"seed": 1981424442,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PLhvx5E1ua7UmjqBWaac6",
				"focus": 0.020338997102545973,
				"gap": 4.087273747854056
			},
			"endBinding": {
				"elementId": "tMDSEBnq",
				"focus": -0.002655208000952317,
				"gap": 9.916312460349673
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
					2.7426785579584703,
					156.332677803631
				]
			]
		},
		{
			"type": "text",
			"version": 293,
			"versionNonce": 2093726246,
			"isDeleted": false,
			"id": "tMDSEBnq",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1209.3502388211095,
			"y": 1705.1059840725056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 950.718994140625,
			"height": 75,
			"seed": 169162790,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "M37Mq3Xc07HKP55IoOWcw",
					"type": "arrow"
				},
				{
					"id": "mJ1xE9XlbEbtYmlsw7p9_",
					"type": "arrow"
				}
			],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Theoretically this converges to a solution exponentially with the amount of iterations\nall you really need to guarantee is that your weak learner is SLIGHTLY smarter than guessing\nand perform the algorithm to make a stronger learner",
			"rawText": "Theoretically this converges to a solution exponentially with the amount of iterations\nall you really need to guarantee is that your weak learner is SLIGHTLY smarter than guessing\nand perform the algorithm to make a stronger learner",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Theoretically this converges to a solution exponentially with the amount of iterations\nall you really need to guarantee is that your weak learner is SLIGHTLY smarter than guessing\nand perform the algorithm to make a stronger learner",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 48,
			"versionNonce": 1384178490,
			"isDeleted": false,
			"id": "mJ1xE9XlbEbtYmlsw7p9_",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -734.3776673790203,
			"y": 1787.203664198346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 2.1450773747980065,
			"height": 75.07770811793034,
			"seed": 677061990,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tMDSEBnq",
				"focus": 0.0034866440673484676,
				"gap": 7.09768012584027
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
					2.1450773747980065,
					75.07770811793034
				]
			]
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 1021150566,
			"isDeleted": false,
			"id": "9kk6Xuxt",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1215.4719720147737,
			"y": 1887.307275022253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 969.3388671875,
			"height": 50,
			"seed": 1337586470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QmUvhmjmVieNYHnrtTw4g",
					"type": "arrow"
				},
				{
					"id": "lsyvidf_OHcX-hONTAiac",
					"type": "arrow"
				}
			],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Its complexity (VC dimension) grows linearly with every iteration as we keep adding models\nto it, but the solution converges so much faster that this model is not very prone to overfitting",
			"rawText": "Its complexity (VC dimension) grows linearly with every iteration as we keep adding models\nto it, but the solution converges so much faster that this model is not very prone to overfitting",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Its complexity (VC dimension) grows linearly with every iteration as we keep adding models\nto it, but the solution converges so much faster that this model is not very prone to overfitting",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 39,
			"versionNonce": 766798842,
			"isDeleted": false,
			"id": "QmUvhmjmVieNYHnrtTw4g",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -727.2274094630269,
			"y": 1948.0844673081965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 5.005180541195273,
			"height": 85.08806920032089,
			"seed": 802233274,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733029,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9kk6Xuxt",
				"focus": -0.003025030174971618,
				"gap": 10.777192285943556
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
					5.005180541195273,
					85.08806920032089
				]
			]
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 118745254,
			"isDeleted": false,
			"id": "S3dYEAMZ",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -988.4718932284723,
			"y": 2059.628490797693,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 532.4993286132812,
			"height": 25,
			"seed": 1096575526,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Small VC implies little deviation from the empirical risk",
			"rawText": "Small VC implies little deviation from the empirical risk",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Small VC implies little deviation from the empirical risk",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 126,
			"versionNonce": 318299322,
			"isDeleted": false,
			"id": "lsyvidf_OHcX-hONTAiac",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -243.6478034587742,
			"y": 1909.7436308610127,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 93.81838853779777,
			"height": 124.78756533668252,
			"seed": 1840544486,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9kk6Xuxt",
				"focus": -0.45685431618538036,
				"gap": 2.4853013684994494
			},
			"endBinding": {
				"elementId": "0lHwTIOD",
				"focus": -1.0910627076239034,
				"gap": 22.965849054394994
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
					81.97723270293011,
					2.7325744234310605
				],
				[
					93.81838853779777,
					124.78756533668252
				]
			]
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 1528554470,
			"isDeleted": false,
			"id": "0lHwTIOD",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -134.1335255859234,
			"y": 1911.5653471433002,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 383.95953369140625,
			"height": 100,
			"seed": 64140730,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lsyvidf_OHcX-hONTAiac",
					"type": "arrow"
				}
			],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "BUt this does not explain\na weird phenomena with boosting\nsuch that even at very high complexity\nthe test error does not shoot up!",
			"rawText": "BUt this does not explain\na weird phenomena with boosting\nsuch that even at very high complexity\nthe test error does not shoot up!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BUt this does not explain\na weird phenomena with boosting\nsuch that even at very high complexity\nthe test error does not shoot up!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 143,
			"versionNonce": 1609643386,
			"isDeleted": false,
			"id": "E6T2F9bSj8YVjYIN_09gW",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -300.43729612487994,
			"y": 2042.2712533452136,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 304.8591949723817,
			"height": 251.302849909666,
			"seed": 1164340390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DkgumDsrKMo2wIGqv-klb",
					"type": "arrow"
				}
			],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "396e5731d9c09f9dbccfc9cc883348c8caacf0e8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 28,
			"versionNonce": 990017318,
			"isDeleted": false,
			"id": "NrOUbC7zK3Gqqe4aN6ciR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -40.4482233864577,
			"y": 2216.680551796326,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 85.16602714037901,
			"height": 29.954947476961024,
			"seed": 519505658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
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
					85.16602714037901,
					-29.954947476961024
				]
			]
		},
		{
			"type": "text",
			"version": 6,
			"versionNonce": 1172338234,
			"isDeleted": false,
			"id": "yoF9LoIF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 51.88542525951061,
			"y": 2164.406231689473,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 44.39994812011719,
			"height": 25,
			"seed": 914481978,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "test",
			"rawText": "test",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "test",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 32,
			"versionNonce": 1597284966,
			"isDeleted": false,
			"id": "DkgumDsrKMo2wIGqv-klb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -229.57553882923042,
			"y": 2228.4275900225853,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 48.16285672766264,
			"height": 69.30752553492903,
			"seed": 1063174374,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "E6T2F9bSj8YVjYIN_09gW",
				"focus": -0.164849217215579,
				"gap": 4.161012302634617
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
					-48.16285672766264,
					69.30752553492903
				]
			]
		},
		{
			"type": "text",
			"version": 7,
			"versionNonce": 1437179642,
			"isDeleted": false,
			"id": "0BuWYrpZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -319.42627764695027,
			"y": 2315.3556728969033,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 46.95994567871094,
			"height": 25,
			"seed": 2123450298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "train",
			"rawText": "train",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "train",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 27,
			"versionNonce": 1786733990,
			"isDeleted": false,
			"id": "6X6UQ_GK5DxjpgQctXCgK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -145.58421551147734,
			"y": 2260.731945144798,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 27.605539831709052,
			"height": 88.1027866969439,
			"seed": 551274406,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
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
					27.605539831709052,
					88.1027866969439
				]
			]
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 198160314,
			"isDeleted": false,
			"id": "fdf412IT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -289.16850073419016,
			"y": 2353.5335471322455,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 382.319580078125,
			"height": 100,
			"seed": 378656890,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-wZKUjVRXGYzOPeoUcM82",
					"type": "arrow"
				}
			],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "defeats the whole concept\nof occam's razor where the training\nerror goes to zero but the test error\nkeeps going down",
			"rawText": "defeats the whole concept\nof occam's razor where the training\nerror goes to zero but the test error\nkeeps going down",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "defeats the whole concept\nof occam's razor where the training\nerror goes to zero but the test error\nkeeps going down",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 100,
			"versionNonce": 504348902,
			"isDeleted": false,
			"id": "-wZKUjVRXGYzOPeoUcM82",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 99.87443710850903,
			"y": 2394.371842188617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 89.46011937483848,
			"height": 0.2867278720614195,
			"seed": 1169164262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fdf412IT",
				"focus": -0.16848596551958506,
				"gap": 6.723357764574189
			},
			"endBinding": {
				"elementId": "S4a1p1YC",
				"focus": 0.007881762395973057,
				"gap": 15.144712255474701
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
					89.46011937483848,
					-0.2867278720614195
				]
			]
		},
		{
			"type": "text",
			"version": 322,
			"versionNonce": 1551214714,
			"isDeleted": false,
			"id": "S4a1p1YC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 204.47926873882227,
			"y": 2368.3983732284655,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 525.3394165039062,
			"height": 50,
			"seed": 365633530,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-wZKUjVRXGYzOPeoUcM82",
					"type": "arrow"
				}
			],
			"updated": 1709145733030,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Hard-margin Boosting does overfit but that dataset\nwas just uniquely non-messy which caused this result",
			"rawText": "Hard-margin Boosting does overfit but that dataset\nwas just uniquely non-messy which caused this result",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hard-margin Boosting does overfit but that dataset\nwas just uniquely non-messy which caused this result",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "ellipse",
			"version": 164,
			"versionNonce": 225621030,
			"isDeleted": false,
			"id": "x0Jrc9FbfVZ9rts511LhY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 366.0376954486668,
			"y": 2532.826016879499,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 1010409126,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 1063160122,
			"isDeleted": false,
			"id": "cglgVPXUG7d31oifceOmA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 428.89917278106213,
			"y": 2492.9066845589264,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 1629055866,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 1385512806,
			"isDeleted": false,
			"id": "Ie-oNTHPYD9rVeOoLNR_0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 322.44761992620283,
			"y": 2555.3093189910855,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 720701434,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 1005408762,
			"isDeleted": false,
			"id": "QYKw96CxQ4GIWN1pw_FP0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 392.1917407621452,
			"y": 2499.3304851622374,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 1723884774,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 1103389350,
			"isDeleted": false,
			"id": "-p_7L75fEzDpG5DXNHP49",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 350.8958797408635,
			"y": 2480.9767691527786,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 68558522,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 1965359802,
			"isDeleted": false,
			"id": "sdLPfVCMcDXkMvyA_GB4O",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 338.9659643347155,
			"y": 2510.3427147679126,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 188477882,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 497884646,
			"isDeleted": false,
			"id": "BN_gDE-qGi56ey1SgyGBI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 416.05157157444114,
			"y": 2439.6809081314973,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 285380390,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 900242298,
			"isDeleted": false,
			"id": "HbnIRkzR-D6WQTaUTyzzo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 297.67010331343397,
			"y": 2477.306025950887,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 1446623738,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 1264349478,
			"isDeleted": false,
			"id": "vFSQ4NZXCBGJ_4fxtsznp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 379.3441395555242,
			"y": 2458.9523099414287,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 1651708646,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 2075860026,
			"isDeleted": false,
			"id": "zfRRiUiG4dPj8_b0-TmPc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 342.6367075366072,
			"y": 2447.9400803357535,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 265032038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 104815718,
			"isDeleted": false,
			"id": "MKkycRMMMxb9aHtwWXZzw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 295.83473171248806,
			"y": 2528.696430777371,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 960455610,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 166,
			"versionNonce": 88048890,
			"isDeleted": false,
			"id": "vqFjMcx9Zk338Q_ll5KkA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 443.5821455886289,
			"y": 2465.376110544739,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 1241152806,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 167,
			"versionNonce": 337829798,
			"isDeleted": false,
			"id": "rhhgIx73EkoYGzEyMjciC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 400.90975586663797,
			"y": 2602.5701377154414,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 880797862,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1538839994,
			"isDeleted": false,
			"id": "98hHxsRVeqmS2Xtq4a0k9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 445.8763600898112,
			"y": 2586.510636207165,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 308527674,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 2033449702,
			"isDeleted": false,
			"id": "iI_DV8J_8xjwajQ0OOj2U",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 439.4525594865006,
			"y": 2618.6296392237177,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 2143508134,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1615466106,
			"isDeleted": false,
			"id": "XcDEXbLwkF1nvCRRVWJcs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 490.8429643129846,
			"y": 2597.5228658128403,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1103627258,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 738176550,
			"isDeleted": false,
			"id": "wR1n4q6LBQ7XQdzQZ_6_j",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 542.2333691394683,
			"y": 2552.5562615896665,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1483778278,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1471557434,
			"isDeleted": false,
			"id": "w9mhgcZ7V3SAjmViUAqgS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 541.3156833389953,
			"y": 2614.9588960218257,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1357441530,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1232271718,
			"isDeleted": false,
			"id": "SNmVzlmA21WEcr5S8VV4y",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 575.2700579564935,
			"y": 2510.3427147679117,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1532092774,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1986017274,
			"isDeleted": false,
			"id": "Xsvk6FBShQ7aERBjwtqvu",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 555.0809703460891,
			"y": 2580.086835603855,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1630145658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1222302886,
			"isDeleted": false,
			"id": "xSkhhkfhZu6FtQEU0FtnV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 537.6449401371035,
			"y": 2497.4951135612914,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 254869562,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1816864954,
			"isDeleted": false,
			"id": "LdJB01AE_LL2bj9M5rctX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 585.3646017616957,
			"y": 2466.293796345212,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1325796538,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 803493862,
			"isDeleted": false,
			"id": "DQu1ZcJbBcwQ0nPu8J6Hd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 613.8128615763562,
			"y": 2569.992291798653,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 1533969446,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 169,
			"versionNonce": 1897529722,
			"isDeleted": false,
			"id": "KMB4IiUtjv5f62Z82_tHL",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 522.0442815290639,
			"y": 2521.354944373588,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 23.859830812295968,
			"height": 21.106773410877395,
			"seed": 703247610,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709145733030,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 168,
			"versionNonce": 1184656166,
			"isDeleted": false,
			"id": "UF0yM8d9PoQAC7AwN5Exh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 491.3018072132206,
			"y": 2557.1446905920307,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 17.436030208985585,
			"height": 13.765287007093777,
			"seed": 647319866,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 331,
			"versionNonce": 1343210042,
			"isDeleted": false,
			"id": "uQqzmo6twnljdeeYA2irv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 354.12594350265294,
			"y": 2619.396578299633,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 214.92380474156175,
			"height": 187.54497611206352,
			"seed": 94697274,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					60.91789370063384,
					-54.073186543259
				],
				[
					117.04449239110545,
					-49.28189153309677
				],
				[
					163.5885010612526,
					-32.854594355397694
				],
				[
					169.74873750288953,
					-70.50048372095807
				],
				[
					139.63202601044145,
					-108.14637308651845
				],
				[
					214.92380474156175,
					-187.54497611206352
				]
			]
		},
		{
			"type": "text",
			"version": 226,
			"versionNonce": 1265636966,
			"isDeleted": false,
			"id": "WIek8J10",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 154.25974475687406,
			"y": 2671.41635269568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 636.5592651367188,
			"height": 100,
			"seed": 522328102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Correctly classifying every point where there exists an outlier is\nliterally overfitting!!!\nthus Boosting can overfit and that graph is just an odd\ncoincidence ",
			"rawText": "Correctly classifying every point where there exists an outlier is\nliterally overfitting!!!\nthus Boosting can overfit and that graph is just an odd\ncoincidence ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Correctly classifying every point where there exists an outlier is\nliterally overfitting!!!\nthus Boosting can overfit and that graph is just an odd\ncoincidence ",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 141,
			"versionNonce": 1417295718,
			"isDeleted": false,
			"id": "l1NoAsWMc6r2DdsU-7owI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1033.964934048395,
			"y": 1505.9760822317828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 986.0916771469983,
			"height": 4.85175548915754,
			"seed": 1844941158,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709146413172,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PLhvx5E1ua7UmjqBWaac6",
				"focus": -0.9404856687475102,
				"gap": 4.695049318346491
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
					-986.0916771469983,
					-4.85175548915754
				]
			]
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 657217958,
			"isDeleted": false,
			"id": "IaFw5o5Y",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1705.8653868330505,
			"y": 1511.381205021256,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 324.91961669921875,
			"height": 125,
			"seed": 1730909286,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets mathematically prove that \n\n\n\nis true",
			"rawText": "Lets mathematically prove that \n\n\n\nis true",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets mathematically prove that \n\n\n\nis true",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 331,
			"versionNonce": 1939602362,
			"isDeleted": false,
			"id": "4cZGZoTQYCm7ry2pGSZyq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1735.6798246719304,
			"y": 1540.9315140181582,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 376.24825014822216,
			"height": 55.51203690711475,
			"seed": 1923107942,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b3c844f070af544f0d4b450f7f99d4d3cddd93b4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 553530598,
			"isDeleted": false,
			"id": "e4Dx9919",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2743.59202846304,
			"y": 1469.06654282039,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 687.059326171875,
			"height": 75,
			"seed": 1657651450,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Firstly we would need to rewrite the objective function in\na different way to help us simplify, then we will compute the gradient\nand try to find the minima of the function",
			"rawText": "Firstly we would need to rewrite the objective function in\na different way to help us simplify, then we will compute the gradient\nand try to find the minima of the function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Firstly we would need to rewrite the objective function in\na different way to help us simplify, then we will compute the gradient\nand try to find the minima of the function",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 463,
			"versionNonce": 1589362214,
			"isDeleted": false,
			"id": "PIdS-cZnppVQYU0IW9yGG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2898.5755210648126,
			"y": 1544.0665433660238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 997.0263119970798,
			"height": 686.5987551728143,
			"seed": 6797562,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709146371371,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 170,
			"versionNonce": 309504038,
			"isDeleted": false,
			"id": "Rq4nPHmf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2894.044049042492,
			"y": 1553.7016202237774,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 108.4435727193155,
			"height": 53.43596336893806,
			"seed": 63531,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e8e50f552e6cc662d6ba9c18ae03e1e8a3360d0a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 292,
			"versionNonce": 25679162,
			"isDeleted": false,
			"id": "FSesPlrIqnCUBvKVMtHMD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2718.093110662388,
			"y": 1556.2561358319388,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 338.9257290213298,
			"height": 54.96092903048592,
			"seed": 1971542950,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bbb4307723475d60c528a637ed8813a268aa124b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 378,
			"versionNonce": 460764006,
			"isDeleted": false,
			"id": "iO4Fn56RVowCudGjJGmvh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2320.791651506023,
			"y": 1551.864366834198,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 373.5854454935065,
			"height": 62.47248252399774,
			"seed": 1762338406,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3d26e6632cc38bcc916ec0c560a08e8759dc0c32",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 427,
			"versionNonce": 51191290,
			"isDeleted": false,
			"id": "dWnSnjL_B6YMKjvQR-5xX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2312.333168945524,
			"y": 1631.6002657867532,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 369.81810104266685,
			"height": 63.10889096291243,
			"seed": 283371898,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d9cc354bd639ae8a5c152c23dc0dfe708282a4e3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 508,
			"versionNonce": 1448564390,
			"isDeleted": false,
			"id": "shcEG2WlOZZrFtr7est1N",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2890.987419120941,
			"y": 1720.461540748198,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 874.9256277937978,
			"height": 61.35523336562396,
			"seed": 1057272486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d38d65d325246d6f1203f7d3eb040d6b28250bf9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 240,
			"versionNonce": 1584090810,
			"isDeleted": false,
			"id": "o6pOce8O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2889.3168898112845,
			"y": 1786.0101521152628,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 426.6212644873269,
			"height": 64.44429977149953,
			"seed": 29578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145733031,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e78a2aa95efba5137be8393208a60853df47bb57",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 327,
			"versionNonce": 643325562,
			"isDeleted": false,
			"id": "snEzClAl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2883.048136268008,
			"y": 1906.950809482939,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 665.0559018279657,
			"height": 70.75062785403891,
			"seed": 69579,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709145870871,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "81047ef2c59328975cc77eef6e42a628fb3eed4d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 145,
			"versionNonce": 1166450170,
			"isDeleted": false,
			"id": "_h5Q5MnqbU1AhSOt0Tn9w",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2747.43703281337,
			"y": 1904.4320849239612,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 103.67668720929805,
			"height": 73.46626179731766,
			"seed": 2027912762,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145878168,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					103.67668720929805,
					73.46626179731766
				]
			]
		},
		{
			"type": "line",
			"version": 82,
			"versionNonce": 511684198,
			"isDeleted": false,
			"id": "9wj8kbfD1XkQmb2lW2B9E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2767.50247222149,
			"y": 1928.2843869376552,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 13.76367313095352,
			"height": 22.365968837798846,
			"seed": 1830973178,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709145875068,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					13.76367313095352,
					22.365968837798846
				]
			]
		},
		{
			"type": "image",
			"version": 190,
			"versionNonce": 1375789114,
			"isDeleted": false,
			"id": "Mlk9ifuD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2877.330658718334,
			"y": 1995.1130698117022,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 431.0718243441809,
			"height": 70.64387756810991,
			"seed": 99246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709146035972,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1fb55b89cae454c0fc9f64501d4d590fea3d27b0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 278,
			"versionNonce": 511210426,
			"isDeleted": false,
			"id": "i85xMQQCrKgAD6dJsXt-k",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2895.185235274575,
			"y": 2073.2187143676833,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 548.3787729959713,
			"height": 55.53202764516165,
			"seed": 1197190246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709146034739,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d346b725860c04b0b4c62808ad09743c1858d37",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 135,
			"versionNonce": 1872161594,
			"isDeleted": false,
			"id": "0sPpfSUk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2886.438618415201,
			"y": 2144.542995694782,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 260.4611295375953,
			"height": 20.88603397235434,
			"seed": 90896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709146235538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bf272e86152d7c7c651df1b6992101469a2bad33",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 192,
			"versionNonce": 1785742458,
			"isDeleted": false,
			"id": "kTSqsoyjGwaLyPDUr-P57",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2885.013508792134,
			"y": 2176.835908095134,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 144.2497833620557,
			"height": 37.712361663282536,
			"seed": 1902394746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aPhadVJTQp-qcQsM0Y7gb",
					"type": "arrow"
				}
			],
			"updated": 1709146285722,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "310bc8e0f146056c50a68e873145de4fdd6ad085",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 117,
			"versionNonce": 1990961978,
			"isDeleted": false,
			"id": "aPhadVJTQp-qcQsM0Y7gb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2733.4663358880634,
			"y": 2192.7765386619535,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#b2f2bb",
			"width": 73.12210562796008,
			"height": 0.54625797069275,
			"seed": 253855590,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709146314067,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kTSqsoyjGwaLyPDUr-P57",
				"focus": -0.18910719856740912,
				"gap": 7.297389542015026
			},
			"endBinding": {
				"elementId": "iP4V0qbokLC215Dtvw2Zh",
				"focus": -0.052784291761552575,
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
					73.12210562796008,
					0.54625797069275
				]
			]
		},
		{
			"type": "image",
			"version": 243,
			"versionNonce": 1463775334,
			"isDeleted": false,
			"id": "iP4V0qbokLC215Dtvw2Zh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2659.3442302601034,
			"y": 2176.322286071066,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 162.84962388657826,
			"height": 33.405051053657075,
			"seed": 187224614,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aPhadVJTQp-qcQsM0Y7gb",
					"type": "arrow"
				},
				{
					"id": "usRMgZIrN11iL4iZ7zWoK",
					"type": "arrow"
				}
			],
			"updated": 1709146318484,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d24ff7f5a4fdc0f4b607f015cec1325f961335a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 76,
			"versionNonce": 207017254,
			"isDeleted": false,
			"id": "usRMgZIrN11iL4iZ7zWoK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2494.7352646989075,
			"y": 2193.4309040807607,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#b2f2bb",
			"width": 71.67114626841067,
			"height": 0.46607484363221374,
			"seed": 823239866,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709146347300,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "iP4V0qbokLC215Dtvw2Zh",
				"focus": -0.00777946439645112,
				"gap": 1.7593416746176445
			},
			"endBinding": {
				"elementId": "FdvBn_rsOQP98K2Wr8hV5",
				"focus": -0.0612272660831544,
				"gap": 8.448976406129987
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
					71.67114626841067,
					0.46607484363221374
				]
			]
		},
		{
			"type": "image",
			"version": 276,
			"versionNonce": 751543718,
			"isDeleted": false,
			"id": "FdvBn_rsOQP98K2Wr8hV5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2414.615142024367,
			"y": 2175.3683740333904,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 151.55490387608342,
			"height": 35.894582496967125,
			"seed": 2022195750,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "usRMgZIrN11iL4iZ7zWoK",
					"type": "arrow"
				},
				{
					"id": "QLOh43zOovm_dwmM53QDZ",
					"type": "arrow"
				}
			],
			"updated": 1709146351847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8476b552a6502fccd43cd3a7e622dc8257cdebfb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 42,
			"versionNonce": 1366983782,
			"isDeleted": false,
			"id": "QLOh43zOovm_dwmM53QDZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2259.4346343601405,
			"y": 2196.2242021216603,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#b2f2bb",
			"width": 83.18415361790676,
			"height": 0.5817073679577334,
			"seed": 74572026,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709146354181,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FdvBn_rsOQP98K2Wr8hV5",
				"focus": 0.18746359338326063,
				"gap": 3.6256037881428256
			},
			"endBinding": {
				"elementId": "Zo3FNxhSks063PFF-kXIj",
				"focus": -0.03269329843496143,
				"gap": 4.207311156099081
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
					83.18415361790676,
					-0.5817073679577334
				]
			]
		},
		{
			"type": "image",
			"version": 312,
			"versionNonce": 498665382,
			"isDeleted": false,
			"id": "Zo3FNxhSks063PFF-kXIj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2166.614057279451,
			"y": 2175.14671187482,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 140.6966792627159,
			"height": 38.664736285937195,
			"seed": 1504637990,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QLOh43zOovm_dwmM53QDZ",
					"type": "arrow"
				}
			],
			"updated": 1709146354181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2e71367acd6baecb5a956e33ef69fab7df2f85d3",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#3bc9db",
		"currentItemBackgroundColor": "#b2f2bb",
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
		"scrollX": 3477.812905585986,
		"scrollY": 453.13501561644557,
		"zoom": {
			"value": 0.30000000000000004
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