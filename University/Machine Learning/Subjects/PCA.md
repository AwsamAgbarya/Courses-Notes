---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Principal component analysis ^VbfAM2aO

What is the motivation to seek PCA? ^O1txWuPW

Often times in machine learning we have to deal with issues that involve
data with really high dimensions, and a much lower amount of available data
N<<D
i.e Face Recognition
The amount of data needed for a reliable result (e.g. no overfitting)
often grows exponentially with the dimensionality ^QSLlecAj

Can we try our previous models? ^AfNDVTA7

standard classification techniques become ill defined or
sometimes ill-conditions for cases where we have high dimensional
data
for example when using a Bayes classifier we often need to 
estimate the covariance matrix


estimating the covariance in this way only works when D<N
and is only really accurate when D<<N ^SXbCGUMe

Well what can we do? ^AzmY3MHq

Preform PCA to extract the key dimensions (features) that represent
the data the best, getting rid of all the other unecessary
irrelevant features that are often regarded as noise

we ask our selves, which lower dimensional plane fits the data the best
such that the noise is reduced and the important info is reserved? ^No6tqKWV

We want to find a subspace such that ^Y0JxAF5I

Minimum distance to
the original data ^UxsIN7QM

and ^Rn86pbZk

Data projected
has maximum variance ^CVctFYtn

projection
of all datapoints
onto w ^vqYE8vEE

The length of the
projected datapoints
onto w ^G66GX3dQ

if the data isnt centered
then we have use the expectation
of the datapoints ^j6aQgVSJ

= ^vsS1E8Tk

You can actually derive on of these equations
from the other, so although they strive for different
goals they end up achieving the same one! ^lNzIiHaP

What happens if we dont center the data? ^MZVK4oEJ

what we need ^Dm0tPI4D

what we get ^b3BsXysy

note that this method is not very robust!! ^pJWcC8x6

centered i.e the mean is 0). The covariance matrix does not depend on w and can be ^kXklT2FM

where Σ is the covariance matrix (recall: the data is assumed to be ^zykM2AsW

precomputed ^6OY1Nj9o

We Apply the Lagrange method! ^T6Rndoek

Notice that the solution of PCA is the eigen vector of the cov
matrix! This makes so much sense because according to linear
algebra, the Eigenvectors are the vectors that do not get
transformed by the cov matrix, only scaled! (Rotation axis)

The cov matrix tells us how scaled the dsitribution is in each 
direction and how sheared it is in each direction

Our eigenvector w is Scaled by this transformation and THUS
it means that its going along its "stretched" direction
and we seek the K most important (highest scaled) vectors ^oDBdCqop

Finding multiple PCA components ^WjniqIi9

1. Find Highest PCA ^uMnh8fH9

2. Remove it from the data ^xTQiZY5L

X = X - W * W * X ^99hlrZff

T ^wW674Nte

Projection in that dimension ^abjC5Xzd

Compute leading eigenvector ^axxAlj8A

3. Take your h leading PCA and use
them to describe the data ^SBwsj06O

Ways to compute PCA? ^3Ve5EQd8

Singular Value Decomposition ^FfapMSBB

A singular value decomposition factorizes a matrix M as UΛV = M where ^IlwMj0Y5

U contains the eigenvectors of MM ^cw2OGd0R

V contains the eigenvectors of MM ^ZjWlYP2s

The square roots of the eigenvalues of MM are on the diagonal of Λ ^XLKzSFif

T ^aIZhEksf

T ^mP6mCErz

T ^d0QOI60u

Setting M =     and computing SVD ^rESXPR6o

Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,
i.e. the principal components
and
Matrix Λ contains the square roots of the
corresponding maximum eigenvalues on the diagonal ^J3UsBnZS

According to the definition
of the covariance ^B6v3IO8D

SVD is computationally faster and more stable than covariance
computation + eigenvalue decomposition

except!
for datasets where the dimensionality is as high
as the number of samples then the complexity is O(d^3) ^M1zDgOxG

Notice that we only ever need
the leading k PCAs, but SVD computes
all of them!


lets improve on that! ^dJ0lwqyr

Power iteraton Algorithm ^PG0Ls5k0

Initialize your w as a unit norm vector!

Multiply the covariance matrix with w


Proceed to normalize the result by dividing it with one of its components




Repeat this set using previous PCA result as the new w ^ILXywG7o

This always converges and converges exponentially fast! ^YX1xzOer


# Embedded files
066992a4d970f0027296267582a885f247595db4: [[Pasted Image 20231227142137_496.png]]
ff4f59a1178f5557483a53dc5e4c7f996acc3fb1: [[Pasted Image 20231227142616_559.png]]
88c3e6446be853083ff1d93cfb270d69b83fa76d: [[Pasted Image 20231227143404_617.png]]
0c8a557654a8f5a094d2d9dd7aa6226c994e7912: [[Pasted Image 20231227143404_633.png]]
1dd57480649105e90f577b40329e68d074d4d6ea: [[Pasted Image 20231227143506_637.png]]
b5687b8bf8eb523359857ef85d33c56a75b46968: [[Pasted Image 20231227143636_650.png]]
cc0bd69983063231b46c45e104c24fdbc71e4d2d: [[Pasted Image 20231227143651_661.png]]
466eaf764d8b9c54f2ded0eb206baf1409cd0cd6: [[Pasted Image 20231227143759_689.png]]
568037a5baf496cd762db98b9c1fcfb979c241b2: [[Pasted Image 20231227143844_702.png]]
568403757cb500032d3f0b11d03a10b18781321c: [[Pasted Image 20231227144110_757.png]]
63f49e2afc776b649af1373f0068efb0acfe7778: [[Pasted Image 20231227144843_816.png]]
33565dae8c199d8f158838e59cb325a6d7fc7a2a: [[Pasted Image 20231227145330_848.png]]
8db0a71f5f2e63fb68ef6c19cfee4d258b539a26: [[Pasted Image 20231227145346_863.png]]
a2df7da46a259498afb1f8149aa53cc80c2103f8: [[Pasted Image 20231227150830_018.png]]
01852b012b4b1455db02049423e1202c2dc32f0c: [[Pasted Image 20231227151518_103.png]]
0af7a45751872f28d33c6b6bd230b3a4c819d169: [[Pasted Image 20231227152406_196.png]]
f9cfa63a7a70cb62bf28447fba1b45ceddbce43b: [[Pasted Image 20231227152533_220.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"id": "V1QpEfyGHj6r-AHKom7vo",
			"type": "image",
			"x": 1748.8812064631773,
			"y": 2608.6908107709974,
			"width": 42.38003955272794,
			"height": 39.12003651021041,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1754218521,
			"version": 152,
			"versionNonce": 1781489369,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "01852b012b4b1455db02049423e1202c2dc32f0c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "25CtriLNqHEhyZ_KXwsL4",
			"type": "rectangle",
			"x": -1120.4207010807058,
			"y": 1050.73319048432,
			"width": 562.840471147974,
			"height": 532.4166618967322,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1990241431,
			"version": 567,
			"versionNonce": 634461817,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-nNjNa1-BfKXZepbqGtZo",
					"type": "arrow"
				}
			],
			"updated": 1703685784310,
			"link": null,
			"locked": false
		},
		{
			"id": "NTmx3hfR6gJYwm0rRUxid",
			"type": "ellipse",
			"x": -302.8717948717949,
			"y": -480.9230769230769,
			"width": 437,
			"height": 205,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 299449881,
			"version": 188,
			"versionNonce": 801241239,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "VbfAM2aO"
				}
			],
			"updated": 1703684627531,
			"link": null,
			"locked": false
		},
		{
			"id": "VbfAM2aO",
			"type": "text",
			"x": -213.21715585793055,
			"y": -413.40152199469804,
			"width": 257.68505859375,
			"height": 70,
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
			"seed": 946719481,
			"version": 175,
			"versionNonce": 535347289,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Principal component\nanalysis",
			"rawText": "Principal component analysis",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 60,
			"containerId": "NTmx3hfR6gJYwm0rRUxid",
			"originalText": "Principal component analysis",
			"lineHeight": 1.25
		},
		{
			"id": "O1txWuPW",
			"type": "text",
			"x": -1222.6666666666672,
			"y": -185,
			"width": 517.3302001953125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1594093273,
			"version": 169,
			"versionNonce": 1078250935,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "What is the motivation to seek PCA?",
			"rawText": "What is the motivation to seek PCA?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "What is the motivation to seek PCA?",
			"lineHeight": 1.25
		},
		{
			"id": "QSLlecAj",
			"type": "text",
			"x": -1354.6666666666672,
			"y": -151,
			"width": 759.5191040039062,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1003707415,
			"version": 346,
			"versionNonce": 1837190457,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "djI-dvvGzKocn9NqHx712",
					"type": "arrow"
				}
			],
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Often times in machine learning we have to deal with issues that involve\ndata with really high dimensions, and a much lower amount of available data\nN<<D\ni.e Face Recognition\nThe amount of data needed for a reliable result (e.g. no overfitting)\noften grows exponentially with the dimensionality",
			"rawText": "Often times in machine learning we have to deal with issues that involve\ndata with really high dimensions, and a much lower amount of available data\nN<<D\ni.e Face Recognition\nThe amount of data needed for a reliable result (e.g. no overfitting)\noften grows exponentially with the dimensionality",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "Often times in machine learning we have to deal with issues that involve\ndata with really high dimensions, and a much lower amount of available data\nN<<D\ni.e Face Recognition\nThe amount of data needed for a reliable result (e.g. no overfitting)\noften grows exponentially with the dimensionality",
			"lineHeight": 1.25
		},
		{
			"id": "djI-dvvGzKocn9NqHx712",
			"type": "arrow",
			"x": -583.8095238095235,
			"y": -121.51990911825001,
			"width": 174.9078947368419,
			"height": 1.3793125503489136,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 468020215,
			"version": 657,
			"versionNonce": 535822039,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					174.9078947368419,
					1.3793125503489136
				]
			],
			"lastCommittedPoint": [
				169.33333333333337,
				-1.3333333333333712
			],
			"startBinding": {
				"elementId": "QSLlecAj",
				"focus": -0.5899895352015805,
				"gap": 11.338038853237435
			},
			"endBinding": {
				"elementId": "SXbCGUMe",
				"focus": 0.29032141610609985,
				"gap": 9.015770627741404
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "AfNDVTA7",
			"type": "text",
			"x": -310.4384605771013,
			"y": -244.0119047619051,
			"width": 445.25787353515625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1242342361,
			"version": 223,
			"versionNonce": 372588057,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Can we try our previous models?",
			"rawText": "Can we try our previous models?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Can we try our previous models?",
			"lineHeight": 1.25
		},
		{
			"id": "SXbCGUMe",
			"type": "text",
			"x": -399.88585844494014,
			"y": -196.67857142857173,
			"width": 634.8193359375,
			"height": 225,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 999683191,
			"version": 446,
			"versionNonce": 22547447,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "djI-dvvGzKocn9NqHx712",
					"type": "arrow"
				},
				{
					"id": "yMdhAglt4OcT7fTzqBz_A",
					"type": "arrow"
				}
			],
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "standard classification techniques become ill defined or\nsometimes ill-conditions for cases where we have high dimensional\ndata\nfor example when using a Bayes classifier we often need to \nestimate the covariance matrix\n\n\nestimating the covariance in this way only works when D<N\nand is only really accurate when D<<N",
			"rawText": "standard classification techniques become ill defined or\nsometimes ill-conditions for cases where we have high dimensional\ndata\nfor example when using a Bayes classifier we often need to \nestimate the covariance matrix\n\n\nestimating the covariance in this way only works when D<N\nand is only really accurate when D<<N",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 218,
			"containerId": null,
			"originalText": "standard classification techniques become ill defined or\nsometimes ill-conditions for cases where we have high dimensional\ndata\nfor example when using a Bayes classifier we often need to \nestimate the covariance matrix\n\n\nestimating the covariance in this way only works when D<N\nand is only really accurate when D<<N",
			"lineHeight": 1.25
		},
		{
			"id": "FePwc-OzEhQirQT4lBYbT",
			"type": "image",
			"x": -135.02614587315708,
			"y": -65.77506265664186,
			"width": 114.78412132024972,
			"height": 44.26315789473682,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 692693783,
			"version": 87,
			"versionNonce": 1761088249,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "066992a4d970f0027296267582a885f247595db4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "yMdhAglt4OcT7fTzqBz_A",
			"type": "arrow",
			"x": 239.0681190154886,
			"y": -118.13231700563065,
			"width": 219.71800398730073,
			"height": 1.3095821134157148,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1513139287,
			"version": 459,
			"versionNonce": 1350661399,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					219.71800398730073,
					1.3095821134157148
				]
			],
			"lastCommittedPoint": [
				224.61538461538476,
				1.5384615384615472
			],
			"startBinding": {
				"elementId": "SXbCGUMe",
				"focus": -0.3135733956626857,
				"gap": 4.134641522928746
			},
			"endBinding": {
				"elementId": "No6tqKWV",
				"focus": 0.7354998813769921,
				"gap": 16.69006063484494
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "AzmY3MHq",
			"type": "text",
			"x": 666.9621032965887,
			"y": -180.85502217081216,
			"width": 294.98126220703125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1652887159,
			"version": 93,
			"versionNonce": 172837849,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Well what can we do?",
			"rawText": "Well what can we do?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Well what can we do?",
			"lineHeight": 1.25
		},
		{
			"id": "No6tqKWV",
			"type": "text",
			"x": 475.47618363763434,
			"y": -132.87931366878774,
			"width": 711.7992553710938,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 395573625,
			"version": 435,
			"versionNonce": 81836599,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "yMdhAglt4OcT7fTzqBz_A",
					"type": "arrow"
				}
			],
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Preform PCA to extract the key dimensions (features) that represent\nthe data the best, getting rid of all the other unecessary\nirrelevant features that are often regarded as noise\n\nwe ask our selves, which lower dimensional plane fits the data the best\nsuch that the noise is reduced and the important info is reserved?",
			"rawText": "Preform PCA to extract the key dimensions (features) that represent\nthe data the best, getting rid of all the other unecessary\nirrelevant features that are often regarded as noise\n\nwe ask our selves, which lower dimensional plane fits the data the best\nsuch that the noise is reduced and the important info is reserved?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "Preform PCA to extract the key dimensions (features) that represent\nthe data the best, getting rid of all the other unecessary\nirrelevant features that are often regarded as noise\n\nwe ask our selves, which lower dimensional plane fits the data the best\nsuch that the noise is reduced and the important info is reserved?",
			"lineHeight": 1.25
		},
		{
			"id": "NroQjAu80s-pv8B6Oayqa",
			"type": "image",
			"x": -248.34406168306907,
			"y": 72.87402277804699,
			"width": 424,
			"height": 306,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1281500535,
			"version": 90,
			"versionNonce": 1112041657,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ff4f59a1178f5557483a53dc5e4c7f996acc3fb1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Y0JxAF5I",
			"type": "text",
			"x": -306.99822737390934,
			"y": 379.245063502029,
			"width": 543.1182861328125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1530641401,
			"version": 83,
			"versionNonce": 861559639,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "We want to find a subspace such that",
			"rawText": "We want to find a subspace such that",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "We want to find a subspace such that",
			"lineHeight": 1.25
		},
		{
			"id": "UxsIN7QM",
			"type": "text",
			"x": -607.7522323572506,
			"y": 471.3038870314406,
			"width": 271.68511962890625,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 781415415,
			"version": 93,
			"versionNonce": 177007001,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Minimum distance to\nthe original data",
			"rawText": "Minimum distance to\nthe original data",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Minimum distance to\nthe original data",
			"lineHeight": 1.25
		},
		{
			"id": "Rn86pbZk",
			"type": "text",
			"x": -74.57529637594905,
			"y": 498.3627105608523,
			"width": 47.68418884277344,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1537276151,
			"version": 79,
			"versionNonce": 1614993527,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "and",
			"rawText": "and",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "and",
			"lineHeight": 1.25
		},
		{
			"id": "CVctFYtn",
			"type": "text",
			"x": 260.2921886704379,
			"y": 464.24506350202904,
			"width": 297.94921875,
			"height": 70,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1703167097,
			"version": 103,
			"versionNonce": 1548635769,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "Data projected\nhas maximum variance",
			"rawText": "Data projected\nhas maximum variance",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Data projected\nhas maximum variance",
			"lineHeight": 1.25
		},
		{
			"id": "_nIbjCMr4bIeMBa1Ypdrf",
			"type": "image",
			"x": -691.2340354863558,
			"y": 545.4546372100546,
			"width": 194,
			"height": 78,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 288345369,
			"version": 62,
			"versionNonce": 291418519,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "s_9NOFjwsO-gx_8JKB95B",
					"type": "arrow"
				}
			],
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "88c3e6446be853083ff1d93cfb270d69b83fa76d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ynMk48mqQMYQdMtOP67f7",
			"type": "image",
			"x": -495.80286139728696,
			"y": 556.1408720278682,
			"width": 225,
			"height": 61,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 509885849,
			"version": 78,
			"versionNonce": 1045436249,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0c8a557654a8f5a094d2d9dd7aa6226c994e7912",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "43lvX0oi5FQflwSqs-Ji7",
			"type": "line",
			"x": -685.2527360840038,
			"y": 570.7010224038082,
			"width": 135.2380952380953,
			"height": 82.85714285714283,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 32098679,
			"version": 73,
			"versionNonce": 534931127,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-71.42857142857144,
					-82.85714285714283
				],
				[
					-135.2380952380953,
					-78.09523809523807
				]
			],
			"lastCommittedPoint": [
				-135.2380952380953,
				-78.09523809523807
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "vqYE8vEE",
			"type": "text",
			"x": -956.7597072458882,
			"y": 496.30053240917744,
			"width": 170.83978271484375,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1757501399,
			"version": 105,
			"versionNonce": 317047865,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627531,
			"link": null,
			"locked": false,
			"text": "projection\nof all datapoints\nonto w",
			"rawText": "projection\nof all datapoints\nonto w",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "projection\nof all datapoints\nonto w",
			"lineHeight": 1.25
		},
		{
			"id": "rYUCdtnxQwPcc8p_lfH9Y",
			"type": "image",
			"x": -726.6813075125752,
			"y": 700.7724509752368,
			"width": 459.99999999999994,
			"height": 157,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1978024119,
			"version": 137,
			"versionNonce": 1597978809,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-nNjNa1-BfKXZepbqGtZo",
					"type": "arrow"
				}
			],
			"updated": 1703685784310,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1dd57480649105e90f577b40329e68d074d4d6ea",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "s_9NOFjwsO-gx_8JKB95B",
			"type": "arrow",
			"x": -487.1574979887658,
			"y": 633.5581652609511,
			"width": 0.9523809523809632,
			"height": 96.19047619047615,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 528163161,
			"version": 63,
			"versionNonce": 636671257,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.9523809523809632,
					96.19047619047615
				]
			],
			"lastCommittedPoint": [
				0.9523809523809632,
				96.19047619047615
			],
			"startBinding": {
				"elementId": "_nIbjCMr4bIeMBa1Ypdrf",
				"focus": -1.0945126839371382,
				"gap": 10.103528050896557
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "M169W79oNePwMQdXjuGtW",
			"type": "image",
			"x": 205.09501726922417,
			"y": 550.7054847166469,
			"width": 167.23790769707946,
			"height": 68.54012610536043,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 300702231,
			"version": 74,
			"versionNonce": 119760119,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b5687b8bf8eb523359857ef85d33c56a75b46968",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xiaMjxoD2tqh7XrGU2crO",
			"type": "image",
			"x": 377.8475014414373,
			"y": 553.5892281852678,
			"width": 201.4012610536042,
			"height": 57.54321744388692,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 500165591,
			"version": 92,
			"versionNonce": 2062207481,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "65B9C-N3cJWsKBJNzelEW",
					"type": "arrow"
				}
			],
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cc0bd69983063231b46c45e104c24fdbc71e4d2d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "LapsooQmLIqJ-t4SXqRLP",
			"type": "line",
			"x": 602.3623816154984,
			"y": 578.5156738746876,
			"width": 220.7123580668524,
			"height": 73.21190413924865,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 672351863,
			"version": 99,
			"versionNonce": 360295959,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					141.04058003296404,
					-73.21190413924865
				],
				[
					220.7123580668524,
					-57.0622194026497
				]
			],
			"lastCommittedPoint": [
				220.7123580668524,
				-57.0622194026497
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "G66GX3dQ",
			"type": "text",
			"x": 768.0839135210529,
			"y": 527.8402892791852,
			"width": 206.8797607421875,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 435983895,
			"version": 88,
			"versionNonce": 1523655385,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"text": "The length of the\nprojected datapoints\nonto w",
			"rawText": "The length of the\nprojected datapoints\nonto w",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "The length of the\nprojected datapoints\nonto w",
			"lineHeight": 1.25
		},
		{
			"id": "65B9C-N3cJWsKBJNzelEW",
			"type": "arrow",
			"x": 403.1366962911884,
			"y": 624.8114367862713,
			"width": 0.08066088010730255,
			"height": 96.91038288139134,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1254409433,
			"version": 565,
			"versionNonce": 1349112631,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.08066088010730255,
					96.91038288139134
				]
			],
			"lastCommittedPoint": [
				0,
				129.19747789279165
			],
			"startBinding": {
				"elementId": "xiaMjxoD2tqh7XrGU2crO",
				"gap": 13.678991157116627,
				"focus": 0.7484083768214703
			},
			"endBinding": {
				"elementId": "hNCShzthZwiPIaevWLWg3",
				"gap": 11.119377466730043,
				"focus": -0.02218029599673686
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "hNCShzthZwiPIaevWLWg3",
			"type": "image",
			"x": 213.94217989861454,
			"y": 732.8411971343927,
			"width": 387.26694176103484,
			"height": 127.39044136876146,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 265693719,
			"version": 148,
			"versionNonce": 574185401,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "65B9C-N3cJWsKBJNzelEW",
					"type": "arrow"
				}
			],
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "466eaf764d8b9c54f2ded0eb206baf1409cd0cd6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "sBMkmetr_fbDlRxdZOBf1",
			"type": "line",
			"x": 630.3551684922688,
			"y": 771.2340169234932,
			"width": 348.7116043242853,
			"height": 7.5205537071676645,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 660470839,
			"version": 106,
			"versionNonce": 1673606807,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685049385,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					348.7116043242853,
					-7.5205537071676645
				]
			],
			"lastCommittedPoint": [
				242.24527104898448,
				6.4598738946396
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "j6aQgVSJ",
			"type": "text",
			"x": 617.3072187976475,
			"y": 681.4928842259385,
			"width": 338.2396240234375,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 86935959,
			"version": 164,
			"versionNonce": 228745623,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685052966,
			"link": null,
			"locked": false,
			"text": "if the data isnt centered\nthen we have use the expectation\nof the datapoints",
			"rawText": "if the data isnt centered\nthen we have use the expectation\nof the datapoints",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "if the data isnt centered\nthen we have use the expectation\nof the datapoints",
			"lineHeight": 1.25
		},
		{
			"id": "6oXBe-QWp5ioe_2lQbbps",
			"type": "image",
			"x": 979.7188075488452,
			"y": 696.9426922725559,
			"width": 419.6636570554519,
			"height": 83.65618204894511,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1406248505,
			"version": 298,
			"versionNonce": 839147193,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Tvm0sUahacXrqID-qwIaI",
					"type": "arrow"
				}
			],
			"updated": 1703685060238,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "568037a5baf496cd762db98b9c1fcfb979c241b2",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "vsS1E8Tk",
			"type": "text",
			"x": -36.42803462126619,
			"y": 764.4651820120882,
			"width": 22.212005615234375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 199347609,
			"version": 36,
			"versionNonce": 1336771961,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627532,
			"link": null,
			"locked": false,
			"text": "=",
			"rawText": "=",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 32,
			"containerId": null,
			"originalText": "=",
			"lineHeight": 1.25
		},
		{
			"id": "lNzIiHaP",
			"type": "text",
			"x": -1107.8517268223645,
			"y": 1071.6047383968014,
			"width": 528.9393920898438,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1253007671,
			"version": 674,
			"versionNonce": 1450897463,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685777845,
			"link": null,
			"locked": false,
			"text": "You can actually derive on of these equations\nfrom the other, so although they strive for different\ngoals they end up achieving the same one!",
			"rawText": "You can actually derive on of these equations\nfrom the other, so although they strive for different\ngoals they end up achieving the same one!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "You can actually derive on of these equations\nfrom the other, so although they strive for different\ngoals they end up achieving the same one!",
			"lineHeight": 1.25
		},
		{
			"id": "bc6HfPu6c_2v9wxbzC2mx",
			"type": "image",
			"x": -1081.5323374426148,
			"y": 1156.5333617448428,
			"width": 492.2019344553877,
			"height": 395.2738998768826,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 462429207,
			"version": 555,
			"versionNonce": 4051287,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685777845,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "568403757cb500032d3f0b11d03a10b18781321c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "MZVK4oEJ",
			"type": "text",
			"x": 1023.9830966600255,
			"y": 781.4304349433158,
			"width": 340.64068603515625,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1002661017,
			"version": 149,
			"versionNonce": 1293602775,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685039137,
			"link": null,
			"locked": false,
			"text": "What happens if we dont center the data?",
			"rawText": "What happens if we dont center the data?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "What happens if we dont center the data?",
			"lineHeight": 1.25
		},
		{
			"id": "iWS4RmDJGSS9IrXtnOhbw",
			"type": "arrow",
			"x": 1364.348731715633,
			"y": 620.139565554583,
			"width": 377.213497063138,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 919169849,
			"version": 52,
			"versionNonce": 2068041945,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703684627533,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					377.213497063138,
					0
				]
			],
			"lastCommittedPoint": [
				377.213497063138,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "S_dQWWNhn5qbOabucQORE",
			"type": "arrow",
			"x": 1363.5215091343541,
			"y": 620.9667881358617,
			"width": 0.8272225812786473,
			"height": 245.68510663980697,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1111938967,
			"version": 58,
			"versionNonce": 1009143225,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703684627533,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8272225812786473,
					-245.68510663980697
				]
			],
			"lastCommittedPoint": [
				-0.8272225812786473,
				-245.68510663980697
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "sd4I6nwDAvsS1LJAIi2g6",
			"type": "line",
			"x": 1710.6788961883067,
			"y": 491.0158020741835,
			"width": 273.67747713944505,
			"height": 128.55413853105443,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
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
			"seed": 765638199,
			"version": 136,
			"versionNonce": 962997913,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627533,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-273.67747713944505,
					-128.55413853105443
				]
			],
			"lastCommittedPoint": [
				-244.5385390724059,
				-118.8411591753748
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "jmWAgyO-SWicpu0Ykxolw",
			"type": "freedraw",
			"x": 1680.9686063944628,
			"y": 496.1579676154257,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 979912441,
			"version": 19,
			"versionNonce": 1236726649,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627533,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "_BC_5q8suAdF1yJi6U1IA",
			"type": "freedraw",
			"x": 1691.2529374769472,
			"y": 456.73469846590234,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2147065241,
			"version": 19,
			"versionNonce": 134143127,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627533,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "hi962zFCWH6EUaGEYKBjS",
			"type": "freedraw",
			"x": 1656.971833868666,
			"y": 488.73039516696474,
			"width": 0.5713517268047781,
			"height": 1.7140551804139932,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 664729657,
			"version": 22,
			"versionNonce": 559684697,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627533,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.1427034536093288
				],
				[
					0.5713517268047781,
					-1.7140551804139932
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.5713517268047781,
				-1.7140551804139932
			]
		},
		{
			"id": "6SGUWuOHoz8DIVVp3tl2P",
			"type": "freedraw",
			"x": 1664.9707580439317,
			"y": 455.59199501229295,
			"width": 1.1427034536093288,
			"height": 0.5713517268046644,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1559214457,
			"version": 21,
			"versionNonce": 1195717047,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.1427034536093288,
					0.5713517268046644
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				1.1427034536093288,
				0.5713517268046644
			]
		},
		{
			"id": "wxpaYK3sw_d7F0ibfK3n4",
			"type": "freedraw",
			"x": 1720.3918755439863,
			"y": 521.297443594832,
			"width": 0.5713517268045507,
			"height": 3.4281103608282137,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 305114585,
			"version": 23,
			"versionNonce": 539568441,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.5713517268047781
				],
				[
					0.5713517268045507,
					-2.8567586340234357
				],
				[
					0.5713517268045507,
					-3.4281103608282137
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.5713517268045507,
				-3.4281103608282137
			]
		},
		{
			"id": "x-SBUcXN7N0MHl08m6fr7",
			"type": "freedraw",
			"x": 1720.9632272707909,
			"y": 473.8752502700429,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1037687287,
			"version": 16,
			"versionNonce": 5828345,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "0nEZQ11VfqE1lKyxoyKm8",
			"type": "freedraw",
			"x": 1706.6794341006737,
			"y": 509.2990573319335,
			"width": 0.5713517268047781,
			"height": 1.71405518041405,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 38201687,
			"version": 18,
			"versionNonce": 19683607,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268047781,
					-1.71405518041405
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.5713517268047781,
				-1.71405518041405
			]
		},
		{
			"id": "XoZHbvHjtFc0XQDO2ypAn",
			"type": "freedraw",
			"x": 1738.1037790749315,
			"y": 479.58876753808977,
			"width": 2.2854069072186576,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1786196727,
			"version": 20,
			"versionNonce": 959621081,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.1427034536095562,
					0
				],
				[
					2.2854069072186576,
					0
				],
				[
					1.1427034536095562,
					0
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				1.1427034536095562,
				0
			]
		},
		{
			"id": "Zv1gEVlcYIMB8lh3eRyXG",
			"type": "freedraw",
			"x": 1632.4037096160646,
			"y": 472.1611950896289,
			"width": 0,
			"height": 1.1427034536094425,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 208895703,
			"version": 18,
			"versionNonce": 646913591,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.1427034536094425
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				-1.1427034536094425
			]
		},
		{
			"id": "L2v7QE4LRZeSBg--52SBS",
			"type": "freedraw",
			"x": 1670.1129235851738,
			"y": 431.59522248649614,
			"width": 0.5713517268047781,
			"height": 1.71405518041405,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 177625207,
			"version": 19,
			"versionNonce": 606225593,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.5713517268046644
				],
				[
					-0.5713517268047781,
					1.71405518041405
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-0.5713517268047781,
				1.71405518041405
			]
		},
		{
			"id": "uVBVVqLsCTp68bid3ANM_",
			"type": "freedraw",
			"x": 1602.1220680954161,
			"y": 463.0195674607539,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 400253561,
			"version": 14,
			"versionNonce": 749223031,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "iGGqxxzHLtTYO0LRdu-4W",
			"type": "freedraw",
			"x": 1613.5491026315099,
			"y": 424.7390017648399,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1814587673,
			"version": 14,
			"versionNonce": 2120297081,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "kcDoZ5fPhA9k-VRQygPBG",
			"type": "freedraw",
			"x": 1653.543723507838,
			"y": 445.3076639298086,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1575449529,
			"version": 14,
			"versionNonce": 1937216919,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "8z-PFDK2U8FwkM5JgQeFg",
			"type": "freedraw",
			"x": 1531.274453971635,
			"y": 446.450367383418,
			"width": 2.2854069072186576,
			"height": 1.7140551804141069,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1554448985,
			"version": 19,
			"versionNonce": 1369928537,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268045507,
					0
				],
				[
					0.5713517268045507,
					-0.5713517268046644
				],
				[
					1.7140551804141069,
					-1.1427034536093856
				],
				[
					2.2854069072186576,
					-1.7140551804141069
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.2854069072186576,
				-1.7140551804141069
			]
		},
		{
			"id": "ftYbNoR_IyYF-HL0inlDf",
			"type": "freedraw",
			"x": 1583.2674611108614,
			"y": 407.5984499606993,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 120346969,
			"version": 14,
			"versionNonce": 356436663,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "Q0Zf3nwQqycB2LSEK4wws",
			"type": "freedraw",
			"x": 1587.838274925299,
			"y": 446.450367383418,
			"width": 1.7140551804141069,
			"height": 4.570813814437486,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1331055609,
			"version": 17,
			"versionNonce": 2062655545,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.1427034536093856
				],
				[
					-0.5713517268047781,
					-2.8567586340234357
				],
				[
					-1.7140551804141069,
					-4.570813814437486
				],
				[
					-1.7140551804141069,
					-4.570813814437486
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-1.7140551804141069,
				-4.570813814437486
			]
		},
		{
			"id": "6IbIsuvyXSkm162FMj3db",
			"type": "freedraw",
			"x": 1544.4155436881429,
			"y": 427.0244086720586,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 92618041,
			"version": 14,
			"versionNonce": 513956823,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "K2enbK_2kHcwBz97CxMHy",
			"type": "freedraw",
			"x": 1598.1226060077834,
			"y": 402.4562844194571,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 664222681,
			"version": 14,
			"versionNonce": 1478701337,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "NPj158s3s2sF0-iwn-BTB",
			"type": "freedraw",
			"x": 1533.5598608788537,
			"y": 394.4573602441915,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2090745465,
			"version": 14,
			"versionNonce": 330746103,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "IeEoeYyC-u6xEf8rUCLSJ",
			"type": "freedraw",
			"x": 1584.9815162912755,
			"y": 409.88385686791804,
			"width": 0.5713517268045507,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 520668441,
			"version": 16,
			"versionNonce": 1051698681,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5713517268045507,
					0
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-0.5713517268045507,
				0
			]
		},
		{
			"id": "hDqtW2fDeUGvT_AvwY6dL",
			"type": "freedraw",
			"x": 1539.8447298737053,
			"y": 400.74222923904307,
			"width": 2.2854069072186576,
			"height": 2.8567586340234357,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 755856761,
			"version": 17,
			"versionNonce": 33591831,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268047781,
					-1.71405518041405
				],
				[
					2.2854069072186576,
					-2.8567586340234357
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.2854069072186576,
				-2.8567586340234357
			]
		},
		{
			"id": "hR9Wu-qe_aIvXyEN1SnIc",
			"type": "freedraw",
			"x": 1563.8415023995021,
			"y": 386.4584360689259,
			"width": 2.2854069072186576,
			"height": 2.8567586340234357,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 154093241,
			"version": 17,
			"versionNonce": 161119961,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268045507,
					0.5713517268047212
				],
				[
					2.2854069072186576,
					2.8567586340234357
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.2854069072186576,
				2.8567586340234357
			]
		},
		{
			"id": "t6RlvsoHn_mCBzbd4jLcn",
			"type": "freedraw",
			"x": 1622.690730260385,
			"y": 415.0260224091602,
			"width": 2.8567586340232083,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 177416185,
			"version": 17,
			"versionNonce": 1383348023,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.2854069072186576,
					0
				],
				[
					2.8567586340232083,
					0
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.8567586340232083,
				0
			]
		},
		{
			"id": "3mNiiMekhfUPlJ5ZxNIBG",
			"type": "freedraw",
			"x": 1560.413392038674,
			"y": 404.17033959987117,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2087524665,
			"version": 14,
			"versionNonce": 1735867321,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "GyL5DppQ0-PEww2a4Sh44",
			"type": "freedraw",
			"x": 1487.8517227344787,
			"y": 433.3092776669102,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 45914073,
			"version": 14,
			"versionNonce": 1534474327,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "KGoWRyaOOZYfLnz5jADhn",
			"type": "freedraw",
			"x": 1554.699874770627,
			"y": 379.60221534726963,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 854661753,
			"version": 14,
			"versionNonce": 1751735449,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "zp5bKRX_GtMorBUkfkJ36",
			"type": "freedraw",
			"x": 1534.1312126056584,
			"y": 419.59683622359773,
			"width": 3.4281103608282137,
			"height": 5.142165541242207,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1299783961,
			"version": 18,
			"versionNonce": 853218679,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5713517268047781,
					0
				],
				[
					-1.1427034536093288,
					-0.5713517268047212
				],
				[
					-2.8567586340234357,
					-4.5708138144375425
				],
				[
					-3.4281103608282137,
					-5.142165541242207
				],
				[
					-3.4281103608282137,
					-5.142165541242207
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-3.4281103608282137,
				-5.142165541242207
			]
		},
		{
			"id": "RPStSGhjsWFSymkU1RVPD",
			"type": "freedraw",
			"x": 1510.7057918066662,
			"y": 376.17410498644153,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 452396857,
			"version": 14,
			"versionNonce": 1277452665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "CfUtyckJx4E82bEneVE1I",
			"type": "freedraw",
			"x": 1492.4225365489162,
			"y": 429.88116730608203,
			"width": 2.285406907218885,
			"height": 0.5713517268046644,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 589645273,
			"version": 19,
			"versionNonce": 1072123543,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627534,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268047781,
					0
				],
				[
					1.1427034536093288,
					-0.5713517268046644
				],
				[
					1.7140551804141069,
					-0.5713517268046644
				],
				[
					2.285406907218885,
					-0.5713517268046644
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.285406907218885,
				-0.5713517268046644
			]
		},
		{
			"id": "4Fin5cKU-RrQWAAPgb4w0",
			"type": "freedraw",
			"x": 1494.1365917293303,
			"y": 409.88385686791804,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 9379033,
			"version": 14,
			"versionNonce": 267111001,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "0WoKh2U-8oMQss75HtXjz",
			"type": "freedraw",
			"x": 1519.8474194355413,
			"y": 421.3108914040118,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 179683193,
			"version": 14,
			"versionNonce": 223306679,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "wu-A3fylwDm8_awJDDMHG",
			"type": "freedraw",
			"x": 1475.2819847447756,
			"y": 395.6000636978009,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1055122969,
			"version": 14,
			"versionNonce": 1016272697,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "bzWOwx0Yf1ZNw9FlnoQM9",
			"type": "freedraw",
			"x": 1511.277143533471,
			"y": 402.4562844194571,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1117262009,
			"version": 14,
			"versionNonce": 1530385623,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "eYMpROsaB6pCq6Y7uXitA",
			"type": "freedraw",
			"x": 1441.0008811364946,
			"y": 387.0297877957306,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1306574681,
			"version": 14,
			"versionNonce": 1954400281,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "Wn7INN9Gs-ihoTxyIaP5B",
			"type": "freedraw",
			"x": 1474.710633017971,
			"y": 410.45520859472276,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1792026073,
			"version": 10,
			"versionNonce": 1693470775,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "UGMrtx3VShBuI8cergWVH",
			"type": "freedraw",
			"x": 1454.713322579807,
			"y": 392.17195333697276,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 432498809,
			"version": 10,
			"versionNonce": 1562718905,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "N_vxwvL2-XSbmHf0pLZzk",
			"type": "freedraw",
			"x": 1442.143584590104,
			"y": 369.88923599159,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1091186457,
			"version": 10,
			"versionNonce": 1493643607,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "s26Rw4BzIROBYf4B5ruR0",
			"type": "freedraw",
			"x": 1418.1468120643071,
			"y": 366.4611256307619,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2090269113,
			"version": 10,
			"versionNonce": 54555545,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "i2enFuRALRd6Q7NWmxfO7",
			"type": "freedraw",
			"x": 1445.0003432241274,
			"y": 342.464353104965,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 184305753,
			"version": 10,
			"versionNonce": 635760247,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "mTWL7tNjEpld6kbq0p0St",
			"type": "freedraw",
			"x": 1510.1344400798616,
			"y": 372.74599462561343,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 391682809,
			"version": 10,
			"versionNonce": 1241553017,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "2t25ubcz0SGFjB5IQZNCr",
			"type": "freedraw",
			"x": 1467.8544122963149,
			"y": 340.1789461977463,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1130000793,
			"version": 10,
			"versionNonce": 1179518871,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "WXYTAnNASnHILZb3wy4P8",
			"type": "freedraw",
			"x": 1467.8544122963149,
			"y": 362.4616635431291,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1900039225,
			"version": 10,
			"versionNonce": 321462617,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "QKvX9gO9IrGc9Tyszy4Kk",
			"type": "freedraw",
			"x": 1508.991736626252,
			"y": 352.1773324606447,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1306045145,
			"version": 10,
			"versionNonce": 1752628407,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "5r46KNGeobogran8dExOb",
			"type": "freedraw",
			"x": 1458.7127846674398,
			"y": 354.46273936786343,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 444730745,
			"version": 10,
			"versionNonce": 1007521337,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "cn1HVMEBl6bw0eqFxa_n_",
			"type": "freedraw",
			"x": 1517.5620125283226,
			"y": 356.7481462750822,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 925561881,
			"version": 10,
			"versionNonce": 282071,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "xy1xXCFuNTp3vc9-WXBGA",
			"type": "freedraw",
			"x": 1487.8517227344787,
			"y": 341.32164965135564,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1817304761,
			"version": 10,
			"versionNonce": 730947353,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "eTr375Edmwz5Fa1etBJUU",
			"type": "freedraw",
			"x": 1491.8511848221117,
			"y": 374.4600498060275,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1963281753,
			"version": 10,
			"versionNonce": 403340023,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "Nr8aklFrzoTPn9WQfCjIV",
			"type": "freedraw",
			"x": 1545.5582471417522,
			"y": 362.4616635431291,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1222885369,
			"version": 10,
			"versionNonce": 539497465,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "86QKur3ss0zxlWL96Ixd4",
			"type": "freedraw",
			"x": 1525.5609367035881,
			"y": 373.3173463524181,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 639350425,
			"version": 10,
			"versionNonce": 1695417367,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "16mGbLYXR7A8iLVQUOlF7",
			"type": "freedraw",
			"x": 1478.7100951056038,
			"y": 346.46381519259785,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1533784377,
			"version": 10,
			"versionNonce": 1037380825,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "Eoe72xJndrjf6B1Nw-72d",
			"type": "freedraw",
			"x": 1516.419309074713,
			"y": 382.45897398129307,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1377972185,
			"version": 10,
			"versionNonce": 386099511,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "E3d6tC3qNXl1dk-vKBJxz",
			"type": "freedraw",
			"x": 1548.9863575025802,
			"y": 379.03086362046497,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1478341241,
			"version": 10,
			"versionNonce": 1546398137,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "Kmko2RQ5ELm7FltN-I6TT",
			"type": "freedraw",
			"x": 1572.4117783015724,
			"y": 452.16388465146485,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 701282585,
			"version": 10,
			"versionNonce": 1800350295,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "8tbJGpvRLwx7b600uL1gn",
			"type": "freedraw",
			"x": 1580.9820542036427,
			"y": 405.8843947802852,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1009632185,
			"version": 10,
			"versionNonce": 340822681,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "h3l2jheh2JUTxH86uHC7L",
			"type": "freedraw",
			"x": 1555.8425782242366,
			"y": 433.8806293937149,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1187992153,
			"version": 10,
			"versionNonce": 2126890871,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "RjxEaByl6vWlOu1m6VfB4",
			"type": "freedraw",
			"x": 1592.980440466541,
			"y": 412.7406155019415,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 231728377,
			"version": 10,
			"versionNonce": 250990457,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "5-UACGfasKFqHGp7mX6PT",
			"type": "freedraw",
			"x": 1584.9815162912755,
			"y": 437.308739754543,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1809709977,
			"version": 10,
			"versionNonce": 1605091479,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "kDzFx4W1Hp0Q_HVw2Nnsi",
			"type": "freedraw",
			"x": 1550.1290609561897,
			"y": 439.02279493495706,
			"width": 2.8567586340232083,
			"height": 0.5713517268046644,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 473437753,
			"version": 13,
			"versionNonce": 308246617,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.2854069072186576,
					0.5713517268046644
				],
				[
					2.8567586340232083,
					0.5713517268046644
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.8567586340232083,
				0.5713517268046644
			]
		},
		{
			"id": "tiyOgGAEAs6nsAlHuJ5pn",
			"type": "freedraw",
			"x": 1602.6934198222207,
			"y": 446.450367383418,
			"width": 0.5713517268047781,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1067079545,
			"version": 12,
			"versionNonce": 1605735863,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268047781,
					0
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.5713517268047781,
				0
			]
		},
		{
			"id": "nYKbFpaBlcVKKmhFAUlH-",
			"type": "freedraw",
			"x": 1635.2604682500878,
			"y": 416.16872586276963,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 544705497,
			"version": 10,
			"versionNonce": 1348535609,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "i6oFJdeDty1_L2_myj06e",
			"type": "freedraw",
			"x": 1610.1209922706817,
			"y": 467.0190295483867,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 262180473,
			"version": 10,
			"versionNonce": 638043863,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627535,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "PxsIfqNjpPSVxK-jHGcQT",
			"type": "freedraw",
			"x": 1634.1177647964785,
			"y": 429.88116730608203,
			"width": 0,
			"height": 1.7140551804141069,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 661460249,
			"version": 12,
			"versionNonce": 1952314905,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.7140551804141069
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				1.7140551804141069
			]
		},
		{
			"id": "vuXhh5PjteC5cCPbevby4",
			"type": "freedraw",
			"x": 1642.1166889717442,
			"y": 441.8795535689805,
			"width": 3.4281103608279864,
			"height": 1.1427034536093856,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1556071801,
			"version": 14,
			"versionNonce": 20370423,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7140551804141069,
					-0.5713517268047212
				],
				[
					2.2854069072186576,
					-0.5713517268047212
				],
				[
					3.4281103608279864,
					-1.1427034536093856
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				3.4281103608279864,
				-1.1427034536093856
			]
		},
		{
			"id": "g35RSBA5Oqz4SpQ7KrLOP",
			"type": "freedraw",
			"x": 1606.121530183049,
			"y": 433.3092776669102,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1532254105,
			"version": 10,
			"versionNonce": 1900661497,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "GWPZjy0Ui3IsQ2kzlSS7Y",
			"type": "freedraw",
			"x": 1707.822137554283,
			"y": 443.59360874939455,
			"width": 0.5713517268047781,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 477884985,
			"version": 12,
			"versionNonce": 2034711831,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5713517268047781,
					0
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.5713517268047781,
				0
			]
		},
		{
			"id": "gLfoh18MmMYDd6ELKVNC6",
			"type": "freedraw",
			"x": 1669.541571858369,
			"y": 444.7363122030039,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1866493593,
			"version": 10,
			"versionNonce": 262669273,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "XCYPvG-bvH8DTgrkOyHMc",
			"type": "freedraw",
			"x": 1702.1086202862361,
			"y": 469.87578818241013,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1361799481,
			"version": 10,
			"versionNonce": 565019191,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "kpIOQChFDGsSdzCE_YwWT",
			"type": "freedraw",
			"x": 1705.5367306470644,
			"y": 447.5930708370273,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1448929241,
			"version": 10,
			"versionNonce": 999039161,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "jkaACq-E7oUurDdZaKGCG",
			"type": "freedraw",
			"x": 1715.249710002744,
			"y": 484.1595813525273,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 414411385,
			"version": 10,
			"versionNonce": 726541143,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684627536,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "LbUz1LbPlDfu07hqaRKqP",
			"type": "freedraw",
			"x": 1760.3864964203144,
			"y": 491.0158020741835,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 839124601,
			"version": 3,
			"versionNonce": 738930359,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684628194,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "KTCXtp3Z570g4e2IT1ex1",
			"type": "freedraw",
			"x": 1742.674592889369,
			"y": 508.1563538783241,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1172540697,
			"version": 3,
			"versionNonce": 1173845527,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684628526,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "50pPC0feyUuQXKt0ZXSKP",
			"type": "freedraw",
			"x": 1738.1037790749315,
			"y": 485.30228480613664,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1380259769,
			"version": 3,
			"versionNonce": 1175222647,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684628850,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "s7pyFPMyIk5vpcC2AsUPe",
			"type": "freedraw",
			"x": 1727.8194479924473,
			"y": 505.87094697110535,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1622615641,
			"version": 3,
			"versionNonce": 1504950487,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684629158,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "XQMtONawUC81O0O4g77BM",
			"type": "freedraw",
			"x": 1679.8259029408534,
			"y": 500.1574297030585,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1196964089,
			"version": 3,
			"versionNonce": 617002039,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684629498,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "mE9T-0s0tuTnaXJ517iPP",
			"type": "freedraw",
			"x": 1647.2588545129863,
			"y": 481.87417444530854,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 852938649,
			"version": 3,
			"versionNonce": 395242391,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684629872,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "hgq1ZyLKr8gdSRW0Wd6DM",
			"type": "freedraw",
			"x": 1624.4047854407988,
			"y": 487.01633998655075,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1886480953,
			"version": 3,
			"versionNonce": 80076535,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684630480,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "q4e01-1iSIF2rrC5j-HQC",
			"type": "freedraw",
			"x": 1660.3999442294942,
			"y": 472.73254681643357,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2012645593,
			"version": 3,
			"versionNonce": 2006257239,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684630762,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "6zvRaJoz6aeDS6iEcSL-U",
			"type": "freedraw",
			"x": 1688.3961788429237,
			"y": 503.0141883370819,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 902081401,
			"version": 3,
			"versionNonce": 1234565559,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684631038,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "o2G5_27oFLI3hTNQ0tsF2",
			"type": "line",
			"x": 1366.1538049250805,
			"y": 619.569940605238,
			"width": 270.65605454449087,
			"height": 267.7787865073742,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
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
			"seed": 827209719,
			"version": 149,
			"versionNonce": 1286949209,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684651510,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					270.65605454449087,
					-267.7787865073742
				]
			],
			"lastCommittedPoint": [
				180.547145670281,
				-154.2649662372654
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Dm0tPI4D",
			"type": "text",
			"x": 1704.573291638042,
			"y": 494.3234020497689,
			"width": 105.93621826171875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 369021687,
			"version": 13,
			"versionNonce": 1487220345,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684660997,
			"link": null,
			"locked": false,
			"text": "what we need",
			"rawText": "what we need",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "what we need",
			"lineHeight": 1.25
		},
		{
			"id": "b3BsXysy",
			"type": "text",
			"x": 1594.0252273850524,
			"y": 317.61632101073366,
			"width": 97.66421508789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1325704249,
			"version": 13,
			"versionNonce": 1159490903,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684666327,
			"link": null,
			"locked": false,
			"text": "what we get",
			"rawText": "what we get",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "what we get",
			"lineHeight": 1.25
		},
		{
			"id": "pJWcC8x6",
			"type": "text",
			"x": 1043.8058365743618,
			"y": -167.6794935126461,
			"width": 338.9447326660156,
			"height": 20,
			"angle": 0.47562375844711724,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1991304633,
			"version": 127,
			"versionNonce": 935011417,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703684724144,
			"link": null,
			"locked": false,
			"text": "note that this method is not very robust!!",
			"rawText": "note that this method is not very robust!!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "note that this method is not very robust!!",
			"lineHeight": 1.25
		},
		{
			"id": "Gs2oeCz7fbyeN3SF7KDsu",
			"type": "image",
			"x": 166.21204298424146,
			"y": 835.2387348268112,
			"width": 738.930404670752,
			"height": 254.53293150267177,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 532587033,
			"version": 303,
			"versionNonce": 1634646551,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "mTDjVmYp2hFO4MiwyW9yR",
					"type": "arrow"
				}
			],
			"updated": 1703685761302,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63f49e2afc776b649af1373f0068efb0acfe7778",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Tvm0sUahacXrqID-qwIaI",
			"type": "arrow",
			"x": 1407.6892633926132,
			"y": 762.1852125432628,
			"width": 146.25678106505939,
			"height": 120.44676087710798,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 979721751,
			"version": 76,
			"versionNonce": 32946745,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703685060674,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					144.10594604939706,
					-11.829592586144486
				],
				[
					146.25678106505939,
					-120.44676087710798
				]
			],
			"lastCommittedPoint": [
				146.25678106505939,
				-120.44676087710798
			],
			"startBinding": {
				"elementId": "6oXBe-QWp5ioe_2lQbbps",
				"focus": 0.6997318883307195,
				"gap": 8.306798788315973
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "SSEgKVMf7l_bvow-IlKRZ",
			"type": "line",
			"x": 438.9522059462013,
			"y": 1088.8717438103,
			"width": 139.98269887539334,
			"height": 45.101593841417525,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 58057049,
			"version": 187,
			"versionNonce": 1418763833,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685133245,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-52.1545948708482,
					42.06007269318707
				],
				[
					-139.98269887539334,
					45.101593841417525
				]
			],
			"lastCommittedPoint": [
				-368.8682051861433,
				73.12839053252992
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "zykM2AsW",
			"type": "text",
			"x": -327.48913432755467,
			"y": 1094.2157144082532,
			"width": 548.4970703125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1235366487,
			"version": 48,
			"versionNonce": 1307369337,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685142483,
			"link": null,
			"locked": false,
			"text": "where Σ is the covariance matrix (recall: the data is assumed to be",
			"rawText": "where Σ is the covariance matrix (recall: the data is assumed to be",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "where Σ is the covariance matrix (recall: the data is assumed to be",
			"lineHeight": 1.25
		},
		{
			"id": "kXklT2FM",
			"type": "text",
			"x": -390.9212021986484,
			"y": 1124.2157144082532,
			"width": 675.3612060546875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1049756313,
			"version": 65,
			"versionNonce": 129040153,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685124315,
			"link": null,
			"locked": false,
			"text": "centered i.e the mean is 0). The covariance matrix does not depend on w and can be",
			"rawText": "centered i.e the mean is 0). The covariance matrix does not depend on w and can be",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "centered i.e the mean is 0). The covariance matrix does not depend on w and can be",
			"lineHeight": 1.25
		},
		{
			"id": "6OY1Nj9o",
			"type": "text",
			"x": -100.44869090714451,
			"y": 1154.2157144082532,
			"width": 94.41618347167969,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 762826615,
			"version": 45,
			"versionNonce": 391361529,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685124315,
			"link": null,
			"locked": false,
			"text": "precomputed",
			"rawText": "precomputed",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "precomputed",
			"lineHeight": 1.25
		},
		{
			"id": "T6Rndoek",
			"type": "text",
			"x": 342.74728787899164,
			"y": 1404.8662071930125,
			"width": 428.68182373046875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1470806265,
			"version": 110,
			"versionNonce": 1523327127,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703685757096,
			"link": null,
			"locked": false,
			"text": "We Apply the Lagrange method!",
			"rawText": "We Apply the Lagrange method!",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "We Apply the Lagrange method!",
			"lineHeight": 1.25
		},
		{
			"id": "3GS7ZJ_IMNvc0FzOCdrCZ",
			"type": "image",
			"x": 332.61611961673304,
			"y": 1448.2323089460413,
			"width": 439,
			"height": 65,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1513142777,
			"version": 81,
			"versionNonce": 229947193,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685755409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "33565dae8c199d8f158838e59cb325a6d7fc7a2a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8umN6qCtdMc2BJLEECo6T",
			"type": "image",
			"x": 278.6579994254936,
			"y": 1501.8274707946898,
			"width": 538.4832025191821,
			"height": 103.24302003187326,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1284547991,
			"version": 192,
			"versionNonce": 1886087193,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685755409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8db0a71f5f2e63fb68ef6c19cfee4d258b539a26",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "oDBdCqop",
			"type": "text",
			"x": 974.1360930002447,
			"y": 1401.8166901527338,
			"width": 506.51287841796875,
			"height": 220,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1606436505,
			"version": 849,
			"versionNonce": 785972473,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "AyiHakIC2UikaDzNEe84q",
					"type": "arrow"
				},
				{
					"id": "-xpNunWwiKaAAeVrVPwxw",
					"type": "arrow"
				}
			],
			"updated": 1703685755409,
			"link": null,
			"locked": false,
			"text": "Notice that the solution of PCA is the eigen vector of the cov\nmatrix! This makes so much sense because according to linear\nalgebra, the Eigenvectors are the vectors that do not get\ntransformed by the cov matrix, only scaled! (Rotation axis)\n\nThe cov matrix tells us how scaled the dsitribution is in each \ndirection and how sheared it is in each direction\n\nOur eigenvector w is Scaled by this transformation and THUS\nit means that its going along its \"stretched\" direction\nand we seek the K most important (highest scaled) vectors",
			"rawText": "Notice that the solution of PCA is the eigen vector of the cov\nmatrix! This makes so much sense because according to linear\nalgebra, the Eigenvectors are the vectors that do not get\ntransformed by the cov matrix, only scaled! (Rotation axis)\n\nThe cov matrix tells us how scaled the dsitribution is in each \ndirection and how sheared it is in each direction\n\nOur eigenvector w is Scaled by this transformation and THUS\nit means that its going along its \"stretched\" direction\nand we seek the K most important (highest scaled) vectors",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 214,
			"containerId": null,
			"originalText": "Notice that the solution of PCA is the eigen vector of the cov\nmatrix! This makes so much sense because according to linear\nalgebra, the Eigenvectors are the vectors that do not get\ntransformed by the cov matrix, only scaled! (Rotation axis)\n\nThe cov matrix tells us how scaled the dsitribution is in each \ndirection and how sheared it is in each direction\n\nOur eigenvector w is Scaled by this transformation and THUS\nit means that its going along its \"stretched\" direction\nand we seek the K most important (highest scaled) vectors",
			"lineHeight": 1.25
		},
		{
			"id": "GigVJkzWOL2QNjNRNCIqw",
			"type": "line",
			"x": 1348.4585074202928,
			"y": 1704.396612242052,
			"width": 325.3983824917017,
			"height": 195.67145259467793,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1142208889,
			"version": 951,
			"versionNonce": 1264456601,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685755409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-227.5626561943629,
					153.51020037814487
				],
				[
					-290.8045345191621,
					153.51020037814487
				],
				[
					-253.50804217376765,
					103.24101504304781
				],
				[
					-37.83702121996532,
					-42.16125221653306
				],
				[
					34.593847972539606,
					-37.83702121996566
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				-1.0810577491419053,
				1.6215866237125738
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "bwGcPxcO7CdbIWaHZY_CM",
			"type": "line",
			"x": 995.2398224727762,
			"y": 1905.0439848244303,
			"width": 420.4675388106383,
			"height": 275.8209613962333,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 781417047,
			"version": 243,
			"versionNonce": 2104113273,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703685755409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					420.4675388106383,
					-275.8209613962333
				]
			],
			"lastCommittedPoint": [
				313.5067472511412,
				-207.56308783523832
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "AyiHakIC2UikaDzNEe84q",
			"type": "arrow",
			"x": 1503.8290705933955,
			"y": 1527.424393770923,
			"width": 261.8515650167242,
			"height": 1.2528783015154659,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 45300855,
			"version": 188,
			"versionNonce": 149347063,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703685755484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					261.8515650167242,
					-1.2528783015154659
				]
			],
			"lastCommittedPoint": [
				261.8515650167242,
				-1.2528783015154659
			],
			"startBinding": {
				"elementId": "oDBdCqop",
				"focus": 0.1522354065937468,
				"gap": 23.180099175182022
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "-xpNunWwiKaAAeVrVPwxw",
			"type": "arrow",
			"x": 804.7229783477871,
			"y": 1507.378340946676,
			"width": 146.58676127730496,
			"height": 3.7586349045463976,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 952249241,
			"version": 175,
			"versionNonce": 996041751,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703685755484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					146.58676127730496,
					-3.7586349045463976
				]
			],
			"lastCommittedPoint": [
				146.58676127730496,
				-3.7586349045463976
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "oDBdCqop",
				"focus": 0.1311317511721698,
				"gap": 22.82635337515262
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "mTDjVmYp2hFO4MiwyW9yR",
			"type": "arrow",
			"x": 468.268187378078,
			"y": 1115.9696982426035,
			"width": 0,
			"height": 272.8613907508352,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1514317113,
			"version": 45,
			"versionNonce": 50427543,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703685761660,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					272.8613907508352
				]
			],
			"lastCommittedPoint": [
				0,
				272.8613907508352
			],
			"startBinding": {
				"elementId": "Gs2oeCz7fbyeN3SF7KDsu",
				"focus": 0.182450356665389,
				"gap": 26.19803191312053
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "-nNjNa1-BfKXZepbqGtZo",
			"type": "arrow",
			"x": -542.7941364735577,
			"y": 869.4317565813482,
			"width": 285.047767746805,
			"height": 166.61242762665358,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1873910967,
			"version": 81,
			"versionNonce": 1217524441,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703685784692,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-18.06640781493843,
					84.30990313637903
				],
				[
					-254.93708805524125,
					96.35417501300458
				],
				[
					-285.047767746805,
					166.61242762665358
				]
			],
			"lastCommittedPoint": [
				-285.047767746805,
				166.61242762665358
			],
			"startBinding": {
				"elementId": "rYUCdtnxQwPcc8p_lfH9Y",
				"focus": 0.10855207311110389,
				"gap": 11.659305606111388
			},
			"endBinding": {
				"elementId": "25CtriLNqHEhyZ_KXwsL4",
				"focus": -0.2761653164162446,
				"gap": 14.689006276318082
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "WjniqIi9",
			"type": "text",
			"x": 1917.1541072279474,
			"y": 1342.365676740643,
			"width": 429.88580322265625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1229054327,
			"version": 225,
			"versionNonce": 664047577,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686122672,
			"link": null,
			"locked": false,
			"text": "Finding multiple PCA components",
			"rawText": "Finding multiple PCA components",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Finding multiple PCA components",
			"lineHeight": 1.25
		},
		{
			"id": "uMnh8fH9",
			"type": "text",
			"x": 1815.1045519694753,
			"y": 1398.9191891801568,
			"width": 259.14105224609375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1598903703,
			"version": 198,
			"versionNonce": 1252179159,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"text": "1. Find Highest PCA",
			"rawText": "1. Find Highest PCA",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "1. Find Highest PCA",
			"lineHeight": 1.25
		},
		{
			"id": "xTQiZY5L",
			"type": "text",
			"x": 1805.0948983543765,
			"y": 1492.0454275989446,
			"width": 390.013671875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1586160313,
			"version": 102,
			"versionNonce": 50530807,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"text": "2. Remove it from the data",
			"rawText": "2. Remove it from the data",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "2. Remove it from the data",
			"lineHeight": 1.25
		},
		{
			"id": "99hlrZff",
			"type": "text",
			"x": 1857.0099586624206,
			"y": 1546.601280003381,
			"width": 261.6890869140625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 763022391,
			"version": 93,
			"versionNonce": 538751767,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"text": "X = X - W * W * X",
			"rawText": "X = X - W * W * X",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "X = X - W * W * X",
			"lineHeight": 1.25
		},
		{
			"id": "wW674Nte",
			"type": "text",
			"x": 2057.875538244769,
			"y": 1533.2406630880087,
			"width": 22.512100219726562,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1925450327,
			"version": 79,
			"versionNonce": 2053388343,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"text": "T",
			"rawText": "T",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25
		},
		{
			"id": "05MmAoBR9sRKrUTUiX_Jz",
			"type": "line",
			"x": 2045.2547386044348,
			"y": 1591.3336028608003,
			"width": 1.2330832089564865,
			"height": 76.45115895529375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 456649977,
			"version": 54,
			"versionNonce": 1740511575,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2330832089564865,
					76.45115895529375
				]
			],
			"lastCommittedPoint": [
				-1.2330832089564865,
				76.45115895529375
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "abjC5Xzd",
			"type": "text",
			"x": 1935.8454163818064,
			"y": 1674.8737340797752,
			"width": 216.35247802734375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1748590489,
			"version": 51,
			"versionNonce": 226416247,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"text": "Projection in that dimension",
			"rawText": "Projection in that dimension",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Projection in that dimension",
			"lineHeight": 1.25
		},
		{
			"id": "axxAlj8A",
			"type": "text",
			"x": 1836.58912766143,
			"y": 1442.4375772661783,
			"width": 272.7796936035156,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 126387671,
			"version": 161,
			"versionNonce": 1919610775,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686052143,
			"link": null,
			"locked": false,
			"text": "Compute leading eigenvector",
			"rawText": "Compute leading eigenvector",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Compute leading eigenvector",
			"lineHeight": 1.25
		},
		{
			"id": "uny-hq7WbUMiJc_pgD-xJ",
			"type": "image",
			"x": 1799.9445585546773,
			"y": 1797.1957527154034,
			"width": 511.1077945530523,
			"height": 259.8958324244283,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 808651031,
			"version": 378,
			"versionNonce": 1454592665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686183475,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a2df7da46a259498afb1f8149aa53cc80c2103f8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "SBwsj06O",
			"type": "text",
			"x": 1793.431417664697,
			"y": 1715.9980827928605,
			"width": 504.84210205078125,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 925557945,
			"version": 171,
			"versionNonce": 1323743159,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686182076,
			"link": null,
			"locked": false,
			"text": "3. Take your h leading PCA and use\nthem to describe the data",
			"rawText": "3. Take your h leading PCA and use\nthem to describe the data",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "3. Take your h leading PCA and use\nthem to describe the data",
			"lineHeight": 1.25
		},
		{
			"id": "edd0K1Un-fE1fJBez9y1V",
			"type": "arrow",
			"x": 2148.644323124216,
			"y": 1456.1803717674516,
			"width": 429.87176834185493,
			"height": 893.2179657040788,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 833965495,
			"version": 390,
			"versionNonce": 68700633,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703686719280,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					385.90927139344103,
					105.48186751420712
				],
				[
					414.2092846289602,
					772.2620418579413
				],
				[
					-15.662483712894755,
					893.2179657040788
				]
			],
			"lastCommittedPoint": [
				15.43637085573755,
				1180.8823704639294
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "3Ve5EQd8",
			"type": "text",
			"x": 2628.018326469966,
			"y": 1934.7078682953188,
			"width": 317.3253173828125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2115235895,
			"version": 91,
			"versionNonce": 36161719,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686255355,
			"link": null,
			"locked": false,
			"text": "Ways to compute PCA?",
			"rawText": "Ways to compute PCA?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Ways to compute PCA?",
			"lineHeight": 1.25
		},
		{
			"id": "FfapMSBB",
			"type": "text",
			"x": 1584.097590474061,
			"y": 2225.8939318670327,
			"width": 389.62164306640625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1022904055,
			"version": 253,
			"versionNonce": 577772473,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "Singular Value Decomposition",
			"rawText": "Singular Value Decomposition",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Singular Value Decomposition",
			"lineHeight": 1.25
		},
		{
			"id": "IlwMj0Y5",
			"type": "text",
			"x": 1428.9087782182019,
			"y": 2286.6082175813185,
			"width": 719.999267578125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 46488503,
			"version": 225,
			"versionNonce": 289815705,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "A singular value decomposition factorizes a matrix M as UΛV = M where",
			"rawText": "A singular value decomposition factorizes a matrix M as UΛV = M where",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "A singular value decomposition factorizes a matrix M as UΛV = M where",
			"lineHeight": 1.25
		},
		{
			"id": "cw2OGd0R",
			"type": "text",
			"x": 1618.857054242845,
			"y": 2330.3293738252105,
			"width": 346.4196472167969,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 486015735,
			"version": 171,
			"versionNonce": 107299193,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "U contains the eigenvectors of MM",
			"rawText": "U contains the eigenvectors of MM",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "U contains the eigenvectors of MM",
			"lineHeight": 1.25
		},
		{
			"id": "ZjWlYP2s",
			"type": "text",
			"x": 1624.726374195911,
			"y": 2379.934896329463,
			"width": 342.4796447753906,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 289369655,
			"version": 182,
			"versionNonce": 252750425,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "V contains the eigenvectors of MM",
			"rawText": "V contains the eigenvectors of MM",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "V contains the eigenvectors of MM",
			"lineHeight": 1.25
		},
		{
			"id": "XLKzSFif",
			"type": "text",
			"x": 1456.9801001410983,
			"y": 2422.0612478126877,
			"width": 695.479248046875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1823958359,
			"version": 226,
			"versionNonce": 1142683449,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "27jCqZx8PytV3_kzrV7MM",
					"type": "arrow"
				}
			],
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "The square roots of the eigenvalues of MM are on the diagonal of Λ",
			"rawText": "The square roots of the eigenvalues of MM are on the diagonal of Λ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "The square roots of the eigenvalues of MM are on the diagonal of Λ",
			"lineHeight": 1.25
		},
		{
			"id": "aIZhEksf",
			"type": "text",
			"x": 1961.9025639684528,
			"y": 2316.4718213677224,
			"width": 16.079986572265625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2147102775,
			"version": 164,
			"versionNonce": 1685077241,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "T",
			"rawText": "T",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 2033202649,
			"isDeleted": false,
			"id": "mP6mCErz",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1943.8484133327852,
			"y": 2370.7174691723126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 16.079986572265625,
			"height": 25,
			"seed": 1581306329,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "T",
			"rawText": "T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 203,
			"versionNonce": 1765675705,
			"isDeleted": false,
			"id": "d0QOI60u",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1888.591770478166,
			"y": 2412.843820655537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 16.079986572265625,
			"height": 25,
			"seed": 911070903,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "T",
			"rawText": "T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "27jCqZx8PytV3_kzrV7MM",
			"type": "arrow",
			"x": 1792.3379401629413,
			"y": 2458.7921342672207,
			"width": 0,
			"height": 133.7126261594617,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1362207257,
			"version": 221,
			"versionNonce": 1696277527,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703686714258,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					133.7126261594617
				]
			],
			"lastCommittedPoint": [
				0,
				133.7126261594617
			],
			"startBinding": {
				"elementId": "XLKzSFif",
				"focus": 0.03560648009661382,
				"gap": 11.730886454532993
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "rESXPR6o",
			"type": "text",
			"x": 1628.899501898914,
			"y": 2617.1667759127263,
			"width": 349.29962158203125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 340989143,
			"version": 136,
			"versionNonce": 224491641,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "Setting M =     and computing SVD",
			"rawText": "Setting M =     and computing SVD",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Setting M =     and computing SVD",
			"lineHeight": 1.25
		},
		{
			"id": "J3UsBnZS",
			"type": "text",
			"x": 1484.2821432757341,
			"y": 2661.8298676266113,
			"width": 620.3793334960938,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1726370007,
			"version": 236,
			"versionNonce": 2003698009,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,\ni.e. the principal components\nand\nMatrix Λ contains the square roots of the\ncorresponding maximum eigenvalues on the diagonal",
			"rawText": "Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,\ni.e. the principal components\nand\nMatrix Λ contains the square roots of the\ncorresponding maximum eigenvalues on the diagonal",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 118,
			"containerId": null,
			"originalText": "Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,\ni.e. the principal components\nand\nMatrix Λ contains the square roots of the\ncorresponding maximum eigenvalues on the diagonal",
			"lineHeight": 1.25
		},
		{
			"id": "B6v3IO8D",
			"type": "text",
			"x": 1800.1347595867064,
			"y": 2503.185202848253,
			"width": 206.99244689941406,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 66162359,
			"version": 150,
			"versionNonce": 79064633,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686713964,
			"link": null,
			"locked": false,
			"text": "According to the definition\nof the covariance",
			"rawText": "According to the definition\nof the covariance",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "According to the definition\nof the covariance",
			"lineHeight": 1.25
		},
		{
			"id": "M1zDgOxG",
			"type": "text",
			"x": 1541.791298549172,
			"y": 2794.276330881939,
			"width": 505.36102294921875,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 286538873,
			"version": 415,
			"versionNonce": 1022405079,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686805935,
			"link": null,
			"locked": false,
			"text": "SVD is computationally faster and more stable than covariance\ncomputation + eigenvalue decomposition\n\nexcept!\nfor datasets where the dimensionality is as high\nas the number of samples then the complexity is O(d^3)",
			"rawText": "SVD is computationally faster and more stable than covariance\ncomputation + eigenvalue decomposition\n\nexcept!\nfor datasets where the dimensionality is as high\nas the number of samples then the complexity is O(d^3)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "SVD is computationally faster and more stable than covariance\ncomputation + eigenvalue decomposition\n\nexcept!\nfor datasets where the dimensionality is as high\nas the number of samples then the complexity is O(d^3)",
			"lineHeight": 1.25
		},
		{
			"id": "ZVtqQoLXuE_f42fhVtSb4",
			"type": "arrow",
			"x": 1418.2595183958306,
			"y": 2368.24989720018,
			"width": 396.1696555003331,
			"height": 2.7801379333354816,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1575194841,
			"version": 126,
			"versionNonce": 891622999,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703686829058,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-396.1696555003331,
					-2.7801379333354816
				]
			],
			"lastCommittedPoint": [
				-396.1696555003331,
				-2.7801379333354816
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dJ0lwqyr",
			"type": "text",
			"x": 1075.8879108500857,
			"y": 2294.591661336562,
			"width": 304.608642578125,
			"height": 120,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1862153079,
			"version": 161,
			"versionNonce": 370472375,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686857177,
			"link": null,
			"locked": false,
			"text": "Notice that we only ever need\nthe leading k PCAs, but SVD computes\nall of them!\n\n\nlets improve on that!",
			"rawText": "Notice that we only ever need\nthe leading k PCAs, but SVD computes\nall of them!\n\n\nlets improve on that!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "Notice that we only ever need\nthe leading k PCAs, but SVD computes\nall of them!\n\n\nlets improve on that!",
			"lineHeight": 1.25
		},
		{
			"id": "PG0Ls5k0",
			"type": "text",
			"x": 504.8247005157317,
			"y": 2258.5918703938096,
			"width": 339.6414489746094,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1868733719,
			"version": 125,
			"versionNonce": 1133848057,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703686984414,
			"link": null,
			"locked": false,
			"text": "Power iteraton Algorithm",
			"rawText": "Power iteraton Algorithm",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Power iteraton Algorithm",
			"lineHeight": 1.25
		},
		{
			"id": "ILXywG7o",
			"type": "text",
			"x": 316.059384726017,
			"y": 2304.0933217951833,
			"width": 719.9392700195312,
			"height": 275,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1526277945,
			"version": 390,
			"versionNonce": 542647511,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703687225048,
			"link": null,
			"locked": false,
			"text": "Initialize your w as a unit norm vector!\n\nMultiply the covariance matrix with w\n\n\nProceed to normalize the result by dividing it with one of its components\n\n\n\n\nRepeat this set using previous PCA result as the new w",
			"rawText": "Initialize your w as a unit norm vector!\n\nMultiply the covariance matrix with w\n\n\nProceed to normalize the result by dividing it with one of its components\n\n\n\n\nRepeat this set using previous PCA result as the new w",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 268,
			"containerId": null,
			"originalText": "Initialize your w as a unit norm vector!\n\nMultiply the covariance matrix with w\n\n\nProceed to normalize the result by dividing it with one of its components\n\n\n\n\nRepeat this set using previous PCA result as the new w",
			"lineHeight": 1.25
		},
		{
			"id": "Z6bGGyKA91GQ2gC3hLdv4",
			"type": "image",
			"x": 660.2396594027894,
			"y": 2376.5224226314012,
			"width": 44,
			"height": 39,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 993792345,
			"version": 111,
			"versionNonce": 1817894617,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703687048284,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0af7a45751872f28d33c6b6bd230b3a4c819d169",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JlWu4wsksWUAupx342c1b",
			"type": "image",
			"x": 644.5330538480245,
			"y": 2459.0665921498485,
			"width": 74,
			"height": 85,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1793957753,
			"version": 52,
			"versionNonce": 2031353945,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703687132210,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f9cfa63a7a70cb62bf28447fba1b45ceddbce43b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YX1xzOer",
			"type": "text",
			"x": 457.7054378654998,
			"y": 2591.0539770359865,
			"width": 445.58489990234375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 576861463,
			"version": 124,
			"versionNonce": 21269209,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703687228297,
			"link": null,
			"locked": false,
			"text": "This always converges and converges exponentially fast!",
			"rawText": "This always converges and converges exponentially fast!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "This always converges and converges exponentially fast!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 48,
			"versionNonce": 886569401,
			"isDeleted": true,
			"id": "vB86H0jR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 667.6315055822168,
			"y": 2472.4543122363034,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 36,
			"height": 35,
			"seed": 20267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703687116605,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "66a87a8c25d996fa398c8e13f45bc963f6b9abb6",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#b2f2bb",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 39.67314482452599,
		"scrollY": -2276.605726869702,
		"zoom": {
			"value": 1.0973087714508458
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