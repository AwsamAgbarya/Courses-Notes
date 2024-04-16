---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - LinearAlgebra
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Linear subspace ^0ZVgsoRk

a linear Transformation is a function that takes in a vector and outputs
a vector indicating the movement from one to another
This is linear because all lines remain straight lines 
aka parallel and evenly spaced
and the origin point stays fixed!

This is described as 3x3 matrix where the image of the basis
vectors are the columns of the matrix!

These matrices can be a combination of different
transformations by composting them via matrix
multiplication from right to left ^gsLEcrWb

a linear subspace is the subspace that
contains all vectors in 3d space that
originate at the origin point of this space




To get from one point to another in a linear subspace
we can use linear transformations! ^ScqukuIO

Affine subspace ^F5NkyLyk

Represented by a homogeneous
coordinate where w is always 1 ^rwRyRYIu

An affine subspace is a subspace that allows for movement of
origin, such that this subspace is a linear subspace except
it can move its origin to any point in space
meaning it represents all vectors that represent
every point in 3d space and originate and any point in 3d space ^FphneE2F

x ^8EOL4F9u

y ^n6KsSxKF

p ^s2b2Kt5e

Projective Space ^R3wDCKNU

Projective space is the set of all lines that go through
the origin, this is intuitively 1 less dimension than the points
in all of space because each line is a bunch of points.

But that is exactly homogeneous coordinates! ^UIkZPd8W

Thus if we take the lines
of a 4dimensional space
we arrive at the points
in a three dimensional
space ^qaH6JEej

Homogeneous Coordinates ^G1XeWCiH

Coordinates in 4D space such that they define lines in R3
These coordinates identify points in R3 by giving them the
w value of 1, and identify a point at infinity (defined by that
vector that goes through it) with w value of 0! Because that
point at infinity is exactly when the "vector" originates from
in R4, thus all lines intersect at infinity! ^m88LUeYm

For any 2 Homogeneous coordinates that are scalar products
of each other, they're defined as the same point as they're 
identified by the same line! ^y0eCztX1

In affine subspace We have mapped R2 to R3 using
homogeneous coordinates to put our plane at elevation 1, this 
is merely the same concept but from R4 to R3.
Going back to normal coords only requires division by w. ^1jQtHZM8

* Vectors usually have 0 as w
* Points usually have 1 as w ^1I8y0Bz3

%%***>>>text element-link:[[Vectors]]<<<***%%Its good to also
refresh yourself on
what vector
subspaces are ^SFItg8RO

a linear transformation is a transformation
that satisfies:
f(v+w) = f(v) + f(w)
f(av) = af(v)  ^hs1SB0a1

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
			"version": 232,
			"versionNonce": 160754763,
			"isDeleted": false,
			"id": "NNbgFZzt5R7AcU5lwl1dT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -505.5861572778789,
			"y": -559.403677656556,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1038.4064670631951,
			"height": 942.1259335205802,
			"seed": 771523499,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753415168,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 203,
			"versionNonce": 789948523,
			"isDeleted": false,
			"id": "zhw8_9r2KXJbWhvnVQH_q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -437.3323624672777,
			"y": -240.73832017271582,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 606.7229075373507,
			"height": 553.4080650472497,
			"seed": 1685935877,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 258,
			"versionNonce": 885499845,
			"isDeleted": false,
			"id": "ibyqhxSvZxo7GpWV6uqkl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -391.83589439304546,
			"y": -0.901386020638995,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 290.9774837801288,
			"height": 257.1862701127267,
			"seed": 1776526149,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 448488203,
			"isDeleted": false,
			"id": "0ZVgsoRk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -293.2633003354458,
			"y": 13.874830111668757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 87.019287109375,
			"height": 13.955754035013662,
			"seed": 95425483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 11.164603228010929,
			"fontFamily": 1,
			"text": "Linear subspace",
			"rawText": "Linear subspace",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear subspace",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 1213,
			"versionNonce": 191391525,
			"isDeleted": false,
			"id": "gsLEcrWb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -360.1098943411742,
			"y": 154.6011266475815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 222.23336791992188,
			"height": 89.95882506776995,
			"seed": 481082469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 5.997255004517997,
			"fontFamily": 1,
			"text": "a linear Transformation is a function that takes in a vector and outputs\na vector indicating the movement from one to another\nThis is linear because all lines remain straight lines \naka parallel and evenly spaced\nand the origin point stays fixed!\n\nThis is described as 3x3 matrix where the image of the basis\nvectors are the columns of the matrix!\n\nThese matrices can be a combination of different\ntransformations by composting them via matrix\nmultiplication from right to left",
			"rawText": "a linear Transformation is a function that takes in a vector and outputs\na vector indicating the movement from one to another\nThis is linear because all lines remain straight lines \naka parallel and evenly spaced\nand the origin point stays fixed!\n\nThis is described as 3x3 matrix where the image of the basis\nvectors are the columns of the matrix!\n\nThese matrices can be a combination of different\ntransformations by composting them via matrix\nmultiplication from right to left",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a linear Transformation is a function that takes in a vector and outputs\na vector indicating the movement from one to another\nThis is linear because all lines remain straight lines \naka parallel and evenly spaced\nand the origin point stays fixed!\n\nThis is described as 3x3 matrix where the image of the basis\nvectors are the columns of the matrix!\n\nThese matrices can be a combination of different\ntransformations by composting them via matrix\nmultiplication from right to left",
			"lineHeight": 1.25,
			"baseline": 88
		},
		{
			"type": "text",
			"version": 475,
			"versionNonce": 185649579,
			"isDeleted": false,
			"id": "ScqukuIO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -374.4510245421087,
			"y": 45.943818042165475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 247.28741455078125,
			"height": 102.86433973060615,
			"seed": 485242379,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 9.143496864942769,
			"fontFamily": 1,
			"text": "a linear subspace is the subspace that\ncontains all vectors in 3d space that\noriginate at the origin point of this space\n\n\n\n\nTo get from one point to another in a linear subspace\nwe can use linear transformations!",
			"rawText": "a linear subspace is the subspace that\ncontains all vectors in 3d space that\noriginate at the origin point of this space\n\n\n\n\nTo get from one point to another in a linear subspace\nwe can use linear transformations!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a linear subspace is the subspace that\ncontains all vectors in 3d space that\noriginate at the origin point of this space\n\n\n\n\nTo get from one point to another in a linear subspace\nwe can use linear transformations!",
			"lineHeight": 1.25,
			"baseline": 99
		},
		{
			"type": "text",
			"version": 47,
			"versionNonce": 41564805,
			"isDeleted": false,
			"id": "F5NkyLyk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -196.9990785443178,
			"y": -223.51679820378135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 123.71224975585938,
			"height": 20,
			"seed": 1205689611,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Affine subspace",
			"rawText": "Affine subspace",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Affine subspace",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 624974923,
			"isDeleted": false,
			"id": "rwRyRYIu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -422.01794884060524,
			"y": -43.720905129165914,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 188.7336883544922,
			"height": 31.36552509382772,
			"seed": 219147467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 12.546210037531088,
			"fontFamily": 1,
			"text": "Represented by a homogeneous\ncoordinate where w is always 1",
			"rawText": "Represented by a homogeneous\ncoordinate where w is always 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Represented by a homogeneous\ncoordinate where w is always 1",
			"lineHeight": 1.25,
			"baseline": 26
		},
		{
			"type": "text",
			"version": 416,
			"versionNonce": 314221029,
			"isDeleted": false,
			"id": "FphneE2F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -363.94909078063546,
			"y": -148.42368850023954,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 434.4208984375,
			"height": 85.76527816187095,
			"seed": 1906895749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5c1G1AqfuUkbpRC5vFu7W",
					"type": "arrow"
				}
			],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 13.722444505899354,
			"fontFamily": 1,
			"text": "An affine subspace is a subspace that allows for movement of\norigin, such that this subspace is a linear subspace except\nit can move its origin to any point in space\nmeaning it represents all vectors that represent\nevery point in 3d space and originate and any point in 3d space",
			"rawText": "An affine subspace is a subspace that allows for movement of\norigin, such that this subspace is a linear subspace except\nit can move its origin to any point in space\nmeaning it represents all vectors that represent\nevery point in 3d space and originate and any point in 3d space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "An affine subspace is a subspace that allows for movement of\norigin, such that this subspace is a linear subspace except\nit can move its origin to any point in space\nmeaning it represents all vectors that represent\nevery point in 3d space and originate and any point in 3d space",
			"lineHeight": 1.25,
			"baseline": 81
		},
		{
			"type": "line",
			"version": 74,
			"versionNonce": 86285035,
			"isDeleted": false,
			"id": "1hSjOdGI2Oag26sk0ArIq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.28047046429697,
			"y": -26.480718999943832,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 139.33034192098376,
			"height": 24.470203419814354,
			"seed": 23632645,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					139.33034192098376,
					24.470203419814354
				]
			]
		},
		{
			"type": "arrow",
			"version": 507,
			"versionNonce": 1094131013,
			"isDeleted": false,
			"id": "6oyjOo5IKzKWD1rV4siYu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -83.26512062639458,
			"y": 29.052546093774012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 232.47743508017757,
			"height": 40.98004943178874,
			"seed": 700568965,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "n6KsSxKF",
				"focus": 2.0668986244776755,
				"gap": 13.702698962720234
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
					204.20158156763452,
					35.701890109447405
				],
				[
					232.47743508017757,
					40.98004943178874
				]
			]
		},
		{
			"type": "arrow",
			"version": 343,
			"versionNonce": 1732773259,
			"isDeleted": false,
			"id": "NnU4eSuSoOtBiyIRq_vnw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 58.352571833478066,
			"y": -11.024851210393933,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 114.23444819067385,
			"height": 128.18386925686178,
			"seed": 341218795,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LeZ8cikFm3eNneVjF1JEZ",
				"focus": -0.2574632277379923,
				"gap": 5.1649294506215995
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
					-98.02295884348251,
					108.57927748816527
				],
				[
					-114.23444819067385,
					128.18386925686178
				]
			]
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 357379237,
			"isDeleted": false,
			"id": "8EOL4F9u",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -47.09415797074094,
			"y": 125.02034940551404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 8.992019653320312,
			"height": 20,
			"seed": 1382643947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669041,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 13,
			"versionNonce": 317004843,
			"isDeleted": false,
			"id": "n6KsSxKF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 128.00560242953932,
			"y": 78.89097327721592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.5040130615234375,
			"height": 20,
			"seed": 1894992229,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6oyjOo5IKzKWD1rV4siYu",
					"type": "arrow"
				}
			],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 220,
			"versionNonce": 1319784453,
			"isDeleted": false,
			"id": "TvwJLGpsiY4hUeO4vhUix",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -85.97726228539403,
			"y": 46.4304993529724,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 139.33034192098376,
			"height": 24.470203419814354,
			"seed": 520587243,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					139.33034192098376,
					24.470203419814354
				]
			]
		},
		{
			"type": "line",
			"version": 83,
			"versionNonce": 65429195,
			"isDeleted": false,
			"id": "g8JcILWRoR97jrZQRNy0R",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 96.55047955015993,
			"y": -2.0105155801294785,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 43.69679182109704,
			"height": 73.41061025944306,
			"seed": 277071915,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-43.69679182109704,
					73.41061025944306
				]
			]
		},
		{
			"type": "line",
			"version": 116,
			"versionNonce": 1531709285,
			"isDeleted": false,
			"id": "Ncm1OVOiIYpS_uo1nEcqa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.15562248766527,
			"y": -26.73041495320725,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 43.69679182109704,
			"height": 73.41061025944306,
			"seed": 1064674277,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-43.69679182109704,
					73.41061025944306
				]
			]
		},
		{
			"type": "rectangle",
			"version": 985,
			"versionNonce": 1424379243,
			"isDeleted": false,
			"id": "LeZ8cikFm3eNneVjF1JEZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.18261169077535833,
			"x": -58.94344346073996,
			"y": -15.257488881570332,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 125.09998486645358,
			"height": 73.92729246577036,
			"seed": 1663696011,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5c1G1AqfuUkbpRC5vFu7W",
					"type": "arrow"
				},
				{
					"id": "NnU4eSuSoOtBiyIRq_vnw",
					"type": "arrow"
				}
			],
			"updated": 1702738669042,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 349,
			"versionNonce": 226480837,
			"isDeleted": false,
			"id": "5c1G1AqfuUkbpRC5vFu7W",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 10.095115172071303,
			"y": 126.96131393081609,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 4.524136562006902,
			"height": 171.75039472500387,
			"seed": 2116482309,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "FphneE2F",
				"focus": -0.7019701566348351,
				"gap": 17.869329544180765
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
					-4.524136562006902,
					-145.14938136438758
				],
				[
					-4.40175603564731,
					-171.75039472500387
				]
			]
		},
		{
			"type": "freedraw",
			"version": 19,
			"versionNonce": 1764714507,
			"isDeleted": false,
			"id": "Mi4-CEnY2cgj9AlWlwZ92",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7.908416141648786,
			"y": 26.95421499842628,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 2.9963514391609465,
			"height": 0.4993919065268244,
			"seed": 337966469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.24969595326342642,
					0.2496959532634122
				],
				[
					-0.9987838130536488,
					0.2496959532634122
				],
				[
					-1.747871672843928,
					0.4993919065268244
				],
				[
					-2.247263579370724,
					0.4993919065268244
				],
				[
					-2.746655485897577,
					0.4993919065268244
				],
				[
					-2.9963514391609465,
					0.4993919065268244
				],
				[
					-2.746655485897577,
					0.4993919065268244
				],
				[
					-2.4969595326341505,
					0.4993919065268244
				],
				[
					-2.247263579370724,
					0.4993919065268244
				],
				[
					-1.9975676261072977,
					0.4993919065268244
				],
				[
					-1.747871672843928,
					0.4993919065268244
				],
				[
					-1.4981757195805017,
					0.4993919065268244
				],
				[
					-1.2484797663170752,
					0.4993919065268244
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
			"versionNonce": 1455173291,
			"isDeleted": false,
			"id": "hu-1zDRgnPoZBp-lUK8RP",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8.907199954702435,
			"y": 28.95178262453358,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 4.744223112004875,
			"height": 1.9975676261072834,
			"seed": 1534672043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.49939190652685284,
					0.2496959532634122
				],
				[
					-0.9987838130536488,
					0.4993919065268244
				],
				[
					-1.4981757195805017,
					0.4993919065268244
				],
				[
					-1.747871672843928,
					0.4993919065268244
				],
				[
					-1.9975676261072977,
					0.4993919065268244
				],
				[
					-1.9975676261072977,
					0.7490878597902366
				],
				[
					-2.247263579370724,
					0.7490878597902366
				],
				[
					-2.4969595326341505,
					0.9987838130536488
				],
				[
					-3.246047392424373,
					1.248479766317061
				],
				[
					-3.4957433456877993,
					1.4981757195804732
				],
				[
					-3.9951352522145953,
					1.4981757195804732
				],
				[
					-4.244831205478022,
					1.7478716728438854
				],
				[
					-4.494527158741448,
					1.9975676261072834
				],
				[
					-4.744223112004875,
					1.9975676261072834
				],
				[
					-4.744223112004875,
					1.9975676261072834
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 27,
			"versionNonce": 627287429,
			"isDeleted": false,
			"id": "68gI_itOMkMi19Fjt1MxJ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 0.9169294502732441,
			"y": 18.714248540733692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 11.73570980338036,
			"seed": 1429535051,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738669042,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.2496959532634122
				],
				[
					0,
					0.9987838130536488
				],
				[
					0,
					1.7478716728438854
				],
				[
					0,
					2.7466554858975343
				],
				[
					0,
					3.2460473924243587
				],
				[
					0,
					4.4945271587414055
				],
				[
					0,
					5.243615018531642
				],
				[
					0,
					6.492094784848703
				],
				[
					0,
					7.24118264463894
				],
				[
					0,
					7.990270504429176
				],
				[
					0,
					8.489662410956
				],
				[
					0,
					9.238750270746237
				],
				[
					0,
					9.738142177273062
				],
				[
					0,
					9.987838130536474
				],
				[
					0,
					10.237534083799886
				],
				[
					0,
					10.73692599032671
				],
				[
					0,
					10.986621943590123
				],
				[
					0,
					11.236317896853535
				],
				[
					0,
					11.486013850116947
				],
				[
					0,
					11.73570980338036
				],
				[
					0,
					11.486013850116947
				],
				[
					0,
					10.986621943590123
				],
				[
					0,
					10.73692599032671
				],
				[
					0,
					10.73692599032671
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 27,
			"versionNonce": 148920485,
			"isDeleted": false,
			"id": "lr23tsMeiDo7ctwbrJQJo",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -0.3315503160438311,
			"y": 18.714248540733692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 4.494527158741391,
			"height": 4.744223112004818,
			"seed": 1325055979,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738671101,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.2496959532634122
				],
				[
					0,
					0.4993919065268244
				],
				[
					-0.24969595326342642,
					0.4993919065268244
				],
				[
					-0.24969595326342642,
					0.9987838130536488
				],
				[
					-0.499391906526796,
					0.9987838130536488
				],
				[
					-0.7490878597902224,
					1.248479766317061
				],
				[
					-0.7490878597902224,
					1.4981757195804732
				],
				[
					-0.9987838130536488,
					1.4981757195804732
				],
				[
					-1.2484797663170752,
					1.9975676261072977
				],
				[
					-1.7478716728438712,
					2.24726357937071
				],
				[
					-1.7478716728438712,
					2.496959532634122
				],
				[
					-1.9975676261072977,
					2.496959532634122
				],
				[
					-2.247263579370724,
					2.7466554858975343
				],
				[
					-2.4969595326340936,
					2.7466554858975343
				],
				[
					-2.74665548589752,
					3.2460473924243587
				],
				[
					-2.9963514391609465,
					3.2460473924243587
				],
				[
					-3.246047392424373,
					3.495743345687771
				],
				[
					-3.4957433456877425,
					3.495743345687771
				],
				[
					-3.745439298951169,
					3.745439298951183
				],
				[
					-3.745439298951169,
					3.9951352522145953
				],
				[
					-3.9951352522145953,
					4.2448312054780075
				],
				[
					-4.244831205478022,
					4.2448312054780075
				],
				[
					-4.244831205478022,
					4.4945271587414055
				],
				[
					-4.494527158741391,
					4.744223112004818
				],
				[
					-4.494527158741391,
					4.744223112004818
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 77,
			"versionNonce": 786764933,
			"isDeleted": false,
			"id": "BKpRr8MC5YJlQVYWREfGj",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 57.397872472419294,
			"y": 19.78127785915308,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.908991321269525,
			"height": 4.251602700317008,
			"seed": 1234793163,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738681239,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.4475371263491468
				],
				[
					0,
					-0.8950742526983078
				],
				[
					0,
					-0.6713056895237344
				],
				[
					0,
					-0.4475371263491468
				],
				[
					0,
					-0.2237685631745734
				],
				[
					0,
					0.6713056895237486
				],
				[
					0,
					1.1188428158728954
				],
				[
					-0.2237685631745876,
					1.342611379047483
				],
				[
					-0.4475371263491468,
					1.790148505396644
				],
				[
					-0.6713056895237344,
					1.790148505396644
				],
				[
					-0.895074252698322,
					1.790148505396644
				],
				[
					-0.895074252698322,
					1.5663799422220563
				],
				[
					-0.895074252698322,
					0.895074252698322
				],
				[
					-0.895074252698322,
					0.447537126349161
				],
				[
					-0.6713056895237344,
					0.2237685631745876
				],
				[
					-0.4475371263491468,
					0
				],
				[
					-0.4475371263491468,
					-0.2237685631745734
				],
				[
					-0.4475371263491468,
					0.447537126349161
				],
				[
					-0.4475371263491468,
					1.1188428158728954
				],
				[
					-0.4475371263491468,
					1.790148505396644
				],
				[
					-0.4475371263491468,
					2.237685631745805
				],
				[
					-1.1188428158728811,
					2.6852227580949517
				],
				[
					-1.3426113790474687,
					2.9089913212695393
				],
				[
					-1.5663799422220563,
					2.9089913212695393
				],
				[
					-1.790148505396644,
					3.1327598844441127
				],
				[
					-2.013917068571203,
					3.1327598844441127
				],
				[
					-2.4614541949203783,
					3.1327598844441127
				],
				[
					-2.4614541949203783,
					2.9089913212695393
				],
				[
					-2.6852227580949375,
					2.6852227580949517
				],
				[
					-2.908991321269525,
					2.4614541949203783
				],
				[
					-2.908991321269525,
					2.0139170685712173
				],
				[
					-2.908991321269525,
					1.342611379047483
				],
				[
					-2.908991321269525,
					1.1188428158728954
				],
				[
					-2.6852227580949375,
					0.6713056895237486
				],
				[
					-2.2376856317457907,
					0.447537126349161
				],
				[
					-2.013917068571203,
					0
				],
				[
					-1.5663799422220563,
					-0.4475371263491468
				],
				[
					-1.3426113790474687,
					-0.6713056895237344
				],
				[
					-1.1188428158728811,
					-0.6713056895237344
				],
				[
					-0.6713056895237344,
					-0.2237685631745734
				],
				[
					-0.6713056895237344,
					0
				],
				[
					-0.6713056895237344,
					0.2237685631745876
				],
				[
					-0.4475371263491468,
					0.447537126349161
				],
				[
					-0.2237685631745876,
					0.6713056895237486
				],
				[
					-0.2237685631745876,
					0.895074252698322
				],
				[
					-0.2237685631745876,
					1.5663799422220563
				],
				[
					-0.4475371263491468,
					2.0139170685712173
				],
				[
					-0.6713056895237344,
					2.4614541949203783
				],
				[
					-0.6713056895237344,
					2.9089913212695393
				],
				[
					-1.1188428158728811,
					3.1327598844441127
				],
				[
					-1.3426113790474687,
					3.1327598844441127
				],
				[
					-1.5663799422220563,
					3.1327598844441127
				],
				[
					-1.790148505396644,
					3.1327598844441127
				],
				[
					-2.013917068571203,
					3.1327598844441127
				],
				[
					-2.2376856317457907,
					2.6852227580949517
				],
				[
					-2.4614541949203783,
					2.4614541949203783
				],
				[
					-2.6852227580949375,
					2.0139170685712173
				],
				[
					-2.908991321269525,
					1.5663799422220563
				],
				[
					-2.908991321269525,
					1.342611379047483
				],
				[
					-2.908991321269525,
					0.895074252698322
				],
				[
					-2.908991321269525,
					0.2237685631745876
				],
				[
					-2.908991321269525,
					-0.2237685631745734
				],
				[
					-2.908991321269525,
					-0.6713056895237344
				],
				[
					-2.6852227580949375,
					-0.8950742526983078
				],
				[
					-2.4614541949203783,
					-0.8950742526983078
				],
				[
					-2.013917068571203,
					-0.8950742526983078
				],
				[
					-1.790148505396644,
					-1.1188428158728954
				],
				[
					-1.5663799422220563,
					-1.1188428158728954
				],
				[
					-1.3426113790474687,
					-1.1188428158728954
				],
				[
					-1.1188428158728811,
					-1.1188428158728954
				],
				[
					-0.895074252698322,
					-1.1188428158728954
				],
				[
					-0.895074252698322,
					-0.6713056895237344
				],
				[
					-0.6713056895237344,
					-0.4475371263491468
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
			"type": "text",
			"version": 2,
			"versionNonce": 1202603685,
			"isDeleted": false,
			"id": "s2b2Kt5e",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 62.62837568904189,
			"y": 15.305906595661497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.8880157470703125,
			"height": 20,
			"seed": 1275306219,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738684488,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "p",
			"rawText": "p",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 109,
			"versionNonce": 508471019,
			"isDeleted": false,
			"id": "HjXrvQ-Uo4mWSBV162gfp",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7.945020010837283,
			"y": 46.85727400327717,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 125.31039537776434,
			"height": 67.13056895237375,
			"seed": 1739497829,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702738695802,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					125.31039537776434,
					-67.13056895237375
				]
			]
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 154713483,
			"isDeleted": false,
			"id": "R3wDCKNU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -141.15564660931892,
			"y": -527.8653026423073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 294.94805908203125,
			"height": 45,
			"seed": 1169997829,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753427243,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Projective Space",
			"rawText": "Projective Space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Projective Space",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 310,
			"versionNonce": 600351051,
			"isDeleted": false,
			"id": "UIkZPd8W",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -319.8361952556427,
			"y": -450.77353429874614,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 679.5400390625,
			"height": 144.14985774001732,
			"seed": 909902597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753558284,
			"link": null,
			"locked": false,
			"fontSize": 23.06397723840277,
			"fontFamily": 1,
			"text": "Projective space is the set of all lines that go through\nthe origin, this is intuitively 1 less dimension than the points\nin all of space because each line is a bunch of points.\n\nBut that is exactly homogeneous coordinates!",
			"rawText": "Projective space is the set of all lines that go through\nthe origin, this is intuitively 1 less dimension than the points\nin all of space because each line is a bunch of points.\n\nBut that is exactly homogeneous coordinates!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Projective space is the set of all lines that go through\nthe origin, this is intuitively 1 less dimension than the points\nin all of space because each line is a bunch of points.\n\nBut that is exactly homogeneous coordinates!",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "arrow",
			"version": 134,
			"versionNonce": 1002891237,
			"isDeleted": false,
			"id": "SUzFDMLp5c48XJviyL1Yi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 294.45508704092947,
			"y": -314.7068321426062,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 197.44091046388883,
			"height": 177.69681941749997,
			"seed": 977472139,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702753574043,
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
					171.93812619563676,
					-23.85744334771988
				],
				[
					197.44091046388883,
					-177.69681941749997
				]
			]
		},
		{
			"type": "text",
			"version": 220,
			"versionNonce": 1036544907,
			"isDeleted": false,
			"id": "qaH6JEej",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 178.6206120394105,
			"y": -281.4293177190836,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 234.00401306152344,
			"height": 115.39703084795903,
			"seed": 890757003,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753684583,
			"link": null,
			"locked": false,
			"fontSize": 18.463524935673444,
			"fontFamily": 1,
			"text": "Thus if we take the lines\nof a 4dimensional space\nwe arrive at the points\nin a three dimensional\nspace",
			"rawText": "Thus if we take the lines\nof a 4dimensional space\nwe arrive at the points\nin a three dimensional\nspace",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thus if we take the lines\nof a 4dimensional space\nwe arrive at the points\nin a three dimensional\nspace",
			"lineHeight": 1.25,
			"baseline": 108
		},
		{
			"type": "rectangle",
			"version": 59,
			"versionNonce": 912832805,
			"isDeleted": false,
			"id": "8wWcXN-ozb1z61UZ6KTTs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 330.65258729264247,
			"y": -944.049734246252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 515.8143785869097,
			"height": 432.724662100023,
			"seed": 1802928485,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702753697333,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 1915164939,
			"isDeleted": false,
			"id": "G1XeWCiH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 425.3050857060018,
			"y": -934.1776887230576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 343.78546142578125,
			"height": 35,
			"seed": 347892299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753709694,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Homogeneous Coordinates",
			"rawText": "Homogeneous Coordinates",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Homogeneous Coordinates",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 470,
			"versionNonce": 467724811,
			"isDeleted": false,
			"id": "m88LUeYm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 348.31013862742816,
			"y": -885.5441657097474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 500.2409973144531,
			"height": 120,
			"seed": 297177675,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753919219,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Coordinates in 4D space such that they define lines in R3\nThese coordinates identify points in R3 by giving them the\nw value of 1, and identify a point at infinity (defined by that\nvector that goes through it) with w value of 0! Because that\npoint at infinity is exactly when the \"vector\" originates from\nin R4, thus all lines intersect at infinity!",
			"rawText": "Coordinates in 4D space such that they define lines in R3\nThese coordinates identify points in R3 by giving them the\nw value of 1, and identify a point at infinity (defined by that\nvector that goes through it) with w value of 0! Because that\npoint at infinity is exactly when the \"vector\" originates from\nin R4, thus all lines intersect at infinity!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Coordinates in 4D space such that they define lines in R3\nThese coordinates identify points in R3 by giving them the\nw value of 1, and identify a point at infinity (defined by that\nvector that goes through it) with w value of 0! Because that\npoint at infinity is exactly when the \"vector\" originates from\nin R4, thus all lines intersect at infinity!",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 1151583845,
			"isDeleted": false,
			"id": "y0eCztX1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 338.8792918953044,
			"y": -715.3473462922475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 491.8410339355469,
			"height": 60,
			"seed": 309040459,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702753921665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "For any 2 Homogeneous coordinates that are scalar products\nof each other, they're defined as the same point as they're \nidentified by the same line!",
			"rawText": "For any 2 Homogeneous coordinates that are scalar products\nof each other, they're defined as the same point as they're \nidentified by the same line!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For any 2 Homogeneous coordinates that are scalar products\nof each other, they're defined as the same point as they're \nidentified by the same line!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 1846856875,
			"isDeleted": false,
			"id": "1jQtHZM8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 338.63939073289964,
			"y": -620.1767087561043,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 499.93695068359375,
			"height": 80,
			"seed": 44181317,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702754162088,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "In affine subspace We have mapped R2 to R3 using\nhomogeneous coordinates to put our plane at elevation 1, this \nis merely the same concept but from R4 to R3.\nGoing back to normal coords only requires division by w.",
			"rawText": "In affine subspace We have mapped R2 to R3 using\nhomogeneous coordinates to put our plane at elevation 1, this \nis merely the same concept but from R4 to R3.\nGoing back to normal coords only requires division by w.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In affine subspace We have mapped R2 to R3 using\nhomogeneous coordinates to put our plane at elevation 1, this \nis merely the same concept but from R4 to R3.\nGoing back to normal coords only requires division by w.",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 95,
			"versionNonce": 1931571211,
			"isDeleted": false,
			"id": "1I8y0Bz3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 160.11963252771727,
			"y": -122.73440780518729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 244.04849243164062,
			"height": 40,
			"seed": 1890006027,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702754415623,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* Vectors usually have 0 as w\n* Points usually have 1 as w",
			"rawText": "* Vectors usually have 0 as w\n* Points usually have 1 as w",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Vectors usually have 0 as w\n* Points usually have 1 as w",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 184,
			"versionNonce": 155888265,
			"isDeleted": false,
			"id": "SFItg8RO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -59.67735094893192,
			"y": 193.0298683157918,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 104.98539733886719,
			"height": 56.13213186412186,
			"seed": 1900772262,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513938972,
			"link": "[[Vectors]]",
			"locked": false,
			"fontSize": 11.226426372824372,
			"fontFamily": 1,
			"text": "Its good to also\nrefresh yourself on\nwhat vector\nsubspaces are",
			"rawText": "Its good to also\nrefresh yourself on\nwhat vector\nsubspaces are",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Its good to also\nrefresh yourself on\nwhat vector\nsubspaces are",
			"lineHeight": 1.25,
			"baseline": 52
		},
		{
			"id": "hs1SB0a1",
			"type": "text",
			"x": -319.7240939014132,
			"y": 86.34433895261611,
			"width": 141.33783042080353,
			"height": 32.59177777256639,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 425413780,
			"version": 300,
			"versionNonce": 13036180,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710919762696,
			"link": null,
			"locked": false,
			"text": "a linear transformation is a transformation\nthat satisfies:\nf(v+w) = f(v) + f(w)\nf(av) = af(v) ",
			"rawText": "a linear transformation is a transformation\nthat satisfies:\nf(v+w) = f(v) + f(w)\nf(av) = af(v) ",
			"fontSize": 6.51835555451327,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 30.000000000000036,
			"containerId": null,
			"originalText": "a linear transformation is a transformation\nthat satisfies:\nf(v+w) = f(v) + f(w)\nf(av) = af(v) ",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1971c2",
		"currentItemBackgroundColor": "#a5d8ff",
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
		"scrollX": 443.2634993545457,
		"scrollY": 635.0734931873646,
		"zoom": {
			"value": 1.0160936957858528
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