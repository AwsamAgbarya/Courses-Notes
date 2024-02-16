---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Visibility ^ks4kWoAo

What is Visibility? ^EeUEcpAe

While rendering different objects, sometimes you come across
two objects that lie on the same coordinates in 2D projections
or one object partially occluded by the other, or one object
being partially transparent, we need an algorithm that decides
what to show! ^JfFKBO80

Idea! ^VOipVBBu

Painter's algorithm! ^UdOJ7Eab

1. Sort polygons according to Z depth value

2. Paint back to front

3. Preform incidence if two polygons possibly intersect
and may need to be cut ^gZShjwOd

BSP ^WHxp2ag9

Each line is defined by its norm and splits
the scene into 2 half spaces!
we can form a tree that stores all the
lines in the scene ordered based off of
the halfspace they're in! ^8QCSHkgs

0. Order the lines in a random way lets say for example A,B,C...

1. Start from the beginning line and insert into tree

2. Move over to the next line

3. If this line is the negative halfspace of the root, traverse right
if this line is in the positive halfspace of the root traverse left

4. If it is in both then divide the segment into 2 using its
intersection with the span of the original line and
treat them as 2 diff nodes

5. traverse down the tree accordingly and place in leaf

6. Repeat steps 2-5 ^aWKaeebM

Now we have an ordered tree of lines to draw! ^DU1lXovY

but how do I traverse it? ^9ZGJ2MoL

Since order of occlusion is based off of the eye location
Traversal is based off of the eye location! ^ynNTk6PK

If your eye is in the negative halfspace of the root
then the furthest away from it are the ones
in the positive halfspace
the same concept applies to each node and thus
we need to test at every level whether left or right
is further away from us ^1CrAwxgJ

Z-Buffer Algorithm ^sS5SDoUG

Each pixel has a Z value that indicates depth

At the very start Z is the maximal potential value
We rasterize one object at a time and check
whether its Z is further or closer than the pixel's Z value
which decides on whether we should proceed or not ^R8baorYR

Pros ^W8sX4y4I

Complexity is independent of depth complexity

Objects can be inserted after computation without recomputation

Very easy to realize in hardware ^uuZaHIYo

Cons ^KGmzVw1L

Only one object

Transparency is impossible!

Two objects can map to the same Value
Z fighting occurs where 2 objects share the same depth value and thus
the process has to pick one of them which is purely random due to
parallelization
Decision is based off of order! ^Q763QChU

Can be avoided or minimized if we
set our far plane as close as makes sense
that way our z buffer has more useable gaps ^MPRXAKjI


# Embedded files
9e5edfcf4b4f7a29c6d9f1756c9b5ffe7f3207af: [[Pasted Image 20231218135942_880.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"type": "ellipse",
			"version": 69,
			"versionNonce": 1685828150,
			"isDeleted": false,
			"id": "-30bX429FVdptNCJTsyU7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -262,
			"y": -434.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 497,
			"height": 206,
			"seed": 614480426,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ks4kWoAo"
				}
			],
			"updated": 1702843300677,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 2012754986,
			"isDeleted": false,
			"id": "ks4kWoAo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -81.05405544956409,
			"y": -353.5898109622144,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.67604064941406,
			"height": 45,
			"seed": 1599466026,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843300677,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Visibility",
			"rawText": "Visibility",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "-30bX429FVdptNCJTsyU7",
			"originalText": "Visibility",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1240726390,
			"isDeleted": false,
			"id": "EeUEcpAe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -133,
			"y": -211.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 236.34893798828125,
			"height": 35,
			"seed": 35612406,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843300677,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is Visibility?",
			"rawText": "What is Visibility?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is Visibility?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 369,
			"versionNonce": 2079596266,
			"isDeleted": false,
			"id": "JfFKBO80",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -317,
			"y": -176.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 632.1793212890625,
			"height": 125,
			"seed": 678056630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843300677,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "While rendering different objects, sometimes you come across\ntwo objects that lie on the same coordinates in 2D projections\nor one object partially occluded by the other, or one object\nbeing partially transparent, we need an algorithm that decides\nwhat to show!",
			"rawText": "While rendering different objects, sometimes you come across\ntwo objects that lie on the same coordinates in 2D projections\nor one object partially occluded by the other, or one object\nbeing partially transparent, we need an algorithm that decides\nwhat to show!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "While rendering different objects, sometimes you come across\ntwo objects that lie on the same coordinates in 2D projections\nor one object partially occluded by the other, or one object\nbeing partially transparent, we need an algorithm that decides\nwhat to show!",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 533,
			"versionNonce": 412517354,
			"isDeleted": false,
			"id": "VOipVBBu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -759.5813179477568,
			"y": -151.14680170005067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 73.47232055664062,
			"height": 35,
			"seed": 595887466,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Idea!",
			"rawText": "Idea!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea!",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 171,
			"versionNonce": 1538422442,
			"isDeleted": false,
			"id": "UdOJ7Eab",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -876.6637001499053,
			"y": -92.14680170005067,
			"strokeColor": "#f08c00",
			"backgroundColor": "#96f2d7",
			"width": 265.6370849609375,
			"height": 35,
			"seed": 450693098,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Painter's algorithm!",
			"rawText": "Painter's algorithm!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Painter's algorithm!",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 411,
			"versionNonce": 608309610,
			"isDeleted": false,
			"id": "gZShjwOd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1000.7348366245146,
			"y": -38.14680170005067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 529.7793579101562,
			"height": 150,
			"seed": 1169718634,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hJQzA2-k0oVnnx1dJu6vS",
					"type": "arrow"
				}
			],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Sort polygons according to Z depth value\n\n2. Paint back to front\n\n3. Preform incidence if two polygons possibly intersect\nand may need to be cut",
			"rawText": "1. Sort polygons according to Z depth value\n\n2. Paint back to front\n\n3. Preform incidence if two polygons possibly intersect\nand may need to be cut",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Sort polygons according to Z depth value\n\n2. Paint back to front\n\n3. Preform incidence if two polygons possibly intersect\nand may need to be cut",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 738,
			"versionNonce": 737768694,
			"isDeleted": false,
			"id": "hJQzA2-k0oVnnx1dJu6vS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -457.3480816460444,
			"y": -28.821442848376137,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 230,
			"height": 220,
			"seed": 1775212918,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702843314087,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gZShjwOd",
				"focus": -0.42588171366770805,
				"gap": 13.607397068313958
			},
			"endBinding": {
				"elementId": "8QCSHkgs",
				"focus": 0.08429956978070711,
				"gap": 20.618033515082516
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
					128.8888888888888,
					-11.111111111111086
				],
				[
					132.22222222222217,
					207.77777777777783
				],
				[
					230,
					208.8888888888889
				]
			]
		},
		{
			"type": "text",
			"version": 295,
			"versionNonce": 78959018,
			"isDeleted": false,
			"id": "WHxp2ag9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -42.16498719753099,
			"y": 63.40077937384615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 71.85603332519531,
			"height": 45,
			"seed": 102203574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "BSP",
			"rawText": "BSP",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BSP",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 411,
			"versionNonce": 1379994730,
			"isDeleted": false,
			"id": "8QCSHkgs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -206.7300481309619,
			"y": 125.62300159606832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 414.3194885253906,
			"height": 125,
			"seed": 93731510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hJQzA2-k0oVnnx1dJu6vS",
					"type": "arrow"
				},
				{
					"id": "DyJSQbCaS7CQW3BDtgTOQ",
					"type": "arrow"
				}
			],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Each line is defined by its norm and splits\nthe scene into 2 half spaces!\nwe can form a tree that stores all the\nlines in the scene ordered based off of\nthe halfspace they're in!",
			"rawText": "Each line is defined by its norm and splits\nthe scene into 2 half spaces!\nwe can form a tree that stores all the\nlines in the scene ordered based off of\nthe halfspace they're in!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Each line is defined by its norm and splits\nthe scene into 2 half spaces!\nwe can form a tree that stores all the\nlines in the scene ordered based off of\nthe halfspace they're in!",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "arrow",
			"version": 428,
			"versionNonce": 1244358198,
			"isDeleted": false,
			"id": "DyJSQbCaS7CQW3BDtgTOQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -7.34808164604442,
			"y": 273.40077937384615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 1.1111111111110858,
			"height": 70,
			"seed": 664776502,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702843314087,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8QCSHkgs",
				"focus": 0.043868911812759516,
				"gap": 22.77777777777783
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
					1.1111111111110858,
					70
				]
			]
		},
		{
			"type": "text",
			"version": 847,
			"versionNonce": 661292906,
			"isDeleted": false,
			"id": "aWKaeebM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -344.2544380494501,
			"y": 375.40408987328726,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 676.71923828125,
			"height": 400,
			"seed": 1924247542,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "0. Order the lines in a random way lets say for example A,B,C...\n\n1. Start from the beginning line and insert into tree\n\n2. Move over to the next line\n\n3. If this line is the negative halfspace of the root, traverse right\nif this line is in the positive halfspace of the root traverse left\n\n4. If it is in both then divide the segment into 2 using its\nintersection with the span of the original line and\ntreat them as 2 diff nodes\n\n5. traverse down the tree accordingly and place in leaf\n\n6. Repeat steps 2-5",
			"rawText": "0. Order the lines in a random way lets say for example A,B,C...\n\n1. Start from the beginning line and insert into tree\n\n2. Move over to the next line\n\n3. If this line is the negative halfspace of the root, traverse right\nif this line is in the positive halfspace of the root traverse left\n\n4. If it is in both then divide the segment into 2 using its\nintersection with the span of the original line and\ntreat them as 2 diff nodes\n\n5. traverse down the tree accordingly and place in leaf\n\n6. Repeat steps 2-5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0. Order the lines in a random way lets say for example A,B,C...\n\n1. Start from the beginning line and insert into tree\n\n2. Move over to the next line\n\n3. If this line is the negative halfspace of the root, traverse right\nif this line is in the positive halfspace of the root traverse left\n\n4. If it is in both then divide the segment into 2 using its\nintersection with the span of the original line and\ntreat them as 2 diff nodes\n\n5. traverse down the tree accordingly and place in leaf\n\n6. Repeat steps 2-5",
			"lineHeight": 1.25,
			"baseline": 393
		},
		{
			"type": "text",
			"version": 304,
			"versionNonce": 138021418,
			"isDeleted": false,
			"id": "DU1lXovY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.3560492021871511,
			"x": 121.11909657557158,
			"y": 100.31135897616332,
			"strokeColor": "#e03131",
			"backgroundColor": "#96f2d7",
			"width": 373.312744140625,
			"height": 20,
			"seed": 1929589866,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Now we have an ordered tree of lines to draw!",
			"rawText": "Now we have an ordered tree of lines to draw!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now we have an ordered tree of lines to draw!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 310,
			"versionNonce": 294335722,
			"isDeleted": false,
			"id": "savHFouS0zglRwyO1aC7P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 304.96301082731907,
			"y": 138.59199734535684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 236.24645675946658,
			"height": 109.68585492403804,
			"seed": 290968886,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702843314040,
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
					29.530807094933152,
					109.68585492403804
				],
				[
					236.24645675946658,
					84.3737345569524
				]
			]
		},
		{
			"type": "text",
			"version": 249,
			"versionNonce": 350816170,
			"isDeleted": false,
			"id": "9ZGJ2MoL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.118635646106535,
			"x": 322.15448010667205,
			"y": 259.52768354365526,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 207.48843383789062,
			"height": 20,
			"seed": 1722844010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "but how do I traverse it?",
			"rawText": "but how do I traverse it?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "but how do I traverse it?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 340,
			"versionNonce": 2055111274,
			"isDeleted": false,
			"id": "ynNTk6PK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 503.8235956535109,
			"y": 117.81102152468395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 564.139404296875,
			"height": 50,
			"seed": 1682584490,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Since order of occlusion is based off of the eye location\nTraversal is based off of the eye location!",
			"rawText": "Since order of occlusion is based off of the eye location\nTraversal is based off of the eye location!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since order of occlusion is based off of the eye location\nTraversal is based off of the eye location!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 511,
			"versionNonce": 1830200618,
			"isDeleted": false,
			"id": "1CrAwxgJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 585.6884687704419,
			"y": 181.8726357145506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 420.09686279296875,
			"height": 120,
			"seed": 36404022,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702843314040,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "If your eye is in the negative halfspace of the root\nthen the furthest away from it are the ones\nin the positive halfspace\nthe same concept applies to each node and thus\nwe need to test at every level whether left or right\nis further away from us",
			"rawText": "If your eye is in the negative halfspace of the root\nthen the furthest away from it are the ones\nin the positive halfspace\nthe same concept applies to each node and thus\nwe need to test at every level whether left or right\nis further away from us",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If your eye is in the negative halfspace of the root\nthen the furthest away from it are the ones\nin the positive halfspace\nthe same concept applies to each node and thus\nwe need to test at every level whether left or right\nis further away from us",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "text",
			"version": 271,
			"versionNonce": 600036911,
			"isDeleted": false,
			"id": "sS5SDoUG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -959.9207976069397,
			"y": 278.33766126177466,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 259.47711181640625,
			"height": 35,
			"seed": 133356458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Z-Buffer Algorithm",
			"rawText": "Z-Buffer Algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z-Buffer Algorithm",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 534,
			"versionNonce": 1751595087,
			"isDeleted": false,
			"id": "R8baorYR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1088.4583629874917,
			"y": 363.6491067259017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 471.55291748046875,
			"height": 120,
			"seed": 391617322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "x1wH33yCNkzN5qh3wvn5F",
					"type": "arrow"
				},
				{
					"id": "SGS1644zJwhsSQ_T3YMNC",
					"type": "arrow"
				}
			],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Each pixel has a Z value that indicates depth\n\nAt the very start Z is the maximal potential value\nWe rasterize one object at a time and check\nwhether its Z is further or closer than the pixel's Z value\nwhich decides on whether we should proceed or not",
			"rawText": "Each pixel has a Z value that indicates depth\n\nAt the very start Z is the maximal potential value\nWe rasterize one object at a time and check\nwhether its Z is further or closer than the pixel's Z value\nwhich decides on whether we should proceed or not",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Each pixel has a Z value that indicates depth\n\nAt the very start Z is the maximal potential value\nWe rasterize one object at a time and check\nwhether its Z is further or closer than the pixel's Z value\nwhich decides on whether we should proceed or not",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 563,
			"versionNonce": 1732377185,
			"isDeleted": false,
			"id": "x1wH33yCNkzN5qh3wvn5F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1100.0723827880647,
			"y": 434.7650304164399,
			"strokeColor": "#1971c2",
			"backgroundColor": "#96f2d7",
			"width": 67.35400449654014,
			"height": 226.44880822112634,
			"seed": 902240938,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702844122394,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "R8baorYR",
				"focus": 0.6595803053345258,
				"gap": 11.614019800573033
			},
			"endBinding": {
				"elementId": "uuZaHIYo",
				"focus": -0.016033877292486506,
				"gap": 24.386794731505915
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
					-67.35400449654014,
					37.16083006705662
				],
				[
					-66.19272855694453,
					226.44880822112634
				]
			]
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1997347023,
			"isDeleted": false,
			"id": "W8sX4y4I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1238.3491164557058,
			"y": 533.4734852820591,
			"strokeColor": "#1971c2",
			"backgroundColor": "#96f2d7",
			"width": 35.00807189941406,
			"height": 20,
			"seed": 1795998762,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Pros",
			"rawText": "Pros",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Pros",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 296,
			"versionNonce": 313468655,
			"isDeleted": false,
			"id": "uuZaHIYo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1422.5565615417054,
			"y": 685.6006333690722,
			"strokeColor": "#1971c2",
			"backgroundColor": "#96f2d7",
			"width": 521.8731079101562,
			"height": 100,
			"seed": 669860150,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "x1wH33yCNkzN5qh3wvn5F",
					"type": "arrow"
				}
			],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Complexity is independent of depth complexity\n\nObjects can be inserted after computation without recomputation\n\nVery easy to realize in hardware",
			"rawText": "Complexity is independent of depth complexity\n\nObjects can be inserted after computation without recomputation\n\nVery easy to realize in hardware",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Complexity is independent of depth complexity\n\nObjects can be inserted after computation without recomputation\n\nVery easy to realize in hardware",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 506,
			"versionNonce": 192779809,
			"isDeleted": false,
			"id": "SGS1644zJwhsSQ_T3YMNC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -599.5624528223957,
			"y": 424.3135469600802,
			"strokeColor": "#e03131",
			"backgroundColor": "#96f2d7",
			"width": 92.90207516764167,
			"height": 238.06156761708155,
			"seed": 841101162,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702844122394,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "R8baorYR",
				"focus": -0.7244845834237532,
				"gap": 17.342992684627234
			},
			"endBinding": {
				"elementId": "Q763QChU",
				"focus": 0.02624597527877995,
				"gap": 27.87062255029241
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
					80.12803983209096,
					42.96720976503423
				],
				[
					92.90207516764167,
					238.06156761708155
				]
			]
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 494844239,
			"isDeleted": false,
			"id": "KGmzVw1L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -501.0988908452655,
			"y": 524.1832777652949,
			"strokeColor": "#e03131",
			"backgroundColor": "#96f2d7",
			"width": 35.32806396484375,
			"height": 20,
			"seed": 478212342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Cons",
			"rawText": "Cons",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cons",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 494,
			"versionNonce": 723040111,
			"isDeleted": false,
			"id": "Q763QChU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -794.8209611508478,
			"y": 690.2457371274542,
			"strokeColor": "#e03131",
			"backgroundColor": "#96f2d7",
			"width": 576.3211669921875,
			"height": 180,
			"seed": 2035037878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SGS1644zJwhsSQ_T3YMNC",
					"type": "arrow"
				}
			],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Only one object\n\nTransparency is impossible!\n\nTwo objects can map to the same Value\nZ fighting occurs where 2 objects share the same depth value and thus\nthe process has to pick one of them which is purely random due to\nparallelization\nDecision is based off of order!",
			"rawText": "Only one object\n\nTransparency is impossible!\n\nTwo objects can map to the same Value\nZ fighting occurs where 2 objects share the same depth value and thus\nthe process has to pick one of them which is purely random due to\nparallelization\nDecision is based off of order!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Only one object\n\nTransparency is impossible!\n\nTwo objects can map to the same Value\nZ fighting occurs where 2 objects share the same depth value and thus\nthe process has to pick one of them which is purely random due to\nparallelization\nDecision is based off of order!",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "arrow",
			"version": 234,
			"versionNonce": 211216303,
			"isDeleted": false,
			"id": "b4gaGFqLUU1251nFBXy49",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -351.16152265726987,
			"y": 855.2781839214401,
			"strokeColor": "#e03131",
			"backgroundColor": "#96f2d7",
			"width": 90.48113253731935,
			"height": 112.75341131573623,
			"seed": 49204662,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702844122336,
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
					5.568069694604219,
					89.78512382549366
				],
				[
					-84.91306284271514,
					112.75341131573623
				]
			]
		},
		{
			"type": "text",
			"version": 268,
			"versionNonce": 937171407,
			"isDeleted": false,
			"id": "MPRXAKjI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -769.6128761898467,
			"y": 963.8555429662231,
			"strokeColor": "#e03131",
			"backgroundColor": "#96f2d7",
			"width": 366.40081787109375,
			"height": 60,
			"seed": 247946166,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702844122336,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Can be avoided or minimized if we\nset our far plane as close as makes sense\nthat way our z buffer has more useable gaps",
			"rawText": "Can be avoided or minimized if we\nset our far plane as close as makes sense\nthat way our z buffer has more useable gaps",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can be avoided or minimized if we\nset our far plane as close as makes sense\nthat way our z buffer has more useable gaps",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"id": "8oIVy9pkkyRd0VA0wG7ny",
			"type": "image",
			"x": -794.8869307427848,
			"y": -149.85216234364336,
			"width": 29,
			"height": 33,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1719915751,
			"version": 61,
			"versionNonce": 916346249,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904374888,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9e5edfcf4b4f7a29c6d9f1756c9b5ffe7f3207af",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "wP-hSVdR2nIuvFilJpON0",
			"type": "freedraw",
			"x": -741.6096289644478,
			"y": -108.20261407363414,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1807542279,
			"version": 3,
			"versionNonce": 54319817,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904387547,
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
			"id": "dgyqNFzIkY8TJEyi7RY1Y",
			"type": "freedraw",
			"x": -793.6193983628807,
			"y": -117.6357585233499,
			"width": 3.56929789989249,
			"height": 5.863846549823322,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1399189863,
			"version": 94,
			"versionNonce": 33856777,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904391344,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2549498499923146
				],
				[
					0.127474924996136,
					-0.5098996999846435
				],
				[
					0.254949849992272,
					-0.7648495499769581
				],
				[
					0.382424774988408,
					-1.1472743249654371
				],
				[
					0.509899699984544,
					-1.4022241749577518
				],
				[
					0.7648495499769297,
					-1.6571740249500664
				],
				[
					0.7648495499769297,
					-1.7846489499462308
				],
				[
					0.8923244749730657,
					-1.9121238749423952
				],
				[
					1.0197993999692017,
					-1.9121238749423952
				],
				[
					1.1472743249653377,
					-2.0395987999385454
				],
				[
					1.1472743249653377,
					-1.7846489499462308
				],
				[
					1.4022241749577233,
					-1.4022241749577518
				],
				[
					1.5296990999538593,
					-1.2747492499616015
				],
				[
					1.4022241749577233,
					-1.2747492499616015
				],
				[
					1.2747492499615873,
					-1.2747492499616015
				],
				[
					1.0197993999692017,
					-1.2747492499616015
				],
				[
					0.509899699984544,
					-1.4022241749577518
				],
				[
					0.127474924996136,
					-1.6571740249500664
				],
				[
					-0.12747492499624968,
					-1.7846489499462308
				],
				[
					-0.2549498499923857,
					-1.9121238749423952
				],
				[
					-0.2549498499923857,
					-2.0395987999385454
				],
				[
					-0.2549498499923857,
					-2.16707372493471
				],
				[
					-0.2549498499923857,
					-2.29454864993086
				],
				[
					-0.2549498499923857,
					-2.549498499923189
				],
				[
					-0.2549498499923857,
					-2.9319232749116537
				],
				[
					-0.12747492499624968,
					-3.1868731249039826
				],
				[
					0,
					-3.441822974896297
				],
				[
					0.254949849992272,
					-3.696772824888612
				],
				[
					0.382424774988408,
					-3.8242477498847762
				],
				[
					0.6373746249807937,
					-3.9517226748809406
				],
				[
					0.8923244749730657,
					-3.9517226748809406
				],
				[
					1.2747492499615873,
					-3.9517226748809406
				],
				[
					1.5296990999538593,
					-3.696772824888612
				],
				[
					1.5296990999538593,
					-3.441822974896297
				],
				[
					1.5296990999538593,
					-3.1868731249039826
				],
				[
					1.5296990999538593,
					-2.6769734249193533
				],
				[
					1.4022241749577233,
					-2.4220235749270245
				],
				[
					1.1472743249653377,
					-1.7846489499462308
				],
				[
					0.8923244749730657,
					-1.2747492499616015
				],
				[
					0.509899699984544,
					-0.8923244749731083
				],
				[
					0.254949849992272,
					-0.6373746249808079
				],
				[
					0,
					-0.38242477498847904
				],
				[
					-0.2549498499923857,
					-0.2549498499923146
				],
				[
					-0.3824247749885217,
					-0.6373746249808079
				],
				[
					-0.3824247749885217,
					-1.1472743249654371
				],
				[
					-0.5098996999846577,
					-1.6571740249500664
				],
				[
					-0.5098996999846577,
					-2.16707372493471
				],
				[
					-0.5098996999846577,
					-2.549498499923189
				],
				[
					-0.3824247749885217,
					-2.9319232749116537
				],
				[
					-0.2549498499923857,
					-3.059398199907818
				],
				[
					-0.12747492499624968,
					-3.1868731249039826
				],
				[
					0.127474924996136,
					-3.1868731249039826
				],
				[
					0.6373746249807937,
					-3.059398199907818
				],
				[
					1.2747492499615873,
					-2.8044483499155035
				],
				[
					1.7846489499461313,
					-2.4220235749270245
				],
				[
					1.912123874942381,
					-2.0395987999385454
				],
				[
					1.912123874942381,
					-1.6571740249500664
				],
				[
					1.912123874942381,
					-1.0197993999692727
				],
				[
					1.5296990999538593,
					-0.38242477498847904
				],
				[
					1.2747492499615873,
					0.38242477498847904
				],
				[
					1.0197993999692017,
					1.0197993999692727
				],
				[
					0.382424774988408,
					1.529699099953902
				],
				[
					0.127474924996136,
					1.6571740249500664
				],
				[
					0,
					1.912123874942381
				],
				[
					-0.12747492499624968,
					1.7846489499462308
				],
				[
					-0.2549498499923857,
					1.4022241749577375
				],
				[
					-0.6373746249807937,
					1.0197993999692727
				],
				[
					-1.1472743249654513,
					0.38242477498847904
				],
				[
					-1.402224174957837,
					0
				],
				[
					-1.657174024950109,
					-0.5098996999846435
				],
				[
					-1.657174024950109,
					-0.7648495499769581
				],
				[
					-1.657174024950109,
					-1.1472743249654371
				],
				[
					-1.657174024950109,
					-1.4022241749577518
				],
				[
					-1.529699099953973,
					-1.6571740249500664
				],
				[
					-1.2747492499615873,
					-2.0395987999385454
				],
				[
					-0.8923244749731793,
					-2.16707372493471
				],
				[
					-0.3824247749885217,
					-2.16707372493471
				],
				[
					0.254949849992272,
					-2.16707372493471
				],
				[
					0.7648495499769297,
					-2.16707372493471
				],
				[
					1.1472743249653377,
					-1.9121238749423952
				],
				[
					1.5296990999538593,
					-1.6571740249500664
				],
				[
					1.7846489499461313,
					-1.2747492499616015
				],
				[
					1.7846489499461313,
					-1.1472743249654371
				],
				[
					1.7846489499461313,
					-0.7648495499769581
				],
				[
					1.7846489499461313,
					-0.5098996999846435
				],
				[
					1.7846489499461313,
					-0.2549498499923146
				],
				[
					1.7846489499461313,
					0
				],
				[
					1.7846489499461313,
					0.1274749249961502
				],
				[
					1.7846489499461313,
					0.38242477498847904
				],
				[
					1.7846489499461313,
					0.6373746249807937
				],
				[
					1.7846489499461313,
					0.7648495499769439
				],
				[
					1.7846489499461313,
					0.7648495499769439
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				1.7846489499461313,
				0.7648495499769439
			]
		},
		{
			"id": "GpkrJf5NbK2n9lDdwK7SW",
			"type": "freedraw",
			"x": -770.2914870885836,
			"y": -119.93030717328077,
			"width": 4.716572224857941,
			"height": 3.824247749884762,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 673987367,
			"version": 52,
			"versionNonce": 1199913609,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904392785,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.254949849992272,
					0
				],
				[
					0.382424774988408,
					0.1274749249961502
				],
				[
					0.7648495499769297,
					0.38242477498846483
				],
				[
					0.8923244749730657,
					0.38242477498846483
				],
				[
					1.1472743249653377,
					0.5098996999846293
				],
				[
					1.5296990999538593,
					0.7648495499769581
				],
				[
					1.6571740249499953,
					0.8923244749731083
				],
				[
					1.7846489499461313,
					1.2747492499615873
				],
				[
					1.912123874942381,
					1.7846489499462166
				],
				[
					1.912123874942381,
					2.1670737249346956
				],
				[
					1.912123874942381,
					2.4220235749270103
				],
				[
					1.912123874942381,
					2.676973424919339
				],
				[
					1.912123874942381,
					2.9319232749116537
				],
				[
					1.7846489499461313,
					3.059398199907804
				],
				[
					1.6571740249499953,
					3.059398199907804
				],
				[
					1.4022241749577233,
					3.059398199907804
				],
				[
					1.1472743249653377,
					3.059398199907804
				],
				[
					0.7648495499769297,
					2.676973424919339
				],
				[
					0.254949849992272,
					2.0395987999385454
				],
				[
					-0.3824247749885217,
					1.4022241749577518
				],
				[
					-0.6373746249807937,
					1.147274324965423
				],
				[
					-0.7648495499770434,
					0.7648495499769581
				],
				[
					-0.7648495499770434,
					0.6373746249807937
				],
				[
					-0.5098996999846577,
					0.6373746249807937
				],
				[
					0.7648495499769297,
					0.8923244749731083
				],
				[
					1.7846489499461313,
					1.2747492499615873
				],
				[
					2.6769734249193107,
					1.6571740249500522
				],
				[
					3.0593981999078323,
					1.912123874942381
				],
				[
					3.4418229748962403,
					2.1670737249346956
				],
				[
					3.824247749884762,
					2.676973424919339
				],
				[
					3.951722674880898,
					2.9319232749116537
				],
				[
					3.951722674880898,
					3.059398199907804
				],
				[
					3.951722674880898,
					3.3143480499001328
				],
				[
					3.696772824888626,
					3.5692978998924474
				],
				[
					3.4418229748962403,
					3.5692978998924474
				],
				[
					3.1868731249039683,
					3.6967728248885976
				],
				[
					3.0593981999078323,
					3.824247749884762
				],
				[
					2.9319232749115827,
					3.824247749884762
				],
				[
					2.8044483499154467,
					3.824247749884762
				],
				[
					2.8044483499154467,
					3.5692978998924474
				],
				[
					2.6769734249193107,
					3.3143480499001328
				],
				[
					2.4220235749270387,
					2.9319232749116537
				],
				[
					2.4220235749270387,
					2.676973424919339
				],
				[
					2.4220235749270387,
					2.4220235749270103
				],
				[
					2.4220235749270387,
					2.29454864993086
				],
				[
					2.4220235749270387,
					2.1670737249346956
				],
				[
					2.4220235749270387,
					2.0395987999385454
				],
				[
					2.5494984999231747,
					2.0395987999385454
				],
				[
					2.6769734249193107,
					2.0395987999385454
				],
				[
					2.6769734249193107,
					2.0395987999385454
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.6769734249193107,
				2.0395987999385454
			]
		},
		{
			"id": "QWvam4Aw1lB9aS92DET72",
			"type": "freedraw",
			"x": -767.7419885886604,
			"y": -148.10226559743194,
			"width": 3.824247749884762,
			"height": 4.206672524873227,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1904928167,
			"version": 164,
			"versionNonce": 990263817,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904397332,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.12747492499616442
				],
				[
					0,
					0.25494984999232884
				],
				[
					0.127474924996136,
					0.25494984999232884
				],
				[
					0.5098996999846577,
					-0.12747492499616442
				],
				[
					0.8923244749730657,
					-0.38242477498846483
				],
				[
					1.2747492499615873,
					-0.6373746249807937
				],
				[
					1.5296990999538593,
					-0.8923244749731225
				],
				[
					1.5296990999538593,
					-1.0197993999692585
				],
				[
					1.5296990999538593,
					-0.8923244749731225
				],
				[
					1.6571740249499953,
					-0.8923244749731225
				],
				[
					1.6571740249499953,
					-0.5098996999846293
				],
				[
					1.6571740249499953,
					-0.12747492499616442
				],
				[
					1.6571740249499953,
					0.25494984999232884
				],
				[
					1.5296990999538593,
					0.8923244749731225
				],
				[
					1.4022241749577233,
					1.5296990999539162
				],
				[
					1.2747492499615873,
					2.16707372493471
				],
				[
					1.1472743249654513,
					2.5494984999231747
				],
				[
					1.1472743249654513,
					2.676973424919339
				],
				[
					0.8923244749730657,
					2.676973424919339
				],
				[
					0.6373746249807937,
					2.676973424919339
				],
				[
					0.5098996999846577,
					2.5494984999231747
				],
				[
					0.5098996999846577,
					2.4220235749270387
				],
				[
					0.5098996999846577,
					2.0395987999385454
				],
				[
					0.5098996999846577,
					1.6571740249500806
				],
				[
					0.5098996999846577,
					1.2747492499615873
				],
				[
					0.5098996999846577,
					0.8923244749731225
				],
				[
					0.5098996999846577,
					0.5098996999846293
				],
				[
					0.5098996999846577,
					0.25494984999232884
				],
				[
					0.5098996999846577,
					0.12747492499616442
				],
				[
					0.6373746249807937,
					0
				],
				[
					0.7648495499769297,
					0
				],
				[
					1.0197993999692017,
					0
				],
				[
					1.4022241749577233,
					0.25494984999232884
				],
				[
					1.784648949946245,
					0.38242477498849325
				],
				[
					1.784648949946245,
					0.5098996999846293
				],
				[
					1.912123874942381,
					0.7648495499769581
				],
				[
					1.912123874942381,
					1.019799399969287
				],
				[
					1.912123874942381,
					1.1472743249654513
				],
				[
					1.6571740249499953,
					1.5296990999539162
				],
				[
					1.4022241749577233,
					1.912123874942381
				],
				[
					0.7648495499769297,
					1.912123874942381
				],
				[
					0.382424774988408,
					1.912123874942381
				],
				[
					0,
					2.0395987999385454
				],
				[
					-0.127474924996136,
					2.0395987999385454
				],
				[
					-0.3824247749885217,
					2.0395987999385454
				],
				[
					-0.5098996999846577,
					2.0395987999385454
				],
				[
					-0.6373746249807937,
					1.784648949946245
				],
				[
					-0.6373746249807937,
					1.5296990999539162
				],
				[
					-0.7648495499770434,
					1.1472743249654513
				],
				[
					-0.7648495499770434,
					0.8923244749731225
				],
				[
					-0.7648495499770434,
					0.7648495499769581
				],
				[
					-0.7648495499770434,
					0.6373746249807937
				],
				[
					-0.7648495499770434,
					0.38242477498849325
				],
				[
					-0.5098996999846577,
					0.38242477498849325
				],
				[
					-0.127474924996136,
					0.12747492499616442
				],
				[
					0.254949849992272,
					0
				],
				[
					0.5098996999846577,
					-0.2549498499923004
				],
				[
					0.8923244749730657,
					-0.38242477498846483
				],
				[
					1.1472743249654513,
					-0.38242477498846483
				],
				[
					1.2747492499615873,
					-0.38242477498846483
				],
				[
					1.4022241749577233,
					-0.38242477498846483
				],
				[
					1.6571740249499953,
					-0.12747492499616442
				],
				[
					1.784648949946245,
					0.12747492499616442
				],
				[
					1.784648949946245,
					0.38242477498849325
				],
				[
					1.912123874942381,
					0.6373746249807937
				],
				[
					1.912123874942381,
					0.8923244749731225
				],
				[
					1.912123874942381,
					1.4022241749577518
				],
				[
					1.6571740249499953,
					2.0395987999385454
				],
				[
					1.1472743249654513,
					2.2945486499308743
				],
				[
					0.6373746249807937,
					2.2945486499308743
				],
				[
					0.127474924996136,
					2.2945486499308743
				],
				[
					-0.127474924996136,
					2.2945486499308743
				],
				[
					-0.2549498499923857,
					2.2945486499308743
				],
				[
					-0.2549498499923857,
					2.0395987999385454
				],
				[
					-0.2549498499923857,
					1.784648949946245
				],
				[
					-0.127474924996136,
					1.6571740249500806
				],
				[
					0.127474924996136,
					1.4022241749577518
				],
				[
					0.254949849992272,
					1.2747492499615873
				],
				[
					0.5098996999846577,
					1.1472743249654513
				],
				[
					0.7648495499769297,
					1.1472743249654513
				],
				[
					1.2747492499615873,
					1.019799399969287
				],
				[
					1.5296990999538593,
					1.019799399969287
				],
				[
					2.039598799938517,
					1.019799399969287
				],
				[
					2.294548649930789,
					1.019799399969287
				],
				[
					2.4220235749270387,
					1.1472743249654513
				],
				[
					2.6769734249193107,
					1.2747492499615873
				],
				[
					2.6769734249193107,
					1.4022241749577518
				],
				[
					2.5494984999231747,
					1.5296990999539162
				],
				[
					2.294548649930789,
					1.5296990999539162
				],
				[
					1.784648949946245,
					1.5296990999539162
				],
				[
					1.2747492499615873,
					1.6571740249500806
				],
				[
					1.0197993999692017,
					1.784648949946245
				],
				[
					0.6373746249807937,
					1.784648949946245
				],
				[
					0.5098996999846577,
					1.784648949946245
				],
				[
					0.254949849992272,
					1.784648949946245
				],
				[
					0.127474924996136,
					1.784648949946245
				],
				[
					0.254949849992272,
					2.0395987999385454
				],
				[
					0.382424774988408,
					2.0395987999385454
				],
				[
					0.5098996999846577,
					2.16707372493471
				],
				[
					0.6373746249807937,
					2.16707372493471
				],
				[
					0.7648495499769297,
					2.2945486499308743
				],
				[
					0.7648495499769297,
					2.4220235749270387
				],
				[
					0.7648495499769297,
					2.5494984999231747
				],
				[
					0.8923244749730657,
					2.8044483499155035
				],
				[
					0.8923244749730657,
					2.931923274911668
				],
				[
					0.8923244749730657,
					3.0593981999078323
				],
				[
					0.8923244749730657,
					3.1868731249039683
				],
				[
					0.6373746249807937,
					3.1868731249039683
				],
				[
					0.5098996999846577,
					3.1868731249039683
				],
				[
					0.254949849992272,
					3.0593981999078323
				],
				[
					0.127474924996136,
					2.931923274911668
				],
				[
					0.127474924996136,
					2.5494984999231747
				],
				[
					0.127474924996136,
					2.4220235749270387
				],
				[
					0.127474924996136,
					2.2945486499308743
				],
				[
					0.127474924996136,
					2.0395987999385454
				],
				[
					0.127474924996136,
					1.912123874942381
				],
				[
					0.254949849992272,
					1.6571740249500806
				],
				[
					0.382424774988408,
					1.5296990999539162
				],
				[
					0.382424774988408,
					1.2747492499615873
				],
				[
					0.5098996999846577,
					1.1472743249654513
				],
				[
					0.5098996999846577,
					0.8923244749731225
				],
				[
					0.6373746249807937,
					0.7648495499769581
				],
				[
					0.6373746249807937,
					0.6373746249807937
				],
				[
					0.6373746249807937,
					0.38242477498849325
				],
				[
					0.6373746249807937,
					0.12747492499616442
				],
				[
					0.6373746249807937,
					0
				],
				[
					0.6373746249807937,
					-0.2549498499923004
				],
				[
					0.6373746249807937,
					-0.5098996999846293
				],
				[
					0.6373746249807937,
					-0.6373746249807937
				],
				[
					0.6373746249807937,
					-0.7648495499769581
				],
				[
					0.8923244749730657,
					-0.7648495499769581
				],
				[
					1.0197993999692017,
					-0.7648495499769581
				],
				[
					1.1472743249654513,
					-0.8923244749731225
				],
				[
					1.2747492499615873,
					-0.7648495499769581
				],
				[
					1.2747492499615873,
					-0.6373746249807937
				],
				[
					1.1472743249654513,
					-0.12747492499616442
				],
				[
					1.0197993999692017,
					0.25494984999232884
				],
				[
					0.8923244749730657,
					0.8923244749731225
				],
				[
					0.7648495499769297,
					1.2747492499615873
				],
				[
					0.7648495499769297,
					1.784648949946245
				],
				[
					0.7648495499769297,
					2.0395987999385454
				],
				[
					0.7648495499769297,
					2.2945486499308743
				],
				[
					0.7648495499769297,
					2.4220235749270387
				],
				[
					0.6373746249807937,
					2.676973424919339
				],
				[
					0.5098996999846577,
					2.676973424919339
				],
				[
					0.382424774988408,
					2.676973424919339
				],
				[
					0.382424774988408,
					2.8044483499155035
				],
				[
					0.254949849992272,
					2.8044483499155035
				],
				[
					0,
					2.676973424919339
				],
				[
					-0.2549498499923857,
					2.5494984999231747
				],
				[
					-0.3824247749885217,
					2.5494984999231747
				],
				[
					-0.5098996999846577,
					2.5494984999231747
				],
				[
					-0.5098996999846577,
					2.4220235749270387
				],
				[
					-0.6373746249807937,
					2.4220235749270387
				],
				[
					-0.7648495499770434,
					2.4220235749270387
				],
				[
					-0.7648495499770434,
					2.2945486499308743
				],
				[
					-0.8923244749731793,
					2.2945486499308743
				],
				[
					-0.8923244749731793,
					2.16707372493471
				],
				[
					-1.1472743249654513,
					2.0395987999385454
				],
				[
					-1.1472743249654513,
					1.912123874942381
				],
				[
					-1.1472743249654513,
					1.784648949946245
				],
				[
					-1.1472743249654513,
					1.784648949946245
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-1.1472743249654513,
				1.784648949946245
			]
		},
		{
			"id": "oY8E8jCTfCqQeVVLhDXzA",
			"type": "freedraw",
			"x": -766.7221891886912,
			"y": -115.59615972341136,
			"width": 2.039598799938517,
			"height": 2.8044483499155035,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1016106535,
			"version": 27,
			"versionNonce": 1716567977,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904398331,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.254949849992272,
					0.1274749249961502
				],
				[
					-0.382424774988408,
					0.1274749249961502
				],
				[
					-0.509899699984544,
					0.2549498499923146
				],
				[
					-0.6373746249807937,
					0.2549498499923146
				],
				[
					-0.7648495499769297,
					0
				],
				[
					-0.8923244749730657,
					-0.2549498499923146
				],
				[
					-1.0197993999692017,
					-0.7648495499769581
				],
				[
					-0.8923244749730657,
					-1.1472743249654371
				],
				[
					-0.6373746249807937,
					-1.4022241749577518
				],
				[
					-0.127474924996136,
					-1.6571740249500664
				],
				[
					0.2549498499923857,
					-1.6571740249500664
				],
				[
					0.5098996999846577,
					-1.6571740249500664
				],
				[
					0.6373746249807937,
					-1.529699099953902
				],
				[
					0.8923244749731793,
					-1.1472743249654371
				],
				[
					1.0197993999693153,
					-0.38242477498847904
				],
				[
					1.0197993999693153,
					0.1274749249961502
				],
				[
					1.0197993999693153,
					0.7648495499769439
				],
				[
					0.7648495499770434,
					1.0197993999692727
				],
				[
					0.7648495499770434,
					1.1472743249654371
				],
				[
					0.6373746249807937,
					1.1472743249654371
				],
				[
					0.6373746249807937,
					1.0197993999692727
				],
				[
					0.6373746249807937,
					0.8923244749731083
				],
				[
					0.6373746249807937,
					0.7648495499769439
				],
				[
					0,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.6373746249807937,
				0.7648495499769439
			]
		},
		{
			"id": "WNtmkBQTNqHpydmFXX64A",
			"type": "freedraw",
			"x": -793.8743482128731,
			"y": -147.20994112245882,
			"width": 2.6769734249193107,
			"height": 4.206672524873255,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "#96f2d7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 642721415,
			"version": 91,
			"versionNonce": 40763721,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702904400952,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.254949849992272,
					-0.38242477498849325
				],
				[
					-0.5098996999846577,
					-0.6373746249807937
				],
				[
					-0.5098996999846577,
					-0.8923244749731225
				],
				[
					-0.6373746249807937,
					-1.147274324965423
				],
				[
					-0.6373746249807937,
					-1.5296990999539162
				],
				[
					-0.6373746249807937,
					-1.784648949946245
				],
				[
					-0.6373746249807937,
					-2.0395987999385454
				],
				[
					-0.5098996999846577,
					-2.4220235749270387
				],
				[
					-0.254949849992272,
					-2.676973424919339
				],
				[
					0.127474924996136,
					-2.8044483499155035
				],
				[
					0.5098996999846577,
					-2.8044483499155035
				],
				[
					0.7648495499769297,
					-2.5494984999231747
				],
				[
					0.8923244749731793,
					-2.16707372493471
				],
				[
					1.0197993999693153,
					-1.912123874942381
				],
				[
					1.0197993999693153,
					-1.6571740249500806
				],
				[
					1.0197993999693153,
					-1.2747492499615873
				],
				[
					1.0197993999693153,
					-0.8923244749731225
				],
				[
					0.8923244749731793,
					-0.6373746249807937
				],
				[
					0.3824247749885217,
					-0.5098996999846293
				],
				[
					0.2549498499923857,
					-0.25494984999232884
				],
				[
					0,
					-0.12747492499616442
				],
				[
					-0.127474924996136,
					-0.12747492499616442
				],
				[
					-0.127474924996136,
					-0.38242477498849325
				],
				[
					-0.127474924996136,
					-0.7648495499769581
				],
				[
					-0.127474924996136,
					-1.019799399969287
				],
				[
					-0.127474924996136,
					-1.2747492499615873
				],
				[
					0,
					-1.4022241749577518
				],
				[
					0.3824247749885217,
					-1.5296990999539162
				],
				[
					0.5098996999846577,
					-1.5296990999539162
				],
				[
					0.6373746249807937,
					-1.4022241749577518
				],
				[
					0.8923244749731793,
					-1.147274324965423
				],
				[
					1.1472743249654513,
					-0.7648495499769581
				],
				[
					1.4022241749577233,
					-0.38242477498849325
				],
				[
					1.4022241749577233,
					-0.25494984999232884
				],
				[
					1.529699099953973,
					-0.12747492499616442
				],
				[
					1.529699099953973,
					0
				],
				[
					1.529699099953973,
					0.12747492499616442
				],
				[
					1.529699099953973,
					0.25494984999232884
				],
				[
					1.2747492499615873,
					0.5098996999846293
				],
				[
					1.0197993999693153,
					0.7648495499769581
				],
				[
					0.7648495499769297,
					1.0197993999692585
				],
				[
					0.5098996999846577,
					1.2747492499615873
				],
				[
					0.2549498499923857,
					1.4022241749577518
				],
				[
					0.127474924996136,
					1.2747492499615873
				],
				[
					0,
					1.147274324965423
				],
				[
					-0.127474924996136,
					1.0197993999692585
				],
				[
					-0.127474924996136,
					0.8923244749731225
				],
				[
					-0.127474924996136,
					0.6373746249807937
				],
				[
					-0.127474924996136,
					0.38242477498846483
				],
				[
					-0.127474924996136,
					0.25494984999232884
				],
				[
					0,
					0
				],
				[
					0.2549498499923857,
					-0.38242477498849325
				],
				[
					0.3824247749885217,
					-0.5098996999846293
				],
				[
					0.5098996999846577,
					-0.7648495499769581
				],
				[
					0.6373746249807937,
					-0.7648495499769581
				],
				[
					1.0197993999693153,
					-1.019799399969287
				],
				[
					1.1472743249654513,
					-1.147274324965423
				],
				[
					1.529699099953973,
					-1.147274324965423
				],
				[
					1.657174024950109,
					-1.147274324965423
				],
				[
					1.784648949946245,
					-1.147274324965423
				],
				[
					1.912123874942381,
					-1.147274324965423
				],
				[
					2.039598799938517,
					-1.147274324965423
				],
				[
					2.039598799938517,
					-1.019799399969287
				],
				[
					2.039598799938517,
					-0.7648495499769581
				],
				[
					2.039598799938517,
					-0.5098996999846293
				],
				[
					2.039598799938517,
					-0.12747492499616442
				],
				[
					1.912123874942381,
					0
				],
				[
					1.529699099953973,
					0.25494984999232884
				],
				[
					1.2747492499615873,
					0.38242477498846483
				],
				[
					1.0197993999693153,
					0.5098996999846293
				],
				[
					0.6373746249807937,
					0.6373746249807937
				],
				[
					0.3824247749885217,
					0.7648495499769581
				],
				[
					0.127474924996136,
					0.8923244749731225
				],
				[
					0,
					0.8923244749731225
				],
				[
					-0.127474924996136,
					0.8923244749731225
				],
				[
					-0.254949849992272,
					0.6373746249807937
				],
				[
					-0.382424774988408,
					0.38242477498846483
				],
				[
					-0.382424774988408,
					0.25494984999232884
				],
				[
					-0.382424774988408,
					0
				],
				[
					-0.382424774988408,
					-0.25494984999232884
				],
				[
					-0.254949849992272,
					-0.5098996999846293
				],
				[
					0,
					-0.7648495499769581
				],
				[
					0.2549498499923857,
					-0.8923244749731225
				],
				[
					0.5098996999846577,
					-1.019799399969287
				],
				[
					0.7648495499769297,
					-1.147274324965423
				],
				[
					0.8923244749731793,
					-1.2747492499615873
				],
				[
					1.0197993999693153,
					-1.2747492499615873
				],
				[
					1.0197993999693153,
					-1.4022241749577518
				],
				[
					1.0197993999693153,
					-1.4022241749577518
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				1.0197993999693153,
				-1.4022241749577518
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#ffffff",
		"currentItemBackgroundColor": "#96f2d7",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 0.5,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 923.5739778687744,
		"scrollY": 207.85138154141987,
		"zoom": {
			"value": 4.657434782220291
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