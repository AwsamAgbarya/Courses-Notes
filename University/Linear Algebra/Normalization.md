---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Norms ^5kL9KcIT

Norms are just mathematical ways to quantify size
of different objects in linear algebra (vectors, matrices etc...)

it is often important for us to know which one of
the two objects is bigger in size, and thus came
a few different ways to quantify magnitude!

Note: this norm idea can also be applied to real numbers
with absolute value, the idea is simple but technically it is
a way to quantify the "length" of a number. ^K3B0p7vy

Level 1
L1 Norm ^k6WDB4gh

L1 Norm is a norm of a vector
that simply adds up the "length"
of each of its components
i.e ^vJ6poqsk

Level 2.1
L2/Euclidean Norm ^27lJgBnS

    L2 Norm is a norm that
quantifies the distance between
both ends of a vector using
euclidean distance
i.e ^s77Vp7z2

Level 3
Frobenius Norm ^oFWnfUGe

How do we apply this concept onto
matrices? well the simplest way is
to think of matrices as just
sequentially stored vectors and
then applying the L2 norm on them ^KNbb8fV8

Level 4
L2 of transformation ^P4CHKd4f

We can think of matrices as transformations
according to linear algebra, which means
we should be able to quantify how big of a
transformation a certain matrix is
i.e given any unit vector whats the maximum
l2 norm of that vector after applying M ^rxizHu1y

Level 2.2
infinity norm ^ete9zZXf

Another way to quantify magnitude
in certain cases its to meassure
the distance of a vector only in a
certain axis, i.e take the maximum
component of that vector ^L9GhLhHT

Level 2.3
P norm ^YRb1IwGJ

To generalize what we have just
said about vector norms, the P 
norm is the sum of norms of all
components of a vector to the
power p under pth root ^DFYL7UWW

Level 5
Lpq Norm ^afzcrTpw

the Lpq norm is as general as you can get
in terms of norms for matrices, its as if
we take each row of the matrix and treat it
as a vector, apply p norm on it, then
take each vector norm and apply q norm
on it ^3lsjXSlx


# Embedded files
e24ed798e0c63531148d3488e85837bf61751598: $$\|v\|_1 = \sum_i | v_i |

$$
7657be6a73ee9c1e6cc7d844d3491806206e606e: $$\|v\|_2 =\sqrt{ \sum_i | v_i |^2}

$$
fde70b9065f0ee15f67b76efba89d7fef867acbd: $$\|M\|_f =\sqrt{ \sum_i \sum_j | v_{ij} |^2}

$$
4b35de1a7a66ff73c004f0533716735dd2f64295: $$\|M\|_{p/q} = \sqrt[q]{\sum_j \sqrt[p]{\sum_i |Mij|^p}^q}

$$
169a31ef89a7d494bd180a5627e0b35f4f3829cc: $$\|M\|_2 = max_{\|v\|=1}\|Mv\|_2 

$$
c8b1d2976ecdb0113de1c40f700a0043a6eedae7: $$\|v\|_\inf = max | v_i |

$$
cf0a393c1add947b387d02c468a9b685457d5347: $$\|v\|_p = \sqrt[p]{\sum_i |v_i|^p }

$$

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.18",
	"elements": [
		{
			"id": "5kL9KcIT",
			"type": "text",
			"x": -61.75,
			"y": -405.2578125,
			"width": 78.5123291015625,
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
			"seed": 2048169756,
			"version": 52,
			"versionNonce": 243212580,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636335,
			"link": null,
			"locked": false,
			"text": "Norms",
			"rawText": "Norms",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Norms",
			"lineHeight": 1.25
		},
		{
			"id": "K3B0p7vy",
			"type": "text",
			"x": -328.75,
			"y": -351.2578125,
			"width": 619.619384765625,
			"height": 250,
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
			"seed": 928077852,
			"version": 657,
			"versionNonce": 1968829212,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636335,
			"link": null,
			"locked": false,
			"text": "Norms are just mathematical ways to quantify size\nof different objects in linear algebra (vectors, matrices etc...)\n\nit is often important for us to know which one of\nthe two objects is bigger in size, and thus came\na few different ways to quantify magnitude!\n\nNote: this norm idea can also be applied to real numbers\nwith absolute value, the idea is simple but technically it is\na way to quantify the \"length\" of a number.",
			"rawText": "Norms are just mathematical ways to quantify size\nof different objects in linear algebra (vectors, matrices etc...)\n\nit is often important for us to know which one of\nthe two objects is bigger in size, and thus came\na few different ways to quantify magnitude!\n\nNote: this norm idea can also be applied to real numbers\nwith absolute value, the idea is simple but technically it is\na way to quantify the \"length\" of a number.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 243,
			"containerId": null,
			"originalText": "Norms are just mathematical ways to quantify size\nof different objects in linear algebra (vectors, matrices etc...)\n\nit is often important for us to know which one of\nthe two objects is bigger in size, and thus came\na few different ways to quantify magnitude!\n\nNote: this norm idea can also be applied to real numbers\nwith absolute value, the idea is simple but technically it is\na way to quantify the \"length\" of a number.",
			"lineHeight": 1.25
		},
		{
			"id": "CYNfpZA-_vRhxt5e7kziC",
			"type": "line",
			"x": 123.25,
			"y": -359.2578125,
			"width": 294,
			"height": 12,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1784193052,
			"version": 83,
			"versionNonce": 466050212,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-294,
					-12
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "waGgk4uL2COO7TAKTSZIH",
			"type": "line",
			"x": -167.75,
			"y": -361.2578125,
			"width": 291,
			"height": 10,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 499952548,
			"version": 77,
			"versionNonce": 1818570652,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					291,
					-10
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "k6WDB4gh",
			"type": "text",
			"x": -603.8399963378906,
			"y": -50.2578125,
			"width": 101.66842651367188,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 206489124,
			"version": 174,
			"versionNonce": 1534863396,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"text": "Level 1\nL1 Norm",
			"rawText": "Level 1\nL1 Norm",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Level 1\nL1 Norm",
			"lineHeight": 1.25
		},
		{
			"id": "vJ6poqsk",
			"type": "text",
			"x": -713.9398193359375,
			"y": 45.7421875,
			"width": 318.379638671875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 388697244,
			"version": 238,
			"versionNonce": 1205132316,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"text": "L1 Norm is a norm of a vector\nthat simply adds up the \"length\"\nof each of its components\ni.e",
			"rawText": "L1 Norm is a norm of a vector\nthat simply adds up the \"length\"\nof each of its components\ni.e",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "L1 Norm is a norm of a vector\nthat simply adds up the \"length\"\nof each of its components\ni.e",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 112,
			"versionNonce": 1904968612,
			"isDeleted": false,
			"id": "cELtq425",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -641.4808116300735,
			"y": 162.66529597420532,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 189.71162326014704,
			"height": 65.66940805158936,
			"seed": 39658,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e24ed798e0c63531148d3488e85837bf61751598",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HmQB9AmROdKhk87Py32VU",
			"type": "rectangle",
			"x": -730.75,
			"y": -59.2578125,
			"width": 349,
			"height": 318,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 494173092,
			"version": 144,
			"versionNonce": 1637546140,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "_YRQVt7pzEFvm1gLJ63IG",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false
		},
		{
			"id": "_YRQVt7pzEFvm1gLJ63IG",
			"type": "arrow",
			"x": -378.75,
			"y": 85.2971824980845,
			"width": 183.67001342773432,
			"height": 2.194910011452464,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1658885020,
			"version": 191,
			"versionNonce": 1411608356,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					183.67001342773432,
					2.194910011452464
				]
			],
			"lastCommittedPoint": [
				184,
				5
			],
			"startBinding": {
				"elementId": "HmQB9AmROdKhk87Py32VU",
				"focus": -0.10284103465043666,
				"gap": 3
			},
			"endBinding": {
				"elementId": "L0jgfhVsMFc3FzieE4Eog",
				"focus": 0.13117861637220346,
				"gap": 2.829986572265682
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 338,
			"versionNonce": 90801436,
			"isDeleted": false,
			"id": "27lJgBnS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -141.17831420898438,
			"y": -39.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 253.34506225585938,
			"height": 70,
			"seed": 981668772,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Level 2.1\nL2/Euclidean Norm",
			"rawText": "Level 2.1\nL2/Euclidean Norm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Level 2.1\nL2/Euclidean Norm",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 551,
			"versionNonce": 61991588,
			"isDeleted": false,
			"id": "s77Vp7z2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -174.26980590820312,
			"y": 56.7421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 316.03961181640625,
			"height": 125,
			"seed": 933822244,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_YRQVt7pzEFvm1gLJ63IG",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "    L2 Norm is a norm that\nquantifies the distance between\nboth ends of a vector using\neuclidean distance\ni.e",
			"rawText": "    L2 Norm is a norm that\nquantifies the distance between\nboth ends of a vector using\neuclidean distance\ni.e",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    L2 Norm is a norm that\nquantifies the distance between\nboth ends of a vector using\neuclidean distance\ni.e",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 276,
			"versionNonce": 951222684,
			"isDeleted": false,
			"id": "45jjtQs9csJgomJkXtmp3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -100.9808116300735,
			"y": 190.66529597420532,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 189.71162326014704,
			"height": 65.66940805158936,
			"seed": 359076,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7657be6a73ee9c1e6cc7d844d3491806206e606e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 283,
			"versionNonce": 1122301476,
			"isDeleted": false,
			"id": "L0jgfhVsMFc3FzieE4Eog",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -192.25,
			"y": -48.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 349,
			"height": 318,
			"seed": 239502884,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "_YRQVt7pzEFvm1gLJ63IG",
					"type": "arrow"
				},
				{
					"id": "1lbD3HBa1OCdSQC_Ai_Hv",
					"type": "arrow"
				},
				{
					"id": "Ed86kAy_jtKM8KF7y8tPZ",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false
		},
		{
			"id": "1lbD3HBa1OCdSQC_Ai_Hv",
			"type": "arrow",
			"x": 161.5,
			"y": 90.17227457579007,
			"width": 189.19989776611328,
			"height": 0.8566285906684925,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 75589916,
			"version": 189,
			"versionNonce": 44559900,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					189.19989776611328,
					0.8566285906684925
				]
			],
			"lastCommittedPoint": [
				166.25,
				2.5
			],
			"startBinding": {
				"elementId": "L0jgfhVsMFc3FzieE4Eog",
				"focus": -0.1330609251754162,
				"gap": 4.75
			},
			"endBinding": {
				"elementId": "0zhLyfQ8AQjwJfD2JDJGi",
				"focus": 0.14601928361111757,
				"gap": 20.05010223388672
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 472,
			"versionNonce": 1319801252,
			"isDeleted": false,
			"id": "oFWnfUGe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 448.09979248046875,
			"y": -34.7578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 200.78884887695312,
			"height": 70,
			"seed": 1697061660,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Level 3\nFrobenius Norm",
			"rawText": "Level 3\nFrobenius Norm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Level 3\nFrobenius Norm",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 879,
			"versionNonce": 876333724,
			"isDeleted": false,
			"id": "KNbb8fV8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 378.31019592285156,
			"y": 61.2421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 339.3796081542969,
			"height": 125,
			"seed": 944592796,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "1lbD3HBa1OCdSQC_Ai_Hv",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we apply this concept onto\nmatrices? well the simplest way is\nto think of matrices as just\nsequentially stored vectors and\nthen applying the L2 norm on them",
			"rawText": "How do we apply this concept onto\nmatrices? well the simplest way is\nto think of matrices as just\nsequentially stored vectors and\nthen applying the L2 norm on them",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we apply this concept onto\nmatrices? well the simplest way is\nto think of matrices as just\nsequentially stored vectors and\nthen applying the L2 norm on them",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 396,
			"versionNonce": 372292900,
			"isDeleted": false,
			"id": "_O6I1KD7Vpgdf-7ppOrkh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 458.26712914213215,
			"y": 196.4146663658392,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 197.21574171573567,
			"height": 63.17066726832159,
			"seed": 880280604,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fde70b9065f0ee15f67b76efba89d7fef867acbd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 404,
			"versionNonce": 807409436,
			"isDeleted": false,
			"id": "0zhLyfQ8AQjwJfD2JDJGi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 370.75,
			"y": -43.7578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 349,
			"height": 318,
			"seed": 530129052,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "1lbD3HBa1OCdSQC_Ai_Hv",
					"type": "arrow"
				},
				{
					"id": "bl0Wac1WbAc2oyolMWHNs",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false
		},
		{
			"id": "bl0Wac1WbAc2oyolMWHNs",
			"type": "arrow",
			"x": 546.428388106643,
			"y": 283.4969810994028,
			"width": 1.0174694878221544,
			"height": 171.8449435664209,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1604035364,
			"version": 347,
			"versionNonce": 1927641252,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.0174694878221544,
					171.8449435664209
				]
			],
			"lastCommittedPoint": [
				2.7062195837231684,
				188.08226106875998
			],
			"startBinding": {
				"elementId": "0zhLyfQ8AQjwJfD2JDJGi",
				"focus": -0.0008116534114139541,
				"gap": 9.254793599402717
			},
			"endBinding": {
				"elementId": "P4CHKd4f",
				"focus": 0.004947163304142687,
				"gap": 13.72628481525146
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 729,
			"versionNonce": 851891100,
			"isDeleted": false,
			"id": "P4CHKd4f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 398.6266905929016,
			"y": 469.0682094810751,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 296.7452392578125,
			"height": 70,
			"seed": 731174820,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bl0Wac1WbAc2oyolMWHNs",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Level 4\nL2 of transformation",
			"rawText": "Level 4\nL2 of transformation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Level 4\nL2 of transformation",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "rectangle",
			"version": 700,
			"versionNonce": 442630172,
			"isDeleted": false,
			"id": "czfJwOOl2V0L_rluPtiO5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 316.3367423199046,
			"y": 455.33982357613274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 462.24131398829036,
			"height": 318,
			"seed": 1845414436,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "OXQmepSEAC1Q4hxcvhOjV",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false
		},
		{
			"id": "rxizHu1y",
			"type": "text",
			"x": 318.28197394714164,
			"y": 543.3090578699725,
			"width": 446.13946533203125,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 745186980,
			"version": 311,
			"versionNonce": 886218660,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"text": "We can think of matrices as transformations\naccording to linear algebra, which means\nwe should be able to quantify how big of a\ntransformation a certain matrix is\ni.e given any unit vector whats the maximum\nl2 norm of that vector after applying M",
			"rawText": "We can think of matrices as transformations\naccording to linear algebra, which means\nwe should be able to quantify how big of a\ntransformation a certain matrix is\ni.e given any unit vector whats the maximum\nl2 norm of that vector after applying M",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "We can think of matrices as transformations\naccording to linear algebra, which means\nwe should be able to quantify how big of a\ntransformation a certain matrix is\ni.e given any unit vector whats the maximum\nl2 norm of that vector after applying M",
			"lineHeight": 1.25
		},
		{
			"id": "Ed86kAy_jtKM8KF7y8tPZ",
			"type": "arrow",
			"x": -24.665346137386997,
			"y": 274.3609371477829,
			"width": 3.235670146940951,
			"height": 152.67355725207,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 442730140,
			"version": 138,
			"versionNonce": 786668700,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.235670146940951,
					152.67355725207
				]
			],
			"lastCommittedPoint": [
				4.044332642439031,
				152.67355725206994
			],
			"startBinding": {
				"elementId": "L0jgfhVsMFc3FzieE4Eog",
				"focus": 0.05835118133484788,
				"gap": 4.61874964778292
			},
			"endBinding": {
				"elementId": "ete9zZXf",
				"focus": 0.039962300007353554,
				"gap": 12.784388858167404
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 436,
			"versionNonce": 1478953764,
			"isDeleted": false,
			"id": "ete9zZXf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -103.36313652207247,
			"y": 439.81888325802026,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.4606475830078,
			"height": 70,
			"seed": 2135116452,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ed86kAy_jtKM8KF7y8tPZ",
					"type": "arrow"
				}
			],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Level 2.2\ninfinity norm",
			"rawText": "Level 2.2\ninfinity norm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Level 2.2\ninfinity norm",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 899,
			"versionNonce": 1778231580,
			"isDeleted": false,
			"id": "L9GhLhHT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -198.37683128525606,
			"y": 535.8188832580203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 345.9996032714844,
			"height": 125,
			"seed": 88757796,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636336,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Another way to quantify magnitude\nin certain cases its to meassure\nthe distance of a vector only in a\ncertain axis, i.e take the maximum\ncomponent of that vector",
			"rawText": "Another way to quantify magnitude\nin certain cases its to meassure\nthe distance of a vector only in a\ncertain axis, i.e take the maximum\ncomponent of that vector",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Another way to quantify magnitude\nin certain cases its to meassure\nthe distance of a vector only in a\ncertain axis, i.e take the maximum\ncomponent of that vector",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "rectangle",
			"version": 366,
			"versionNonce": 1059202460,
			"isDeleted": false,
			"id": "yeYUGp5Y8PgAgE6pvneXC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -201.37702964951387,
			"y": 430.81888325802026,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 349,
			"height": 318,
			"seed": 1186864420,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "OL6p2ZAr2K3cYNxFAVkmn",
					"type": "arrow"
				}
			],
			"updated": 1707762636337,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 555,
			"versionNonce": 1471255076,
			"isDeleted": false,
			"id": "YRb1IwGJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -83.62167030398484,
			"y": 948.3937130447167,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 130.0885467529297,
			"height": 70,
			"seed": 1860518692,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636337,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Level 2.3\nP norm",
			"rawText": "Level 2.3\nP norm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Level 2.3\nP norm",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 1169,
			"versionNonce": 1669534236,
			"isDeleted": false,
			"id": "DFYL7UWW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -183.7614331824028,
			"y": 1044.3937130447166,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 326.879638671875,
			"height": 125,
			"seed": 253312676,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "BWl-cXEcByjyzVZ4kaLEj",
					"type": "arrow"
				}
			],
			"updated": 1707762636337,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "To generalize what we have just\nsaid about vector norms, the P \nnorm is the sum of norms of all\ncomponents of a vector to the\npower p under pth root",
			"rawText": "To generalize what we have just\nsaid about vector norms, the P \nnorm is the sum of norms of all\ncomponents of a vector to the\npower p under pth root",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To generalize what we have just\nsaid about vector norms, the P \nnorm is the sum of norms of all\ncomponents of a vector to the\npower p under pth root",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "rectangle",
			"version": 477,
			"versionNonce": 370306716,
			"isDeleted": false,
			"id": "4qX98HTIXLtoJTHuo5mi3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -196.3216138464653,
			"y": 939.3937130447167,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 349,
			"height": 318,
			"seed": 1062004132,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "OL6p2ZAr2K3cYNxFAVkmn",
					"type": "arrow"
				}
			],
			"updated": 1707762636337,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 198,
			"versionNonce": 1569085732,
			"isDeleted": false,
			"id": "OL6p2ZAr2K3cYNxFAVkmn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -24.788192455679933,
			"y": 757.6016423613046,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2135038257214354,
			"height": 172.89522046426464,
			"seed": 1558783140,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707762636337,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yeYUGp5Y8PgAgE6pvneXC",
				"focus": -0.005188686918700076,
				"gap": 8.78275910328432
			},
			"endBinding": {
				"elementId": "4qX98HTIXLtoJTHuo5mi3",
				"focus": -0.0032722144545805063,
				"gap": 8.896850219147439
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
					1.2135038257214354,
					172.89522046426464
				]
			]
		},
		{
			"id": "BWl-cXEcByjyzVZ4kaLEj",
			"type": "arrow",
			"x": 152.33319398777428,
			"y": 1108.2405750138448,
			"width": 133.89830508474597,
			"height": 3.389830508474688,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 245695132,
			"version": 48,
			"versionNonce": 1736588060,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1707762636337,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					133.89830508474597,
					3.389830508474688
				]
			],
			"lastCommittedPoint": [
				133.89830508474597,
				3.389830508474688
			],
			"startBinding": {
				"elementId": "DFYL7UWW",
				"focus": -0.04538189426012474,
				"gap": 9.214988498302091
			},
			"endBinding": {
				"elementId": "uMig1AhApBYBFSzIat534",
				"focus": 0.022124721970009406,
				"gap": 26.5064616499227
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "OXQmepSEAC1Q4hxcvhOjV",
			"type": "arrow",
			"x": 548.9433634792998,
			"y": 781.1219309460483,
			"width": 0,
			"height": 162.71186440677968,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1710548516,
			"version": 52,
			"versionNonce": 1965528228,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1707762636337,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					162.71186440677968
				]
			],
			"lastCommittedPoint": [
				0,
				162.71186440677968
			],
			"startBinding": {
				"elementId": "czfJwOOl2V0L_rluPtiO5",
				"focus": -0.006429387076758273,
				"gap": 7.782107369915593
			},
			"endBinding": {
				"elementId": "uMig1AhApBYBFSzIat534",
				"focus": 0.022000395070010982,
				"gap": 18.966101694915324
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 822,
			"versionNonce": 38041500,
			"isDeleted": false,
			"id": "afzcrTpw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 481.81426306038134,
			"y": 976.5282829526857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 123.17253112792969,
			"height": 70,
			"seed": 300106268,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762636337,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Level 5\nLpq Norm",
			"rawText": "Level 5\nLpq Norm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Level 5\nLpq Norm",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "rectangle",
			"version": 774,
			"versionNonce": 1921721372,
			"isDeleted": false,
			"id": "uMig1AhApBYBFSzIat534",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 312.73796072244295,
			"y": 962.7998970477433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 462.24131398829036,
			"height": 318,
			"seed": 1066822428,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "BWl-cXEcByjyzVZ4kaLEj",
					"type": "arrow"
				},
				{
					"id": "OXQmepSEAC1Q4hxcvhOjV",
					"type": "arrow"
				}
			],
			"updated": 1707762636337,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 684,
			"versionNonce": 1111165860,
			"isDeleted": false,
			"id": "3lsjXSlx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 310.6732131016331,
			"y": 1050.769131341583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 454.159423828125,
			"height": 150,
			"seed": 676505500,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762665521,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "the Lpq norm is as general as you can get\nin terms of norms for matrices, its as if\nwe take each row of the matrix and treat it\nas a vector, apply p norm on it, then\ntake each vector norm and apply q norm\non it",
			"rawText": "the Lpq norm is as general as you can get\nin terms of norms for matrices, its as if\nwe take each row of the matrix and treat it\nas a vector, apply p norm on it, then\ntake each vector norm and apply q norm\non it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the Lpq norm is as general as you can get\nin terms of norms for matrices, its as if\nwe take each row of the matrix and treat it\nas a vector, apply p norm on it, then\ntake each vector norm and apply q norm\non it",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 43,
			"versionNonce": 338434724,
			"isDeleted": false,
			"id": "BGwzzsl8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 366.4601213292579,
			"y": 1201.7805061863864,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 337.2985148070679,
			"height": 79.63992710722437,
			"seed": 36881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762681016,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4b35de1a7a66ff73c004f0533716735dd2f64295",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 602,
			"versionNonce": 802997148,
			"isDeleted": false,
			"id": "sFXyGWBoK2-KTkCrkaKA7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 371.58569297302654,
			"y": 716.932121777344,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 352.9624625934036,
			"height": 35.296246259340364,
			"seed": 1140179236,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762985899,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "169a31ef89a7d494bd180a5627e0b35f4f3829cc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 416,
			"versionNonce": 1437414812,
			"isDeleted": false,
			"id": "tdu2jATjp3U8HjTKIn_JV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -171.16933242284304,
			"y": 682.010840500793,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 294.066169024432,
			"height": 42.36546502894359,
			"seed": 811253156,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707762992998,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c8b1d2976ecdb0113de1c40f700a0043a6eedae7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 520,
			"versionNonce": 834769956,
			"isDeleted": false,
			"id": "10iV2cBCdkTsQJW5xG4Aj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -113.08668126334148,
			"y": 1177.8189219429087,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 197.21574171573567,
			"height": 63.17066726832159,
			"seed": 88559772,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707763010656,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cf0a393c1add947b387d02c468a9b685457d5347",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 471,
			"versionNonce": 793848732,
			"isDeleted": true,
			"id": "DDoI8YF_SU57NqmM8rVFE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -158.03448481744414,
			"y": 1189.9687930302448,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 294.066169024432,
			"height": 42.36546502894359,
			"seed": 239192612,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707763008827,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1d280b3ef4768a7eca0179893e29efc2f1518954",
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
		"currentItemRoughness": 2,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 572.5982195574799,
		"scrollY": -709.2420462444036,
		"zoom": {
			"value": 1.2425656385139658
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