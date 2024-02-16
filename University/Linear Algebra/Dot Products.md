---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
What is a dot product? ^FBbXNbwN

Imagine that you have 2 vectors v and w ^iiafPJ01

v ^c1oW4IvE

w ^IJLpOWKC

The dot product of those two vector
v.dot(w)
or known as
v^T * w

Is the length of w multiplied by the
length of the projection of v onto
w ^dYxK8Hle

V is a nx1 vector
w is a nx1 vector
in order to achieve a scalar
we need a 1xn * nx1 matrix multiplication
which is achieved by transposing the first! ^jcGu4kb7

* If the two vectors are perpendicular
then the projection is the point (0,0)
with length 0 therefore the entire 
product is 0! ^BHsw7r2m

Commutative and symmetric ^iUUdBmFE

This is because we can always descale
both vectors to be the same length
then calculate the symmetric projection
then multiply by the scale ^vQhanJMx

* The dot product can also be though about as a
linear transformation that projects points onto its 
column space multiplied by its length ^jiVhQsOs


# Embedded files
5e531b2d35b854dd98551bee776860e55180a571: [[Pasted Image 20231216133704_570.png]]

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
			"version": 55,
			"versionNonce": 1918380139,
			"isDeleted": false,
			"id": "FBbXNbwN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165,
			"y": -397.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 328.609375,
			"height": 35,
			"seed": 832359147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702728167014,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is a dot product?",
			"rawText": "What is a dot product?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is a dot product?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 485304261,
			"isDeleted": false,
			"id": "iiafPJ01",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -732,
			"y": -318.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 418.05950927734375,
			"height": 25,
			"seed": 924433163,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702728167014,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Imagine that you have 2 vectors v and w",
			"rawText": "Imagine that you have 2 vectors v and w",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Imagine that you have 2 vectors v and w",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 167,
			"versionNonce": 446661829,
			"isDeleted": false,
			"id": "PxJaAQD4O7C3hg15NMqus",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -518.6966889629882,
			"y": -282.6179068740321,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 339,
			"seed": 1068714411,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728262875,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					339
				]
			]
		},
		{
			"type": "line",
			"version": 232,
			"versionNonce": 71083045,
			"isDeleted": false,
			"id": "6BbWuOHi6eghNDqX-2RrS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -738.6966889629882,
			"y": -111.61790687403212,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 431,
			"height": 0,
			"seed": 1214718885,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728262875,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					431,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 285,
			"versionNonce": 1697438475,
			"isDeleted": false,
			"id": "8_6rXKNJUQgF6MZRCvyGR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -519.6966889629882,
			"y": -110.61790687403212,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 76,
			"height": 135,
			"seed": 1177772261,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728263017,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "c1oW4IvE",
				"focus": -1.8059091627238868,
				"gap": 15.540008544921875
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
					57,
					-103
				],
				[
					76,
					-135
				]
			]
		},
		{
			"type": "arrow",
			"version": 272,
			"versionNonce": 2022916523,
			"isDeleted": false,
			"id": "YPZ4H9RPk5_MQ54owtQla",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -520.6966889629882,
			"y": -111.61790687403212,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 102,
			"height": 43,
			"seed": 1541932933,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728263017,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "IJLpOWKC",
				"focus": -0.27438995048940407,
				"gap": 9
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
					75,
					-30
				],
				[
					102,
					-43
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1371044421,
			"isDeleted": false,
			"id": "c1oW4IvE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -469.6966889629882,
			"y": -261.6179068740321,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 10.459991455078125,
			"height": 25,
			"seed": 1619366053,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8_6rXKNJUQgF6MZRCvyGR",
					"type": "arrow"
				}
			],
			"updated": 1702728262875,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "v",
			"rawText": "v",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "v",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 708340997,
			"isDeleted": false,
			"id": "IJLpOWKC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -409.6966889629882,
			"y": -178.61790687403212,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.17999267578125,
			"height": 25,
			"seed": 266209963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YPZ4H9RPk5_MQ54owtQla",
					"type": "arrow"
				}
			],
			"updated": 1702728262875,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "w",
			"rawText": "w",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1784286597,
			"isDeleted": false,
			"id": "dYxK8Hle",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -233.33576998322292,
			"y": -205.62272606745455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 376.11956787109375,
			"height": 200,
			"seed": 2035984869,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702728349091,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The dot product of those two vector\nv.dot(w)\nor known as\nv^T * w\n\nIs the length of w multiplied by the\nlength of the projection of v onto\nw",
			"rawText": "The dot product of those two vector\nv.dot(w)\nor known as\nv^T * w\n\nIs the length of w multiplied by the\nlength of the projection of v onto\nw",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The dot product of those two vector\nv.dot(w)\nor known as\nv^T * w\n\nIs the length of w multiplied by the\nlength of the projection of v onto\nw",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 277,
			"versionNonce": 1264999205,
			"isDeleted": false,
			"id": "fFdyORVfC3u3EujrWia_a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -94.09339870747908,
			"y": -116.9028180884822,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 345.21460998522684,
			"height": 294.13693809965764,
			"seed": 998125637,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728374161,
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
					-186.69769723690843,
					48.43572333976397
				],
				[
					-182.29444966056622,
					269.47875167214147
				],
				[
					-345.21460998522684,
					294.13693809965764
				]
			]
		},
		{
			"type": "text",
			"version": 217,
			"versionNonce": 111560005,
			"isDeleted": false,
			"id": "jcGu4kb7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -619.7342423237053,
			"y": 145.53073746151176,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 414.3794860839844,
			"height": 125,
			"seed": 1989783173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702728425665,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "V is a nx1 vector\nw is a nx1 vector\nin order to achieve a scalar\nwe need a 1xn * nx1 matrix multiplication\nwhich is achieved by transposing the first!",
			"rawText": "V is a nx1 vector\nw is a nx1 vector\nin order to achieve a scalar\nwe need a 1xn * nx1 matrix multiplication\nwhich is achieved by transposing the first!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V is a nx1 vector\nw is a nx1 vector\nin order to achieve a scalar\nwe need a 1xn * nx1 matrix multiplication\nwhich is achieved by transposing the first!",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "line",
			"version": 65,
			"versionNonce": 1840028715,
			"isDeleted": false,
			"id": "B1WdAnmvIDb5MIVQTZK8R",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -420.0697318752946,
			"y": -156.60878330716756,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.610401619061406,
			"height": 34.88900317895653,
			"seed": 275740677,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728447007,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-52.610401619061406,
					-34.88900317895653
				]
			]
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 1884867787,
			"isDeleted": false,
			"id": "BHsw7r2m",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 214.68814243887135,
			"y": -320.9733519512687,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 387.6795654296875,
			"height": 100,
			"seed": 1353484133,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702728522585,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* If the two vectors are perpendicular\nthen the projection is the point (0,0)\nwith length 0 therefore the entire \nproduct is 0!",
			"rawText": "* If the two vectors are perpendicular\nthen the projection is the point (0,0)\nwith length 0 therefore the entire \nproduct is 0!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* If the two vectors are perpendicular\nthen the projection is the point (0,0)\nwith length 0 therefore the entire \nproduct is 0!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1425134699,
			"isDeleted": false,
			"id": "iUUdBmFE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.32341556426107676,
			"x": 29.757341488120126,
			"y": -146.81797248790176,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 137.58607482910156,
			"height": 12.899802226976577,
			"seed": 243296677,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4LiZT1YVeROI9uawldQR9",
					"type": "arrow"
				}
			],
			"updated": 1702728620992,
			"link": null,
			"locked": false,
			"fontSize": 10.319841781581262,
			"fontFamily": 1,
			"text": "Commutative and symmetric",
			"rawText": "Commutative and symmetric",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Commutative and symmetric",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "arrow",
			"version": 91,
			"versionNonce": 81858437,
			"isDeleted": false,
			"id": "4LiZT1YVeROI9uawldQR9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 161.5013617128712,
			"y": -141.18705090563464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.13335598740855,
			"height": 8.240205464591554,
			"seed": 364984421,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702728625718,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "iUUdBmFE",
				"focus": -0.21876244837453412,
				"gap": 14.283942193512644
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
					75.6600683567043,
					5.243767113830984
				],
				[
					98.13335598740855,
					8.240205464591554
				]
			]
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1544019621,
			"isDeleted": false,
			"id": "vQhanJMx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 288.84999162019534,
			"y": -146.43081801946562,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 310.7686767578125,
			"height": 80,
			"seed": 1906980331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702728681033,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is because we can always descale\nboth vectors to be the same length\nthen calculate the symmetric projection\nthen multiply by the scale",
			"rawText": "This is because we can always descale\nboth vectors to be the same length\nthen calculate the symmetric projection\nthen multiply by the scale",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is because we can always descale\nboth vectors to be the same length\nthen calculate the symmetric projection\nthen multiply by the scale",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 851659141,
			"isDeleted": false,
			"id": "jiVhQsOs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 217.22061375354497,
			"y": -2.103998497114162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 414.4168701171875,
			"height": 60,
			"seed": 1994668907,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702729055280,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* The dot product can also be though about as a\nlinear transformation that projects points onto its \ncolumn space multiplied by its length",
			"rawText": "* The dot product can also be though about as a\nlinear transformation that projects points onto its \ncolumn space multiplied by its length",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* The dot product can also be though about as a\nlinear transformation that projects points onto its \ncolumn space multiplied by its length",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "embeddable",
			"version": 123,
			"versionNonce": 1200603429,
			"isDeleted": false,
			"id": "NuCVEeeTH9rGKc02h2mq9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 240.05155035321536,
			"y": 66.38881130189736,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 360.7287982747946,
			"height": 202.90994902957198,
			"seed": 42024907,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702730158700,
			"link": "https://www.youtube.com/watch?v=LyGKycYT2v0&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=9",
			"locked": false,
			"validated": true,
			"scale": [
				1,
				1
			]
		},
		{
			"id": "vb7fNWnUrLRMNY95TpplP",
			"type": "image",
			"x": -103.7573870686,
			"y": -350.77573990019647,
			"width": 189,
			"height": 41,
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
			"seed": 251322955,
			"version": 16,
			"versionNonce": 1370106501,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702730222133,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e531b2d35b854dd98551bee776860e55180a571",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 803.5431013543142,
		"scrollY": 525.0227637097203,
		"zoom": {
			"value": 1.05
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