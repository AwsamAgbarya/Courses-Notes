---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Component Analysis ^BFQE4thX

Measurements are linear superpositions of underlying factors

meaning that our observation X is usually a linear combination
of different basis functions/signals S ^OB59syTz

Forwards and backwards
problem ^r4a1v7RT

This is called the forward problem
The issue is that its very hard to solve this problem with infinite
solutions of A and S, which are both unknown
Assumptions on A and/or S required to determine the
factorization
Thus we usually reformulate to the backwards problem ^ejAYkonK

s = wX ^DX2a9ZTu

Canonical Correlation Analysis
(CCA) ^kaEHI3lw

Assume we have two modalities/Datasets X and Y
We want to find a representation of each of our datasets such
that it represent their relationship as much as possible.

The CCA approach is to find the projections
that maximises the correlation between X and Y ^tbOHgG47

and the projections ^eEeiiQTU

We try to maximize the corrolation between the
projected datasets using the following ^P2OBaPev

CCA is a method to estimate the correlation between
two sets of modalities, this method works even if each modality
has multiple features that differ in size.
This is done by introducing a new "feature" that is a linear combination
of other features. ^1RzOu7l1

The following formula is called the sample correlation formula
and it is used to find out the correlation between 2 datasets ^OQJUIAVx

Cross Covariance of
the projected data
which is an unscaled version
of the cross correlation matrix ^vHg1pI3b

Variance of the projected
data to scale down the
covariance to correlation ^rI51MtBA

Covariance matrix
assuming centered data!! ^vuOfdnbO

problem! This only finds linear functions!!
You know what that means? ^7UBAeG1X

Kernerlize ^UzZMCPeC

any solution found by CCA has to lie
in the subspace spanned by the data points
we can represent this subspace by the
inner products of all data points (linear kernels) ^QkCwqnkr

Which changes our solution to ^9yeg8oOa

and the solution can be recovered by ^z6Mu1tr5

Why project in the first place?
Canonical correlations are invariant
to transformations of the data ^px51q0lm

problem:
What if the data has a timeshift?
i.e the correlations between one dataset and another is not
instantaneous but an overtime effect?
this is quite a common effect in the real world and needs
to be modeled properly in order for this to work ^SNnA1pVl

Maximise correlation for (a sum over) all relative time lags!
This is otherwise known as a convolution operation! ^DJvrvwNm

ಠ_ಠ ^LDdD9mpc

Me in
a social
situation ^ksvjKfKH

Who's talking? ^gQ6wR3eU

Friend ^Zi9OFlgC

Colleague ^YjQuw675

un-important ^E2Pm6VlN

Independent Component analysis
(ICA) ^L6KrgCOW

ICA main assumption and approach to the cocktail problem is
statistical independence




higher cross moments should vanish and we are only left with the signals
themselves.
to help us reach this we try to minimize the divergence between the actual
distribution and the combination of independent distributions
there are many algorithms to do ICA, we will talk about a few here: ^LdoINES4

Which helps us find w to calculate ui such that they independently represent u ^7xK552E8

Some quick ugly math that gets
us the derivative of this according
to different methods ^rOOFWvl1

Gram Chalier expansion ^sgKvrcPY

Edgeworth expansion ^oRDPxxqD

Hermite
polynomial ^Y09O8pCq

k-th
order
moment ^1XByOdQv

JADE ^B8XxfGtA

TDSEP ^FcjJTfgq

# Embedded files
23ca8990931317c083068c35e72ad5cd60c599b0: $$\arg\max_{w_x, w_y} \frac{w_x^TXY^Tw_y}{\sqrt{w_x^TXX^Tw_x}\sqrt{w_y^TYY^Tw_y}}$$
227be7c271fcf269ef382931334009e19498dedf: [[Pasted Image 20240503214853_482.png]]
b17c7882f604c1353bca77e917a77b8d282a236f: [[Pasted Image 20240503221736_734.png]]
3008fa2c7eefe60e46520c259839ecc58451db73: [[Pasted Image 20240503221808_736.png]]
bac7377a1f7e100b46c9f2f34cb0806a657a8e9c: [[Pasted Image 20240503221840_740.png]]
5cee40657161170638debc59cfbb35b031345b39: [[Pasted Image 20240503221950_759.png]]
e13cc7f94e6e0ef235bc1a09a7ecbd860c516756: [[Pasted Image 20240503222020_761.png]]
f7fe35e37ab3555dce1ad9beb576fd97260254b2: [[Pasted Image 20240504112755_405.png]]
16bca1067da917656d7cd7450b1c73bbce8859f7: [[Pasted Image 20240504113029_744.png]]
aaf3a74630f1a6ba22e66a3238e91f9c4938f332: [[Pasted Image 20240504113045_766.png]]
cfac5f42da7a7c84c9548140d53d7e14fd350482: [[Pasted Image 20240504113115_768.png]]
828b22c7997fc6236b9bfde385d48ae95aaeb026: [[Pasted Image 20240504113148_776.png]]
979852782f495c1770232e0d0d57adc879bf138a: [[Pasted Image 20240504114217_877.png]]
5385afabf6c29d3d90c7749105d86c459c7125f0: [[Pasted Image 20240504114247_889.png]]
d996a3c00f0036c7ef195724c7346adc5ac0b194: [[Pasted Image 20240529134106_335.png]]
4c993c830fa770afa5bbb9c65e22df48c1a4d503: [[Pasted Image 20240529140541_368.png]]
f2f339b9a4e3656505452477bb6f9660b6bc428f: [[Pasted Image 20240529140735_434.png]]
3f0379064db456c67c11853582584e95a629a1b5: [[Pasted Image 20240529140935_447.png]]
e22bd27cd40bc93463f1fe6840eadb1a51252d21: [[Pasted Image 20240529141125_494.png]]
c7d35282d6ad22e63400da0cd58f537865b196f4: [[Pasted Image 20240529141219_528.png]]
728478d56a95f92aca5c26a3e6bd51d1dbd31a0f: [[Pasted Image 20240529141329_542.png]]
d20b92888df1584cf38233df4d759f4116f009a7: [[Pasted Image 20240529141344_545.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "ellipse",
			"version": 355,
			"versionNonce": 1941078888,
			"isDeleted": false,
			"id": "F7pJuRO3YsDkGLI7Ajrul",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -28.92876702367056,
			"y": -646.6249868417253,
			"strokeColor": "#ffffff",
			"backgroundColor": "#d0bfff",
			"width": 119.04761904761904,
			"height": 108.57142857142856,
			"seed": 1928154548,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 245,
			"versionNonce": 959956760,
			"isDeleted": false,
			"id": "Xj-w-JU9iBEsc32_CjPeK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -116.57730863425189,
			"y": -646.2277313208392,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffec99",
			"width": 119.04761904761904,
			"height": 108.57142857142856,
			"seed": 454010124,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 152,
			"versionNonce": 1818089064,
			"isDeleted": false,
			"id": "r8dRI6PawHc-Dvfeonypj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -116.5773089675852,
			"y": -721.8557435113155,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffc9c9",
			"width": 119.04761904761904,
			"height": 108.57142857142856,
			"seed": 1181688716,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 265,
			"versionNonce": 1910449176,
			"isDeleted": false,
			"id": "Aak4-SdveE68BvTiSnJiF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -28.928766690337255,
			"y": -722.2529990322018,
			"strokeColor": "#ffffff",
			"backgroundColor": "#fcc2d7",
			"width": 119.04761904761904,
			"height": 108.57142857142856,
			"seed": 1222735668,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 306,
			"versionNonce": 2049362280,
			"isDeleted": false,
			"id": "0w-JJMI3BTJNkyenDuMi2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 50.07066130966274,
			"y": -672.9672847941065,
			"strokeColor": "#ffffff",
			"backgroundColor": "#b2f2bb",
			"width": 119.04761904761904,
			"height": 108.57142857142856,
			"seed": 1905553588,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 194,
			"versionNonce": 932372760,
			"isDeleted": false,
			"id": "_-qt67VUPdzeCZlZeG9QE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -195.5767369675852,
			"y": -672.5700292732201,
			"strokeColor": "#ffffff",
			"backgroundColor": "#a5d8ff",
			"width": 119.04761904761904,
			"height": 108.57142857142856,
			"seed": 106615308,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 1750686824,
			"isDeleted": false,
			"id": "BFQE4thX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -140.69047619047615,
			"y": -648.3809520476191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 259.029052734375,
			"height": 35,
			"seed": 2096232972,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Component Analysis",
			"rawText": "Component Analysis",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Component Analysis",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 1774648856,
			"isDeleted": false,
			"id": "OB59syTz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -321.78026227429757,
			"y": -459.859519378685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 614.7392578125,
			"height": 100,
			"seed": 1488828684,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Measurements are linear superpositions of underlying factors\n\nmeaning that our observation X is usually a linear combination\nof different basis functions/signals S",
			"rawText": "Measurements are linear superpositions of underlying factors\n\nmeaning that our observation X is usually a linear combination\nof different basis functions/signals S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Measurements are linear superpositions of underlying factors\n\nmeaning that our observation X is usually a linear combination\nof different basis functions/signals S",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 952209256,
			"isDeleted": false,
			"id": "r4a1v7RT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -180.03065615711094,
			"y": -533.7579112575974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 337.70941162109375,
			"height": 70,
			"seed": 231050036,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Forwards and backwards\nproblem",
			"rawText": "Forwards and backwards\nproblem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Forwards and backwards\nproblem",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 66,
			"versionNonce": 1500478232,
			"isDeleted": false,
			"id": "PBAtW_rZwk1bLZ7yD2XUn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -162.34041495203556,
			"y": -344.12890967821795,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 302.3289289746134,
			"height": 70.50358422728138,
			"seed": 1997730740,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "227be7c271fcf269ef382931334009e19498dedf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 261,
			"versionNonce": 1403740776,
			"isDeleted": false,
			"id": "ejAYkonK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -350.17786863620813,
			"y": -271.36785705583657,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 652.959228515625,
			"height": 150,
			"seed": 2055504692,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This is called the forward problem\nThe issue is that its very hard to solve this problem with infinite\nsolutions of A and S, which are both unknown\nAssumptions on A and/or S required to determine the\nfactorization\nThus we usually reformulate to the backwards problem",
			"rawText": "This is called the forward problem\nThe issue is that its very hard to solve this problem with infinite\nsolutions of A and S, which are both unknown\nAssumptions on A and/or S required to determine the\nfactorization\nThus we usually reformulate to the backwards problem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is called the forward problem\nThe issue is that its very hard to solve this problem with infinite\nsolutions of A and S, which are both unknown\nAssumptions on A and/or S required to determine the\nfactorization\nThus we usually reformulate to the backwards problem",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 419452952,
			"isDeleted": false,
			"id": "DX2a9ZTu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -89.53478552298326,
			"y": -110.07653510781662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 121.2120361328125,
			"height": 45,
			"seed": 531673996,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983738921,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "s = wX",
			"rawText": "s = wX",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s = wX",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 418,
			"versionNonce": 260583784,
			"isDeleted": false,
			"id": "kaEHI3lw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1009.7422186493723,
			"y": 268.6506648816983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 409.27764892578125,
			"height": 70,
			"seed": 1787111732,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Canonical Correlation Analysis\n(CCA)",
			"rawText": "Canonical Correlation Analysis\n(CCA)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Canonical Correlation Analysis\n(CCA)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1083,
			"versionNonce": 491635816,
			"isDeleted": false,
			"id": "tbOHgG47",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1134.2991628559864,
			"y": 491.28702287393253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 645.6793212890625,
			"height": 150,
			"seed": 1329569716,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assume we have two modalities/Datasets X and Y\nWe want to find a representation of each of our datasets such\nthat it represent their relationship as much as possible.\n\nThe CCA approach is to find the projections\nthat maximises the correlation between X and Y",
			"rawText": "Assume we have two modalities/Datasets X and Y\nWe want to find a representation of each of our datasets such\nthat it represent their relationship as much as possible.\n\nThe CCA approach is to find the projections\nthat maximises the correlation between X and Y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assume we have two modalities/Datasets X and Y\nWe want to find a representation of each of our datasets such\nthat it represent their relationship as much as possible.\n\nThe CCA approach is to find the projections\nthat maximises the correlation between X and Y",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 581,
			"versionNonce": 585693032,
			"isDeleted": false,
			"id": "jPPe_OcnmVG7Vj8w0sWKy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -913.5550061356762,
			"y": 646.315930533601,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 206.05625036739164,
			"height": 52.696352552972286,
			"seed": 1255939852,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b17c7882f604c1353bca77e917a77b8d282a236f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 515,
			"versionNonce": 1420151400,
			"isDeleted": false,
			"id": "eEeiiQTU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -906.7006860799929,
			"y": 699.012283100388,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 190.21978759765625,
			"height": 25,
			"seed": 1015375668,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "and the projections",
			"rawText": "and the projections",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and the projections",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 610,
			"versionNonce": 2102410600,
			"isDeleted": false,
			"id": "-k2DIWMWkS70MrOkQfsK2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -927.4946647038157,
			"y": 744.3470473237746,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 233.93556764627078,
			"height": 41.36665525452349,
			"seed": 1633089164,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3008fa2c7eefe60e46520c259839ecc58451db73",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 856,
			"versionNonce": 775180392,
			"isDeleted": false,
			"id": "OoeuZ3377fdhxB97ccJJg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1065.4259838028775,
			"y": 1032.6639135413511,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 568.0260088664566,
			"height": 82.59561863619393,
			"seed": 892084660,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bac7377a1f7e100b46c9f2f34cb0806a657a8e9c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 641,
			"versionNonce": 1864237928,
			"isDeleted": false,
			"id": "P2OBaPev",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1048.2704409977255,
			"y": 788.6498539266612,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 472.6994934082031,
			"height": 50,
			"seed": 918914188,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We try to maximize the corrolation between the\nprojected datasets using the following",
			"rawText": "We try to maximize the corrolation between the\nprojected datasets using the following",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We try to maximize the corrolation between the\nprojected datasets using the following",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 850,
			"versionNonce": 1851348584,
			"isDeleted": false,
			"id": "NJChxSveIHfke2P0rSS2W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1102.074068344159,
			"y": 1116.9644517741237,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 641.3221780460743,
			"height": 227.50266866466242,
			"seed": 2088020364,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5cee40657161170638debc59cfbb35b031345b39",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 848,
			"versionNonce": 816990568,
			"isDeleted": false,
			"id": "XHISJmcA-B07FPo5l6nbZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1095.4726826430115,
			"y": 1356.289679567279,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 628.1194065195929,
			"height": 119.18163098064069,
			"seed": 1199550348,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e13cc7f94e6e0ef235bc1a09a7ecbd860c516756",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 873,
			"versionNonce": 1098177640,
			"isDeleted": false,
			"id": "1RzOu7l1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1159.3129884344926,
			"y": 350.11666597652027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 708.419189453125,
			"height": 125,
			"seed": 732964706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CCA is a method to estimate the correlation between\ntwo sets of modalities, this method works even if each modality\nhas multiple features that differ in size.\nThis is done by introducing a new \"feature\" that is a linear combination\nof other features.",
			"rawText": "CCA is a method to estimate the correlation between\ntwo sets of modalities, this method works even if each modality\nhas multiple features that differ in size.\nThis is done by introducing a new \"feature\" that is a linear combination\nof other features.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CCA is a method to estimate the correlation between\ntwo sets of modalities, this method works even if each modality\nhas multiple features that differ in size.\nThis is done by introducing a new \"feature\" that is a linear combination\nof other features.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 540,
			"versionNonce": 1651314536,
			"isDeleted": false,
			"id": "Jfdtc329",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -999.5675417644838,
			"y": 906.4824531995911,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 378.3656707725588,
			"height": 83.59241563579788,
			"seed": 95916,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "23ca8990931317c083068c35e72ad5cd60c599b0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 571,
			"versionNonce": 1004986984,
			"isDeleted": false,
			"id": "OQJUIAVx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1053.1818055478807,
			"y": 840.4034190675516,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 503.92108154296875,
			"height": 40,
			"seed": 1354054590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The following formula is called the sample correlation formula\nand it is used to find out the correlation between 2 datasets",
			"rawText": "The following formula is called the sample correlation formula\nand it is used to find out the correlation between 2 datasets",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The following formula is called the sample correlation formula\nand it is used to find out the correlation between 2 datasets",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 1111,
			"versionNonce": 251005208,
			"isDeleted": false,
			"id": "1vwp6s0Nv7YwR5CoZTTXz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -838.003055134996,
			"y": 917.3925259625792,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 208.56394894879077,
			"height": 24.01558162982022,
			"seed": 503355390,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983771716,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "vHg1pI3b",
				"focus": 0.5320994410334084,
				"gap": 4.477771913083643
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
					-163.7294200990085,
					-17.769084351830372
				],
				[
					-208.56394894879077,
					6.246497277989846
				]
			]
		},
		{
			"type": "text",
			"version": 558,
			"versionNonce": 1510959208,
			"isDeleted": false,
			"id": "vHg1pI3b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1298.9173193318313,
			"y": 895.8157806782136,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 247.87254333496094,
			"height": 80,
			"seed": 1396796222,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "1vwp6s0Nv7YwR5CoZTTXz",
					"type": "arrow"
				}
			],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Cross Covariance of\nthe projected data\nwhich is an unscaled version\nof the cross correlation matrix",
			"rawText": "Cross Covariance of\nthe projected data\nwhich is an unscaled version\nof the cross correlation matrix",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cross Covariance of\nthe projected data\nwhich is an unscaled version\nof the cross correlation matrix",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 1134,
			"versionNonce": 981804568,
			"isDeleted": false,
			"id": "68AMc2AQlI3MEGyc9HJVt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -795.4841747216876,
			"y": 984.0265922819431,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 261.53834183338654,
			"height": 40.635733374047106,
			"seed": 474830626,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983771716,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "rI51MtBA",
				"focus": -0.21785629285315336,
				"gap": 4.709505913859516
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
					144.40808079531723,
					33.06383338163539
				],
				[
					261.53834183338654,
					-7.571899992411716
				]
			]
		},
		{
			"type": "arrow",
			"version": 1194,
			"versionNonce": 1076405016,
			"isDeleted": false,
			"id": "n1nS6EXdSZmzYi-k7h2F2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -681.2543467456353,
			"y": 983.3919821265206,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 147.01810842807708,
			"height": 36.4764969271053,
			"seed": 1039623102,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983771716,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "rI51MtBA",
				"focus": -0.033956861888055176,
				"gap": 1
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
					70.14982146343073,
					25.65856971046395
				],
				[
					147.01810842807708,
					-10.817927216641351
				]
			]
		},
		{
			"type": "text",
			"version": 668,
			"versionNonce": 2063856744,
			"isDeleted": false,
			"id": "rI51MtBA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -576.4415942237047,
			"y": 911.7451863756718,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 203.15243530273438,
			"height": 60,
			"seed": 1143309246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "68AMc2AQlI3MEGyc9HJVt",
					"type": "arrow"
				},
				{
					"id": "n1nS6EXdSZmzYi-k7h2F2",
					"type": "arrow"
				}
			],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Variance of the projected\ndata to scale down the\ncovariance to correlation",
			"rawText": "Variance of the projected\ndata to scale down the\ncovariance to correlation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Variance of the projected\ndata to scale down the\ncovariance to correlation",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 892,
			"versionNonce": 508854296,
			"isDeleted": false,
			"id": "NodvU-Vr6jnuyZZm7aF6T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -993.1613559479447,
			"y": 1195.448628660822,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 180.43184475483787,
			"height": 36.793944812751306,
			"seed": 365975166,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983771716,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "vuOfdnbO",
				"focus": -0.34830141666168424,
				"gap": 7.843741506288779
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
					-98.35304478793125,
					36.793944812751306
				],
				[
					-180.43184475483787,
					28.303034471347132
				]
			]
		},
		{
			"type": "text",
			"version": 483,
			"versionNonce": 659718248,
			"isDeleted": false,
			"id": "vuOfdnbO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1379.437369455165,
			"y": 1203.2319631404423,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 198.00042724609375,
			"height": 40,
			"seed": 1439734754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "NodvU-Vr6jnuyZZm7aF6T",
					"type": "arrow"
				}
			],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Covariance matrix\nassuming centered data!!",
			"rawText": "Covariance matrix\nassuming centered data!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Covariance matrix\nassuming centered data!!",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 350,
			"versionNonce": 2041284200,
			"isDeleted": false,
			"id": "7UBAeG1X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -954.500501342442,
			"y": 1487.2938698467267,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 318.03265380859375,
			"height": 40,
			"seed": 1354767678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "problem! This only finds linear functions!!\nYou know what that means?",
			"rawText": "problem! This only finds linear functions!!\nYou know what that means?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "problem! This only finds linear functions!!\nYou know what that means?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 519,
			"versionNonce": 1916696936,
			"isDeleted": false,
			"id": "J36IyBFOwb-vcX8_E27C5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -847.2229156273797,
			"y": 1526.854650616324,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 108.88436358901981,
			"height": 85.6716531096024,
			"seed": 399093090,
			"groupIds": [
				"4_l0MpvcHR2fFsQBr_vqO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f7fe35e37ab3555dce1ad9beb576fd97260254b2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 519,
			"versionNonce": 1643842664,
			"isDeleted": false,
			"id": "_jKC3iQp4q40IZsuI5jCV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -831.818584591528,
			"y": 1530.7783337904896,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffffff",
			"width": 56.66916371422705,
			"height": 9.415252905498537,
			"seed": 1960238882,
			"groupIds": [
				"4_l0MpvcHR2fFsQBr_vqO"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 621,
			"versionNonce": 1923956584,
			"isDeleted": false,
			"id": "UzZMCPeC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -822.0392211243418,
			"y": 1528.6318272233698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 44.38648986816406,
			"height": 11.34619196276831,
			"seed": 347565374,
			"groupIds": [
				"4_l0MpvcHR2fFsQBr_vqO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 9.866253880668097,
			"fontFamily": 2,
			"text": "Kernerlize",
			"rawText": "Kernerlize",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernerlize",
			"lineHeight": 1.15
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 882971240,
			"isDeleted": false,
			"id": "QkCwqnkr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1021.6727146514529,
			"y": 1617.9757276038736,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 480.51947021484375,
			"height": 100,
			"seed": 683915938,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "any solution found by CCA has to lie\nin the subspace spanned by the data points\nwe can represent this subspace by the\ninner products of all data points (linear kernels)",
			"rawText": "any solution found by CCA has to lie\nin the subspace spanned by the data points\nwe can represent this subspace by the\ninner products of all data points (linear kernels)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "any solution found by CCA has to lie\nin the subspace spanned by the data points\nwe can represent this subspace by the\ninner products of all data points (linear kernels)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 324,
			"versionNonce": 1319273832,
			"isDeleted": false,
			"id": "p8_SRHsjg2WS6B4Y7OKEl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -967.9669442814634,
			"y": 1717.975727878182,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 172.4827699632973,
			"height": 44.67179653725685,
			"seed": 2098948258,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "16bca1067da917656d7cd7450b1c73bbce8859f7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 340,
			"versionNonce": 771594344,
			"isDeleted": false,
			"id": "9rRfjLSSIxzIo5a_8rxMa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -755.587468870064,
			"y": 1719.0498805068094,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 164.18792452545216,
			"height": 42.523491244001995,
			"seed": 1342746978,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aaf3a74630f1a6ba22e66a3238e91f9c4938f332",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 317,
			"versionNonce": 914246504,
			"isDeleted": false,
			"id": "9yeg8oOa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -927.2127988888847,
			"y": 1761.5733720844357,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 291.5996398925781,
			"height": 25,
			"seed": 117189090,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which changes our solution to",
			"rawText": "Which changes our solution to",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which changes our solution to",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 379,
			"versionNonce": 1919983208,
			"isDeleted": false,
			"id": "FbUcCK8r0HmIdVoZ_Bxnu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1013.3749696526647,
			"y": 1794.9138349754448,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 472.22172483833305,
			"height": 58.46074715181071,
			"seed": 1876412514,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cfac5f42da7a7c84c9548140d53d7e14fd350482",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 314,
			"versionNonce": 1117819240,
			"isDeleted": false,
			"id": "z6Mu1tr5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -965.0027623185715,
			"y": 1861.71504544952,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 367.1795654296875,
			"height": 25,
			"seed": 60454626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "and the solution can be recovered by",
			"rawText": "and the solution can be recovered by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and the solution can be recovered by",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 377,
			"versionNonce": 240788584,
			"isDeleted": false,
			"id": "qeoRNBUGHjN5a7tWuTtc4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -844.0800862596166,
			"y": 1901.7550154836015,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 133.63195818563483,
			"height": 69.29064498514398,
			"seed": 231963810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "828b22c7997fc6236b9bfde385d48ae95aaeb026",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 562,
			"versionNonce": 1694285080,
			"isDeleted": false,
			"id": "0ptf_1IuLU96YZdUPOJKu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -564.2871393058344,
			"y": 612.962196916578,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 137.52051555670892,
			"height": 42.04448883262444,
			"seed": 482457150,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983771717,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "px51q0lm",
				"focus": 0.18016042310191593,
				"gap": 11.387049058835828
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
					88.46861191864707,
					-8.759268506796786
				],
				[
					137.52051555670892,
					33.28522032582765
				]
			]
		},
		{
			"type": "text",
			"version": 379,
			"versionNonce": 1981426280,
			"isDeleted": false,
			"id": "px51q0lm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -584.837899967954,
			"y": 657.6344663012414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 351.17962646484375,
			"height": 75,
			"seed": 754992290,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0ptf_1IuLU96YZdUPOJKu",
					"type": "arrow"
				}
			],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Why project in the first place?\nCanonical correlations are invariant\nto transformations of the data",
			"rawText": "Why project in the first place?\nCanonical correlations are invariant\nto transformations of the data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why project in the first place?\nCanonical correlations are invariant\nto transformations of the data",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 625,
			"versionNonce": 101757032,
			"isDeleted": false,
			"id": "SNnA1pVl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1014.7781268331205,
			"y": 1970.7951330357066,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 482.2889404296875,
			"height": 120,
			"seed": 1715736290,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "problem:\nWhat if the data has a timeshift?\ni.e the correlations between one dataset and another is not\ninstantaneous but an overtime effect?\nthis is quite a common effect in the real world and needs\nto be modeled properly in order for this to work",
			"rawText": "problem:\nWhat if the data has a timeshift?\ni.e the correlations between one dataset and another is not\ninstantaneous but an overtime effect?\nthis is quite a common effect in the real world and needs\nto be modeled properly in order for this to work",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "problem:\nWhat if the data has a timeshift?\ni.e the correlations between one dataset and another is not\ninstantaneous but an overtime effect?\nthis is quite a common effect in the real world and needs\nto be modeled properly in order for this to work",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 405,
			"versionNonce": 1282302824,
			"isDeleted": false,
			"id": "DJvrvwNm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1074.437077155761,
			"y": 2100.2859893706664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 594.5994262695312,
			"height": 50,
			"seed": 542846718,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "jhEyX6BBe0iRV1qo0yEeL",
					"type": "arrow"
				}
			],
			"updated": 1716983770177,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Maximise correlation for (a sum over) all relative time lags!\nThis is otherwise known as a convolution operation!",
			"rawText": "Maximise correlation for (a sum over) all relative time lags!\nThis is otherwise known as a convolution operation!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Maximise correlation for (a sum over) all relative time lags!\nThis is otherwise known as a convolution operation!",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 997,
			"versionNonce": 588404504,
			"isDeleted": false,
			"id": "jhEyX6BBe0iRV1qo0yEeL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -478.4463079392265,
			"y": 2092.402647714549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 121.75383224447478,
			"height": 44.67226938466342,
			"seed": 1418878654,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716983771717,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "DJvrvwNm",
				"focus": 0.49675118590601053,
				"gap": 7.883341656117409
			},
			"endBinding": {
				"elementId": "Np7vPUn0uV2dUlLiX-LOc",
				"focus": 0.03940426696167647,
				"gap": 5.255561104078197
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
					61.31487954757722,
					-18.39446386427312
				],
				[
					121.75383224447478,
					26.277805520390302
				]
			]
		},
		{
			"type": "embeddable",
			"version": 318,
			"versionNonce": 404831336,
			"isDeleted": false,
			"id": "Np7vPUn0uV2dUlLiX-LOc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -396.9851108260166,
			"y": 2123.936014339017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 307.45032458856576,
			"height": 172.94080758106824,
			"seed": 1387562402,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "jhEyX6BBe0iRV1qo0yEeL",
					"type": "arrow"
				}
			],
			"updated": 1716983770177,
			"link": "https://www.youtube.com/watch?v=KuXjwB4LzSA&t=17s",
			"locked": false,
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 374,
			"versionNonce": 1526415976,
			"isDeleted": false,
			"id": "dig9vLsGeF6Sl6ZKXB_r-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1002.9992003334378,
			"y": 2164.864522582633,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 458.73108846113826,
			"height": 91.08379012766284,
			"seed": 184016126,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770178,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "979852782f495c1770232e0d0d57adc879bf138a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 318,
			"versionNonce": 171357544,
			"isDeleted": false,
			"id": "NSOBYlEowuOXFrFk_0jhs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1070.470731059619,
			"y": 2255.948312621418,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 573.0707559335613,
			"height": 73.70684963775707,
			"seed": 1078308158,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716983770178,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5385afabf6c29d3d90c7749105d86c459c7125f0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 529,
			"versionNonce": 823309416,
			"isDeleted": false,
			"id": "PGIutltHfAeoFmmN4u_9D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -149.84975715144066,
			"y": -54.04474868498875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.550145132526055,
			"height": 16.85646350673451,
			"seed": 1784000792,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 435,
			"versionNonce": 1351608168,
			"isDeleted": false,
			"id": "GNM4o9llwH4vaa858jlkr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -143.4678861941585,
			"y": -49.81329076766028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.0810448773746457,
			"height": 1.73420406447885,
			"seed": 1538248216,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0810448773746457,
					-1.73420406447885
				]
			]
		},
		{
			"type": "line",
			"version": 388,
			"versionNonce": 267303528,
			"isDeleted": false,
			"id": "DXo9U8tnj__jUTTWKG5lD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -137.50222421235122,
			"y": -51.2700221818225,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.8729403896371792,
			"height": 1.2486269264247958,
			"seed": 901663512,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8729403896371792,
					1.2486269264247958
				]
			]
		},
		{
			"type": "ellipse",
			"version": 394,
			"versionNonce": 1106980200,
			"isDeleted": false,
			"id": "UHdLjUf5O9zPbtrvHVt39",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -141.52557764194228,
			"y": -49.67455444250194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 586491928,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 399,
			"versionNonce": 82024,
			"isDeleted": false,
			"id": "sD6u3hu0WO_kX5g6febgg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.19590583814292,
			"y": -49.50113403605414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1598579992,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 442,
			"versionNonce": 1506603880,
			"isDeleted": false,
			"id": "FnjStt25mNbcOl21rkO46",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -139.7220054148843,
			"y": -53.76727603467208,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.993000704958198,
			"height": 0.8384459539135903,
			"seed": 137101848,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.586228401226234,
					-0.8384459539135903
				],
				[
					4.993000704958198,
					-0.444857365718071
				]
			]
		},
		{
			"type": "line",
			"version": 429,
			"versionNonce": 95045224,
			"isDeleted": false,
			"id": "NNC7v7M1MyHOTVtDNTQPr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -142.04305303227483,
			"y": -53.83712502328484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.819677709912036,
			"height": 1.486686547905812,
			"seed": 1821638424,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6433497124040102,
					-1.3557748948375248
				],
				[
					3.819677709912036,
					-1.486686547905812
				]
			]
		},
		{
			"type": "line",
			"version": 431,
			"versionNonce": 275069288,
			"isDeleted": false,
			"id": "jH6wXD8Le6kwW6GFNqpv2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -144.30821074396675,
			"y": -53.437391309456785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.1347915078700503,
			"height": 2.388981198992249,
			"seed": 1559518232,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1033726726767847,
					-1.6222640373895194
				],
				[
					3.1347915078700503,
					-2.388981198992249
				]
			]
		},
		{
			"type": "line",
			"version": 608,
			"versionNonce": 222940264,
			"isDeleted": false,
			"id": "8rc9ll8WZ3LOGZoOr3bbD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -136.40743554359122,
			"y": -43.99270725717406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.468035680497612,
			"height": 3.7308479957280527,
			"seed": 2067863832,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.7078459199480815,
					-0.3840532055146051
				],
				[
					-7.038960201848123,
					0.19333993668141047
				],
				[
					-7.468035680497612,
					2.651230169011954
				],
				[
					-4.507313347604101,
					3.3467947902134476
				],
				[
					-0.43255554618207703,
					3.1499813009898583
				]
			]
		},
		{
			"type": "line",
			"version": 393,
			"versionNonce": 1176764264,
			"isDeleted": false,
			"id": "afbamGfaYiY9icid4WgdS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.57210001313908,
			"y": -43.52338953549679,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.009552810001913,
			"height": 0.7290096018185386,
			"seed": 183383576,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.009552810001913,
					0.7290096018185386
				]
			]
		},
		{
			"type": "line",
			"version": 397,
			"versionNonce": 1799344744,
			"isDeleted": false,
			"id": "Fb64wtkUWenvyrW60JPU3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -125.55958667727992,
			"y": -39.837840992969774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.265069346467175,
			"height": 1.1340149361621554,
			"seed": 1089450776,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.265069346467175,
					-1.1340149361621554
				]
			]
		},
		{
			"type": "line",
			"version": 395,
			"versionNonce": 1130972520,
			"isDeleted": false,
			"id": "b_GBuRptxrzUrZ3eaXU2y",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.51612561798845,
			"y": -38.13681858872653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.402044808486481,
			"height": 1.4580192036370632,
			"seed": 330928152,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.402044808486481,
					-1.4580192036370632
				]
			]
		},
		{
			"type": "line",
			"version": 672,
			"versionNonce": 1542215784,
			"isDeleted": false,
			"id": "dHW2Ly_JvGyIUu_-GjAdF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -140.48700002676847,
			"y": -36.92917142236314,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.882651349276086,
			"height": 55.388813376175264,
			"seed": 188730648,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5745727528648912,
					8.04401854010845
				],
				[
					0.45965820229191295,
					18.386328091676436
				],
				[
					-1.7887389760249348,
					28.900257272390544
				],
				[
					-9.308078596411194,
					55.388813376175264
				]
			]
		},
		{
			"type": "line",
			"version": 503,
			"versionNonce": 949291880,
			"isDeleted": false,
			"id": "F1SOgLfMdjBDMhSxHvgxB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -140.49531566562558,
			"y": -15.37212096093262,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.8469484480247527,
			"height": 33.86918328960181,
			"seed": 284584472,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8469484480247527,
					33.86918328960181
				]
			]
		},
		{
			"type": "line",
			"version": 425,
			"versionNonce": 61824616,
			"isDeleted": false,
			"id": "Du2ro-lemEx-lKaENotk9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -140.14225637504947,
			"y": -34.05630765803866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.960900844541328,
			"height": 9.767736798703094,
			"seed": 1070688024,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.503676742400346,
					9.767736798703094
				],
				[
					-18.960900844541328,
					6.5501293826597315
				]
			]
		},
		{
			"type": "line",
			"version": 418,
			"versionNonce": 1040666984,
			"isDeleted": false,
			"id": "f46DdLZYEUe1ScTMcs2fP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -140.05077480872993,
			"y": -34.240458777159404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.342246396844614,
			"height": 8.305163957086544,
			"seed": 876921880,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.958052403996862,
					8.305163957086544
				],
				[
					7.342246396844614,
					4.694223106179348
				]
			]
		},
		{
			"type": "ellipse",
			"version": 423,
			"versionNonce": 1860756584,
			"isDeleted": false,
			"id": "10-Iq8lMKvO1s4_WcwxzD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.15776873759594867,
			"x": -163.34134329708132,
			"y": -30.027694451101013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.573858411149109,
			"height": 2.8887526807257444,
			"seed": 1547993368,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 459,
			"versionNonce": 1411389288,
			"isDeleted": false,
			"id": "III6amRXKBbFh0laDEpPn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.140413362159975,
			"x": -132.82646869941217,
			"y": -33.84546044179416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.1112808199764053,
			"height": 7.582975786905106,
			"seed": 1195679256,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 391,
			"versionNonce": 301525608,
			"isDeleted": false,
			"id": "B8jL1n1FNF24fI3Abh53K",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -135.05563996497494,
			"y": -38.51340545073293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.296046581330532,
			"height": 4.754405453694469,
			"seed": 1983453976,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 413,
			"versionNonce": 1665097064,
			"isDeleted": false,
			"id": "HjNe2-cR5WpqvfMY-HXiv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -134.9954576174598,
			"y": -36.70793502527934,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.29604658133056,
			"height": 0.9629175602419148,
			"seed": 731248664,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.52765859563504,
					0.9629175602419148
				],
				[
					5.29604658133056,
					0.2407293900604787
				]
			]
		},
		{
			"type": "ellipse",
			"version": 405,
			"versionNonce": 1228894312,
			"isDeleted": false,
			"id": "XGPBGY1oIObdokC7kM_cQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -154.3145046020025,
			"y": 18.228951086725402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 0.8621003799462329,
			"seed": 995046680,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 437,
			"versionNonce": 1002775400,
			"isDeleted": false,
			"id": "VfapCzQLqHYYNdo2kRPnU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.6587617021789,
			"y": 18.07377301833509,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 1.034520455935474,
			"seed": 1524159000,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 499,
			"versionNonce": 1495037544,
			"isDeleted": false,
			"id": "xk2fan-PqY5o8SdPfMwaJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.267561578559105,
			"x": -134.09966867703767,
			"y": -33.34347681526074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.647933303273467,
			"height": 2.1780710122005775,
			"seed": 1898368792,
			"groupIds": [
				"ci-tr-4FwLTKZ_br1Jafj",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 549,
			"versionNonce": 370239848,
			"isDeleted": false,
			"id": "BWLpvzpUrV1O9-QqmqlN3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -175.38368888265663,
			"y": -23.472705226647633,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.550145132526055,
			"height": 16.85646350673451,
			"seed": 1722625048,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 1844444264,
			"isDeleted": false,
			"id": "BMLbERUZ0bMWMTpI4a4Pf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -169.00181792537447,
			"y": -19.241247309319164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.0810448773746457,
			"height": 1.73420406447885,
			"seed": 1969219864,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0810448773746457,
					-1.73420406447885
				]
			]
		},
		{
			"type": "line",
			"version": 408,
			"versionNonce": 310652776,
			"isDeleted": false,
			"id": "Won9FOQ4m28BX7p46yuYE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -163.0361559435671,
			"y": -20.697978723481413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.8729403896371792,
			"height": 1.2486269264247958,
			"seed": 2024998424,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8729403896371792,
					1.2486269264247958
				]
			]
		},
		{
			"type": "ellipse",
			"version": 414,
			"versionNonce": 471466600,
			"isDeleted": false,
			"id": "sZnLiHnrG9KwFT7cDoIAy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.05950937315816,
			"y": -19.10251098416083,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1033536280,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 419,
			"versionNonce": 964523368,
			"isDeleted": false,
			"id": "tlwR5pXGBSmz5e0dxFK6Y",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -163.72983756935878,
			"y": -18.929090577713055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1384800280,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 462,
			"versionNonce": 1610254440,
			"isDeleted": false,
			"id": "vu-Ri_-LQRrGjMjUethuE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165.2559371461002,
			"y": -23.195232576330994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.993000704958198,
			"height": 0.8384459539135903,
			"seed": 1467391256,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.586228401226234,
					-0.8384459539135903
				],
				[
					4.993000704958198,
					-0.444857365718071
				]
			]
		},
		{
			"type": "line",
			"version": 449,
			"versionNonce": 2069707624,
			"isDeleted": false,
			"id": "-IoqKXE87RTtepnU49Ayl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.5769847634907,
			"y": -23.265081564943728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.819677709912036,
			"height": 1.486686547905812,
			"seed": 1305688600,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6433497124040102,
					-1.3557748948375248
				],
				[
					3.819677709912036,
					-1.486686547905812
				]
			]
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 502369896,
			"isDeleted": false,
			"id": "1P3rohprDG4d7c9_Pfutd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -169.8421424751826,
			"y": -22.865347851115672,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.1347915078700503,
			"height": 2.388981198992249,
			"seed": 1754543896,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1033726726767847,
					-1.6222640373895194
				],
				[
					3.1347915078700503,
					-2.388981198992249
				]
			]
		},
		{
			"type": "line",
			"version": 628,
			"versionNonce": 813924712,
			"isDeleted": false,
			"id": "o2Lby_Qaffhsf4y5qYe4B",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -161.94136727480708,
			"y": -13.420663798832948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.468035680497612,
			"height": 3.7308479957280527,
			"seed": 1546490904,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.7078459199480815,
					-0.3840532055146051
				],
				[
					-7.038960201848123,
					0.19333993668141047
				],
				[
					-7.468035680497612,
					2.651230169011954
				],
				[
					-4.507313347604101,
					3.3467947902134476
				],
				[
					-0.43255554618207703,
					3.1499813009898583
				]
			]
		},
		{
			"type": "line",
			"version": 413,
			"versionNonce": 576656488,
			"isDeleted": false,
			"id": "2thnJXm3S36G_xXjvYlqd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -152.10603174435494,
			"y": -12.951346077155705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.009552810001913,
			"height": 0.7290096018185386,
			"seed": 781406488,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.009552810001913,
					0.7290096018185386
				]
			]
		},
		{
			"type": "line",
			"version": 417,
			"versionNonce": 424691560,
			"isDeleted": false,
			"id": "J_sFEWnq94r0IxA_MgsHL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.09351840849578,
			"y": -9.265797534628689,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.265069346467175,
			"height": 1.1340149361621554,
			"seed": 121204248,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.265069346467175,
					-1.1340149361621554
				]
			]
		},
		{
			"type": "line",
			"version": 415,
			"versionNonce": 564337256,
			"isDeleted": false,
			"id": "WZwB_1ChvZkJPPPb5oXoA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -154.05005734920442,
			"y": -7.564775130385414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.402044808486481,
			"height": 1.4580192036370632,
			"seed": 2132011800,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.402044808486481,
					-1.4580192036370632
				]
			]
		},
		{
			"type": "line",
			"version": 692,
			"versionNonce": 1579388264,
			"isDeleted": false,
			"id": "vnUSEUWet_KYQAmtnmXEe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -166.02093175798433,
			"y": -6.357127964022027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.882651349276086,
			"height": 55.388813376175264,
			"seed": 1888929816,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5745727528648912,
					8.04401854010845
				],
				[
					0.45965820229191295,
					18.386328091676436
				],
				[
					-1.7887389760249348,
					28.900257272390544
				],
				[
					-9.308078596411194,
					55.388813376175264
				]
			]
		},
		{
			"type": "line",
			"version": 523,
			"versionNonce": 941465704,
			"isDeleted": false,
			"id": "01hQMz2zakLQJBlMQpH_I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -166.02924739684144,
			"y": 15.199922497408437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.8469484480247527,
			"height": 33.86918328960181,
			"seed": 1203111192,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8469484480247527,
					33.86918328960181
				]
			]
		},
		{
			"type": "line",
			"version": 445,
			"versionNonce": 257774440,
			"isDeleted": false,
			"id": "0QBDPo7DZskhwNq6WHX5z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165.67618810626533,
			"y": -3.4842641996975487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.960900844541328,
			"height": 9.767736798703094,
			"seed": 1374003736,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.503676742400346,
					9.767736798703094
				],
				[
					-18.960900844541328,
					6.5501293826597315
				]
			]
		},
		{
			"type": "line",
			"version": 438,
			"versionNonce": 1781442152,
			"isDeleted": false,
			"id": "mD48MOoHARJvIkpull4ST",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165.58470653994578,
			"y": -3.668415318818262,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.342246396844614,
			"height": 8.305163957086544,
			"seed": 236560152,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.958052403996862,
					8.305163957086544
				],
				[
					7.342246396844614,
					4.694223106179348
				]
			]
		},
		{
			"type": "ellipse",
			"version": 443,
			"versionNonce": 626891112,
			"isDeleted": false,
			"id": "4420X2sCllTg5ovWANW3g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.15776873759594867,
			"x": -188.87527502829718,
			"y": 0.5443490072401005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.573858411149109,
			"height": 2.8887526807257444,
			"seed": 2093349912,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 479,
			"versionNonce": 607530088,
			"isDeleted": false,
			"id": "iwSIy5sRUp23-uAUZGkOL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.140413362159975,
			"x": -158.36040043062815,
			"y": -3.273416983453018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.1112808199764053,
			"height": 7.582975786905106,
			"seed": 1876867352,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 411,
			"versionNonce": 8675176,
			"isDeleted": false,
			"id": "Avx1u4m_7U07YMonv_3-n",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -160.58957169619083,
			"y": -7.941361992391791,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.296046581330532,
			"height": 4.754405453694469,
			"seed": 1524094488,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 433,
			"versionNonce": 982790760,
			"isDeleted": false,
			"id": "mgnLOnU641U-F2h__cvWo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -160.52938934867578,
			"y": -6.135891566938227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.29604658133056,
			"height": 0.9629175602419148,
			"seed": 581260056,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.52765859563504,
					0.9629175602419148
				],
				[
					5.29604658133056,
					0.2407293900604787
				]
			]
		},
		{
			"type": "ellipse",
			"version": 425,
			"versionNonce": 1764861288,
			"isDeleted": false,
			"id": "JR-WtxEzH4g70IQVyyInq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.84843633321847,
			"y": 48.80099454506653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 0.8621003799462329,
			"seed": 1840984088,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 457,
			"versionNonce": 1772664936,
			"isDeleted": false,
			"id": "e96pPWasxg-7qmrVCe5le",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -164.19269343339488,
			"y": 48.64581647667616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 1.034520455935474,
			"seed": 1947036952,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 519,
			"versionNonce": 264596328,
			"isDeleted": false,
			"id": "IMzwMO3RzSVryGKydrln8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.267561578559105,
			"x": -159.63360040825353,
			"y": -2.77143335691963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.647933303273467,
			"height": 2.1780710122005775,
			"seed": 1326451224,
			"groupIds": [
				"Q8xzoTRyfb-kS_ztQ8F6-",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 547,
			"versionNonce": 1439940200,
			"isDeleted": false,
			"id": "ZK_k0aw0bffdpZVFPh9gZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -131.45798397253833,
			"y": 0.5708385136275638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.550145132526055,
			"height": 16.85646350673451,
			"seed": 1236731672,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 211792232,
			"isDeleted": false,
			"id": "dhFgBsAjprq7sSYMk162C",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -125.07611301525606,
			"y": 4.802296430956005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.0810448773746457,
			"height": 1.73420406447885,
			"seed": 813065240,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0810448773746457,
					-1.73420406447885
				]
			]
		},
		{
			"type": "line",
			"version": 406,
			"versionNonce": 192234600,
			"isDeleted": false,
			"id": "iAhl_G45PafA_mssHxeGk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.11045103344878,
			"y": 3.3455650167937847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.8729403896371792,
			"height": 1.2486269264247958,
			"seed": 557981976,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8729403896371792,
					1.2486269264247958
				]
			]
		},
		{
			"type": "ellipse",
			"version": 412,
			"versionNonce": 1612740456,
			"isDeleted": false,
			"id": "kuyKydwDNwRoZwQGrpo4Q",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -123.13380446303975,
			"y": 4.941032756114311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1536048664,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 417,
			"versionNonce": 2129480296,
			"isDeleted": false,
			"id": "uyyFeM_fkEMeLiMOcwWFI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.8041326592404,
			"y": 5.1144531625621426,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 273595160,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 460,
			"versionNonce": 1923595624,
			"isDeleted": false,
			"id": "UaFuSp7xsWLY0jnRqcr6d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -121.3302322359819,
			"y": 0.8483111639442029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.993000704958198,
			"height": 0.8384459539135903,
			"seed": 838309912,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.586228401226234,
					-0.8384459539135903
				],
				[
					4.993000704958198,
					-0.444857365718071
				]
			]
		},
		{
			"type": "line",
			"version": 447,
			"versionNonce": 211538024,
			"isDeleted": false,
			"id": "d2jJ00aCcKZbcui-24CFA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -123.6512798533723,
			"y": 0.7784621753314411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.819677709912036,
			"height": 1.486686547905812,
			"seed": 1149031704,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6433497124040102,
					-1.3557748948375248
				],
				[
					3.819677709912036,
					-1.486686547905812
				]
			]
		},
		{
			"type": "line",
			"version": 449,
			"versionNonce": 345342824,
			"isDeleted": false,
			"id": "UwoThlLmaBaQMHiJxpwMd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -125.9164375650642,
			"y": 1.1781958891594968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.1347915078700503,
			"height": 2.388981198992249,
			"seed": 760377880,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1033726726767847,
					-1.6222640373895194
				],
				[
					3.1347915078700503,
					-2.388981198992249
				]
			]
		},
		{
			"type": "line",
			"version": 626,
			"versionNonce": 2028000872,
			"isDeleted": false,
			"id": "X4M9T9VhDLAgNKECFRd7B",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -118.01566236468881,
			"y": 10.622879941442221,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.468035680497612,
			"height": 3.7308479957280527,
			"seed": 57437976,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.7078459199480815,
					-0.3840532055146051
				],
				[
					-7.038960201848123,
					0.19333993668141047
				],
				[
					-7.468035680497612,
					2.651230169011954
				],
				[
					-4.507313347604101,
					3.3467947902134476
				],
				[
					-0.43255554618207703,
					3.1499813009898583
				]
			]
		},
		{
			"type": "line",
			"version": 411,
			"versionNonce": 2118764904,
			"isDeleted": false,
			"id": "V036HoNs4umEzbSV5YFY1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -108.18032683423667,
			"y": 11.092197663119492,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.009552810001913,
			"height": 0.7290096018185386,
			"seed": 1597951000,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.009552810001913,
					0.7290096018185386
				]
			]
		},
		{
			"type": "line",
			"version": 415,
			"versionNonce": 1880906856,
			"isDeleted": false,
			"id": "epeB173fk_l1iRucMNoeK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -107.16781349837748,
			"y": 14.777746205646508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.265069346467175,
			"height": 1.1340149361621554,
			"seed": 717064472,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.265069346467175,
					-1.1340149361621554
				]
			]
		},
		{
			"type": "line",
			"version": 413,
			"versionNonce": 1344573288,
			"isDeleted": false,
			"id": "z0WnCq2nhydMj_BGXshBC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -110.1243524390859,
			"y": 16.478768609889755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.402044808486481,
			"height": 1.4580192036370632,
			"seed": 1901897240,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.402044808486481,
					-1.4580192036370632
				]
			]
		},
		{
			"type": "line",
			"version": 690,
			"versionNonce": 112091752,
			"isDeleted": false,
			"id": "upWIMVe6G08pplz6wKh8L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -122.09522684786594,
			"y": 17.686415776253142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.882651349276086,
			"height": 55.388813376175264,
			"seed": 806363928,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5745727528648912,
					8.04401854010845
				],
				[
					0.45965820229191295,
					18.386328091676436
				],
				[
					-1.7887389760249348,
					28.900257272390544
				],
				[
					-9.308078596411194,
					55.388813376175264
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 310760808,
			"isDeleted": false,
			"id": "Mu-qBT44miMaRvZhHKHuy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -122.10354248672314,
			"y": 39.24346623768369,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.8469484480247527,
			"height": 33.86918328960181,
			"seed": 625737752,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8469484480247527,
					33.86918328960181
				]
			]
		},
		{
			"type": "line",
			"version": 443,
			"versionNonce": 955705448,
			"isDeleted": false,
			"id": "acgPWrffHJja21dXpVrUl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -121.75048319614706,
			"y": 20.55927954057762,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.960900844541328,
			"height": 9.767736798703094,
			"seed": 553925912,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.503676742400346,
					9.767736798703094
				],
				[
					-18.960900844541328,
					6.5501293826597315
				]
			]
		},
		{
			"type": "line",
			"version": 436,
			"versionNonce": 902667112,
			"isDeleted": false,
			"id": "GJJ4I7caShN5lXOykvwEK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -121.65900162982751,
			"y": 20.37512842145688,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.342246396844614,
			"height": 8.305163957086544,
			"seed": 1420614168,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.958052403996862,
					8.305163957086544
				],
				[
					7.342246396844614,
					4.694223106179348
				]
			]
		},
		{
			"type": "ellipse",
			"version": 441,
			"versionNonce": 1800793704,
			"isDeleted": false,
			"id": "Cm3bfv5KNLVmBsB8bMnSa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.15776873759594867,
			"x": -144.94957011817877,
			"y": 24.58789274751524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.573858411149109,
			"height": 2.8887526807257444,
			"seed": 590993176,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 477,
			"versionNonce": 308011368,
			"isDeleted": false,
			"id": "ZXbPPmWOG1FofUBe156OT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.140413362159975,
			"x": -114.43469552050965,
			"y": 20.770126756822123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.1112808199764053,
			"height": 7.582975786905106,
			"seed": 1897870360,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 409,
			"versionNonce": 1781232744,
			"isDeleted": false,
			"id": "zNOHtfTZFxi-w4lVVPWtP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -116.66386678607253,
			"y": 16.102181747883378,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.296046581330532,
			"height": 4.754405453694469,
			"seed": 1951461656,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 431,
			"versionNonce": 1754310504,
			"isDeleted": false,
			"id": "0rv8_ryIziO21QqEj0GMZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -116.60368443855725,
			"y": 17.907652173336942,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.29604658133056,
			"height": 0.9629175602419148,
			"seed": 71503384,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.52765859563504,
					0.9629175602419148
				],
				[
					5.29604658133056,
					0.2407293900604787
				]
			]
		},
		{
			"type": "ellipse",
			"version": 423,
			"versionNonce": 1775729256,
			"isDeleted": false,
			"id": "bPMDcZwUd-uCIielWe7mT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -135.92273142310006,
			"y": 72.84453828534168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 0.8621003799462329,
			"seed": 1776913176,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 455,
			"versionNonce": 1623977320,
			"isDeleted": false,
			"id": "LydXIEWwiAD4IBKYSqKq_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -120.2669885232765,
			"y": 72.68936021695137,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 1.034520455935474,
			"seed": 800614424,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 517,
			"versionNonce": 112853096,
			"isDeleted": false,
			"id": "O-fpWqTftH_B95wueiE_z",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.267561578559105,
			"x": -115.70789549813514,
			"y": 21.27211038335554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.647933303273467,
			"height": 2.1780710122005775,
			"seed": 1906550040,
			"groupIds": [
				"1-m100iZDgZuk7X9SALua",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 571,
			"versionNonce": 191738728,
			"isDeleted": false,
			"id": "4UiFSh1zLMqq44E856YAq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -161.97478948904143,
			"y": 32.47477155360825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.550145132526055,
			"height": 16.85646350673451,
			"seed": 757023256,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 1160971880,
			"isDeleted": false,
			"id": "SwW27ccDkwRl2-CFDMDPu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -155.59291853175938,
			"y": 36.70622947093668,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.0810448773746457,
			"height": 1.73420406447885,
			"seed": 287260440,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0810448773746457,
					-1.73420406447885
				]
			]
		},
		{
			"type": "line",
			"version": 430,
			"versionNonce": 1624635752,
			"isDeleted": false,
			"id": "aO8DF2jiWE0W_LYLA51v9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -149.627256549952,
			"y": 35.2494980567745,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.8729403896371792,
			"height": 1.2486269264247958,
			"seed": 1310170136,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8729403896371792,
					1.2486269264247958
				]
			]
		},
		{
			"type": "ellipse",
			"version": 436,
			"versionNonce": 295865448,
			"isDeleted": false,
			"id": "Nj3yE2LznJj4i-hgDwwKI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -153.65060997954305,
			"y": 36.84496579609501,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1711036696,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 441,
			"versionNonce": 1097121640,
			"isDeleted": false,
			"id": "u7FDF-kwsbVS05RSjkk8-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.3209381757437,
			"y": 37.0183862025428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 2084664856,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 484,
			"versionNonce": 1080595048,
			"isDeleted": false,
			"id": "Re3o9pBVbx5zyKk_2MDJR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.8470377524851,
			"y": 32.75224420392489,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.993000704958198,
			"height": 0.8384459539135903,
			"seed": 635106072,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.586228401226234,
					-0.8384459539135903
				],
				[
					4.993000704958198,
					-0.444857365718071
				]
			]
		},
		{
			"type": "line",
			"version": 471,
			"versionNonce": 1970931048,
			"isDeleted": false,
			"id": "socrvRofIumDcFhC7KcbK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -154.1680853698756,
			"y": 32.682395215312155,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.819677709912036,
			"height": 1.486686547905812,
			"seed": 960286744,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6433497124040102,
					-1.3557748948375248
				],
				[
					3.819677709912036,
					-1.486686547905812
				]
			]
		},
		{
			"type": "line",
			"version": 473,
			"versionNonce": 233117800,
			"isDeleted": false,
			"id": "gJbcfhZ1Khn5xLGrx8ci3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -156.43324308156753,
			"y": 33.08212892914018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.1347915078700503,
			"height": 2.388981198992249,
			"seed": 509283608,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1033726726767847,
					-1.6222640373895194
				],
				[
					3.1347915078700503,
					-2.388981198992249
				]
			]
		},
		{
			"type": "line",
			"version": 650,
			"versionNonce": 762694504,
			"isDeleted": false,
			"id": "lZgOzoJJ906PzDcUtfTlu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -148.53246788119202,
			"y": 42.526812981422935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.468035680497612,
			"height": 3.7308479957280527,
			"seed": 514435608,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.7078459199480815,
					-0.3840532055146051
				],
				[
					-7.038960201848123,
					0.19333993668141047
				],
				[
					-7.468035680497612,
					2.651230169011954
				],
				[
					-4.507313347604101,
					3.3467947902134476
				],
				[
					-0.43255554618207703,
					3.1499813009898583
				]
			]
		},
		{
			"type": "line",
			"version": 435,
			"versionNonce": 511188584,
			"isDeleted": false,
			"id": "4gJLgCNGOB596litcqtvn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.69713235073988,
			"y": 42.99613070310018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.009552810001913,
			"height": 0.7290096018185386,
			"seed": 891070232,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.009552810001913,
					0.7290096018185386
				]
			]
		},
		{
			"type": "line",
			"version": 439,
			"versionNonce": 28840296,
			"isDeleted": false,
			"id": "WE33_eQJhc4BTycVcOu3e",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -137.6846190148807,
			"y": 46.681679245627194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.265069346467175,
			"height": 1.1340149361621554,
			"seed": 1579680792,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.265069346467175,
					-1.1340149361621554
				]
			]
		},
		{
			"type": "line",
			"version": 437,
			"versionNonce": 2122425448,
			"isDeleted": false,
			"id": "515EfupWoqATLwbXv5Sgk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -140.64115795558922,
			"y": 48.382701649870455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.402044808486481,
			"height": 1.4580192036370632,
			"seed": 1740620056,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.402044808486481,
					-1.4580192036370632
				]
			]
		},
		{
			"type": "line",
			"version": 714,
			"versionNonce": 1923143528,
			"isDeleted": false,
			"id": "H1vEfUxruniUnm4kMF7jR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -152.61203236436924,
			"y": 49.59034881623384,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.882651349276086,
			"height": 55.388813376175264,
			"seed": 1096277528,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5745727528648912,
					8.04401854010845
				],
				[
					0.45965820229191295,
					18.386328091676436
				],
				[
					-1.7887389760249348,
					28.900257272390544
				],
				[
					-9.308078596411194,
					55.388813376175264
				]
			]
		},
		{
			"type": "line",
			"version": 545,
			"versionNonce": 576825960,
			"isDeleted": false,
			"id": "RuX2m1z0mwGTDYqnki_nw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -152.62034800322635,
			"y": 71.14739927766438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.8469484480247527,
			"height": 33.86918328960181,
			"seed": 1273256728,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8469484480247527,
					33.86918328960181
				]
			]
		},
		{
			"type": "line",
			"version": 467,
			"versionNonce": 1754275176,
			"isDeleted": false,
			"id": "ASnButHg6wmb0A0UzJkJT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -152.26728871265024,
			"y": 52.463212580558334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.960900844541328,
			"height": 9.767736798703094,
			"seed": 702101528,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.503676742400346,
					9.767736798703094
				],
				[
					-18.960900844541328,
					6.5501293826597315
				]
			]
		},
		{
			"type": "line",
			"version": 460,
			"versionNonce": 1719152744,
			"isDeleted": false,
			"id": "2gIHATQ_RUf4eod21AgIf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -152.1758071463306,
			"y": 52.27906146143758,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.342246396844614,
			"height": 8.305163957086544,
			"seed": 254440728,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.958052403996862,
					8.305163957086544
				],
				[
					7.342246396844614,
					4.694223106179348
				]
			]
		},
		{
			"type": "ellipse",
			"version": 465,
			"versionNonce": 870703976,
			"isDeleted": false,
			"id": "djC2mOizZZW58R676cOZD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.15776873759594867,
			"x": -175.4663756346821,
			"y": 56.49182578749594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.573858411149109,
			"height": 2.8887526807257444,
			"seed": 290198040,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 501,
			"versionNonce": 254097000,
			"isDeleted": false,
			"id": "aMKtE-9ZLtHpO5zdOG0ei",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.140413362159975,
			"x": -144.95150103701306,
			"y": 52.67405979680285,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.1112808199764053,
			"height": 7.582975786905106,
			"seed": 1999769368,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 433,
			"versionNonce": 218245480,
			"isDeleted": false,
			"id": "yU9oYnKL7qFlN1zq4fJEx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -147.18067230257574,
			"y": 48.00611478786409,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.296046581330532,
			"height": 4.754405453694469,
			"seed": 156265496,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 1221114984,
			"isDeleted": false,
			"id": "HKpByg7hjVj9XPcBpIWsX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -147.1204899550607,
			"y": 49.81158521331763,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.29604658133056,
			"height": 0.9629175602419148,
			"seed": 1637558552,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.52765859563504,
					0.9629175602419148
				],
				[
					5.29604658133056,
					0.2407293900604787
				]
			]
		},
		{
			"type": "ellipse",
			"version": 447,
			"versionNonce": 340062056,
			"isDeleted": false,
			"id": "Yf_5OqamzsH9sNCX9vqQo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -166.43953693960339,
			"y": 104.74847132532238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 0.8621003799462329,
			"seed": 998655512,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 479,
			"versionNonce": 667075176,
			"isDeleted": false,
			"id": "7iRv6fE_MmY0HjyAMkgLq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.7837940397798,
			"y": 104.59329325693207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 1.034520455935474,
			"seed": 1141228312,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 541,
			"versionNonce": 1376662888,
			"isDeleted": false,
			"id": "6TxZnRv_dug8O5wmq5zA0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.267561578559105,
			"x": -146.22470101463844,
			"y": 53.17604342333624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.647933303273467,
			"height": 2.1780710122005775,
			"seed": 1770889240,
			"groupIds": [
				"nsBzEkKsQOdDq0aaojO0c",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 699,
			"versionNonce": 678643816,
			"isDeleted": false,
			"id": "uBOs_x2E-KhX96LdeebWJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.39362158992543,
			"y": 83.7984899222728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.550145132526055,
			"height": 16.85646350673451,
			"seed": 739368216,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 605,
			"versionNonce": 918420328,
			"isDeleted": false,
			"id": "BRkkJD4guCX-Pkb-E2oY7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -132.01175063264316,
			"y": 88.02994783960125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.0810448773746457,
			"height": 1.73420406447885,
			"seed": 1829141016,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0810448773746457,
					-1.73420406447885
				]
			]
		},
		{
			"type": "line",
			"version": 558,
			"versionNonce": 792350312,
			"isDeleted": false,
			"id": "IVmqjKvQbGgu0n3q_TGpX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.04608865083588,
			"y": 86.57321642543903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.8729403896371792,
			"height": 1.2486269264247958,
			"seed": 1063221016,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8729403896371792,
					1.2486269264247958
				]
			]
		},
		{
			"type": "ellipse",
			"version": 564,
			"versionNonce": 448020840,
			"isDeleted": false,
			"id": "nJkuX_AGJm8MH1yV3iemB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -130.06944208042682,
			"y": 88.1686841647596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 932238360,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 569,
			"versionNonce": 142070888,
			"isDeleted": false,
			"id": "ThKDGZz00oIfdvmNYzVI9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.73977027662738,
			"y": 88.34210457120739,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 999199000,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 612,
			"versionNonce": 1045497704,
			"isDeleted": false,
			"id": "_FXqKyfmam2qYTG81bi6J",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.26586985336877,
			"y": 84.07596257258942,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.993000704958198,
			"height": 0.8384459539135903,
			"seed": 1389145624,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.586228401226234,
					-0.8384459539135903
				],
				[
					4.993000704958198,
					-0.444857365718071
				]
			]
		},
		{
			"type": "line",
			"version": 599,
			"versionNonce": 1753995880,
			"isDeleted": false,
			"id": "IwW7Bn9kOURl34phNBTnW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -130.5869174707593,
			"y": 84.00611358397671,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.819677709912036,
			"height": 1.486686547905812,
			"seed": 1983851288,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6433497124040102,
					-1.3557748948375248
				],
				[
					3.819677709912036,
					-1.486686547905812
				]
			]
		},
		{
			"type": "line",
			"version": 601,
			"versionNonce": 1240747368,
			"isDeleted": false,
			"id": "PW7KJ9yt_7H49etHB9bME",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -132.85207518245142,
			"y": 84.40584729780474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.1347915078700503,
			"height": 2.388981198992249,
			"seed": 1616513048,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1033726726767847,
					-1.6222640373895194
				],
				[
					3.1347915078700503,
					-2.388981198992249
				]
			]
		},
		{
			"type": "line",
			"version": 778,
			"versionNonce": 1809211496,
			"isDeleted": false,
			"id": "BXvGu0oWy2CRd4FIDbOWB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -124.9512999820758,
			"y": 93.85053135008746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.468035680497612,
			"height": 3.7308479957280527,
			"seed": 1561412888,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.7078459199480815,
					-0.3840532055146051
				],
				[
					-7.038960201848123,
					0.19333993668141047
				],
				[
					-7.468035680497612,
					2.651230169011954
				],
				[
					-4.507313347604101,
					3.3467947902134476
				],
				[
					-0.43255554618207703,
					3.1499813009898583
				]
			]
		},
		{
			"type": "line",
			"version": 563,
			"versionNonce": 1308496744,
			"isDeleted": false,
			"id": "kBWd82yMiaIuF8_Ps_eqz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -115.11596445162354,
			"y": 94.31984907176476,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.009552810001913,
			"height": 0.7290096018185386,
			"seed": 433644056,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.009552810001913,
					0.7290096018185386
				]
			]
		},
		{
			"type": "line",
			"version": 567,
			"versionNonce": 381118056,
			"isDeleted": false,
			"id": "Cs39G7RTcC3gswhvGtSRW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.10345111576459,
			"y": 98.00539761429172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.265069346467175,
			"height": 1.1340149361621554,
			"seed": 1973739288,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.265069346467175,
					-1.1340149361621554
				]
			]
		},
		{
			"type": "line",
			"version": 565,
			"versionNonce": 1120819560,
			"isDeleted": false,
			"id": "oJI8VcSKZwueJph_Uhh-u",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.059990056473,
			"y": 99.70642001853497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.402044808486481,
			"height": 1.4580192036370632,
			"seed": 1357462552,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.402044808486481,
					-1.4580192036370632
				]
			]
		},
		{
			"type": "line",
			"version": 842,
			"versionNonce": 1435429992,
			"isDeleted": false,
			"id": "Gb5meYUHgvcREY_uAgARk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -129.0308644652529,
			"y": 100.91406718489837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.882651349276086,
			"height": 55.388813376175264,
			"seed": 1570371864,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5745727528648912,
					8.04401854010845
				],
				[
					0.45965820229191295,
					18.386328091676436
				],
				[
					-1.7887389760249348,
					28.900257272390544
				],
				[
					-9.308078596411194,
					55.388813376175264
				]
			]
		},
		{
			"type": "line",
			"version": 673,
			"versionNonce": 147136360,
			"isDeleted": false,
			"id": "PlsRzNSvxAmbXQ-3KOGsx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -129.03918010411002,
			"y": 122.4711176463289,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.8469484480247527,
			"height": 33.86918328960181,
			"seed": 1865094680,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8469484480247527,
					33.86918328960181
				]
			]
		},
		{
			"type": "line",
			"version": 595,
			"versionNonce": 2092757608,
			"isDeleted": false,
			"id": "34FKMRtHXJ94QNNCh3SRw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.68612081353413,
			"y": 103.78693094922286,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.960900844541328,
			"height": 9.767736798703094,
			"seed": 1250988824,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.503676742400346,
					9.767736798703094
				],
				[
					-18.960900844541328,
					6.5501293826597315
				]
			]
		},
		{
			"type": "line",
			"version": 588,
			"versionNonce": 1749181800,
			"isDeleted": false,
			"id": "V55wM3_sy6DeOZtjB8eA3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.5946392472146,
			"y": 103.60277983010215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.342246396844614,
			"height": 8.305163957086544,
			"seed": 1983803416,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.958052403996862,
					8.305163957086544
				],
				[
					7.342246396844614,
					4.694223106179348
				]
			]
		},
		{
			"type": "ellipse",
			"version": 593,
			"versionNonce": 1218541672,
			"isDeleted": false,
			"id": "UAiiGaJasdQ9NmsCL7vK7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.15776873759594867,
			"x": -151.88520773556576,
			"y": 107.81554415616051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.573858411149109,
			"height": 2.8887526807257444,
			"seed": 170437912,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 629,
			"versionNonce": 296102760,
			"isDeleted": false,
			"id": "VtcE3s3jkGSI3SgaWTROO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.140413362159975,
			"x": -121.37033313789675,
			"y": 103.99777816546737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.1112808199764053,
			"height": 7.582975786905106,
			"seed": 2143504920,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 561,
			"versionNonce": 1570537064,
			"isDeleted": false,
			"id": "4X_vpJ2Gw0OSdKKWLvDk0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -123.59950440345952,
			"y": 99.32983315652862,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.296046581330532,
			"height": 4.754405453694469,
			"seed": 33703704,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 583,
			"versionNonce": 491811176,
			"isDeleted": false,
			"id": "AvPzYCTuB36SesolKRkxH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -123.53932205594435,
			"y": 101.1353035819822,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.29604658133056,
			"height": 0.9629175602419148,
			"seed": 1029284888,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.52765859563504,
					0.9629175602419148
				],
				[
					5.29604658133056,
					0.2407293900604787
				]
			]
		},
		{
			"type": "ellipse",
			"version": 575,
			"versionNonce": 1208878184,
			"isDeleted": false,
			"id": "lXBRk6S63GZkkJV2gUhyf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -142.85836904048716,
			"y": 156.07218969398696,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 0.8621003799462329,
			"seed": 800940312,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 607,
			"versionNonce": 195114856,
			"isDeleted": false,
			"id": "CpNSqzrExGqrwRRMegjNn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -127.20262614066368,
			"y": 155.91701162559664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 1.034520455935474,
			"seed": 2023849496,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 669,
			"versionNonce": 2086013544,
			"isDeleted": false,
			"id": "XTh2wPkXQtSwyZDs2zU5F",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.267561578559105,
			"x": -122.6435331155223,
			"y": 104.49976179200075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.647933303273467,
			"height": 2.1780710122005775,
			"seed": 687471384,
			"groupIds": [
				"Nnt1rXKhThrSHBxG0SXfx",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 632,
			"versionNonce": 1157135720,
			"isDeleted": false,
			"id": "BMAsomuGxdhjy9JfEfOQu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.54507145308895,
			"y": 68.07771132286204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.550145132526055,
			"height": 16.85646350673451,
			"seed": 322623512,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 538,
			"versionNonce": 1456771176,
			"isDeleted": false,
			"id": "ir3-2-fkSSy7kQCQU_kgi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -173.16320049580668,
			"y": 72.30916924019051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.0810448773746457,
			"height": 1.73420406447885,
			"seed": 458757400,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0810448773746457,
					-1.73420406447885
				]
			]
		},
		{
			"type": "line",
			"version": 491,
			"versionNonce": 431375208,
			"isDeleted": false,
			"id": "PZoP7SwOTsDI7_rzLnM4c",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.19753851399943,
			"y": 70.85243782602828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.8729403896371792,
			"height": 1.2486269264247958,
			"seed": 113619480,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8729403896371792,
					1.2486269264247958
				]
			]
		},
		{
			"type": "ellipse",
			"version": 497,
			"versionNonce": 468293224,
			"isDeleted": false,
			"id": "i_kPxaVEJZa-3acD3q5sV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -171.22089194359037,
			"y": 72.44790556534885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1282912024,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 502,
			"versionNonce": 1111132520,
			"isDeleted": false,
			"id": "Hr0se8vqQqytZ5tDftGgJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.8912201397909,
			"y": 72.62132597179664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.526099576741398,
			"height": 2.7053583405870287,
			"seed": 1692535832,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 545,
			"versionNonce": 2012552296,
			"isDeleted": false,
			"id": "ndYJL4HjJU5sH-4sC2ytq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -169.41731971653232,
			"y": 68.35518397317873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.993000704958198,
			"height": 0.8384459539135903,
			"seed": 435734808,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.586228401226234,
					-0.8384459539135903
				],
				[
					4.993000704958198,
					-0.444857365718071
				]
			]
		},
		{
			"type": "line",
			"version": 532,
			"versionNonce": 1592086376,
			"isDeleted": false,
			"id": "JfLaMR1-lBbFB44-HPoo3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -171.73836733392284,
			"y": 68.28533498456596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.819677709912036,
			"height": 1.486686547905812,
			"seed": 1462756888,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6433497124040102,
					-1.3557748948375248
				],
				[
					3.819677709912036,
					-1.486686547905812
				]
			]
		},
		{
			"type": "line",
			"version": 534,
			"versionNonce": 2136416872,
			"isDeleted": false,
			"id": "T58S8A0WO06A9QCuaEQ5H",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -174.00352504561496,
			"y": 68.68506869839405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.1347915078700503,
			"height": 2.388981198992249,
			"seed": 2038129432,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1033726726767847,
					-1.6222640373895194
				],
				[
					3.1347915078700503,
					-2.388981198992249
				]
			]
		},
		{
			"type": "line",
			"version": 711,
			"versionNonce": 2014745960,
			"isDeleted": false,
			"id": "xMSTK_CNbM6W0rszxffE1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -166.10274984523932,
			"y": 78.12975275067672,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.468035680497612,
			"height": 3.7308479957280527,
			"seed": 525287448,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.7078459199480815,
					-0.3840532055146051
				],
				[
					-7.038960201848123,
					0.19333993668141047
				],
				[
					-7.468035680497612,
					2.651230169011954
				],
				[
					-4.507313347604101,
					3.3467947902134476
				],
				[
					-0.43255554618207703,
					3.1499813009898583
				]
			]
		},
		{
			"type": "line",
			"version": 496,
			"versionNonce": 779069544,
			"isDeleted": false,
			"id": "5zSpaDhaSnbmna7YCIvk7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -156.26741431478706,
			"y": 78.599070472354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.009552810001913,
			"height": 0.7290096018185386,
			"seed": 2023718168,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.009552810001913,
					0.7290096018185386
				]
			]
		},
		{
			"type": "line",
			"version": 500,
			"versionNonce": 2116967272,
			"isDeleted": false,
			"id": "kVzOo3v_Hb02ffaGwfxe6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -155.2549009789281,
			"y": 82.28461901488102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.265069346467175,
			"height": 1.1340149361621554,
			"seed": 383785496,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.265069346467175,
					-1.1340149361621554
				]
			]
		},
		{
			"type": "line",
			"version": 498,
			"versionNonce": 1772007016,
			"isDeleted": false,
			"id": "xQaePn0qD9BSBvwLYYRH9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -158.21143991963655,
			"y": 83.98564141912428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.402044808486481,
			"height": 1.4580192036370632,
			"seed": 1023743768,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.402044808486481,
					-1.4580192036370632
				]
			]
		},
		{
			"type": "line",
			"version": 775,
			"versionNonce": 1233953128,
			"isDeleted": false,
			"id": "tLRDpX9DLnfDmMcrKPoVq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -170.18231432841645,
			"y": 85.19328858548768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.882651349276086,
			"height": 55.388813376175264,
			"seed": 797078552,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5745727528648912,
					8.04401854010845
				],
				[
					0.45965820229191295,
					18.386328091676436
				],
				[
					-1.7887389760249348,
					28.900257272390544
				],
				[
					-9.308078596411194,
					55.388813376175264
				]
			]
		},
		{
			"type": "line",
			"version": 606,
			"versionNonce": 2101621864,
			"isDeleted": false,
			"id": "vEAEhh9heE7PukXCo6t1w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -170.19062996727357,
			"y": 106.75033904691816,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 1.8469484480247527,
			"height": 33.86918328960181,
			"seed": 72102168,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8469484480247527,
					33.86918328960181
				]
			]
		},
		{
			"type": "line",
			"version": 528,
			"versionNonce": 445736808,
			"isDeleted": false,
			"id": "VsvPTxWmbZg13hQs5QkHC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -169.83757067669768,
			"y": 88.06615234981217,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.960900844541328,
			"height": 9.767736798703094,
			"seed": 1926647320,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.503676742400346,
					9.767736798703094
				],
				[
					-18.960900844541328,
					6.5501293826597315
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 499137128,
			"isDeleted": false,
			"id": "i0HDhnlsgIM58O7uIav52",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -169.74608911037814,
			"y": 87.8820012306914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.342246396844614,
			"height": 8.305163957086544,
			"seed": 605342488,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.958052403996862,
					8.305163957086544
				],
				[
					7.342246396844614,
					4.694223106179348
				]
			]
		},
		{
			"type": "ellipse",
			"version": 526,
			"versionNonce": 429698408,
			"isDeleted": false,
			"id": "MLUPMuwiNaY8ps277KdH5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.15776873759594867,
			"x": -193.0366575987293,
			"y": 92.09476555674978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.573858411149109,
			"height": 2.8887526807257444,
			"seed": 41658392,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 562,
			"versionNonce": 1735573608,
			"isDeleted": false,
			"id": "uOf2cJSuwuPkXfjbdNca-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.140413362159975,
			"x": -162.52178300106027,
			"y": 88.27699956605663,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.1112808199764053,
			"height": 7.582975786905106,
			"seed": 167699736,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 494,
			"versionNonce": 1460564840,
			"isDeleted": false,
			"id": "20yYIyBanrlLwQTavXYiL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -164.75095426662307,
			"y": 83.60905455711787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.296046581330532,
			"height": 4.754405453694469,
			"seed": 403866136,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 516,
			"versionNonce": 1589364328,
			"isDeleted": false,
			"id": "Q-v38mFZJ5ucPU4da_Ldv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -164.6907719191079,
			"y": 85.41452498257145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.29604658133056,
			"height": 0.9629175602419148,
			"seed": 1001029400,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.52765859563504,
					0.9629175602419148
				],
				[
					5.29604658133056,
					0.2407293900604787
				]
			]
		},
		{
			"type": "ellipse",
			"version": 508,
			"versionNonce": 1262926184,
			"isDeleted": false,
			"id": "A1v_PnftcVFgumBHfGubq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.0098189036507,
			"y": 140.3514110945762,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 0.8621003799462329,
			"seed": 87743512,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 540,
			"versionNonce": 1878740072,
			"isDeleted": false,
			"id": "bFGsY8ifTg8YkxJzKVpBJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -168.35407600382723,
			"y": 140.1962330261859,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.379506370864475,
			"height": 1.034520455935474,
			"seed": 1454872856,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 602,
			"versionNonce": 1453686632,
			"isDeleted": false,
			"id": "4LW62rBHBEXWxhPJDNIXr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.267561578559105,
			"x": -163.79498297868588,
			"y": 88.77898319259008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 4.647933303273467,
			"height": 2.1780710122005775,
			"seed": 865383960,
			"groupIds": [
				"NPjcUd91aDesmF8M42LiQ",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 3056,
			"versionNonce": 1871794792,
			"isDeleted": false,
			"id": "NmPPZWIMoqevv8M4PH44a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -13.713994400094464,
			"y": 15.39935043163399,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 33.68562713673201,
			"height": 31.004403888654263,
			"seed": 281424664,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-QP2qEdfAxGNcqs4LCF27",
					"type": "arrow"
				}
			],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3119,
			"versionNonce": 433969256,
			"isDeleted": false,
			"id": "VXR9BSCJ1z-RmVMCbsdgT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1.6872577878051231,
			"y": 46.23191660980547,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 1.652895272932641,
			"height": 37.587595557758085,
			"seed": 616566808,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.652895272932641,
					37.587595557758085
				]
			]
		},
		{
			"type": "line",
			"version": 3072,
			"versionNonce": 1012304744,
			"isDeleted": false,
			"id": "WYWonKLiybvcUwU6qZ1PX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0.38759940662302483,
			"y": 84.78216435077944,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 14.879211836685531,
			"height": 22.92288158091874,
			"seed": 930499864,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.879211836685531,
					22.92288158091874
				]
			]
		},
		{
			"type": "line",
			"version": 3049,
			"versionNonce": 323018344,
			"isDeleted": false,
			"id": "F5rAT2o5Q4Dff1Cni6h5o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1.7572272065004597,
			"y": 83.29810182129746,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 12.731078857931479,
			"height": 21.295221350320972,
			"seed": 1918691864,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.731078857931479,
					21.295221350320972
				]
			]
		},
		{
			"type": "line",
			"version": 3200,
			"versionNonce": 1600704872,
			"isDeleted": false,
			"id": "fbdUfMbVHXZZ7D7ybeScJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -15.79280119661837,
			"y": 30.3517480839361,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 24.731567133608714,
			"height": 30.14871415942204,
			"seed": 812115736,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.12273385002255,
					30.14871415942204
				],
				[
					16.60883328358616,
					24.639083004376545
				]
			]
		},
		{
			"type": "line",
			"version": 3215,
			"versionNonce": 1746560104,
			"isDeleted": false,
			"id": "ecY2n9ZBTMXpA3D_rEVMM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0.8326243306992467,
			"y": 54.54793298284915,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 13.38199598516125,
			"height": 33.007136033602166,
			"seed": 1309361176,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.944961765921084,
					15.241069564779155
				],
				[
					13.38199598516125,
					33.007136033602166
				]
			]
		},
		{
			"type": "text",
			"version": 852,
			"versionNonce": 723621736,
			"isDeleted": false,
			"id": "LDdD9mpc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6.566473450050353,
			"y": 29.937215633836445,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 23.2273668549511,
			"height": 15.793732169832948,
			"seed": 2033910040,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"fontSize": 11.148516825764439,
			"fontFamily": 1,
			"text": "ಠ_ಠ",
			"rawText": "ಠ_ಠ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ಠ_ಠ",
			"lineHeight": 1.4166666666666656
		},
		{
			"type": "line",
			"version": 783,
			"versionNonce": 214592104,
			"isDeleted": false,
			"id": "yozPX0dTszlr0vhYpDlFg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -9.942089343852729,
			"y": 29.2648438926809,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 39.0999472182744,
			"height": 33.357996927478865,
			"seed": 23797272,
			"groupIds": [
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.017939244305657,
					1.0025627491865183
				],
				[
					-17.86384534914168,
					-2.3696937708045054
				],
				[
					-28.345183181546243,
					-16.40557225941584
				],
				[
					-34.178275540449654,
					-15.31186744212144
				],
				[
					-37.36824792422496,
					-8.0205019934922
				],
				[
					-39.0999472182744,
					4.10139306485396
				],
				[
					-36.82139551557776,
					14.30930469293492
				],
				[
					-29.347745930732767,
					16.95242466806302
				],
				[
					-24.790642525339475,
					9.84334335564949
				],
				[
					-16.496714327523694,
					5.650808222687669
				],
				[
					-4.739387541609012,
					2.9165461794516947
				],
				[
					-0.09114206810786049,
					2.2785517026966446
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 442,
			"versionNonce": 132177256,
			"isDeleted": false,
			"id": "dSpmHziddy7lN3d_T1oMi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -49.40660483455869,
			"y": 11.947850952186371,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 17.04356673617089,
			"height": 34.99855415342048,
			"seed": 663722776,
			"groupIds": [
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 328,
			"versionNonce": 1571876968,
			"isDeleted": false,
			"id": "RZLjTzCRU1I9FU5pdeboH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -36.197879709622555,
			"y": 24.23960687600453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 1.9785318789637691,
			"height": 11.77226467983445,
			"seed": 1847359512,
			"groupIds": [
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.9892659394818812,
					6.1334488247877
				],
				[
					0.9892659394818879,
					11.77226467983445
				]
			]
		},
		{
			"type": "line",
			"version": 418,
			"versionNonce": 1174840168,
			"isDeleted": false,
			"id": "i_RR3zOwEnkrc1cgiAc7h",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -38.17641158858649,
			"y": 17.809378269372246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 3.2645776002902287,
			"height": 23.445602765720704,
			"seed": 1761981720,
			"groupIds": [
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.572091442652906,
					6.331302012684072
				],
				[
					-2.769944630549285,
					15.531475249865606
				],
				[
					0.49463296974094395,
					23.445602765720704
				]
			]
		},
		{
			"type": "line",
			"version": 417,
			"versionNonce": 523105896,
			"isDeleted": false,
			"id": "IPIP-OtCGeUY-srpEBTYV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -40.1549434675502,
			"y": 14.544800669082036,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 5.44096266715037,
			"height": 29.38119840261202,
			"seed": 230642200,
			"groupIds": [
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.759210570031166,
					5.935595636891314
				],
				[
					-4.748476509513054,
					13.651869964850025
				],
				[
					-3.8581371639793653,
					21.565997480705114
				],
				[
					0.6924861576373161,
					29.38119840261202
				]
			]
		},
		{
			"type": "line",
			"version": 473,
			"versionNonce": 502458728,
			"isDeleted": false,
			"id": "08KwR00ZhhnO-qphqFu6P",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -43.10271862527915,
			"y": 17.90568227961569,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 9.722906753787953,
			"height": 18.422349638756096,
			"seed": 54349592,
			"groupIds": [
				"jgPq5mV4Yn2wVRTxpja1h",
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.801437227044921,
					-1.4620912411711093
				],
				[
					-2.997287044400786,
					-7.52976989203125
				],
				[
					-8.26081551261683,
					-9.869115877905061
				],
				[
					-6.213887774977261,
					-16.448526463175092
				],
				[
					-9.722906753787953,
					-18.422349638756096
				]
			]
		},
		{
			"type": "line",
			"version": 486,
			"versionNonce": 2107735144,
			"isDeleted": false,
			"id": "ckf9hmLqW-ZzLewzCRuf1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.880691983504505,
			"y": 24.411988302827183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 20.834800186688447,
			"height": 9.942220439963602,
			"seed": 1911794712,
			"groupIds": [
				"jgPq5mV4Yn2wVRTxpja1h",
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.482842154391692,
					-0.2924182482342165
				],
				[
					-7.237351643797031,
					-4.678691971747571
				],
				[
					-14.036075915242739,
					-4.313169161454813
				],
				[
					-15.278853470238198,
					-9.649802191729385
				],
				[
					-20.834800186688447,
					-9.942220439963602
				]
			]
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 805678952,
			"isDeleted": false,
			"id": "wQvjF0c3GlvyHnB_dUSk4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.51516917321152,
			"y": 30.845189763980173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 30.630811502534968,
			"height": 5.409737592333139,
			"seed": 1406560536,
			"groupIds": [
				"jgPq5mV4Yn2wVRTxpja1h",
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.8014372270449215,
					2.1200322996981096
				],
				[
					-9.576697629670845,
					0.07310456205854085
				],
				[
					-15.86368996670666,
					3.8745417891034615
				],
				[
					-21.9313686175668,
					2.4855551099908935
				],
				[
					-26.244537779021613,
					5.409737592333139
				],
				[
					-30.630811502534968,
					3.8745417891034615
				]
			]
		},
		{
			"type": "line",
			"version": 549,
			"versionNonce": 225149544,
			"isDeleted": false,
			"id": "yS4v-ShgT-N11kRNKZwcX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.29856844263517,
			"y": 39.106005276596974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 25.80591040667029,
			"height": 20.615486500512812,
			"seed": 1146717720,
			"groupIds": [
				"jgPq5mV4Yn2wVRTxpja1h",
				"qQb9eiwLkKkwwE_578q65",
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.874541789103462,
					0.43862737235135135
				],
				[
					-4.898005657923247,
					4.532482847630489
				],
				[
					-11.184997994959062,
					6.4332014611529225
				],
				[
					-13.378134856715754,
					10.746370622607737
				],
				[
					-19.37270894551734,
					12.939507484364427
				],
				[
					-20.688591062571355,
					16.96025839758501
				],
				[
					-25.80591040667029,
					20.615486500512812
				]
			]
		},
		{
			"type": "ellipse",
			"version": 243,
			"versionNonce": 77526376,
			"isDeleted": false,
			"id": "gLCRhgAYK0BRdy69EQRTw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -15.491282869508382,
			"y": 28.04794533372231,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 3.2548247048012406,
			"height": 2.967634289671722,
			"seed": 1349583640,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 297,
			"versionNonce": 1256982632,
			"isDeleted": false,
			"id": "MZK0y4wU0W_T7sAaaf-l1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -15.012632177625846,
			"y": 31.15917483095872,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 2.201793182659656,
			"height": 2.010332905906653,
			"seed": 1183899672,
			"groupIds": [
				"dk4cvkmhbJeHZbbTTUNoC",
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 765,
			"versionNonce": 535269656,
			"isDeleted": false,
			"id": "-QP2qEdfAxGNcqs4LCF27",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1.7124361935386787,
			"y": -10.890955288170915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 0.15450393671939086,
			"height": 20.591927230199417,
			"seed": 112008472,
			"groupIds": [
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952712,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ksvjKfKH",
				"focus": -0.11189823311075935,
				"gap": 1.965753657104024
			},
			"endBinding": {
				"elementId": "NmPPZWIMoqevv8M4PH44a",
				"focus": -0.06547492765249216,
				"gap": 5.73153558033944
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
					0.15450393671939086,
					20.591927230199417
				]
			]
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 444796520,
			"isDeleted": false,
			"id": "ksvjKfKH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -21.145904314151323,
			"y": -47.91483975569949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 40.82631029311214,
			"height": 35.05813081042455,
			"seed": 1379514904,
			"groupIds": [
				"asPtBQAeFTZ485ZH_YzUk",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-QP2qEdfAxGNcqs4LCF27",
					"type": "arrow"
				}
			],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"fontSize": 9.348834882779881,
			"fontFamily": 1,
			"text": "Me in\na social\nsituation",
			"rawText": "Me in\na social\nsituation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Me in\na social\nsituation",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1932,
			"versionNonce": 1217434728,
			"isDeleted": false,
			"id": "kQYAmRbSla3_xJOC2n3rY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 59.43783641803245,
			"y": 15.301647505534618,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.3667211608594,
			"height": 93.35216748476445,
			"seed": 472561432,
			"groupIds": [
				"OndkM3Iu_TIY7jWMBT9Ml",
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-13.793802967836688,
					10.141662174391948
				],
				[
					-27.924040154401077,
					18.694871237132165
				],
				[
					-20.01783601429956,
					2.81034012061463
				],
				[
					-14.130237186564411,
					-7.33132205377732
				],
				[
					-30.279079685495148,
					-12.341058790525132
				],
				[
					-36.67132984132187,
					-25.415249786427985
				],
				[
					-30.783731013586735,
					-40.077893893982626
				],
				[
					-11.775197655470347,
					-47.77578205044883
				],
				[
					-6.392250155826762,
					-61.338727849936845
				],
				[
					8.915506796284674,
					-70.25850301536596
				],
				[
					32.634119216589184,
					-69.15880470729932
				],
				[
					50.96978413725024,
					-74.65729624763229
				],
				[
					70.48296882345824,
					-74.16854144404714
				],
				[
					88.31398241602754,
					-67.69254029654385
				],
				[
					103.28530514941124,
					-51.808009180026325
				],
				[
					120.94810163261678,
					-47.28702724686366
				],
				[
					129.69539131953755,
					-35.06815715723482
				],
				[
					126.49926624162426,
					-19.061437339820994
				],
				[
					109.50933819587415,
					-10.141662174391897
				],
				[
					101.09848272768102,
					2.68815141971834
				],
				[
					78.05273874483198,
					10.26385087528824
				],
				[
					54.165909215163644,
					4.276604531370104
				],
				[
					38.858152263052204,
					11.852303986940008
				],
				[
					15.47597406147543,
					11.241360482458566
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 375,
			"versionNonce": 2102511464,
			"isDeleted": false,
			"id": "rX332gu2C2E27iCFYLDN7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 116.91035302949439,
			"y": -34.332590806494665,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 27.325626572843397,
			"height": 41.84833719896995,
			"seed": 1492390936,
			"groupIds": [
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d996a3c00f0036c7ef195724c7346adc5ac0b194",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 283,
			"versionNonce": 158636648,
			"isDeleted": false,
			"id": "gQ6wR3eU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 81.43597720123756,
			"y": -51.234993643162454,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 50.394073045987874,
			"height": 9.348834882779881,
			"seed": 1317654808,
			"groupIds": [
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"fontSize": 7.4790679062239045,
			"fontFamily": 1,
			"text": "Who's talking?",
			"rawText": "Who's talking?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Who's talking?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 238,
			"versionNonce": 1338314088,
			"isDeleted": false,
			"id": "Zi9OFlgC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 74.27842049976726,
			"y": -35.06211342074366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 20.986312647084773,
			"height": 9.348834882779881,
			"seed": 1684008472,
			"groupIds": [
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"fontSize": 7.4790679062239045,
			"fontFamily": 1,
			"text": "Friend",
			"rawText": "Friend",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Friend",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 271,
			"versionNonce": 2039423080,
			"isDeleted": false,
			"id": "YjQuw675",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 67.39476788179786,
			"y": -18.688562575654203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 34.05973869650854,
			"height": 9.348834882779881,
			"seed": 1936354072,
			"groupIds": [
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"fontSize": 7.4790679062239045,
			"fontFamily": 1,
			"text": "Colleague",
			"rawText": "Colleague",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Colleague",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 214,
			"versionNonce": 647943016,
			"isDeleted": false,
			"id": "E2Pm6VlN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 63.08885889889433,
			"y": 0.8387879703186343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 45.166194765086686,
			"height": 9.348834882779881,
			"seed": 371017752,
			"groupIds": [
				"O0gIgdXbMJFoKtkOXu5um"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1716984952314,
			"link": null,
			"locked": false,
			"fontSize": 7.4790679062239045,
			"fontFamily": 1,
			"text": "un-important",
			"rawText": "un-important",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "un-important",
			"lineHeight": 1.25
		},
		{
			"id": "L6KrgCOW",
			"type": "text",
			"x": 652.2967519921235,
			"y": 268.6506650300724,
			"width": 435.2618408203125,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2060007272,
			"version": 259,
			"versionNonce": 1846172952,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716984290803,
			"link": null,
			"locked": false,
			"text": "Independent Component analysis\n(ICA)",
			"rawText": "Independent Component analysis\n(ICA)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Independent Component analysis\n(ICA)",
			"lineHeight": 1.25
		},
		{
			"id": "LdoINES4",
			"type": "text",
			"x": 500.87693502407694,
			"y": 359.969960319789,
			"width": 746.439208984375,
			"height": 275,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1270392424,
			"version": 426,
			"versionNonce": 1952002328,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985690144,
			"link": null,
			"locked": false,
			"text": "ICA main assumption and approach to the cocktail problem is\nstatistical independence\n\n\n\n\nhigher cross moments should vanish and we are only left with the signals\nthemselves.\nto help us reach this we try to minimize the divergence between the actual\ndistribution and the combination of independent distributions\nthere are many algorithms to do ICA, we will talk about a few here:",
			"rawText": "ICA main assumption and approach to the cocktail problem is\nstatistical independence\n\n\n\n\nhigher cross moments should vanish and we are only left with the signals\nthemselves.\nto help us reach this we try to minimize the divergence between the actual\ndistribution and the combination of independent distributions\nthere are many algorithms to do ICA, we will talk about a few here:",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ICA main assumption and approach to the cocktail problem is\nstatistical independence\n\n\n\n\nhigher cross moments should vanish and we are only left with the signals\nthemselves.\nto help us reach this we try to minimize the divergence between the actual\ndistribution and the combination of independent distributions\nthere are many algorithms to do ICA, we will talk about a few here:",
			"lineHeight": 1.25
		},
		{
			"id": "dtclNYHrOsRyXM8WVKB0O",
			"type": "image",
			"x": 769.1268704230721,
			"y": 425.12262072099776,
			"width": 212.59740498467147,
			"height": 73.06164340318287,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 191807768,
			"version": 108,
			"versionNonce": 1931102824,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716984375277,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4c993c830fa770afa5bbb9c65e22df48c1a4d503",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "p9iTLzR3Vhn5RTkyP7YQV",
			"type": "image",
			"x": 709.6920761508595,
			"y": 703.3545359277331,
			"width": 325.1153606858588,
			"height": 104.15826485425647,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 340620056,
			"version": 164,
			"versionNonce": 1067635480,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "B6ppmzfIamHBDrZ9Wx5dW",
					"type": "arrow"
				}
			],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f2f339b9a4e3656505452477bb6f9660b6bc428f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "7xK552E8",
			"type": "text",
			"x": 501.9088981651355,
			"y": 813.972334098537,
			"width": 780.09912109375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1182105448,
			"version": 154,
			"versionNonce": 262860056,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "Which helps us find w to calculate ui such that they independently represent u",
			"rawText": "Which helps us find w to calculate ui such that they independently represent u",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which helps us find w to calculate ui such that they independently represent u",
			"lineHeight": 1.25
		},
		{
			"id": "EGcEEDp0-ATUHH8RK7nCW",
			"type": "image",
			"x": 821.3706788115308,
			"y": 845.4318687873708,
			"width": 141.17555917625987,
			"height": 33.68962207615292,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 823104360,
			"version": 120,
			"versionNonce": 452823576,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3f0379064db456c67c11853582584e95a629a1b5",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "B6ppmzfIamHBDrZ9Wx5dW",
			"type": "arrow",
			"x": 1041.9665062693161,
			"y": 765.6617405237548,
			"width": 452.53336482296095,
			"height": 3.9435512710149396,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 623249000,
			"version": 340,
			"versionNonce": 127788136,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716985721921,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					452.53336482296095,
					-3.9435512710149396
				]
			],
			"lastCommittedPoint": [
				335.3388267534249,
				-3.481025883253551
			],
			"startBinding": {
				"elementId": "p9iTLzR3Vhn5RTkyP7YQV",
				"focus": 0.21884085449688886,
				"gap": 7.159069432597789
			},
			"endBinding": {
				"elementId": "rOOFWvl1",
				"focus": 0.2356068265195176,
				"gap": 12.67491641024094
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "rOOFWvl1",
			"type": "text",
			"x": 1507.174787502518,
			"y": 731.7907348641075,
			"width": 345.9595947265625,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1496524392,
			"version": 186,
			"versionNonce": 2130961432,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "B6ppmzfIamHBDrZ9Wx5dW",
					"type": "arrow"
				},
				{
					"id": "ysJ5brDRbicVVKN8LzlD1",
					"type": "arrow"
				},
				{
					"id": "19KkSfgqI5GV6hK5VmEBt",
					"type": "arrow"
				}
			],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "Some quick ugly math that gets\nus the derivative of this according\nto different methods",
			"rawText": "Some quick ugly math that gets\nus the derivative of this according\nto different methods",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Some quick ugly math that gets\nus the derivative of this according\nto different methods",
			"lineHeight": 1.25
		},
		{
			"id": "ysJ5brDRbicVVKN8LzlD1",
			"type": "arrow",
			"x": 1868.5354030778738,
			"y": 767.6274596414933,
			"width": 148.13486731785247,
			"height": 44.88471073505673,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 720485144,
			"version": 464,
			"versionNonce": 1097722472,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716985721921,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					127.91931910275025,
					-0.5397439624589424
				],
				[
					148.13486731785247,
					44.344966772597786
				]
			],
			"lastCommittedPoint": [
				141.95266212668093,
				76.10389870669962
			],
			"startBinding": {
				"elementId": "rOOFWvl1",
				"focus": -0.02271572964683153,
				"gap": 15.401020848793223
			},
			"endBinding": {
				"elementId": "sgKvrcPY",
				"focus": 0.5298876275256982,
				"gap": 14.82449922680928
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "lpIPz2Az4up8LuftReN2r",
			"type": "image",
			"x": 1848.2595378379617,
			"y": 856.5242617363106,
			"width": 451.2478025983185,
			"height": 59.04176856426597,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 880326504,
			"version": 294,
			"versionNonce": 1251628312,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e22bd27cd40bc93463f1fe6840eadb1a51252d21",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "sgKvrcPY",
			"type": "text",
			"x": 1853.0860190417989,
			"y": 826.7969256409003,
			"width": 226.03973388671875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 842619160,
			"version": 123,
			"versionNonce": 331346456,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ysJ5brDRbicVVKN8LzlD1",
					"type": "arrow"
				}
			],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "Gram Chalier expansion",
			"rawText": "Gram Chalier expansion",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gram Chalier expansion",
			"lineHeight": 1.25
		},
		{
			"id": "19KkSfgqI5GV6hK5VmEBt",
			"type": "arrow",
			"x": 1673.6381734801807,
			"y": 815.5481674676323,
			"width": 1.406094771658445,
			"height": 105.45710787439089,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1117488232,
			"version": 198,
			"versionNonce": 1544838504,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721922,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.406094771658445,
					105.45710787439089
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "rOOFWvl1",
				"focus": 0.04111820086305509,
				"gap": 8.757432603524762
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "oRDPxxqD",
			"type": "text",
			"x": 1581.0487590328094,
			"y": 937.1753652160962,
			"width": 199.23977661132812,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 543705880,
			"version": 56,
			"versionNonce": 1981483288,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "Edgeworth expansion",
			"rawText": "Edgeworth expansion",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Edgeworth expansion",
			"lineHeight": 1.25
		},
		{
			"id": "DVQkFSqz4a_NNImQv4T7X",
			"type": "image",
			"x": 1435.0778957803286,
			"y": 966.190937153609,
			"width": 488.17333133710133,
			"height": 109.99718133817039,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1503934056,
			"version": 175,
			"versionNonce": 1963599384,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ix1Qf9lX04mWo08JyocMD",
					"type": "arrow"
				}
			],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c7d35282d6ad22e63400da0cd58f537865b196f4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "wpsbtJ3fNji0Ceseluyam",
			"type": "arrow",
			"x": 1725.6636800315468,
			"y": 1044.741615247975,
			"width": 54.134648708853774,
			"height": 89.2870180003174,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1990445160,
			"version": 104,
			"versionNonce": 999915544,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.921331700804785,
					45.69808007890265
				],
				[
					-49.21331700804899,
					89.2870180003174
				]
			],
			"lastCommittedPoint": [
				-49.21331700804899,
				89.2870180003174
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Y09O8pCq",
			"type": "text",
			"x": 1585.6353840413617,
			"y": 1128.4042541616584,
			"width": 91.639892578125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 970998040,
			"version": 84,
			"versionNonce": 295812376,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "Hermite\npolynomial",
			"rawText": "Hermite\npolynomial",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hermite\npolynomial",
			"lineHeight": 1.25
		},
		{
			"id": "UiYevkcHJfIFh_HDWiC9P",
			"type": "arrow",
			"x": 1565.368876062473,
			"y": 1048.2568521771213,
			"width": 57.64988563800034,
			"height": 89.99006538614663,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 378702872,
			"version": 105,
			"versionNonce": 1436178968,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-7.03047385829268,
					71.00778596875625
				],
				[
					-57.64988563800034,
					89.99006538614663
				]
			],
			"lastCommittedPoint": [
				-57.64988563800034,
				89.99006538614663
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "1XByOdQv",
			"type": "text",
			"x": 1444.2010328734518,
			"y": 1123.4829224608534,
			"width": 67.97993469238281,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1366857064,
			"version": 88,
			"versionNonce": 712464152,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "k-th\norder\nmoment",
			"rawText": "k-th\norder\nmoment",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "k-th\norder\nmoment",
			"lineHeight": 1.25
		},
		{
			"id": "ix1Qf9lX04mWo08JyocMD",
			"type": "arrow",
			"x": 1929.8697712384856,
			"y": 1030.1253937751758,
			"width": 127.8100378877748,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 144775528,
			"version": 195,
			"versionNonce": 1129980776,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721924,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					127.8100378877748,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "DVQkFSqz4a_NNImQv4T7X",
				"focus": 0.16247445332275626,
				"gap": 6.618544121055493
			},
			"endBinding": {
				"elementId": "rpvwCON9eHJgwyIf6E87u",
				"focus": 0.15948537848170743,
				"gap": 15.06070789062278
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "rpvwCON9eHJgwyIf6E87u",
			"type": "image",
			"x": 2072.740517016883,
			"y": 1009.4111437607177,
			"width": 224.75987364813037,
			"height": 49.289445975467196,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1206901864,
			"version": 131,
			"versionNonce": 1781428504,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ix1Qf9lX04mWo08JyocMD",
					"type": "arrow"
				}
			],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "728478d56a95f92aca5c26a3e6bd51d1dbd31a0f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "jcisrk10zrm9i_QVM4u6b",
			"type": "arrow",
			"x": 2212.0861554762305,
			"y": 1046.3786933909623,
			"width": 2.2163590385162024,
			"height": 48.02111250118696,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1634591848,
			"version": 157,
			"versionNonce": 638678632,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1716985721925,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.2163590385162024,
					48.02111250118696
				]
			],
			"lastCommittedPoint": [
				2.2163590385162024,
				48.02111250118696
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "DupbvPngsUk383--EtM7w",
				"focus": 0.019746838469853468,
				"gap": 4.721639638737315
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "DupbvPngsUk383--EtM7w",
			"type": "image",
			"x": 2072.603323558011,
			"y": 1099.1214455308866,
			"width": 279.7044501826107,
			"height": 30.80078766891844,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1495239704,
			"version": 123,
			"versionNonce": 8775704,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jcisrk10zrm9i_QVM4u6b",
					"type": "arrow"
				}
			],
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d20b92888df1584cf38233df4d759f4116f009a7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "B8XxfGtA",
			"type": "text",
			"x": 838.0024642156519,
			"y": 667.0795326559494,
			"width": 76.83232116699219,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1531318888,
			"version": 55,
			"versionNonce": 1217184280,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985721788,
			"link": null,
			"locked": false,
			"text": "JADE",
			"rawText": "JADE",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "JADE",
			"lineHeight": 1.25
		},
		{
			"id": "FcjJTfgq",
			"type": "text",
			"x": 832.9714626804706,
			"y": 916.820567852183,
			"width": 98.75642395019531,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1730677096,
			"version": 45,
			"versionNonce": 877128040,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985735533,
			"link": null,
			"locked": false,
			"text": "TDSEP",
			"rawText": "TDSEP",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TDSEP",
			"lineHeight": 1.25
		},
		{
			"id": "dNvDXWn_RxFGv6GuqsS4c",
			"type": "line",
			"x": 1268.716002604973,
			"y": 649.1573625205697,
			"width": 766.2879504377969,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 849166616,
			"version": 67,
			"versionNonce": 22671208,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1716985725901,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-766.2879504377969,
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
			"version": 113,
			"versionNonce": 764874264,
			"isDeleted": false,
			"id": "-fTT9HJ_STG0pnTJ7BecI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1275.682256699862,
			"y": 892.9762558416869,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 766.2879504377969,
			"height": 0,
			"seed": 1831023896,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1716985731084,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-766.2879504377969,
					0
				]
			]
		},
		{
			"id": "HJ4DMAxH",
			"type": "text",
			"x": -61.818351998599155,
			"y": 104.62529340849642,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1422797672,
			"version": 3,
			"versionNonce": 1473090664,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716983738924,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "J5aDUkuX",
			"type": "text",
			"x": 841.2906627156492,
			"y": 364.9699603197889,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1012124776,
			"version": 11,
			"versionNonce": 888369944,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716984285301,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "2V55QRB1",
			"type": "text",
			"x": 1202.3138425771267,
			"y": 657.8155624677306,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 113480808,
			"version": 2,
			"versionNonce": 1283972376,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716984617332,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "B6ppmzfIamHBDrZ9Wx5dW",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "JwBier1E",
			"type": "text",
			"x": 1983.7352054871335,
			"y": 646.0903084039851,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1348488984,
			"version": 2,
			"versionNonce": 1177061224,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716984667436,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ysJ5brDRbicVVKN8LzlD1",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "MXcY2esc",
			"type": "text",
			"x": 1723.2629346634499,
			"y": 984.5551190006765,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1234889320,
			"version": 2,
			"versionNonce": 1029515032,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716984752804,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wpsbtJ3fNji0Ceseluyam",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "3nwhdfSp",
			"type": "text",
			"x": 1551.0163251352785,
			"y": 1013.3800618196765,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1653475096,
			"version": 2,
			"versionNonce": 1221021544,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716984772552,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "UiYevkcHJfIFh_HDWiC9P",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "WJ2UXGHj",
			"type": "text",
			"x": 2205.872257926587,
			"y": 964.5046733153546,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1628016488,
			"version": 2,
			"versionNonce": 610480664,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1716984808714,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "jcisrk10zrm9i_QVM4u6b",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#ffffff",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 28,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": -86.78117029418195,
		"scrollY": 49.685259155566655,
		"zoom": {
			"value": 0.6306475128722354
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