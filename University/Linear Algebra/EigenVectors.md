---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - LinearAlgebra
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
What the fuck is an eigen-vector and why does it appear everywhere in my courses? ^88MYjtln

Consider a linear transformation A
This transformation more often than not, moves vectors
off of their own span (aka change of direction).

BUT! there are cases where certain vectors stay within the
same direction even after transformation, thus only scaling 
or descaling!

Introducing the new technology to the market:

EIGENVECTORS!!!     DUNNN DUNNN DUNNNNNNNNNN
and their side-kick the eigen-value which is just a fancy way
of saying thats how much they have been scaled...

Yes this also can be called the rotation axis :] ^ZcROQ0hZ

The only way to find a solution for this problem
is if the left hand side is 0, which means the determinant
of that matrix is zero because it squishes space into a lower
dimension!
thus we need to subtract lambda from the diagonal of A and find 
such values that lead to determinant 0 ^vi4zInb6

But how do I compute those eigenvalues?

Heres a trick you can use!

Background:
    1. The mean of a trace of a matrix is the same as the mean of the eigenvalues
       Trace being the diagonal of a matrix
    2. The determinant of our initial matrix is the product of our resulting eigenvalues

Thus we can compute our value:

Lambada  = m +/- Sqrt(m^2 - det) 
 ^K2VOdmIR

Note that a diagonal matrix is a matrix with its diagonal consisting of all
the eigenvalues and its columns all eigenvectors
this is often referred to as an eigenbases ^niElaxrb


# Embedded files
e6593e4bbec2b7bb2aea75beceda2276c3cb55cf: $$A * v = \lambda * v
$$
6c31bf424afb01fabbc10f9f65da6f91ddb3e030: $$A * v = \lambda \mathcal{I} * v$$
4d541520b6cc4d6bf39291e05a65e812df30368d: $$(A - \lambda \mathcal(I) ) * v = 0$$

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1444470955,
			"isDeleted": false,
			"id": "88MYjtln",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -589,
			"y": -408.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1161.52880859375,
			"height": 35,
			"seed": 787698405,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702733962189,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What the fuck is an eigen-vector and why does it appear everywhere in my courses?",
			"rawText": "What the fuck is an eigen-vector and why does it appear everywhere in my courses?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What the fuck is an eigen-vector and why does it appear everywhere in my courses?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 708,
			"versionNonce": 628334123,
			"isDeleted": false,
			"id": "ZcROQ0hZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -787,
			"y": -328.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 603.619384765625,
			"height": 375,
			"seed": 2013115973,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZeIV9jAhMUL0PiLYsyRjm",
					"type": "arrow"
				}
			],
			"updated": 1702734430203,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Consider a linear transformation A\nThis transformation more often than not, moves vectors\noff of their own span (aka change of direction).\n\nBUT! there are cases where certain vectors stay within the\nsame direction even after transformation, thus only scaling \nor descaling!\n\nIntroducing the new technology to the market:\n\nEIGENVECTORS!!!     DUNNN DUNNN DUNNNNNNNNNN\nand their side-kick the eigen-value which is just a fancy way\nof saying thats how much they have been scaled...\n\nYes this also can be called the rotation axis :]",
			"rawText": "Consider a linear transformation A\nThis transformation more often than not, moves vectors\noff of their own span (aka change of direction).\n\nBUT! there are cases where certain vectors stay within the\nsame direction even after transformation, thus only scaling \nor descaling!\n\nIntroducing the new technology to the market:\n\nEIGENVECTORS!!!     DUNNN DUNNN DUNNNNNNNNNN\nand their side-kick the eigen-value which is just a fancy way\nof saying thats how much they have been scaled...\n\nYes this also can be called the rotation axis :]",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider a linear transformation A\nThis transformation more often than not, moves vectors\noff of their own span (aka change of direction).\n\nBUT! there are cases where certain vectors stay within the\nsame direction even after transformation, thus only scaling \nor descaling!\n\nIntroducing the new technology to the market:\n\nEIGENVECTORS!!!     DUNNN DUNNN DUNNNNNNNNNN\nand their side-kick the eigen-value which is just a fancy way\nof saying thats how much they have been scaled...\n\nYes this also can be called the rotation axis :]",
			"lineHeight": 1.25,
			"baseline": 368
		},
		{
			"type": "image",
			"version": 209,
			"versionNonce": 2049304683,
			"isDeleted": false,
			"id": "sG0q5Ztu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -140,
			"y": -352.4286684782609,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 286.00000000000006,
			"height": 40.41304347826088,
			"seed": 8357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702734270236,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e6593e4bbec2b7bb2aea75beceda2276c3cb55cf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 98,
			"versionNonce": 268625829,
			"isDeleted": false,
			"id": "pXv0VsZB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -111,
			"y": -304.015625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 251.0769230769231,
			"height": 32,
			"seed": 27655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702734348874,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6c31bf424afb01fabbc10f9f65da6f91ddb3e030",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 45,
			"versionNonce": 181413093,
			"isDeleted": false,
			"id": "Qc5-MZcR9IDFuEOuKQvEn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -156,
			"y": -362.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 324,
			"height": 128,
			"seed": 1680114283,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "SyWfWyaGS1FxGTiL5AMy7",
					"type": "arrow"
				}
			],
			"updated": 1702734442660,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 66,
			"versionNonce": 1896121605,
			"isDeleted": false,
			"id": "ZeIV9jAhMUL0PiLYsyRjm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -561,
			"y": 69.7421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 196,
			"height": 134,
			"seed": 875641413,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702734432771,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZcROQ0hZ",
				"focus": 0.4017874859521568,
				"gap": 23
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
					38,
					113
				],
				[
					196,
					134
				]
			]
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 1506236965,
			"isDeleted": false,
			"id": "SyWfWyaGS1FxGTiL5AMy7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3,
			"y": -218.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7,
			"height": 276,
			"seed": 227182699,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702734506467,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Qc5-MZcR9IDFuEOuKQvEn",
				"focus": 0.030735163861824625,
				"gap": 16
			},
			"endBinding": {
				"elementId": "ONvVdlSO",
				"focus": 0.07715280977911028,
				"gap": 12.821134868421062
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
					7,
					276
				]
			]
		},
		{
			"type": "image",
			"version": 120,
			"versionNonce": 780324229,
			"isDeleted": false,
			"id": "ONvVdlSO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.5,
			"y": 70.56332236842104,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 238,
			"height": 30.42105263157895,
			"seed": 40680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SyWfWyaGS1FxGTiL5AMy7",
					"type": "arrow"
				}
			],
			"updated": 1702734506467,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4d541520b6cc4d6bf39291e05a65e812df30368d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 370,
			"versionNonce": 1062036427,
			"isDeleted": false,
			"id": "vi4zInb6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -328,
			"y": 108.7421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 669.71923828125,
			"height": 150,
			"seed": 477556805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ijHuMvzjsPEdw9I3GLO1I",
					"type": "arrow"
				}
			],
			"updated": 1702734919027,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The only way to find a solution for this problem\nis if the left hand side is 0, which means the determinant\nof that matrix is zero because it squishes space into a lower\ndimension!\nthus we need to subtract lambda from the diagonal of A and find \nsuch values that lead to determinant 0",
			"rawText": "The only way to find a solution for this problem\nis if the left hand side is 0, which means the determinant\nof that matrix is zero because it squishes space into a lower\ndimension!\nthus we need to subtract lambda from the diagonal of A and find \nsuch values that lead to determinant 0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The only way to find a solution for this problem\nis if the left hand side is 0, which means the determinant\nof that matrix is zero because it squishes space into a lower\ndimension!\nthus we need to subtract lambda from the diagonal of A and find \nsuch values that lead to determinant 0",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "embeddable",
			"version": 97,
			"versionNonce": 868480427,
			"isDeleted": false,
			"id": "ddwQComx-weWi5RpDxLCV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -335,
			"y": 292.7421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 699,
			"height": 393.1875,
			"seed": 1897702475,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702734777671,
			"link": "https://www.youtube.com/watch?v=PFDu9oVAE-g&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=14",
			"locked": false,
			"validated": true,
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ijHuMvzjsPEdw9I3GLO1I",
			"type": "arrow",
			"x": 361.514404296875,
			"y": 196.013671875,
			"width": 181.25,
			"height": 427.5,
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
			"seed": 2085073221,
			"version": 141,
			"versionNonce": 172756907,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702734926862,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					165,
					-28.75
				],
				[
					115,
					-391.25
				],
				[
					181.25,
					-427.5
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "vi4zInb6",
				"focus": 0.5554495546303649,
				"gap": 19.795166015625
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "K2VOdmIR",
			"type": "text",
			"x": 590.264404296875,
			"y": -310.236328125,
			"width": 868.59912109375,
			"height": 325,
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
			"seed": 1992712427,
			"version": 514,
			"versionNonce": 1446822411,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702735342094,
			"link": null,
			"locked": false,
			"text": "But how do I compute those eigenvalues?\n\nHeres a trick you can use!\n\nBackground:\n    1. The mean of a trace of a matrix is the same as the mean of the eigenvalues\n       Trace being the diagonal of a matrix\n    2. The determinant of our initial matrix is the product of our resulting eigenvalues\n\nThus we can compute our value:\n\nLambada  = m +/- Sqrt(m^2 - det) \n",
			"rawText": "But how do I compute those eigenvalues?\n\nHeres a trick you can use!\n\nBackground:\n    1. The mean of a trace of a matrix is the same as the mean of the eigenvalues\n       Trace being the diagonal of a matrix\n    2. The determinant of our initial matrix is the product of our resulting eigenvalues\n\nThus we can compute our value:\n\nLambada  = m +/- Sqrt(m^2 - det) \n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 318,
			"containerId": null,
			"originalText": "But how do I compute those eigenvalues?\n\nHeres a trick you can use!\n\nBackground:\n    1. The mean of a trace of a matrix is the same as the mean of the eigenvalues\n       Trace being the diagonal of a matrix\n    2. The determinant of our initial matrix is the product of our resulting eigenvalues\n\nThus we can compute our value:\n\nLambada  = m +/- Sqrt(m^2 - det) \n",
			"lineHeight": 1.25
		},
		{
			"id": "niElaxrb",
			"type": "text",
			"x": 614.014404296875,
			"y": 97.263671875,
			"width": 743.7991943359375,
			"height": 75,
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
			"seed": 162689765,
			"version": 181,
			"versionNonce": 133937771,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702735540019,
			"link": null,
			"locked": false,
			"text": "Note that a diagonal matrix is a matrix with its diagonal consisting of all\nthe eigenvalues and its columns all eigenvectors\nthis is often referred to as an eigenbases",
			"rawText": "Note that a diagonal matrix is a matrix with its diagonal consisting of all\nthe eigenvalues and its columns all eigenvectors\nthis is often referred to as an eigenbases",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Note that a diagonal matrix is a matrix with its diagonal consisting of all\nthe eigenvalues and its columns all eigenvectors\nthis is often referred to as an eigenbases",
			"lineHeight": 1.25
		},
		{
			"id": "MRG0J9Bb",
			"type": "text",
			"x": 651.514404296875,
			"y": -55.236328125,
			"width": 9.999984741210938,
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
			"seed": 1972604075,
			"version": 4,
			"versionNonce": 418855333,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702735275235,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
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
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 410.985595703125,
		"scrollY": 617.091796875,
		"zoom": {
			"value": 0.8
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