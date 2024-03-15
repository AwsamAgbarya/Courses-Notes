---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - MachineLearning
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

%%***>>>text element-link:[[Lagrange]]<<<***%%We Apply the Lagrange method! ^T6Rndoek

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


Proceed to normalize the result by dividing its largest component




Apply this iteration t times with a certain stopping criterion to stop
this will give you the largest principal component of the matrix
Remove it from the covariance matrix
Repeat this set using previous PCA result as the new w ^ILXywG7o

This always converges and converges exponentially fast! ^YX1xzOer

%%***>>>text element-link:[[Auto-encoders]]<<<***%%Reconstruction Error
This is quite similar to a linear
 auto encoder
or sparse encoding  ^ULVJC6Kk

Such that ui is the ith Eigenvector
the closer w gets to 1 AND the more
orthogonal w gets to other eigenvectors the less
error we have, and the further it strays
away towards any other eigenvector k
the more error k we have. ^nxuRQtK7

Think of this as slightly transforming w
to be in the shape of the covariance matrix
i.e the more we do it, the more w will head towards
the stretchy side of the distribution ^JoA44PJN

From the definition of the eigenvector
problem the matrix will only scale the
eigenvector k with its respective eigenvalue ^gJlZrhnk

if we iterate recursively
over this  ^AQ3gKlmk

Exponential convergence with t timesteps
from the start of the algorithm ^8QQPRG6P

The covariance matrix is a positive semi-definite
for a positive semi-definite matrix, the eigenvalues
of that matrix are all non-negative ^b91ibhDz

Since the covariance is also a Gramian matrix
is has wonderful properties like being symmetrical and
its eigenvectors are all orthogonal
and its diagonizable and
The trace of a Gram matrix is the sum of its eigenvalues ^M1POFb35

A Gram matrix (in very simple terms)
is a matrix that can be written as X X
such that each entry of it is a dot
product between the columns and rows
of X ^UUEz70NB

T ^ilaf71Lw


# Embedded files
c91e1b93b1e3dc3cabf2ba7a1e584e20b4834d3a: $$w^{(t+1)}= \frac{\hat{\Sigma} w^{(t)}}{\|\hat{\Sigma}w^{(t)}\|} $$
e9dcba6e8bc5e825ab330f15a6fc45cafa6a0bfc: $$\mathcal{E}_k(w^{(t)}) = \left| \frac{w^{(t)T}u_k}{w^{(t)T}u_1} \right| $$
5bd1518ab8f143e85fc852b01baa876f883f8e42: $$\mathcal{E}_k(w^{(t)}) = \left| \frac{\frac{\hat{\Sigma} w^{(t-1)}}{\|\hat{\Sigma}w^{(t-1)}\|} ^Tu_k}{\frac{\hat{\Sigma} w^{(t-1)}}{\|\hat{\Sigma}w^{(t-1)}\|} ^Tu_1} \right| $$
2fb11fc8e8d8c4c0cf01a843123c244cf00d3a66: $$\mathcal{E}_k(w^{(t)}) = \left|\frac{w^{(t-1)T}\hat{\Sigma} u_k}{ w^{(t-1)T}\hat{\Sigma} u_1} \right|$$
4557bc83f17f87b1afb5b4474e04fa5f367add50: $$\mathcal{E}_k(w^{(t)}) = \left|\frac{w^{(t-1)T}\lambda_k u_k}{ w^{(t-1)T}\lambda_1u_1} \right|$$
01a0e243793e059291cee04e4f2be77333c8acc2: $$\mathcal{E}_k(w^{(t)}) = \left|\frac{w^{(t-1)T}u_k}{ w^{(t-1)T}u_1} \frac{\lambda_k}{\lambda_1}\right |$$
548cc7046129ed759a87b14992346c7d00685543: $$\mathcal{E}_k(w^{(t)}) = \left|\frac{w^{(t-1)T}u_k}{ w^{(t-1)T}u_1}\right |\left | \frac{\lambda_k}{\lambda_1}\right |$$
311b570fb50553bfa919820491d3710b2931976e: $$\mathcal{E}_k(w^{(t)}) = \mathcal{E}_k(w^{(t-1)})  \left | \frac{\lambda_k}{\lambda_1}\right |$$
553e345046cb66721228bfab93bdcef0849b5d61: $$\mathcal{E}_k(w^{(t)}) = \mathcal{E}_k(w^{(0)})  \left | \frac{\lambda_k}{\lambda_1}\right |^{(t)}$$
680b1a394b55b2e3bfa1eaad4e665d9d9e3a1aec: $$\lambda = u^TSu = \sum_k (u^T (x_k - \mu))^2$$
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

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"type": "image",
			"version": 557,
			"versionNonce": 760210263,
			"isDeleted": false,
			"id": "bc6HfPu6c_2v9wxbzC2mx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1081.5323374426148,
			"y": 1156.5333617448428,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 492.2019344553877,
			"height": 395.2738998768826,
			"seed": 462429207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061863,
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
			"type": "rectangle",
			"version": 574,
			"versionNonce": 2056511897,
			"isDeleted": false,
			"id": "25CtriLNqHEhyZ_KXwsL4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 60,
			"angle": 0,
			"x": -1120.4207010807058,
			"y": 1050.73319048432,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 562.840471147974,
			"height": 532.4166618967322,
			"seed": 1990241431,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "-nNjNa1-BfKXZepbqGtZo",
					"type": "arrow"
				}
			],
			"updated": 1708785061863,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 153,
			"versionNonce": 306667639,
			"isDeleted": false,
			"id": "V1QpEfyGHj6r-AHKom7vo",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1748.8812064631773,
			"y": 2608.6908107709974,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 42.38003955272794,
			"height": 39.12003651021041,
			"seed": 1754218521,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061863,
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
			"type": "ellipse",
			"version": 189,
			"versionNonce": 548816505,
			"isDeleted": false,
			"id": "NTmx3hfR6gJYwm0rRUxid",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -302.8717948717949,
			"y": -480.9230769230769,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 437,
			"height": 205,
			"seed": 299449881,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "VbfAM2aO"
				}
			],
			"updated": 1708785061863,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 176,
			"versionNonce": 563231127,
			"isDeleted": false,
			"id": "VbfAM2aO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -213.21715585793055,
			"y": -413.40152199469804,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 257.68505859375,
			"height": 70,
			"seed": 946719481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Principal component\nanalysis",
			"rawText": "Principal component analysis",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "NTmx3hfR6gJYwm0rRUxid",
			"originalText": "Principal component analysis",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 586747737,
			"isDeleted": false,
			"id": "O1txWuPW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1222.6666666666672,
			"y": -185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 517.3302001953125,
			"height": 35,
			"seed": 1594093273,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is the motivation to seek PCA?",
			"rawText": "What is the motivation to seek PCA?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is the motivation to seek PCA?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 1885662903,
			"isDeleted": false,
			"id": "QSLlecAj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1354.6666666666672,
			"y": -151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 759.5191040039062,
			"height": 150,
			"seed": 1003707415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "djI-dvvGzKocn9NqHx712",
					"type": "arrow"
				}
			],
			"updated": 1708785061863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Often times in machine learning we have to deal with issues that involve\ndata with really high dimensions, and a much lower amount of available data\nN<<D\ni.e Face Recognition\nThe amount of data needed for a reliable result (e.g. no overfitting)\noften grows exponentially with the dimensionality",
			"rawText": "Often times in machine learning we have to deal with issues that involve\ndata with really high dimensions, and a much lower amount of available data\nN<<D\ni.e Face Recognition\nThe amount of data needed for a reliable result (e.g. no overfitting)\noften grows exponentially with the dimensionality",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Often times in machine learning we have to deal with issues that involve\ndata with really high dimensions, and a much lower amount of available data\nN<<D\ni.e Face Recognition\nThe amount of data needed for a reliable result (e.g. no overfitting)\noften grows exponentially with the dimensionality",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 658,
			"versionNonce": 1739570233,
			"isDeleted": false,
			"id": "djI-dvvGzKocn9NqHx712",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -583.8095238095235,
			"y": -121.51990911825001,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 174.9078947368419,
			"height": 1.3793125503489136,
			"seed": 468020215,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061863,
			"link": null,
			"locked": false,
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
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					174.9078947368419,
					1.3793125503489136
				]
			]
		},
		{
			"type": "text",
			"version": 224,
			"versionNonce": 2036596695,
			"isDeleted": false,
			"id": "AfNDVTA7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -310.4384605771013,
			"y": -244.0119047619051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 445.25787353515625,
			"height": 35,
			"seed": 1242342361,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Can we try our previous models?",
			"rawText": "Can we try our previous models?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can we try our previous models?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 447,
			"versionNonce": 1052626201,
			"isDeleted": false,
			"id": "SXbCGUMe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -399.88585844494014,
			"y": -196.67857142857173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 634.8193359375,
			"height": 225,
			"seed": 999683191,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
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
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "standard classification techniques become ill defined or\nsometimes ill-conditions for cases where we have high dimensional\ndata\nfor example when using a Bayes classifier we often need to \nestimate the covariance matrix\n\n\nestimating the covariance in this way only works when D<N\nand is only really accurate when D<<N",
			"rawText": "standard classification techniques become ill defined or\nsometimes ill-conditions for cases where we have high dimensional\ndata\nfor example when using a Bayes classifier we often need to \nestimate the covariance matrix\n\n\nestimating the covariance in this way only works when D<N\nand is only really accurate when D<<N",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "standard classification techniques become ill defined or\nsometimes ill-conditions for cases where we have high dimensional\ndata\nfor example when using a Bayes classifier we often need to \nestimate the covariance matrix\n\n\nestimating the covariance in this way only works when D<N\nand is only really accurate when D<<N",
			"lineHeight": 1.25,
			"baseline": 218
		},
		{
			"type": "image",
			"version": 88,
			"versionNonce": 1856236791,
			"isDeleted": false,
			"id": "FePwc-OzEhQirQT4lBYbT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -135.02614587315708,
			"y": -65.77506265664186,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 114.78412132024972,
			"height": 44.26315789473682,
			"seed": 692693783,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
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
			"type": "arrow",
			"version": 460,
			"versionNonce": 798409209,
			"isDeleted": false,
			"id": "yMdhAglt4OcT7fTzqBz_A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 239.0681190154886,
			"y": -118.13231700563065,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 219.71800398730073,
			"height": 1.3095821134157148,
			"seed": 1513139287,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
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
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					219.71800398730073,
					1.3095821134157148
				]
			]
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 1269380631,
			"isDeleted": false,
			"id": "AzmY3MHq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 666.9621032965887,
			"y": -180.85502217081216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 294.98126220703125,
			"height": 35,
			"seed": 1652887159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Well what can we do?",
			"rawText": "Well what can we do?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Well what can we do?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 436,
			"versionNonce": 121510617,
			"isDeleted": false,
			"id": "No6tqKWV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 475.47618363763434,
			"y": -132.87931366878774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 711.7992553710938,
			"height": 150,
			"seed": 395573625,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "yMdhAglt4OcT7fTzqBz_A",
					"type": "arrow"
				}
			],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Preform PCA to extract the key dimensions (features) that represent\nthe data the best, getting rid of all the other unecessary\nirrelevant features that are often regarded as noise\n\nwe ask our selves, which lower dimensional plane fits the data the best\nsuch that the noise is reduced and the important info is reserved?",
			"rawText": "Preform PCA to extract the key dimensions (features) that represent\nthe data the best, getting rid of all the other unecessary\nirrelevant features that are often regarded as noise\n\nwe ask our selves, which lower dimensional plane fits the data the best\nsuch that the noise is reduced and the important info is reserved?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Preform PCA to extract the key dimensions (features) that represent\nthe data the best, getting rid of all the other unecessary\nirrelevant features that are often regarded as noise\n\nwe ask our selves, which lower dimensional plane fits the data the best\nsuch that the noise is reduced and the important info is reserved?",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 91,
			"versionNonce": 661150519,
			"isDeleted": false,
			"id": "NroQjAu80s-pv8B6Oayqa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -248.34406168306907,
			"y": 72.87402277804699,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 424,
			"height": 306,
			"seed": 1281500535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
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
			"type": "text",
			"version": 84,
			"versionNonce": 642209721,
			"isDeleted": false,
			"id": "Y0JxAF5I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -306.99822737390934,
			"y": 379.245063502029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 543.1182861328125,
			"height": 35,
			"seed": 1530641401,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "We want to find a subspace such that",
			"rawText": "We want to find a subspace such that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to find a subspace such that",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 1178983511,
			"isDeleted": false,
			"id": "UxsIN7QM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -607.7522323572506,
			"y": 471.3038870314406,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 271.68511962890625,
			"height": 70,
			"seed": 781415415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Minimum distance to\nthe original data",
			"rawText": "Minimum distance to\nthe original data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Minimum distance to\nthe original data",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 248903833,
			"isDeleted": false,
			"id": "Rn86pbZk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -74.57529637594905,
			"y": 498.3627105608523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 47.68418884277344,
			"height": 35,
			"seed": 1537276151,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "and",
			"rawText": "and",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 1813395831,
			"isDeleted": false,
			"id": "CVctFYtn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 260.2921886704379,
			"y": 464.24506350202904,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#b2f2bb",
			"width": 297.94921875,
			"height": 70,
			"seed": 1703167097,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Data projected\nhas maximum variance",
			"rawText": "Data projected\nhas maximum variance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Data projected\nhas maximum variance",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "image",
			"version": 63,
			"versionNonce": 849182073,
			"isDeleted": false,
			"id": "_nIbjCMr4bIeMBa1Ypdrf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -691.2340354863558,
			"y": 545.4546372100546,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 194,
			"height": 78,
			"seed": 288345369,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "s_9NOFjwsO-gx_8JKB95B",
					"type": "arrow"
				}
			],
			"updated": 1708785061864,
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
			"type": "image",
			"version": 79,
			"versionNonce": 1847456407,
			"isDeleted": false,
			"id": "ynMk48mqQMYQdMtOP67f7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -495.80286139728696,
			"y": 556.1408720278682,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 225,
			"height": 61,
			"seed": 509885849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
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
			"type": "line",
			"version": 74,
			"versionNonce": 14771801,
			"isDeleted": false,
			"id": "43lvX0oi5FQflwSqs-Ji7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -685.2527360840038,
			"y": 570.7010224038082,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 135.2380952380953,
			"height": 82.85714285714283,
			"seed": 32098679,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
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
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 85034935,
			"isDeleted": false,
			"id": "vqYE8vEE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -956.7597072458882,
			"y": 496.30053240917744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 170.83978271484375,
			"height": 75,
			"seed": 1757501399,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "projection\nof all datapoints\nonto w",
			"rawText": "projection\nof all datapoints\nonto w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "projection\nof all datapoints\nonto w",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 139,
			"versionNonce": 880096057,
			"isDeleted": false,
			"id": "rYUCdtnxQwPcc8p_lfH9Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -726.6813075125752,
			"y": 700.7724509752368,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 459.99999999999994,
			"height": 157,
			"seed": 1978024119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-nNjNa1-BfKXZepbqGtZo",
					"type": "arrow"
				},
				{
					"id": "2Pn4MiSbKqrPyXB7ifK5Z",
					"type": "arrow"
				}
			],
			"updated": 1708785061864,
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
			"type": "arrow",
			"version": 64,
			"versionNonce": 1595242711,
			"isDeleted": false,
			"id": "s_9NOFjwsO-gx_8JKB95B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -487.1574979887658,
			"y": 633.5581652609511,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.9523809523809632,
			"height": 96.19047619047615,
			"seed": 528163161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "_nIbjCMr4bIeMBa1Ypdrf",
				"focus": -1.0945126839371382,
				"gap": 10.103528050896557
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
					0.9523809523809632,
					96.19047619047615
				]
			]
		},
		{
			"type": "image",
			"version": 75,
			"versionNonce": 1639736345,
			"isDeleted": false,
			"id": "M169W79oNePwMQdXjuGtW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 205.09501726922417,
			"y": 550.7054847166469,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 167.23790769707946,
			"height": 68.54012610536043,
			"seed": 300702231,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
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
			"type": "image",
			"version": 93,
			"versionNonce": 1908295159,
			"isDeleted": false,
			"id": "xiaMjxoD2tqh7XrGU2crO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 377.8475014414373,
			"y": 553.5892281852678,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 201.4012610536042,
			"height": 57.54321744388692,
			"seed": 500165591,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "65B9C-N3cJWsKBJNzelEW",
					"type": "arrow"
				}
			],
			"updated": 1708785061864,
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
			"type": "line",
			"version": 100,
			"versionNonce": 1152022777,
			"isDeleted": false,
			"id": "LapsooQmLIqJ-t4SXqRLP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 602.3623816154984,
			"y": 578.5156738746876,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 220.7123580668524,
			"height": 73.21190413924865,
			"seed": 672351863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
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
			]
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 202403607,
			"isDeleted": false,
			"id": "G66GX3dQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 768.0839135210529,
			"y": 527.8402892791852,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 206.8797607421875,
			"height": 75,
			"seed": 435983895,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061864,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The length of the\nprojected datapoints\nonto w",
			"rawText": "The length of the\nprojected datapoints\nonto w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The length of the\nprojected datapoints\nonto w",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 566,
			"versionNonce": 1321398745,
			"isDeleted": false,
			"id": "65B9C-N3cJWsKBJNzelEW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 403.1366962911884,
			"y": 624.8114367862713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.08066088010730255,
			"height": 96.91038288139134,
			"seed": 1254409433,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
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
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.08066088010730255,
					96.91038288139134
				]
			]
		},
		{
			"type": "image",
			"version": 149,
			"versionNonce": 679506999,
			"isDeleted": false,
			"id": "hNCShzthZwiPIaevWLWg3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 213.94217989861454,
			"y": 732.8411971343927,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 387.26694176103484,
			"height": 127.39044136876146,
			"seed": 265693719,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "65B9C-N3cJWsKBJNzelEW",
					"type": "arrow"
				}
			],
			"updated": 1708785061865,
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
			"type": "line",
			"version": 107,
			"versionNonce": 1964592825,
			"isDeleted": false,
			"id": "sBMkmetr_fbDlRxdZOBf1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 630.3551684922688,
			"y": 771.2340169234932,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 348.7116043242853,
			"height": 7.5205537071676645,
			"seed": 660470839,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					348.7116043242853,
					-7.5205537071676645
				]
			]
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 2129843543,
			"isDeleted": false,
			"id": "j6aQgVSJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 617.3072187976475,
			"y": 681.4928842259385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 338.2396240234375,
			"height": 75,
			"seed": 86935959,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "if the data isnt centered\nthen we have use the expectation\nof the datapoints",
			"rawText": "if the data isnt centered\nthen we have use the expectation\nof the datapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if the data isnt centered\nthen we have use the expectation\nof the datapoints",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 299,
			"versionNonce": 1045499801,
			"isDeleted": false,
			"id": "6oXBe-QWp5ioe_2lQbbps",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 979.7188075488452,
			"y": 696.9426922725559,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 419.6636570554519,
			"height": 83.65618204894511,
			"seed": 1406248505,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Tvm0sUahacXrqID-qwIaI",
					"type": "arrow"
				}
			],
			"updated": 1708785061865,
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
			"type": "text",
			"version": 37,
			"versionNonce": 1455166071,
			"isDeleted": false,
			"id": "vsS1E8Tk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -36.42803462126619,
			"y": 764.4651820120882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 22.212005615234375,
			"height": 45,
			"seed": 199347609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "=",
			"rawText": "=",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "=",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 675,
			"versionNonce": 278770809,
			"isDeleted": false,
			"id": "lNzIiHaP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1107.8517268223645,
			"y": 1071.6047383968014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 528.9393920898438,
			"height": 75,
			"seed": 1253007671,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "You can actually derive on of these equations\nfrom the other, so although they strive for different\ngoals they end up achieving the same one!",
			"rawText": "You can actually derive on of these equations\nfrom the other, so although they strive for different\ngoals they end up achieving the same one!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "You can actually derive on of these equations\nfrom the other, so although they strive for different\ngoals they end up achieving the same one!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 413182871,
			"isDeleted": false,
			"id": "MZVK4oEJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1023.9830966600255,
			"y": 781.4304349433158,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 340.64068603515625,
			"height": 20,
			"seed": 1002661017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What happens if we dont center the data?",
			"rawText": "What happens if we dont center the data?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What happens if we dont center the data?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 1069727065,
			"isDeleted": false,
			"id": "iWS4RmDJGSS9IrXtnOhbw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1364.348731715633,
			"y": 620.139565554583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 377.213497063138,
			"height": 0,
			"seed": 919169849,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061865,
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
					377.213497063138,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 550838455,
			"isDeleted": false,
			"id": "S_dQWWNhn5qbOabucQORE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1363.5215091343541,
			"y": 620.9667881358617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.8272225812786473,
			"height": 245.68510663980697,
			"seed": 1111938967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061865,
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
					-0.8272225812786473,
					-245.68510663980697
				]
			]
		},
		{
			"type": "line",
			"version": 137,
			"versionNonce": 1528015417,
			"isDeleted": false,
			"id": "sd4I6nwDAvsS1LJAIi2g6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1710.6788961883067,
			"y": 491.0158020741835,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 273.67747713944505,
			"height": 128.55413853105443,
			"seed": 765638199,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061865,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-273.67747713944505,
					-128.55413853105443
				]
			]
		},
		{
			"type": "freedraw",
			"version": 20,
			"versionNonce": 1358819799,
			"isDeleted": false,
			"id": "jmWAgyO-SWicpu0Ykxolw",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1680.9686063944628,
			"y": 496.1579676154257,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 979912441,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"version": 20,
			"versionNonce": 997456665,
			"isDeleted": false,
			"id": "_BC_5q8suAdF1yJi6U1IA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1691.2529374769472,
			"y": 456.73469846590234,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2147065241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"version": 23,
			"versionNonce": 1647288055,
			"isDeleted": false,
			"id": "hi962zFCWH6EUaGEYKBjS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1656.971833868666,
			"y": 488.73039516696474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268047781,
			"height": 1.7140551804139932,
			"seed": 664729657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 22,
			"versionNonce": 1364668409,
			"isDeleted": false,
			"id": "6SGUWuOHoz8DIVVp3tl2P",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1664.9707580439317,
			"y": 455.59199501229295,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1.1427034536093288,
			"height": 0.5713517268046644,
			"seed": 1559214457,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 24,
			"versionNonce": 1995352087,
			"isDeleted": false,
			"id": "wxpaYK3sw_d7F0ibfK3n4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1720.3918755439863,
			"y": 521.297443594832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268045507,
			"height": 3.4281103608282137,
			"seed": 305114585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 17,
			"versionNonce": 851495129,
			"isDeleted": false,
			"id": "x-SBUcXN7N0MHl08m6fr7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1720.9632272707909,
			"y": 473.8752502700429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1037687287,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"version": 19,
			"versionNonce": 1831832887,
			"isDeleted": false,
			"id": "0nEZQ11VfqE1lKyxoyKm8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1706.6794341006737,
			"y": 509.2990573319335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268047781,
			"height": 1.71405518041405,
			"seed": 38201687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 21,
			"versionNonce": 1766081977,
			"isDeleted": false,
			"id": "XoZHbvHjtFc0XQDO2ypAn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1738.1037790749315,
			"y": 479.58876753808977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.2854069072186576,
			"height": 0,
			"seed": 1786196727,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 19,
			"versionNonce": 1884737111,
			"isDeleted": false,
			"id": "Zv1gEVlcYIMB8lh3eRyXG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1632.4037096160646,
			"y": 472.1611950896289,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0,
			"height": 1.1427034536094425,
			"seed": 208895703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061865,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 20,
			"versionNonce": 337561,
			"isDeleted": false,
			"id": "L2v7QE4LRZeSBg--52SBS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1670.1129235851738,
			"y": 431.59522248649614,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268047781,
			"height": 1.71405518041405,
			"seed": 177625207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 1262021495,
			"isDeleted": false,
			"id": "uVBVVqLsCTp68bid3ANM_",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1602.1220680954161,
			"y": 463.0195674607539,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 400253561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 1370942329,
			"isDeleted": false,
			"id": "iGGqxxzHLtTYO0LRdu-4W",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1613.5491026315099,
			"y": 424.7390017648399,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1814587673,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 2048550039,
			"isDeleted": false,
			"id": "kcDoZ5fPhA9k-VRQygPBG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1653.543723507838,
			"y": 445.3076639298086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1575449529,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 20,
			"versionNonce": 379393113,
			"isDeleted": false,
			"id": "8z-PFDK2U8FwkM5JgQeFg",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1531.274453971635,
			"y": 446.450367383418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.2854069072186576,
			"height": 1.7140551804141069,
			"seed": 1554448985,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 2091891127,
			"isDeleted": false,
			"id": "ftYbNoR_IyYF-HL0inlDf",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1583.2674611108614,
			"y": 407.5984499606993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 120346969,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 18,
			"versionNonce": 847978809,
			"isDeleted": false,
			"id": "Q0Zf3nwQqycB2LSEK4wws",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1587.838274925299,
			"y": 446.450367383418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1.7140551804141069,
			"height": 4.570813814437486,
			"seed": 1331055609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 1746758359,
			"isDeleted": false,
			"id": "6IbIsuvyXSkm162FMj3db",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1544.4155436881429,
			"y": 427.0244086720586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 92618041,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 1122275865,
			"isDeleted": false,
			"id": "K2enbK_2kHcwBz97CxMHy",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1598.1226060077834,
			"y": 402.4562844194571,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 664222681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 955774967,
			"isDeleted": false,
			"id": "NPj158s3s2sF0-iwn-BTB",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1533.5598608788537,
			"y": 394.4573602441915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2090745465,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 17,
			"versionNonce": 1822222073,
			"isDeleted": false,
			"id": "IeEoeYyC-u6xEf8rUCLSJ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1584.9815162912755,
			"y": 409.88385686791804,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268045507,
			"height": 0,
			"seed": 520668441,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 18,
			"versionNonce": 1698947351,
			"isDeleted": false,
			"id": "hDqtW2fDeUGvT_AvwY6dL",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1539.8447298737053,
			"y": 400.74222923904307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.2854069072186576,
			"height": 2.8567586340234357,
			"seed": 755856761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 18,
			"versionNonce": 1782030297,
			"isDeleted": false,
			"id": "hR9Wu-qe_aIvXyEN1SnIc",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1563.8415023995021,
			"y": 386.4584360689259,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.2854069072186576,
			"height": 2.8567586340234357,
			"seed": 154093241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 18,
			"versionNonce": 779462199,
			"isDeleted": false,
			"id": "t6RlvsoHn_mCBzbd4jLcn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1622.690730260385,
			"y": 415.0260224091602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.8567586340232083,
			"height": 0,
			"seed": 177416185,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 1506294969,
			"isDeleted": false,
			"id": "3mNiiMekhfUPlJ5ZxNIBG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1560.413392038674,
			"y": 404.17033959987117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2087524665,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 863094615,
			"isDeleted": false,
			"id": "GyL5DppQ0-PEww2a4Sh44",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1487.8517227344787,
			"y": 433.3092776669102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 45914073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 1257389465,
			"isDeleted": false,
			"id": "KGoWRyaOOZYfLnz5jADhn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1554.699874770627,
			"y": 379.60221534726963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 854661753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 19,
			"versionNonce": 1116521591,
			"isDeleted": false,
			"id": "zp5bKRX_GtMorBUkfkJ36",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1534.1312126056584,
			"y": 419.59683622359773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 3.4281103608282137,
			"height": 5.142165541242207,
			"seed": 1299783961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 216605305,
			"isDeleted": false,
			"id": "RPStSGhjsWFSymkU1RVPD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1510.7057918066662,
			"y": 376.17410498644153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 452396857,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 20,
			"versionNonce": 1804279191,
			"isDeleted": false,
			"id": "CfUtyckJx4E82bEneVE1I",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1492.4225365489162,
			"y": 429.88116730608203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.285406907218885,
			"height": 0.5713517268046644,
			"seed": 589645273,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 1014000473,
			"isDeleted": false,
			"id": "4Fin5cKU-RrQWAAPgb4w0",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1494.1365917293303,
			"y": 409.88385686791804,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 9379033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 1369526967,
			"isDeleted": false,
			"id": "0WoKh2U-8oMQss75HtXjz",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1519.8474194355413,
			"y": 421.3108914040118,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 179683193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 299604025,
			"isDeleted": false,
			"id": "wu-A3fylwDm8_awJDDMHG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1475.2819847447756,
			"y": 395.6000636978009,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1055122969,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 1031005143,
			"isDeleted": false,
			"id": "bzWOwx0Yf1ZNw9FlnoQM9",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1511.277143533471,
			"y": 402.4562844194571,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1117262009,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 15,
			"versionNonce": 1863199001,
			"isDeleted": false,
			"id": "eYMpROsaB6pCq6Y7uXitA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1441.0008811364946,
			"y": 387.0297877957306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1306574681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 1863799031,
			"isDeleted": false,
			"id": "Wn7INN9Gs-ihoTxyIaP5B",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1474.710633017971,
			"y": 410.45520859472276,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1792026073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 763076089,
			"isDeleted": false,
			"id": "UGMrtx3VShBuI8cergWVH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1454.713322579807,
			"y": 392.17195333697276,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 432498809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 806361623,
			"isDeleted": false,
			"id": "N_vxwvL2-XSbmHf0pLZzk",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1442.143584590104,
			"y": 369.88923599159,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1091186457,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 740783833,
			"isDeleted": false,
			"id": "s26Rw4BzIROBYf4B5ruR0",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1418.1468120643071,
			"y": 366.4611256307619,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2090269113,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 626179895,
			"isDeleted": false,
			"id": "i2enFuRALRd6Q7NWmxfO7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1445.0003432241274,
			"y": 342.464353104965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 184305753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 497365945,
			"isDeleted": false,
			"id": "mTWL7tNjEpld6kbq0p0St",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1510.1344400798616,
			"y": 372.74599462561343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 391682809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 1631830103,
			"isDeleted": false,
			"id": "2t25ubcz0SGFjB5IQZNCr",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1467.8544122963149,
			"y": 340.1789461977463,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1130000793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 370693273,
			"isDeleted": false,
			"id": "WXYTAnNASnHILZb3wy4P8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1467.8544122963149,
			"y": 362.4616635431291,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1900039225,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 901225847,
			"isDeleted": false,
			"id": "QKvX9gO9IrGc9Tyszy4Kk",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1508.991736626252,
			"y": 352.1773324606447,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1306045145,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061866,
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
			"version": 11,
			"versionNonce": 1496603001,
			"isDeleted": false,
			"id": "5r46KNGeobogran8dExOb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1458.7127846674398,
			"y": 354.46273936786343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 444730745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1173542551,
			"isDeleted": false,
			"id": "cn1HVMEBl6bw0eqFxa_n_",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1517.5620125283226,
			"y": 356.7481462750822,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 925561881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1748812377,
			"isDeleted": false,
			"id": "xy1xXCFuNTp3vc9-WXBGA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1487.8517227344787,
			"y": 341.32164965135564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1817304761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1487530935,
			"isDeleted": false,
			"id": "eTr375Edmwz5Fa1etBJUU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1491.8511848221117,
			"y": 374.4600498060275,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1963281753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1342508857,
			"isDeleted": false,
			"id": "Nr8aklFrzoTPn9WQfCjIV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1545.5582471417522,
			"y": 362.4616635431291,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1222885369,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1778474199,
			"isDeleted": false,
			"id": "86QKur3ss0zxlWL96Ixd4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1525.5609367035881,
			"y": 373.3173463524181,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 639350425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 921747481,
			"isDeleted": false,
			"id": "16mGbLYXR7A8iLVQUOlF7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1478.7100951056038,
			"y": 346.46381519259785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1533784377,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 2106436087,
			"isDeleted": false,
			"id": "Eoe72xJndrjf6B1Nw-72d",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1516.419309074713,
			"y": 382.45897398129307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1377972185,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 720590073,
			"isDeleted": false,
			"id": "E3d6tC3qNXl1dk-vKBJxz",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1548.9863575025802,
			"y": 379.03086362046497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1478341241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 810767127,
			"isDeleted": false,
			"id": "Kmko2RQ5ELm7FltN-I6TT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1572.4117783015724,
			"y": 452.16388465146485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 701282585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 797986265,
			"isDeleted": false,
			"id": "8tbJGpvRLwx7b600uL1gn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1580.9820542036427,
			"y": 405.8843947802852,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1009632185,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 180803639,
			"isDeleted": false,
			"id": "h3l2jheh2JUTxH86uHC7L",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1555.8425782242366,
			"y": 433.8806293937149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1187992153,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 198912697,
			"isDeleted": false,
			"id": "RjxEaByl6vWlOu1m6VfB4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1592.980440466541,
			"y": 412.7406155019415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 231728377,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 315406679,
			"isDeleted": false,
			"id": "5-UACGfasKFqHGp7mX6PT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1584.9815162912755,
			"y": 437.308739754543,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1809709977,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 14,
			"versionNonce": 1484221337,
			"isDeleted": false,
			"id": "kDzFx4W1Hp0Q_HVw2Nnsi",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1550.1290609561897,
			"y": 439.02279493495706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 2.8567586340232083,
			"height": 0.5713517268046644,
			"seed": 473437753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 13,
			"versionNonce": 498693751,
			"isDeleted": false,
			"id": "tiyOgGAEAs6nsAlHuJ5pn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1602.6934198222207,
			"y": 446.450367383418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268047781,
			"height": 0,
			"seed": 1067079545,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 11,
			"versionNonce": 1301844089,
			"isDeleted": false,
			"id": "nYKbFpaBlcVKKmhFAUlH-",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1635.2604682500878,
			"y": 416.16872586276963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 544705497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1649512343,
			"isDeleted": false,
			"id": "i6oFJdeDty1_L2_myj06e",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1610.1209922706817,
			"y": 467.0190295483867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 262180473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 13,
			"versionNonce": 1359092057,
			"isDeleted": false,
			"id": "PxsIfqNjpPSVxK-jHGcQT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1634.1177647964785,
			"y": 429.88116730608203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0,
			"height": 1.7140551804141069,
			"seed": 661460249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 1254720695,
			"isDeleted": false,
			"id": "vuXhh5PjteC5cCPbevby4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1642.1166889717442,
			"y": 441.8795535689805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 3.4281103608279864,
			"height": 1.1427034536093856,
			"seed": 1556071801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 11,
			"versionNonce": 1141343801,
			"isDeleted": false,
			"id": "g35RSBA5Oqz4SpQ7KrLOP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1606.121530183049,
			"y": 433.3092776669102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1532254105,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 13,
			"versionNonce": 113628631,
			"isDeleted": false,
			"id": "GWPZjy0Ui3IsQ2kzlSS7Y",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1707.822137554283,
			"y": 443.59360874939455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.5713517268047781,
			"height": 0,
			"seed": 477884985,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 11,
			"versionNonce": 294410009,
			"isDeleted": false,
			"id": "gLfoh18MmMYDd6ELKVNC6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1669.541571858369,
			"y": 444.7363122030039,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1866493593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1566245623,
			"isDeleted": false,
			"id": "XCYPvG-bvH8DTgrkOyHMc",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1702.1086202862361,
			"y": 469.87578818241013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1361799481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 2080639993,
			"isDeleted": false,
			"id": "kpIOQChFDGsSdzCE_YwWT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1705.5367306470644,
			"y": 447.5930708370273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1448929241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 11,
			"versionNonce": 1057852439,
			"isDeleted": false,
			"id": "jkaACq-E7oUurDdZaKGCG",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1715.249710002744,
			"y": 484.1595813525273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 414411385,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 728900825,
			"isDeleted": false,
			"id": "LbUz1LbPlDfu07hqaRKqP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1760.3864964203144,
			"y": 491.0158020741835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 839124601,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 399634743,
			"isDeleted": false,
			"id": "KTCXtp3Z570g4e2IT1ex1",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1742.674592889369,
			"y": 508.1563538783241,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1172540697,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 2070553017,
			"isDeleted": false,
			"id": "50pPC0feyUuQXKt0ZXSKP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1738.1037790749315,
			"y": 485.30228480613664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1380259769,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 1628222039,
			"isDeleted": false,
			"id": "s7pyFPMyIk5vpcC2AsUPe",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1727.8194479924473,
			"y": 505.87094697110535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1622615641,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 152011417,
			"isDeleted": false,
			"id": "XQMtONawUC81O0O4g77BM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1679.8259029408534,
			"y": 500.1574297030585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1196964089,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 1938968439,
			"isDeleted": false,
			"id": "mE9T-0s0tuTnaXJ517iPP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1647.2588545129863,
			"y": 481.87417444530854,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 852938649,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 18204537,
			"isDeleted": false,
			"id": "hgq1ZyLKr8gdSRW0Wd6DM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1624.4047854407988,
			"y": 487.01633998655075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1886480953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 430393495,
			"isDeleted": false,
			"id": "q4e01-1iSIF2rrC5j-HQC",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1660.3999442294942,
			"y": 472.73254681643357,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2012645593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 4,
			"versionNonce": 767586393,
			"isDeleted": false,
			"id": "6zvRaJoz6aeDS6iEcSL-U",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1688.3961788429237,
			"y": 503.0141883370819,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 902081401,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"version": 150,
			"versionNonce": 1627397559,
			"isDeleted": false,
			"id": "o2G5_27oFLI3hTNQ0tsF2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1366.1538049250805,
			"y": 619.569940605238,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 270.65605454449087,
			"height": 267.7787865073742,
			"seed": 827209719,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					270.65605454449087,
					-267.7787865073742
				]
			]
		},
		{
			"type": "text",
			"version": 14,
			"versionNonce": 1155726649,
			"isDeleted": false,
			"id": "Dm0tPI4D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1704.573291638042,
			"y": 494.3234020497689,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 105.93621826171875,
			"height": 20,
			"seed": 369021687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "what we need",
			"rawText": "what we need",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "what we need",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 14,
			"versionNonce": 750866135,
			"isDeleted": false,
			"id": "b3BsXysy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1594.0252273850524,
			"y": 317.61632101073366,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 97.66421508789062,
			"height": 20,
			"seed": 1325704249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "what we get",
			"rawText": "what we get",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "what we get",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1977675289,
			"isDeleted": false,
			"id": "pJWcC8x6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.47562375844711724,
			"x": 1043.8058365743618,
			"y": -167.6794935126461,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 338.9447326660156,
			"height": 20,
			"seed": 1991304633,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "note that this method is not very robust!!",
			"rawText": "note that this method is not very robust!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "note that this method is not very robust!!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 304,
			"versionNonce": 125787127,
			"isDeleted": false,
			"id": "Gs2oeCz7fbyeN3SF7KDsu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 166.21204298424146,
			"y": 835.2387348268112,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 738.930404670752,
			"height": 254.53293150267177,
			"seed": 532587033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mTDjVmYp2hFO4MiwyW9yR",
					"type": "arrow"
				}
			],
			"updated": 1708785061867,
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
			"type": "arrow",
			"version": 77,
			"versionNonce": 934134521,
			"isDeleted": false,
			"id": "Tvm0sUahacXrqID-qwIaI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1407.6892633926132,
			"y": 762.1852125432628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 146.25678106505939,
			"height": 120.44676087710798,
			"seed": 979721751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6oXBe-QWp5ioe_2lQbbps",
				"focus": 0.6997318883307195,
				"gap": 8.306798788315973
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
					144.10594604939706,
					-11.829592586144486
				],
				[
					146.25678106505939,
					-120.44676087710798
				]
			]
		},
		{
			"type": "line",
			"version": 188,
			"versionNonce": 893306135,
			"isDeleted": false,
			"id": "SSEgKVMf7l_bvow-IlKRZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 438.9522059462013,
			"y": 1088.8717438103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 139.98269887539334,
			"height": 45.101593841417525,
			"seed": 58057049,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
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
			]
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1456274393,
			"isDeleted": false,
			"id": "zykM2AsW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -327.48913432755467,
			"y": 1094.2157144082532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 548.4970703125,
			"height": 20,
			"seed": 1235366487,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "where Σ is the covariance matrix (recall: the data is assumed to be",
			"rawText": "where Σ is the covariance matrix (recall: the data is assumed to be",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "where Σ is the covariance matrix (recall: the data is assumed to be",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 66,
			"versionNonce": 91490871,
			"isDeleted": false,
			"id": "kXklT2FM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -390.9212021986484,
			"y": 1124.2157144082532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 675.3612060546875,
			"height": 20,
			"seed": 1049756313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "centered i.e the mean is 0). The covariance matrix does not depend on w and can be",
			"rawText": "centered i.e the mean is 0). The covariance matrix does not depend on w and can be",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "centered i.e the mean is 0). The covariance matrix does not depend on w and can be",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 1129453753,
			"isDeleted": false,
			"id": "6OY1Nj9o",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -100.44869090714451,
			"y": 1154.2157144082532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 94.41618347167969,
			"height": 20,
			"seed": 762826615,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "precomputed",
			"rawText": "precomputed",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "precomputed",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 112,
			"versionNonce": 1694739287,
			"isDeleted": false,
			"id": "T6Rndoek",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 342.74728787899164,
			"y": 1404.8662071930125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 428.68182373046875,
			"height": 35,
			"seed": 1470806265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": "[[Lagrange]]",
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "We Apply the Lagrange method!",
			"rawText": "We Apply the Lagrange method!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We Apply the Lagrange method!",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 82,
			"versionNonce": 518035865,
			"isDeleted": false,
			"id": "3GS7ZJ_IMNvc0FzOCdrCZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 332.61611961673304,
			"y": 1448.2323089460413,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 439,
			"height": 65,
			"seed": 1513142777,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"type": "image",
			"version": 193,
			"versionNonce": 809642103,
			"isDeleted": false,
			"id": "8umN6qCtdMc2BJLEECo6T",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 278.6579994254936,
			"y": 1501.8274707946898,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 538.4832025191821,
			"height": 103.24302003187326,
			"seed": 1284547991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"type": "text",
			"version": 851,
			"versionNonce": 112285561,
			"isDeleted": false,
			"id": "oDBdCqop",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 974.1360930002447,
			"y": 1401.8166901527338,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 506.51287841796875,
			"height": 220,
			"seed": 1606436505,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AyiHakIC2UikaDzNEe84q",
					"type": "arrow"
				},
				{
					"id": "-xpNunWwiKaAAeVrVPwxw",
					"type": "arrow"
				},
				{
					"id": "MYo3pevYjmiOv52HYTzOI",
					"type": "arrow"
				}
			],
			"updated": 1708786194992,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Notice that the solution of PCA is the eigen vector of the cov\nmatrix! This makes so much sense because according to linear\nalgebra, the Eigenvectors are the vectors that do not get\ntransformed by the cov matrix, only scaled! (Rotation axis)\n\nThe cov matrix tells us how scaled the dsitribution is in each \ndirection and how sheared it is in each direction\n\nOur eigenvector w is Scaled by this transformation and THUS\nit means that its going along its \"stretched\" direction\nand we seek the K most important (highest scaled) vectors",
			"rawText": "Notice that the solution of PCA is the eigen vector of the cov\nmatrix! This makes so much sense because according to linear\nalgebra, the Eigenvectors are the vectors that do not get\ntransformed by the cov matrix, only scaled! (Rotation axis)\n\nThe cov matrix tells us how scaled the dsitribution is in each \ndirection and how sheared it is in each direction\n\nOur eigenvector w is Scaled by this transformation and THUS\nit means that its going along its \"stretched\" direction\nand we seek the K most important (highest scaled) vectors",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notice that the solution of PCA is the eigen vector of the cov\nmatrix! This makes so much sense because according to linear\nalgebra, the Eigenvectors are the vectors that do not get\ntransformed by the cov matrix, only scaled! (Rotation axis)\n\nThe cov matrix tells us how scaled the dsitribution is in each \ndirection and how sheared it is in each direction\n\nOur eigenvector w is Scaled by this transformation and THUS\nit means that its going along its \"stretched\" direction\nand we seek the K most important (highest scaled) vectors",
			"lineHeight": 1.25,
			"baseline": 214
		},
		{
			"type": "line",
			"version": 952,
			"versionNonce": 1156841879,
			"isDeleted": false,
			"id": "GigVJkzWOL2QNjNRNCIqw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1348.4585074202928,
			"y": 1704.396612242052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 325.3983824917017,
			"height": 195.67145259467793,
			"seed": 1142208889,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
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
			]
		},
		{
			"type": "line",
			"version": 244,
			"versionNonce": 897042265,
			"isDeleted": false,
			"id": "bwGcPxcO7CdbIWaHZY_CM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 995.2398224727762,
			"y": 1905.0439848244303,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 420.4675388106383,
			"height": 275.8209613962333,
			"seed": 781417047,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					420.4675388106383,
					-275.8209613962333
				]
			]
		},
		{
			"type": "arrow",
			"version": 189,
			"versionNonce": 1414379191,
			"isDeleted": false,
			"id": "AyiHakIC2UikaDzNEe84q",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1503.8290705933955,
			"y": 1527.424393770923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 261.8515650167242,
			"height": 1.2528783015154659,
			"seed": 45300855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oDBdCqop",
				"focus": 0.1522354065937468,
				"gap": 23.180099175182022
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
					261.8515650167242,
					-1.2528783015154659
				]
			]
		},
		{
			"type": "arrow",
			"version": 176,
			"versionNonce": 697791545,
			"isDeleted": false,
			"id": "-xpNunWwiKaAAeVrVPwxw",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 804.7229783477871,
			"y": 1507.378340946676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 146.58676127730496,
			"height": 3.7586349045463976,
			"seed": 952249241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "oDBdCqop",
				"focus": 0.1311317511721698,
				"gap": 22.82635337515262
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
					146.58676127730496,
					-3.7586349045463976
				]
			]
		},
		{
			"type": "arrow",
			"version": 46,
			"versionNonce": 1962133463,
			"isDeleted": false,
			"id": "mTDjVmYp2hFO4MiwyW9yR",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 468.268187378078,
			"y": 1115.9696982426035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0,
			"height": 272.8613907508352,
			"seed": 1514317113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Gs2oeCz7fbyeN3SF7KDsu",
				"focus": 0.182450356665389,
				"gap": 26.19803191312053
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
					272.8613907508352
				]
			]
		},
		{
			"type": "arrow",
			"version": 82,
			"versionNonce": 1525581081,
			"isDeleted": false,
			"id": "-nNjNa1-BfKXZepbqGtZo",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -542.7941364735577,
			"y": 869.4317565813482,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 285.047767746805,
			"height": 166.61242762665358,
			"seed": 1873910967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
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
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
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
			]
		},
		{
			"type": "text",
			"version": 226,
			"versionNonce": 1962587383,
			"isDeleted": false,
			"id": "WjniqIi9",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1917.1541072279474,
			"y": 1342.365676740643,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 429.88580322265625,
			"height": 35,
			"seed": 1229054327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Finding multiple PCA components",
			"rawText": "Finding multiple PCA components",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Finding multiple PCA components",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 1961916921,
			"isDeleted": false,
			"id": "uMnh8fH9",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1815.1045519694753,
			"y": 1398.9191891801568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 259.14105224609375,
			"height": 35,
			"seed": 1598903703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "1. Find Highest PCA",
			"rawText": "1. Find Highest PCA",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Find Highest PCA",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 1810300439,
			"isDeleted": false,
			"id": "xTQiZY5L",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1805.0948983543765,
			"y": 1492.0454275989446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 390.013671875,
			"height": 35,
			"seed": 1586160313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "2. Remove it from the data",
			"rawText": "2. Remove it from the data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2. Remove it from the data",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 1755370201,
			"isDeleted": false,
			"id": "99hlrZff",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1857.0099586624206,
			"y": 1546.601280003381,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 261.6890869140625,
			"height": 35,
			"seed": 763022391,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "X = X - W * W * X",
			"rawText": "X = X - W * W * X",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "X = X - W * W * X",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 212673335,
			"isDeleted": false,
			"id": "wW674Nte",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2057.875538244769,
			"y": 1533.2406630880087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 22.512100219726562,
			"height": 35,
			"seed": 1925450327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "T",
			"rawText": "T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 55,
			"versionNonce": 982716345,
			"isDeleted": false,
			"id": "05MmAoBR9sRKrUTUiX_Jz",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2045.2547386044348,
			"y": 1591.3336028608003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1.2330832089564865,
			"height": 76.45115895529375,
			"seed": 456649977,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.2330832089564865,
					76.45115895529375
				]
			]
		},
		{
			"type": "text",
			"version": 52,
			"versionNonce": 934388823,
			"isDeleted": false,
			"id": "abjC5Xzd",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1935.8454163818064,
			"y": 1674.8737340797752,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 216.35247802734375,
			"height": 20,
			"seed": 1748590489,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Projection in that dimension",
			"rawText": "Projection in that dimension",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Projection in that dimension",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 283816089,
			"isDeleted": false,
			"id": "axxAlj8A",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1836.58912766143,
			"y": 1442.4375772661783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 272.7796936035156,
			"height": 25,
			"seed": 126387671,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Compute leading eigenvector",
			"rawText": "Compute leading eigenvector",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Compute leading eigenvector",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 379,
			"versionNonce": 1288241527,
			"isDeleted": false,
			"id": "uny-hq7WbUMiJc_pgD-xJ",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1799.9445585546773,
			"y": 1797.1957527154034,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 511.1077945530523,
			"height": 259.8958324244283,
			"seed": 808651031,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
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
			"type": "text",
			"version": 172,
			"versionNonce": 22754681,
			"isDeleted": false,
			"id": "SBwsj06O",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1793.431417664697,
			"y": 1715.9980827928605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 504.84210205078125,
			"height": 70,
			"seed": 925557945,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061867,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "3. Take your h leading PCA and use\nthem to describe the data",
			"rawText": "3. Take your h leading PCA and use\nthem to describe the data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3. Take your h leading PCA and use\nthem to describe the data",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "arrow",
			"version": 391,
			"versionNonce": 1027062423,
			"isDeleted": false,
			"id": "edd0K1Un-fE1fJBez9y1V",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2148.644323124216,
			"y": 1456.1803717674516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 429.87176834185493,
			"height": 893.2179657040788,
			"seed": 833965495,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061868,
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
			]
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 522722905,
			"isDeleted": false,
			"id": "3Ve5EQd8",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2628.018326469966,
			"y": 1934.7078682953188,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 317.3253173828125,
			"height": 35,
			"seed": 2115235895,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Ways to compute PCA?",
			"rawText": "Ways to compute PCA?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ways to compute PCA?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 1571966903,
			"isDeleted": false,
			"id": "FfapMSBB",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1584.097590474061,
			"y": 2225.8939318670327,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 389.62164306640625,
			"height": 35,
			"seed": 1022904055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Singular Value Decomposition",
			"rawText": "Singular Value Decomposition",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Singular Value Decomposition",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 226,
			"versionNonce": 1227156281,
			"isDeleted": false,
			"id": "IlwMj0Y5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1428.9087782182019,
			"y": 2286.6082175813185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 719.999267578125,
			"height": 25,
			"seed": 46488503,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A singular value decomposition factorizes a matrix M as UΛV = M where",
			"rawText": "A singular value decomposition factorizes a matrix M as UΛV = M where",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A singular value decomposition factorizes a matrix M as UΛV = M where",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 172,
			"versionNonce": 2019377367,
			"isDeleted": false,
			"id": "cw2OGd0R",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1618.857054242845,
			"y": 2330.3293738252105,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 346.4196472167969,
			"height": 25,
			"seed": 486015735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "U contains the eigenvectors of MM",
			"rawText": "U contains the eigenvectors of MM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "U contains the eigenvectors of MM",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 183,
			"versionNonce": 934616089,
			"isDeleted": false,
			"id": "ZjWlYP2s",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1624.726374195911,
			"y": 2379.934896329463,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 342.4796447753906,
			"height": 25,
			"seed": 289369655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "V contains the eigenvectors of MM",
			"rawText": "V contains the eigenvectors of MM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V contains the eigenvectors of MM",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 516754935,
			"isDeleted": false,
			"id": "XLKzSFif",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1456.9801001410983,
			"y": 2422.0612478126877,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 695.479248046875,
			"height": 25,
			"seed": 1823958359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "27jCqZx8PytV3_kzrV7MM",
					"type": "arrow"
				}
			],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The square roots of the eigenvalues of MM are on the diagonal of Λ",
			"rawText": "The square roots of the eigenvalues of MM are on the diagonal of Λ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The square roots of the eigenvalues of MM are on the diagonal of Λ",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 1254895865,
			"isDeleted": false,
			"id": "aIZhEksf",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1961.9025639684528,
			"y": 2316.4718213677224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 16.080071585518972,
			"height": 25,
			"seed": 2147102775,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
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
			"version": 195,
			"versionNonce": 1007040279,
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
			"width": 16.080071585518972,
			"height": 25,
			"seed": 1581306329,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
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
			"version": 204,
			"versionNonce": 401451481,
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
			"width": 16.080071585518972,
			"height": 25,
			"seed": 911070903,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
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
			"type": "arrow",
			"version": 222,
			"versionNonce": 1719483447,
			"isDeleted": false,
			"id": "27jCqZx8PytV3_kzrV7MM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1792.3379401629413,
			"y": 2458.7921342672207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0,
			"height": 133.7126261594617,
			"seed": 1362207257,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XLKzSFif",
				"focus": 0.03560648009661382,
				"gap": 11.730886454532993
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
					133.7126261594617
				]
			]
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 942474937,
			"isDeleted": false,
			"id": "rESXPR6o",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1628.899501898914,
			"y": 2617.1667759127263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 349.29962158203125,
			"height": 25,
			"seed": 340989143,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Setting M =     and computing SVD",
			"rawText": "Setting M =     and computing SVD",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Setting M =     and computing SVD",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 239,
			"versionNonce": 510322649,
			"isDeleted": false,
			"id": "J3UsBnZS",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1484.2821432757341,
			"y": 2661.8298676266113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 620.3793334960938,
			"height": 125,
			"seed": 1726370007,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708788197627,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,\ni.e. the principal components\nand\nMatrix Λ contains the square roots of the\ncorresponding maximum eigenvalues on the diagonal",
			"rawText": "Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,\ni.e. the principal components\nand\nMatrix Λ contains the square roots of the\ncorresponding maximum eigenvalues on the diagonal",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Matrix U = (w1 . . . wd ) that contains the eigenvectors of Σ,\ni.e. the principal components\nand\nMatrix Λ contains the square roots of the\ncorresponding maximum eigenvalues on the diagonal",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1445840793,
			"isDeleted": false,
			"id": "B6v3IO8D",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1800.1347595867064,
			"y": 2503.185202848253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 206.99244689941406,
			"height": 40,
			"seed": 66162359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "According to the definition\nof the covariance",
			"rawText": "According to the definition\nof the covariance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "According to the definition\nof the covariance",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 416,
			"versionNonce": 1109842551,
			"isDeleted": false,
			"id": "M1zDgOxG",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1541.791298549172,
			"y": 2794.276330881939,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 505.36102294921875,
			"height": 120,
			"seed": 286538873,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "SVD is computationally faster and more stable than covariance\ncomputation + eigenvalue decomposition\n\nexcept!\nfor datasets where the dimensionality is as high\nas the number of samples then the complexity is O(d^3)",
			"rawText": "SVD is computationally faster and more stable than covariance\ncomputation + eigenvalue decomposition\n\nexcept!\nfor datasets where the dimensionality is as high\nas the number of samples then the complexity is O(d^3)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SVD is computationally faster and more stable than covariance\ncomputation + eigenvalue decomposition\n\nexcept!\nfor datasets where the dimensionality is as high\nas the number of samples then the complexity is O(d^3)",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 127,
			"versionNonce": 2082696313,
			"isDeleted": false,
			"id": "ZVtqQoLXuE_f42fhVtSb4",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1418.2595183958306,
			"y": 2368.24989720018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 396.1696555003331,
			"height": 2.7801379333354816,
			"seed": 1575194841,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061868,
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
					-396.1696555003331,
					-2.7801379333354816
				]
			]
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 1534227351,
			"isDeleted": false,
			"id": "dJ0lwqyr",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1075.8879108500857,
			"y": 2294.591661336562,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 304.608642578125,
			"height": 120,
			"seed": 1862153079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Notice that we only ever need\nthe leading k PCAs, but SVD computes\nall of them!\n\n\nlets improve on that!",
			"rawText": "Notice that we only ever need\nthe leading k PCAs, but SVD computes\nall of them!\n\n\nlets improve on that!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notice that we only ever need\nthe leading k PCAs, but SVD computes\nall of them!\n\n\nlets improve on that!",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 567375193,
			"isDeleted": false,
			"id": "PG0Ls5k0",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 504.8247005157317,
			"y": 2258.5918703938096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 339.6414489746094,
			"height": 35,
			"seed": 1868733719,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Power iteraton Algorithm",
			"rawText": "Power iteraton Algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power iteraton Algorithm",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 691,
			"versionNonce": 908978359,
			"isDeleted": false,
			"id": "ILXywG7o",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 336.0993932709389,
			"y": 2304.0933217951833,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 679.8592529296875,
			"height": 350,
			"seed": 1526277945,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Initialize your w as a unit norm vector!\n\nMultiply the covariance matrix with w\n\n\nProceed to normalize the result by dividing its largest component\n\n\n\n\nApply this iteration t times with a certain stopping criterion to stop\nthis will give you the largest principal component of the matrix\nRemove it from the covariance matrix\nRepeat this set using previous PCA result as the new w",
			"rawText": "Initialize your w as a unit norm vector!\n\nMultiply the covariance matrix with w\n\n\nProceed to normalize the result by dividing its largest component\n\n\n\n\nApply this iteration t times with a certain stopping criterion to stop\nthis will give you the largest principal component of the matrix\nRemove it from the covariance matrix\nRepeat this set using previous PCA result as the new w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Initialize your w as a unit norm vector!\n\nMultiply the covariance matrix with w\n\n\nProceed to normalize the result by dividing its largest component\n\n\n\n\nApply this iteration t times with a certain stopping criterion to stop\nthis will give you the largest principal component of the matrix\nRemove it from the covariance matrix\nRepeat this set using previous PCA result as the new w",
			"lineHeight": 1.25,
			"baseline": 343
		},
		{
			"type": "image",
			"version": 112,
			"versionNonce": 2055955001,
			"isDeleted": false,
			"id": "Z6bGGyKA91GQ2gC3hLdv4",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 660.2396594027894,
			"y": 2376.5224226314012,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 44,
			"height": 39,
			"seed": 993792345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
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
			"type": "text",
			"version": 168,
			"versionNonce": 1342028247,
			"isDeleted": false,
			"id": "YX1xzOer",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 461.6345876166238,
			"y": 2654.829426163232,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 445.58489990234375,
			"height": 20,
			"seed": 576861463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZQKz0NgIRvOQvZh3elPGk",
					"type": "arrow"
				}
			],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This always converges and converges exponentially fast!",
			"rawText": "This always converges and converges exponentially fast!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This always converges and converges exponentially fast!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 45,
			"versionNonce": 53785369,
			"isDeleted": false,
			"id": "2Pn4MiSbKqrPyXB7ifK5Z",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -737.5765523310138,
			"y": 781.6098785937414,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 188.84666794233556,
			"height": 3.824798005216394,
			"seed": 1358274871,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rYUCdtnxQwPcc8p_lfH9Y",
				"focus": -0.049470528501092154,
				"gap": 10.895244818438442
			},
			"endBinding": {
				"elementId": "ULVJC6Kk",
				"focus": -0.10414380163558605,
				"gap": 12.997698888065202
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
					-188.84666794233556,
					3.824798005216394
				]
			]
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 2113300215,
			"isDeleted": false,
			"id": "ULVJC6Kk",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1189.3414971643442,
			"y": 752.6581301887275,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 249.9205780029297,
			"height": 80,
			"seed": 16979865,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2Pn4MiSbKqrPyXB7ifK5Z",
					"type": "arrow"
				}
			],
			"updated": 1708785061868,
			"link": "[[Auto-encoders]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Reconstruction Error\nThis is quite similar to a linear\n auto encoder\nor sparse encoding ",
			"rawText": "Reconstruction Error\nThis is quite similar to a linear\n auto encoder\nor sparse encoding ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reconstruction Error\nThis is quite similar to a linear\n auto encoder\nor sparse encoding ",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 135,
			"versionNonce": 1346430969,
			"isDeleted": false,
			"id": "ZQKz0NgIRvOQvZh3elPGk",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 686.3276932134395,
			"y": 2685.601238847548,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 1.6064739511069774,
			"height": 100.7563617617352,
			"seed": 1861511735,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "YX1xzOer",
				"focus": -0.010004849109786728,
				"gap": 10.771812684316046
			},
			"endBinding": {
				"elementId": "fyN1JMdK",
				"focus": -0.019400948391454256,
				"gap": 9.260776866985225
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
					-1.6064739511069774,
					100.7563617617352
				]
			]
		},
		{
			"type": "image",
			"version": 117,
			"versionNonce": 2124181527,
			"isDeleted": false,
			"id": "1d46qou6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 589.300713759411,
			"y": 2466.6914519002125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 178.43667905139634,
			"height": 70.80820597277632,
			"seed": 82537,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785061868,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c91e1b93b1e3dc3cabf2ba7a1e584e20b4834d3a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 116,
			"versionNonce": 917569273,
			"isDeleted": false,
			"id": "fyN1JMdK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 580.453254815862,
			"y": 2798.284431611322,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.94863160639107,
			"height": 62.7144580451433,
			"seed": 73389,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZQKz0NgIRvOQvZh3elPGk",
					"type": "arrow"
				},
				{
					"id": "opZIt8z54cCICAA7jM0Z8",
					"type": "arrow"
				}
			],
			"updated": 1708785761495,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e9dcba6e8bc5e825ab330f15a6fc45cafa6a0bfc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 64,
			"versionNonce": 60533273,
			"isDeleted": false,
			"id": "opZIt8z54cCICAA7jM0Z8",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 801.3391647055273,
			"y": 2822.794662787697,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 122.58947223506846,
			"height": 3.1433198008990075,
			"seed": 723310423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785761495,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fyN1JMdK",
				"focus": -0.27601535484623585,
				"gap": 15.049836489521283
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
					122.58947223506846,
					3.1433198008990075
				]
			]
		},
		{
			"type": "text",
			"version": 323,
			"versionNonce": 172076857,
			"isDeleted": false,
			"id": "nxuRQtK7",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 890.0492001927632,
			"y": 2816.5080231858983,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 391.52081298828125,
			"height": 120,
			"seed": 462342777,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785433929,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Such that ui is the ith Eigenvector\nthe closer w gets to 1 AND the more\northogonal w gets to other eigenvectors the less\nerror we have, and the further it strays\naway towards any other eigenvector k\nthe more error k we have.",
			"rawText": "Such that ui is the ith Eigenvector\nthe closer w gets to 1 AND the more\northogonal w gets to other eigenvectors the less\nerror we have, and the further it strays\naway towards any other eigenvector k\nthe more error k we have.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Such that ui is the ith Eigenvector\nthe closer w gets to 1 AND the more\northogonal w gets to other eigenvectors the less\nerror we have, and the further it strays\naway towards any other eigenvector k\nthe more error k we have.",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 117,
			"versionNonce": 1050623545,
			"isDeleted": false,
			"id": "mJ71SuAIei47JfBMHRHCc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 632.385725407196,
			"y": 2401.589809467205,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 355.19513750160843,
			"height": 77.01133512203023,
			"seed": 1577552279,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785064933,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "JoA44PJN",
				"focus": 0.15277884104010184,
				"gap": 15.085423977200662
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
					-240.463964768788,
					-1.5716599004499585
				],
				[
					-355.19513750160843,
					-77.01133512203023
				]
			]
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 1349324569,
			"isDeleted": false,
			"id": "JoA44PJN",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 29.35354660025496,
			"y": 2229.4930503679743,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 409.2327880859375,
			"height": 80,
			"seed": 572258425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mJ71SuAIei47JfBMHRHCc",
					"type": "arrow"
				}
			],
			"updated": 1708785064933,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Think of this as slightly transforming w\nto be in the shape of the covariance matrix\ni.e the more we do it, the more w will head towards\nthe stretchy side of the distribution",
			"rawText": "Think of this as slightly transforming w\nto be in the shape of the covariance matrix\ni.e the more we do it, the more w will head towards\nthe stretchy side of the distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Think of this as slightly transforming w\nto be in the shape of the covariance matrix\ni.e the more we do it, the more w will head towards\nthe stretchy side of the distribution",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 216,
			"versionNonce": 1611236695,
			"isDeleted": false,
			"id": "Is5ot_pXU_p8C0bq2F-vK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 557.8637621759922,
			"y": 2884.793733204759,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 274.9015715073269,
			"height": 117.59678336702316,
			"seed": 1846355577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785176215,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5bd1518ab8f143e85fc852b01baa876f883f8e42",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 46,
			"versionNonce": 2074954713,
			"isDeleted": false,
			"id": "I6XPBLY7OFMybcYcotSOR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 693.8623103971446,
			"y": 2917.8763740330596,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 87.42167382144191,
			"height": 17.987998728691764,
			"seed": 1204509591,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785183211,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					87.42167382144191,
					17.987998728691764
				]
			]
		},
		{
			"type": "line",
			"version": 54,
			"versionNonce": 816074199,
			"isDeleted": false,
			"id": "4Ml2yH4Q4TzHh8bB8-Dwb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 694.9415903208661,
			"y": 2984.431969329219,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 84.54359402485113,
			"height": 12.95135908465818,
			"seed": 128477369,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785186409,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					84.54359402485113,
					12.95135908465818
				]
			]
		},
		{
			"type": "image",
			"version": 365,
			"versionNonce": 1517661977,
			"isDeleted": false,
			"id": "lgeoGmvcg2krCzKCnWT6J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 554.1277469076564,
			"y": 3026.5023376629583,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 268.67133419674656,
			"height": 75.22797357508904,
			"seed": 409348953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785582215,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2fb11fc8e8d8c4c0cf01a843123c244cf00d3a66",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 46,
			"versionNonce": 108981369,
			"isDeleted": false,
			"id": "_SGnhjZ70pTkI0Rp_ijVb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 810.5788664932807,
			"y": 3045.663896542843,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 199.40503075908157,
			"height": 0,
			"seed": 468024537,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785636748,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "gJlZrhnk",
				"focus": 0.1175106924974898,
				"gap": 5.36573136298
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
					199.40503075908157,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 1421669721,
			"isDeleted": false,
			"id": "gJlZrhnk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1015.3496286153422,
			"y": 3019.1892173177675,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 341.88873291015625,
			"height": 60,
			"seed": 1458637335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_SGnhjZ70pTkI0Rp_ijVb",
					"type": "arrow"
				}
			],
			"updated": 1708785636748,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "From the definition of the eigenvector\nproblem the matrix will only scale the\neigenvector k with its respective eigenvalue",
			"rawText": "From the definition of the eigenvector\nproblem the matrix will only scale the\neigenvector k with its respective eigenvalue",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "From the definition of the eigenvector\nproblem the matrix will only scale the\neigenvector k with its respective eigenvalue",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 391,
			"versionNonce": 229208183,
			"isDeleted": false,
			"id": "L-e9EMF9TaR7_veAtJcmY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 541.3554645534823,
			"y": 3130.034069657178,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 288.3455788597313,
			"height": 70.09505784435457,
			"seed": 1214441207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785639987,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4557bc83f17f87b1afb5b4474e04fa5f367add50",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 422,
			"versionNonce": 8762455,
			"isDeleted": false,
			"id": "Bm3OyI9oGrrx82mR78Ftq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 541.4104937775663,
			"y": 3227.5787997888365,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 293.8684308849839,
			"height": 68.77771786669837,
			"seed": 1745991897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785662227,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "01a0e243793e059291cee04e4f2be77333c8acc2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 470,
			"versionNonce": 652295289,
			"isDeleted": false,
			"id": "XDlJL5dphX5joejE8sBeT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 540.544095606234,
			"y": 3318.918456753977,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 304.6138839851208,
			"height": 66.3515390858679,
			"seed": 436874809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_2Gbfjw91jTDVqC0nfH8C",
					"type": "arrow"
				}
			],
			"updated": 1708785857184,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "548cc7046129ed759a87b14992346c7d00685543",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 28,
			"versionNonce": 2019923865,
			"isDeleted": false,
			"id": "_2Gbfjw91jTDVqC0nfH8C",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 856.1696575851325,
			"y": 3351.720896341438,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 91.65938057755523,
			"height": 0.7105378339342678,
			"seed": 125615127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785857184,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XDlJL5dphX5joejE8sBeT",
				"focus": -0.04771639907237942,
				"gap": 11.01167799377771
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
					91.65938057755523,
					0.7105378339342678
				]
			]
		},
		{
			"type": "image",
			"version": 530,
			"versionNonce": 1413420057,
			"isDeleted": false,
			"id": "qzCKF0052rvRIT5x-IPbr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 969.2112116543708,
			"y": 3320.812268164784,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 319.6099483232469,
			"height": 63.23833202117719,
			"seed": 587498265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8ScI7FmJP55w_sVOos-Vp",
					"type": "arrow"
				}
			],
			"updated": 1708785889778,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "311b570fb50553bfa919820491d3710b2931976e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 512879897,
			"isDeleted": false,
			"id": "8ScI7FmJP55w_sVOos-Vp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1104.1473616282858,
			"y": 3390.0899393739032,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 2.1316135018034856,
			"height": 123.63358310460944,
			"seed": 77757079,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708785905125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qzCKF0052rvRIT5x-IPbr",
				"focus": 0.15913992966877955,
				"gap": 6.0393391879422325
			},
			"endBinding": {
				"elementId": "xpOVCtnQW5LRSuA93Zwgb",
				"focus": -0.2523471856437758,
				"gap": 11.72364185941774
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
					2.1316135018034856,
					123.63358310460944
				]
			]
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 1150115319,
			"isDeleted": false,
			"id": "AQ3gKlmk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1118.0339865771534,
			"y": 3418.5114527312844,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 191.07240295410156,
			"height": 40,
			"seed": 412709047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785901158,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "if we iterate recursively\nover this ",
			"rawText": "if we iterate recursively\nover this ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if we iterate recursively\nover this ",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 564,
			"versionNonce": 1072095737,
			"isDeleted": false,
			"id": "xpOVCtnQW5LRSuA93Zwgb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 996.0870247872456,
			"y": 3523.6925188799546,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 302.80628942209336,
			"height": 66.7476229371281,
			"seed": 1576594775,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8ScI7FmJP55w_sVOos-Vp",
					"type": "arrow"
				}
			],
			"updated": 1708785905125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "553e345046cb66721228bfab93bdcef0849b5d61",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 979649879,
			"isDeleted": false,
			"id": "8QQPRG6P",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 981.6668471669996,
			"y": 3593.4116870945973,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 322.752685546875,
			"height": 40,
			"seed": 2019078681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708785984496,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Exponential convergence with t timesteps\nfrom the start of the algorithm",
			"rawText": "Exponential convergence with t timesteps\nfrom the start of the algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Exponential convergence with t timesteps\nfrom the start of the algorithm",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 43,
			"versionNonce": 1731278551,
			"isDeleted": false,
			"id": "MYo3pevYjmiOv52HYTzOI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1231.6934391825323,
			"y": 1377.701949710856,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 0.933419535915391,
			"height": 107.3432466302545,
			"seed": 1517689751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708786409607,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oDBdCqop",
				"focus": 0.021506071473265314,
				"gap": 24.114740441877757
			},
			"endBinding": {
				"elementId": "MnbFacEY",
				"focus": 0.02137838454132946,
				"gap": 15.59885723564446
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
					-0.933419535915391,
					-107.3432466302545
				]
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 1717630457,
			"isDeleted": false,
			"id": "b91ibhDz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1031.083168437623,
			"y": 1149.832874870076,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 401.6488037109375,
			"height": 60,
			"seed": 97852247,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4dFC1WyJtCd46v2URwoz6",
					"type": "arrow"
				}
			],
			"updated": 1708787632666,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The covariance matrix is a positive semi-definite\nfor a positive semi-definite matrix, the eigenvalues\nof that matrix are all non-negative",
			"rawText": "The covariance matrix is a positive semi-definite\nfor a positive semi-definite matrix, the eigenvalues\nof that matrix are all non-negative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The covariance matrix is a positive semi-definite\nfor a positive semi-definite matrix, the eigenvalues\nof that matrix are all non-negative",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 193,
			"versionNonce": 1001538551,
			"isDeleted": false,
			"id": "MnbFacEY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1132.4435698735556,
			"y": 1221.5200384955347,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 200.36217207846394,
			"height": 33.23980734942259,
			"seed": 92527,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MYo3pevYjmiOv52HYTzOI",
					"type": "arrow"
				}
			],
			"updated": 1708786409607,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "680b1a394b55b2e3bfa1eaad4e665d9d9e3a1aec",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 366,
			"versionNonce": 786783351,
			"isDeleted": false,
			"id": "4dFC1WyJtCd46v2URwoz6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1230.0553006991402,
			"y": 1138.688888815222,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 2.1622875095986274,
			"height": 64.8374868030744,
			"seed": 1882798135,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708788276303,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "b91ibhDz",
				"focus": -0.01597621808979764,
				"gap": 11.14398605485394
			},
			"endBinding": {
				"elementId": "M1POFb35",
				"focus": -0.01383585845325027,
				"gap": 7.395897721464564
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
					2.1622875095986274,
					-64.8374868030744
				]
			]
		},
		{
			"type": "text",
			"version": 404,
			"versionNonce": 261373495,
			"isDeleted": false,
			"id": "M1POFb35",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 997.0409014881718,
			"y": 966.455504290683,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 467.6649169921875,
			"height": 100,
			"seed": 2105509079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4dFC1WyJtCd46v2URwoz6",
					"type": "arrow"
				},
				{
					"id": "uNkbidLmJq3een2FffVOP",
					"type": "arrow"
				}
			],
			"updated": 1708788276301,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Since the covariance is also a Gramian matrix\nis has wonderful properties like being symmetrical and\nits eigenvectors are all orthogonal\nand its diagonizable and\nThe trace of a Gram matrix is the sum of its eigenvalues",
			"rawText": "Since the covariance is also a Gramian matrix\nis has wonderful properties like being symmetrical and\nits eigenvectors are all orthogonal\nand its diagonizable and\nThe trace of a Gram matrix is the sum of its eigenvalues",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since the covariance is also a Gramian matrix\nis has wonderful properties like being symmetrical and\nits eigenvectors are all orthogonal\nand its diagonizable and\nThe trace of a Gram matrix is the sum of its eigenvalues",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 665,
			"versionNonce": 1119087287,
			"isDeleted": false,
			"id": "uNkbidLmJq3een2FffVOP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1472.4221975902756,
			"y": 1020.4217170547442,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 57.8268587469322,
			"height": 3.3969131419602263,
			"seed": 2135701815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708788276304,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "M1POFb35",
				"focus": -0.16416857072172636,
				"gap": 7.716379109916261
			},
			"endBinding": {
				"elementId": "UUEz70NB",
				"focus": 0.18967169516131885,
				"gap": 3.9396656785763753
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
					57.8268587469322,
					3.3969131419602263
				]
			]
		},
		{
			"type": "text",
			"version": 300,
			"versionNonce": 286626615,
			"isDeleted": false,
			"id": "UUEz70NB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1534.1887220157842,
			"y": 994.6006053308394,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 316.7207336425781,
			"height": 100,
			"seed": 2008773273,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uNkbidLmJq3een2FffVOP",
					"type": "arrow"
				}
			],
			"updated": 1708788141624,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A Gram matrix (in very simple terms)\nis a matrix that can be written as X X\nsuch that each entry of it is a dot\nproduct between the columns and rows\nof X",
			"rawText": "A Gram matrix (in very simple terms)\nis a matrix that can be written as X X\nsuch that each entry of it is a dot\nproduct between the columns and rows\nof X",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A Gram matrix (in very simple terms)\nis a matrix that can be written as X X\nsuch that each entry of it is a dot\nproduct between the columns and rows\nof X",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 882326455,
			"isDeleted": false,
			"id": "ilaf71Lw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1832.645637578185,
			"y": 1010.5728504426991,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 12.864057268415177,
			"height": 20,
			"seed": 153641047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708788038814,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "T",
			"rawText": "T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 3,
			"versionNonce": 1143800769,
			"isDeleted": true,
			"id": "rSY1qw1P",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -968.3785976269911,
			"y": 4038.271920393243,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 139,
			"height": 17,
			"seed": 15988,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709246063468,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bc5734f2b86dc37f31401b0afc8b1045b1c475a5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 56,
			"versionNonce": 1274699873,
			"isDeleted": true,
			"id": "QDyyMA6O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -819.7596366219421,
			"y": 4025.3377405809674,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 243,
			"height": 41,
			"seed": 40794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709246061957,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "85b52c1fecb5f6a496a4a9a23b8d714115db3bf7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "pYPgxvd7",
			"type": "text",
			"x": -729.1644061560986,
			"y": 4081.782681057158,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1514960961,
			"version": 2,
			"versionNonce": 63112815,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1709243178446,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "PM3Iag_eEREJhYeghPOoL",
			"type": "line",
			"x": -685.1506622386034,
			"y": 4054.6882555792904,
			"width": 83.57177966525012,
			"height": 5.548333919684865,
			"angle": 0,
			"strokeColor": "#e03131",
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
			"seed": 1137715087,
			"version": 36,
			"versionNonce": 1037335585,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1709246062847,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					83.57177966525012,
					5.548333919684865
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#b2f2bb",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 988.1623788626606,
		"scrollY": -3806.7801955817376,
		"zoom": {
			"value": 2.0665675629866977
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