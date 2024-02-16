---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Idea ^cQFRTTGj

Given an N dimensional space with features X1...Xn
and a target Y

Partition space into a set of rectangles each of
which represent a simple decision model inside of them
different rectangles lead to different predictions  ^8hqVQH9o

Problem!
Describing rectangles in space with different heights and width is not easy ^sDM2Xx2H

Recursive Binary splitting ^TbectVVc

We start with our space, We split our space into 2 parts according to the mean
We recursive go to each half
recalculate the mean in each one and split in half again using a different dimension ^wYzcSKty

Divide and conquer! ^sFQWJVIi

X1>t ^hrYuHzDj

yes ^mNvnm7ps

No ^yUVnRPdz

X2>t3 ^Sx12qaSb

yes ^Cpguv1B8

No ^rM6UBj9T

X2>t2 ^vJFzlbTM

yes ^dUluLXl6

No ^uKq3mIlC

X1>t4 ^37JLJ7ox

yes ^2m6eY7tD

No ^id5wt6yT

R1 ^bkUIyli5

R2 ^UFrm0c1V

R3 ^ZoP8890j

R4 ^6d09SLWN

R5 ^yoIO4wex

x ^KcRCK2lT

z ^oCzBy6ct

y ^XTwvgc3N

How do we find the most optimal binary
partition? ^LrWSgTy9

CANT!!!! VERY BAD!!! BAD DOG!!!
NP DIFFICULTY!!!
ABORT ABORT! ^MX9MzVUn

WARNING! ^NbdxxyjJ

ಠ_ಠ ^tZTuJb55

Oh okay I guess ^ZfPef9xN

Greedy Algorithm ^STc1R3xG

Given N datapoints (xi,yi)
such that xi has P features 
We consider the two half planes splitting up feature j by value s ^OrZd6P3k

We seek such j and s values as they define our paritions ^qa3ajZVF

Error measurement 
between decision of 
R1 half and y label ^nBgrLBn6

for every x
in R1 half ^xFBXXuTv

Error measurement 
between decision of 
R2 half and y label ^UiU9G3OH

for every x
in R2 half ^C43ebJ4n

Minimize partitions
such that the
error is minimal ^ogiSJH0C

mean of y value in each half ^FJ4Hsk2Y

Scan through all features P
and determine optimal j and s for
each feature ^XJjw2crD

Rgression Surface ^FiC8m2Gy

Decision tree ^AU3cjKER

How do we decide where to split the tree? ^ctJMz5RS

We base the following on the concept of entropy from information theory ^VuqVN3ef

%%***>>>text element-link:[[entropy]]<<<***%%wtf is that
shit? ^DSAMbCnV

weighted sum of entropy (Children) ^OqG6nZWr

Entropy (parent) ^lWklG8Y2

information gain ^tYn30RwH

probability of each class
present in the child node ^IwrvfqbH

Choose the split that results in the purest daughter node!  ^38xNvpBb

Gini Impurity ^Zj4BxxE0

Choose a random element from the set
given a distribution of labels in the subset we randomly
label our element according to them
This impurity measures how often this is wrong ^LtOdaowr

Information Gain ^SLDciDeV

Variance reduction (Regression) ^3QrLcI45

The definition of variance reduction at a node is
the total reduction of the variance of the target variable
due to the split at this node ^dO2559FY

s = set of pre-split sample indices
st = set of pre-split sample indices for which the
split test is true (indices go to the right)
sf = set of pre-split sample indices for which the
split test is false (indices go to the left) ^yFgNiMlg

%%***>>>text element-link:[[Gini impurity]]<<<***%%who is Gini
and why is she impure? ^xoHkiCyC

How deep is the tree? ^l8kPLBYr

too deep = overfitting
too shallow = does not capture all
     the details

We need to split large enough to avoid
both ^z8thcB50

Idea ^Lwjt68H8

Grow tree large then prune it according to the cost complexity critereon ^mwzUR1kS

regularization
parameter ^AZIi1MtD

Number of
Terminal leaves ^quWojizW

num of training data
in current region
m ^c8m1mNG1

Squared loss ^SjkOcNFG

Prediction in
region m ^dk8DOG29

actual
label ^KF50kMLo

Weakest Link pruning ^JgAVlrMi

Find the node with the lowest node contribution to the cost function
this node adds complexity and barely changes the cost
thus we prune it in return for lower complexity
we calculate the cost for the new tree and repeat the pruning!

Finally we can find the minimally complex tree with the best score! ^SxNkW2lV

Why trees? ^dcYIyU2O

Interpretability

Generalizes to higher dimensions

can handle qualitive and quantitive predictors

ignored redundant variables

Handles missing data ^0OK9lzcX

Prone to overtfitting
high variance! ^uzFC6xRD

Information gain is the expected reduction of entropy caused by a certain split ^nNI2f8ft

how often this
value occurs in
dataset ^XaCGwP3Y

How this value splits
our datapoints classes
given each value of it
going in a seperate node ^Ba8U18rI


# Embedded files
602fc71879689f2a4016156dc09706da613b2064: $$\mathcal{\hat{f}}(X) = \sum_{p}^P c_p I\{(X1...Xn) \in R_p\}$$
317892ff9debf82d6b858e9fa88e1fa57b408ef8: [[Pasted Image 20240113133029_358.png]]
de669187b9fc85cb113907cc38e433711f9f5ba2: [[Pasted Image 20240113155118_344.png]]
2106759a162a3aa2b2bf8d996460342e1630d855: [[Pasted Image 20240113155216_373.png]]
ac728d66f270bb07e3b8a43ca335f2e6440476fc: [[Pasted Image 20240113155700_470.png]]
df75d4a28c64c65ed4986db4727836b7a0aa3b2e: [[Pasted Image 20240113160436_575.png]]
bc2628c17514f27fea7b8db947f215f47a8c34c9: [[Pasted Image 20240113160536_584.png]]
3f819d3f04892e93a38d6d7dde606d21ab4d69e6: [[Pasted Image 20240113162857_713.png]]
e0d46e13a9c2b7057e19acac310ca98b0a1e5394: [[Pasted Image 20240113170437_870.png]]
d09e0e0bce2f63d54aee2c3496e2e5b56fe2688e: [[Pasted Image 20240113174012_081.png]]
fdd2b621bcbbaa9d10a449ef745b081d21299d93: [[Pasted Image 20240113174622_124.png]]
39d3974d96d121eda383867ac6d42f9c96dfab0c: [[Pasted Image 20240114173402_702.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.14",
	"elements": [
		{
			"type": "text",
			"version": 169,
			"versionNonce": 1203819290,
			"isDeleted": false,
			"id": "cQFRTTGj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 395.3777709078222,
			"y": 152.7220439160448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 65.18428039550781,
			"height": 35,
			"seed": 1092782359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Idea",
			"rawText": "Idea",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 83,
			"versionNonce": 800916358,
			"isDeleted": false,
			"id": "6VCpt38hxWOqWHupvDJ0a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 343.80633160992784,
			"y": 145.5249371066122,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 40.397558742642104,
			"height": 45.5274074718665,
			"seed": 444781911,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "317892ff9debf82d6b858e9fa88e1fa57b408ef8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 349,
			"versionNonce": 2032885722,
			"isDeleted": false,
			"id": "8hqVQH9o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 157.5855539827595,
			"y": 195.54866064545513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 525.6194458007812,
			"height": 150,
			"seed": 1988801783,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given an N dimensional space with features X1...Xn\nand a target Y\n\nPartition space into a set of rectangles each of\nwhich represent a simple decision model inside of them\ndifferent rectangles lead to different predictions ",
			"rawText": "Given an N dimensional space with features X1...Xn\nand a target Y\n\nPartition space into a set of rectangles each of\nwhich represent a simple decision model inside of them\ndifferent rectangles lead to different predictions ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given an N dimensional space with features X1...Xn\nand a target Y\n\nPartition space into a set of rectangles each of\nwhich represent a simple decision model inside of them\ndifferent rectangles lead to different predictions ",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 252,
			"versionNonce": 161391302,
			"isDeleted": false,
			"id": "sDM2Xx2H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 186.85531967501913,
			"y": 348.7062469116574,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 474.4477233886719,
			"height": 32.08990678051585,
			"seed": 1062951831,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pf-0Kw9fSk2bxDL0qc--v",
					"type": "arrow"
				}
			],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"fontSize": 12.835962712206339,
			"fontFamily": 1,
			"text": "Problem!\nDescribing rectangles in space with different heights and width is not easy",
			"rawText": "Problem!\nDescribing rectangles in space with different heights and width is not easy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem!\nDescribing rectangles in space with different heights and width is not easy",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "arrow",
			"version": 453,
			"versionNonce": 1596347546,
			"isDeleted": false,
			"id": "pf-0Kw9fSk2bxDL0qc--v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 416.5118274325532,
			"y": 389.32236348985174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 547.609649394547,
			"height": 169.2484484718779,
			"seed": 1338834489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sDM2Xx2H",
				"focus": 0.1003741828321861,
				"gap": 8.52620979767849
			},
			"endBinding": {
				"elementId": "TbectVVc",
				"focus": 0.07867053672060614,
				"gap": 7.371010194655469
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
					55.949900321281916,
					79.7286079578268
				],
				[
					492.359122827281,
					90.2192142680671
				],
				[
					547.609649394547,
					169.2484484718779
				]
			]
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1284135430,
			"isDeleted": false,
			"id": "TbectVVc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 793.726656170396,
			"y": 565.9418221563851,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 346.389404296875,
			"height": 35,
			"seed": 89333721,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pf-0Kw9fSk2bxDL0qc--v",
					"type": "arrow"
				}
			],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Recursive Binary splitting",
			"rawText": "Recursive Binary splitting",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recursive Binary splitting",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 289,
			"versionNonce": 1533325658,
			"isDeleted": false,
			"id": "d1Z1TUNagWdtAuY1MLq0c",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 705.3364421030175,
			"y": 186.37129859143977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 228.8684585866048,
			"height": 195.9453856576732,
			"seed": 1368728727,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.5930519159160212,
					192.75928182584113
				],
				[
					228.8684585866048,
					189.5731779940091
				],
				[
					221.96523361763525,
					-3.186103831832071
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 391,
			"versionNonce": 2138908998,
			"isDeleted": false,
			"id": "8symGhgJqiw3vVbd7zOQu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 705.7635043799613,
			"y": 224.80494577256775,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 131.877296824645,
			"height": 45.24909507301588,
			"seed": 177455065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					131.877296824645,
					-1.1907656598161793
				],
				[
					131.2819139947369,
					44.0583294131997
				],
				[
					2.0838399046783707,
					42.86756375338348
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 287,
			"versionNonce": 557413914,
			"isDeleted": false,
			"id": "CSsRkKqjh7t6Zq6Ci9V9M",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 756.9664277520583,
			"y": 266.7794352810891,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 53.286763276775325,
			"height": 112.52735485263167,
			"seed": 65432663,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.3815313196323515,
					112.52735485263167
				],
				[
					-50.90523195714297,
					111.93197202272358
				],
				[
					-50.60754054218887,
					1.4884570747702845
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 332,
			"versionNonce": 1104416902,
			"isDeleted": false,
			"id": "cavkG761B_IBNQaChKL8J",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 757.2641191670123,
			"y": 315.8985187485077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 176.53100906775288,
			"height": 63.705962800167065,
			"seed": 96576151,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					175.34024340793667,
					-1.4884570747702242
				],
				[
					176.53100906775288,
					60.431357235672635
				],
				[
					2.083839904678374,
					62.21750572539684
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 346,
			"versionNonce": 26714842,
			"isDeleted": false,
			"id": "iXRHE3iOtmQEQhD5z6uIg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 755.775662092242,
			"y": 267.37481811099724,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 127.41192560033426,
			"height": 48.82139205246449,
			"seed": 1141224089,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					127.41192560033426,
					0.8930742448621416
				],
				[
					127.41192560033426,
					46.73755214778612
				],
				[
					2.6792227345864603,
					48.82139205246449
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 304,
			"versionNonce": 1061949382,
			"isDeleted": false,
			"id": "UKTnY-I2mrHoVJLBboQJr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 883.4852791075303,
			"y": 309.9446904494266,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#eebefa",
			"width": 53.584454691729434,
			"height": 128.30499984519636,
			"seed": 1867102967,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.656136884127022,
					-125.32808569565589
				],
				[
					45.24909507301583,
					-126.51885135547204
				],
				[
					47.92831780760241,
					1.488457074770281
				],
				[
					2.083839904678371,
					1.7861484897243265
				]
			]
		},
		{
			"type": "line",
			"version": 242,
			"versionNonce": 923940762,
			"isDeleted": false,
			"id": "uxsHRwKczrgffhSTR9pQE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 838.2361840345144,
			"y": 266.184052451181,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 47.9283178076023,
			"height": 85.13974467685887,
			"seed": 527498039,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.8699883944026396,
					-78.88822496282378
				],
				[
					39.89064960384292,
					-79.78129920768595
				],
				[
					44.05832941319966,
					5.358445469172917
				],
				[
					2.3815313196324723,
					3.5722969794485957
				]
			]
		},
		{
			"type": "line",
			"version": 254,
			"versionNonce": 604120838,
			"isDeleted": false,
			"id": "ftJJkzH0dW8OMW4DZjD1N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 834.9615784700198,
			"y": 221.82803162302724,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 132.1749882395991,
			"height": 37.8068096991646,
			"seed": 720087353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-128.90038267510454,
					2.0838399046783707
				],
				[
					-129.79345691996662,
					-34.82989554962408
				],
				[
					-1.1907656598161793,
					-35.72296979448623
				],
				[
					2.3815313196324728,
					2.083839904678371
				]
			]
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 836514906,
			"isDeleted": false,
			"id": "wYzcSKty",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 551.4882420138347,
			"y": 602.9540557173372,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 826.1390991210938,
			"height": 75,
			"seed": 1709273849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We start with our space, We split our space into 2 parts according to the mean\nWe recursive go to each half\nrecalculate the mean in each one and split in half again using a different dimension",
			"rawText": "We start with our space, We split our space into 2 parts according to the mean\nWe recursive go to each half\nrecalculate the mean in each one and split in half again using a different dimension",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We start with our space, We split our space into 2 parts according to the mean\nWe recursive go to each half\nrecalculate the mean in each one and split in half again using a different dimension",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 275994182,
			"isDeleted": false,
			"id": "sFQWJVIi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 873.226617810497,
			"y": 683.6628618724363,
			"strokeColor": "#1971c2",
			"backgroundColor": "#96f2d7",
			"width": 189.39979553222656,
			"height": 25,
			"seed": 1890214199,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Divide and conquer!",
			"rawText": "Divide and conquer!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Divide and conquer!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 314,
			"versionNonce": 1674090778,
			"isDeleted": false,
			"id": "IUVKjl478TeiCTIKklRjG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1390.7799604985053,
			"y": 531.2319957057017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 290.18456586868706,
			"height": 265.2607381253641,
			"seed": 62261273,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7802734102372142,
					264.3706014202454
				],
				[
					290.18456586868706,
					265.2607381253641
				],
				[
					288.4042924584496,
					0.8901367051186071
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 4193,
			"versionNonce": 226270598,
			"isDeleted": false,
			"id": "yo-1i_--P693fwoJ9nJV0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -17.621760676696184,
			"y": -48.69578890463629,
			"strokeColor": "#000000",
			"backgroundColor": "#deb072",
			"width": 126.0069051220011,
			"height": 153.37469580364106,
			"seed": 917908441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.99668963516609,
					-3.9013942245901614
				],
				[
					26.349593909341372,
					-11.09602023818454
				],
				[
					36.23198974027602,
					-19.650185512472518
				],
				[
					42.07640945043719,
					-27.77893471017809
				],
				[
					49.46446821945845,
					-45.77694945461754
				],
				[
					55.495104480979165,
					-71.91240491366148
				],
				[
					59.47815406359372,
					-107.91698480255974
				],
				[
					54.88284324148288,
					-104.55634404596101
				],
				[
					54.95273458327658,
					-109.91830759538962
				],
				[
					56.929685849569616,
					-113.71354664734626
				],
				[
					51.95682323065467,
					-117.22612538238366
				],
				[
					47.254571471467564,
					-110.53219488620236
				],
				[
					43.20758311361438,
					-113.05471042319842
				],
				[
					43.22537025483999,
					-115.64013201645095
				],
				[
					41.52468093785979,
					-125.86826420225721
				],
				[
					39.0769316894052,
					-127.5715385238944
				],
				[
					38.965192778424395,
					-130.72247959749754
				],
				[
					35.475282545763946,
					-131.01192314624012
				],
				[
					32.37293699395129,
					-130.24851289994996
				],
				[
					27.04816736388677,
					-121.71247473027918
				],
				[
					23.82442922365212,
					-120.372993309691
				],
				[
					20.35231254662084,
					-122.20843000342046
				],
				[
					19.97358691395512,
					-129.69625840627606
				],
				[
					22.802698114961434,
					-133.8421055526502
				],
				[
					18.01070243479072,
					-134.32997867723606
				],
				[
					15.247608275794427,
					-127.76750817595115
				],
				[
					13.207603421961757,
					-142.1336972149406
				],
				[
					7.651745921486372,
					-142.76532610471324
				],
				[
					6.5274574791500335,
					-137.69064509144923
				],
				[
					6.466044696055201,
					-143.35484186898918
				],
				[
					1.407127721116435,
					-144.75844551675937
				],
				[
					-0.7915758925655455,
					-134.77180921267032
				],
				[
					-1.323625014850887,
					-143.06871200115432
				],
				[
					0.6638843597931791,
					-151.91596420543843
				],
				[
					-4.22133826252415,
					-152.25397120395345
				],
				[
					-4.692232460739942,
					-149.6413140529498
				],
				[
					-5.142061757482687,
					-153.20654221286262
				],
				[
					-8.117831882752116,
					-153.37469580364106
				],
				[
					-8.079095299318544,
					-151.16349372451438
				],
				[
					-10.25124328203271,
					-143.09896874300833
				],
				[
					-12.262319175559783,
					-136.10018730060017
				],
				[
					-14.181694755000732,
					-127.83102039334929
				],
				[
					-12.329901332051932,
					-137.4725746117355
				],
				[
					-14.512184072478457,
					-137.97086472779282
				],
				[
					-18.778763123702163,
					-131.1089602441343
				],
				[
					-19.031798517523594,
					-124.34930135410573
				],
				[
					-20.804123894080874,
					-140.34823193257714
				],
				[
					-22.18538232541632,
					-142.2724728371604
				],
				[
					-21.869851397169796,
					-145.36064255698298
				],
				[
					-25.511282672033897,
					-145.79447433110883
				],
				[
					-25.195084645811324,
					-141.52584908513177
				],
				[
					-28.425500180209635,
					-142.29304062235326
				],
				[
					-31.35086592186907,
					-135.09286935683338
				],
				[
					-33.61607407223581,
					-143.4097882917993
				],
				[
					-45.64698080856175,
					-139.2853748751061
				],
				[
					-42.68013632592321,
					-137.81939500081808
				],
				[
					-45.61530648350877,
					-135.5377339051778
				],
				[
					-45.54865120833909,
					-132.48194409480587
				],
				[
					-47.1606485665287,
					-116.08508636644595
				],
				[
					-48.49862580946906,
					-124.34377855259285
				],
				[
					-55.50188450560075,
					-122.71534107793688
				],
				[
					-55.714284652518394,
					-119.90414530622847
				],
				[
					-57.57956115186681,
					-105.54165417092328
				],
				[
					-60.869977017683894,
					-91.54702908296295
				],
				[
					-64.199770907296,
					-79.67136374293757
				],
				[
					-66.12681811346103,
					-71.79514640836963
				],
				[
					-66.52875105840738,
					-60.03485053177136
				],
				[
					-65.02261701748675,
					-47.21098239169894
				],
				[
					-63.12657062399514,
					-39.680645736083896
				],
				[
					-58.20286799438888,
					-26.841472828985072
				],
				[
					-52.605261706542144,
					-17.6792220919545
				],
				[
					-43.35243317605812,
					-9.855881893590315
				],
				[
					-27.722346841482885,
					-3.3633700853371065
				],
				[
					-23.86680745471673,
					-2.419077817786093
				],
				[
					-19.32068297297808,
					-2.131388348388974
				],
				[
					-10.702353205789226,
					-0.947025410259106
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1071,
			"versionNonce": 206202330,
			"isDeleted": false,
			"id": "3YhnDXayfr90n84HpZHe3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -36.506377558402164,
			"y": -172.9779518257904,
			"strokeColor": "#8b9743",
			"backgroundColor": "#8b9743",
			"width": 6.61157018759358,
			"height": 27.399588331842256,
			"seed": 781535417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.02390181725382693,
					-4.628123564361965
				],
				[
					0.6305583384859077,
					-7.715113895934063
				],
				[
					3.798452680844639,
					-13.29984396574062
				],
				[
					5.9716026796050965,
					-14.419326053614826
				],
				[
					6.587668370339753,
					-12.167786762833828
				],
				[
					4.7500789469793965,
					-4.082666386310723
				],
				[
					1.3355604198895423,
					12.980262278227428
				],
				[
					1.322253980446384,
					9.536156490476804
				],
				[
					2.316057358923094,
					5.208281398304045
				],
				[
					3.231808524824648,
					-0.6826392393034154
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1966,
			"versionNonce": 5962950,
			"isDeleted": false,
			"id": "RxynmZqCdx7tHn7pYzFfS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 9.024189820267608,
			"y": -170.1049788990225,
			"strokeColor": "#969a55",
			"backgroundColor": "#969a55",
			"width": 21.572225509429128,
			"height": 45.59381389801159,
			"seed": 440256921,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7831541394192365,
					-2.348424624284022
				],
				[
					3.6212043277542945,
					-5.600163885506534
				],
				[
					5.671729969771488,
					-8.948732151373413
				],
				[
					7.555458375811067,
					-9.805523868624578
				],
				[
					9.378258694418207,
					-9.38399808618298
				],
				[
					12.094145925050759,
					-9.412431929502969
				],
				[
					12.39792200050039,
					-6.142773115437455
				],
				[
					14.381635214459287,
					-5.44627363751033
				],
				[
					15.176303515998962,
					-2.8228719022791346
				],
				[
					16.415380193490897,
					6.134481374161264
				],
				[
					16.134326684677337,
					8.215866711972264
				],
				[
					19.907575953132916,
					10.996694739322539
				],
				[
					21.572225509429128,
					9.670076487261593
				],
				[
					18.759709286919318,
					14.766308247255441
				],
				[
					13.39254686336043,
					19.98347808935787
				],
				[
					11.411867912223475,
					21.20430037380765
				],
				[
					10.106939051224792,
					24.471407213229334
				],
				[
					7.365938847310105,
					31.905166775323703
				],
				[
					4.978917506912936,
					35.788290029387014
				],
				[
					6.360555304405056,
					30.234963286040912
				],
				[
					10.466226291905581,
					20.21582611517594
				],
				[
					12.741213658755452,
					16.609233299034003
				],
				[
					12.681807117842897,
					13.037756593656349
				],
				[
					12.446088781096432,
					8.653600607818467
				],
				[
					12.298476859724655,
					3.258040703110721
				],
				[
					7.97374665801017,
					4.381787861416229
				],
				[
					3.50415906310523,
					1.1963643284916268
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2378,
			"versionNonce": 74750618,
			"isDeleted": false,
			"id": "CjpmXiYeOcMV-QAwieRTO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -54.37925823888932,
			"y": -38.82068862268285,
			"strokeColor": "#deb072",
			"backgroundColor": "#deb072",
			"width": 121.39397444631054,
			"height": 58.230993614785156,
			"seed": 48443001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.710303859301161,
					1.4335268406361295
				],
				[
					-0.9460485867368226,
					3.562720384675348
				],
				[
					-2.1761038737117877,
					5.284047147271616
				],
				[
					-3.282753219257919,
					9.224942808782657
				],
				[
					-3.7553649381858896,
					12.27932837791505
				],
				[
					-3.330833536150058,
					16.702197195566296
				],
				[
					-4.173026513949483,
					18.555879532091815
				],
				[
					-4.65714259404975,
					21.271416019802597
				],
				[
					-4.43349876732262,
					23.465556170176413
				],
				[
					-4.086585241099585,
					25.793539779542087
				],
				[
					0.8128840282237582,
					31.15733079256071
				],
				[
					3.25720285362484,
					31.604159687868215
				],
				[
					17.076894839337584,
					31.763108609458524
				],
				[
					25.274805932857628,
					31.0355243468174
				],
				[
					40.96111708088354,
					29.835610085855215
				],
				[
					41.241267441668086,
					26.341184626201777
				],
				[
					40.82550016758015,
					22.14945909940865
				],
				[
					40.24271567845826,
					19.83588480632467
				],
				[
					37.72464917180988,
					14.293443672451318
				],
				[
					36.561220038612205,
					10.976563003621592
				],
				[
					36.317571739617776,
					8.748878088100533
				],
				[
					36.611421727067984,
					3.458069646265977
				],
				[
					39.82383793176907,
					3.5433093730306786
				],
				[
					46.71474090786836,
					3.4165335605185234
				],
				[
					76.6396856757562,
					3.511217855166582
				],
				[
					81.13864060963675,
					3.115542032659005
				],
				[
					83.13355502839049,
					2.4131402054597735
				],
				[
					81.1027805013604,
					1.933266868486918
				],
				[
					78.99292099612275,
					1.475183004019562
				],
				[
					81.03548776275944,
					0.870801474500632
				],
				[
					84.96694039584385,
					-0.23701323989439627
				],
				[
					84.27566884179792,
					-1.478860766476022
				],
				[
					78.57108518306228,
					-1.8178753395109088
				],
				[
					83.66613628959982,
					-4.162177191674176
				],
				[
					85.08180850948426,
					-5.682320803243156
				],
				[
					83.38975759814114,
					-6.8940834939877
				],
				[
					76.62178795021227,
					-5.892963916722535
				],
				[
					74.64039612058428,
					-6.441352321049336
				],
				[
					76.00422251207829,
					-9.71302376004519
				],
				[
					74.62872087969966,
					-11.198069294487436
				],
				[
					73.00803303091567,
					-9.867008702965602
				],
				[
					71.60422232619688,
					-7.83075524894338
				],
				[
					69.75903240348202,
					-6.881398369397829
				],
				[
					64.35030310503826,
					-6.306532846403375
				],
				[
					53.58724275602805,
					-6.603441734649759
				],
				[
					48.96018961618605,
					-6.984797529373861
				],
				[
					42.99509598738396,
					-7.95016476034352
				],
				[
					39.392141897471205,
					-9.365191947800477
				],
				[
					38.54579007694358,
					-10.21992611097262
				],
				[
					36.652487508742574,
					-9.810387479371437
				],
				[
					19.9507413740387,
					-11.44617893948436
				],
				[
					12.849914980545792,
					-12.350716071783692
				],
				[
					10.717043674049654,
					-12.247880353021149
				],
				[
					5.624534210800725,
					-14.381056471977045
				],
				[
					3.0371074749779945,
					-13.571516144069983
				],
				[
					-4.594689907840601,
					-13.146593719989834
				],
				[
					-8.164836632445725,
					-13.515700056417694
				],
				[
					-9.898640692954839,
					-14.887911869470056
				],
				[
					-13.230160826867916,
					-15.42444953482927
				],
				[
					-15.581025383658211,
					-15.51777141014941
				],
				[
					-17.500945161101914,
					-16.759663580980177
				],
				[
					-18.399259808741945,
					-18.749091375457496
				],
				[
					-20.5704866830969,
					-19.068448623748708
				],
				[
					-26.12490864004315,
					-23.99290866613387
				],
				[
					-27.420778787026194,
					-26.11400389732053
				],
				[
					-29.76715043894807,
					-25.840507069118175
				],
				[
					-29.09312926883305,
					-23.14480879233291
				],
				[
					-31.04913083634192,
					-24.4982577050817
				],
				[
					-33.93979670705108,
					-26.467885005326636
				],
				[
					-33.94755326047902,
					-23.234756178199
				],
				[
					-35.60970561026607,
					-24.545216527645692
				],
				[
					-36.31216593682629,
					-22.60892385668558
				],
				[
					-35.90827095410212,
					-19.86498823840785
				],
				[
					-32.83839844888058,
					-17.619785843189167
				],
				[
					-29.29094485796229,
					-15.983529467102093
				],
				[
					-27.852048391771547,
					-15.88376958316123
				],
				[
					-27.181653412308684,
					-13.695605604347824
				],
				[
					-22.4474509955608,
					-13.596169006349179
				],
				[
					-22.842865110400922,
					-11.522442093253291
				],
				[
					-20.9772527528791,
					-9.633280664026342
				],
				[
					-18.405276006180657,
					-9.250807223616208
				],
				[
					-18.395257220885693,
					-7.100030494291797
				],
				[
					-13.981024756262258,
					-6.9065654102707015
				],
				[
					-11.215970868673539,
					-3.7572092075130072
				],
				[
					-7.742248024976978,
					-3.19973492875298
				],
				[
					-5.903763976377858,
					-1.171408138142537
				],
				[
					0.14180014181283293,
					-0.21953886498890732
				]
			]
		},
		{
			"type": "line",
			"version": 1613,
			"versionNonce": 514552838,
			"isDeleted": false,
			"id": "sgaBl2_EhKJabv-PdBgs-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 7.446866813672472,
			"y": 48.935948073065646,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 95.7943817997795,
			"height": 68.46904763357067,
			"seed": 2135488345,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.16209811487836112,
					-5.136899835894934
				],
				[
					1.2562905101156818,
					-12.60137144297694
				],
				[
					3.203810540411322,
					-24.793307598761547
				],
				[
					6.322482422747943,
					-34.82970294167943
				],
				[
					8.991811809567526,
					-57.94220385462147
				],
				[
					7.163440856538843,
					-61.45546286316658
				],
				[
					-11.960102634696435,
					-58.63808864895343
				],
				[
					-36.755496550268305,
					-56.32931579882804
				],
				[
					-60.86434823906772,
					-56.318860878709074
				],
				[
					-80.45417114576082,
					-57.52932577384764
				],
				[
					-86.80256999021196,
					-58.68519349650862
				],
				[
					-86.24747196352662,
					-55.050750017165775
				],
				[
					-84.64274547127864,
					-40.955161658524325
				],
				[
					-81.85757349281229,
					-25.034051879707302
				],
				[
					-76.8961315800911,
					-8.48729344327446
				],
				[
					-66.90130826589187,
					2.15728106845625
				],
				[
					-58.70265629202099,
					5.840511943923849
				],
				[
					-48.7931456614554,
					6.756856911197124
				],
				[
					-32.819379764472195,
					6.937227709766032
				],
				[
					-20.703968001593903,
					7.013584770404089
				],
				[
					-7.540366830659755,
					3.277496978048429
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1081,
			"versionNonce": 184170330,
			"isDeleted": false,
			"id": "PmBe_e66dKAuyNfEoIy3l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -13.165463866409723,
			"y": -16.153287342247012,
			"strokeColor": "#000000",
			"backgroundColor": "#613407",
			"width": 28.463889136846944,
			"height": 6.987236596221095,
			"seed": 29533241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.960074557702476,
					0.0457996520546197
				],
				[
					17.152650497973475,
					-0.13527612616741208
				],
				[
					25.100576795575677,
					0.6696394302369891
				],
				[
					28.461336075699098,
					1.3417711601187312
				],
				[
					28.130284708733697,
					3.2338657408229756
				],
				[
					25.34308859148961,
					3.9977296542489262
				],
				[
					1.9265839848977135,
					6.7807889483383965
				],
				[
					-0.002553061147844793,
					6.851960470053682
				],
				[
					0.1274830712441367,
					4.9292987578803915
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 661,
			"versionNonce": 1651180358,
			"isDeleted": false,
			"id": "xea-f45uye5RnSk-AXkI_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -59.4514971727875,
			"y": -16.994408968205207,
			"strokeColor": "#000000",
			"backgroundColor": "#613407",
			"width": 26.457182701182948,
			"height": 9.936320439248869,
			"seed": 1714664729,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.0535726729414,
					2.17778752637283
				],
				[
					-18.57425012746996,
					5.081023575558978
				],
				[
					-20.219770441834562,
					6.4218263632919035
				],
				[
					-16.48014747642551,
					8.313133795392464
				],
				[
					-2.2924950233467705,
					9.439349124574896
				],
				[
					6.237412259348383,
					9.935988173141608
				],
				[
					4.854605390980186,
					8.139331680790288
				],
				[
					1.1256559931871857,
					3.575601533439664
				],
				[
					0.5024889846639833,
					-0.0003322661072600618
				]
			]
		},
		{
			"type": "freedraw",
			"version": 447,
			"versionNonce": 271465498,
			"isDeleted": false,
			"id": "9MqTujYgU8TnIbcJQ5B0q",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -47.70186973760897,
			"y": -102.93756700630246,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.049707513992417,
			"height": 3.6081603464384635,
			"seed": 1074768377,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.12431347457741533
				],
				[
					-0.0222661443319501,
					0.1911165725940725
				],
				[
					-0.19351905831185018,
					0.4972585633304109
				],
				[
					-0.5337530211366086,
					1.0501381697930172
				],
				[
					-0.9689248224905007,
					1.616854227981721
				],
				[
					-2.049707513992417,
					3.5413572484218063
				],
				[
					-2.049707513992417,
					3.6081603464384635
				],
				[
					-2.049707513992417,
					3.6081603464384635
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 456,
			"versionNonce": 2113317510,
			"isDeleted": false,
			"id": "Is1uBmnXiaiU_C6W-9jL_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -32.524345818844466,
			"y": -101.67938756841232,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.143645564181995,
			"height": 4.311995361331385,
			"seed": 1750729433,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.017465837917172957,
					0.017470502938037178
				],
				[
					-0.017465837917172957,
					0.06988201175209137
				],
				[
					-0.017465837917172957,
					0.1716261156448229
				],
				[
					-0.017465837917172957,
					0.27337021953752577
				],
				[
					0.004795641393941597,
					0.8560079937549215
				],
				[
					0.041164143638239,
					1.0378365099138445
				],
				[
					0.07752331584086529,
					1.4014888772109124
				],
				[
					0.09979412519365094,
					1.5926054498050137
				],
				[
					0.648568513342393,
					2.732685220838355
				],
				[
					0.9782641941545833,
					3.1873288190582985
				],
				[
					1.751603354113867,
					3.8621474045053836
				],
				[
					1.9334272052519543,
					3.934875078952308
				],
				[
					2.297074907528244,
					4.116698930090452
				],
				[
					2.6032402233686454,
					4.241021734709452
				],
				[
					3.091238720388805,
					4.311995361331385
				],
				[
					3.126179726264822,
					4.311995361331385
				],
				[
					3.126179726264822,
					4.311995361331385
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 533,
			"versionNonce": 33794266,
			"isDeleted": false,
			"id": "NYzQSVyHhSn7z5GzqHs-N",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -47.933781917197194,
			"y": -101.28211439612872,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.330895807975184,
			"height": 3.410778650894936,
			"seed": 1269186489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.017470502938037178
				],
				[
					0.017470502938008507,
					0.034941005876045685
				],
				[
					0.06988201175203403,
					0.08735251469009987
				],
				[
					0.17162611564479424,
					0.16683047425088132
				],
				[
					0.20656712152081125,
					0.21924198306493553
				],
				[
					0.2764537982936809,
					0.28912865983783376
				],
				[
					0.7067786430247271,
					0.59064294992945
				],
				[
					0.7735770760206349,
					0.612913759282207
				],
				[
					1.357409095565652,
					1.0352287632803923
				],
				[
					1.5378101153563517,
					1.1617954429095931
				],
				[
					1.8040801732191887,
					1.3436379541309653
				],
				[
					2.2550757251647426,
					1.6563716192735842
				],
				[
					2.4354767449554426,
					1.7829382989027853
				],
				[
					2.772874375126982,
					2.0184378794948232
				],
				[
					2.9639909477210837,
					2.1028607611154815
				],
				[
					3.2126178968758565,
					2.196095867048528
				],
				[
					3.518759887612195,
					2.330984943804966
				],
				[
					3.767391501787861,
					2.455298418382382
				],
				[
					4.322160441678974,
					2.6576250359858147
				],
				[
					4.583159026025165,
					2.750710861252927
				],
				[
					4.684903129917869,
					2.772977005584877
				],
				[
					4.809216604495284,
					2.8351337428735848
				],
				[
					5.000333177089328,
					2.866212111517924
				],
				[
					5.248964791264994,
					2.924842093073336
				],
				[
					5.408219271718426,
					3.021944501258896
				],
				[
					5.541825467751741,
					3.0664767899227963
				],
				[
					5.6435695716445,
					3.1062181022135906
				],
				[
					5.892196520799274,
					3.168374839502298
				],
				[
					6.06892616921155,
					3.203315845378344
				],
				[
					6.17067027310431,
					3.220786348316352
				],
				[
					6.324825885811039,
					3.2430524926483026
				],
				[
					6.359766891687113,
					3.2430524926483026
				],
				[
					6.444040492641808,
					3.2653186369802816
				],
				[
					6.54578459653451,
					3.2653186369802816
				],
				[
					6.745078950610663,
					3.338050976448012
				],
				[
					6.993710564786271,
					3.374414813671474
				],
				[
					7.152965045239762,
					3.374414813671474
				],
				[
					7.5351981904279075,
					3.410778650894936
				],
				[
					7.69445267088134,
					3.410778650894936
				],
				[
					7.897940878666803,
					3.410778650894936
				],
				[
					7.999684982559505,
					3.410778650894936
				],
				[
					8.133291178592877,
					3.410778650894936
				],
				[
					8.391210849203606,
					3.410778650894936
				],
				[
					8.582327421797707,
					3.410778650894936
				],
				[
					8.773443994391753,
					3.410778650894936
				],
				[
					8.907045525404287,
					3.410778650894936
				],
				[
					9.098162097998388,
					3.410778650894936
				],
				[
					9.257421243472658,
					3.410778650894936
				],
				[
					9.47418610048682,
					3.410778650894936
				],
				[
					9.66530267308092,
					3.410778650894936
				],
				[
					9.798908869114236,
					3.3662463622310352
				],
				[
					9.958163349567723,
					3.3662463622310352
				],
				[
					10.672191434933103,
					3.267721122698059
				],
				[
					11.045131858665293,
					3.1949934482511355
				],
				[
					11.204386339118782,
					3.163915079606767
				],
				[
					11.306139773053099,
					3.1464445766687583
				],
				[
					11.407874546904187,
					3.1464445766687583
				],
				[
					11.59899111949829,
					3.062021695048101
				],
				[
					11.732597315531603,
					3.039750885695315
				],
				[
					11.866203511564974,
					2.9952185970314154
				],
				[
					12.24223217907424,
					2.923909088911101
				],
				[
					12.401486659527674,
					2.875364882349531
				],
				[
					12.622440705230307,
					2.8006825641827198
				],
				[
					12.781704515725355,
					2.7832120612446825
				],
				[
					12.883448619618115,
					2.7386797725807823
				],
				[
					13.025227932112703,
					2.690126235977599
				],
				[
					13.095119273906409,
					2.672660398060397
				],
				[
					13.165001285658501,
					2.6377193921843514
				],
				[
					13.199942291534516,
					2.6202442242255075
				],
				[
					13.45275842937782,
					2.513704478938863
				],
				[
					13.505174603212684,
					2.4962386410216615
				],
				[
					13.606918707105386,
					2.434231184398917
				],
				[
					13.67371247508046,
					2.4119650400669665
				],
				[
					13.775465909014832,
					2.3722237277761726
				],
				[
					13.938387095825853,
					2.2456617131677503
				],
				[
					14.008278437619559,
					2.228191210229742
				],
				[
					14.075081535636246,
					2.183654256545006
				],
				[
					14.15935047157016,
					2.1439176092750474
				],
				[
					14.30113911410636,
					2.0817608719863396
				],
				[
					14.353545957899609,
					2.046819866110294
				],
				[
					14.405962131734526,
					2.0293493631722854
				],
				[
					14.50770623562723,
					1.9721422129642898
				],
				[
					14.577588247379323,
					1.9372012070882438
				],
				[
					14.74613544928871,
					1.8577232475274625
				],
				[
					14.847879553181413,
					1.8179819352366968
				],
				[
					14.900295727016276,
					1.7655704264226142
				],
				[
					15.002039830909034,
					1.7480999234846057
				],
				[
					15.036980836785052,
					1.7306294205465682
				],
				[
					15.089387680578298,
					1.6956884146705515
				],
				[
					15.191131784471002,
					1.6559517674005642
				],
				[
					15.243547958305921,
					1.6384812644625555
				],
				[
					15.278488964181935,
					1.6210107615245186
				],
				[
					15.295954802099166,
					1.60354025858651
				],
				[
					15.330895807975184,
					1.5860697556484729
				],
				[
					15.330895807975184,
					1.5860697556484729
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 585,
			"versionNonce": 1342925254,
			"isDeleted": false,
			"id": "4QkEFHiX91qiUcYtEHZ_G",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -15.111164271730033,
			"y": -89.38805096608814,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.245421756554425,
			"height": 28.242259912127682,
			"seed": 2014830745,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.483734070373312,
					14.34862195319115
				],
				[
					-9.089638653522744,
					23.39603479462973
				],
				[
					-9.245421756554425,
					28.242259912127682
				]
			]
		},
		{
			"type": "line",
			"version": 534,
			"versionNonce": 403537306,
			"isDeleted": false,
			"id": "6aSjTB38iupnR6BsndnHQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -30.698224649099245,
			"y": -81.1318990906893,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.6742912300047594,
			"height": 11.904073699056866,
			"seed": 1801610617,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.453397648128615,
					5.221708579510462
				],
				[
					-3.6742912300047594,
					8.509660693590416
				],
				[
					-3.6220539822906668,
					11.904073699056866
				]
			]
		},
		{
			"type": "line",
			"version": 512,
			"versionNonce": 1472610566,
			"isDeleted": false,
			"id": "x5O8qq-7wfuJtblP_CapH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 11.884205101416782,
			"y": -77.83599146079627,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.175414001643883,
			"height": 17.83171760621709,
			"seed": 550063705,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.421904725529686,
					6.88783791747567
				],
				[
					-8.379174343088001,
					14.892030363530656
				],
				[
					-11.175414001643883,
					17.83171760621709
				]
			]
		},
		{
			"type": "line",
			"version": 563,
			"versionNonce": 528398938,
			"isDeleted": false,
			"id": "e2pTTR8VbTsDdMDdGuM9t",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 24.657555467776533,
			"y": -96.43979138007523,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18.959046972466084,
			"height": 38.70415055356104,
			"seed": 1595939641,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.0533132474636515,
					16.794858643889985
				],
				[
					-11.834728616151706,
					29.63360613118773
				],
				[
					-18.959046972466084,
					38.70415055356104
				]
			]
		},
		{
			"type": "line",
			"version": 492,
			"versionNonce": 681848902,
			"isDeleted": false,
			"id": "vdn4z1-9onVX6rnuyU5cF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -38.316490156390856,
			"y": -71.43514830844359,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.2371621647747666,
			"height": 4.299931467029022,
			"seed": 1187662873,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.2371621647747666,
					1.790681330542172
				],
				[
					-1.2040787400888595,
					4.299931467029022
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 1193959194,
			"isDeleted": false,
			"id": "ebqC1dpGrNliU1Opab4UM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -61.7209919637929,
			"y": -97.31371124793074,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2121462783203345,
			"height": 27.10712400976242,
			"seed": 532373753,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.16788522040783666,
					10.99850557759535
				],
				[
					0.4435820814537782,
					21.80907326758357
				],
				[
					3.044261057912498,
					27.10712400976242
				]
			]
		},
		{
			"type": "line",
			"version": 648,
			"versionNonce": 1585592198,
			"isDeleted": false,
			"id": "KKWsmbneOxzNTNLTTFpPJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -31.237218294421353,
			"y": -129.32510783108333,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.039116292380407,
			"height": 10.185890855003738,
			"seed": 1735842265,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.4334045728080445,
					4.618281215290141
				],
				[
					-3.039116292380407,
					10.185890855003738
				]
			]
		},
		{
			"type": "line",
			"version": 602,
			"versionNonce": 1803774938,
			"isDeleted": false,
			"id": "ioGHOiKHAMCaVwc00-fx1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 28.622476290444297,
			"y": -139.47497415388537,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.09096653343659,
			"height": 38.404476651800564,
			"seed": 521156281,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.608458487276161,
					12.874461645130982
				],
				[
					-11.326280774678754,
					29.39738764831602
				],
				[
					-13.65571738302803,
					34.453008695760914
				],
				[
					-14.09096653343659,
					38.404476651800564
				]
			]
		},
		{
			"type": "line",
			"version": 979,
			"versionNonce": 295524038,
			"isDeleted": false,
			"id": "Z2vQpsG3Ql-EPeCEvzWWS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 29.323261886571757,
			"y": -159.03330809649617,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.446988281047467,
			"height": 22.794077363418577,
			"seed": 1495988121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.214822946874181,
					4.4938484064707085
				],
				[
					-7.078730569070812,
					7.958820679371845
				],
				[
					-8.855452502015831,
					9.084190962607003
				],
				[
					-10.055404504501297,
					11.73565215174032
				],
				[
					-14.446988281047467,
					22.794077363418577
				]
			]
		},
		{
			"type": "line",
			"version": 513,
			"versionNonce": 1654448282,
			"isDeleted": false,
			"id": "6PHBnLub8Lw27KDWXK3sS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 13.574767109669637,
			"y": -160.86556717744094,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.613607408769284,
			"height": 21.57631732116673,
			"seed": 133864569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.189127529832884,
					7.016784811110411
				],
				[
					-7.613607408769284,
					21.57631732116673
				]
			]
		},
		{
			"type": "line",
			"version": 509,
			"versionNonce": 1251118598,
			"isDeleted": false,
			"id": "s2dQFz3OULZnu_YkifUQu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -17.47536280935023,
			"y": -152.04496102652416,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.136429020349956,
			"height": 15.339351835376002,
			"seed": 188917081,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.9838845527591453,
					5.445992547165052
				],
				[
					-6.136429020349956,
					15.339351835376002
				]
			]
		},
		{
			"type": "line",
			"version": 498,
			"versionNonce": 1210695002,
			"isDeleted": false,
			"id": "xo4c_XpwamADWzREzYL4c",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -40.18515242626707,
			"y": -168.4052806565606,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.02860410179986677,
			"height": 8.606035659498527,
			"seed": 2119602745,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.02860410179986677,
					8.606035659498527
				]
			]
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 1985928518,
			"isDeleted": false,
			"id": "0qXnDEkvzQPQI4uwGgxzI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -40.495914141967404,
			"y": -153.83619854793474,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.15825120000992346,
			"height": 6.908923510573309,
			"seed": 1176101657,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.15825120000992346,
					6.908923510573309
				]
			]
		},
		{
			"type": "line",
			"version": 491,
			"versionNonce": 1232929306,
			"isDeleted": false,
			"id": "T_cnEmCoBcAC3QvlOnqik",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -51.65212962667394,
			"y": -160.37172927824162,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.58244247624093,
			"height": 17.949247689081314,
			"seed": 1593841657,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3989590815703261,
					7.138416801628602
				],
				[
					-1.58244247624093,
					17.949247689081314
				]
			]
		},
		{
			"type": "line",
			"version": 482,
			"versionNonce": 1516192902,
			"isDeleted": false,
			"id": "OhVmuPb3RWJIaZKT03BnX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -68.85305726434481,
			"y": -163.5647118015541,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.969386345258381,
			"height": 13.061268528539353,
			"seed": 1795993817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6372532043956359,
					6.7656944299982
				],
				[
					-2.969386345258381,
					13.061268528539353
				]
			]
		},
		{
			"type": "line",
			"version": 631,
			"versionNonce": 1904848602,
			"isDeleted": false,
			"id": "mmstrfMdvkhXxrd_9O3Ar",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -31.64714586235121,
			"y": -176.8698253319476,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.6169539106676254,
			"height": 18.004764973121592,
			"seed": 2144546233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.6169539106676254,
					18.004764973121592
				]
			]
		},
		{
			"type": "line",
			"version": 461,
			"versionNonce": 139510726,
			"isDeleted": false,
			"id": "MNW4JiAUH8PZKTH5kQyTu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 29.363392947615225,
			"y": -110.55112131811788,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0845473632965916,
			"height": 3.821500360481713,
			"seed": 880217753,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.0845473632965916,
					3.821500360481713
				]
			]
		},
		{
			"type": "line",
			"version": 520,
			"versionNonce": 1961018266,
			"isDeleted": false,
			"id": "g-TKd9-ZzluRzKHXRb9Bm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -62.516775094934246,
			"y": -142.90576196587966,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5742707005446802,
			"height": 6.081778301546508,
			"seed": 1873531769,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5742707005446802,
					2.7131979935188624
				],
				[
					-0.39687790148171437,
					6.081778301546508
				]
			]
		},
		{
			"type": "ellipse",
			"version": 622,
			"versionNonce": 1380997894,
			"isDeleted": false,
			"id": "caVpxxA184HbmHOyUkbm-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -78.576566768448,
			"y": -128.99463465002825,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 24.9402670346161,
			"height": 25.19423893136538,
			"seed": 1974795353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 787,
			"versionNonce": 2109423706,
			"isDeleted": false,
			"id": "D1wAgrmkFTtpBTzF3cNLc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -23.317667766450313,
			"y": -124.86218916646936,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 27.642771723892334,
			"height": 26.86659829465448,
			"seed": 912656697,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 576,
			"versionNonce": 1054542406,
			"isDeleted": false,
			"id": "ip4ABJp2yW_Xn7WviSTM_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -14.032202750370999,
			"y": -97.3860740102347,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.787538342168673,
			"height": 2.0507223354427575,
			"seed": 1528986137,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5641312008216555,
					1.30930214499325
				],
				[
					6.144102620736693,
					2.0507223354427575
				],
				[
					9.61782783282841,
					1.7652892692068065
				],
				[
					11.787538342168673,
					0.8248646736669407
				]
			]
		},
		{
			"type": "line",
			"version": 551,
			"versionNonce": 2011571482,
			"isDeleted": false,
			"id": "1yPuWonbVVdiOXOgchGo2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -66.84452584635989,
			"y": -101.48316083398703,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 10.768619209339828,
			"height": 4.854546970565675,
			"seed": 350080761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.5502997729641064,
					-0.1015804693165777
				],
				[
					-5.963388147432223,
					-0.9133183126923806
				],
				[
					-10.768619209339828,
					-4.854546970565675
				]
			]
		},
		{
			"type": "line",
			"version": 926,
			"versionNonce": 2093863302,
			"isDeleted": false,
			"id": "NGLxTLhrDIlwgCyGamRu8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -78.30047778519983,
			"y": -109.65845875389763,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 21.77600817886035,
			"height": 53.01188407394688,
			"seed": 706447321,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.05353757306827793,
					5.395885136117434
				],
				[
					0.21969233699707102,
					12.157161936104105
				],
				[
					1.4073714684538596,
					20.26385890759546
				],
				[
					3.2595571568545427,
					28.271059597529607
				],
				[
					4.184302976295645,
					31.869232134411266
				],
				[
					5.957923075551878,
					35.75530678950516
				],
				[
					8.278571409782453,
					39.51111970963957
				],
				[
					12.949727620488979,
					45.757850814560435
				],
				[
					16.033058412907277,
					49.05572268445689
				],
				[
					19.491631816828008,
					51.48551258961961
				],
				[
					21.77600817886035,
					53.01188407394688
				]
			]
		},
		{
			"type": "line",
			"version": 597,
			"versionNonce": 1557557722,
			"isDeleted": false,
			"id": "6grw1w_LxmY7EgcKp_8ti",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -38.034183111432796,
			"y": -50.93403728268531,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.895044528397792,
			"height": 25.67696227667936,
			"seed": 1156523193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910996,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.16822118872424674,
					3.972455948335856
				],
				[
					1.1251061307726153,
					7.6868515577411225
				],
				[
					4.121007615081228,
					12.096199444143076
				],
				[
					7.804543035276996,
					16.838070013968824
				],
				[
					11.39993862880884,
					21.070078390199367
				],
				[
					14.895044528397792,
					25.67696227667936
				]
			]
		},
		{
			"type": "line",
			"version": 753,
			"versionNonce": 1466282182,
			"isDeleted": false,
			"id": "Y6yTLc9s5ooxHgcURIEo2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.93125290623104,
			"y": -52.4595326517952,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 27.301362328363123,
			"height": 43.507775780618424,
			"seed": 16524697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.25044542504227085,
					6.088540046051409
				],
				[
					2.757971717619095,
					13.294077147110485
				],
				[
					7.050070382425496,
					18.326222179758265
				],
				[
					14.971014402808411,
					26.049968091431598
				],
				[
					20.924939894262916,
					31.128339742530837
				],
				[
					24.562764610047967,
					34.09594874608821
				],
				[
					26.759653576486976,
					39.66649931787858
				],
				[
					27.301362328363123,
					43.507775780618424
				]
			]
		},
		{
			"type": "line",
			"version": 913,
			"versionNonce": 2141136538,
			"isDeleted": false,
			"id": "EH2xW_kG_JZ_pzg-OQw2g",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -47.374902787086825,
			"y": -52.70950176968884,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 25.826490732290267,
			"height": 44.2457631912289,
			"seed": 964037241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.2428702364838085,
					2.3092622743975193
				],
				[
					-3.3229946217797837,
					5.86323167571824
				],
				[
					-2.8913190740999863,
					10.282964974989245
				],
				[
					-1.6430800778629833,
					14.631522078080772
				],
				[
					0.5775094809548573,
					18.596304426029945
				],
				[
					7.890136837121328,
					24.89304419519931
				],
				[
					11.704206357722347,
					28.47598203007871
				],
				[
					14.339626253494528,
					31.252457621848066
				],
				[
					18.940820070552025,
					34.60549533649989
				],
				[
					21.455126157751604,
					39.48926830360011
				],
				[
					22.503496110510486,
					44.2457631912289
				]
			]
		},
		{
			"type": "line",
			"version": 607,
			"versionNonce": 708814854,
			"isDeleted": false,
			"id": "_cXrdfqcy0TrQl3YWnReW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -50.70172752407339,
			"y": -43.96750943531832,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6311331004943885,
			"height": 5.4109658924329755,
			"seed": 387994457,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.378506652184433,
					0.6150367025990265
				],
				[
					-2.6311331004943885,
					2.3831443620713064
				],
				[
					-1.9939755869040507,
					5.4109658924329755
				]
			]
		},
		{
			"type": "line",
			"version": 826,
			"versionNonce": 1492337498,
			"isDeleted": false,
			"id": "-5fBtC9r3utFGMkPKVnSb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -52.82540903706783,
			"y": -39.45016272865905,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 23.367372258184027,
			"height": 31.678689865985547,
			"seed": 1582202937,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.6343643835966308,
					0.686858286465304
				],
				[
					-2.3263147197012994,
					2.8194442013421566
				],
				[
					-2.119476847549546,
					5.653596136758818
				],
				[
					-0.5136753098367453,
					8.410775228790342
				],
				[
					0.1408484614189144,
					11.419158155703293
				],
				[
					3.311709218741945,
					14.472167568815735
				],
				[
					9.02609613881119,
					17.47342754722153
				],
				[
					15.186244636899657,
					21.673065882314646
				],
				[
					18.91004956689527,
					26.06127888929273
				],
				[
					21.041057538482725,
					31.678689865985547
				]
			]
		},
		{
			"type": "line",
			"version": 660,
			"versionNonce": 1431877446,
			"isDeleted": false,
			"id": "KF3d328lbPnBrOKAiDCRf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -44.775050265946476,
			"y": -22.422171105119318,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.896362563807656,
			"height": 12.784620871427974,
			"seed": 2095321369,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2521985608574321,
					2.109180249499827
				],
				[
					1.3224645012121086,
					4.692779658709921
				],
				[
					3.4412485931711885,
					7.125157035607996
				],
				[
					4.965595099618625,
					8.51517408837248
				],
				[
					5.896362563807656,
					12.784620871427974
				]
			]
		},
		{
			"type": "line",
			"version": 583,
			"versionNonce": 1394984986,
			"isDeleted": false,
			"id": "96QSnD2bPI5SHm8CEvci5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -50.446939991572066,
			"y": -25.432529552247928,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.057235293041969,
			"height": 17.97494584976445,
			"seed": 1481934329,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.25499326717107257,
					2.181866297607115
				],
				[
					0.18757097735369307,
					5.55672285286465
				],
				[
					1.5397173911726885,
					9.10356042419636
				],
				[
					3.6379615759238244,
					13.337931274620061
				],
				[
					6.802242025870897,
					17.97494584976445
				]
			]
		},
		{
			"type": "line",
			"version": 816,
			"versionNonce": 822992518,
			"isDeleted": false,
			"id": "2tAhPJ-6264ajiufctwNJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -55.43153337514575,
			"y": -35.245714607871065,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.21813678348159,
			"height": 27.727723941413895,
			"seed": 1537433305,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.6147639003372989,
					2.855756199419029
				],
				[
					-2.6599426147363645,
					8.947090975521181
				],
				[
					-0.9261580516923844,
					16.826574997508654
				],
				[
					8.558194168745226,
					27.727723941413895
				]
			]
		},
		{
			"type": "line",
			"version": 603,
			"versionNonce": 371832026,
			"isDeleted": false,
			"id": "drgRU4DJgmE_H-TKiLJfF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -57.837096949338985,
			"y": -21.861311442287487,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.289933670204591,
			"height": 14.251095119185532,
			"seed": 1164188601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.7888509167199131,
					3.341965254274142
				],
				[
					-0.8240325010514387,
					6.062357694717061
				],
				[
					-0.330651405425629,
					8.869629002058527
				],
				[
					4.4659011691531525,
					14.251095119185532
				]
			]
		},
		{
			"type": "line",
			"version": 657,
			"versionNonce": 35397062,
			"isDeleted": false,
			"id": "jeGMNtythe9qCRICHJdgF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -29.665411371178976,
			"y": -49.94412506983686,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.72736334160527,
			"height": 18.22899297789004,
			"seed": 901397657,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.24786816978595902,
					3.8802563068888962
				],
				[
					1.7309906091050944,
					8.512709390459884
				],
				[
					3.6295982674479896,
					12.628744634908346
				],
				[
					7.73028492777729,
					16.78453537537364
				],
				[
					11.72736334160527,
					18.22899297789004
				]
			]
		},
		{
			"type": "line",
			"version": 840,
			"versionNonce": 1402079642,
			"isDeleted": false,
			"id": "DCUSCjzTxt6PtLvrPPMeG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -17.75021652875003,
			"y": -35.43811905487138,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.485864813714726,
			"height": 25.617853053947577,
			"seed": 2086224249,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.06427824521453396,
					7.825432280774147
				],
				[
					4.1224108892260505,
					17.68450484674747
				],
				[
					4.485864813714726,
					25.617853053947577
				]
			]
		},
		{
			"type": "line",
			"version": 555,
			"versionNonce": 1839232262,
			"isDeleted": false,
			"id": "Uu8SKAtAJ-qw2oIBS9L4S",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -22.0519267751598,
			"y": -32.98087352857195,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.404851843409941,
			"height": 5.762381678685405,
			"seed": 646228569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2572685697851977,
					2.4218140108889767
				],
				[
					2.916238003350311,
					4.254554930038747
				],
				[
					4.404851843409941,
					5.762381678685405
				]
			]
		},
		{
			"type": "line",
			"version": 1536,
			"versionNonce": 311543386,
			"isDeleted": false,
			"id": "OC8QCMmFBk9n8di0Bx0Bu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -17.62065939135671,
			"y": -35.54425276392361,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 48.22137850907772,
			"height": 14.529393917378613,
			"seed": 1292891961,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					35.730059696874896,
					0.2618912181359582
				],
				[
					46.51086429942135,
					-0.7391346890997577
				],
				[
					42.10305586988709,
					-1.9174882645310567
				],
				[
					47.96193265896619,
					-3.320040048791429
				],
				[
					46.70230168190813,
					-5.088911515709617
				],
				[
					41.95858376384114,
					-4.98562580186265
				],
				[
					44.94537876867852,
					-6.44009872948027
				],
				[
					48.22137850907772,
					-8.696818156785458
				],
				[
					46.36654613906216,
					-10.151154901680199
				],
				[
					38.55227492057892,
					-9.289201159477479
				],
				[
					39.22648597677728,
					-13.122863229214044
				],
				[
					37.22341575237789,
					-14.267502699242653
				],
				[
					33.01653012803063,
					-10.241053261766094
				],
				[
					18.610458547730953,
					-9.882697307904612
				],
				[
					6.068882389785583,
					-11.330011761087414
				],
				[
					1.7797187168476052,
					-13.60360600405784
				]
			]
		},
		{
			"type": "line",
			"version": 551,
			"versionNonce": 1830282310,
			"isDeleted": false,
			"id": "ckLDFGdH89Br5CO58PaMv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -23.598885534598395,
			"y": -46.39328491064906,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.4395614958964496,
			"height": 10.833827049662984,
			"seed": 576628761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6923115163697611,
					2.310440551000129
				],
				[
					3.427926370277558,
					6.746871036297708
				],
				[
					7.4395614958964496,
					10.833827049662984
				]
			]
		},
		{
			"type": "line",
			"version": 757,
			"versionNonce": 2080107290,
			"isDeleted": false,
			"id": "jHUPchlsBaVJrTD85WkGG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -20.249430017658327,
			"y": -48.85662905453982,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 19.286191297833074,
			"height": 13.656285359151598,
			"seed": 1080311033,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.8864865798046947,
					1.7200604261603747
				],
				[
					3.9812250557259703,
					4.367961355273937
				],
				[
					7.87498559035446,
					7.378125971631913
				],
				[
					11.33541025230297,
					10.116877124369053
				],
				[
					16.983820423474196,
					13.557692936675815
				],
				[
					19.286191297833074,
					13.656285359151598
				]
			]
		},
		{
			"type": "line",
			"version": 628,
			"versionNonce": 1113549702,
			"isDeleted": false,
			"id": "6xbk_JF7meuREjsPMoldP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -10.08479302640957,
			"y": -46.59504553563147,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18.636688524361396,
			"height": 11.488655751798156,
			"seed": 916731353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.5503870114634455,
					2.158321489013236
				],
				[
					3.5110037522420123,
					4.0353516428634295
				],
				[
					8.422451417033107,
					7.218533976116025
				],
				[
					13.660678406934005,
					10.434447530771196
				],
				[
					16.49802767584512,
					11.488655751798156
				],
				[
					18.636688524361396,
					11.367701809900327
				]
			]
		},
		{
			"type": "line",
			"version": 545,
			"versionNonce": 641955802,
			"isDeleted": false,
			"id": "ReUn7jMOEnNRxegOfW01q",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -0.3067787855088113,
			"y": -45.54997339901544,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.069677762782932,
			"height": 7.219291862573989,
			"seed": 1479676601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.352194166014451,
					4.011928214522572
				],
				[
					11.069677762782932,
					7.219291862573989
				]
			]
		},
		{
			"type": "line",
			"version": 653,
			"versionNonce": 1806961350,
			"isDeleted": false,
			"id": "IK80d0Ns-KvngAh9bp_EI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 20.66912629130256,
			"y": -45.201526218492916,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.210217564244612,
			"height": 5.0392936366659224,
			"seed": 1236358041,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3195675617832593,
					1.953547081162965
				],
				[
					-1.3379893316240736,
					3.898485045842739
				],
				[
					-3.210217564244612,
					5.0392936366659224
				]
			]
		},
		{
			"type": "line",
			"version": 1426,
			"versionNonce": 1635478682,
			"isDeleted": false,
			"id": "HSIzVNOqy8cSKG_qRP9Ia",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -48.53621861913261,
			"y": -53.22374328836821,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 41.88302197315356,
			"height": 26.152320435420336,
			"seed": 1331001465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.441031209034651,
					0.9741486853535919
				],
				[
					-9.486386776386091,
					1.2870055619282164
				],
				[
					-13.733035898258844,
					1.0346523587972087
				],
				[
					-15.476950749249806,
					-0.31752807167807195
				],
				[
					-18.377990808492335,
					-0.9490736496673141
				],
				[
					-20.62108813227886,
					-1.120603857972492
				],
				[
					-23.103860779109425,
					-2.3849643112310703
				],
				[
					-24.261994180682205,
					-4.382501662633189
				],
				[
					-26.264890954963935,
					-4.745573509252245
				],
				[
					-31.40604601762965,
					-9.04287679915816
				],
				[
					-33.336129500611904,
					-11.573242811543755
				],
				[
					-35.74657786008925,
					-11.423646845060471
				],
				[
					-35.1659279335634,
					-8.868033740044524
				],
				[
					-39.77405058360137,
					-12.130411493022807
				],
				[
					-39.89493718877347,
					-8.88483193115976
				],
				[
					-41.72833070629245,
					-9.976140830502734
				],
				[
					-41.88302197315356,
					-5.46299210430195
				],
				[
					-36.37505961705744,
					-1.8974937848015576
				],
				[
					-33.7540346878785,
					-1.2728274660309438
				],
				[
					-33.14309670211639,
					0.7232987165757613
				],
				[
					-28.455483743933122,
					0.874041729352647
				],
				[
					-28.702288865254687,
					2.9177009066568127
				],
				[
					-27.271300317324535,
					4.618746411696555
				],
				[
					-24.54797998855821,
					5.130344151348735
				],
				[
					-24.23947283227058,
					7.246149521976386
				],
				[
					-20.119041062292176,
					7.614991313306429
				],
				[
					-17.212513292097743,
					10.601501414135251
				],
				[
					-13.810515856847458,
					11.08266922303582
				],
				[
					-11.381421958013686,
					13.300190433018328
				],
				[
					-5.361674712606933,
					14.021908942397527
				]
			]
		},
		{
			"type": "line",
			"version": 578,
			"versionNonce": 397591046,
			"isDeleted": false,
			"id": "rw__6B3Q29PymSfbCkXPx",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -73.685818351589,
			"y": -48.32820253185879,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18.057605685980377,
			"height": 3.7294731149822895,
			"seed": 1524760921,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.415961183553149,
					-0.7705977742001967
				],
				[
					13.011586039195821,
					-2.141487133432371
				],
				[
					15.929810663041923,
					-3.663010837897825
				],
				[
					18.057605685980377,
					-3.7294731149822895
				]
			]
		},
		{
			"type": "line",
			"version": 577,
			"versionNonce": 56019290,
			"isDeleted": false,
			"id": "Gbs8JJxIdgVJkMkMzcbnp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -68.84649040982217,
			"y": -45.804528629033385,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18.1495142795251,
			"height": 2.6657778458858954,
			"seed": 1504341561,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.77181819925361,
					-0.5320423305638124
				],
				[
					12.40888565694732,
					-1.831029998445658
				],
				[
					15.972498896420449,
					-2.664304796961504
				],
				[
					18.1495142795251,
					-2.6657778458858954
				]
			]
		},
		{
			"type": "line",
			"version": 579,
			"versionNonce": 425234758,
			"isDeleted": false,
			"id": "Uy5pkeigph-GrjyVdT57v",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -76.79756175933397,
			"y": -52.36573077101107,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.301496979694086,
			"height": 1.5269140727311572,
			"seed": 1116880665,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.443417295294209,
					-0.01756267500635721
				],
				[
					7.7605844854714405,
					-0.42076169214303777
				],
				[
					11.301496979694086,
					-1.5269140727311572
				]
			]
		},
		{
			"type": "line",
			"version": 567,
			"versionNonce": 858295834,
			"isDeleted": false,
			"id": "QMFL-ZV4Spsv_OCwlMaqL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -72.52082682059773,
			"y": -57.3361593177345,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.254261855960554,
			"height": 1.068775476759842,
			"seed": 1678570489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4916280558032347,
					0.7083886240306269
				],
				[
					-7.254261855960554,
					1.068775476759842
				]
			]
		},
		{
			"type": "line",
			"version": 535,
			"versionNonce": 1543665798,
			"isDeleted": false,
			"id": "-V6Hqp4LthWHRBqsBB9g7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -83.4753151295971,
			"y": -62.02570414335956,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.8908504853679577,
			"height": 5.418934961728301,
			"seed": 1914571993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4751910940024163,
					1.205124567823678
				],
				[
					0.8908504853679577,
					3.337572674608333
				],
				[
					0.2986485952485947,
					5.418934961728301
				]
			]
		},
		{
			"type": "line",
			"version": 481,
			"versionNonce": 904116954,
			"isDeleted": false,
			"id": "qSbefWJ1m4HXY2lVdCZ-K",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -88.25663271433734,
			"y": -62.05321816169112,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.247778087959118,
			"height": 1.247883736959854,
			"seed": 1415121337,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.247778087959118,
					1.247883736959854
				]
			]
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 1466791878,
			"isDeleted": false,
			"id": "lTVKL0OGAnMwYLgrInYtZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -26.515219633079667,
			"y": -54.71472306247041,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.194081104753949,
			"height": 4.781061398085074,
			"seed": 870410905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.02486222841339951,
					1.4470944216305106
				],
				[
					-0.4155664494565766,
					3.444711034126212
				],
				[
					-2.1692188763405493,
					4.781061398085074
				]
			]
		},
		{
			"type": "line",
			"version": 1014,
			"versionNonce": 974868378,
			"isDeleted": false,
			"id": "jdk7K96X1kBTtT2wYI0jv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -59.40454017716908,
			"y": -16.971918026568204,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 94.51162448047299,
			"height": 9.589491014223803,
			"seed": 1231728505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.610534882567289,
					1.129499503833512
				],
				[
					-17.68707095143928,
					4.2443093574193975
				],
				[
					-19.941431508631037,
					6.649653820233758
				],
				[
					-13.733494716776287,
					8.763445232177403
				],
				[
					14.289245339307717,
					9.589491014223803
				],
				[
					40.126411787023386,
					8.880852244857298
				],
				[
					67.17887233913872,
					5.79711264683608
				],
				[
					74.57019297184195,
					3.2328895419840564
				],
				[
					71.84200767064344,
					1.2977520995373146
				],
				[
					65.05013815564232,
					1.1624238009301624
				],
				[
					46.466751909436624,
					0.25840452853461804
				]
			]
		},
		{
			"type": "ellipse",
			"version": 807,
			"versionNonce": 62295814,
			"isDeleted": false,
			"id": "sFNCmwx5pYXczuAVmDPny",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -73.44930501376882,
			"y": -123.88088310961015,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 5.932125331041969,
			"height": 5.729538728240217,
			"seed": 1798854745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 876,
			"versionNonce": 604130394,
			"isDeleted": false,
			"id": "ojvOEkg_50RSMIj6e4hbU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -59.87431376571283,
			"y": -116.67383166683527,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 16.35201554902782,
			"height": 10.008208248895487,
			"seed": 1528685881,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.416459151138018,
					2.0525114136438067
				],
				[
					-2.936191422275502,
					3.568089594820877
				],
				[
					-6.44451588047693,
					4.222444288976066
				],
				[
					-10.92050871556361,
					4.24517937897149
				],
				[
					-12.507544574807747,
					5.798642860588014
				],
				[
					-12.481107457582857,
					8.043764764204738
				],
				[
					-10.434770976486153,
					9.234324503292461
				],
				[
					-3.4466117864651657,
					9.082966570209322
				],
				[
					0.9716025444361138,
					6.200179639749142
				],
				[
					3.2563226997054393,
					3.456381228619217
				],
				[
					3.844470974220071,
					0.35232547462357305
				],
				[
					2.082643227351157,
					-0.7738837456030261
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 874,
			"versionNonce": 1297792582,
			"isDeleted": false,
			"id": "OcDb-wA_x04e34P0XC8xq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -15.72286092692778,
			"y": -120.02930561057579,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 5.932125331041969,
			"height": 5.729538728240217,
			"seed": 1417598489,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 912,
			"versionNonce": 1500229914,
			"isDeleted": false,
			"id": "LVM9eCX9CMpv809Z7575N",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2.017766591965483,
			"y": -111.46657540110394,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 16.35201554902782,
			"height": 10.008208248895487,
			"seed": 1515105017,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.416459151138018,
					2.0525114136438067
				],
				[
					-2.936191422275502,
					3.568089594820877
				],
				[
					-6.44451588047693,
					4.222444288976066
				],
				[
					-10.92050871556361,
					4.24517937897149
				],
				[
					-12.507544574807747,
					5.798642860588014
				],
				[
					-12.481107457582857,
					8.043764764204738
				],
				[
					-10.434770976486153,
					9.234324503292461
				],
				[
					-3.4466117864651657,
					9.082966570209322
				],
				[
					0.9716025444361138,
					6.200179639749142
				],
				[
					3.2563226997054393,
					3.456381228619217
				],
				[
					3.844470974220071,
					0.35232547462357305
				],
				[
					2.082643227351157,
					-0.7738837456030261
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 837,
			"versionNonce": 154600838,
			"isDeleted": false,
			"id": "u2cD6CzZ85ykaKWJWyE8L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 65.49927573163767,
			"y": -208.84165787196056,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 226.49679950953976,
			"height": 120.02018828203519,
			"seed": 1158734809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.244887319713063,
					13.050578821456103
				],
				[
					12.222902665342957,
					8.557879213981312
				],
				[
					39.05050434650967,
					16.76292774269237
				],
				[
					110.1141425449705,
					25.371211340283732
				],
				[
					185.5533789985028,
					6.509901256454644
				],
				[
					206.74646591341957,
					-35.47317862137815
				],
				[
					198.58205904601581,
					-83.51293082500665
				],
				[
					91.94572916848715,
					-92.28963100392468
				],
				[
					-0.7207993630728539,
					-94.64897694175147
				],
				[
					-19.75033359612016,
					-26.49850428927356
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 487,
			"versionNonce": 231374298,
			"isDeleted": false,
			"id": "mwjYs8GNTjPy-hV4-BzYU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 87.52677246031438,
			"y": -266.1103277864397,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2107352277628185,
			"height": 34.59465273877539,
			"seed": 282656953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2107352277628185,
					34.59465273877539
				]
			]
		},
		{
			"type": "line",
			"version": 640,
			"versionNonce": 1753769158,
			"isDeleted": false,
			"id": "QOUgQwRABu_1uPwoNRolm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 107.27259398166274,
			"y": -231.22429984709012,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.863739996190894,
			"height": 33.91628007390165,
			"seed": 1800044953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.208259293552254,
					-32.886735305264004
				],
				[
					7.999677651812496,
					-17.41345639781491
				],
				[
					9.863739996190894,
					1.0295447686376527
				]
			]
		},
		{
			"type": "line",
			"version": 706,
			"versionNonce": 238138010,
			"isDeleted": false,
			"id": "HQ3evszxj_xCukbIhgBPE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 126.23513984872392,
			"y": -229.99684690198896,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.320361281189058,
			"height": 36.78215497105805,
			"seed": 26797689,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.222495501864999,
					-34.63890112760136
				],
				[
					2.5457778298791296,
					-27.016522361821806
				],
				[
					5.518842909509561,
					-15.955678713064271
				],
				[
					12.320361281189058,
					-32.3038749429108
				],
				[
					11.252462044304574,
					-21.186731157277293
				],
				[
					10.624957432788014,
					2.1432538434566952
				]
			]
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 1827396614,
			"isDeleted": false,
			"id": "CJ6KvXB-gf9kb0wc58L4J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 109.42594226372319,
			"y": -245.91120219427583,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.734178129837961,
			"height": 0.3608706820305014,
			"seed": 243773273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.734178129837961,
					-0.3608706820305014
				]
			]
		},
		{
			"type": "line",
			"version": 833,
			"versionNonce": 223629146,
			"isDeleted": false,
			"id": "WjdzOkNnVxPlityXZfYvx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 165.0552628345352,
			"y": -257.8275455930235,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.983654497166203,
			"height": 31.603012674081846,
			"seed": 678059065,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.5744352961793093,
					-0.9833902446186322
				],
				[
					-5.9144097350874985,
					0.8493272353935263
				],
				[
					-7.446417999945728,
					10.708547826065672
				],
				[
					-8.82500754596149,
					19.726295371863575
				],
				[
					-6.328322318909104,
					29.87121547322952
				],
				[
					-1.9407163002694794,
					30.619622429463217
				],
				[
					-0.8308803974269553,
					27.297658059587217
				],
				[
					0.1586469512047129,
					16.759110679125563
				],
				[
					-4.196452843574608,
					15.455439393675315
				]
			]
		},
		{
			"type": "line",
			"version": 882,
			"versionNonce": 1549691718,
			"isDeleted": false,
			"id": "zC0RZ_0fuOSzUtLpKzcT6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 174.44343330764195,
			"y": -229.20115270598225,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.075183897287152,
			"height": 36.77255028274339,
			"seed": 1327787289,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8154578001300847,
					-32.56762450540847
				],
				[
					7.075183897287152,
					-23.40620714743224
				],
				[
					4.563335020087894,
					-14.97404827065066
				],
				[
					0.5343336368037389,
					-13.609603964853877
				],
				[
					4.149250727615573,
					-11.730898171413099
				],
				[
					6.3541555893467905,
					-7.650082222554801
				],
				[
					6.579271551308485,
					4.204925777334918
				]
			]
		},
		{
			"type": "ellipse",
			"version": 585,
			"versionNonce": 1871008794,
			"isDeleted": false,
			"id": "2tC7BA2CO8OWot4WH2O8k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.06135700878540096,
			"x": 188.03364876920824,
			"y": -258.0823101677888,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.772411748948018,
			"height": 32.240807714730096,
			"seed": 975790585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 648,
			"versionNonce": 893194886,
			"isDeleted": false,
			"id": "MKj3ad8IrG5jiQ-Q6wvhs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.06135700878540096,
			"x": 203.48784185367083,
			"y": -257.2739707360471,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.772411748948018,
			"height": 32.240807714730096,
			"seed": 1719450329,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 452,
			"versionNonce": 381141210,
			"isDeleted": false,
			"id": "AHWuKSpO-gG2q7mzv5fSa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 219.2094712722211,
			"y": -254.83839107448696,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 10.690106909087044,
			"height": 0.5345527133579779,
			"seed": 1689384889,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.690106909087044,
					0.5345527133579779
				]
			]
		},
		{
			"type": "line",
			"version": 485,
			"versionNonce": 574935494,
			"isDeleted": false,
			"id": "n6p3GP92NCmTIK7aSEH9k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 223.83812071041496,
			"y": -254.757030779029,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0356400028073096,
			"height": 29.548885770566283,
			"seed": 1726781593,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.0356400028073096,
					29.548885770566283
				]
			]
		},
		{
			"type": "line",
			"version": 1143,
			"versionNonce": 780047770,
			"isDeleted": false,
			"id": "t8L4aUPO_X5CgnNnhPtf3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 37.604550805262804,
			"y": -153.32085780175723,
			"strokeColor": "#959c57",
			"backgroundColor": "#959c57",
			"width": 4.649966525822175,
			"height": 15.18397097752588,
			"seed": 249568633,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0997000173229474,
					-1.5164474855908006
				],
				[
					3.3094858877656925,
					-4.848533149980476
				],
				[
					4.19620479647215,
					-2.7116845467053494
				],
				[
					3.9384392381559836,
					1.3593734025430253
				],
				[
					3.4763685102849298,
					7.48857247367498
				],
				[
					3.034918257350648,
					10.335437827545405
				],
				[
					2.895209797576551,
					7.280833765499009
				],
				[
					3.085104551237758,
					3.6074120271179977
				],
				[
					3.052322367046019,
					1.1343364223312236
				],
				[
					-0.45376172935002496,
					-0.05760196758007818
				]
			]
		},
		{
			"type": "line",
			"version": 1367,
			"versionNonce": 1855105286,
			"isDeleted": false,
			"id": "NJ-JZEoAZikYzF48qrC0_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -63.26086050538703,
			"y": -179.1974880011541,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 26.017432251530074,
			"height": 9.603517953795143,
			"seed": 2077230681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.3562247372971017,
					-2.25814885984457
				],
				[
					3.6821947141027804,
					-1.4475512927009015
				],
				[
					7.862578349865594,
					-1.5862471656936346
				],
				[
					11.415824020875332,
					-2.8442752341026063
				],
				[
					13.915417159996027,
					-2.933228268694027
				],
				[
					17.410347285778535,
					-4.08870323504899
				],
				[
					24.756750343296865,
					-2.3513962897877807
				],
				[
					26.017432251530074,
					2.952671379163451
				],
				[
					24.436221637260278,
					4.238434945856079
				],
				[
					23.330455043854396,
					2.3168274411690506
				],
				[
					20.991997084845753,
					4.674066773963666
				],
				[
					13.82185494558884,
					5.5148147187461545
				],
				[
					10.450922326257835,
					4.1284533899911615
				],
				[
					6.1814340079137375,
					5.048492554247625
				],
				[
					0.17257311486947893,
					4.010432192962014
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 866,
			"versionNonce": 2014106202,
			"isDeleted": false,
			"id": "QrFRTUoeh8NTBv1SjZe-E",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -27.748414436873674,
			"y": -191.99122127304113,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 11.060510482718986,
			"height": 16.56034996245727,
			"seed": 412078905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.596150238976944,
					4.912725095848687
				],
				[
					-2.2113493710664063,
					7.283258902429202
				],
				[
					-2.5034325905027806,
					10.99494455518414
				],
				[
					0.12301179451662078,
					12.636458222428361
				],
				[
					0.39659166148197106,
					14.948366294711196
				],
				[
					3.1808625431964606,
					15.179675433325551
				],
				[
					6.18905546825712,
					13.322483858916229
				],
				[
					8.557077892216205,
					12.909185643874407
				],
				[
					6.862119796997751,
					4.0903472371218745
				],
				[
					5.097396733310505,
					-1.3806745291317193
				],
				[
					0.8187543908456432,
					-1.0165757471938721
				]
			]
		},
		{
			"type": "line",
			"version": 1955,
			"versionNonce": 2040764486,
			"isDeleted": false,
			"id": "yLUE91wBqjwgKvVPZkgXH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2.4399382798893754,
			"y": -171.99840867944624,
			"strokeColor": "#8b9743",
			"backgroundColor": "#8b9743",
			"width": 32.36566044028372,
			"height": 31.657395363937727,
			"seed": 696452121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.33364149996430215,
					-2.665684483630161
				],
				[
					-0.077792441548495,
					-6.4079762023180775
				],
				[
					1.1864355571982959,
					-8.455566585316456
				],
				[
					2.7833640357958704,
					-10.271437270113438
				],
				[
					0.8287373333647157,
					-11.430343652493734
				],
				[
					-1.9019837823029278,
					-11.103209068106954
				],
				[
					-2.9455317231891205,
					-9.195494603407676
				],
				[
					-3.829617951570709,
					-5.502053537155443
				],
				[
					-4.851171173490719,
					-4.245256128106684
				],
				[
					-5.763626773220108,
					-9.23370782571244
				],
				[
					-6.29783565230586,
					-17.283605843898126
				],
				[
					-7.947907916575789,
					-19.993526403796764
				],
				[
					-12.01086850080619,
					-19.68818326502202
				],
				[
					-13.153357985054418,
					-17.97575432461368
				],
				[
					-13.643648978428459,
					-20.04718894306855
				],
				[
					-16.70697083448799,
					-21.928082166284007
				],
				[
					-18.50010200674969,
					-21.189323918587338
				],
				[
					-19.537667748342873,
					-18.214732236708905
				],
				[
					-20.538499013523975,
					-11.3401401530428
				],
				[
					-21.40627567210419,
					-13.304105504388367
				],
				[
					-21.351000497557273,
					-20.147307845697046
				],
				[
					-19.199642048679394,
					-27.564505353125153
				],
				[
					-20.863474021797774,
					-29.27743678526468
				],
				[
					-24.704553338160956,
					-28.821314687544078
				],
				[
					-25.257439515075422,
					-30.01151866169458
				],
				[
					-28.28971638038593,
					-29.871483377085923
				],
				[
					-27.98443124227501,
					-27.80359384592502
				],
				[
					-29.58229640448785,
					-22.137784378903653
				],
				[
					-29.483107680727358,
					-19.884633139084773
				],
				[
					-25.72721670362497,
					-20.028854228599236
				],
				[
					-24.212909357342593,
					-17.682056309743647
				],
				[
					-23.373825139227545,
					-10.847752462780043
				],
				[
					-21.16484113376808,
					-5.8329782209856385
				],
				[
					-13.547810199541818,
					-7.2354993161816425
				],
				[
					-7.575634722228425,
					-4.957562820792748
				],
				[
					-4.804209066029048,
					-0.439790303366068
				],
				[
					0.49055768801469546,
					1.645876702243143
				]
			]
		},
		{
			"type": "line",
			"version": 1627,
			"versionNonce": 372602650,
			"isDeleted": false,
			"id": "Mett6P_D4ScI69yrSUrKW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -60.35338626411192,
			"y": -186.2734919763751,
			"strokeColor": "#8b9743",
			"backgroundColor": "#8b9743",
			"width": 25.99950217441492,
			"height": 15.482756078829603,
			"seed": 446503161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.474938037895787,
					1.6920628372622333
				],
				[
					-2.707335615851886,
					4.506708340190999
				],
				[
					-2.842253508560004,
					6.837238464544158
				],
				[
					-1.462576869156117,
					4.710751285678373
				],
				[
					0.9908763235695024,
					5.460332847502137
				],
				[
					5.216168167905996,
					5.208861028706001
				],
				[
					9.47212445359024,
					3.998744787081511
				],
				[
					11.87072602839122,
					5.303520692044211
				],
				[
					13.737160455880263,
					3.2853912637254075
				],
				[
					18.129812814132283,
					4.037853149348608
				],
				[
					21.64163721530449,
					4.698272448308752
				],
				[
					23.032638099427107,
					6.26361528324193
				],
				[
					22.29418219238622,
					-1.0879609237761798
				],
				[
					21.577931411205167,
					-4.302237946966098
				],
				[
					20.716497531744622,
					-4.62983706246266
				],
				[
					20.487321666763496,
					-5.22103776228033
				],
				[
					20.865461536091104,
					-7.535819759277009
				],
				[
					18.917331211546742,
					-8.645517614285444
				],
				[
					17.23450164684105,
					-8.102600439666436
				],
				[
					17.646780511666858,
					-4.192311874735086
				],
				[
					14.935664574351772,
					-5.129086003572388
				],
				[
					13.698209118213601,
					-3.715084094389344
				],
				[
					11.472933452690496,
					2.281138891734525
				],
				[
					9.846963727393403,
					-5.656460051926656
				],
				[
					3.8561873396674757,
					-4.877196991965139
				],
				[
					-2.9668640749878152,
					-1.666608122566065
				],
				[
					-0.061322432566097214,
					-0.5514971523464567
				]
			]
		},
		{
			"type": "line",
			"version": 4576,
			"versionNonce": 726966150,
			"isDeleted": false,
			"id": "uIlJYCffSWha_H4B_0tpN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -17.663571106263092,
			"y": -48.883818880326444,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 126.00690512200109,
			"height": 153.37469580364106,
			"seed": 224498137,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.99668963516609,
					-3.9013942245901614
				],
				[
					26.349593909341372,
					-11.09602023818454
				],
				[
					36.23198974027602,
					-19.650185512472518
				],
				[
					42.07640945043719,
					-27.77893471017809
				],
				[
					49.46446821945845,
					-45.77694945461754
				],
				[
					55.495104480979165,
					-71.91240491366148
				],
				[
					59.47815406359372,
					-107.91698480255974
				],
				[
					54.88284324148288,
					-104.55634404596101
				],
				[
					54.95273458327658,
					-109.91830759538962
				],
				[
					56.929685849569616,
					-113.71354664734626
				],
				[
					51.95682323065467,
					-117.22612538238366
				],
				[
					47.254571471467564,
					-110.53219488620236
				],
				[
					43.20758311361438,
					-113.05471042319842
				],
				[
					43.22537025483999,
					-115.64013201645095
				],
				[
					41.52468093785979,
					-125.86826420225721
				],
				[
					39.0769316894052,
					-127.5715385238944
				],
				[
					38.965192778424395,
					-130.72247959749754
				],
				[
					35.475282545763946,
					-131.01192314624012
				],
				[
					32.37293699395129,
					-130.24851289994996
				],
				[
					27.04816736388677,
					-121.71247473027918
				],
				[
					23.82442922365212,
					-120.372993309691
				],
				[
					20.35231254662084,
					-122.20843000342046
				],
				[
					19.97358691395512,
					-129.69625840627606
				],
				[
					22.802698114961434,
					-133.8421055526502
				],
				[
					18.01070243479072,
					-134.32997867723606
				],
				[
					15.247608275794427,
					-127.76750817595115
				],
				[
					13.207603421961757,
					-142.1336972149406
				],
				[
					7.651745921486372,
					-142.76532610471324
				],
				[
					6.5274574791500335,
					-137.69064509144923
				],
				[
					6.466044696055201,
					-143.35484186898918
				],
				[
					1.407127721116435,
					-144.75844551675937
				],
				[
					-0.7915758925655455,
					-134.77180921267032
				],
				[
					-1.323625014850887,
					-143.06871200115432
				],
				[
					0.6638843597931791,
					-151.91596420543843
				],
				[
					-4.22133826252415,
					-152.25397120395345
				],
				[
					-4.692232460739942,
					-149.6413140529498
				],
				[
					-5.142061757482687,
					-153.20654221286262
				],
				[
					-8.117831882752116,
					-153.37469580364106
				],
				[
					-8.079095299318544,
					-151.16349372451438
				],
				[
					-10.25124328203271,
					-143.09896874300833
				],
				[
					-12.262319175559783,
					-136.10018730060017
				],
				[
					-14.181694755000732,
					-127.83102039334929
				],
				[
					-12.329901332051932,
					-137.4725746117355
				],
				[
					-14.512184072478457,
					-137.97086472779282
				],
				[
					-18.778763123702163,
					-131.1089602441343
				],
				[
					-19.031798517523594,
					-124.34930135410573
				],
				[
					-20.804123894080874,
					-140.34823193257714
				],
				[
					-22.18538232541632,
					-142.2724728371604
				],
				[
					-21.869851397169796,
					-145.36064255698298
				],
				[
					-25.511282672033897,
					-145.79447433110883
				],
				[
					-25.195084645811324,
					-141.52584908513177
				],
				[
					-28.425500180209635,
					-142.29304062235326
				],
				[
					-31.35086592186907,
					-135.09286935683338
				],
				[
					-33.61607407223581,
					-143.4097882917993
				],
				[
					-45.64698080856175,
					-139.2853748751061
				],
				[
					-42.68013632592321,
					-137.81939500081808
				],
				[
					-45.61530648350877,
					-135.5377339051778
				],
				[
					-45.54865120833909,
					-132.48194409480587
				],
				[
					-47.1606485665287,
					-116.08508636644595
				],
				[
					-48.49862580946906,
					-124.34377855259285
				],
				[
					-55.50188450560075,
					-122.71534107793688
				],
				[
					-55.714284652518394,
					-119.90414530622847
				],
				[
					-57.57956115186681,
					-105.54165417092328
				],
				[
					-60.869977017683894,
					-91.54702908296295
				],
				[
					-64.199770907296,
					-79.67136374293757
				],
				[
					-66.12681811346103,
					-71.79514640836963
				],
				[
					-66.52875105840738,
					-60.03485053177136
				],
				[
					-65.02261701748675,
					-47.21098239169894
				],
				[
					-63.12657062399514,
					-39.680645736083896
				],
				[
					-58.20286799438888,
					-26.841472828985072
				],
				[
					-52.605261706542144,
					-17.6792220919545
				],
				[
					-43.35243317605812,
					-9.855881893590315
				],
				[
					-27.722346841482885,
					-3.3633700853371065
				],
				[
					-23.86680745471673,
					-2.419077817786093
				],
				[
					-19.32068297297808,
					-2.131388348388974
				],
				[
					-10.702353205789226,
					-0.947025410259106
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 486,
			"versionNonce": 1500218330,
			"isDeleted": false,
			"id": "4xdRy8xN9sH5DLiB2Ulyc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -16.369561317701525,
			"y": -32.04829644100728,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 1.8064162823551715,
			"height": 4.039728352572535,
			"seed": 652471993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.32557313527810017,
					1.1516698819525122
				],
				[
					0.9796091862976504,
					2.8021193905925568
				],
				[
					1.480843147077071,
					0.7213674959645361
				],
				[
					0.8109330965275398,
					-1.2376089619799782
				]
			]
		},
		{
			"type": "line",
			"version": 501,
			"versionNonce": 1742913222,
			"isDeleted": false,
			"id": "78Icm9JH4wVnuD7RhkUjf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -14.439963873044235,
			"y": -35.38035981739286,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2642676580302092,
			"height": 4.496773641918796,
			"seed": 499625881,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.9163557142426968,
					2.368927490163513
				],
				[
					-3.2642676580302092,
					4.496773641918796
				]
			]
		},
		{
			"type": "line",
			"version": 716,
			"versionNonce": 197261466,
			"isDeleted": false,
			"id": "s2ujkUZM4Z86GTEc0rfQg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.7264182044043244,
			"x": -12.14938993280434,
			"y": -45.715274303040204,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 1.8263549207061947,
			"height": 4.3776006506439336,
			"seed": 138433657,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3854945840009844,
					-1.8018938092873777
				],
				[
					0.9429898498171292,
					-4.022967909436532
				],
				[
					1.4408603367052104,
					-1.5382420188538268
				],
				[
					-0.06926259519922047,
					0.3546327412074017
				]
			]
		},
		{
			"type": "line",
			"version": 586,
			"versionNonce": 65730054,
			"isDeleted": false,
			"id": "HghRwuhdsjVHGY52SmOPD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -13.811869958306872,
			"y": -46.76122183548313,
			"strokeColor": "#000000",
			"backgroundColor": "#a7a967",
			"width": 2.0259965390570867,
			"height": 0.7839739211012101,
			"seed": 1779522905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4153422273846664,
					0.6980986744860949
				],
				[
					2.0259965390570867,
					0.7839739211012101
				]
			]
		},
		{
			"type": "line",
			"version": 437,
			"versionNonce": 1022088538,
			"isDeleted": false,
			"id": "gml96WqQ63go6cr3fLPx2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -56.29185548937215,
			"y": -51.14554982639363,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 0.865243690553531,
			"height": 2.232180290413555,
			"seed": 42879545,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.865243690553531,
					-2.232180290413555
				]
			]
		},
		{
			"type": "line",
			"version": 529,
			"versionNonce": 946488646,
			"isDeleted": false,
			"id": "RRkI6X_AGEA08NxVhAv9e",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -57.23232540944464,
			"y": -53.45022013717494,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 3.0392788788896135,
			"height": 1.3798251391251386,
			"seed": 1520081689,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.7060511878708688,
					-1.2543167986577255
				],
				[
					3.0392788788896135,
					-0.6515906493916748
				],
				[
					1.3420916806620287,
					0.12550834046741297
				]
			]
		},
		{
			"type": "line",
			"version": 570,
			"versionNonce": 238819866,
			"isDeleted": false,
			"id": "9WhIN_5JsH7346waavHgo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -57.288475559237355,
			"y": -53.51186202865729,
			"strokeColor": "#a7a967",
			"backgroundColor": "#a7a967",
			"width": 1.7920740424083252,
			"height": 0.8402278611078257,
			"seed": 313118713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.7635490539843274,
					-0.5318792688775782
				],
				[
					-1.7920740424083252,
					-0.19454732219904516
				],
				[
					-0.918774029411687,
					0.30834859223024746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 575,
			"versionNonce": 381529222,
			"isDeleted": false,
			"id": "bkDE8CGJBANppmbqNkmm_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -57.071954869650966,
			"y": -51.15310317504026,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.4155290503959084,
			"height": 0.5741712279471255,
			"seed": 1891592409,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.8432729067922106,
					0.16772074682246266
				],
				[
					1.4155290503959084,
					-0.40645048112466287
				]
			]
		},
		{
			"type": "line",
			"version": 916,
			"versionNonce": 2124793562,
			"isDeleted": false,
			"id": "YQrdNtZbfTvfgOwjqUMq3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -79.3717817918104,
			"y": -9.542887731854137,
			"strokeColor": "#7d4105",
			"backgroundColor": "#7d4105",
			"width": 30.10593539607036,
			"height": 64.14975077606748,
			"seed": 779019705,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.750936794409393,
					12.789295491416604
				],
				[
					4.647223577401807,
					30.45286372476331
				],
				[
					7.6316620290339205,
					42.13392494057851
				],
				[
					11.191638272632712,
					52.07593278480534
				],
				[
					19.05639775538872,
					59.92706215329424
				],
				[
					29.74504123309343,
					64.14975077606748
				],
				[
					30.10593539607036,
					63.02282749409215
				],
				[
					20.928782065251678,
					56.70988387561233
				],
				[
					15.209355737256852,
					51.46104992324312
				],
				[
					11.400948639195503,
					42.415204089522156
				],
				[
					1.7064381695443374,
					3.7799850333979563
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 936,
			"versionNonce": 2091002822,
			"isDeleted": false,
			"id": "dHIGPkWDCfRQ34BYHKJMN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -79.73639802732177,
			"y": -9.942684342439335,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 95.51973446364276,
			"height": 69.94081859877498,
			"seed": 115066521,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.230279158599701,
					21.43086606806956
				],
				[
					6.8450979095247595,
					38.13360495165435
				],
				[
					13.649102360617904,
					55.23001642276441
				],
				[
					27.60791332320934,
					64.5500489388144
				],
				[
					51.07845264833334,
					66.4574761576425
				],
				[
					69.5322701726042,
					65.14116021626788
				],
				[
					85.84732696386635,
					60.173634102273894
				],
				[
					86.91342092462273,
					56.18980754016048
				],
				[
					89.77971558672627,
					37.05834787588983
				],
				[
					92.93751644666544,
					23.247137360457458
				],
				[
					95.51973446364276,
					3.223174230490738
				],
				[
					95.23731775461732,
					-3.483342441132475
				]
			]
		},
		{
			"type": "arrow",
			"version": 190,
			"versionNonce": 918281114,
			"isDeleted": false,
			"id": "leHhyCDuUBR2WyN9Ap9rL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 68.36494794480268,
			"y": -62.33448487212996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 322.21080124722357,
			"height": 184.68180071487205,
			"seed": 1492145241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
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
					278.98740107991284,
					17.02740006591018
				],
				[
					322.21080124722357,
					184.68180071487205
				]
			]
		},
		{
			"type": "line",
			"version": 184,
			"versionNonce": 137675526,
			"isDeleted": false,
			"id": "ca160ETK8X2QCyO6TlAY2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1519.0751770755837,
			"y": 792.5039872633392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 260.95298826505507,
			"seed": 676903161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-260.95298826505507
				]
			]
		},
		{
			"type": "line",
			"version": 99,
			"versionNonce": 1420908634,
			"isDeleted": false,
			"id": "yMv6FJ9phYp9_TnoCzfdi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1517.546155659968,
			"y": 682.9241191442244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 128.43779891170675,
			"height": 2.0386952208207276,
			"seed": 753590167,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-128.43779891170675,
					2.0386952208207276
				]
			]
		},
		{
			"type": "line",
			"version": 83,
			"versionNonce": 200438342,
			"isDeleted": false,
			"id": "gr7STI99OOto7sut5T2-Z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1520.6041984911992,
			"y": 652.8533646371185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 156.46985819799215,
			"height": 1.5290214156156026,
			"seed": 2063302841,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					156.46985819799215,
					-1.5290214156156026
				]
			]
		},
		{
			"type": "line",
			"version": 112,
			"versionNonce": 945372442,
			"isDeleted": false,
			"id": "F2NkSGZofnhpZgfuw-N58",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1488.4947487632726,
			"y": 684.45314055984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.0193476104104775,
			"height": 108.05084670349936,
			"seed": 446795865,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.0193476104104775,
					108.05084670349936
				]
			]
		},
		{
			"type": "line",
			"version": 127,
			"versionNonce": 45627782,
			"isDeleted": false,
			"id": "ie8jDYuGLL58A7IqbU3yf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1543.5395197254325,
			"y": 652.8533646371185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5096738052052388,
			"height": 146.2763820938883,
			"seed": 899693113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5096738052052388,
					146.2763820938883
				]
			]
		},
		{
			"type": "freedraw",
			"version": 41,
			"versionNonce": 1327925722,
			"isDeleted": false,
			"id": "lUI2FlR0zlQ9H4XAegQ6_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1535.0475890074151,
			"y": 664.5555581771428,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0,
			"seed": 1609598521,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
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
			"version": 39,
			"versionNonce": 63117510,
			"isDeleted": false,
			"id": "xMB7lJPgEAjVLqfj9pRmP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1544.5590155565283,
			"y": 662.2810866110505,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 324567705,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 43,
			"versionNonce": 1613512346,
			"isDeleted": false,
			"id": "4uTVMnaFMf6Nt_WnB3UoL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1547.6605676921085,
			"y": 667.657110312723,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.8270805694880892,
			"seed": 667680057,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
				],
				[
					0,
					0.6203104271161237
				],
				[
					-0.20677014237207914,
					0.8270805694880892
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
			"version": 37,
			"versionNonce": 917508102,
			"isDeleted": false,
			"id": "-7vH7Q7IruJhskr1Vdoj_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1544.7657856989001,
			"y": 675.721145865232,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 129441047,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 37,
			"versionNonce": 1478318938,
			"isDeleted": false,
			"id": "53DOUuHk7eYtyUhfoNPwj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1539.8033022819716,
			"y": 682.9581008482528,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 142180471,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 37,
			"versionNonce": 1199316806,
			"isDeleted": false,
			"id": "OROk3VDQHVvSFkpAnqVRd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1531.7392667294628,
			"y": 691.4356766855058,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 390733783,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 37,
			"versionNonce": 357359642,
			"isDeleted": false,
			"id": "MSAv00HMViwkGoLfwqOBs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1522.6413804650938,
			"y": 692.6762975397378,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 427981623,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 37,
			"versionNonce": 1518618246,
			"isDeleted": false,
			"id": "EoYGmsZkzQH-M5cIxzoRB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1526.1564728854182,
			"y": 682.5445605635088,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 820777623,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 37,
			"versionNonce": 867028186,
			"isDeleted": false,
			"id": "ilidawQ91Y9t38cvLbb99",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1518.7127477600252,
			"y": 687.3002738380652,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1371563511,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
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
			"version": 42,
			"versionNonce": 8750534,
			"isDeleted": false,
			"id": "3SC-uDnOFVsVT6S6nFQxE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1521.6075297532336,
			"y": 678.2023875736962,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8270805694880892,
			"height": 1.2406208542321338,
			"seed": 413726039,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.20677014237196545
				],
				[
					0.41354028474415827,
					-0.62031042711601
				],
				[
					0.62031042711601,
					-1.0338507118600546
				],
				[
					0.8270805694880892,
					-1.2406208542321338
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
			"version": 41,
			"versionNonce": 1490231706,
			"isDeleted": false,
			"id": "gz4pIcVsJZxrLf5mAHv2Z",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1527.1903235972782,
			"y": 670.3451221635594,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.41354028474415827,
			"height": 0.4135402847440446,
			"seed": 1508699735,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.41354028474415827,
					-0.4135402847440446
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
			"version": 40,
			"versionNonce": 714923270,
			"isDeleted": false,
			"id": "Mfcb4AU5lUUwnCq2yQa8j",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1536.7017501463913,
			"y": 670.1383520211873,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.20677014237207914,
			"seed": 70239799,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					0
				],
				[
					0.20677014237207914,
					0.20677014237207914
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
			"version": 37,
			"versionNonce": 2146426458,
			"isDeleted": false,
			"id": "00A7ariCUwLPyWKQD6afW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1534.220508437927,
			"y": 679.0294681431843,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2058973431,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 507989062,
			"isDeleted": false,
			"id": "EmUQRnNpvDxNR-VogXa-i",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1555.5178331022453,
			"y": 663.7284776076547,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1251598423,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 41,
			"versionNonce": 1171718938,
			"isDeleted": false,
			"id": "Pt9wmTwk4ycjwc-5sewim",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1552.623051109037,
			"y": 680.4768591397885,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.8270805694880892,
			"seed": 204737463,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237196545
				],
				[
					0,
					0.4135402847440446
				],
				[
					-0.20677014237207914,
					0.8270805694880892
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
			"version": 42,
			"versionNonce": 1768018822,
			"isDeleted": false,
			"id": "a2Xu24nXtTvUIVFh8KvIK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1547.2470274073644,
			"y": 693.089837824482,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4135402847439309,
			"height": 1.0338507118600546,
			"seed": 2088742807,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237196545
				],
				[
					-0.20677014237185176,
					0.20677014237196545
				],
				[
					-0.20677014237185176,
					0.4135402847439309
				],
				[
					-0.4135402847439309,
					1.0338507118600546
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
			"version": 43,
			"versionNonce": 888901594,
			"isDeleted": false,
			"id": "KEC3B6-XWLC1u4gZXaxzY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1537.5288307158794,
			"y": 705.0825060820592,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.6541611389761783,
			"height": 1.6541611389761783,
			"seed": 196438167,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237196545
				],
				[
					-0.41354028474415827,
					0.4135402847440446
				],
				[
					-0.62031042711601,
					0.62031042711601
				],
				[
					-0.8270805694880892,
					0.8270805694880892
				],
				[
					-1.24062085423202,
					1.2406208542321338
				],
				[
					-1.6541611389761783,
					1.6541611389761783
				],
				[
					-1.6541611389761783,
					1.6541611389761783
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 44,
			"versionNonce": 1445556934,
			"isDeleted": false,
			"id": "vj-0I-Uw4q3-E4jZKB9nS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1523.0549207498377,
			"y": 714.5939326311723,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.9286327050683667,
			"height": 0.8270805694880892,
			"seed": 460838583,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.62031042711601,
					0.20677014237207914
				],
				[
					-1.033850711859941,
					0.20677014237207914
				],
				[
					-1.6541611389761783,
					0.4135402847440446
				],
				[
					-2.2744715660921884,
					0.8270805694880892
				],
				[
					-2.8947819932081984,
					0.8270805694880892
				],
				[
					-3.5150924203242084,
					0.8270805694880892
				],
				[
					-3.9286327050683667,
					0.8270805694880892
				],
				[
					-3.9286327050683667,
					0.8270805694880892
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 42,
			"versionNonce": 292586650,
			"isDeleted": false,
			"id": "xr23qfRwNRudS5TpXuBv1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1509.4080913532844,
			"y": 715.0074729159163,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.8609312813482575,
			"height": 0.20677014237196545,
			"seed": 500116983,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.41354028474415827,
					0
				],
				[
					-0.8270805694880892,
					0
				],
				[
					-1.0338507118601683,
					0
				],
				[
					-1.4473909966043266,
					0
				],
				[
					-1.8609312813482575,
					-0.20677014237196545
				],
				[
					-1.8609312813482575,
					-0.20677014237196545
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 39,
			"versionNonce": 1597712902,
			"isDeleted": false,
			"id": "DNlk1aNVIzPPOXZw4kWOR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1498.862814092311,
			"y": 706.5298970786633,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237196545,
			"seed": 1087932151,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.20677014237196545
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
			"version": 43,
			"versionNonce": 619241818,
			"isDeleted": false,
			"id": "NiTyJeR4MOHbFxvF81AXG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1503.2049870821236,
			"y": 693.2966079668539,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 1.0338507118600546,
			"seed": 171068567,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.20677014237196545
				],
				[
					0,
					-0.4135402847440446
				],
				[
					0,
					-0.6203104271161237
				],
				[
					0.20677014237207914,
					-0.8270805694880892
				],
				[
					0.20677014237207914,
					-1.0338507118600546
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
			"version": 37,
			"versionNonce": 596900166,
			"isDeleted": false,
			"id": "GWfPelxU4ScU89xT9hGHK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1513.3367240583527,
			"y": 672.4128235872796,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 789854903,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 41,
			"versionNonce": 179807770,
			"isDeleted": false,
			"id": "GZU-Oj49DwjdrSfpwlhmi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1517.6788970481653,
			"y": 663.9352477500266,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8270805694880892,
			"height": 1.0338507118600546,
			"seed": 277611031,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.4135402847440446
				],
				[
					0.4135402847439309,
					-0.62031042711601
				],
				[
					0.8270805694880892,
					-1.0338507118600546
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
			"version": 37,
			"versionNonce": 1519444102,
			"isDeleted": false,
			"id": "2B9rbnwrL7xOX3JrkF7Yr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1499.6898946617991,
			"y": 687.9205842651813,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1677627895,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 43,
			"versionNonce": 2077217498,
			"isDeleted": false,
			"id": "X41fN6p6snIWmtMh95fva",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1504.6523780787277,
			"y": 679.0294681431843,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 1.2406208542321338,
			"seed": 1963368791,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
				],
				[
					-0.20677014237185176,
					0.20677014237207914
				],
				[
					-0.20677014237185176,
					0.4135402847440446
				],
				[
					-0.20677014237185176,
					0.6203104271161237
				],
				[
					-0.62031042711601,
					1.2406208542321338
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
			"version": 40,
			"versionNonce": 1206837190,
			"isDeleted": false,
			"id": "t9Q01Dlm8fhUTf_2HT4_M",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1491.4190889669183,
			"y": 697.6387809566664,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.41354028474415827,
			"height": 0.4135402847440446,
			"seed": 216479607,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.41354028474415827,
					-0.4135402847440446
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
			"version": 39,
			"versionNonce": 449079194,
			"isDeleted": false,
			"id": "gAXmnnHR601JUGNwCsNXe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.2086529533349,
			"y": 674.2737548686279,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0,
			"seed": 1677390391,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
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
			"version": 37,
			"versionNonce": 801830662,
			"isDeleted": false,
			"id": "hOds_v-bi9DjBW51xqqtj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1498.6560439499392,
			"y": 664.9690984618868,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1512681431,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 1070097498,
			"isDeleted": false,
			"id": "SIIHbU1mbHYW91vyTHb6x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1482.5279728449214,
			"y": 687.0935036956932,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4135402847439309,
			"height": 0,
			"seed": 1046920633,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4135402847439309,
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
			"version": 37,
			"versionNonce": 1252140614,
			"isDeleted": false,
			"id": "m8cgxly5gO8DmBpUYkfnb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1503.4117572244957,
			"y": 665.3826387466308,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237196545,
			"seed": 997984793,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237196545
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
			"version": 39,
			"versionNonce": 1152305434,
			"isDeleted": false,
			"id": "dh3IYpa2shfXh5Xlgfkh9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1489.9716979703142,
			"y": 678.4091577160683,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.6203104271161237,
			"seed": 1607834233,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.4135402847439309,
					-0.4135402847440446
				],
				[
					0.62031042711601,
					-0.6203104271161237
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
			"version": 37,
			"versionNonce": 961637766,
			"isDeleted": false,
			"id": "aa3aJIUCdXDTKe8KgJeSF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1511.4757927770045,
			"y": 648.4274870721249,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237207914,
			"seed": 1044106393,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
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
			"version": 38,
			"versionNonce": 1357551066,
			"isDeleted": false,
			"id": "mI55oIHLvCCul78PSsvZy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1512.3028733464926,
			"y": 660.8336956144464,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.6203104271162374,
			"height": 0.4135402847440446,
			"seed": 1978387705,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.6203104271162374,
					-0.4135402847440446
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
			"version": 35,
			"versionNonce": 2031471814,
			"isDeleted": false,
			"id": "rqSGhvwCeqsoaQyhuzMWv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1525.536162458302,
			"y": 644.7056245094285,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1212546617,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 630114970,
			"isDeleted": false,
			"id": "RKgPS44z5Grrwnzd9NRMF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1534.6340487226712,
			"y": 636.4348188145476,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 363044057,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 1468810246,
			"isDeleted": false,
			"id": "9v71Io_moYurWSMn-exHC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1543.938705129412,
			"y": 636.6415889569197,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 303710073,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 1766745946,
			"isDeleted": false,
			"id": "5LSAFy2x_rmBD81DaKmxR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1561.720937373406,
			"y": 643.6717737975684,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.4135402847440446,
			"seed": 446195225,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					0.4135402847440446
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
			"version": 35,
			"versionNonce": 1722929990,
			"isDeleted": false,
			"id": "yfnGgH2asCgcaszb3pUxM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1564.8224895089863,
			"y": 654.2170510585416,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1975023225,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 1954311194,
			"isDeleted": false,
			"id": "tuWCqRcYPUre4vp15xjJM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1564.6157193666145,
			"y": 667.4503401703511,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4135402847440446,
			"seed": 917372185,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4135402847440446
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
			"version": 37,
			"versionNonce": 1893956230,
			"isDeleted": false,
			"id": "P4Hjjki4SkyP43bBMM3fA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1560.273546376802,
			"y": 679.4430084279284,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237207914,
			"seed": 1047506297,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
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
			"version": 37,
			"versionNonce": 487315674,
			"isDeleted": false,
			"id": "B4_svnlz8VDcmThgUheFB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1555.7246032446174,
			"y": 695.3643093905741,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.20677014237207914,
			"seed": 1094132185,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237207914
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
			"version": 39,
			"versionNonce": 1826503110,
			"isDeleted": false,
			"id": "O5IHaN6O1ud7CzAFCXlfT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1551.589200397177,
			"y": 702.1877240888509,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.4135402847440446,
			"seed": 1323948601,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237196545
				],
				[
					-0.4135402847439309,
					0.4135402847440446
				],
				[
					-0.62031042711601,
					0.4135402847440446
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
			"version": 35,
			"versionNonce": 42970522,
			"isDeleted": false,
			"id": "yPP7MC9U2_mixiCA3ag4p",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1542.491314132808,
			"y": 710.2517596413597,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 306791513,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 1908347142,
			"isDeleted": false,
			"id": "RPxl-LRgKeCZN3FCynAs1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1531.9460368718348,
			"y": 716.2480937701484,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.20677014237207914,
			"seed": 1400313593,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237207914
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
			"version": 38,
			"versionNonce": 1513810522,
			"isDeleted": false,
			"id": "kGT-32R5As93-mdupH7fh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1530.9121861599747,
			"y": 701.3606435193628,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.41354028474415827,
			"height": 0.62031042711601,
			"seed": 619486041,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.4135402847440446
				],
				[
					-0.41354028474415827,
					0.62031042711601
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
			"version": 35,
			"versionNonce": 721616966,
			"isDeleted": false,
			"id": "3bEqHCXPLi0vKIdA4j1n8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1516.438276193933,
			"y": 707.5637477905235,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1605403801,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 987795226,
			"isDeleted": false,
			"id": "4nh_PwWnPseDrs4Tt5GJg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1509.4080913532844,
			"y": 701.9809539464788,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.24062085423202,
			"height": 1.2406208542321338,
			"seed": 1011564345,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4135402847439309,
					-0.62031042711601
				],
				[
					1.24062085423202,
					-1.2406208542321338
				],
				[
					1.24062085423202,
					-1.2406208542321338
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 35,
			"versionNonce": 1283917702,
			"isDeleted": false,
			"id": "mOpB2B3cuKz80AKZw6sUg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1536.0814397192753,
			"y": 650.0816482111011,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1658821529,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 1760795610,
			"isDeleted": false,
			"id": "njmRz4Rux1gsX-p-LL7yc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1549.3147288310847,
			"y": 645.5327050789166,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1662891577,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 38,
			"versionNonce": 109586118,
			"isDeleted": false,
			"id": "zuRGX6wRy0TU85gbBYNXI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1533.8069681531829,
			"y": 658.14568376361,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4135402847440446,
			"seed": 905336025,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
				],
				[
					0,
					0.4135402847440446
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
			"version": 38,
			"versionNonce": 579276954,
			"isDeleted": false,
			"id": "uBEkoihFuk9iL6nw-Xkm6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1552.623051109037,
			"y": 653.1832003466815,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.4135402847440446,
			"seed": 998317593,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.41354028474415827,
					0.20677014237196545
				],
				[
					-0.62031042711601,
					0.4135402847440446
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
			"version": 41,
			"versionNonce": 2040749574,
			"isDeleted": false,
			"id": "9Yp6WKGRVq2VkIN104lN4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1524.915852031186,
			"y": 662.2810866110505,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.721862562696515,
			"height": 3.3083222779523567,
			"seed": 825489241,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8270805694880892,
					-0.62031042711601
				],
				[
					1.0338507118601683,
					-0.62031042711601
				],
				[
					1.4473909966040992,
					-1.2406208542321338
				],
				[
					2.0677014237203366,
					-2.067701423720223
				],
				[
					3.515092420324436,
					-3.1015521355802775
				],
				[
					3.721862562696515,
					-3.3083222779523567
				],
				[
					3.721862562696515,
					-3.3083222779523567
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 35,
			"versionNonce": 1800269146,
			"isDeleted": false,
			"id": "VbPfzbDq61DaH7gRqO6fD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1535.8746695769032,
			"y": 622.7879894179941,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 548084537,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 718646598,
			"isDeleted": false,
			"id": "q3WzPlqYicUSfY4xQvs_v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1565.8563402208465,
			"y": 613.4833330112531,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0,
			"seed": 1893849561,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
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
			"version": 37,
			"versionNonce": 1486565914,
			"isDeleted": false,
			"id": "yAqbDqi4g7RXqqhQbiECp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1556.3449136717336,
			"y": 632.9197263942233,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237185176,
			"height": 0,
			"seed": 1155633721,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237185176,
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
			"version": 35,
			"versionNonce": 2004620422,
			"isDeleted": false,
			"id": "QU8_VB1r0QaSgQFEbPEL-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1587.773975312281,
			"y": 619.4796671400418,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 69340825,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 1566695130,
			"isDeleted": false,
			"id": "EWrhVh9g6MmaR0imCy-Kx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1579.916709902144,
			"y": 640.7769918043601,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 32573753,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 156472262,
			"isDeleted": false,
			"id": "9Pm167j9nDg0kKQxPHOlB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1602.2478852783224,
			"y": 639.949911234872,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237185176,
			"height": 0.20677014237196545,
			"seed": 2105968601,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237185176,
					0.20677014237196545
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
			"version": 40,
			"versionNonce": 372568986,
			"isDeleted": false,
			"id": "xJfXM7jQGCNCjO_9IuAye",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1583.8453426072126,
			"y": 667.243570027979,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.6541611389764057,
			"height": 1.0338507118601683,
			"seed": 786006073,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.41354028474415827,
					0.20677014237207914
				],
				[
					-0.8270805694880892,
					0.4135402847440446
				],
				[
					-1.2406208542322474,
					0.6203104271161237
				],
				[
					-1.4473909966043266,
					0.8270805694880892
				],
				[
					-1.6541611389764057,
					1.0338507118601683
				],
				[
					-1.6541611389764057,
					1.0338507118601683
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 38,
			"versionNonce": 1249454854,
			"isDeleted": false,
			"id": "HxP-DLXAZu2ISZbVLb9L_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1569.578202783543,
			"y": 678.6159278584403,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4135402847439309,
			"height": 0,
			"seed": 580581177,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237185176,
					0
				],
				[
					0.4135402847439309,
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
			"version": 35,
			"versionNonce": 357003354,
			"isDeleted": false,
			"id": "9DevHTRZ0luSS-8rtSggT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.0018828109628,
			"y": 742.3011317090234,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2138695097,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 39,
			"versionNonce": 1500109382,
			"isDeleted": false,
			"id": "QPSo7two9aT4b-beUtQLG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1513.5434942007248,
			"y": 730.7220037361901,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.0338507118601683,
			"height": 0.62031042711601,
			"seed": 1496757337,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237196545
				],
				[
					-0.62031042711601,
					0.20677014237196545
				],
				[
					-1.0338507118601683,
					0.62031042711601
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
			"version": 35,
			"versionNonce": 778851610,
			"isDeleted": false,
			"id": "DSJ2v_Nq8M9vbeyAVlTC-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1475.9113282890166,
			"y": 747.2636151259519,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 714523257,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 2097324422,
			"isDeleted": false,
			"id": "yOP5m0HFrp6N29_5fTBvS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1480.8738117059452,
			"y": 731.5490843056782,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1277151513,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 38,
			"versionNonce": 1125556698,
			"isDeleted": false,
			"id": "R52aihUu_pMaH5IEypTYM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1504.2388377939837,
			"y": 727.0001411734936,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.20677014237207914,
			"seed": 1150997433,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0
				],
				[
					-0.62031042711601,
					0.20677014237207914
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
			"version": 35,
			"versionNonce": 411074758,
			"isDeleted": false,
			"id": "mLcmpdVxwOfi6dK0yRv0B",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1463.9186600314392,
			"y": 729.0678425972139,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1160836345,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 240735898,
			"isDeleted": false,
			"id": "IF4AQ5_eSa6YrH4TwKIdB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1473.2233164381803,
			"y": 710.2517596413597,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1008274329,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 528513030,
			"isDeleted": false,
			"id": "mQ2scRNDCAWK3mSiMDkYN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1491.6258591092903,
			"y": 718.5225653362407,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.20677014237207914,
			"seed": 999106105,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.62031042711601,
					-0.20677014237207914
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
			"version": 37,
			"versionNonce": 1894216538,
			"isDeleted": false,
			"id": "jp1AteZX4tv-CWw2XJdzV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1457.5087856179066,
			"y": 713.9736222040563,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 1.6541611389761783,
			"seed": 1775869561,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.6203104271161237
				],
				[
					0.62031042711601,
					-1.6541611389761783
				],
				[
					0.62031042711601,
					-1.6541611389761783
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 37,
			"versionNonce": 167741254,
			"isDeleted": false,
			"id": "7si5MKlD4VO_Xhm-AN1jK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1571.351622446998,
			"y": 596.570613889223,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444431136,
			"seed": 487544441,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
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
			"version": 35,
			"versionNonce": 1024718874,
			"isDeleted": false,
			"id": "i3S19uNg1589lyXdychMG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1542.8068121693111,
			"y": 617.4466691669342,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1508715225,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 42,
			"versionNonce": 1213902470,
			"isDeleted": false,
			"id": "AhK0pGQv16umk2TL112ya",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1561.552657724807,
			"y": 596.570613889223,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888862272,
			"height": 2.1302097222154543,
			"seed": 2028375417,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
				],
				[
					0,
					0.8520838888862272
				],
				[
					0,
					1.2781258333293408
				],
				[
					-0.4260419444431136,
					1.2781258333293408
				],
				[
					-0.4260419444431136,
					1.7041677777723407
				],
				[
					-0.8520838888862272,
					2.1302097222154543
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
			"version": 35,
			"versionNonce": 47310042,
			"isDeleted": false,
			"id": "m_U95E5gqal5DhUS9TC3U",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1585.4110066136197,
			"y": 605.0914527780847,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1816705593,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 927919558,
			"isDeleted": false,
			"id": "eujtu4N-HnOypWlOA69sc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1553.8839027248314,
			"y": 608.9258302780725,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1028643033,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 37,
			"versionNonce": 1538537882,
			"isDeleted": false,
			"id": "JCjJhbzXGoOKif5n-xoMM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1578.5943355025304,
			"y": 634.0623050002146,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444429999,
			"seed": 1541405561,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
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
			"version": 38,
			"versionNonce": 335103238,
			"isDeleted": false,
			"id": "GKM0iJcZnYKAHzDjK14EO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1594.3578874469245,
			"y": 651.5300247223811,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0.4260419444429999,
			"seed": 683061209,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					-0.4260419444431136,
					0.4260419444429999
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
			"version": 35,
			"versionNonce": 921564762,
			"isDeleted": false,
			"id": "uwOjy4SqgKrNNT1GWBbol",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1586.6891324469489,
			"y": 659.1987797223566,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 654391577,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 1876341830,
			"isDeleted": false,
			"id": "sArw_Q4CWA6rM4oHpDpeU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1610.1214393913187,
			"y": 622.9852144446943,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 531776441,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 626137882,
			"isDeleted": false,
			"id": "144dWVdi0MJYC2Xe6LeCh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1603.3047682802294,
			"y": 611.908123889174,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1923338841,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 616840070,
			"isDeleted": false,
			"id": "o-gdi82RQOy25j_AlYmNp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1599.8964327246847,
			"y": 604.6654108336417,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1314028441,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 38,
			"versionNonce": 626239450,
			"isDeleted": false,
			"id": "l9BLNHDIb0bD3JRFYMmDd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1582.8547549469613,
			"y": 588.4758169448044,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0.4260419444431136,
			"seed": 1828492857,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4260419444431136,
					-0.4260419444431136
				],
				[
					-0.4260419444431136,
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
			"version": 35,
			"versionNonce": 1224661702,
			"isDeleted": false,
			"id": "1VGFCZtTbYSOkfoJwwuOY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1569.2214127247826,
			"y": 592.3101944447922,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1392433017,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 1862638746,
			"isDeleted": false,
			"id": "70uKJB3b99tegyWJ_LKzt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1607.56518772466,
			"y": 603.3872850003123,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1047299129,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 38,
			"versionNonce": 589533702,
			"isDeleted": false,
			"id": "sfR0avch9ofl3QGyauz8F",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1512.9838760582952,
			"y": 748.2415461109615,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.8520838888861135,
			"seed": 1599613977,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					0,
					0.8520838888861135
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
			"version": 37,
			"versionNonce": 1075509594,
			"isDeleted": false,
			"id": "S8DtVQh0CZ5vgbcVq6uXX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1502.332827447218,
			"y": 755.4842591664939,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2781258333291134,
			"height": 0.8520838888861135,
			"seed": 401114457,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2781258333291134,
					0.8520838888861135
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
			"version": 37,
			"versionNonce": 506421574,
			"isDeleted": false,
			"id": "hAQlCcr3NsZ_EzkKQOysZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1482.308856058393,
			"y": 764.4311399997987,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0.4260419444431136,
			"seed": 147656121,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4260419444431136,
					-0.4260419444431136
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
			"version": 38,
			"versionNonce": 669433370,
			"isDeleted": false,
			"id": "iWKU7pgkC7nUkq8Ca4SLM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1496.794282169458,
			"y": 752.0759236109492,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.4083355555446815,
			"height": 0.8520838888862272,
			"seed": 737171993,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8520838888862272,
					0.4260419444431136
				],
				[
					-2.5562516666584543,
					0.8520838888862272
				],
				[
					-3.4083355555446815,
					0.8520838888862272
				],
				[
					-3.4083355555446815,
					0.8520838888862272
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 38,
			"versionNonce": 1031751814,
			"isDeleted": false,
			"id": "pw4fRfsaQgtaWgLlPqD_w",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1466.971346058442,
			"y": 758.4665527775956,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888859998,
			"height": 0.4260419444429999,
			"seed": 738603865,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					-0.8520838888859998,
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
			"version": 35,
			"versionNonce": 1398532826,
			"isDeleted": false,
			"id": "GL2m85UiuGiM89PGt3Sj5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1460.1546749473525,
			"y": 748.2415461109615,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 481827993,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910998,
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
			"version": 35,
			"versionNonce": 282085318,
			"isDeleted": false,
			"id": "7WBhKqm1Y_IS2j9uz4Lbc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1454.1900877251494,
			"y": 738.4425813887705,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2109347289,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 37,
			"versionNonce": 1494056858,
			"isDeleted": false,
			"id": "SlB1PiOx79MquJT0NRKfp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1453.7640457807063,
			"y": 727.3654908332503,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444429999,
			"seed": 330782841,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
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
			"version": 35,
			"versionNonce": 675241734,
			"isDeleted": false,
			"id": "GSeNr-PN0L9726I1MP5tO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1455.0421716140356,
			"y": 743.5550847220875,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1565781209,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 38,
			"versionNonce": 86932570,
			"isDeleted": false,
			"id": "UNnam9IFIloCT-_sn-eL0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1458.8765491140234,
			"y": 755.910301110937,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.8520838888861135,
			"seed": 636260217,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					0,
					0.8520838888861135
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
			"version": 33,
			"versionNonce": 139038278,
			"isDeleted": false,
			"id": "ih5qBQaeWoJq4M-I9WBTj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1448.6515424473891,
			"y": 717.9925680555024,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2000046935,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 33,
			"versionNonce": 630317338,
			"isDeleted": false,
			"id": "_fM9q30OnzIaxD5zJUBl-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1470.3796816139866,
			"y": 693.2821352778034,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1476679351,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 33,
			"versionNonce": 499897734,
			"isDeleted": false,
			"id": "ZHOpwblRV75oZCy1XNEaz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1466.119262169556,
			"y": 724.8092391665917,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 530685463,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 1437248986,
			"isDeleted": false,
			"id": "644aA5fARTjW1wQ_9ZYvD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1513.8359599471814,
			"y": 685.1873383333848,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1796470393,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 839070918,
			"isDeleted": false,
			"id": "Af0kHot6MCH4xGhlD9kZC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1509.1494985583074,
			"y": 691.577967500031,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 263814425,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 1250681498,
			"isDeleted": false,
			"id": "1s0wSMW4KKn8uH-tr4H-9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1527.043260224917,
			"y": 688.5956738889295,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1520502713,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 1586277382,
			"isDeleted": false,
			"id": "umavIDGgxKlJSCRjUW-gg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1515.9661696693968,
			"y": 675.3883736111939,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 760813145,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 518553434,
			"isDeleted": false,
			"id": "nf_rp9EYIEi136b2ArVlV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1536.842224947108,
			"y": 672.4060800000923,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 905980153,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 23411526,
			"isDeleted": false,
			"id": "gT9eL-XKAhB6bbllj4_b9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1524.4870085582584,
			"y": 658.3466958334704,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2034548633,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 521372698,
			"isDeleted": false,
			"id": "i31Ptekf0xEtjTs4qOkCr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1530.8776377249048,
			"y": 653.6602344445964,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 476404281,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 820634246,
			"isDeleted": false,
			"id": "WUzT4u2RTC2BXqxkDJ3Cd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1518.5224213360552,
			"y": 655.7904441668119,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1865447641,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 352317658,
			"isDeleted": false,
			"id": "PxjAyd__TWDA-ig4TiOhX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1550.4755671692867,
			"y": 655.7904441668119,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 906271609,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 802660806,
			"isDeleted": false,
			"id": "UzfxEErU6atn28DtFJ-8d",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1533.4338893915633,
			"y": 644.2873116668486,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 869286425,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 36,
			"versionNonce": 339789210,
			"isDeleted": false,
			"id": "ZnV1ADMmszbBYEQ9HicfN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1557.7182802248192,
			"y": 666.867534722332,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 1.704167777772227,
			"seed": 1947331769,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4260419444429999
				],
				[
					0.4260419444431136,
					-0.8520838888861135
				],
				[
					0.4260419444431136,
					-1.2781258333292271
				],
				[
					0.4260419444431136,
					-1.704167777772227
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
			"version": 33,
			"versionNonce": 1632336134,
			"isDeleted": false,
			"id": "YG1IfuUiAkFjpr_XZv9kE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1568.3693288358963,
			"y": 655.7904441668119,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444431136,
			"seed": 255779769,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
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
			"version": 31,
			"versionNonce": 1174995546,
			"isDeleted": false,
			"id": "VeIt1iJTiBdnxZLp2zDJS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1552.179734947059,
			"y": 682.2050447222832,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 41709593,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 35,
			"versionNonce": 1019373638,
			"isDeleted": false,
			"id": "zw_uflM4DOTe6KCMB256_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1551.753693002616,
			"y": 668.5717025001045,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 2.5562516666584543,
			"seed": 80009913,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.8520838888861135
				],
				[
					-0.4260419444431136,
					1.704167777772227
				],
				[
					-0.4260419444431136,
					2.5562516666584543
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
			"version": 31,
			"versionNonce": 892053274,
			"isDeleted": false,
			"id": "BdOk1gqUJyHRQMtQF7lTD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1546.2151477248558,
			"y": 697.9685966666773,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1294062809,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 35,
			"versionNonce": 1108963206,
			"isDeleted": false,
			"id": "MfC8QJrpeaevl96XrQSuc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1545.7891057804127,
			"y": 687.3175480556002,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888859998,
			"height": 2.1302097222154543,
			"seed": 1386444665,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					0,
					1.2781258333292271
				],
				[
					-0.8520838888859998,
					2.1302097222154543
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
			"version": 31,
			"versionNonce": 438023130,
			"isDeleted": false,
			"id": "kUx6NWl-Ml-9S62qWuasT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1535.5640991137789,
			"y": 704.7852677777666,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2041858457,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 1837993670,
			"isDeleted": false,
			"id": "ifc5XUw75_mlVjqqgILaQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1543.2328541137542,
			"y": 696.2644288889051,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 382280761,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 653011098,
			"isDeleted": false,
			"id": "gJK1zaRmnAUjXdhelZE2r",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1509.1494985583074,
			"y": 703.5071419444374,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1559266009,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 37,
			"versionNonce": 733726214,
			"isDeleted": false,
			"id": "HJkDRYn-U9NZsuqTtda_6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1506.1672049472058,
			"y": 694.9863030555757,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2781258333293408,
			"height": 1.7041677777723407,
			"seed": 696837497,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4260419444431136,
					0
				],
				[
					-0.8520838888862272,
					0
				],
				[
					-1.2781258333293408,
					0.4260419444431136
				],
				[
					-1.2781258333293408,
					0.8520838888862272
				],
				[
					-1.2781258333293408,
					1.7041677777723407
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
			"version": 31,
			"versionNonce": 1397753178,
			"isDeleted": false,
			"id": "qeZGOwTKm7sUZPiuPJhy1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1541.9547282804251,
			"y": 697.9685966666773,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 572073305,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 37,
			"versionNonce": 1302402374,
			"isDeleted": false,
			"id": "1P_C6PVcB3k5c3wloj0rG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1505.3151210583196,
			"y": 700.5248483333359,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 4.260419444430681,
			"height": 0.8520838888861135,
			"seed": 1734776825,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8520838888862272,
					0
				],
				[
					-1.704167777772227,
					0.4260419444431136
				],
				[
					-2.982293611101568,
					0.8520838888861135
				],
				[
					-3.4083355555446815,
					0.8520838888861135
				],
				[
					-3.834377499987795,
					0.8520838888861135
				],
				[
					-4.260419444430681,
					0.8520838888861135
				],
				[
					-4.260419444430681,
					0.8520838888861135
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 34,
			"versionNonce": 681200154,
			"isDeleted": false,
			"id": "55Mxr0UIDLJhXtYLkrTW6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.646366058344,
			"y": 691.1519255555879,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.8520838888862272,
			"seed": 53610457,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
				],
				[
					0,
					0.8520838888862272
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
			"version": 33,
			"versionNonce": 2090499206,
			"isDeleted": false,
			"id": "e8y3JnINvKoJpZds8j2BL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1481.4567721695068,
			"y": 711.175896944413,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444431136,
			"seed": 857379097,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4260419444431136
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
			"version": 36,
			"versionNonce": 230553306,
			"isDeleted": false,
			"id": "SHgBSmJz38GrykC8n41FH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1504.8890791138765,
			"y": 680.5008769445109,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.704167777772227,
			"height": 3.4083355555446815,
			"seed": 8372601,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4260419444431136,
					0.4260419444429999
				],
				[
					-0.8520838888862272,
					1.2781258333292271
				],
				[
					-0.8520838888862272,
					2.1302097222154543
				],
				[
					-1.704167777772227,
					2.982293611101568
				],
				[
					-1.704167777772227,
					3.4083355555446815
				],
				[
					-1.704167777772227,
					3.4083355555446815
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 36,
			"versionNonce": 778369990,
			"isDeleted": false,
			"id": "MWtoYgpOKW0xK4AOgxUKI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1490.8296949472547,
			"y": 702.6550580555513,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.7041677777724544,
			"height": 2.1302097222154543,
			"seed": 1694234745,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4260419444431136
				],
				[
					0.4260419444431136,
					-0.4260419444431136
				],
				[
					0.8520838888862272,
					-1.2781258333293408
				],
				[
					1.7041677777724544,
					-2.1302097222154543
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
			"version": 34,
			"versionNonce": 323881882,
			"isDeleted": false,
			"id": "RNIk_qpibLxS9LxFs5x6R",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1496.368240225015,
			"y": 686.8915061111571,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888862272,
			"height": 2.1302097222154543,
			"seed": 1888563065,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
				],
				[
					-0.8520838888862272,
					2.1302097222154543
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
			"version": 33,
			"versionNonce": 421368582,
			"isDeleted": false,
			"id": "WeLgCAKIz55u011qq-Zvh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1495.5161563361287,
			"y": 715.4363163888438,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0,
			"seed": 1226801337,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4260419444431136,
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
			"version": 31,
			"versionNonce": 1065191514,
			"isDeleted": false,
			"id": "tXDKR77E1GtOD1IpNGkSn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1503.1849113361043,
			"y": 718.8446519443885,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 190508313,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 31,
			"versionNonce": 658588230,
			"isDeleted": false,
			"id": "SfQthpujSvBMMR6qvlfsp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1484.4390657806084,
			"y": 702.6550580555513,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 242775993,
			"groupIds": [
				"JYMtkLPt0FgtZe6Q-GZ5y",
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 101,
			"versionNonce": 1512008986,
			"isDeleted": false,
			"id": "Rdi5oYcFD193ph_jNcWoY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1523.0064183802845,
			"y": 658.2357306479367,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0,
			"seed": 2123138585,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
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
			"version": 99,
			"versionNonce": 1806502278,
			"isDeleted": false,
			"id": "TIq-Bj6jLDw6x6kEiTr35",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1532.5178449293974,
			"y": 655.9612590818443,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1462131449,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 103,
			"versionNonce": 950450650,
			"isDeleted": false,
			"id": "63dW2iknM5S8yQN0Hv3Hq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1535.6193970649776,
			"y": 661.337282783517,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.8270805694880892,
			"seed": 728929241,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
				],
				[
					0,
					0.6203104271161237
				],
				[
					-0.20677014237207914,
					0.8270805694880892
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
			"version": 97,
			"versionNonce": 362670278,
			"isDeleted": false,
			"id": "SivrxtRa01FU5q4wk9man",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1532.7246150717694,
			"y": 669.4013183360258,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 528789689,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 170290842,
			"isDeleted": false,
			"id": "iptFZSW_n2kqYGbAPpY2O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1527.7621316548405,
			"y": 676.6382733190468,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 151007641,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 1689313286,
			"isDeleted": false,
			"id": "fp_jfx1eOAcuhPJAuU1o-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1519.698096102332,
			"y": 685.1158491562998,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1025021561,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 592546650,
			"isDeleted": false,
			"id": "jaaC7nGB1P26MXMk9Fbzz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1510.600209837963,
			"y": 686.3564700105318,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 512843609,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 484634438,
			"isDeleted": false,
			"id": "Iau9GnPijnXuYjaTro93P",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1514.1153022582873,
			"y": 676.2247330343026,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1807617081,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 1249579034,
			"isDeleted": false,
			"id": "8pcu1X3p6gHsl1NMVsBqV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1506.6715771328943,
			"y": 680.9804463088591,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1283595545,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 102,
			"versionNonce": 2056328838,
			"isDeleted": false,
			"id": "F3STaaxvq1dBF27FcNhs8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1509.566359126103,
			"y": 671.8825600444901,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8270805694880892,
			"height": 1.2406208542321338,
			"seed": 542183929,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.20677014237196545
				],
				[
					0.41354028474415827,
					-0.62031042711601
				],
				[
					0.62031042711601,
					-1.0338507118600546
				],
				[
					0.8270805694880892,
					-1.2406208542321338
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
			"version": 101,
			"versionNonce": 60161242,
			"isDeleted": false,
			"id": "r4Ie2elDlmaEm9f7PLa9J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1515.1491529701473,
			"y": 664.0252946343531,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.41354028474415827,
			"height": 0.4135402847440446,
			"seed": 204368601,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.41354028474415827,
					-0.4135402847440446
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
			"version": 100,
			"versionNonce": 645420486,
			"isDeleted": false,
			"id": "B5qwEFhyUR185Wj3sh-4t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1524.6605795192602,
			"y": 663.8185244919811,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.20677014237207914,
			"seed": 1219340217,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					0
				],
				[
					0.20677014237207914,
					0.20677014237207914
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
			"version": 97,
			"versionNonce": 1546998170,
			"isDeleted": false,
			"id": "35BpnwsxyOJ9Zfoaj3ZyK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1522.1793378107961,
			"y": 672.7096406139782,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 804407449,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 699772166,
			"isDeleted": false,
			"id": "AKlCMbcTfMJaQIryWjZfl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1543.4766624751144,
			"y": 657.4086500784484,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 196070777,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 101,
			"versionNonce": 931925594,
			"isDeleted": false,
			"id": "cdZ1l1wNYFM8a64bwjwN7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1540.5818804819062,
			"y": 674.1570316105823,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.8270805694880892,
			"seed": 589936217,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237196545
				],
				[
					0,
					0.4135402847440446
				],
				[
					-0.20677014237207914,
					0.8270805694880892
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
			"version": 102,
			"versionNonce": 1640373318,
			"isDeleted": false,
			"id": "fxOLUz3ho0swErqNGMUG8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1535.2058567802335,
			"y": 686.7700102952759,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4135402847439309,
			"height": 1.0338507118600546,
			"seed": 154370873,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237196545
				],
				[
					-0.20677014237185176,
					0.20677014237196545
				],
				[
					-0.20677014237185176,
					0.4135402847439309
				],
				[
					-0.4135402847439309,
					1.0338507118600546
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
			"version": 103,
			"versionNonce": 443364122,
			"isDeleted": false,
			"id": "lMd0XZzqEnS_msglSg6Hh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1525.4876600887485,
			"y": 698.7626785528531,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.6541611389761783,
			"height": 1.6541611389761783,
			"seed": 707834905,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237196545
				],
				[
					-0.41354028474415827,
					0.4135402847440446
				],
				[
					-0.62031042711601,
					0.62031042711601
				],
				[
					-0.8270805694880892,
					0.8270805694880892
				],
				[
					-1.24062085423202,
					1.2406208542321338
				],
				[
					-1.6541611389761783,
					1.6541611389761783
				],
				[
					-1.6541611389761783,
					1.6541611389761783
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 104,
			"versionNonce": 1954980742,
			"isDeleted": false,
			"id": "oYSIhSPuYPmNrA96eSleq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1511.0137501227066,
			"y": 708.2741051019663,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.9286327050683667,
			"height": 0.8270805694880892,
			"seed": 437569785,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.62031042711601,
					0.20677014237207914
				],
				[
					-1.033850711859941,
					0.20677014237207914
				],
				[
					-1.6541611389761783,
					0.4135402847440446
				],
				[
					-2.2744715660921884,
					0.8270805694880892
				],
				[
					-2.8947819932081984,
					0.8270805694880892
				],
				[
					-3.5150924203242084,
					0.8270805694880892
				],
				[
					-3.9286327050683667,
					0.8270805694880892
				],
				[
					-3.9286327050683667,
					0.8270805694880892
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 102,
			"versionNonce": 2001453018,
			"isDeleted": false,
			"id": "1j_j9fPS2J1jy4-zuAPVj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.3669207261535,
			"y": 708.6876453867102,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.8609312813482575,
			"height": 0.20677014237196545,
			"seed": 576930265,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.41354028474415827,
					0
				],
				[
					-0.8270805694880892,
					0
				],
				[
					-1.0338507118601683,
					0
				],
				[
					-1.4473909966043266,
					0
				],
				[
					-1.8609312813482575,
					-0.20677014237196545
				],
				[
					-1.8609312813482575,
					-0.20677014237196545
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 99,
			"versionNonce": 1144275654,
			"isDeleted": false,
			"id": "OpjdEbeiYVFyewy6DWEKt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1486.8216434651802,
			"y": 700.2100695494572,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237196545,
			"seed": 271556281,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.20677014237196545
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
			"version": 103,
			"versionNonce": 2050667674,
			"isDeleted": false,
			"id": "gEq8MNZLPFmlOd6yENoUz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1491.1638164549925,
			"y": 686.9767804376478,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 1.0338507118600546,
			"seed": 1109221273,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.20677014237196545
				],
				[
					0,
					-0.4135402847440446
				],
				[
					0,
					-0.6203104271161237
				],
				[
					0.20677014237207914,
					-0.8270805694880892
				],
				[
					0.20677014237207914,
					-1.0338507118600546
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
			"version": 97,
			"versionNonce": 1668020742,
			"isDeleted": false,
			"id": "xX-6RE4MxCk2sn5mguK-e",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1501.2955534312216,
			"y": 666.0929960580735,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1986004089,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 101,
			"versionNonce": 1424822618,
			"isDeleted": false,
			"id": "xHoLpSWTjM-n_qzqQuTYX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1505.6377264210344,
			"y": 657.6154202208205,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8270805694880892,
			"height": 1.0338507118600546,
			"seed": 1488653657,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.4135402847440446
				],
				[
					0.4135402847439309,
					-0.62031042711601
				],
				[
					0.8270805694880892,
					-1.0338507118600546
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
			"version": 97,
			"versionNonce": 153798982,
			"isDeleted": false,
			"id": "tWqru0HufpE4aKqqSBC2G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1487.648724034668,
			"y": 681.6007567359753,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1350695481,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 103,
			"versionNonce": 179688986,
			"isDeleted": false,
			"id": "d7-suzzuZuv8QIzpgzBSu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1492.611207451597,
			"y": 672.7096406139782,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 1.2406208542321338,
			"seed": 244861721,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
				],
				[
					-0.20677014237185176,
					0.20677014237207914
				],
				[
					-0.20677014237185176,
					0.4135402847440446
				],
				[
					-0.20677014237185176,
					0.6203104271161237
				],
				[
					-0.62031042711601,
					1.2406208542321338
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
			"version": 100,
			"versionNonce": 80588934,
			"isDeleted": false,
			"id": "KSEkNVUaGLVp_IO1yEgvy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1479.3779183397876,
			"y": 691.3189534274603,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.41354028474415827,
			"height": 0.4135402847440446,
			"seed": 1534164985,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.41354028474415827,
					-0.4135402847440446
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
			"version": 99,
			"versionNonce": 1015546586,
			"isDeleted": false,
			"id": "3peyGgdwJBXCxOuoCQcgL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1485.167482326204,
			"y": 667.9539273394217,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0,
			"seed": 621877465,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
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
			"version": 97,
			"versionNonce": 840019910,
			"isDeleted": false,
			"id": "ngHuidm24Dxrhr0-erY4S",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1486.6148733228085,
			"y": 658.6492709326807,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1292539321,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 1962317722,
			"isDeleted": false,
			"id": "0ub8Le0gYCW0TtZ6HwDQ0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1470.4868022177905,
			"y": 680.773676166487,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4135402847439309,
			"height": 0,
			"seed": 914454169,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4135402847439309,
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
			"version": 97,
			"versionNonce": 1830012678,
			"isDeleted": false,
			"id": "qx9s9xxY3egRUHURhSv0u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1491.3705865973645,
			"y": 659.0628112174246,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237196545,
			"seed": 338246521,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237196545
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
			"version": 99,
			"versionNonce": 1949602906,
			"isDeleted": false,
			"id": "BNn_x8U6dZ-07x7z4E_QU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1477.930527343183,
			"y": 672.0893301868622,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.6203104271161237,
			"seed": 1984259161,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.4135402847439309,
					-0.4135402847440446
				],
				[
					0.62031042711601,
					-0.6203104271161237
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
			"version": 97,
			"versionNonce": 105969222,
			"isDeleted": false,
			"id": "TD_kUxkqn6AZUBLC3ZWsD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1499.4346221498738,
			"y": 642.1076595429187,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237207914,
			"seed": 413757753,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
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
			"version": 98,
			"versionNonce": 2081749274,
			"isDeleted": false,
			"id": "JDHGtAHZzmCJYTWE0rnCD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1500.2617027193617,
			"y": 654.5138680852402,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.6203104271162374,
			"height": 0.4135402847440446,
			"seed": 1891164697,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					-0.20677014237207914
				],
				[
					0.6203104271162374,
					-0.4135402847440446
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
			"version": 95,
			"versionNonce": 916864390,
			"isDeleted": false,
			"id": "6XCuRuDXY46fRil1Yaztr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1513.494991831171,
			"y": 638.3857969802224,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2070361849,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 470468058,
			"isDeleted": false,
			"id": "vqrqBihZkHujKA_CFanja",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1522.5928780955403,
			"y": 630.1149912853415,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1261957081,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 96,
			"versionNonce": 324050118,
			"isDeleted": false,
			"id": "rZ3st2SmgS-ZTVS5GN1vY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1531.6615462352552,
			"y": 630.3217614277136,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1446939833,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 2099837594,
			"isDeleted": false,
			"id": "CQGlXffzP_JeGw2nzTni7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1549.6797667462754,
			"y": 637.3519462683622,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.4135402847440446,
			"seed": 69111193,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
					0.4135402847440446
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
			"version": 95,
			"versionNonce": 32314374,
			"isDeleted": false,
			"id": "gp4Kp5cf_NDOuNW4WTRok",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1552.7813188818557,
			"y": 647.8972235293355,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2081124985,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 774018906,
			"isDeleted": false,
			"id": "UZY33TmdVTaKAwxe8UJBb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1552.5745487394836,
			"y": 661.130512641145,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4135402847440446,
			"seed": 852015961,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4135402847440446
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
			"version": 97,
			"versionNonce": 746103622,
			"isDeleted": false,
			"id": "1rP8j_cLTXNYg5pSngojp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1548.2323757496708,
			"y": 673.1231808987224,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.20677014237207914,
			"seed": 950659129,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
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
			"version": 97,
			"versionNonce": 1867160602,
			"isDeleted": false,
			"id": "NM-2_6AroCDh8C1I7rMTm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1543.6834326174865,
			"y": 689.0444818613679,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.20677014237207914,
			"seed": 1200781593,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237207914
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
			"version": 99,
			"versionNonce": 1968196230,
			"isDeleted": false,
			"id": "MW2f2T15tsEJJdHB7xpLi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1539.5480297700462,
			"y": 695.8678965596447,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.4135402847440446,
			"seed": 284552697,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237196545
				],
				[
					-0.4135402847439309,
					0.4135402847440446
				],
				[
					-0.62031042711601,
					0.4135402847440446
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
			"version": 95,
			"versionNonce": 2123630810,
			"isDeleted": false,
			"id": "lRZ6FG4XZFj3iT7r1R6QV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1530.450143505677,
			"y": 703.9319321121535,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1272432345,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 1798375878,
			"isDeleted": false,
			"id": "ftmmyucPfsW4Sx3agRmBe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1519.9048662447042,
			"y": 709.9282662409424,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0.20677014237207914,
			"seed": 46891961,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237207914
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
			"version": 98,
			"versionNonce": 1670503834,
			"isDeleted": false,
			"id": "DO07OPbPih5jVH-X4ofRo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1518.8710155328438,
			"y": 695.0408159901568,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.41354028474415827,
			"height": 0.62031042711601,
			"seed": 569681049,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.4135402847440446
				],
				[
					-0.41354028474415827,
					0.62031042711601
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
			"version": 95,
			"versionNonce": 1027072262,
			"isDeleted": false,
			"id": "Lwz5FomYrdIftI01voBBN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1504.3971055668019,
			"y": 701.2439202613174,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1158064505,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 997661274,
			"isDeleted": false,
			"id": "LrVy7g1YJLNAhImqNZUCg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.3669207261535,
			"y": 695.6611264172726,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.24062085423202,
			"height": 1.2406208542321338,
			"seed": 1162154585,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4135402847439309,
					-0.62031042711601
				],
				[
					1.24062085423202,
					-1.2406208542321338
				],
				[
					1.24062085423202,
					-1.2406208542321338
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 95,
			"versionNonce": 786550854,
			"isDeleted": false,
			"id": "_9CW0CvoGNrGGHMopCPTm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1524.0402690921444,
			"y": 643.7618206818948,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 126050105,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 85376794,
			"isDeleted": false,
			"id": "gfQZj7PRcznLrk9wIu8p2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1537.2735582039538,
			"y": 639.2128775497105,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 170201113,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 98,
			"versionNonce": 202102662,
			"isDeleted": false,
			"id": "xFiCehHQX2OBTeN1CsAfD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1521.765797526052,
			"y": 651.8258562344039,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4135402847440446,
			"seed": 857580793,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20677014237207914
				],
				[
					0,
					0.4135402847440446
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
			"version": 98,
			"versionNonce": 1826868186,
			"isDeleted": false,
			"id": "bqUjX5twufApnB6IM9njf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1540.5818804819062,
			"y": 646.8633728174754,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.4135402847440446,
			"seed": 1576050137,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.41354028474415827,
					0.20677014237196545
				],
				[
					-0.62031042711601,
					0.4135402847440446
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
			"version": 101,
			"versionNonce": 485684934,
			"isDeleted": false,
			"id": "qDesVEZyz6q3o2hCFqT2C",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1512.8746814040553,
			"y": 655.9612590818443,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.721862562696515,
			"height": 3.3083222779523567,
			"seed": 699497145,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8270805694880892,
					-0.62031042711601
				],
				[
					1.0338507118601683,
					-0.62031042711601
				],
				[
					1.4473909966040992,
					-1.2406208542321338
				],
				[
					2.0677014237203366,
					-2.067701423720223
				],
				[
					3.515092420324436,
					-3.1015521355802775
				],
				[
					3.721862562696515,
					-3.3083222779523567
				],
				[
					3.721862562696515,
					-3.3083222779523567
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 95,
			"versionNonce": 418463898,
			"isDeleted": false,
			"id": "outM9UNggBTN5QYJvgskr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1523.8334989497723,
			"y": 616.4681618887881,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 117685145,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 439627270,
			"isDeleted": false,
			"id": "4VVReV6RL0QgitQQrKwbq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1553.8151695937156,
			"y": 607.1635054820468,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237207914,
			"height": 0,
			"seed": 102424697,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237207914,
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
			"version": 97,
			"versionNonce": 1962024282,
			"isDeleted": false,
			"id": "9wOTLK_FUD4nqP7Z1fDka",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1544.3037430446027,
			"y": 626.5998988650173,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237185176,
			"height": 0,
			"seed": 1689938265,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237185176,
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
			"version": 95,
			"versionNonce": 550272326,
			"isDeleted": false,
			"id": "izpPugLnEiYkO_RWUupfT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1575.73280468515,
			"y": 613.1598396108358,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1547032121,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 2117689882,
			"isDeleted": false,
			"id": "uIMHl4JIOrf7tXazVanwQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1567.875539275013,
			"y": 634.457164275154,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 795911961,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 639165574,
			"isDeleted": false,
			"id": "qyx6MLhq9EU6-0EdAYEUZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1590.2067146511915,
			"y": 633.6300837056659,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.20677014237185176,
			"height": 0.20677014237196545,
			"seed": 2027838457,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237185176,
					0.20677014237196545
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
			"version": 100,
			"versionNonce": 263851738,
			"isDeleted": false,
			"id": "_vH2wMUBV_ox2VQOuQUWN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1571.8041719800815,
			"y": 660.9237424987729,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.6541611389764057,
			"height": 1.0338507118601683,
			"seed": 948073689,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.41354028474415827,
					0.20677014237207914
				],
				[
					-0.8270805694880892,
					0.4135402847440446
				],
				[
					-1.2406208542322474,
					0.6203104271161237
				],
				[
					-1.4473909966043266,
					0.8270805694880892
				],
				[
					-1.6541611389764057,
					1.0338507118601683
				],
				[
					-1.6541611389764057,
					1.0338507118601683
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 98,
			"versionNonce": 1809212358,
			"isDeleted": false,
			"id": "-jzpDIOMeTrhwuGd3Gnil",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1557.5370321564121,
			"y": 672.296100329234,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4135402847439309,
			"height": 0,
			"seed": 569405881,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20677014237185176,
					0
				],
				[
					0.4135402847439309,
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
			"version": 95,
			"versionNonce": 772219802,
			"isDeleted": false,
			"id": "_aTFSw4isNE0LLul4yRSJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1484.960712183832,
			"y": 735.9813041798171,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 709612185,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 99,
			"versionNonce": 1948384006,
			"isDeleted": false,
			"id": "BvMI5HS5lk3BhRlLNdBQC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1501.5023235735937,
			"y": 724.4021762069839,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.0338507118601683,
			"height": 0.62031042711601,
			"seed": 1447565177,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0.20677014237196545
				],
				[
					-0.62031042711601,
					0.20677014237196545
				],
				[
					-1.0338507118601683,
					0.62031042711601
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
			"version": 95,
			"versionNonce": 1397989466,
			"isDeleted": false,
			"id": "mCYZ-2v20DCMYeEuT88yi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1463.8701576618857,
			"y": 740.9437875967457,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1210630233,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 1970842182,
			"isDeleted": false,
			"id": "WW-99EJ8Y_FfHFgbIbuaM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1468.8326410788143,
			"y": 725.2292567764722,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 230772025,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 98,
			"versionNonce": 997360922,
			"isDeleted": false,
			"id": "qiSlf-ZW2nugCUGHiSrZf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1492.1976671668529,
			"y": 720.6803136442874,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.20677014237207914,
			"seed": 779435545,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20677014237207914,
					0
				],
				[
					-0.62031042711601,
					0.20677014237207914
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
			"version": 95,
			"versionNonce": 1320644998,
			"isDeleted": false,
			"id": "-MwMZGqrSCytQhxe4eFj7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1451.8774894043083,
			"y": 722.7480150680077,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2033718009,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 802607578,
			"isDeleted": false,
			"id": "E7pPnAS-BiDo2K1Of8iLf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1461.1821458110492,
			"y": 703.9319321121535,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 311249881,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 2065387718,
			"isDeleted": false,
			"id": "VzjhZQwNxKfkVEnIx2YDQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1479.5846884821597,
			"y": 712.2027378070346,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 0.20677014237207914,
			"seed": 1116235961,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.62031042711601,
					-0.20677014237207914
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
			"version": 97,
			"versionNonce": 1402177178,
			"isDeleted": false,
			"id": "MYQaOnQ8ik6j7mkOSpz00",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1445.4676149907757,
			"y": 707.65379467485,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.62031042711601,
			"height": 1.6541611389761783,
			"seed": 46983577,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.6203104271161237
				],
				[
					0.62031042711601,
					-1.6541611389761783
				],
				[
					0.62031042711601,
					-1.6541611389761783
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 97,
			"versionNonce": 104941574,
			"isDeleted": false,
			"id": "pdsCB_unVwFCDiy8x5POV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1559.3104518198672,
			"y": 590.2507863600168,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444431136,
			"seed": 1284394617,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
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
			"version": 95,
			"versionNonce": 1868276570,
			"isDeleted": false,
			"id": "R2-0tQRtN1Sj5YR_ov5mN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1530.76564154218,
			"y": 611.126841637728,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 646977369,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 102,
			"versionNonce": 2512710,
			"isDeleted": false,
			"id": "RuUqdB210Y1ncTKwT1hcM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1549.511487097676,
			"y": 590.2507863600168,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888862272,
			"height": 2.1302097222154543,
			"seed": 1931854905,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
				],
				[
					0,
					0.8520838888862272
				],
				[
					0,
					1.2781258333293408
				],
				[
					-0.4260419444431136,
					1.2781258333293408
				],
				[
					-0.4260419444431136,
					1.7041677777723407
				],
				[
					-0.8520838888862272,
					2.1302097222154543
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
			"version": 95,
			"versionNonce": 1031940122,
			"isDeleted": false,
			"id": "t6wDAbXMjgAAc7hGcuCMO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1573.3698359864886,
			"y": 598.7716252488786,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2117260569,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 1898413702,
			"isDeleted": false,
			"id": "YDjtWEVyuoQiiz4J4FOLW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1541.8427320977005,
			"y": 602.6060027488662,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1261095417,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 905581786,
			"isDeleted": false,
			"id": "vh6kltah7YKUKa3xfnMt4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1566.5531648753997,
			"y": 627.7424774710086,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444429999,
			"seed": 588325593,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
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
			"version": 98,
			"versionNonce": 1308736966,
			"isDeleted": false,
			"id": "xZSkZNHBlXyBGglMpvaPa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1582.3167168197936,
			"y": 645.2101971931748,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0.4260419444429999,
			"seed": 1652121529,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					-0.4260419444431136,
					0.4260419444429999
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
			"version": 95,
			"versionNonce": 1515612570,
			"isDeleted": false,
			"id": "yzEk8aXGmJ9B96BxRzMS7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1574.647961819818,
			"y": 652.8789521931504,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 126288025,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 1808930054,
			"isDeleted": false,
			"id": "k4g6hVMYQG78zv48o3Lk6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1598.0802687641878,
			"y": 616.665386915488,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2146272633,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 30025306,
			"isDeleted": false,
			"id": "olf3mVMDrGsWKZRdsZfyl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1591.2635976530985,
			"y": 605.588296359968,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 921726553,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 1947567174,
			"isDeleted": false,
			"id": "04k696WGqIpDbrMcq0Scd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1587.8552620975536,
			"y": 598.3455833044355,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1667447609,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 98,
			"versionNonce": 623397658,
			"isDeleted": false,
			"id": "cqiqUZGGmk_K4eYWL5NEN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1570.8135843198304,
			"y": 582.1559894155981,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0.4260419444431136,
			"seed": 363424793,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4260419444431136,
					-0.4260419444431136
				],
				[
					-0.4260419444431136,
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
			"version": 95,
			"versionNonce": 1487473542,
			"isDeleted": false,
			"id": "CPsCvtuwaAdt1LtOmkDpp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1557.1802420976517,
			"y": 585.9903669155862,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 95846649,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 719575002,
			"isDeleted": false,
			"id": "lw4aWTt4g7J4Y_0E6r5QL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1595.5240170975292,
			"y": 597.0674574711062,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 554564057,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 98,
			"versionNonce": 1204398790,
			"isDeleted": false,
			"id": "FrUR4lhyp7GXXuspaJby8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1500.9427054311643,
			"y": 741.9217185817553,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.8520838888861135,
			"seed": 1489196729,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					0,
					0.8520838888861135
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
			"version": 97,
			"versionNonce": 856673434,
			"isDeleted": false,
			"id": "my6gs5qxGVtL9AHBnC5Je",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1490.2916568200874,
			"y": 749.1644316372877,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2781258333291134,
			"height": 0.8520838888861135,
			"seed": 796530585,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2781258333291134,
					0.8520838888861135
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
			"version": 97,
			"versionNonce": 538206726,
			"isDeleted": false,
			"id": "1wsW3Ir3CvgoYq0JYYNve",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1470.2676854312624,
			"y": 758.1113124705927,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0.4260419444431136,
			"seed": 124107897,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4260419444431136,
					-0.4260419444431136
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
			"version": 98,
			"versionNonce": 1667180890,
			"isDeleted": false,
			"id": "m0DO5WDI8orZk5JpG6YGh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1484.7531115423274,
			"y": 745.7560960817431,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.4083355555446815,
			"height": 0.8520838888862272,
			"seed": 810141017,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8520838888862272,
					0.4260419444431136
				],
				[
					-2.5562516666584543,
					0.8520838888862272
				],
				[
					-3.4083355555446815,
					0.8520838888862272
				],
				[
					-3.4083355555446815,
					0.8520838888862272
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 98,
			"versionNonce": 1686516038,
			"isDeleted": false,
			"id": "SYg-cTfqYdN-fFSCss0sj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1454.9301754313112,
			"y": 752.1467252483895,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888859998,
			"height": 0.4260419444429999,
			"seed": 897167929,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					-0.8520838888859998,
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
			"version": 95,
			"versionNonce": 858058266,
			"isDeleted": false,
			"id": "Ev1nttkte16VfdZ-M-rqs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1448.1135043202214,
			"y": 741.9217185817553,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1809384217,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 95,
			"versionNonce": 813439110,
			"isDeleted": false,
			"id": "1mUzBrmhFb33FieTICN4W",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1442.1489170980187,
			"y": 732.1227538595643,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1071331321,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 97,
			"versionNonce": 928258778,
			"isDeleted": false,
			"id": "bK7RVT_KNjKfPEaH7WA3F",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1441.7228751535752,
			"y": 721.0456633040441,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444429999,
			"seed": 1132712153,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
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
			"version": 95,
			"versionNonce": 733157318,
			"isDeleted": false,
			"id": "U_UNtKyRauSLhM4SljDP3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1443.001000986905,
			"y": 737.2352571928815,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2087079353,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 98,
			"versionNonce": 1853861786,
			"isDeleted": false,
			"id": "FowOcQBi-eS-rUq4fXaor",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1446.8353784868925,
			"y": 749.5904735817309,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.8520838888861135,
			"seed": 1906716313,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					0,
					0.8520838888861135
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
			"version": 93,
			"versionNonce": 2118659846,
			"isDeleted": false,
			"id": "vDgiuX9YxBDVRmq4q92Xx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1436.6103718202583,
			"y": 711.6727405262963,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2046227321,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 93,
			"versionNonce": 215657562,
			"isDeleted": false,
			"id": "Zxm2Bf89IL7z_cOdKRbSn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1458.3385109868557,
			"y": 686.9623077485973,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1234967641,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 93,
			"versionNonce": 1152933446,
			"isDeleted": false,
			"id": "Zbl_XX_TmeHsoNi0gVrFv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1454.078091542425,
			"y": 718.4894116373856,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1080633657,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 91,
			"versionNonce": 1211633946,
			"isDeleted": false,
			"id": "Sg-t4JznCqBtHM41IZ7b5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1501.7947893200505,
			"y": 678.8675108041786,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2009176601,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 91,
			"versionNonce": 65054086,
			"isDeleted": false,
			"id": "kDUlid--1dLe-dbGAasxC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.1083279311763,
			"y": 685.2581399708248,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 278458105,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 91,
			"versionNonce": 604691930,
			"isDeleted": false,
			"id": "Lmb47XOUoPF2tTSwcwo2p",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1515.0020895977862,
			"y": 682.2758463597235,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1098033113,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 91,
			"versionNonce": 486409414,
			"isDeleted": false,
			"id": "7ZBX_YE0mwx4y82mIhBwJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1503.924999042266,
			"y": 669.0685460819878,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 610419897,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 91,
			"versionNonce": 1030099610,
			"isDeleted": false,
			"id": "MOowHrRFhluRvhRTb23fx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1524.8010543199773,
			"y": 666.086252470886,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1158366617,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249910999,
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
			"version": 91,
			"versionNonce": 1101888518,
			"isDeleted": false,
			"id": "emVjrRS209rpL-a6X8vyP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1512.4458379311275,
			"y": 652.0268683042642,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1856055929,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 385658714,
			"isDeleted": false,
			"id": "4RYib-CGH6oCuI83ZXWaW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1518.8364670977737,
			"y": 647.3404069153904,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 971469657,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 1743522630,
			"isDeleted": false,
			"id": "esGm9miuDWs1u0VdPi8PL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1506.4812507089243,
			"y": 649.4706166376058,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1529978937,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 1696707610,
			"isDeleted": false,
			"id": "D6FmXGlroRulqudVtRYXS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1538.434396542156,
			"y": 649.4706166376058,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 811807001,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 1041674886,
			"isDeleted": false,
			"id": "KBg8sh90qWeBCwjcuX8IF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1521.3927187644324,
			"y": 637.9674841376424,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 250586617,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 96,
			"versionNonce": 1506287834,
			"isDeleted": false,
			"id": "JKEIojohsbruDIGGWOUno",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1545.6771095976885,
			"y": 660.547707193126,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 1.704167777772227,
			"seed": 1373273817,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4260419444429999
				],
				[
					0.4260419444431136,
					-0.8520838888861135
				],
				[
					0.4260419444431136,
					-1.2781258333292271
				],
				[
					0.4260419444431136,
					-1.704167777772227
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
			"version": 93,
			"versionNonce": 518681030,
			"isDeleted": false,
			"id": "c-UuHTCqg41k3AGpQRwLs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1556.3281582087654,
			"y": 649.4706166376058,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444431136,
			"seed": 666319801,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
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
			"version": 91,
			"versionNonce": 1887630746,
			"isDeleted": false,
			"id": "deYz1fFeHVRogpFgq5F2w",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1540.138564319928,
			"y": 675.8852171930772,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 547970201,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 95,
			"versionNonce": 92555526,
			"isDeleted": false,
			"id": "eO5UqyTFdJS94AXW6IbJ8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1539.712522375485,
			"y": 662.2518749708985,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 2.5562516666584543,
			"seed": 2086953337,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.8520838888861135
				],
				[
					-0.4260419444431136,
					1.704167777772227
				],
				[
					-0.4260419444431136,
					2.5562516666584543
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
			"version": 91,
			"versionNonce": 981807706,
			"isDeleted": false,
			"id": "tpOIMUubPsrSrQQ2HlKXH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1534.173977097725,
			"y": 691.648769137471,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 942393945,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 95,
			"versionNonce": 23148614,
			"isDeleted": false,
			"id": "J3waLSabmdmc8VFDt_5cb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1533.7479351532818,
			"y": 680.9977205263941,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888859998,
			"height": 2.1302097222154543,
			"seed": 1557337913,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444429999
				],
				[
					0,
					1.2781258333292271
				],
				[
					-0.8520838888859998,
					2.1302097222154543
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
			"version": 91,
			"versionNonce": 715249434,
			"isDeleted": false,
			"id": "PsZK-GvArBKdkM_SBJy-2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1523.522928486648,
			"y": 698.4654402485604,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 213764121,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 710819718,
			"isDeleted": false,
			"id": "mCZEF-ixW6Bnau3-M455r",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1531.1916834866236,
			"y": 689.944601359699,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1373592825,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 1632363482,
			"isDeleted": false,
			"id": "jdAsmKVZiVdAERnmPf9j2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1497.1083279311763,
			"y": 697.1873144152313,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 733697497,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 97,
			"versionNonce": 347627206,
			"isDeleted": false,
			"id": "NY8xECjMaixKUPpCqurMp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1494.126034320075,
			"y": 688.6664755263697,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2781258333293408,
			"height": 1.7041677777723407,
			"seed": 1566913209,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4260419444431136,
					0
				],
				[
					-0.8520838888862272,
					0
				],
				[
					-1.2781258333293408,
					0.4260419444431136
				],
				[
					-1.2781258333293408,
					0.8520838888862272
				],
				[
					-1.2781258333293408,
					1.7041677777723407
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
			"version": 91,
			"versionNonce": 2023119002,
			"isDeleted": false,
			"id": "B2V0knNEHZ7tjERcG5-9t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1529.9135576532942,
			"y": 691.648769137471,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2072015769,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 97,
			"versionNonce": 1158452742,
			"isDeleted": false,
			"id": "rlf2wlgwx6aLvvPOBxNvI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1493.2739504311887,
			"y": 694.2050208041297,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 4.260419444430681,
			"height": 0.8520838888861135,
			"seed": 977311865,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8520838888862272,
					0
				],
				[
					-1.704167777772227,
					0.4260419444431136
				],
				[
					-2.982293611101568,
					0.8520838888861135
				],
				[
					-3.4083355555446815,
					0.8520838888861135
				],
				[
					-3.834377499987795,
					0.8520838888861135
				],
				[
					-4.260419444430681,
					0.8520838888861135
				],
				[
					-4.260419444430681,
					0.8520838888861135
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 94,
			"versionNonce": 1345598810,
			"isDeleted": false,
			"id": "tLRtOOBunnA8ftsPAFzYq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1485.6051954312131,
			"y": 684.8320980263817,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.8520838888862272,
			"seed": 2070487385,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
				],
				[
					0,
					0.8520838888862272
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
			"version": 93,
			"versionNonce": 609740102,
			"isDeleted": false,
			"id": "pWkXKYg-KgxyBVBm1rz0W",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1469.4156015423762,
			"y": 704.8560694152069,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.4260419444431136,
			"seed": 474844729,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4260419444431136
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
			"version": 96,
			"versionNonce": 1501067802,
			"isDeleted": false,
			"id": "K6VUERblXHjCqXiybpBMF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1492.8479084867456,
			"y": 674.1810494153048,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.704167777772227,
			"height": 3.4083355555446815,
			"seed": 64053017,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4260419444431136,
					0.4260419444429999
				],
				[
					-0.8520838888862272,
					1.2781258333292271
				],
				[
					-0.8520838888862272,
					2.1302097222154543
				],
				[
					-1.704167777772227,
					2.982293611101568
				],
				[
					-1.704167777772227,
					3.4083355555446815
				],
				[
					-1.704167777772227,
					3.4083355555446815
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 96,
			"versionNonce": 1945586822,
			"isDeleted": false,
			"id": "ZGiZ0Sgzvqi0tzw_MEvTS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1478.7885243201238,
			"y": 696.3352305263453,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.7041677777724544,
			"height": 2.1302097222154543,
			"seed": 1885869049,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4260419444431136
				],
				[
					0.4260419444431136,
					-0.4260419444431136
				],
				[
					0.8520838888862272,
					-1.2781258333293408
				],
				[
					1.7041677777724544,
					-2.1302097222154543
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
			"version": 94,
			"versionNonce": 1666590426,
			"isDeleted": false,
			"id": "n1xyDKHdxtDLrS0ggJOQy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1484.3270695978838,
			"y": 680.571678581951,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8520838888862272,
			"height": 2.1302097222154543,
			"seed": 102051033,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4260419444431136
				],
				[
					-0.8520838888862272,
					2.1302097222154543
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
			"version": 93,
			"versionNonce": 1101515718,
			"isDeleted": false,
			"id": "aWPEGKnlV8dwHufnwUDOl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1483.4749857089976,
			"y": 709.1164888596378,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.4260419444431136,
			"height": 0,
			"seed": 476850617,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4260419444431136,
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
			"version": 91,
			"versionNonce": 1717582746,
			"isDeleted": false,
			"id": "XwpLttWmr6L_IEWTIEIVY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1491.1437407089736,
			"y": 712.5248244151823,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1284541081,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 91,
			"versionNonce": 1535533830,
			"isDeleted": false,
			"id": "hJwficvmEsHl4hr84nVWR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 2,
			"opacity": 50,
			"angle": 0,
			"x": 1472.3978951534775,
			"y": 696.3352305263453,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1060491129,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
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
			"version": 60,
			"versionNonce": 1355397210,
			"isDeleted": false,
			"id": "mx-WSM7_eY8gVL74JJd9M",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1541.8353579791728,
			"y": 674.219419580489,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.11277198984999,
			"height": 0.9476517732018692,
			"seed": 2052318039,
			"groupIds": [
				"eMuvbiEkvQ6hI0N_Js_8k"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-25.11277198984999,
					0.9476517732018692
				]
			]
		},
		{
			"type": "ellipse",
			"version": 2014,
			"versionNonce": 1141903942,
			"isDeleted": false,
			"id": "y6CQu7BSYI_qs10TVVSS7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 529.3726066958159,
			"y": 974.0894308702798,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 47.74091292270944,
			"height": 43.940952628271475,
			"seed": 1258879961,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2078,
			"versionNonce": 1382391066,
			"isDeleted": false,
			"id": "kdY3sKBwCrPdWa-2U8Glv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 551.2777141245836,
			"y": 1017.7859334492993,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 2.3425637579829472,
			"height": 53.270972786497396,
			"seed": 1343101113,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.3425637579829472,
					53.270972786497396
				]
			]
		},
		{
			"type": "line",
			"version": 2032,
			"versionNonce": 639752582,
			"isDeleted": false,
			"id": "JOhZX41Cxoe6r9vm3XOJW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 548.4846125516148,
			"y": 1073.194502972079,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 21.087544363369275,
			"height": 32.487425246683145,
			"seed": 874289561,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.087544363369275,
					32.487425246683145
				]
			]
		},
		{
			"type": "line",
			"version": 2036,
			"versionNonce": 682027482,
			"isDeleted": false,
			"id": "zm1RLBPkBNqWWzLDi6k0T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 547.8279122290845,
			"y": 1072.2631003654094,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 20.301991719673605,
			"height": 27.813659011267443,
			"seed": 409468537,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.301991719673605,
					27.813659011267443
				]
			]
		},
		{
			"type": "line",
			"version": 1985,
			"versionNonce": 1224259782,
			"isDeleted": false,
			"id": "AIgvnjXihNTv-4YPFKwug",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 530.1659015068724,
			"y": 1028.2574762772726,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 20.484021257782057,
			"height": 19.66144161757433,
			"seed": 733202265,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.484021257782057,
					19.66144161757433
				]
			]
		},
		{
			"type": "line",
			"version": 2005,
			"versionNonce": 1788911258,
			"isDeleted": false,
			"id": "fHrFzEGHADE28jFJ73Ae8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 552.3240143367673,
			"y": 1048.0625697944413,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 29.51898567549869,
			"height": 16.648296631161145,
			"seed": 2018735161,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.51898567549869,
					-16.648296631161145
				]
			]
		},
		{
			"type": "line",
			"version": 2025,
			"versionNonce": 70365190,
			"isDeleted": false,
			"id": "f8pQuFQAQPjEb4izOkB4f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 521.7192023142178,
			"y": 978.2572402781441,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 68.59256278317874,
			"height": 13.955110380026658,
			"seed": 1915389209,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					68.59256278317874,
					13.955110380026658
				]
			]
		},
		{
			"type": "rectangle",
			"version": 2457,
			"versionNonce": 1426439002,
			"isDeleted": false,
			"id": "Bn-dPvT_hHeGv7rIB6kiN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.1875122815022081,
			"x": 543.5502620906807,
			"y": 933.6755399314159,
			"strokeColor": "#000000",
			"backgroundColor": "#fff",
			"width": 35.3600290649305,
			"height": 49.698488904209356,
			"seed": 1152154105,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1715,
			"versionNonce": 868859718,
			"isDeleted": false,
			"id": "aJjnIVsHkdRTiMOwD7wAR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 553.4667339109999,
			"y": 1005.6352172173836,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 57.51080144618725,
			"height": 13.444159916387159,
			"seed": 1625084633,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.356210576866463,
					6.538148547443978
				],
				[
					24.300577259953197,
					5.907059440338917
				],
				[
					29.6090928593852,
					2.179382849148027
				],
				[
					25.778302347029165,
					10.988471214646433
				],
				[
					17.049370845409715,
					11.496939381251888
				],
				[
					-0.17506806764109226,
					7.062966172782695
				],
				[
					-17.82870611426276,
					9.451622093716889
				],
				[
					-27.901708586802055,
					-1.9472205351352707
				],
				[
					-17.817411400221438,
					4.124968438409942
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1075,
			"versionNonce": 371802138,
			"isDeleted": false,
			"id": "GVH7V6BLulfdgeuhM_G_l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 534.5517375090266,
			"y": 987.6211879669823,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.640259369965662,
			"height": 12.454509569443015,
			"seed": 1263472569,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 915,
			"versionNonce": 740157062,
			"isDeleted": false,
			"id": "9a46_ZMuAElwu2SOwB7Jy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 541.6489121745805,
			"y": 992.5332597292685,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.8160135323460346,
			"height": 1.0715329212624702,
			"seed": 707178649,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 916,
			"versionNonce": 436088026,
			"isDeleted": false,
			"id": "ZhAs9_mt9N-N1iont0O4y",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 563.1166621240368,
			"y": 994.3837146586795,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.824256093278823,
			"height": 1.4012353585739992,
			"seed": 320288121,
			"groupIds": [
				"WMJZf8LzcHxaN81-2xx_1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 2987,
			"versionNonce": 770385350,
			"isDeleted": false,
			"id": "en0ks7RUHD9cx4ceNrbD5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 972.0811449475226,
			"y": 238.10942964293542,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 37.04697027407043,
			"height": 40.651504232204545,
			"seed": 141424441,
			"groupIds": [
				"ixJNPiME1coviqsFgq4aK",
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2962,
			"versionNonce": 1444381082,
			"isDeleted": false,
			"id": "j1r8GD5Ej7OSx5pYkrYhM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 985.2022741410892,
			"y": 279.0736012995074,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 2.0875659446637718,
			"height": 47.47220571872788,
			"seed": 1107077145,
			"groupIds": [
				"ixJNPiME1coviqsFgq4aK",
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.0875659446637718,
					47.47220571872788
				]
			]
		},
		{
			"type": "line",
			"version": 2969,
			"versionNonce": 1515093254,
			"isDeleted": false,
			"id": "6DVW4RbNxtJIOQ6rpLKjb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 982.7852435794014,
			"y": 325.96993041468437,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 12.952000898428516,
			"height": 26.429182597176492,
			"seed": 1010973945,
			"groupIds": [
				"ixJNPiME1coviqsFgq4aK",
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.952000898428516,
					26.429182597176492
				]
			]
		},
		{
			"type": "line",
			"version": 2942,
			"versionNonce": 363347546,
			"isDeleted": false,
			"id": "nFjQlT0TsdJqr5aUa377X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 982.1409804338938,
			"y": 324.9979686573723,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 20.868343625895054,
			"height": 23.90340597241749,
			"seed": 113391065,
			"groupIds": [
				"ixJNPiME1coviqsFgq4aK",
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.868343625895054,
					23.90340597241749
				]
			]
		},
		{
			"type": "line",
			"version": 2866,
			"versionNonce": 650439750,
			"isDeleted": false,
			"id": "SqH_nDcJ7FFnWGUAOrfDT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 965.8424193705301,
			"y": 285.3267834811997,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 18.254250302384257,
			"height": 17.521211879067213,
			"seed": 1955599033,
			"groupIds": [
				"ixJNPiME1coviqsFgq4aK",
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.254250302384257,
					17.521211879067213
				]
			]
		},
		{
			"type": "line",
			"version": 2894,
			"versionNonce": 1166238490,
			"isDeleted": false,
			"id": "BT6HtS8aODyipdIpjz76P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 982.7257159973589,
			"y": 301.67392223232133,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 26.305721245448133,
			"height": 14.836060263221073,
			"seed": 709841817,
			"groupIds": [
				"ixJNPiME1coviqsFgq4aK",
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.305721245448133,
					-14.836060263221073
				]
			]
		},
		{
			"type": "line",
			"version": 3068,
			"versionNonce": 1361802118,
			"isDeleted": false,
			"id": "zvaXyYri4tbRNbx_FjShO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 976.060873016341,
			"y": 242.03957648871312,
			"strokeColor": "#000000",
			"backgroundColor": "#4c6ef5",
			"width": 57.96522282094665,
			"height": 21.582083962356627,
			"seed": 1815312505,
			"groupIds": [
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.96227128786686,
					-16.542109928865568
				],
				[
					32.89145861969144,
					-0.05147185039389543
				],
				[
					31.035330151256474,
					2.7520609614160847
				],
				[
					29.605936518748273,
					5.039974033491062
				],
				[
					-24.793479978528396,
					2.2392897996773575
				],
				[
					-25.073764201255205,
					-1.0762112685375433
				],
				[
					0.595175681679317,
					-0.281354017166153
				]
			]
		},
		{
			"type": "line",
			"version": 2239,
			"versionNonce": 1075572698,
			"isDeleted": false,
			"id": "xgVhItI9vDsuys-pyXd18",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 993.6685049967532,
			"y": 227.4418034406333,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 39.78584099020641,
			"height": 17.161787312837635,
			"seed": 738197849,
			"groupIds": [
				"DuXlDU1fFvOYg6q_QIXtR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.4257766602096669,
					-8.496858789272117
				],
				[
					-11.290551261524852,
					-8.509930879717139
				],
				[
					-17.062812913753326,
					-17.161787312837635
				],
				[
					11.632293054587992,
					-3.901085277096611
				],
				[
					22.723028076453083,
					-9.977739892545248
				],
				[
					1.139139310210116,
					-7.720003128538587
				]
			]
		},
		{
			"type": "arrow",
			"version": 325,
			"versionNonce": 1405031110,
			"isDeleted": false,
			"id": "1sWpd2G7E_3viZNXfOdzF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -135.78636525005263,
			"y": -61.88513959518191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 322.21080124722357,
			"height": 184.68180071487205,
			"seed": 297934841,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
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
					-278.98740107991284,
					17.02740006591018
				],
				[
					-322.21080124722357,
					184.68180071487205
				]
			]
		},
		{
			"type": "ellipse",
			"version": 420,
			"versionNonce": 428139674,
			"isDeleted": false,
			"id": "Dg1wNjkRY3o4jM4JND03o",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -361.18347270686195,
			"y": 174.273392304941,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.10632904181001,
			"height": 66.05129327639587,
			"seed": 1230303927,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "0YMW_JWDFhg4mTAhHt5E6",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "hrYuHzDj"
				},
				{
					"id": "VFaXJZBVSjgcM4GUfupoz",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 448,
			"versionNonce": 1495058950,
			"isDeleted": false,
			"id": "hrYuHzDj",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -336.6993594683636,
			"y": 199.37839897458264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.737014770507812,
			"height": 16.13596255523171,
			"seed": 1649513815,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "X1>t",
			"rawText": "X1>t",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Dg1wNjkRY3o4jM4JND03o",
			"originalText": "X1>t",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "arrow",
			"version": 1172,
			"versionNonce": 925318,
			"isDeleted": false,
			"id": "VFaXJZBVSjgcM4GUfupoz",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -300.0400286486214,
			"y": 232.28925182311616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 51.7820568026375,
			"height": 59.029944178364644,
			"seed": 676727993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250042772,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "n1Q0nYIQU-I0dQ5nlWcF1",
				"gap": 1.636170642687098,
				"focus": 0.30210318245444495
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
					51.7820568026375,
					59.029944178364644
				]
			]
		},
		{
			"type": "arrow",
			"version": 1082,
			"versionNonce": 964887046,
			"isDeleted": false,
			"id": "0YMW_JWDFhg4mTAhHt5E6",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -350.43753636260715,
			"y": 232.79781921473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.67759395905682,
			"height": 58.01639093858512,
			"seed": 328881433,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250042773,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Dg1wNjkRY3o4jM4JND03o",
				"gap": 1.7001860642365543,
				"focus": 0.21595920928545495
			},
			"endBinding": {
				"elementId": "hYra-vQn6_aQB1sWi-Xxn",
				"gap": 6.142266316070582,
				"focus": -0.15020991781675141
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
					-38.67759395905682,
					58.01639093858512
				]
			]
		},
		{
			"type": "text",
			"version": 462,
			"versionNonce": 557057562,
			"isDeleted": false,
			"id": "mNvnm7ps",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.9378945530863785,
			"x": -276.3015268039252,
			"y": 233.64019342983516,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 20.096420288085938,
			"height": 16.13596255523171,
			"seed": 1207030297,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "yes",
			"rawText": "yes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "yes",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 411,
			"versionNonce": 1082818694,
			"isDeleted": false,
			"id": "yUVnRPdz",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.301432088659821,
			"x": -382.4009502596498,
			"y": 238.9543618231454,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 15.442901611328125,
			"height": 16.13596255523171,
			"seed": 599841463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "No",
			"rawText": "No",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "ellipse",
			"version": 462,
			"versionNonce": 1136669402,
			"isDeleted": false,
			"id": "n1Q0nYIQU-I0dQ5nlWcF1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -271.2068890343332,
			"y": 290.57005501054545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.10632904181001,
			"height": 66.05129327639587,
			"seed": 994154103,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "uZvRPFinFno_NZVIA4VDv",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "Sx12qaSb"
				},
				{
					"id": "VFaXJZBVSjgcM4GUfupoz",
					"type": "arrow"
				},
				{
					"id": "uOpAOfy6uyItUcD6Zr-ht",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 519,
			"versionNonce": 2108981190,
			"isDeleted": false,
			"id": "Sx12qaSb",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -253.9543889550145,
			"y": 315.67506168018707,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.20024108886719,
			"height": 16.13596255523171,
			"seed": 1507176343,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "X2>t3",
			"rawText": "X2>t3",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "n1Q0nYIQU-I0dQ5nlWcF1",
			"originalText": "X2>t3",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "arrow",
			"version": 1215,
			"versionNonce": 459722502,
			"isDeleted": false,
			"id": "uOpAOfy6uyItUcD6Zr-ht",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -208.76391034181032,
			"y": 353.2076695436979,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 46.74263071310233,
			"height": 56.51084281948596,
			"seed": 2093589687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250042773,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "n1Q0nYIQU-I0dQ5nlWcF1",
				"gap": 4.422908614624227,
				"focus": -0.019473292659539496
			},
			"endBinding": {
				"elementId": "iQ5Q68cglMhb1oZR7Ibac",
				"gap": 1.408155210064244,
				"focus": 0.34468159737399645
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
					46.74263071310233,
					56.51084281948596
				]
			]
		},
		{
			"type": "arrow",
			"version": 1159,
			"versionNonce": 258012998,
			"isDeleted": false,
			"id": "uZvRPFinFno_NZVIA4VDv",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -260.4607364354406,
			"y": 349.0912457388797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.282490364322143,
			"height": 66.09323681651455,
			"seed": 1136784855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250042772,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "n1Q0nYIQU-I0dQ5nlWcF1",
				"gap": 1.6975521302164367,
				"focus": 0.39975130717016927
			},
			"endBinding": {
				"elementId": "ZoP8890j",
				"gap": 6.538833383236351,
				"focus": -0.31829493888297616
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
					-27.282490364322143,
					66.09323681651455
				]
			]
		},
		{
			"type": "text",
			"version": 464,
			"versionNonce": 1327547482,
			"isDeleted": false,
			"id": "Cpguv1B8",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.9378945530863785,
			"x": -178.9787603222233,
			"y": 351.6321290914026,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 20.096420288085938,
			"height": 16.13596255523171,
			"seed": 1708335863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uOpAOfy6uyItUcD6Zr-ht",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "yes",
			"rawText": "yes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "yes",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 473,
			"versionNonce": 1132447302,
			"isDeleted": false,
			"id": "rM6UBj9T",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.301432088659821,
			"x": -285.076457252659,
			"y": 360.39456106287344,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 15.442901611328125,
			"height": 16.13596255523171,
			"seed": 1132571671,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "No",
			"rawText": "No",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "ellipse",
			"version": 442,
			"versionNonce": 167455002,
			"isDeleted": false,
			"id": "hYra-vQn6_aQB1sWi-Xxn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -443.5884548807487,
			"y": 293.6300828066355,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.10632904181001,
			"height": 66.05129327639587,
			"seed": 1431074233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "v1WRglRRgm9Oj7gY8lqju",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "vJFzlbTM"
				},
				{
					"id": "0YMW_JWDFhg4mTAhHt5E6",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 481,
			"versionNonce": 91950470,
			"isDeleted": false,
			"id": "vJFzlbTM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -426.5357533854144,
			"y": 318.73508947627715,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.59983825683594,
			"height": 16.13596255523171,
			"seed": 461854361,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "X2>t2",
			"rawText": "X2>t2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hYra-vQn6_aQB1sWi-Xxn",
			"originalText": "X2>t2",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "arrow",
			"version": 892,
			"versionNonce": 1839920602,
			"isDeleted": false,
			"id": "QkIKZXa-e5WtaB4b-LvQk",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -386.45552983864275,
			"y": 354.4032400584595,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.655208141622552,
			"height": 65.06301420618468,
			"seed": 494082937,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "UFrm0c1V",
				"focus": 0.432455435702192,
				"gap": 4.3669114839491385
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
					25.655208141622552,
					65.06301420618468
				]
			]
		},
		{
			"type": "arrow",
			"version": 1084,
			"versionNonce": 1866443654,
			"isDeleted": false,
			"id": "v1WRglRRgm9Oj7gY8lqju",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -432.8410517863334,
			"y": 352.15230959118367,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.671527081184195,
			"height": 58.00729062177629,
			"seed": 2069054553,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250042773,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hYra-vQn6_aQB1sWi-Xxn",
				"gap": 1.6975521911340365,
				"focus": 0.21595920928545803
			},
			"endBinding": {
				"elementId": "bkUIyli5",
				"gap": 5.234166295782643,
				"focus": -0.14721888382226217
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
					-38.671527081184195,
					58.00729062177629
				]
			]
		},
		{
			"type": "text",
			"version": 448,
			"versionNonce": 188951194,
			"isDeleted": false,
			"id": "dUluLXl6",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.9378945530863785,
			"x": -376.0526911263404,
			"y": 364.63388241300487,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 20.096420288085938,
			"height": 16.13596255523171,
			"seed": 16470329,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "yes",
			"rawText": "yes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "yes",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 434,
			"versionNonce": 500032518,
			"isDeleted": false,
			"id": "uKq3mIlC",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.301432088659821,
			"x": -464.8059324335368,
			"y": 358.3110523248399,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 15.442901611328125,
			"height": 16.13596255523171,
			"seed": 869188121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "No",
			"rawText": "No",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "ellipse",
			"version": 440,
			"versionNonce": 1500956506,
			"isDeleted": false,
			"id": "iQ5Q68cglMhb1oZR7Ibac",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -187.72757613421822,
			"y": 409.59405354558953,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.10632904181001,
			"height": 66.05129327639587,
			"seed": 1072003513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "f-s39td0l5MY6R-qhymop",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "37JLJ7ox"
				},
				{
					"id": "uOpAOfy6uyItUcD6Zr-ht",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 469,
			"versionNonce": 868184902,
			"isDeleted": false,
			"id": "37JLJ7ox",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -167.3684476369308,
			"y": 434.69906021523116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.98698425292969,
			"height": 16.13596255523171,
			"seed": 1415568025,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "X1>t4",
			"rawText": "X1>t4",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "iQ5Q68cglMhb1oZR7Ibac",
			"originalText": "X1>t4",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "arrow",
			"version": 996,
			"versionNonce": 10013722,
			"isDeleted": false,
			"id": "weAbuGThtSoy7Fxf4B9a5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -125.40721094738888,
			"y": 467.0533086722103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 43.44398245233055,
			"height": 63.23337979726424,
			"seed": 815472505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2m6eY7tD",
				"focus": 1.6764107864627038,
				"gap": 15.55074736122532
			},
			"endBinding": {
				"elementId": "yoIO4wex",
				"focus": 0.23762798251355002,
				"gap": 6.21245713112512
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
					43.44398245233055,
					63.23337979726424
				]
			]
		},
		{
			"type": "arrow",
			"version": 1078,
			"versionNonce": 1992472710,
			"isDeleted": false,
			"id": "f-s39td0l5MY6R-qhymop",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -176.85788197126075,
			"y": 468.217169122123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.228727164405285,
			"height": 57.906401829790866,
			"seed": 1926940761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250042773,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "iQ5Q68cglMhb1oZR7Ibac",
				"gap": 1.6975644471150986,
				"focus": 0.2159592092854537
			},
			"endBinding": {
				"elementId": "6d09SLWN",
				"gap": 5.7339050667679885,
				"focus": -0.2454076614099012
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
					-38.228727164405285,
					57.906401829790866
				]
			]
		},
		{
			"type": "text",
			"version": 419,
			"versionNonce": 647772378,
			"isDeleted": false,
			"id": "2m6eY7tD",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.9378945530863785,
			"x": -109.62672205513377,
			"y": 471.7863095970888,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 20.096420288085938,
			"height": 16.13596255523171,
			"seed": 619861305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "weAbuGThtSoy7Fxf4B9a5",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "yes",
			"rawText": "yes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "yes",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 431,
			"versionNonce": 1258543558,
			"isDeleted": false,
			"id": "id5wt6yT",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.301432088659821,
			"x": -208.37996270168526,
			"y": 474.2750230637939,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 15.442901611328125,
			"height": 16.13596255523171,
			"seed": 1246053913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 12.908770044185369,
			"fontFamily": 1,
			"text": "No",
			"rawText": "No",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 289,
			"versionNonce": 991169946,
			"isDeleted": false,
			"id": "bkUIyli5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -496.2812341942732,
			"y": 415.3937665087426,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 26.572113037109375,
			"height": 35,
			"seed": 1550005817,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "v1WRglRRgm9Oj7gY8lqju",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "R1",
			"rawText": "R1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "R1",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 976269574,
			"isDeleted": false,
			"id": "UFrm0c1V",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -383.0377614396441,
			"y": 423.83316574859333,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 38.920166015625,
			"height": 35,
			"seed": 1886245305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QkIKZXa-e5WtaB4b-LvQk",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "R2",
			"rawText": "R2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "R2",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 1127434842,
			"isDeleted": false,
			"id": "ZoP8890j",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -308.33705002104784,
			"y": 421.7233159386306,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 38.05216979980469,
			"height": 35,
			"seed": 922942295,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uZvRPFinFno_NZVIA4VDv",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "R3",
			"rawText": "R3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "R3",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 274,
			"versionNonce": 876650566,
			"isDeleted": false,
			"id": "6d09SLWN",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -241.51376086126828,
			"y": 531.8574760186818,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 36.90415954589844,
			"height": 35,
			"seed": 1904210649,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "f-s39td0l5MY6R-qhymop",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "R4",
			"rawText": "R4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "R4",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 634187546,
			"isDeleted": false,
			"id": "yoIO4wex",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -90.98445573469968,
			"y": 536.4991456005996,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 36.28816223144531,
			"height": 35,
			"seed": 1971124919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "weAbuGThtSoy7Fxf4B9a5",
					"type": "arrow"
				}
			],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "R5",
			"rawText": "R5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "R5",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 896,
			"versionNonce": 487630726,
			"isDeleted": false,
			"id": "fI-lA9NO2k3uWcCVnY8a7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4043184601958,
			"y": 211.9209116165977,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1482784185,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 926,
			"versionNonce": 2001992666,
			"isDeleted": false,
			"id": "xTR1FuMJc7wq2uwLjfugk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4250980343954,
			"y": 276.2888592282836,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 112942745,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 946,
			"versionNonce": 1423820486,
			"isDeleted": false,
			"id": "cXKwr75lwV2b2_2UtZh4D",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3835388859966,
			"y": 222.64890288521198,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 350626681,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 981,
			"versionNonce": 1172009114,
			"isDeleted": false,
			"id": "SRyNUir8wHtY6kaYTlU7k",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3835388859966,
			"y": 287.01685049689786,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 522538073,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 973,
			"versionNonce": 742718982,
			"isDeleted": false,
			"id": "ZmquY-xXgF6bwAhcOIpZS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3627593117967,
			"y": 233.37689415382633,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 1833720121,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1000,
			"versionNonce": 1695960410,
			"isDeleted": false,
			"id": "kJeEYD9J4SeOLpqhu_alU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4043184601958,
			"y": 297.74484176551226,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 12503577,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1013,
			"versionNonce": 1480805702,
			"isDeleted": false,
			"id": "jaMJf-jARDy7TWlcBSJ_F",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3835388859966,
			"y": 244.10488542244073,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1651515129,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1023,
			"versionNonce": 978817562,
			"isDeleted": false,
			"id": "CubmXEHaErg6FDTPNApsJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4043184601958,
			"y": 308.4728330341265,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 820238297,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1004,
			"versionNonce": 1714795654,
			"isDeleted": false,
			"id": "VFCqLhoINmWp6Rqe-Jw0p",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3835388859966,
			"y": 254.83287669105496,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1848472761,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1025,
			"versionNonce": 143802074,
			"isDeleted": false,
			"id": "Pm-WWjlzheJfw9b3CsEch",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3916091147298,
			"y": 319.20082430274084,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 233862553,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 992,
			"versionNonce": 802763718,
			"isDeleted": false,
			"id": "GTDAdhxG0lFNLrMQHlD0V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3835388859966,
			"y": 265.5608679596693,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1130388089,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1420,
			"versionNonce": 1012487066,
			"isDeleted": false,
			"id": "mn7QpCxrElTM7cxv7BZJf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -879.6695435801671,
			"y": 265.54478051941237,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 255894361,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1167,
			"versionNonce": 1330301702,
			"isDeleted": false,
			"id": "ns4vYjefSEL0433G6umXl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -944.0489686246146,
			"y": 265.55625795217406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 233099321,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1182,
			"versionNonce": 937414746,
			"isDeleted": false,
			"id": "eTabM_1mfKy3EN1njshd_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -890.4183144229806,
			"y": 265.5655600936119,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 87056665,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1223,
			"versionNonce": 319257158,
			"isDeleted": false,
			"id": "xKvNEwncuPei9YoTPlW6M",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -954.8402102946152,
			"y": 265.5345666991866,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 848745977,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1233,
			"versionNonce": 519615770,
			"isDeleted": false,
			"id": "NHMp3OgpdxxpQvJ3WUJs3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -901.1679969445827,
			"y": 265.50230969222525,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 1494986457,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1231,
			"versionNonce": 1911308678,
			"isDeleted": false,
			"id": "w8l4_SKU8SK91jkSGWCK9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -965.5361205231425,
			"y": 265.5874273134734,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 257059769,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1227,
			"versionNonce": 588710362,
			"isDeleted": false,
			"id": "TNRWvJAOa8NhJUUBHF0Cn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -911.9074656459588,
			"y": 265.51378712498695,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 1298042009,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1267,
			"versionNonce": 2134253766,
			"isDeleted": false,
			"id": "UL7m4BXwSgmwamnnMY93Z",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -976.323700500705,
			"y": 265.5278386045252,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 989041017,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1285,
			"versionNonce": 1330493082,
			"isDeleted": false,
			"id": "-Th19fNL5rI3DV1FHZ_83",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -922.6033758744857,
			"y": 265.5666477392739,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1028979289,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1282,
			"versionNonce": 1585584134,
			"isDeleted": false,
			"id": "TAS7z5hpee8QB6EXzXonP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -987.0309121951198,
			"y": 265.50705903032565,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 1163282233,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1218,
			"versionNonce": 1414517594,
			"isDeleted": false,
			"id": "ejkMw6uItX94an3gy-VaE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -933.3209773560002,
			"y": 265.55625795217406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1566242841,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1448,
			"versionNonce": 936191814,
			"isDeleted": false,
			"id": "xsb7tLAV6OKUutZhCYGLh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -997.8368228254087,
			"y": 265.5495754313947,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 2002160889,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1052,
			"versionNonce": 1416648730,
			"isDeleted": false,
			"id": "BJ0jwl48YnqAcbhmT6Wzt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4043184601958,
			"y": 201.10914579552409,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 2060223961,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 918,
			"versionNonce": 729042566,
			"isDeleted": false,
			"id": "4bTlzZc4eg_tXZPZHP9F_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3994210525882,
			"y": 211.92595733522373,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 315646649,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 948,
			"versionNonce": 799163610,
			"isDeleted": false,
			"id": "Qz3Q-qzhFFE8tCeDoueEs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.4202006267876,
			"y": 276.2939049469097,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1007002521,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 968,
			"versionNonce": 1177849286,
			"isDeleted": false,
			"id": "tPFAG2VcUq81Q-b-6BsBh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3786414783884,
			"y": 222.65394860383813,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 312461433,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1003,
			"versionNonce": 1333303706,
			"isDeleted": false,
			"id": "ySRuv5ikXjxJ8p1Mb05kI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3786414783884,
			"y": 287.02189621552395,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 1617056089,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 995,
			"versionNonce": 1965745414,
			"isDeleted": false,
			"id": "epx7zE6bd6AyXINPWhoX5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3578619041889,
			"y": 233.38193987245236,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 1788919353,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1022,
			"versionNonce": 1931892314,
			"isDeleted": false,
			"id": "11rpt_i_3PRMhMUQ1EGNA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3994210525882,
			"y": 297.74988748413836,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 4099865,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1035,
			"versionNonce": 2043958342,
			"isDeleted": false,
			"id": "iV2IKX7a22JaYBvHe3BKO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3786414783884,
			"y": 244.10993114106677,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1202668537,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1045,
			"versionNonce": 2071886618,
			"isDeleted": false,
			"id": "J7NOp8YOSIouZln-WztIe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3994210525882,
			"y": 308.4778787527526,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 1291214041,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1026,
			"versionNonce": 1577966470,
			"isDeleted": false,
			"id": "1JnAVNKa2cvNPFDdE5nR3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3786414783884,
			"y": 254.8379224096811,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1336367545,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1049,
			"versionNonce": 921962458,
			"isDeleted": false,
			"id": "d2UR5IfcUbGgLezmjo-sQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3867117071219,
			"y": 319.20587002136693,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 1357232793,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1014,
			"versionNonce": 1746172614,
			"isDeleted": false,
			"id": "Y2PBbJdNJSnnWnUNhbffQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3786414783884,
			"y": 265.5659136782954,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1634008953,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1442,
			"versionNonce": 765066394,
			"isDeleted": false,
			"id": "pT2alqeWWsnVEgtF8e2ga",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -750.6646461725593,
			"y": 265.54982623803846,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 795387993,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1189,
			"versionNonce": 243610118,
			"isDeleted": false,
			"id": "yJ_GDdwJzFOq7VNrwaGxK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -815.0440712170067,
			"y": 265.56130367080016,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1422144825,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1204,
			"versionNonce": 1831033178,
			"isDeleted": false,
			"id": "BoxGZOOwR-BlrJ52cUoUj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -761.4134170153727,
			"y": 265.570605812238,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 1692083737,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1245,
			"versionNonce": 1818034502,
			"isDeleted": false,
			"id": "y8oCkr429fLIJK9neZ3aV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -825.8353128870074,
			"y": 265.5396124178127,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 983628537,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1255,
			"versionNonce": 1424170522,
			"isDeleted": false,
			"id": "KYS7t7EW8tn1YPdZYVF7s",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -772.1630995369749,
			"y": 265.50735541085135,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 110703577,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1253,
			"versionNonce": 888727686,
			"isDeleted": false,
			"id": "0RshbKCo7jOec29gaKFvI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -836.5312231155345,
			"y": 265.5924730320995,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 483872953,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911000,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1249,
			"versionNonce": 1640778458,
			"isDeleted": false,
			"id": "sx0ZjukV8GUIGDfwxJnyb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -782.9025682383509,
			"y": 265.51883284361315,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 50254233,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1289,
			"versionNonce": 672524230,
			"isDeleted": false,
			"id": "Cb9-bu1cDIvHDFdCfCNCw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -847.3188030930971,
			"y": 265.5328843231514,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 1044592249,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1307,
			"versionNonce": 2054283162,
			"isDeleted": false,
			"id": "3a-xZu_9gnBZciYAKqfIq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -793.5984784668779,
			"y": 265.5716934579,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1634205529,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1304,
			"versionNonce": 97582854,
			"isDeleted": false,
			"id": "CLFCSO1fcKadi6Ot1mYkG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -858.026014787512,
			"y": 265.51210474895174,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 1522576441,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1240,
			"versionNonce": 990305370,
			"isDeleted": false,
			"id": "A0NUmMCF1nNe__BLNydjO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -804.3160799483923,
			"y": 265.56130367080016,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 36748569,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1378,
			"versionNonce": 44510790,
			"isDeleted": false,
			"id": "BeZLQK3zwN5413gw0TWY8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -739.8382027698174,
			"y": 265.5706058122381,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.222300890877916e-13,
			"seed": 1730916857,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.222300890877916e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1471,
			"versionNonce": 1096696090,
			"isDeleted": false,
			"id": "2HEAHXGg32hrEEb1M0Ruv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -868.831925417801,
			"y": 265.5546211500209,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 1588923097,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1074,
			"versionNonce": 997553542,
			"isDeleted": false,
			"id": "mSYL5u63YO_pbPVIYEJY-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3994210525882,
			"y": 201.11419151415018,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1365264313,
			"groupIds": [
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 875,
			"versionNonce": 2028670426,
			"isDeleted": false,
			"id": "HCLeWcVUsG997RSiK3z5N",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.4092060431069,
			"y": 211.94046867530793,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1230039193,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 905,
			"versionNonce": 695784646,
			"isDeleted": false,
			"id": "Sd0fFcBQKCbBfcGaj_Iqc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.4299856173064,
			"y": 276.30841628699375,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1077570937,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 925,
			"versionNonce": 1723875994,
			"isDeleted": false,
			"id": "kBUci1PRGBq8aWD1O9uUC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3884264689073,
			"y": 222.66845994392216,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 761288281,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 960,
			"versionNonce": 374230022,
			"isDeleted": false,
			"id": "aj4w7_N0S193fQ9ClHr8b",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3884264689073,
			"y": 287.036407555608,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 1402348345,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 952,
			"versionNonce": 1972428634,
			"isDeleted": false,
			"id": "Jf0kLtbwwK7Gna_1Ponjk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3676468947077,
			"y": 233.39645121253656,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 1329550361,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 979,
			"versionNonce": 267574086,
			"isDeleted": false,
			"id": "BIl8yoU6h3hi9OQFmHT6q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.4092060431069,
			"y": 297.7643988242225,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 1682925817,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 992,
			"versionNonce": 1102046234,
			"isDeleted": false,
			"id": "flszqSfgtive5tVeFZ4Qf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3884264689073,
			"y": 244.1244424811508,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 206168537,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 1556316806,
			"isDeleted": false,
			"id": "ae29A8s6fC691ZImMEWEq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.4092060431071,
			"y": 308.49239009283673,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 1145192121,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 983,
			"versionNonce": 1695568090,
			"isDeleted": false,
			"id": "9l1Yo9P32SB2F4fhr-BYF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3884264689073,
			"y": 254.8524337497652,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 450625433,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1006,
			"versionNonce": 1870479814,
			"isDeleted": false,
			"id": "wilZasdschY0XQ8VjnrGb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3964966976407,
			"y": 319.22038136145096,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 2118820985,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 971,
			"versionNonce": 1128605082,
			"isDeleted": false,
			"id": "Iq39ODBwP0-fOQ0orZQh8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3884264689073,
			"y": 265.5804250183795,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1246866777,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1399,
			"versionNonce": 1530730758,
			"isDeleted": false,
			"id": "Jo27u7ccgLb37m0NpFkXD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -621.674431163078,
			"y": 265.5643375781226,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 373594681,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1146,
			"versionNonce": 1434542682,
			"isDeleted": false,
			"id": "-E38lK4BXlOji1A_BCrZY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -686.0538562075255,
			"y": 265.5758150108843,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1124526873,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1161,
			"versionNonce": 1199573062,
			"isDeleted": false,
			"id": "2JT8lnZMKkYBq-HJptc-g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -632.4232020058917,
			"y": 265.58511715232214,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 1225531385,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1202,
			"versionNonce": 1989674778,
			"isDeleted": false,
			"id": "_xn3yzjHiTfJilJjYrqT4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -696.8450978775262,
			"y": 265.5541237578967,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 1180154073,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1212,
			"versionNonce": 1680019334,
			"isDeleted": false,
			"id": "mX2n_J6Tcrn-XvAPnzBBS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -643.1728845274937,
			"y": 265.5218667509354,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 1283274169,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1210,
			"versionNonce": 788272090,
			"isDeleted": false,
			"id": "rOxmrQ2p1LaGIqOIEQjTr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -707.5410081060534,
			"y": 265.60698437218366,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 1855985305,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1206,
			"versionNonce": 1566781126,
			"isDeleted": false,
			"id": "ELdKpBOYF6owlzuBmi8Pq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -653.9123532288697,
			"y": 265.5333441836972,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 259251065,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1246,
			"versionNonce": 12617882,
			"isDeleted": false,
			"id": "IPVdrNqy9mEYwUtKXeZ0V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -718.3285880836161,
			"y": 265.5473956632354,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 1866204249,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1264,
			"versionNonce": 1339909638,
			"isDeleted": false,
			"id": "TdFEG5E7PTZPaLuYbbF6E",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -664.6082634573966,
			"y": 265.586204797984,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 2043416889,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1261,
			"versionNonce": 865625434,
			"isDeleted": false,
			"id": "q9658EOGc98ZVF2iNZvnL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -729.0357997780305,
			"y": 265.5266160890359,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 1418166809,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1197,
			"versionNonce": 1015985478,
			"isDeleted": false,
			"id": "TIhqT-jStmHbsMey0m4DW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -675.3258649389111,
			"y": 265.5758150108843,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 744609529,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1335,
			"versionNonce": 550939162,
			"isDeleted": false,
			"id": "spzd84XO0ce7T2QUhawlH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -610.8479877603363,
			"y": 265.58511715232214,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.222300890877916e-13,
			"seed": 1138659289,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.222300890877916e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1031,
			"versionNonce": 2094275718,
			"isDeleted": false,
			"id": "4k46C5nWDprdjDeuWepJG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.4092060431069,
			"y": 201.12870285423432,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1091644601,
			"groupIds": [
				"kZ8UMqXZAYT4ObulDl87D",
				"KvDJftKxG8Wyl8JzfwN9e"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1280,
			"versionNonce": 2137937626,
			"isDeleted": false,
			"id": "d1-Z5wz3jufp23EvpSz2o",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4921394589605,
			"y": 575.5167054949184,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1000156569,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1365,
			"versionNonce": 912956358,
			"isDeleted": false,
			"id": "D3LyuB61S_AZlZyfAXEF4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4071978045885,
			"y": 511.1487578832314,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 179704441,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1344,
			"versionNonce": 804416410,
			"isDeleted": false,
			"id": "MlN2ZeMYNk7RqSLiEwRUN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4921394589608,
			"y": 564.7887142263037,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1394563929,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1429,
			"versionNonce": 1332687622,
			"isDeleted": false,
			"id": "LC9rvdJimCspodoAoqXq2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3222561502146,
			"y": 500.42076661461743,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 1428981817,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1357,
			"versionNonce": 144042074,
			"isDeleted": false,
			"id": "-QEbBMfZ5HZ7EnFmBpDO9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3222561502128,
			"y": 554.0607229576899,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 2059475225,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1395,
			"versionNonce": 1650385478,
			"isDeleted": false,
			"id": "tlTlZatWkECFtWnmlv5zp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3909359172662,
			"y": 489.6927753460045,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 626036217,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1452,
			"versionNonce": 556518682,
			"isDeleted": false,
			"id": "jwY9KEmZWdiCDp56saClG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4071978045872,
			"y": 543.3327316890737,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1004431065,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1430,
			"versionNonce": 840345990,
			"isDeleted": false,
			"id": "aC7tqE1wXoDnv3J6ut496",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4758775716407,
			"y": 478.96478407738994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 2029921209,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1443,
			"versionNonce": 522656218,
			"isDeleted": false,
			"id": "0FTV5LMaljgoyXcsO62o7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4921394589612,
			"y": 532.6047404204595,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 2027111577,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1405,
			"versionNonce": 500402374,
			"isDeleted": false,
			"id": "MDy-axvpBQf4rHAIU8QzG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3909359172667,
			"y": 468.23679280877616,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 118573433,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1431,
			"versionNonce": 26922650,
			"isDeleted": false,
			"id": "KAbp5ok5K-AjrJnBirbAN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.4921394589622,
			"y": 521.8767491518463,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 754692697,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1771,
			"versionNonce": 355631110,
			"isDeleted": false,
			"id": "EZXoWzcJbuTBR2PBaiz4V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -728.9653587203695,
			"y": 521.8928365921062,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 2137390905,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1606,
			"versionNonce": 1832512346,
			"isDeleted": false,
			"id": "r0VZcAus8A2cso9DfETTC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -664.6088885414456,
			"y": 521.8813591593391,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 749973529,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1533,
			"versionNonce": 204508998,
			"isDeleted": false,
			"id": "_9Rgd_xsxLs3v4eVnW0H0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -718.2581470259552,
			"y": 521.8720570179062,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 1255687417,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1662,
			"versionNonce": 2018996250,
			"isDeleted": false,
			"id": "kJfnVYKXx4mNzQOmY4_C1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -653.9441476742181,
			"y": 521.9030504123264,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 1700216281,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1584,
			"versionNonce": 1865070214,
			"isDeleted": false,
			"id": "w-H2Wxa7YLLaQMlDdrx4l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -707.5518470103282,
			"y": 521.9353074192928,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 1262754489,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1670,
			"versionNonce": 1994808538,
			"isDeleted": false,
			"id": "guzYhbmACX_TjBiEI-p3J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -643.1840753655165,
			"y": 521.8501897980393,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 490888089,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1578,
			"versionNonce": 383645126,
			"isDeleted": false,
			"id": "gYsqjaZE9Dg1wuBYlFk_P",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -696.8353331744756,
			"y": 521.9238299865308,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 461734009,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1706,
			"versionNonce": 1182380442,
			"isDeleted": false,
			"id": "jYGz2n4cHIjcwKeY55az7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -632.5156728058503,
			"y": 521.9097785069866,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 869337433,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1724,
			"versionNonce": 1013402886,
			"isDeleted": false,
			"id": "6lithW9qpJV3_c8Bh0QW9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -686.0752608657742,
			"y": 521.8709693722416,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1333294649,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1721,
			"versionNonce": 440692314,
			"isDeleted": false,
			"id": "y8OKA_wdw1-M8_KkFjen0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -621.7669019630366,
			"y": 521.9305580811863,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 1633634073,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1657,
			"versionNonce": 1833155654,
			"isDeleted": false,
			"id": "K7hj9z0AD_-pYiST_mH8Y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -675.3368798100603,
			"y": 521.8813591593411,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 871955449,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1887,
			"versionNonce": 1192858394,
			"isDeleted": false,
			"id": "_Ip89OnM8cIkKeKSw8VMC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -610.9620554257494,
			"y": 521.8880416801169,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 2001278169,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1491,
			"versionNonce": 2135966598,
			"isDeleted": false,
			"id": "vxv3BBRwQ_T_EENcdwLJi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.492139458959,
			"y": 586.3284713159915,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 249762233,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1247,
			"versionNonce": 258744282,
			"isDeleted": false,
			"id": "xmw2TZpH-P4CaWQJ4EojI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4970368665688,
			"y": 575.5116597762965,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 535458457,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1130,
			"versionNonce": 80339654,
			"isDeleted": false,
			"id": "CYgiYWrM00OEAkkQ2R4hD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4120952121962,
			"y": 511.14371216461075,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1595062137,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1296,
			"versionNonce": 1867453594,
			"isDeleted": false,
			"id": "9yLwUUdvBPhHo6xeCQKxc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4970368665688,
			"y": 564.7836685076823,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 513761369,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1297,
			"versionNonce": 1078827526,
			"isDeleted": false,
			"id": "DiGe5ilyXBjskADLX0tfj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.3271535578226,
			"y": 500.41572089599646,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 476310841,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1321,
			"versionNonce": 1752527194,
			"isDeleted": false,
			"id": "hFMBYFfhNL-9uHZ2v7ufR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.327153557821,
			"y": 554.055677239068,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 264494617,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1361,
			"versionNonce": 416835910,
			"isDeleted": false,
			"id": "eWnc-nlTfG8KDmVxxYG1I",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.3958333248736,
			"y": 489.6877296273823,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 2008199929,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1319,
			"versionNonce": 1311913498,
			"isDeleted": false,
			"id": "v9CHPl59oaO2CL_dDUrUG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4120952121953,
			"y": 543.3276859704536,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 682879961,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1398,
			"versionNonce": 231166086,
			"isDeleted": false,
			"id": "8uVpwJkeUevUCh7tsLJDi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4807749792483,
			"y": 478.9597383587678,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 450562233,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1208,
			"versionNonce": 293102298,
			"isDeleted": false,
			"id": "n2EmXkAWeC-b54Md4J2ZD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4970368665699,
			"y": 532.5996947018392,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 2009827737,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1400,
			"versionNonce": 718753734,
			"isDeleted": false,
			"id": "_mnx4JMOjeJzrVXUwpR7L",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.3958333248744,
			"y": 468.2317470901536,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 1756950137,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1196,
			"versionNonce": 215676826,
			"isDeleted": false,
			"id": "96pWt6KhmuZKHtgRDNL3n",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4970368665702,
			"y": 521.8717034332249,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 610711385,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1722,
			"versionNonce": 2082825990,
			"isDeleted": false,
			"id": "t_mSiAeQRaNxyfuEub8pq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -857.9702561279776,
			"y": 521.8877908734828,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 1026057273,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1371,
			"versionNonce": 1351414874,
			"isDeleted": false,
			"id": "VPa9-vR-A1BXC0EUxkeqY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -793.6137859490536,
			"y": 521.87631344072,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 786527513,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1484,
			"versionNonce": 36607558,
			"isDeleted": false,
			"id": "buz_ImTOGVf54zdDOFV8I",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -847.2630444335634,
			"y": 521.8670112992829,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 755329529,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1525,
			"versionNonce": 1851873562,
			"isDeleted": false,
			"id": "TI9Q9Vifop0V3-QsCVXRF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -782.9490450818264,
			"y": 521.898004693707,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 815252185,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1487,
			"versionNonce": 634379654,
			"isDeleted": false,
			"id": "Y-Qtvn0yVPAj0XUWrMC-Q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -836.5567444179363,
			"y": 521.9302617006692,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 1177288633,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1651,
			"versionNonce": 1170941402,
			"isDeleted": false,
			"id": "PiNT_L7QMy99qyqeV0Lrq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -772.1889727731246,
			"y": 521.8451440794199,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 468033689,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1498,
			"versionNonce": 742800582,
			"isDeleted": false,
			"id": "kfmiIOdq5z-98dig2Aiqb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -825.8402305820833,
			"y": 521.9187842679075,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 1333273977,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1642,
			"versionNonce": 1339906714,
			"isDeleted": false,
			"id": "gMe5nBfY-eXlemq2EinJ9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -761.5205702134583,
			"y": 521.9047327883678,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 2082934361,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1489,
			"versionNonce": 724481030,
			"isDeleted": false,
			"id": "RRzv4WVJQQHJLlBPe42WJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -815.0801582733822,
			"y": 521.8659236536201,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 147184441,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1659,
			"versionNonce": 1800075098,
			"isDeleted": false,
			"id": "le_RdVerXslkzChwfImUH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -750.7717993706443,
			"y": 521.9255123625672,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 901254169,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1422,
			"versionNonce": 2089173830,
			"isDeleted": false,
			"id": "Gmg9b43XMymTHbBmWWODy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -804.3417772176681,
			"y": 521.8763134407201,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1794187513,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1702,
			"versionNonce": 677837850,
			"isDeleted": false,
			"id": "dC1qsseNWDYBvWnVg86mR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -868.8382586791188,
			"y": 521.8670112992835,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.222300890877916e-13,
			"seed": 1173658073,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.222300890877916e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1869,
			"versionNonce": 849996422,
			"isDeleted": false,
			"id": "U2xWSHS3JW1UXvA7tpo3X",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -739.966952833357,
			"y": 521.8829959614978,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 1742075577,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1441,
			"versionNonce": 354707674,
			"isDeleted": false,
			"id": "D0dmFIW6cqHh_5AbbiP06",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -804.4970368665684,
			"y": 586.32342559737,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 54048665,
			"groupIds": [
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1205,
			"versionNonce": 207006150,
			"isDeleted": false,
			"id": "fV1uHW6ySgLLSZdNKRbaC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4872518760501,
			"y": 575.4971484362156,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 709909625,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1283,
			"versionNonce": 152452506,
			"isDeleted": false,
			"id": "5Od4z4ulCKNKAzqONXZlP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4023102216779,
			"y": 511.12920082453206,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1558209881,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1270,
			"versionNonce": 1755939078,
			"isDeleted": false,
			"id": "k2wTAGVih82tweYUKsluZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4872518760501,
			"y": 564.7691571676016,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1446793785,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1349,
			"versionNonce": 1903131226,
			"isDeleted": false,
			"id": "xc3aG6_RAyXKOJsMkeWAO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.3173685673039,
			"y": 500.40120955591783,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 457679641,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1283,
			"versionNonce": 991916102,
			"isDeleted": false,
			"id": "8krVvQL6hm5xcGn98boBI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.3173685673023,
			"y": 554.0411658989867,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 1215682553,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1343,
			"versionNonce": 486743834,
			"isDeleted": false,
			"id": "vFkXGlDqZSZGIgEjjXi1N",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.3860483343551,
			"y": 489.673218287302,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 533360857,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1354,
			"versionNonce": 2140501894,
			"isDeleted": false,
			"id": "nMnqMzm0ETv3fCNNUNlOi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4023102216768,
			"y": 543.3131746303743,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1457057209,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1377,
			"versionNonce": 138685402,
			"isDeleted": false,
			"id": "e7NQTqS9NxYf8dizdFeeK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4709899887296,
			"y": 478.9452270186879,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 616877721,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1341,
			"versionNonce": 776509126,
			"isDeleted": false,
			"id": "Qdwp7EDJfG666y84X--Jq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4872518760508,
			"y": 532.58518336176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 272733049,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1367,
			"versionNonce": 692428954,
			"isDeleted": false,
			"id": "sOoMIzMmUhpWNUcSP0Dl5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.3860483343558,
			"y": 468.2172357500734,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 2106768473,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1340,
			"versionNonce": 802541062,
			"isDeleted": false,
			"id": "BHEnBx8Pv3HSWswZHvhvK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4872518760515,
			"y": 521.8571920931454,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 2089535801,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1838,
			"versionNonce": 1002077530,
			"isDeleted": false,
			"id": "E2PHhzWBEM4tTMN7vfjAk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -986.9604711374593,
			"y": 521.8732795334063,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 1452292633,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1470,
			"versionNonce": 1362763078,
			"isDeleted": false,
			"id": "cSTxqCJOUZXXB2nNN7k1n",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -922.6040009585347,
			"y": 521.86180210064,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1553174265,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1600,
			"versionNonce": 217432602,
			"isDeleted": false,
			"id": "soAbOLOzeAZ8DnNAYjKay",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -976.2532594430454,
			"y": 521.8524999592064,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 1964591065,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1486,
			"versionNonce": 936543366,
			"isDeleted": false,
			"id": "f9Slo-3aHJT9ZgwDixU6U",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -911.9392600913072,
			"y": 521.8834933536256,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 1781851321,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1651,
			"versionNonce": 1206546138,
			"isDeleted": false,
			"id": "GLErMLDOuWgmhrW2A-M1V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -965.546959427418,
			"y": 521.915750360592,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 2005525913,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1536,
			"versionNonce": 1432093638,
			"isDeleted": false,
			"id": "K-QDg19hVwepQ7YIj5f29",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -901.1791877826058,
			"y": 521.8306327393386,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 407620217,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1645,
			"versionNonce": 1093370778,
			"isDeleted": false,
			"id": "JaAr3C1s3Qx4xpd-jWtFQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -954.830445591565,
			"y": 521.9042729278301,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 356389721,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1571,
			"versionNonce": 1542691590,
			"isDeleted": false,
			"id": "6YQqn-zCYz007PbuJhFx9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -890.5107852229395,
			"y": 521.8902214482868,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 1387544633,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1677,
			"versionNonce": 1122762842,
			"isDeleted": false,
			"id": "J64XHLKvU11C6kRTb01VQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -944.0703732828638,
			"y": 521.8514123135429,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1586614553,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1612,
			"versionNonce": 840321606,
			"isDeleted": false,
			"id": "l3I4cd9HTHQe07_LOJsbG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -879.7620143801261,
			"y": 521.911001022486,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 1045054969,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1563,
			"versionNonce": 1493099802,
			"isDeleted": false,
			"id": "agrx2yLZGCKYVQ2gMWGYa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -933.3319922271494,
			"y": 521.8618021006406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 2095128281,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1774,
			"versionNonce": 1721831814,
			"isDeleted": false,
			"id": "-nyKD1Ov0NjTlxE2WBKoq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -997.8284736886003,
			"y": 521.8524999592066,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.222300890877916e-13,
			"seed": 2028592057,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.222300890877916e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1453,
			"versionNonce": 483865050,
			"isDeleted": false,
			"id": "BBQcVJrM1EkvP5R0K9vIW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -933.4872518760478,
			"y": 586.3089142572901,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1921514649,
			"groupIds": [
				"YS1QERTc5JZXJANJTD1fG",
				"KqzqfYJHXAvDMM91Qrqk_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1160,
			"versionNonce": 617672902,
			"isDeleted": false,
			"id": "45VVU0XV5WyazfqQ_wn-5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2963037699446,
			"y": 339.46628490085243,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1500447097,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1190,
			"versionNonce": 25683610,
			"isDeleted": false,
			"id": "sIhptq5Ca3LFCWlW1MTE9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3170833441443,
			"y": 403.83423251253834,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1524787801,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1210,
			"versionNonce": 675473414,
			"isDeleted": false,
			"id": "O_9tHL7BY12V8VlYDEf_4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2755241957451,
			"y": 350.1942761694668,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 800438073,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1245,
			"versionNonce": 532939610,
			"isDeleted": false,
			"id": "C_9kFAPNUhQ7KqdOv3NC8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2755241957451,
			"y": 414.56222378115274,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 709650457,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1237,
			"versionNonce": 821294918,
			"isDeleted": false,
			"id": "Sota52vvlGhv2vJ-lSe0O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2547446215456,
			"y": 360.9222674380811,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 77200633,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1264,
			"versionNonce": 31361050,
			"isDeleted": false,
			"id": "QBsaoDHRuXisVvU1qx5Jr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2963037699446,
			"y": 425.29021504976697,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 1847719385,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1277,
			"versionNonce": 2000756358,
			"isDeleted": false,
			"id": "AzucAKhAgOnwAVvnTgFoE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2755241957451,
			"y": 371.65025870669547,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1509413561,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1287,
			"versionNonce": 1875539162,
			"isDeleted": false,
			"id": "So8i5nLVxuphK_RM4lgMb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2963037699446,
			"y": 436.0182063183812,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 213848985,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1268,
			"versionNonce": 535256518,
			"isDeleted": false,
			"id": "bfk7Hmpvmvj928rI-RLuc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2755241957451,
			"y": 382.3782499753097,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1789606009,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1288,
			"versionNonce": 991611290,
			"isDeleted": false,
			"id": "U_sBde7qSvXWL-kyBhgNV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2835944244786,
			"y": 446.7461975869956,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 92258649,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1256,
			"versionNonce": 805549318,
			"isDeleted": false,
			"id": "ACOShBf3KNB4OkOwhRkme",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2755241957451,
			"y": 393.10624124392393,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1787833913,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1684,
			"versionNonce": 184714842,
			"isDeleted": false,
			"id": "nkFE4VwuwIvNpJUI9Kq2y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -750.5615288899157,
			"y": 393.0901538036671,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 817889049,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1431,
			"versionNonce": 18031686,
			"isDeleted": false,
			"id": "07i7009-31JAsLUUOwsE8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -814.9409539343633,
			"y": 393.1016312364289,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1182970873,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1446,
			"versionNonce": 676637466,
			"isDeleted": false,
			"id": "_kXmZS1P-znMhSLI4vQwv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -761.3102997327294,
			"y": 393.1109333778667,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 2145111257,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911001,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1487,
			"versionNonce": 888318854,
			"isDeleted": false,
			"id": "wqlI8yXmJmN9bssodayLb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -825.7321956043639,
			"y": 393.07993998344136,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 1683933625,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1497,
			"versionNonce": 1233401818,
			"isDeleted": false,
			"id": "NWB7GSnUxFlersC4DjHDj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -772.0599822543313,
			"y": 393.04768297648013,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 1026501273,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1495,
			"versionNonce": 702499526,
			"isDeleted": false,
			"id": "7dAcihhFQPaxjYgwxJEAa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -836.4281058328911,
			"y": 393.1328005977282,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 1660972921,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1491,
			"versionNonce": 1587817626,
			"isDeleted": false,
			"id": "OOKYRuF8zPLmxyLaQdgEI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -782.7994509557075,
			"y": 393.0591604092418,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 1276516441,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1531,
			"versionNonce": 1853227526,
			"isDeleted": false,
			"id": "xMdl4V7QUi3N514YLgdkI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -847.2156858104538,
			"y": 393.07321188878,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 1514382649,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1549,
			"versionNonce": 1567066458,
			"isDeleted": false,
			"id": "xd09zK2_GOvf3f_MlQ8hB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -793.4953611842343,
			"y": 393.11202102352865,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1760335385,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1546,
			"versionNonce": 900976966,
			"isDeleted": false,
			"id": "4JHWB3qMl4nzy4EiLD9KW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -857.9228975048687,
			"y": 393.05243231458036,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 453274361,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1482,
			"versionNonce": 220286490,
			"isDeleted": false,
			"id": "hrWgz2uqTdQ6AhyOOopvS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -804.2129626657488,
			"y": 393.1016312364289,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1762567129,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1620,
			"versionNonce": 1257617542,
			"isDeleted": false,
			"id": "0EE3j1QN8ClpuAT5pK8ZB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -739.735085487174,
			"y": 393.1109333778668,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.222300890877916e-13,
			"seed": 1864286393,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.222300890877916e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1465,
			"versionNonce": 1388608218,
			"isDeleted": false,
			"id": "GHx2LFGVJWnKKIO5WX8ED",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3459331470772,
			"y": 457.4684578739854,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.91152727308716,
			"height": 0,
			"seed": 2060992921,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.91152727308716,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1712,
			"versionNonce": 100186054,
			"isDeleted": false,
			"id": "FzrYsXcZtyP3zHE7S_EqR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -868.7288081351575,
			"y": 393.09494871564954,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 1500423801,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1316,
			"versionNonce": 2095320986,
			"isDeleted": false,
			"id": "wC7wk3rtWTFDFpkjSFGPe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.2963037699446,
			"y": 328.6545190797788,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1705340761,
			"groupIds": [
				"316yfJ27xeBUwXmp5NGO2",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1271,
			"versionNonce": 1054461702,
			"isDeleted": false,
			"id": "wbXHUpNeijRFblXwZKz7s",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4101094238881,
			"y": 339.4485923521492,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1439702073,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1301,
			"versionNonce": 263392346,
			"isDeleted": false,
			"id": "yizvg4PWqP5PdQJ7VcXIT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4308889980878,
			"y": 403.816539963835,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1238510873,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1321,
			"versionNonce": 1108737606,
			"isDeleted": false,
			"id": "82ZEqlSLxi_XKM3QymGBe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3893298496885,
			"y": 350.1765836207635,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 421470713,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1356,
			"versionNonce": 285503770,
			"isDeleted": false,
			"id": "jkKvZBM_xSMglN9IxRBuS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3893298496885,
			"y": 414.5445312324493,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 1622833881,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1348,
			"versionNonce": 1149912454,
			"isDeleted": false,
			"id": "1WdqPKL9jHQOQU4Q_6LOq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3685502754888,
			"y": 360.9045748893777,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 1362606009,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1369,
			"versionNonce": 1414217178,
			"isDeleted": false,
			"id": "kzxMOAsvTFd0yct2cJohl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4101094238881,
			"y": 425.2725225010637,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 1018845337,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1388,
			"versionNonce": 1467196614,
			"isDeleted": false,
			"id": "LCWcSeukVYVLCUaTnvXV8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3893298496887,
			"y": 371.632566157992,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1693834617,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1392,
			"versionNonce": 1184527002,
			"isDeleted": false,
			"id": "WJZ9h_bVikZpxPbzZLoqz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4101094238881,
			"y": 436.0005137696779,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 153994841,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1379,
			"versionNonce": 1550785542,
			"isDeleted": false,
			"id": "BY17urJ27uVSBT8R3nN32",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3893298496885,
			"y": 382.36055742660636,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 875926329,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1376,
			"versionNonce": 983895898,
			"isDeleted": false,
			"id": "zo8GnoWfUmZhERRHVDWbM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3974000784219,
			"y": 446.72850503829216,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 1248904217,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1367,
			"versionNonce": 2038016838,
			"isDeleted": false,
			"id": "DV53bGE1jNoZnI5sNQhjc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.3893298496885,
			"y": 393.08854869522077,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1473435897,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1795,
			"versionNonce": 884872218,
			"isDeleted": false,
			"id": "LJwx4A0PLG4xwe7-ffPPb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -879.6753345438592,
			"y": 393.07246125496374,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 501174745,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1542,
			"versionNonce": 217076358,
			"isDeleted": false,
			"id": "QO02tly9j0Zmq6KRoU_ds",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -944.054759588307,
			"y": 393.08393868772544,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1638510265,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1557,
			"versionNonce": 920158426,
			"isDeleted": false,
			"id": "zpNRCcLCISm23QFuNH_AS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -890.4241053866729,
			"y": 393.09324082916334,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 2044030873,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1598,
			"versionNonce": 563089862,
			"isDeleted": false,
			"id": "TjUgJXTRrV6TBdpw5rCic",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -954.8460012583075,
			"y": 393.0622474347381,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 479597689,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1608,
			"versionNonce": 210195866,
			"isDeleted": false,
			"id": "jGJc43VdUq-2Ml2TxCbM7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -901.1737879082748,
			"y": 393.0299904277767,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78648747340443,
			"height": 1.2933230081457278e-13,
			"seed": 1840192857,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78648747340443,
					1.2933230081457278e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1617,
			"versionNonce": 1651894534,
			"isDeleted": false,
			"id": "3YeWrypxVtN2z877uYzy-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -965.4895006983368,
			"y": 393.0626972605272,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.68201783015743,
			"height": 1.2217209230238881e-13,
			"seed": 1282673209,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.68201783015743,
					1.2217209230238881e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1602,
			"versionNonce": 385716826,
			"isDeleted": false,
			"id": "uEdpLlXx1UxGd5kKSN1QQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -911.913256609651,
			"y": 393.0414678605384,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8094423389279,
			"height": 1.2229307050205955e-13,
			"seed": 1640520473,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8094423389279,
					1.2229307050205955e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1650,
			"versionNonce": 253679686,
			"isDeleted": false,
			"id": "6aEubhrYMIH3Tp9DjGWa7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -976.3078179053678,
			"y": 393.03384578104703,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8626697069898,
			"height": 1.223436051380058e-13,
			"seed": 1847562233,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8626697069898,
					1.223436051380058e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1660,
			"versionNonce": 420362010,
			"isDeleted": false,
			"id": "kevX94p4SxbYPtX9molMP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -922.6091668381778,
			"y": 393.09432847482526,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1467820249,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1657,
			"versionNonce": 1869078406,
			"isDeleted": false,
			"id": "WH5meC6WJfyhynhnrmxkU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -987.0367031588121,
			"y": 393.034739765877,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 2004133305,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1593,
			"versionNonce": 53232602,
			"isDeleted": false,
			"id": "KHg46PcNNYwRjyxWdsV0o",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -933.3267683196923,
			"y": 393.08393868772544,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 690587289,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1503,
			"versionNonce": 1200488134,
			"isDeleted": false,
			"id": "pQOk9JwIzskgE6iDYLnKq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4597388010209,
			"y": 457.4507653252821,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.91152727308716,
			"height": 0,
			"seed": 391072633,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.91152727308716,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1823,
			"versionNonce": 1063958682,
			"isDeleted": false,
			"id": "QeibE6_5gFWvenHFxoLhT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": -997.842613789101,
			"y": 393.0772561669462,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 1244230745,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1377,
			"versionNonce": 1278096902,
			"isDeleted": false,
			"id": "DRd2eqOhJLCxj0q56d-kl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -933.4101094238881,
			"y": 328.6368265310755,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1972076857,
			"groupIds": [
				"Thbk0QufHY5LnS8ml3EMo",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1794,
			"versionNonce": 2105316698,
			"isDeleted": false,
			"id": "AtNhKdrpb0FPiyXyyOckX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3930477734125,
			"y": 446.73666582298097,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 114881049,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1826,
			"versionNonce": 373654854,
			"isDeleted": false,
			"id": "D1F6zH-DokYd-MdLG6tJI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3081061190393,
			"y": 382.36871821129483,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.89893935747708,
			"height": 0,
			"seed": 1929725689,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.89893935747708,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1867,
			"versionNonce": 2125781530,
			"isDeleted": false,
			"id": "UoV1NOxVYcM34D9rmFz41",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3930477734125,
			"y": 436.0086745543663,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 1150549977,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1883,
			"versionNonce": 389082246,
			"isDeleted": false,
			"id": "VsTC9sCUDRsbebJm4GU29",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.2231644646653,
			"y": 371.64072694268054,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.77243855470374,
			"height": 0,
			"seed": 1771609273,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.77243855470374,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1901,
			"versionNonce": 1644594906,
			"isDeleted": false,
			"id": "P4QVfqOVq9NAoc1vKRUUz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.2231644646645,
			"y": 425.28068328575205,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.75165898050415,
			"height": 0,
			"seed": 1102486937,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.75165898050415,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1952,
			"versionNonce": 212691910,
			"isDeleted": false,
			"id": "jZ7fWSXMX8MBE2lIncJOe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.2918442317167,
			"y": 360.9127356740663,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8618978959546,
			"height": 0,
			"seed": 1814135417,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8618978959546,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1892,
			"versionNonce": 1879350170,
			"isDeleted": false,
			"id": "j8Xy79S5HIIMxL7Vu_dir",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3081061190387,
			"y": 414.55269201713776,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85738020907792,
			"height": 0,
			"seed": 1436339033,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85738020907792,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1939,
			"versionNonce": 1960313606,
			"isDeleted": false,
			"id": "PGVXo6eCBeIaxX8eq8XgH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.376785886091,
			"y": 350.18474440545185,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94683955032878,
			"height": 0,
			"seed": 108787769,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94683955032878,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1882,
			"versionNonce": 1726093402,
			"isDeleted": false,
			"id": "3sDCHmNsNCDZYJAAmBSac",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3930477734132,
			"y": 403.82470074852347,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 815958297,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1914,
			"versionNonce": 36549190,
			"isDeleted": false,
			"id": "0XyOX1flCWWOOezCRWFSE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.291844231717,
			"y": 339.4567531368377,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.84918855048838,
			"height": 0,
			"seed": 2105802233,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.84918855048838,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1757,
			"versionNonce": 1181875482,
			"isDeleted": false,
			"id": "3MJeW1It9YBQmj8CGCYTH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3930477734132,
			"y": 393.096709479909,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.94232186345204,
			"height": 0,
			"seed": 472110809,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.94232186345204,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2356,
			"versionNonce": 260798854,
			"isDeleted": false,
			"id": "G5DKBN1xcHOsH-AVz32Sm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -728.8662670348208,
			"y": 393.1127969201673,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7015458190303,
			"height": 1.3013428428257029e-13,
			"seed": 253072313,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7015458190303,
					1.3013428428257029e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2145,
			"versionNonce": 472336858,
			"isDeleted": false,
			"id": "Ar3VElGq_KeiPlWA5QimR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -664.5097968558966,
			"y": 393.101319487404,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 981251225,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2160,
			"versionNonce": 338581702,
			"isDeleted": false,
			"id": "wUS5T6XZeBku_vsZXSG_n",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -718.1590553404066,
			"y": 393.0920173459676,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7431049674295,
			"height": 1.3282162495103308e-13,
			"seed": 839694713,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7431049674295,
					1.3282162495103308e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2203,
			"versionNonce": 1326775962,
			"isDeleted": false,
			"id": "YjwlhnZ0Lx6FtbBHpsHLg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -653.8450559886693,
			"y": 393.1230107403911,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.85100148732707,
			"height": 1.2233252720471195e-13,
			"seed": 1191780953,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.85100148732707,
					1.2233252720471195e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2183,
			"versionNonce": 397627398,
			"isDeleted": false,
			"id": "WWUZV5XFolaGldqeQcgYM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -707.3496154410865,
			"y": 393.05212786366064,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.5802077060184,
			"height": 2.5202413234022216e-13,
			"seed": 1447391033,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.5802077060184,
					2.5202413234022216e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2242,
			"versionNonce": 1810766682,
			"isDeleted": false,
			"id": "va9_HlIcVSsY3hD43TPzs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -643.0849836799678,
			"y": 393.07015012610407,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.78683940715257,
			"height": 1.2227161103543224e-13,
			"seed": 1445273625,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.78683940715257,
					1.2227161103543224e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2134,
			"versionNonce": 639065926,
			"isDeleted": false,
			"id": "wzjIA9m3Ot7MWU8eP7S5o",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -696.6331016052341,
			"y": 393.0406504308988,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.60316257154213,
			"height": 2.5206912511298104e-13,
			"seed": 614184185,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.60316257154213,
					2.5206912511298104e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2245,
			"versionNonce": 1896194074,
			"isDeleted": false,
			"id": "dGY6VhVicvQ5UwH5eaoZw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -632.4165811203015,
			"y": 393.1297388350519,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.90601682504902,
			"height": 1.2238475935829132e-13,
			"seed": 355249625,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.90601682504902,
					1.2238475935829132e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2185,
			"versionNonce": 1136100998,
			"isDeleted": false,
			"id": "WhKcDmHiVLlv8VVCZFyZx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -685.9761691802254,
			"y": 393.09092970030474,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.74528025875338,
			"height": 1.2929317824160751e-13,
			"seed": 1055623865,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.74528025875338,
					1.2929317824160751e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2260,
			"versionNonce": 441355482,
			"isDeleted": false,
			"id": "Zdah7DXTNgslawqP7ERh0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -621.6678102774874,
			"y": 393.1505184092514,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.8644576766498,
			"height": 1.2234530265563894e-13,
			"seed": 175885209,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.8644576766498,
					1.2234530265563894e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1983,
			"versionNonce": 1632683462,
			"isDeleted": false,
			"id": "KdV7FfqCAv_YVCiuoxNE1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -675.2377881245111,
			"y": 393.1013194874042,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.7245006845538,
			"height": 1.2221242598145366e-13,
			"seed": 1110137,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.7245006845538,
					1.2221242598145366e-13
				]
			]
		},
		{
			"type": "line",
			"version": 2087,
			"versionNonce": 760996250,
			"isDeleted": false,
			"id": "Y53L--V8eaKtbdfxDBKDR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.2918442317173,
			"y": 328.73449284984815,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.91152727308716,
			"height": 0,
			"seed": 1433303385,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.91152727308716,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2475,
			"versionNonce": 1342184710,
			"isDeleted": false,
			"id": "cDd2CTlmuDlNK2PISNsGC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.712388980384688,
			"x": -610.8629637402003,
			"y": 393.1080020081822,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.86552176965154,
			"height": 1.2234631291698404e-13,
			"seed": 1005053497,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.86552176965154,
					1.2234631291698404e-13
				]
			]
		},
		{
			"type": "line",
			"version": 1930,
			"versionNonce": 1163959898,
			"isDeleted": false,
			"id": "WjADyz6QlLgMauiGvRKZv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.141592653589793,
			"x": -675.3930477734123,
			"y": 457.4607086353071,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 128.96310143765163,
			"height": 0,
			"seed": 1851832089,
			"groupIds": [
				"4oy_y5RvMOG4zIM53uWlV",
				"6oPaGx8gK4pZva3u-kAdV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					128.96310143765163,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 771,
			"versionNonce": 893553734,
			"isDeleted": false,
			"id": "BDyk-RN5ZEynls23QY-Mk",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -752.6938950700528,
			"y": 401.7599962644958,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 682877593,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 673,
			"versionNonce": 523223834,
			"isDeleted": false,
			"id": "sG4nTgTLWWgmHC-Cc6GXj",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -795.5176485085915,
			"y": 444.71095773354875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1831741305,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 856,
			"versionNonce": 2129990534,
			"isDeleted": false,
			"id": "IF0JqQRhyBJ_oI5x5DXpc",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -709.3382019339838,
			"y": 358.8246169276465,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 936169561,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 658,
			"versionNonce": 1698451418,
			"isDeleted": false,
			"id": "QXDZJv2MNTaq_R1MoYrIw",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -817.304902697081,
			"y": 465.99905585897386,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 241392953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 842,
			"versionNonce": 1465168582,
			"isDeleted": false,
			"id": "AJi6gn8wIwjO_kudglgOc",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -731.1254561224735,
			"y": 380.1127150530715,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1884638745,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 744,
			"versionNonce": 2073642138,
			"isDeleted": false,
			"id": "Z_ObDz9x0eXelfkBiC71n",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -773.9492095610121,
			"y": 423.0636765221245,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 613819129,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 927,
			"versionNonce": 419326470,
			"isDeleted": false,
			"id": "XNszcGJUHa0FT2HRuxvx6",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -687.7697629864047,
			"y": 337.17733571622216,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1202281433,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 1274650970,
			"isDeleted": false,
			"id": "8gb5zo3XzgTUhaemoLHe4",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -666.677310339981,
			"y": 315.72413950527,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 430078137,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 626,
			"versionNonce": 1122974022,
			"isDeleted": false,
			"id": "I7Bt44qVGzt3-WhOCyYCM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -828.0915464487683,
			"y": 476.92398991516995,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 203749785,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 712,
			"versionNonce": 296773146,
			"isDeleted": false,
			"id": "B6B7mEC8vKJoKsubIEf41",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -784.7358533126994,
			"y": 433.9886105783206,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 275013241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 895,
			"versionNonce": 1820598406,
			"isDeleted": false,
			"id": "UPfYFiQEY2rGWftQR3Vt1",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -698.5564067380922,
			"y": 348.10226977241825,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 623126361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 881,
			"versionNonce": 632328922,
			"isDeleted": false,
			"id": "FXv4pka4WaIu6XiJyeOIA",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -720.3436609265816,
			"y": 369.39036789784325,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1392698649,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 783,
			"versionNonce": 964304838,
			"isDeleted": false,
			"id": "1JtXlGoP3YhL-uchpafQZ",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -763.1674143651203,
			"y": 412.34132936689633,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 729340409,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 966,
			"versionNonce": 1250764698,
			"isDeleted": false,
			"id": "OSBwXo_v0z9zp2XLy9RnN",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -676.9879677905128,
			"y": 326.45498856099397,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1864184537,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1055,
			"versionNonce": 1307457286,
			"isDeleted": false,
			"id": "ucf3QHXkSfIpsa2RoK0Vs",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -655.8955151440892,
			"y": 305.0017923500418,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1921216441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 576,
			"versionNonce": 2021205082,
			"isDeleted": false,
			"id": "sKiK2b-g2b1X7p_GWBzVz",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -911.8580167037851,
			"y": 391.2065584178014,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 734990489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 648,
			"versionNonce": 1113417286,
			"isDeleted": false,
			"id": "dIi03nR20o70Fkn-Pov2G",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -890.3819808374967,
			"y": 391.2961912886957,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 11769209,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 702,
			"versionNonce": 692554010,
			"isDeleted": false,
			"id": "sKgidNG9eQRzfWmp1OfMA",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -868.8820179290134,
			"y": 391.29527204445657,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1416920665,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 774,
			"versionNonce": 396668294,
			"isDeleted": false,
			"id": "u9PsvAftWssT14rXwmpe1",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -847.4059820627253,
			"y": 391.38490491535094,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1441090361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 667,
			"versionNonce": 611014106,
			"isDeleted": false,
			"id": "dHg_JnQnETwWN8tdERHTv",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -825.7822625710687,
			"y": 391.2755995836276,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 225016857,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 739,
			"versionNonce": 721489094,
			"isDeleted": false,
			"id": "8MSaffKP6MIBYpR0wio9a",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -804.3062267047808,
			"y": 391.3652324545219,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 720670969,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 793,
			"versionNonce": 1257736858,
			"isDeleted": false,
			"id": "-7UbaSKsIZMrGzsRnyGke",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -782.8062637962973,
			"y": 391.3643132102827,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 336202201,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 879,
			"versionNonce": 705659910,
			"isDeleted": false,
			"id": "ZQhHCx6pafzbukgKW947i",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -783.7549605546404,
			"y": 424.08482970387087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#be4bdb",
			"width": 163.07767248490075,
			"height": 85.10616032805763,
			"seed": 299741655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-84.08692487502697
				],
				[
					141.41891910799984,
					-84.5965426015423
				],
				[
					163.07767248490075,
					-84.5965426015423
				],
				[
					162.3132458951278,
					-12.99525202614052
				],
				[
					113.6447530129152,
					-14.01448747917118
				],
				[
					102.17835416632067,
					0.5096177265153301
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 865,
			"versionNonce": 1671374682,
			"isDeleted": false,
			"id": "6bz8o8eI0UdsIPTNnmClq",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -761.330227930009,
			"y": 391.4539460811771,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 834496185,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 651,
			"versionNonce": 114103110,
			"isDeleted": false,
			"id": "n9LnC_8w7W3jeKUTO98VN",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -718.341373596316,
			"y": 391.5353622255112,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 2125604761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 723,
			"versionNonce": 1723149338,
			"isDeleted": false,
			"id": "LSChgucRVJcq0ffwfXhnL",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -696.8653377300277,
			"y": 391.62499509640554,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1427885177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 777,
			"versionNonce": 1805040262,
			"isDeleted": false,
			"id": "FxjifoGi6nnkuvuie6Ei6",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.3653748215446,
			"y": 391.62407585216647,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 2092815705,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 849,
			"versionNonce": 1244436698,
			"isDeleted": false,
			"id": "55zMgj9kSlKBZCRxaXBlc",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -653.8893389552563,
			"y": 391.7137087230608,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 2028716601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 346,
			"versionNonce": 791247302,
			"isDeleted": false,
			"id": "_ajyYIY-fUXqC66HdpO-E",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -772.8364694118472,
			"y": 263.48965076574757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 74.85485854058857,
			"height": 20.61407464112594,
			"seed": 2104333911,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.773616339689283,
					-20.61407464112594
				],
				[
					74.85485854058857,
					-20.485236674618903
				],
				[
					53.33891813391335,
					-0.12883796650703516
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 515,
			"versionNonce": 1301835162,
			"isDeleted": false,
			"id": "7Az0-8-HkEJOgq8Ikudvj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -610.7371546522045,
			"y": 317.9669485237093,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#228be6",
			"width": 161.78768995423184,
			"height": 55.10672408921437,
			"seed": 444170841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-33.44083256695916
				],
				[
					-107.85845996948774,
					-32.734336104276935
				],
				[
					-108.09395879038198,
					-54.8712252683203
				],
				[
					-161.78768995423184,
					-53.92922998474398
				],
				[
					-161.3166923124437,
					0.23549882089406537
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 974,
			"versionNonce": 1218597126,
			"isDeleted": false,
			"id": "7UV_qPWb3ll_sYWlWUvAZ",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -740.1812970042669,
			"y": 575.7365619072441,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.44551741989038696,
			"height": 364.87876689022664,
			"seed": 1722713305,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "oCzBy6ct",
				"focus": 4.204152008870341,
				"gap": 4.5456987450317
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
					0.44551741989038696,
					-364.87876689022664
				]
			]
		},
		{
			"type": "line",
			"version": 503,
			"versionNonce": 1177266778,
			"isDeleted": false,
			"id": "JCoQaNuLjkQH49_woFi4X",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -784.849880426131,
			"y": 424.66383454798233,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 142.05446296179207,
			"height": 32.159287317967426,
			"seed": 1501880025,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					119.51181518699889,
					0
				],
				[
					96.61134760625657,
					31.84596272946976
				],
				[
					-22.54264777479318,
					32.159287317967426
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 1784,
			"versionNonce": 1132347462,
			"isDeleted": false,
			"id": "Cj_4sHoOBFn3rP7hQHbaX",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -836.6508752139932,
			"y": 489.80029558344336,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 193.5276537146184,
			"height": 193.4002787992304,
			"seed": 1343914425,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "KcRCK2lT",
				"focus": -1.22415930753315,
				"gap": 6.780138569012934
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					193.5276537146184,
					-193.4002787992304
				]
			]
		},
		{
			"type": "line",
			"version": 742,
			"versionNonce": 1790529306,
			"isDeleted": false,
			"id": "_egmUutMc3NSmqtYxLswB",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -632.2656194635997,
			"y": 391.6044033913374,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 378082073,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 814,
			"versionNonce": 865748870,
			"isDeleted": false,
			"id": "bb6JvsgfoebJZ9n6M7kjA",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -610.7895835973115,
			"y": 391.69403626223163,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 973686777,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 868,
			"versionNonce": 531913690,
			"isDeleted": false,
			"id": "uigZG8ddMw3Y_Ya8gMkTM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -589.2896206888281,
			"y": 391.69311701799256,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1836048601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 940,
			"versionNonce": 691234502,
			"isDeleted": false,
			"id": "ZXcLvmsyZqzPr9Q0RBWA6",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -567.8135848225397,
			"y": 391.782749888887,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 777018809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 645,
			"versionNonce": 1127207066,
			"isDeleted": false,
			"id": "XKIWffmwGZQkm5k5ETwOU",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.3148621444789,
			"y": 562.9131864537953,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 2077114009,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 715,
			"versionNonce": 619093510,
			"isDeleted": false,
			"id": "9HfboKCtkcq9B-47DPvo5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.2252292735844,
			"y": 541.5936877123964,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 614269817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 769,
			"versionNonce": 2027859290,
			"isDeleted": false,
			"id": "BJO4Mspa7nKS9RVXGR8Y-",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.2261485178237,
			"y": 520.0937248039133,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1426074713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 841,
			"versionNonce": 196144454,
			"isDeleted": false,
			"id": "ChfG8EuUFzOFzTmQSnUV4",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.1365156469293,
			"y": 498.6176889376254,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1691040057,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 734,
			"versionNonce": 1981018650,
			"isDeleted": false,
			"id": "FXWyzzYxOrKsRjbhZr43r",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.2458209786528,
			"y": 476.9939694459688,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1700899353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 806,
			"versionNonce": 451892358,
			"isDeleted": false,
			"id": "N5DoKVFSzf1kYVrnx8uUJ",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.1561881077585,
			"y": 455.51793357968074,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1874263801,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 861,
			"versionNonce": 1304600282,
			"isDeleted": false,
			"id": "iiU46f_fuack0KyE9qQGB",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.1571073519976,
			"y": 434.0179706711973,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 844019673,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 933,
			"versionNonce": 1549718470,
			"isDeleted": false,
			"id": "gkpktQvAr0NPIoHnoxCXG",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -740.0674744811033,
			"y": 412.54193480490915,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1060918457,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 719,
			"versionNonce": 1014870938,
			"isDeleted": false,
			"id": "9iI10aAy5YGXuh8bF3Oe7",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.9860583367689,
			"y": 369.55308047121594,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 438523289,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 791,
			"versionNonce": 438070022,
			"isDeleted": false,
			"id": "31CYojauLsldPdP4qI6H6",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.8964254658749,
			"y": 348.07704460492783,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 104282745,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 845,
			"versionNonce": 1954033754,
			"isDeleted": false,
			"id": "gh8k4sBa0w4T8csta87Et",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.897344710114,
			"y": 326.57708169644457,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 339444569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 917,
			"versionNonce": 1386551878,
			"isDeleted": false,
			"id": "zttocyxae58ICIh3JEAq-",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.8077118392193,
			"y": 305.10104583015624,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1887678521,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 810,
			"versionNonce": 1770329370,
			"isDeleted": false,
			"id": "A5kfWNU-rvVH0exbuorLs",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.917017170943,
			"y": 283.47732633849944,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1894990105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 889,
			"versionNonce": 752214406,
			"isDeleted": false,
			"id": "vzX_36fzeWZB0u4o0EVVk",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.8273843000486,
			"y": 262.0012904722115,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 1660794361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 981,
			"versionNonce": 488071642,
			"isDeleted": false,
			"id": "Ni0Ne0SC2rnJ2cpp0vp7A",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.8283035442879,
			"y": 240.50132756372824,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 430345945,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "line",
			"version": 1009,
			"versionNonce": 1810612422,
			"isDeleted": false,
			"id": "SjnLljnDDHBJ9BWi31DKn",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.71238898038469,
			"x": -739.7386706733935,
			"y": 219.0252916974399,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 4.123112061140448,
			"seed": 998329273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					4.123112061140448
				]
			]
		},
		{
			"type": "text",
			"version": 601,
			"versionNonce": 1782716058,
			"isDeleted": false,
			"id": "KcRCK2lT",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -829.8707366449803,
			"y": 484.00468138410906,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.783660888671875,
			"height": 5.962504620871954,
			"seed": 1353804953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Cj_4sHoOBFn3rP7hQHbaX",
					"type": "arrow"
				}
			],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"fontSize": 4.968753850726628,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.2,
			"baseline": 3
		},
		{
			"type": "text",
			"version": 498,
			"versionNonce": 1669576710,
			"isDeleted": false,
			"id": "oCzBy6ct",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -735.1900808393448,
			"y": 214.93343453307187,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.8332061767578125,
			"height": 5.962504620871954,
			"seed": 283799929,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7UV_qPWb3ll_sYWlWUvAZ",
					"type": "arrow"
				}
			],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"fontSize": 4.968753850726628,
			"fontFamily": 1,
			"text": "z",
			"rawText": "z",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "z",
			"lineHeight": 1.2,
			"baseline": 3
		},
		{
			"type": "text",
			"version": 488,
			"versionNonce": 1371026266,
			"isDeleted": false,
			"id": "XTwvgc3N",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -566.6995107608371,
			"y": 396.2579526146292,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.323028564453125,
			"height": 5.962504620871954,
			"seed": 1903155801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "jPEEKu0c1XAgx9yJ2Yg_S",
					"type": "arrow"
				}
			],
			"updated": 1705249911002,
			"link": null,
			"locked": false,
			"fontSize": 4.968753850726628,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.2,
			"baseline": 3
		},
		{
			"type": "line",
			"version": 172,
			"versionNonce": 1805305670,
			"isDeleted": false,
			"id": "W2iNfPedsZmh7VRLd9WZ4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -740.2184366401953,
			"y": 418.4112986513865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 0,
			"height": 17.57596180816381,
			"seed": 1829050265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					17.57596180816381
				]
			]
		},
		{
			"type": "line",
			"version": 591,
			"versionNonce": 1171044378,
			"isDeleted": false,
			"id": "OJEAdwvRFYhJt-pM4U6CZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -622.4082730139868,
			"y": 339.8929147411962,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#7950f2",
			"width": 173.86890371405184,
			"height": 21.77363803417228,
			"seed": 1968402359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.84742069506433,
					-21.45343747484617
				],
				[
					-150.49426288324923,
					-21.133236915520115
				],
				[
					-162.0214830189875,
					0.3202005593261106
				],
				[
					2.5616044746085436,
					-0.32020055932605374
				]
			]
		},
		{
			"type": "line",
			"version": 519,
			"versionNonce": 1418587782,
			"isDeleted": false,
			"id": "xfpT1d50xdAt_HSMQiDP6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -688.1705277636464,
			"y": 457.0503186399684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#eebefa",
			"width": 28.07703703456002,
			"height": 47.276775594957826,
			"seed": 727996473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.748322439668186,
					-16.928801741425957
				],
				[
					18.37394335349893,
					-47.276775594957826
				],
				[
					23.328714594891835,
					-32.41246187077894
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 747,
			"versionNonce": 1987224794,
			"isDeleted": false,
			"id": "Cqx1E3MPO_mPaXT3l3Wfw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -693.4967852210483,
			"y": 440.12151689854244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#eebefa",
			"width": 71.09043831615145,
			"height": 30.34797385353187,
			"seed": 1857410007,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.12226579316723,
					-30.34797385353187
				],
				[
					71.09043831615145,
					-30.247444760167355
				],
				[
					55.23232571208166,
					-0.08363379122749848
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 1034,
			"versionNonce": 1528442310,
			"isDeleted": false,
			"id": "jPEEKu0c1XAgx9yJ2Yg_S",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -922.5628489390929,
			"y": 393.47548347983127,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 365.47903540537635,
			"height": 0,
			"seed": 2135714809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "XTwvgc3N",
				"focus": 1.933322256911229,
				"gap": 7.292668662667552
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
					365.47903540537635,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 210,
			"versionNonce": 490535322,
			"isDeleted": false,
			"id": "olW1j93F8kUtFmMyZ_a41",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -739.9368277609229,
			"y": 317.28744980481235,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#7950f2",
			"width": 0.17514811327725965,
			"height": 23.99529151899179,
			"seed": 52712569,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.17514811327725965,
					23.99529151899179
				]
			]
		},
		{
			"type": "freedraw",
			"version": 289,
			"versionNonce": 475825414,
			"isDeleted": false,
			"id": "GI49ovo-t6Gsm86Tz9iib",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -714.4226765835915,
			"y": 369.5013050178977,
			"strokeColor": "#be4bdb",
			"backgroundColor": "#7950f2",
			"width": 19.588807053612754,
			"height": 18.627393210490595,
			"seed": 1502255351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.06008836519515626,
					0.060088365195099414
				],
				[
					-0.12017673039031251,
					-0.06008836519515626
				],
				[
					-0.18026509558535508,
					-0.12017673039025567
				],
				[
					-0.24035346078051134,
					-0.18026509558541193
				],
				[
					-0.24035346078051134,
					-0.3004418259756676
				],
				[
					-0.24035346078051134,
					-0.36053019117082385
				],
				[
					-0.3004418259756676,
					-0.36053019117082385
				],
				[
					-0.36053019117082385,
					-0.4807069215610795
				],
				[
					-0.4206185563658664,
					-0.5407952867561789
				],
				[
					-0.4206185563658664,
					-0.6008836519513352
				],
				[
					-0.4807069215610227,
					-0.6609720171464346
				],
				[
					-0.5407952867561789,
					-0.7210603823415909
				],
				[
					-0.5407952867561789,
					-0.7811487475367471
				],
				[
					-0.6008836519513352,
					-0.8412371127318465
				],
				[
					-0.4807069215610227,
					-0.9013254779270028
				],
				[
					-0.36053019117082385,
					-0.9614138431221022
				],
				[
					-0.24035346078051134,
					-0.9614138431221022
				],
				[
					-0.12017673039031251,
					-1.0215022083172585
				],
				[
					0,
					-1.0815905735123579
				],
				[
					0.24035346078051134,
					-1.1416789387075141
				],
				[
					0.36053019117082385,
					-1.2017673039026135
				],
				[
					0.4807069215610227,
					-1.321944034292926
				],
				[
					0.6008836519513352,
					-1.3820323994880255
				],
				[
					0.721060382341534,
					-1.4421207646831817
				],
				[
					0.7811487475366903,
					-1.5022091298782811
				],
				[
					0.9013254779270028,
					-1.5622974950734374
				],
				[
					0.9614138431220454,
					-1.6223858602685368
				],
				[
					1.0815905735123579,
					-1.7425625906587925
				],
				[
					1.2017673039026704,
					-1.8026509558539487
				],
				[
					1.261855669097713,
					-1.862739321049105
				],
				[
					1.3820323994880255,
					-1.9829160514393607
				],
				[
					1.502209129878338,
					-2.04300441663446
				],
				[
					1.5622974950733806,
					-2.1631811470247158
				],
				[
					1.682474225463693,
					-2.223269512219872
				],
				[
					1.8627393210490482,
					-2.403534607805284
				],
				[
					1.9829160514393607,
					-2.5237113381955396
				],
				[
					2.1030927818295595,
					-2.583799703390639
				],
				[
					2.1631811470247158,
					-2.6438880685857953
				],
				[
					2.343446242610071,
					-2.764064798976051
				],
				[
					2.6438880685857384,
					-2.944329894561463
				],
				[
					2.88424152936625,
					-3.184683355341974
				],
				[
					3.124594990146761,
					-3.3649484509273293
				],
				[
					3.30486008573223,
					-3.5452135465127412
				],
				[
					3.4250368161224287,
					-3.6053019117078975
				],
				[
					3.6053019117078975,
					-3.725478642098153
				],
				[
					3.7254786420980963,
					-3.845655372488409
				],
				[
					3.845655372488409,
					-3.9658321028786645
				],
				[
					4.146097198464076,
					-4.08600883326892
				],
				[
					4.266273928854275,
					-4.206185563659176
				],
				[
					4.386450659244588,
					-4.3263622940494315
				],
				[
					4.566715754829943,
					-4.506627389634843
				],
				[
					4.746980850415412,
					-4.626804120025099
				],
				[
					4.8671575808056105,
					-4.686892485220255
				],
				[
					4.987334311195923,
					-4.807069215610511
				],
				[
					5.107511041586122,
					-4.927245946000767
				],
				[
					5.287776137171477,
					-5.107511041586179
				],
				[
					5.407952867561789,
					-5.227687771976434
				],
				[
					5.5882179631471445,
					-5.468041232756946
				],
				[
					5.888659789122812,
					-5.708394693537457
				],
				[
					6.129013249903323,
					-5.948748154317968
				],
				[
					6.429455075878991,
					-6.1891016150985365
				],
				[
					6.729896901854659,
					-6.489543441074147
				],
				[
					6.910161997440014,
					-6.609720171464403
				],
				[
					7.030338727830326,
					-6.7298969018547155
				],
				[
					7.150515458220639,
					-6.850073632244971
				],
				[
					7.2706921886108375,
					-6.9101619974400705
				],
				[
					7.39086891900115,
					-7.030338727830326
				],
				[
					7.571134014586505,
					-7.150515458220582
				],
				[
					7.691310744976818,
					-7.330780553805994
				],
				[
					7.8114874753670165,
					-7.39086891900115
				],
				[
					7.931664205757329,
					-7.511045649391406
				],
				[
					8.051840936147528,
					-7.631222379781661
				],
				[
					8.17201766653784,
					-7.751399110171917
				],
				[
					8.29219439692804,
					-7.871575840562173
				],
				[
					8.412371127318352,
					-8.051840936147585
				],
				[
					8.592636222903707,
					-8.23210603173294
				],
				[
					8.71281295329402,
					-8.352282762123252
				],
				[
					8.832989683684218,
					-8.472459492513508
				],
				[
					9.013254779269687,
					-8.71281295329402
				],
				[
					9.193519874855042,
					-8.893078048879431
				],
				[
					9.373784970440397,
					-9.073343144464786
				],
				[
					9.554050066025866,
					-9.253608240050198
				],
				[
					9.674226796416065,
					-9.373784970440454
				],
				[
					9.854491892001533,
					-9.614138431220965
				],
				[
					10.154933717977087,
					-9.854491892001477
				],
				[
					10.335198813562556,
					-10.094845352782045
				],
				[
					10.635640639538224,
					-10.335198813562556
				],
				[
					10.815905735123579,
					-10.455375543952812
				],
				[
					11.05625919590409,
					-10.695729004733323
				],
				[
					11.236524291489445,
					-10.875994100318735
				],
				[
					11.536966117465113,
					-11.116347561099246
				],
				[
					11.657142847855425,
					-11.236524291489502
				],
				[
					11.83740794344078,
					-11.416789387074914
				],
				[
					11.897496308635937,
					-11.657142847855425
				],
				[
					12.01767303902625,
					-11.777319578245681
				],
				[
					12.077761404221292,
					-11.837407943440837
				],
				[
					12.137849769416448,
					-12.017673039026192
				],
				[
					12.318114865001803,
					-12.197938134611604
				],
				[
					12.37820323019696,
					-12.31811486500186
				],
				[
					12.498379960587272,
					-12.498379960587272
				],
				[
					12.61855669097747,
					-12.738733421367783
				],
				[
					12.79882178656294,
					-12.918998516953195
				],
				[
					12.918998516953138,
					-13.03917524734345
				],
				[
					12.979086882148295,
					-13.159351977733706
				],
				[
					13.099263612538607,
					-13.279528708123962
				],
				[
					13.15935197773365,
					-13.399705438514218
				],
				[
					13.279528708123962,
					-13.57997053409963
				],
				[
					13.399705438514161,
					-13.700147264489885
				],
				[
					13.459793803709317,
					-13.820323994880141
				],
				[
					13.640058899294672,
					-14.000589090465553
				],
				[
					13.760235629684985,
					-14.120765820855809
				],
				[
					13.820323994880141,
					-14.240942551246064
				],
				[
					13.880412360075297,
					-14.36111928163632
				],
				[
					14.000589090465496,
					-14.481296012026576
				],
				[
					14.120765820855809,
					-14.661561107611988
				],
				[
					14.240942551246007,
					-14.841826203197343
				],
				[
					14.36111928163632,
					-15.022091298782755
				],
				[
					14.481296012026519,
					-15.202356394368167
				],
				[
					14.661561107611988,
					-15.382621489953522
				],
				[
					14.781737838002186,
					-15.502798220343777
				],
				[
					14.901914568392499,
					-15.62297495073409
				],
				[
					15.082179663977854,
					-15.803240046319445
				],
				[
					15.202356394368167,
					-15.9234167767097
				],
				[
					15.382621489953522,
					-16.103681872295112
				],
				[
					15.442709855148678,
					-16.16377023749027
				],
				[
					15.562886585538877,
					-16.283946967880524
				],
				[
					15.68306331592919,
					-16.40412369827078
				],
				[
					15.863328411514544,
					-16.524300428661036
				],
				[
					16.043593507100013,
					-16.64447715905129
				],
				[
					16.163770237490212,
					-16.764653889441547
				],
				[
					16.283946967880524,
					-16.824742254636703
				],
				[
					16.46421206346588,
					-16.884830619831803
				],
				[
					16.584388793856192,
					-16.94491898502696
				],
				[
					16.764653889441547,
					-17.125184080612314
				],
				[
					16.884830619831746,
					-17.18527244580747
				],
				[
					17.12518408061237,
					-17.365537541392882
				],
				[
					17.185272445807414,
					-17.365537541392882
				],
				[
					17.365537541392882,
					-17.485714271783138
				],
				[
					17.48571427178308,
					-17.545802636978237
				],
				[
					17.605891002173394,
					-17.605891002173394
				],
				[
					17.726067732563592,
					-17.665979367368493
				],
				[
					17.846244462953905,
					-17.786156097758806
				],
				[
					18.02650955853926,
					-17.90633282814906
				],
				[
					18.086597923734416,
					-17.96642119334416
				],
				[
					18.26686301931977,
					-18.086597923734416
				],
				[
					18.326951384514928,
					-18.146686288929573
				],
				[
					18.44712811490524,
					-18.146686288929573
				],
				[
					18.507216480100396,
					-18.206774654124672
				],
				[
					18.56730484529544,
					-18.26686301931983
				],
				[
					18.627393210490595,
					-18.326951384514985
				],
				[
					18.68748157568575,
					-18.326951384514985
				],
				[
					18.747569940880908,
					-18.387039749710084
				],
				[
					18.80765830607595,
					-18.44712811490524
				],
				[
					18.80765830607595,
					-18.50721648010034
				],
				[
					18.867746671271107,
					-18.50721648010034
				],
				[
					18.927835036466263,
					-18.567304845295496
				],
				[
					18.98792340166142,
					-18.567304845295496
				],
				[
					18.98792340166142,
					-18.567304845295496
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 237,
			"versionNonce": 1230943834,
			"isDeleted": false,
			"id": "RWhF0AvCW02XcofMteEgy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -691.3487443486612,
			"y": 346.12693095699177,
			"strokeColor": "#be4bdb",
			"backgroundColor": "#7950f2",
			"width": 7.571134014586505,
			"height": 2.6438880685857384,
			"seed": 1799954937,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.06008836519515626,
					0
				],
				[
					-0.12017673039031251,
					0
				],
				[
					-0.24035346078062503,
					0
				],
				[
					-0.3004418259756676,
					0
				],
				[
					-0.48070692156113637,
					-0.06008836519515626
				],
				[
					-0.5407952867561789,
					-0.06008836519515626
				],
				[
					-0.6609720171464915,
					-0.12017673039025567
				],
				[
					-0.7210603823416477,
					-0.18026509558541193
				],
				[
					-0.8412371127318465,
					-0.24035346078051134
				],
				[
					-0.9013254779270028,
					-0.42061855636592327
				],
				[
					-0.961413843122159,
					-0.5407952867561789
				],
				[
					-0.961413843122159,
					-0.6609720171464346
				],
				[
					-1.0215022083173153,
					-0.7811487475366903
				],
				[
					-0.961413843122159,
					-0.8412371127318465
				],
				[
					-0.9013254779270028,
					-0.901325477926946
				],
				[
					-0.6609720171464915,
					-1.0815905735123579
				],
				[
					-0.48070692156113637,
					-1.2618556690977698
				],
				[
					-0.36053019117082385,
					-1.3219440342928692
				],
				[
					-0.24035346078062503,
					-1.5022091298782811
				],
				[
					-0.18026509558546877,
					-1.6223858602685368
				],
				[
					-0.12017673039031251,
					-1.6223858602685368
				],
				[
					-0.06008836519515626,
					-1.682474225463693
				],
				[
					0.12017673039019883,
					-1.7425625906587925
				],
				[
					0.3004418259755539,
					-1.7425625906587925
				],
				[
					0.5407952867561789,
					-1.7425625906587925
				],
				[
					0.7811487475366903,
					-1.7425625906587925
				],
				[
					1.0215022083172016,
					-1.7425625906587925
				],
				[
					1.3219440342928692,
					-1.682474225463693
				],
				[
					1.5622974950733806,
					-1.682474225463693
				],
				[
					1.6824742254635794,
					-1.682474225463693
				],
				[
					1.802650955853892,
					-1.7425625906587925
				],
				[
					1.9228276862440907,
					-1.8026509558539487
				],
				[
					2.0430044166344032,
					-1.8627393210490482
				],
				[
					2.1030927818295595,
					-1.9228276862442044
				],
				[
					2.1631811470247158,
					-1.9829160514393038
				],
				[
					2.2232695122197583,
					-2.04300441663446
				],
				[
					2.2833578774149146,
					-2.04300441663446
				],
				[
					2.403534607805227,
					-2.1631811470247158
				],
				[
					2.523711338195426,
					-2.2833578774149714
				],
				[
					2.583799703390582,
					-2.3434462426101277
				],
				[
					2.6438880685857384,
					-2.4636229730003834
				],
				[
					2.7640647989759373,
					-2.5237113381954828
				],
				[
					2.8241531641710935,
					-2.583799703390639
				],
				[
					2.88424152936625,
					-2.6438880685857384
				],
				[
					2.88424152936625,
					-2.583799703390639
				],
				[
					2.8241531641710935,
					-2.4636229730003834
				],
				[
					2.7640647989759373,
					-2.403534607805227
				],
				[
					2.7640647989759373,
					-2.3434462426101277
				],
				[
					2.7039764337808947,
					-2.2833578774149714
				],
				[
					2.7039764337808947,
					-2.223269512219872
				],
				[
					2.6438880685857384,
					-2.223269512219872
				],
				[
					2.583799703390582,
					-2.223269512219872
				],
				[
					2.4636229730002697,
					-2.1631811470247158
				],
				[
					2.403534607805227,
					-2.1631811470247158
				],
				[
					2.403534607805227,
					-2.1030927818296163
				],
				[
					2.343446242610071,
					-2.04300441663446
				],
				[
					2.2833578774149146,
					-2.04300441663446
				],
				[
					2.2833578774149146,
					-1.9829160514393038
				],
				[
					2.343446242610071,
					-1.9829160514393038
				],
				[
					2.4636229730002697,
					-1.9829160514393038
				],
				[
					2.6438880685857384,
					-2.04300441663446
				],
				[
					2.7640647989759373,
					-2.1030927818296163
				],
				[
					2.8241531641710935,
					-2.1030927818296163
				],
				[
					2.88424152936625,
					-2.1631811470247158
				],
				[
					2.944329894561406,
					-2.223269512219872
				],
				[
					3.064506624951605,
					-2.2833578774149714
				],
				[
					3.124594990146761,
					-2.2833578774149714
				],
				[
					3.24477172053696,
					-2.3434462426101277
				],
				[
					3.3649484509272725,
					-2.3434462426101277
				],
				[
					3.5452135465126275,
					-2.3434462426101277
				],
				[
					3.66539027690294,
					-2.403534607805227
				],
				[
					3.845655372488295,
					-2.403534607805227
				],
				[
					3.9658321028786077,
					-2.403534607805227
				],
				[
					4.025920468073764,
					-2.403534607805227
				],
				[
					4.206185563659119,
					-2.403534607805227
				],
				[
					4.266273928854275,
					-2.403534607805227
				],
				[
					4.326362294049318,
					-2.403534607805227
				],
				[
					4.386450659244474,
					-2.403534607805227
				],
				[
					4.506627389634787,
					-2.403534607805227
				],
				[
					4.566715754829943,
					-2.3434462426101277
				],
				[
					4.626804120024985,
					-2.3434462426101277
				],
				[
					4.686892485220142,
					-2.2833578774149714
				],
				[
					4.746980850415298,
					-2.2833578774149714
				],
				[
					4.807069215610454,
					-2.2833578774149714
				],
				[
					4.8671575808056105,
					-2.2833578774149714
				],
				[
					5.0474226763909655,
					-2.2833578774149714
				],
				[
					5.167599406781164,
					-2.2833578774149714
				],
				[
					5.287776137171477,
					-2.2833578774149714
				],
				[
					5.347864502366633,
					-2.2833578774149714
				],
				[
					5.468041232756832,
					-2.2833578774149714
				],
				[
					5.528129597951988,
					-2.2833578774149714
				],
				[
					5.648306328342301,
					-2.2833578774149714
				],
				[
					5.7684830587325,
					-2.2833578774149714
				],
				[
					5.828571423927656,
					-2.2833578774149714
				],
				[
					5.948748154317968,
					-2.2833578774149714
				],
				[
					6.008836519513011,
					-2.2833578774149714
				],
				[
					6.068924884708167,
					-2.2833578774149714
				],
				[
					6.18910161509848,
					-2.2833578774149714
				],
				[
					6.249189980293522,
					-2.2833578774149714
				],
				[
					6.3092783454886785,
					-2.2833578774149714
				],
				[
					6.369366710683835,
					-2.2833578774149714
				],
				[
					6.429455075878991,
					-2.2833578774149714
				],
				[
					6.489543441074034,
					-2.2833578774149714
				],
				[
					6.54963180626919,
					-2.2833578774149714
				],
				[
					6.54963180626919,
					-2.223269512219872
				],
				[
					6.54963180626919,
					-2.223269512219872
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 1057,
			"versionNonce": 164754502,
			"isDeleted": false,
			"id": "RyQxwHUgtj1FQCoh2AyBv",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -719.5349307866076,
			"y": 368.75766506932416,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1546629303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1084,
			"versionNonce": 732617498,
			"isDeleted": false,
			"id": "PFshIuBL4-d7UnkrtEWoN",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -729.4701647839902,
			"y": 378.4901391892089,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 516037943,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1074,
			"versionNonce": 1566014342,
			"isDeleted": false,
			"id": "uGy3xqLEkD4PMlpKoVU33",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -756.8427482461659,
			"y": 405.65996277388695,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 186941751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1067,
			"versionNonce": 1653893082,
			"isDeleted": false,
			"id": "maSwZBK1v7llQmAsNrp3U",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -771.4414594259929,
			"y": 420.03506912135174,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 1339268599,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1065,
			"versionNonce": 220863174,
			"isDeleted": false,
			"id": "cBwo___K4US3RWpegH_Kx",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -784.6000065084721,
			"y": 433.0325462360628,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 638259639,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 1064,
			"versionNonce": 1177443482,
			"isDeleted": false,
			"id": "D8qG4_k6sqUhPy0RUE44s",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -796.7864441131926,
			"y": 445.4008987634163,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 325719863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "line",
			"version": 698,
			"versionNonce": 1072091654,
			"isDeleted": false,
			"id": "wsvw5t5Mkx7J19-kO7krH",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -806.5231075011892,
			"y": 455.2767087037457,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.082480593004741,
			"height": 4.082480593004798,
			"seed": 616027193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.082480593004741,
					4.082480593004798
				]
			]
		},
		{
			"type": "freedraw",
			"version": 200,
			"versionNonce": 875280730,
			"isDeleted": false,
			"id": "pmqxeyhmDoNEBadUrKfOF",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -667.2454443603016,
			"y": 316.9541572667971,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 7.384699383738393,
			"height": 0.27350738458289925,
			"seed": 890054679,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.03418842307291925,
					0
				],
				[
					0.06837684614572481,
					0
				],
				[
					0.17094211536436887,
					0
				],
				[
					0.3076958076558185,
					0
				],
				[
					0.4444494999472681,
					0
				],
				[
					0.5812031922387177,
					0
				],
				[
					0.7179568845301674,
					0
				],
				[
					0.7863337306758922,
					0
				],
				[
					0.8888989998944226,
					0
				],
				[
					0.9914642691130666,
					0
				],
				[
					1.0598411152587914,
					0.034188423072862406
				],
				[
					1.1282179614045162,
					0.034188423072862406
				],
				[
					1.2307832306230466,
					0.034188423072862406
				],
				[
					1.3333484998416907,
					0.034188423072862406
				],
				[
					1.435913769060221,
					0.034188423072862406
				],
				[
					1.5042906152059459,
					0.034188423072862406
				],
				[
					1.5726674613516707,
					0.034188423072862406
				],
				[
					1.6752327305703147,
					0.034188423072862406
				],
				[
					1.7777979997888451,
					0.06837684614572481
				],
				[
					1.9145516920802947,
					0.10256526921858722
				],
				[
					2.017116961298939,
					0.10256526921858722
				],
				[
					2.0854938074446636,
					0.10256526921858722
				],
				[
					2.2222474997361132,
					0.10256526921858722
				],
				[
					2.3248127689546436,
					0.10256526921858722
				],
				[
					2.4273780381732877,
					0.10256526921858722
				],
				[
					2.529943307391818,
					0.10256526921858722
				],
				[
					2.6666969996832677,
					0.10256526921858722
				],
				[
					2.7350738458289925,
					0.10256526921858722
				],
				[
					2.8376391150476366,
					0.10256526921858722
				],
				[
					2.940204384266167,
					0.10256526921858722
				],
				[
					3.042769653484811,
					0.10256526921858722
				],
				[
					3.1453349227033414,
					0.10256526921858722
				],
				[
					3.282088614994791,
					0.10256526921858722
				],
				[
					3.384653884213435,
					0.10256526921858722
				],
				[
					3.5897844226506095,
					0.10256526921858722
				],
				[
					3.726538114942059,
					0.10256526921858722
				],
				[
					3.8291033841605895,
					0.10256526921858722
				],
				[
					4.000045499524958,
					0.10256526921858722
				],
				[
					4.068422345670683,
					0.10256526921858722
				],
				[
					4.205176037962133,
					0.10256526921858722
				],
				[
					4.341929730253582,
					0.10256526921858722
				],
				[
					4.478683422545032,
					0.10256526921858722
				],
				[
					4.649625537909287,
					0.10256526921858722
				],
				[
					4.7863792302008505,
					0.10256526921858722
				],
				[
					4.9231329224923,
					0.10256526921858722
				],
				[
					5.05988661478375,
					0.10256526921858722
				],
				[
					5.16245188400228,
					0.10256526921858722
				],
				[
					5.2650171532208105,
					0.10256526921858722
				],
				[
					5.40177084551226,
					0.10256526921858722
				],
				[
					5.504336114730904,
					0.10256526921858722
				],
				[
					5.606901383949548,
					0.10256526921858722
				],
				[
					5.709466653168079,
					0.10256526921858722
				],
				[
					5.8804087685324475,
					0.10256526921858722
				],
				[
					6.017162460823897,
					0.10256526921858722
				],
				[
					6.1197277300424275,
					0.10256526921858722
				],
				[
					6.256481422333877,
					0.10256526921858722
				],
				[
					6.359046691552521,
					0.10256526921858722
				],
				[
					6.495800383843971,
					0.10256526921858722
				],
				[
					6.564177229989696,
					0.06837684614572481
				],
				[
					6.6325540761354205,
					0.06837684614572481
				],
				[
					6.735119345353951,
					0.06837684614572481
				],
				[
					6.803496191499676,
					0.034188423072862406
				],
				[
					6.90606146071832,
					0.034188423072862406
				],
				[
					6.9744383068640445,
					0
				],
				[
					7.042815153009769,
					0
				],
				[
					7.1453804222283,
					-0.034188423072862406
				],
				[
					7.179568845301219,
					-0.034188423072862406
				],
				[
					7.2137572683740245,
					-0.034188423072862406
				],
				[
					7.247945691446944,
					-0.034188423072862406
				],
				[
					7.282134114519749,
					-0.06837684614572481
				],
				[
					7.350510960665474,
					-0.06837684614572481
				],
				[
					7.384699383738393,
					-0.06837684614572481
				],
				[
					7.384699383738393,
					-0.10256526921858722
				],
				[
					7.384699383738393,
					-0.13675369229144962
				],
				[
					7.384699383738393,
					-0.17094211536431203
				],
				[
					7.384699383738393,
					-0.17094211536431203
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 179,
			"versionNonce": 1082827078,
			"isDeleted": false,
			"id": "5d1aGbx-oHooKeXs6oh3E",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -660.6470787072391,
			"y": 315.89431615153836,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 6.461611960771052,
			"height": 1.025652692185929,
			"seed": 1520577495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.03418842307280556,
					0
				],
				[
					-0.13675369229144962,
					0
				],
				[
					-0.3076958076557048,
					0
				],
				[
					-0.5128263460928792,
					0
				],
				[
					-0.8205221537486977,
					0
				],
				[
					-1.094029538331597,
					0
				],
				[
					-1.5042906152059459,
					-0.034188423072862406
				],
				[
					-1.84617484593457,
					-0.10256526921864406
				],
				[
					-2.119682230517469,
					-0.13675369229144962
				],
				[
					-2.359001192027563,
					-0.17094211536436887
				],
				[
					-2.5641317304647373,
					-0.20513053843717444
				],
				[
					-2.7350738458289925,
					-0.20513053843717444
				],
				[
					-2.940204384266167,
					-0.2393189615100937
				],
				[
					-3.111146499630536,
					-0.2393189615100937
				],
				[
					-3.2479001919219854,
					-0.2393189615100937
				],
				[
					-3.350465461140516,
					-0.2393189615100937
				],
				[
					-3.5897844226506095,
					-0.2393189615100937
				],
				[
					-3.794914961087784,
					-0.2393189615100937
				],
				[
					-3.965857076452039,
					-0.2393189615100937
				],
				[
					-4.1709876148892135,
					-0.2393189615100937
				],
				[
					-4.307741307180663,
					-0.2393189615100937
				],
				[
					-4.478683422545032,
					-0.2393189615100937
				],
				[
					-4.615437114836482,
					-0.2393189615100937
				],
				[
					-4.6838139609822065,
					-0.2393189615100937
				],
				[
					-4.786379230200737,
					-0.2393189615100937
				],
				[
					-4.6838139609822065,
					-0.2393189615100937
				],
				[
					-4.376118153326388,
					-0.17094211536436887
				],
				[
					-3.965857076452039,
					-0.10256526921864406
				],
				[
					-3.5555959995776902,
					-0.034188423072862406
				],
				[
					-3.213711768849066,
					0
				],
				[
					-2.871827538120442,
					0.034188423072862406
				],
				[
					-2.4615664612460932,
					0.034188423072862406
				],
				[
					-2.290624345881838,
					0.034188423072862406
				],
				[
					-1.948740115153214,
					0.10256526921858722
				],
				[
					-1.7094211536431203,
					0.13675369229144962
				],
				[
					-1.3675369229144962,
					0.17094211536431203
				],
				[
					-1.1282179614044026,
					0.20513053843717444
				],
				[
					-0.8205221537486977,
					0.23931896151003684
				],
				[
					-0.6153916153115233,
					0.30769580765576166
				],
				[
					-0.27350738458289925,
					0.4102610768743489
				],
				[
					0.03418842307291925,
					0.4444494999472113
				],
				[
					0.27350738458289925,
					0.4786379230200737
				],
				[
					0.4786379230200737,
					0.5470147691657985
				],
				[
					0.5812031922387177,
					0.5470147691657985
				],
				[
					0.7179568845301674,
					0.6153916153115233
				],
				[
					0.854710576821617,
					0.6495800383843857
				],
				[
					0.9914642691130666,
					0.6837684614572481
				],
				[
					1.196594807550241,
					0.7179568845301105
				],
				[
					1.3675369229144962,
					0.7521453076029729
				],
				[
					1.4701021921331403,
					0.7521453076029729
				],
				[
					1.5726674613516707,
					0.7521453076029729
				],
				[
					1.6410443074973955,
					0.7521453076029729
				],
				[
					1.6410443074973955,
					0.7863337306758353
				],
				[
					1.6752327305703147,
					0.7863337306758353
				],
				[
					1.6752327305703147,
					0.7863337306758353
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 192,
			"versionNonce": 1541373466,
			"isDeleted": false,
			"id": "ibmjAJrqeMliwZLoaMCml",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -641.568733454262,
			"y": 294.828623778399,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 15.72233406127907,
			"height": 16.46096720509769,
			"seed": 1928846743,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.10551902054544371,
					0
				],
				[
					-0.3165570616364448,
					0.2110380410910011
				],
				[
					-0.8441521643638907,
					0.7386331438185039
				],
				[
					-1.3717472670914503,
					1.2662282465460066
				],
				[
					-1.7938233492734525,
					1.7938233492735094
				],
				[
					-2.1103804109098974,
					2.2158994314554548
				],
				[
					-2.637975513637457,
					2.849013554728458
				],
				[
					-2.954532575273902,
					3.1655706163649597
				],
				[
					-3.2710896369103466,
					3.587646698546962
				],
				[
					-3.4821276780013477,
					3.9042037601834636
				],
				[
					-3.90420376018335,
					4.4317988629109095
				],
				[
					-4.115241801274351,
					4.642836904001911
				],
				[
					-4.4317988629109095,
					5.170432006729413
				],
				[
					-4.642836904001797,
					5.486989068365915
				],
				[
					-4.959393965638355,
					5.909065150547917
				],
				[
					-5.064912986183799,
					6.120103191638918
				],
				[
					-5.1704320067293565,
					6.43666025327542
				],
				[
					-5.486989068365801,
					6.753217314911865
				],
				[
					-5.6980271094568025,
					6.964255356002866
				],
				[
					-6.014584171093361,
					7.280812417639368
				],
				[
					-6.120103191638805,
					7.597369479275869
				],
				[
					-6.436660253275363,
					7.913926540912371
				],
				[
					-6.647698294366364,
					8.124964582003372
				],
				[
					-6.858736335457252,
					8.336002623094373
				],
				[
					-7.17529339709381,
					8.652559684730875
				],
				[
					-7.386331438184811,
					8.863597725821876
				],
				[
					-7.8084075203668135,
					9.07463576691282
				],
				[
					-8.019445561457815,
					9.285673808003821
				],
				[
					-8.33600262309426,
					9.602230869640323
				],
				[
					-8.441521643639817,
					9.707749890185823
				],
				[
					-8.758078705276262,
					10.024306951822325
				],
				[
					-8.969116746367263,
					10.235344992913326
				],
				[
					-9.180154787458264,
					10.340864013458827
				],
				[
					-9.391192828549265,
					10.657421075095328
				],
				[
					-9.602230869640266,
					10.86845911618633
				],
				[
					-9.91878793127671,
					11.185016177822774
				],
				[
					-10.129825972367712,
					11.290535198368275
				],
				[
					-10.340864013458713,
					11.607092260004777
				],
				[
					-10.551902054549714,
					11.818130301095778
				],
				[
					-10.762940095640715,
					12.029168342186779
				],
				[
					-11.079497157277274,
					12.451244424368781
				],
				[
					-11.290535198368161,
					12.662282465459782
				],
				[
					-11.60709226000472,
					12.978839527096284
				],
				[
					-11.81813030109572,
					13.189877568187228
				],
				[
					-12.556763444914168,
					13.822991691460231
				],
				[
					-12.873320506550726,
					14.034029732551232
				],
				[
					-13.189877568187171,
					14.350586794187734
				],
				[
					-13.506434629823616,
					14.561624835278735
				],
				[
					-13.822991691460174,
					14.772662876369736
				],
				[
					-14.034029732551176,
					14.878181896915237
				],
				[
					-14.13954875309662,
					14.983700917460737
				],
				[
					-14.35058679418762,
					15.194738958551739
				],
				[
					-14.561624835278622,
					15.300257979097239
				],
				[
					-14.561624835278622,
					15.405776999642683
				],
				[
					-14.667143855824179,
					15.51129602018824
				],
				[
					-14.772662876369623,
					15.616815040733684
				],
				[
					-14.87818189691518,
					15.616815040733684
				],
				[
					-14.983700917460624,
					15.722334061279184
				],
				[
					-15.089219938006181,
					15.827853081824685
				],
				[
					-15.194738958551625,
					15.933372102370186
				],
				[
					-15.300257979097182,
					16.038891122915686
				],
				[
					-15.405776999642626,
					16.144410143461187
				],
				[
					-15.511296020188183,
					16.144410143461187
				],
				[
					-15.511296020188183,
					16.249929164006687
				],
				[
					-15.616815040733627,
					16.249929164006687
				],
				[
					-15.616815040733627,
					16.355448184552188
				],
				[
					-15.72233406127907,
					16.355448184552188
				],
				[
					-15.72233406127907,
					16.46096720509769
				],
				[
					-15.72233406127907,
					16.46096720509769
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 431,
			"versionNonce": 1920108678,
			"isDeleted": false,
			"id": "BevEo91SW8_7yLyz8yU8k",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -611.6718930219611,
			"y": 284.2043321092035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#15aabf",
			"width": 128.80772065016436,
			"height": 21.22808804011092,
			"seed": 723696217,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					22.487381398422485,
					-19.788895630611847
				],
				[
					-84.91235216044356,
					-19.249198477049674
				],
				[
					-106.32033925174187,
					1.4391924094990713
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 300,
			"versionNonce": 171748058,
			"isDeleted": false,
			"id": "wQVl4-y7EpcOatWossTvU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -718.7118284784524,
			"y": 285.2837264163278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#15aabf",
			"width": 22.4873813984226,
			"height": 42.63607513140914,
			"seed": 2059570583,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5396971535622015,
					-21.767785193673035
				],
				[
					21.228088040110833,
					-42.63607513140914
				],
				[
					21.947684244860397,
					-19.96879468179924
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 215,
			"versionNonce": 1163626438,
			"isDeleted": false,
			"id": "gKqpAoS1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -224.74237269666344,
			"y": 68.10813872818352,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 377.9637695236678,
			"height": 77.45159211550569,
			"seed": 73142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "602fc71879689f2a4016156dc09706da613b2064",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 248,
			"versionNonce": 1976975258,
			"isDeleted": false,
			"id": "dnl7-CbVnR00ELQHS2Ae5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 970.4642334984147,
			"y": 726.1738044553565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 599.7878365774549,
			"height": 281.79687149544213,
			"seed": 1657649497,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "LrWSgTy9",
				"focus": 0.10231212627424259,
				"gap": 16.39894288625044
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
					65.92495617553948,
					166.7513597381286
				],
				[
					540.3261113995176,
					184.84840653141396
				],
				[
					599.7878365774549,
					281.79687149544213
				]
			]
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 694329094,
			"isDeleted": false,
			"id": "LrWSgTy9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1301.9041733614872,
			"y": 1024.369618837049,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 540.0943603515625,
			"height": 70,
			"seed": 1305952281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "dnl7-CbVnR00ELQHS2Ae5",
					"type": "arrow"
				}
			],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we find the most optimal binary\npartition?",
			"rawText": "How do we find the most optimal binary\npartition?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we find the most optimal binary\npartition?",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 182402138,
			"isDeleted": false,
			"id": "MX9MzVUn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1412.5135854452494,
			"y": 1146.3000738173646,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 334.27978515625,
			"height": 75,
			"seed": 1612481049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CANT!!!! VERY BAD!!! BAD DOG!!!\nNP DIFFICULTY!!!\nABORT ABORT!",
			"rawText": "CANT!!!! VERY BAD!!! BAD DOG!!!\nNP DIFFICULTY!!!\nABORT ABORT!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CANT!!!! VERY BAD!!! BAD DOG!!!\nNP DIFFICULTY!!!\nABORT ABORT!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 22,
			"versionNonce": 50646598,
			"isDeleted": false,
			"id": "NbdxxyjJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1510.5609344967488,
			"y": 1111.94548269707,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 139.94459533691406,
			"height": 35,
			"seed": 1513496281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "WARNING!",
			"rawText": "WARNING!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "WARNING!",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "ellipse",
			"version": 2847,
			"versionNonce": 925540634,
			"isDeleted": false,
			"id": "51VL7Z-yT1NG3kUUt7Go8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1742.2419206518937,
			"y": 1064.472237179723,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 72.06379738031175,
			"height": 66.32784572067462,
			"seed": 2059684729,
			"groupIds": [
				"1KlKODuq4pVthVM-NzduW",
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2911,
			"versionNonce": 522130822,
			"isDeleted": false,
			"id": "l0ivSdNBV71iGd5WLLFSH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1781.3373536766164,
			"y": 1130.432469796439,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 3.536045493705738,
			"height": 80.41129408968958,
			"seed": 1996387417,
			"groupIds": [
				"1KlKODuq4pVthVM-NzduW",
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.536045493705738,
					80.41129408968958
				]
			]
		},
		{
			"type": "line",
			"version": 2864,
			"versionNonce": 908815834,
			"isDeleted": false,
			"id": "3jp4yWTeQCoOIivD9HFS3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1785.3307376766322,
			"y": 1212.9031695666995,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 31.83115762177455,
			"height": 49.03901260068592,
			"seed": 1069580601,
			"groupIds": [
				"1KlKODuq4pVthVM-NzduW",
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.83115762177455,
					49.03901260068592
				]
			]
		},
		{
			"type": "line",
			"version": 2841,
			"versionNonce": 653161670,
			"isDeleted": false,
			"id": "DCXEH8SM90dVEHonWeJMl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1789.242211550229,
			"y": 1209.7283086389157,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 27.235648115641727,
			"height": 45.55695253436506,
			"seed": 1114501657,
			"groupIds": [
				"1KlKODuq4pVthVM-NzduW",
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.235648115641727,
					45.55695253436506
				]
			]
		},
		{
			"type": "line",
			"version": 2902,
			"versionNonce": 1559536282,
			"isDeleted": false,
			"id": "IIRT-fqOtXdQVLeDKH3Sb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1826.211860067011,
			"y": 1176.1255547003852,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 42.08481154773555,
			"height": 26.955103993318286,
			"seed": 1945782009,
			"groupIds": [
				"1KlKODuq4pVthVM-NzduW",
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-42.08481154773555,
					-26.955103993318286
				]
			]
		},
		{
			"type": "line",
			"version": 2945,
			"versionNonce": 336587782,
			"isDeleted": false,
			"id": "lu0AYBkBpt4F4ABJvr4jc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1785.6344036475925,
			"y": 1147.6247637928814,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 30.106414594301825,
			"height": 35.87326254755846,
			"seed": 1592328153,
			"groupIds": [
				"1KlKODuq4pVthVM-NzduW",
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.106414594301825,
					35.87326254755846
				]
			]
		},
		{
			"type": "text",
			"version": 645,
			"versionNonce": 1715027802,
			"isDeleted": false,
			"id": "tZTuJb55",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1749.3245985967892,
			"y": 1095.5731505758522,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 49.690399169921875,
			"height": 33.787594642246304,
			"seed": 1900911801,
			"groupIds": [
				"GvYXeQjjnfFhJ3_hWUFVc"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 23.850066806291526,
			"fontFamily": 1,
			"text": "ಠ_ಠ",
			"rawText": "ಠ_ಠ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ಠ_ಠ",
			"lineHeight": 1.4166666666666656,
			"baseline": 22
		},
		{
			"type": "arrow",
			"version": 121,
			"versionNonce": 612399942,
			"isDeleted": false,
			"id": "dglu6BUJAO5gdfGFZgI1i",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1230.2137553411521,
			"y": 1183.8000736305835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 524.2859707676997,
			"height": 1.6591328188851548,
			"seed": 1557695513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
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
					-524.2859707676997,
					-1.6591328188851548
				]
			]
		},
		{
			"type": "text",
			"version": 71,
			"versionNonce": 1045185562,
			"isDeleted": false,
			"id": "ZfPef9xN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 887.4604331074676,
			"y": 1145.6400187962251,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 162.8798065185547,
			"height": 25,
			"seed": 613670711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Oh okay I guess",
			"rawText": "Oh okay I guess",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Oh okay I guess",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 277,
			"versionNonce": 1318920838,
			"isDeleted": false,
			"id": "QjE-F97VMwXspIjOlE9IB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 968.070770051706,
			"y": 726.5836830144011,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 599.787836577455,
			"height": 281.7968714954422,
			"seed": 1111459575,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
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
					-65.92495617553949,
					166.75135973812863
				],
				[
					-540.3261113995177,
					184.84840653141399
				],
				[
					-599.787836577455,
					281.7968714954422
				]
			]
		},
		{
			"type": "text",
			"version": 52,
			"versionNonce": 1327542490,
			"isDeleted": false,
			"id": "STc1R3xG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 252.38273089904123,
			"y": 1028.5212918505317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 228.6489715576172,
			"height": 35,
			"seed": 1793500153,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Greedy Algorithm",
			"rawText": "Greedy Algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Greedy Algorithm",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 891478470,
			"isDeleted": false,
			"id": "OrZd6P3k",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 38.87324882924423,
			"y": 1079.874076842919,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 649.3992309570312,
			"height": 75,
			"seed": 653505111,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given N datapoints (xi,yi)\nsuch that xi has P features \nWe consider the two half planes splitting up feature j by value s",
			"rawText": "Given N datapoints (xi,yi)\nsuch that xi has P features \nWe consider the two half planes splitting up feature j by value s",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given N datapoints (xi,yi)\nsuch that xi has P features \nWe consider the two half planes splitting up feature j by value s",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 36,
			"versionNonce": 1279886746,
			"isDeleted": false,
			"id": "dDOTAkYF8mRSGQEmdYa5M",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 56.931086960848916,
			"y": 1161.726609648736,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 629,
			"height": 53,
			"seed": 1906583543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "de669187b9fc85cb113907cc38e433711f9f5ba2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 456046854,
			"isDeleted": false,
			"id": "qa3ajZVF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 98.75328792324387,
			"y": 1217.5732232511752,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 570.7593383789062,
			"height": 25,
			"seed": 1053871447,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We seek such j and s values as they define our paritions",
			"rawText": "We seek such j and s values as they define our paritions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We seek such j and s values as they define our paritions",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 40,
			"versionNonce": 2130297434,
			"isDeleted": false,
			"id": "5-e5Pqi3SkT_qxdPRRaLx",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 49.832201760971884,
			"y": 1250.8928623960262,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 662,
			"height": 105,
			"seed": 1831030679,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2106759a162a3aa2b2bf8d996460342e1630d855",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 50,
			"versionNonce": 1480435782,
			"isDeleted": false,
			"id": "yrvLKqAYD_FVMy6AnOcr8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 350.52816988006015,
			"y": 1317.7532917275037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 1.1408878783047385,
			"height": 78.15081966387129,
			"seed": 1253132087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1408878783047385,
					78.15081966387129
				]
			]
		},
		{
			"type": "text",
			"version": 148,
			"versionNonce": 302278426,
			"isDeleted": false,
			"id": "nBgrLBn6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 270.82080960315136,
			"y": 1402.1930536395955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 159.2003173828125,
			"height": 60,
			"seed": 726297945,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Error measurement \nbetween decision of \nR1 half and y label",
			"rawText": "Error measurement \nbetween decision of \nR1 half and y label",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Error measurement \nbetween decision of \nR1 half and y label",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 44,
			"versionNonce": 1277996934,
			"isDeleted": false,
			"id": "pltq0RtDw-F3ZbUI5jZ7P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 211.339848726888,
			"y": 1353.6912598941012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 31.944860592531313,
			"height": 70.16460451573857,
			"seed": 1609199289,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.944860592531313,
					70.16460451573857
				]
			]
		},
		{
			"type": "text",
			"version": 54,
			"versionNonce": 1574728666,
			"isDeleted": false,
			"id": "xFBXXuTv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 121.89069092496604,
			"y": 1430.5671962272968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 88.76817321777344,
			"height": 40,
			"seed": 1392323577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "for every x\nin R1 half",
			"rawText": "for every x\nin R1 half",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for every x\nin R1 half",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 89,
			"versionNonce": 1396231878,
			"isDeleted": false,
			"id": "uoV_SD3tCTvhSpP_lDEMw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 699.0215329261586,
			"y": 1317.3321477724069,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 1.1408878783047385,
			"height": 78.15081966387129,
			"seed": 1617557367,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1408878783047385,
					78.15081966387129
				]
			]
		},
		{
			"type": "text",
			"version": 188,
			"versionNonce": 882174106,
			"isDeleted": false,
			"id": "UiU9G3OH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 618.2090186327794,
			"y": 1402.8770637009693,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 159.2003173828125,
			"height": 60,
			"seed": 1565126807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Error measurement \nbetween decision of \nR2 half and y label",
			"rawText": "Error measurement \nbetween decision of \nR2 half and y label",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Error measurement \nbetween decision of \nR2 half and y label",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 83,
			"versionNonce": 973014534,
			"isDeleted": false,
			"id": "eeHnqDaO2ITi-EIMdfxcb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 559.8332117729865,
			"y": 1353.2701159390042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 31.944860592531313,
			"height": 70.16460451573857,
			"seed": 1779287479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.944860592531313,
					70.16460451573857
				]
			]
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 769705306,
			"isDeleted": false,
			"id": "C43ebJ4n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 471.98818420301916,
			"y": 1424.6560160516808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 88.76817321777344,
			"height": 40,
			"seed": 366606039,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "for every x\nin R2 half",
			"rawText": "for every x\nin R2 half",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for every x\nin R2 half",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 47,
			"versionNonce": 830231878,
			"isDeleted": false,
			"id": "bvicFqWk64supVRfrCa1-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 78.83183809441664,
			"y": 1327.2620098466825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 59.43255784146487,
			"height": 68.26712725033144,
			"seed": 857306743,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-59.43255784146487,
					68.26712725033144
				]
			]
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 1930627610,
			"isDeleted": false,
			"id": "ogiSJH0C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -51.51289015720448,
			"y": 1403.029137097014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 141.8243408203125,
			"height": 60,
			"seed": 33827991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Minimize partitions\nsuch that the\nerror is minimal",
			"rawText": "Minimize partitions\nsuch that the\nerror is minimal",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Minimize partitions\nsuch that the\nerror is minimal",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 1338,
			"versionNonce": 1124973702,
			"isDeleted": false,
			"id": "kLHmyI1TcfVkA9kXWihmf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 799.3717685662043,
			"y": 1448.156355740218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 709.8829899784091,
			"height": 41.248757270727694,
			"seed": 801789177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.873888415517968,
					0.7779194324375408
				],
				[
					16.24137158371002,
					10.895628892010034
				],
				[
					-6.2393104157495145,
					23.234298964659622
				],
				[
					-270.65495107606023,
					23.234298964659622
				],
				[
					-322.039367074825,
					31.624594614061323
				],
				[
					-332.7444537412343,
					41.248757270727694
				],
				[
					-333.53063175398376,
					32.98835663749264
				],
				[
					-373.4237830735898,
					22.987525563206646
				],
				[
					-661.3906144000013,
					28.16976699371938
				],
				[
					-693.5058743992291,
					17.558510731240943
				],
				[
					-678.5187530662561,
					6.947254468762331
				],
				[
					-693.6416183946991,
					7.944778632349503
				]
			]
		},
		{
			"type": "image",
			"version": 205,
			"versionNonce": 186562266,
			"isDeleted": false,
			"id": "ppbJhOcpZYYkziLIpk46l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 272.8937738314763,
			"y": 1490.1400975413483,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 390.1938248373543,
			"height": 28.903246284248468,
			"seed": 1352797271,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ac728d66f270bb07e3b8a43ca335f2e6440476fc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 1148206022,
			"isDeleted": false,
			"id": "FJ4Hsk2Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 350.13729571336177,
			"y": 1519.178386523495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 227.1524658203125,
			"height": 20,
			"seed": 1047874713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "mean of y value in each half",
			"rawText": "mean of y value in each half",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "mean of y value in each half",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 486,
			"versionNonce": 647416730,
			"isDeleted": false,
			"id": "_ZWjQJMLp-Q6wxfhzLfTz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 87.77103498947122,
			"y": 1457.8471147668984,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 139.32933769451586,
			"height": 39.69571696579601,
			"seed": 1808273207,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.731939770757151,
					-3.680397599477601
				],
				[
					0.2628855428198449,
					14.984475940731045
				],
				[
					-62.82964473394205,
					15.247361483550776
				],
				[
					-69.40178330443808,
					25.499897653524613
				],
				[
					-68.61312667597855,
					36.01531936631841
				],
				[
					-73.3450664467357,
					24.185469939425502
				],
				[
					-81.49451827415078,
					16.561789197650114
				],
				[
					-136.17471118067775,
					17.087560283289804
				],
				[
					-134.07162683811902,
					-1.3144277140991107
				],
				[
					-139.066452151696,
					-0.2628855428197312
				]
			]
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1270928134,
			"isDeleted": false,
			"id": "XJjw2crD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -135.59370722280738,
			"y": 1502.3576025389837,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 333.29962158203125,
			"height": 75,
			"seed": 1322326585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Scan through all features P\nand determine optimal j and s for\neach feature",
			"rawText": "Scan through all features P\nand determine optimal j and s for\neach feature",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Scan through all features P\nand determine optimal j and s for\neach feature",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1806583898,
			"isDeleted": false,
			"id": "FiC8m2Gy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -828.2762025992533,
			"y": 162.05998782266462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 175.79978942871094,
			"height": 25,
			"seed": 572133047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Rgression Surface",
			"rawText": "Rgression Surface",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rgression Surface",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 595362374,
			"isDeleted": false,
			"id": "AU3cjKER",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -385.1164398738316,
			"y": 143.17102915409572,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 128.3998565673828,
			"height": 25,
			"seed": 234005177,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Decision tree",
			"rawText": "Decision tree",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Decision tree",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 497,
			"versionNonce": 1110977818,
			"isDeleted": false,
			"id": "SlCFWuIybcGhK6GAvaxO0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -465.8491855520643,
			"y": 626.4161149858136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 538.793386901895,
			"height": 244.4903115262896,
			"seed": 2019521977,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "SLDciDeV",
				"focus": -0.04718038937816932,
				"gap": 10.6480334543877
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
					-55.12053766079583,
					79.61172800646648
				],
				[
					-480.6609207581701,
					84.07562658076642
				],
				[
					-538.793386901895,
					244.4903115262896
				]
			]
		},
		{
			"type": "text",
			"version": 292,
			"versionNonce": 1048594822,
			"isDeleted": false,
			"id": "ctJMz5RS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1130.8133762380617,
			"y": 646.9009764232796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 586.2105712890625,
			"height": 35,
			"seed": 1608034713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we decide where to split the tree?",
			"rawText": "How do we decide where to split the tree?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we decide where to split the tree?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 531069402,
			"isDeleted": false,
			"id": "VuqVN3ef",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1334.7632329721835,
			"y": 909.4681025340211,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 716.499267578125,
			"height": 25,
			"seed": 1125533497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pzvXClb0j-EiD60WsaDeh",
					"type": "arrow"
				}
			],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We base the following on the concept of entropy from information theory",
			"rawText": "We base the following on the concept of entropy from information theory",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We base the following on the concept of entropy from information theory",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 737,
			"versionNonce": 738797766,
			"isDeleted": false,
			"id": "pzvXClb0j-EiD60WsaDeh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -603.070290963669,
			"y": 925.3306847225997,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 51.91838602530129,
			"height": 89.49740829123346,
			"seed": 714759351,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "VuqVN3ef",
				"focus": -0.8173498681632535,
				"gap": 15.193674430389478
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
					46.97377783241541,
					7.9113731086172265
				],
				[
					21.261815229408967,
					85.0472609176361
				],
				[
					51.91838602530129,
					89.49740829123346
				]
			]
		},
		{
			"type": "text",
			"version": 355,
			"versionNonce": 1393503898,
			"isDeleted": false,
			"id": "DSAMbCnV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -534.3887479948241,
			"y": 991.501559307562,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 91.40821838378906,
			"height": 40,
			"seed": 2084078489,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": "[[entropy]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "wtf is that\nshit?",
			"rawText": "wtf is that\nshit?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "wtf is that\nshit?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 292,
			"versionNonce": 196354054,
			"isDeleted": false,
			"id": "oq0MKWjJvh7r-dzA5xyD4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1262.4880846101767,
			"y": 947.8699474737269,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 584,
			"height": 31,
			"seed": 1062263639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "df75d4a28c64c65ed4986db4727836b7a0aa3b2e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 1361202010,
			"isDeleted": false,
			"id": "OqG6nZWr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -863.8280320271319,
			"y": 989.6066812264386,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 267.9365539550781,
			"height": 20,
			"seed": 184992409,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "weighted sum of entropy (Children)",
			"rawText": "weighted sum of entropy (Children)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "weighted sum of entropy (Children)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 25046854,
			"isDeleted": false,
			"id": "lWklG8Y2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1074.8101359191796,
			"y": 994.422126910959,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 129.1842803955078,
			"height": 20,
			"seed": 649921529,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Entropy (parent)",
			"rawText": "Entropy (parent)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Entropy (parent)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 3395610,
			"isDeleted": false,
			"id": "tYn30RwH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1269.0380734407488,
			"y": 991.105923155165,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 121.84028625488281,
			"height": 20,
			"seed": 1159455673,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "information gain",
			"rawText": "information gain",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "information gain",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 534,
			"versionNonce": 330466758,
			"isDeleted": false,
			"id": "R675f2LWJMh2dqNOsmwec",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -543.5458804481177,
			"y": 1037.3957630878617,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 266.70273483800133,
			"height": 40.63596835535222,
			"seed": 780916825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249926944,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bc2628c17514f27fea7b8db947f215f47a8c34c9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 768,
			"versionNonce": 70696154,
			"isDeleted": false,
			"id": "1ZZUDMwYFMBv7DYa85b_w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -685.6512816750446,
			"y": 971.6716929356354,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 95.83151116938436,
			"height": 23.586983374517757,
			"seed": 783831063,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2546550963187215,
					-2.186872630749887
				],
				[
					0.18081417201771188,
					8.903695710910737
				],
				[
					-43.21458711223181,
					9.059900898821386
				],
				[
					-47.73494141267446,
					15.151903227339236
				],
				[
					-47.192498896621345,
					21.40011074376787
				],
				[
					-50.44715399294006,
					14.370877287785726
				],
				[
					-56.052393325488964,
					9.840926838375033
				],
				[
					-93.66174110517187,
					10.153337214196464
				],
				[
					-92.21522772903023,
					-0.781025939553512
				],
				[
					-95.65069699736665,
					-0.1562051879106483
				]
			]
		},
		{
			"type": "line",
			"version": 753,
			"versionNonce": 222533062,
			"isDeleted": false,
			"id": "99PBujQRg0ERhA8dMM7Gw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -960.8968486384244,
			"y": 973.5594474127294,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 95.14829923443462,
			"height": 19.4447375939032,
			"seed": 1328843737,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2314516721128825,
					-1.8028233530770323
				],
				[
					0.17952509289516172,
					7.340066508956887
				],
				[
					-42.906497201943154,
					7.468839605605198
				],
				[
					-47.39462452432214,
					12.49099037489147
				],
				[
					-46.856049245636655,
					17.641914240826168
				],
				[
					-50.08750091774954,
					11.84712489164969
				],
				[
					-55.65277879749948,
					8.11270508884709
				],
				[
					-92.99399811969269,
					8.370251282143826
				],
				[
					-91.5577973765314,
					-0.6438654832417814
				],
				[
					-94.96877414153946,
					-0.1287730966483116
				]
			]
		},
		{
			"type": "line",
			"version": 765,
			"versionNonce": 180228506,
			"isDeleted": false,
			"id": "VuEYYB0W2g6Hrn5d2RR4y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1141.4133874262084,
			"y": 969.6586802953394,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 121.33809007417362,
			"height": 26.57860532718369,
			"seed": 1092471001,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.120916266670054,
					-2.464241553513603
				],
				[
					0.22893979259278296,
					10.032983467877354
				],
				[
					-54.71661042967452,
					10.20900072169969
				],
				[
					-60.44010524449402,
					17.073673620773647
				],
				[
					-59.753285866715686,
					24.11436377367009
				],
				[
					-63.87420213338572,
					16.193587351661666
				],
				[
					-70.97133570376192,
					11.089086990811822
				],
				[
					-118.59081256306024,
					11.441121498456644
				],
				[
					-116.759294222318,
					-0.8800862691119793
				],
				[
					-121.10915028158084,
					-0.17601725382233502
				]
			]
		},
		{
			"type": "line",
			"version": 1212,
			"versionNonce": 1344920838,
			"isDeleted": false,
			"id": "g7W3zMJrkJ-d2OppBg7mL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -382.1155937728454,
			"y": 1066.286891411023,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 93.05364799592807,
			"height": 14.433614441117404,
			"seed": 1172574359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249926944,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.160312573446618,
					-1.3382159084479077
				],
				[
					0.1755729207470384,
					5.448450484395347
				],
				[
					-41.96192805854114,
					5.544037334998735
				],
				[
					-46.351251077216986,
					9.271924508532381
				],
				[
					-45.8245323149759,
					13.095398532669495
				],
				[
					-48.984844888422494,
					8.793990255515284
				],
				[
					-54.42760543158057,
					6.021971588015915
				],
				[
					-90.94677294696365,
					6.21314528922277
				],
				[
					-89.54218958098737,
					-0.47793425301709813
				],
				[
					-92.87807507518103,
					-0.0955868506033865
				]
			]
		},
		{
			"type": "text",
			"version": 525,
			"versionNonce": 171199558,
			"isDeleted": false,
			"id": "IwrvfqbH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -472.5238156802716,
			"y": 1079.9088162342707,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 90.84182739257812,
			"height": 18.68320384154125,
			"seed": 490933463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249926944,
			"link": null,
			"locked": false,
			"fontSize": 7.4732815366165,
			"fontFamily": 1,
			"text": "probability of each class\npresent in the child node",
			"rawText": "probability of each class\npresent in the child node",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of each class\npresent in the child node",
			"lineHeight": 1.25,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 413,
			"versionNonce": 1675366874,
			"isDeleted": false,
			"id": "38xNvpBb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1259.7352117918253,
			"y": 1187.1892287184908,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 599.7393188476562,
			"height": 25,
			"seed": 1203058937,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705250216842,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Choose the split that results in the purest daughter node! ",
			"rawText": "Choose the split that results in the purest daughter node! ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Choose the split that results in the purest daughter node! ",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 743,
			"versionNonce": 1304818458,
			"isDeleted": false,
			"id": "ktZ7MBQCeWN2VKaCBhQuA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -927.0521283553471,
			"y": 703.7498681427084,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 860.6669530021088,
			"height": 135.95099247784708,
			"seed": 270645849,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-53.30848487477704,
					26.65424243738846
				],
				[
					-159.92545462433122,
					86.6262879215127
				],
				[
					-787.0310010732094,
					57.844027450340604
				],
				[
					-860.6669530021088,
					135.95099247784708
				]
			]
		},
		{
			"type": "arrow",
			"version": 118,
			"versionNonce": 1343873926,
			"isDeleted": false,
			"id": "XPYaPEZjzxUd29PwUILdv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1789.137375921033,
			"y": 803.483933224648,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 2.814530251552469,
			"height": 52.228181028891754,
			"seed": 1935620473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zj4BxxE0",
				"focus": 0.015462695197613369,
				"gap": 12.516899524207133
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
					2.814530251552469,
					52.228181028891754
				]
			]
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1099726810,
			"isDeleted": false,
			"id": "Zj4BxxE0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1847.090747760522,
			"y": 868.2290137777469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 122.31985473632812,
			"height": 25,
			"seed": 557204439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "XPYaPEZjzxUd29PwUILdv",
					"type": "arrow"
				}
			],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Gini Impurity",
			"rawText": "Gini Impurity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gini Impurity",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 106,
			"versionNonce": 1264550598,
			"isDeleted": false,
			"id": "mQ7RBmOt85klvvdenOJdl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1966.2288896342088,
			"y": 899.5094356733557,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 367.0300896964076,
			"height": 67.46035916538332,
			"seed": 2067658713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3f819d3f04892e93a38d6d7dde606d21ab4d69e6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 337,
			"versionNonce": 2022664218,
			"isDeleted": false,
			"id": "LtOdaowr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2060.7479121775796,
			"y": 976.8490138089728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 549.099365234375,
			"height": 100,
			"seed": 927491577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705250365288,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Choose a random element from the set\ngiven a distribution of labels in the subset we randomly\nlabel our element according to them\nThis impurity measures how often this is wrong",
			"rawText": "Choose a random element from the set\ngiven a distribution of labels in the subset we randomly\nlabel our element according to them\nThis impurity measures how often this is wrong",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Choose a random element from the set\ngiven a distribution of labels in the subset we randomly\nlabel our element according to them\nThis impurity measures how often this is wrong",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 406,
			"versionNonce": 1664039430,
			"isDeleted": false,
			"id": "YBKltKakNxj7hPNZsT-_2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1241.204032312496,
			"y": 786.2096219291241,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 496.7682145262106,
			"height": 538.6962020638832,
			"seed": 626266265,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "3QrLcI45",
				"focus": 0.06359657943021228,
				"gap": 10.300177240504354
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
					-199.93159411838133,
					29.355035644365444
				],
				[
					-241.3140806372171,
					426.80117368046444
				],
				[
					-479.4227039124289,
					465.4133828602287
				],
				[
					-496.7682145262106,
					538.6962020638832
				]
			]
		},
		{
			"type": "text",
			"version": 50,
			"versionNonce": 368955738,
			"isDeleted": false,
			"id": "SLDciDeV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1091.2248766814464,
			"y": 881.5544599664909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 164.57981872558594,
			"height": 25,
			"seed": 1249961849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SlCFWuIybcGhK6GAvaxO0",
					"type": "arrow"
				}
			],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Information Gain",
			"rawText": "Information Gain",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Information Gain",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 156,
			"versionNonce": 780536134,
			"isDeleted": false,
			"id": "3QrLcI45",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1905.4256149280466,
			"y": 1335.2060012335116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 304.379638671875,
			"height": 25,
			"seed": 59909593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YBKltKakNxj7hPNZsT-_2",
					"type": "arrow"
				}
			],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Variance reduction (Regression)",
			"rawText": "Variance reduction (Regression)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Variance reduction (Regression)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 257,
			"versionNonce": 1806603802,
			"isDeleted": false,
			"id": "dO2559FY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2046.0491307167688,
			"y": 1367.143776918516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 591.079345703125,
			"height": 75,
			"seed": 1219229495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The definition of variance reduction at a node is\nthe total reduction of the variance of the target variable\ndue to the split at this node",
			"rawText": "The definition of variance reduction at a node is\nthe total reduction of the variance of the target variable\ndue to the split at this node",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The definition of variance reduction at a node is\nthe total reduction of the variance of the target variable\ndue to the split at this node",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 229,
			"versionNonce": 1556148358,
			"isDeleted": false,
			"id": "ADt5qW2ggR1lkYrM_5p8G",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2106.40222397413,
			"y": 1452.2958429001517,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 721.0915231514916,
			"height": 77.68015320130324,
			"seed": 1525525913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0d46e13a9c2b7057e19acac310ca98b0a1e5394",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 306,
			"versionNonce": 6865626,
			"isDeleted": false,
			"id": "yFgNiMlg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1939.14174400021,
			"y": 1529.7993273301051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 391.8408203125,
			"height": 100,
			"seed": 1612096249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "s = set of pre-split sample indices\nst = set of pre-split sample indices for which the\nsplit test is true (indices go to the right)\nsf = set of pre-split sample indices for which the\nsplit test is false (indices go to the left)",
			"rawText": "s = set of pre-split sample indices\nst = set of pre-split sample indices for which the\nsplit test is true (indices go to the right)\nsf = set of pre-split sample indices for which the\nsplit test is false (indices go to the left)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s = set of pre-split sample indices\nst = set of pre-split sample indices for which the\nsplit test is true (indices go to the right)\nsf = set of pre-split sample indices for which the\nsplit test is false (indices go to the left)",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 86,
			"versionNonce": 698150854,
			"isDeleted": false,
			"id": "dLaoMni-AnTSLsmdogOEX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1905.4216422827226,
			"y": 866.7284309134437,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 152.56073265545865,
			"height": 48.50648935712013,
			"seed": 1942231417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
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
					-112.6602333455694,
					0
				],
				[
					-152.56073265545865,
					48.50648935712013
				]
			]
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 557449453,
			"isDeleted": false,
			"id": "xoHkiCyC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2163.7929027617683,
			"y": 929.3174494387601,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 175.6323699951172,
			"height": 40,
			"seed": 1427189879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705250371451,
			"link": "[[Gini impurity]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "who is Gini\nand why is she impure?",
			"rawText": "who is Gini\nand why is she impure?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "who is Gini\nand why is she impure?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 294,
			"versionNonce": 1362560774,
			"isDeleted": false,
			"id": "l8kPLBYr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -470.33955844961065,
			"y": 472.66135326279755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 168.4707794189453,
			"height": 19.52678329875626,
			"seed": 1182250265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 15.621426639005008,
			"fontFamily": 1,
			"text": "How deep is the tree?",
			"rawText": "How deep is the tree?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How deep is the tree?",
			"lineHeight": 1.25,
			"baseline": 13
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 1189434458,
			"isDeleted": false,
			"id": "z8thcB50",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -507.8294492848737,
			"y": 500.4094890899339,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 241.13449096679688,
			"height": 93.72855983403008,
			"seed": 392115033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 12.49714131120401,
			"fontFamily": 1,
			"text": "too deep = overfitting\ntoo shallow = does not capture all\n     the details\n\nWe need to split large enough to avoid\nboth",
			"rawText": "too deep = overfitting\ntoo shallow = does not capture all\n     the details\n\nWe need to split large enough to avoid\nboth",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "too deep = overfitting\ntoo shallow = does not capture all\n     the details\n\nWe need to split large enough to avoid\nboth",
			"lineHeight": 1.25,
			"baseline": 88
		},
		{
			"type": "arrow",
			"version": 734,
			"versionNonce": 67909190,
			"isDeleted": false,
			"id": "tuz4ZWO-tb_7OhtgzVjh7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -465.1661732702724,
			"y": 627.0835977587826,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 434.323456600325,
			"height": 714.1455485737783,
			"seed": 1657677721,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
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
					25.421616725760657,
					72.84617464677558
				],
				[
					261.658888348209,
					130.83399552118442
				],
				[
					242.466182551224,
					556.989505266195
				],
				[
					-141.55512159967162,
					584.7247915726962
				],
				[
					-172.664568252116,
					714.1455485737783
				]
			]
		},
		{
			"type": "text",
			"version": 28,
			"versionNonce": 984463642,
			"isDeleted": false,
			"id": "Lwjt68H8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.6863533345853,
			"y": 1357.6550129553752,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 65.18428039550781,
			"height": 35,
			"seed": 297022841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Idea",
			"rawText": "Idea",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1526300038,
			"isDeleted": false,
			"id": "mwzUR1kS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1004.1838432637845,
			"y": 1400.560893987483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 722.1792602539062,
			"height": 25,
			"seed": 332302135,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Grow tree large then prune it according to the cost complexity critereon",
			"rawText": "Grow tree large then prune it according to the cost complexity critereon",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Grow tree large then prune it according to the cost complexity critereon",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 44,
			"versionNonce": 160138714,
			"isDeleted": false,
			"id": "YP92A-ei4uSHFrD0lj--N",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -885.0367177528419,
			"y": 1424.5609264684008,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 477.99999999999994,
			"height": 188,
			"seed": 1630293657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d09e0e0bce2f63d54aee2c3496e2e5b56fe2688e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 102,
			"versionNonce": 1262214342,
			"isDeleted": false,
			"id": "a1ZOxm9VtLX5DIRpww3Mv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -527.9581816612808,
			"y": 1545.0172108415163,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 32.73511366329046,
			"height": 95.1602141374724,
			"seed": 742275607,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-32.73511366329046,
					26.64485995849236
				],
				[
					-31.21255023709091,
					95.1602141374724
				]
			]
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 2089925274,
			"isDeleted": false,
			"id": "AZIi1MtD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -612.522858973567,
			"y": 1645.1774249789887,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 106.70425415039062,
			"height": 40,
			"seed": 212837015,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "regularization\nparameter",
			"rawText": "regularization\nparameter",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "regularization\nparameter",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 190,
			"versionNonce": 443569158,
			"isDeleted": false,
			"id": "LH9_CPosrI3GEaAgFX80P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -480.3780745925444,
			"y": 1546.9204151242657,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 59.760614478332684,
			"height": 96.68277756367206,
			"seed": 1019310167,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					53.28971991698455,
					23.599733106093254
				],
				[
					59.760614478332684,
					96.68277756367206
				]
			]
		},
		{
			"type": "text",
			"version": 31,
			"versionNonce": 1114855258,
			"isDeleted": false,
			"id": "quWojizW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -481.5775888983914,
			"y": 1643.6031926879377,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 121.92025756835938,
			"height": 40,
			"seed": 1763399927,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Number of\nTerminal leaves",
			"rawText": "Number of\nTerminal leaves",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Number of\nTerminal leaves",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 176,
			"versionNonce": 1385423686,
			"isDeleted": false,
			"id": "xxy3iicncY5nWb8JuFoYJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -676.2559494527657,
			"y": 1547.3223013698728,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 116.08261740046123,
			"height": 108.74654120786704,
			"seed": 1496263479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.2946016810459469,
					28.481236983012877
				],
				[
					-94.07438882267854,
					31.933508132468887
				],
				[
					-116.08261740046123,
					108.74654120786704
				]
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 998464538,
			"isDeleted": false,
			"id": "c8m1mNG1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -885.2466347344671,
			"y": 1666.425656026108,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 163.37637329101562,
			"height": 60,
			"seed": 1749099161,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "num of training data\nin current region\nm",
			"rawText": "num of training data\nin current region\nm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "num of training data\nin current region\nm",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 252,
			"versionNonce": 906201734,
			"isDeleted": false,
			"id": "La7BfxRu6w0Dpojd3faNv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -606.0664772946018,
			"y": 1566.616951076297,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 80.79929269755917,
			"height": 151.4504425741968,
			"seed": 1457252473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1461560894003924,
					49.28471184422028
				],
				[
					-72.78091167693015,
					59.600116648824496
				],
				[
					-79.65313660815877,
					151.4504425741968
				]
			]
		},
		{
			"type": "image",
			"version": 195,
			"versionNonce": 1169475802,
			"isDeleted": false,
			"id": "cwBo5k9ngujVD8K0PrlWM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -819.4821531637855,
			"y": 1748.9300274617212,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"width": 265.2610359742939,
			"height": 61.487711404002994,
			"seed": 1763697209,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fdd2b621bcbbaa9d10a449ef745b081d21299d93",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 280,
			"versionNonce": 863783366,
			"isDeleted": false,
			"id": "YUh0ySj5SYl3c6c3Z1DlM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -585.7658851104313,
			"y": 1798.6476159693327,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 37.74982658622184,
			"height": 32.36352537370499,
			"seed": 1843152889,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2080246915510315,
					32.36352537370499
				],
				[
					37.74982658622184,
					30.789070246035863
				]
			]
		},
		{
			"type": "text",
			"version": 41,
			"versionNonce": 144350618,
			"isDeleted": false,
			"id": "SjkOcNFG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -734.6158185669741,
			"y": 1728.6383486845712,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 101.40821838378906,
			"height": 20,
			"seed": 894816887,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Squared loss",
			"rawText": "Squared loss",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Squared loss",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 1511727366,
			"isDeleted": false,
			"id": "dk8DOG29",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -557.4371569649829,
			"y": 1805.1225061718737,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 94.70420837402344,
			"height": 40,
			"seed": 1389638551,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Prediction in\nregion m",
			"rawText": "Prediction in\nregion m",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prediction in\nregion m",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 66,
			"versionNonce": 1097325146,
			"isDeleted": false,
			"id": "X1NtMXgTbTRQ4_Y8tWzcU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -625.8981930616412,
			"y": 1800.0215301060741,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 23.651413091619702,
			"height": 31.092307097972025,
			"seed": 962328889,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.797238643537753,
					26.04312902223296
				],
				[
					-22.85417444808195,
					31.092307097972025
				]
			]
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 1297944646,
			"isDeleted": false,
			"id": "KF50kMLo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -708.6239391807126,
			"y": 1814.3718256897537,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 51.71211242675781,
			"height": 40,
			"seed": 399250999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "actual\nlabel",
			"rawText": "actual\nlabel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "actual\nlabel",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 176,
			"versionNonce": 250576666,
			"isDeleted": false,
			"id": "5vFZ0x6JlkEeI093Chm6V",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -869.1482297400479,
			"y": 1534.7057870471808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 227.27446658395286,
			"height": 251.95585662021904,
			"seed": 2020372983,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "JgAVlrMi",
				"focus": -0.03214957311870687,
				"gap": 14.98265127568834
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
					-199.50790279315322,
					18.511042527199606
				],
				[
					-227.27446658395286,
					251.95585662021904
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 958338950,
			"isDeleted": false,
			"id": "JgAVlrMi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1236.6892826277115,
			"y": 1796.6442949430882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 280.5331726074219,
			"height": 35,
			"seed": 1642536121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5vFZ0x6JlkEeI093Chm6V",
					"type": "arrow"
				}
			],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Weakest Link pruning",
			"rawText": "Weakest Link pruning",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weakest Link pruning",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 363,
			"versionNonce": 1034193882,
			"isDeleted": false,
			"id": "SxNkW2lV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1447.1491848299827,
			"y": 1850.0965534683792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 682.3593139648438,
			"height": 150,
			"seed": 2026684057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Find the node with the lowest node contribution to the cost function\nthis node adds complexity and barely changes the cost\nthus we prune it in return for lower complexity\nwe calculate the cost for the new tree and repeat the pruning!\n\nFinally we can find the minimally complex tree with the best score!",
			"rawText": "Find the node with the lowest node contribution to the cost function\nthis node adds complexity and barely changes the cost\nthus we prune it in return for lower complexity\nwe calculate the cost for the new tree and repeat the pruning!\n\nFinally we can find the minimally complex tree with the best score!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Find the node with the lowest node contribution to the cost function\nthis node adds complexity and barely changes the cost\nthus we prune it in return for lower complexity\nwe calculate the cost for the new tree and repeat the pruning!\n\nFinally we can find the minimally complex tree with the best score!",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 49,
			"versionNonce": 1167996614,
			"isDeleted": false,
			"id": "RZdsBoWM_Dqy84Cuz9hi8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -969.0864198453667,
			"y": 347.5105219160478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 237.9636289558032,
			"height": 1.6298878695603207,
			"seed": 1566064569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705249911003,
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
					-237.9636289558032,
					-1.6298878695603207
				]
			]
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 328859802,
			"isDeleted": false,
			"id": "dcYIyU2O",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1514.9838521947613,
			"y": 223.92752773727696,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 148.5966339111328,
			"height": 35,
			"seed": 1445615705,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Why trees?",
			"rawText": "Why trees?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why trees?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 172,
			"versionNonce": 192376326,
			"isDeleted": false,
			"id": "0OK9lzcX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1662.7236623741642,
			"y": 287.68473741535615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 454.0194396972656,
			"height": 225,
			"seed": 913378137,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Interpretability\n\nGeneralizes to higher dimensions\n\ncan handle qualitive and quantitive predictors\n\nignored redundant variables\n\nHandles missing data",
			"rawText": "Interpretability\n\nGeneralizes to higher dimensions\n\ncan handle qualitive and quantitive predictors\n\nignored redundant variables\n\nHandles missing data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Interpretability\n\nGeneralizes to higher dimensions\n\ncan handle qualitive and quantitive predictors\n\nignored redundant variables\n\nHandles missing data",
			"lineHeight": 1.25,
			"baseline": 218
		},
		{
			"type": "text",
			"version": 76,
			"versionNonce": 478338394,
			"isDeleted": false,
			"id": "uzFC6xRD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1539.9234375063447,
			"y": 524.4216456173252,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 208.3797607421875,
			"height": 50,
			"seed": 1389047415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1705249911003,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Prone to overtfitting\nhigh variance!",
			"rawText": "Prone to overtfitting\nhigh variance!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prone to overtfitting\nhigh variance!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"id": "nNI2f8ft",
			"type": "text",
			"x": -1364.6045153684315,
			"y": 1022.8984103670045,
			"width": 792.939208984375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 375395142,
			"version": 118,
			"versionNonce": 1998508870,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705249935445,
			"link": null,
			"locked": false,
			"text": "Information gain is the expected reduction of entropy caused by a certain split",
			"rawText": "Information gain is the expected reduction of entropy caused by a certain split",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Information gain is the expected reduction of entropy caused by a certain split",
			"lineHeight": 1.25
		},
		{
			"id": "AfTgFRlJ7cChFTgBATgCD",
			"type": "image",
			"x": -1178.9686408461303,
			"y": 1066.1660698315618,
			"width": 434.86194145023353,
			"height": 66.26467679241654,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#99e9f2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 639211014,
			"version": 111,
			"versionNonce": 264213850,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705250045324,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "39d3974d96d121eda383867ac6d42f9c96dfab0c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 829,
			"versionNonce": 1272276806,
			"isDeleted": false,
			"id": "jzf90wH8cooFxIMRCK2Ha",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -847.7606776201765,
			"y": 1120.1632162118021,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 34.335618714627515,
			"height": 10.968847635203538,
			"seed": 708890970,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250148988,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1661153525722554,
					-1.0169792509459752
				],
				[
					0.06478418625401616,
					4.140558378851694
				],
				[
					-15.48342051470938,
					4.213199753919238
				],
				[
					-17.10302517105974,
					7.0462133815545975
				],
				[
					-16.908672612297693,
					9.951868384257564
				],
				[
					-18.074787964869955,
					6.683006506216758
				],
				[
					-20.083097738744385,
					4.576406629257139
				],
				[
					-33.558208479579335,
					4.721689379392288
				],
				[
					-33.03993498954722,
					-0.36320687533783924
				],
				[
					-34.2708345283735,
					-0.07264137506754265
				]
			]
		},
		{
			"id": "XaCGwP3Y",
			"type": "text",
			"x": -915.1817793897618,
			"y": 1136.8481701124801,
			"width": 69.85368347167969,
			"height": 35.6968521016981,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 623693254,
			"version": 152,
			"versionNonce": 1655958810,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705250171613,
			"link": null,
			"locked": false,
			"text": "how often this\nvalue occurs in\ndataset",
			"rawText": "how often this\nvalue occurs in\ndataset",
			"fontSize": 9.519160560452827,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 31,
			"containerId": null,
			"originalText": "how often this\nvalue occurs in\ndataset",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 779,
			"versionNonce": 941394822,
			"isDeleted": false,
			"id": "1-js2QsSQe2NT3UdO5NXH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -750.2620795390826,
			"y": 1112.1645021027207,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"width": 95.14829923443462,
			"height": 19.4447375939032,
			"seed": 1619423046,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1705250175580,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2314516721128825,
					-1.8028233530770323
				],
				[
					0.17952509289516172,
					7.340066508956887
				],
				[
					-42.906497201943154,
					7.468839605605198
				],
				[
					-47.39462452432214,
					12.49099037489147
				],
				[
					-46.856049245636655,
					17.641914240826168
				],
				[
					-50.08750091774954,
					11.84712489164969
				],
				[
					-55.65277879749948,
					8.11270508884709
				],
				[
					-92.99399811969269,
					8.370251282143826
				],
				[
					-91.5577973765314,
					-0.6438654832417814
				],
				[
					-94.96877414153946,
					-0.1287730966483116
				]
			]
		},
		{
			"id": "Ba8U18rI",
			"type": "text",
			"x": -833.2559434480222,
			"y": 1133.7694952422655,
			"width": 98.07726546567096,
			"height": 40.625074744067,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#99e9f2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1912884378,
			"version": 218,
			"versionNonce": 614784070,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1705250211694,
			"link": null,
			"locked": false,
			"text": "How this value splits\nour datapoints classes\ngiven each value of it\ngoing in a seperate node",
			"rawText": "How this value splits\nour datapoints classes\ngiven each value of it\ngoing in a seperate node",
			"fontSize": 8.12501494881341,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 36.99999999999995,
			"containerId": null,
			"originalText": "How this value splits\nour datapoints classes\ngiven each value of it\ngoing in a seperate node",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#99e9f2",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 2615.8541703613255,
		"scrollY": -642.3549528177936,
		"zoom": {
			"value": 0.9590276178173414
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