---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
What is clipping and what is culling? ^7CGwyM53

Clipping and Culling ^9Fhd2i6U

Clipping ^scW3jHmQ

Culling ^MjZHKyxR

V.S ^W1uiRDSW

Clipping part of an object to make it only
partially visible that way we do not have to
render all of it when it is not within the view ^YbM8aBtZ

Is the removal of primitives that are occluded
either by being behind the view, behind a
larger object or not facing the viewer ^U1J1pLnB

Sometimes is too complicated and doesnt
save on time ^Lzf7WECB

BV-Heirarchy ^AR2fGi7K

Collect bounding boxes of local ecosystems using 
min and max values of their vertices.
build a hierarchy tree using those boxes and render
according to the hierarchy

If BV within view => check rendering of children
if BV not within view => dont render ^1Fr7UcME

Backface culling ^G3evEN23

We dont want to render vertices that are not facing the viewer
to have less primitives within the scene

but how do we detect backfaces?
we shoot a ray from the viewer to the object and check
the sign of the dot-product of that ray and the points
it intersects ^AOPADBRA

NDC Clipping ^g2KBNTm6

We always turn our scene
(whether its perspective or parallel)
into the NDC space, thus clipping primitives from the 
six faces of the canonical box is quite easy
intersections with planes! ^CwjZmaTU

Perspective culling ^TSQzaHSl

Lets say we had some object behind the the eye
that object intuitively should be not rendered
but when we preform our perspective transformation
we warp space to look like perspective
but in reality we go to parallel where the 
eye is at infinity, and thus those objects will be morphed
but will be in front of the eye and we do not want that

Using homogeneous coordinates and using the convention of
w=1 we can actually tell whether this object was
within our view or not, because the sign of w
indicates whether it is in our finite view or not
so we clip all points that have w<0 ^uH8C8ux7

But what if half of my object is behind
me and the other half is in front??? ^BB0nBEQP

Firstly we Need to detect such objects
and using homogeneous coordinates we can actually see
that a point at the view line goes to infinity and we
can detect that point of the line that intersects
the view plane ^gmUU2JgE

Then we cut the line into two segments, one with w= epsilon the other with w=-epsilon
and we render each segment on its own using previous methodology such that
the one in front is rendered normally and the one at the back is culled ^8HvkVrP3

These two segments can never intersect at a finite point anymore!!
they only intersect at infinity as if they're both going the opposite
direction of each other to meet all the way around the world ^DISzDELF


# Embedded files
f28f688f89ecb2996525e33d9d73f79fb7b0ecd6: [[Pasted Image 20231217165643_117.png]]

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
			"version": 100,
			"versionNonce": 1464143286,
			"isDeleted": false,
			"id": "7CGwyM53",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -186.580201139711,
			"y": -380.3803983689446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 627.8402099609375,
			"height": 45,
			"seed": 702443434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052826,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "What is clipping and what is culling?",
			"rawText": "What is clipping and what is culling?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is clipping and what is culling?",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "ellipse",
			"version": 149,
			"versionNonce": 1973702826,
			"isDeleted": false,
			"id": "oPM-zi1yPi6kUIGocOhJW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -273.74171380074574,
			"y": -611.5672437642747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 716.4252919089593,
			"height": 218.87406034191326,
			"seed": 2000716918,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9Fhd2i6U"
				}
			],
			"updated": 1702827052826,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 1863075638,
			"isDeleted": false,
			"id": "9Fhd2i6U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -76.00972458128268,
			"y": -524.5138797401183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 321.37213134765625,
			"height": 45,
			"seed": 1729683638,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827707018,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Clipping and Culling",
			"rawText": "Clipping and Culling",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "oPM-zi1yPi6kUIGocOhJW",
			"originalText": "Clipping and Culling",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 384346986,
			"isDeleted": false,
			"id": "scW3jHmQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -228.1836698855218,
			"y": -295.3084546476244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 92.37237548828125,
			"height": 35,
			"seed": 417287338,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052826,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Clipping",
			"rawText": "Clipping",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Clipping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 702126134,
			"isDeleted": false,
			"id": "MjZHKyxR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 353.31552458622104,
			"y": -298.95655250869584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 81.90032958984375,
			"height": 35,
			"seed": 291776362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052826,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Culling",
			"rawText": "Culling",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Culling",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 743681578,
			"isDeleted": false,
			"id": "W1uiRDSW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 89.13326745335428,
			"y": -232.92739506826888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 39.17216491699219,
			"height": 35,
			"seed": 1107274282,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052826,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 350,
			"versionNonce": 874749994,
			"isDeleted": false,
			"id": "YbM8aBtZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -405.2433780601283,
			"y": -242.50733672948974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 446.65948486328125,
			"height": 75,
			"seed": 1100797162,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rvPWIYpoheqWJmz1KpIN0",
					"type": "arrow"
				},
				{
					"id": "Lr80h8X7b0F8xLnO_PB-A",
					"type": "arrow"
				}
			],
			"updated": 1702828210974,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Clipping part of an object to make it only\npartially visible that way we do not have to\nrender all of it when it is not within the view",
			"rawText": "Clipping part of an object to make it only\npartially visible that way we do not have to\nrender all of it when it is not within the view",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Clipping part of an object to make it only\npartially visible that way we do not have to\nrender all of it when it is not within the view",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 469,
			"versionNonce": 1255168234,
			"isDeleted": false,
			"id": "U1J1pLnB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 172.52226833905024,
			"y": -245.56334450799363,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 465.01947021484375,
			"height": 75,
			"seed": 298231722,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Cy8v903bdkJnZIiwZfzLG",
					"type": "arrow"
				},
				{
					"id": "DuHXJgGJX8jnHVgTDJSvZ",
					"type": "arrow"
				}
			],
			"updated": 1702827052826,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Is the removal of primitives that are occluded\neither by being behind the view, behind a\nlarger object or not facing the viewer",
			"rawText": "Is the removal of primitives that are occluded\neither by being behind the view, behind a\nlarger object or not facing the viewer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Is the removal of primitives that are occluded\neither by being behind the view, behind a\nlarger object or not facing the viewer",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 1269662390,
			"isDeleted": false,
			"id": "Lzf7WECB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.78276703549083,
			"x": -588.4360998102604,
			"y": -268.5357740499985,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 323.9366455078125,
			"height": 40,
			"seed": 1252532842,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052827,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sometimes is too complicated and doesnt\nsave on time",
			"rawText": "Sometimes is too complicated and doesnt\nsave on time",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sometimes is too complicated and doesnt\nsave on time",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 441,
			"versionNonce": 439355178,
			"isDeleted": false,
			"id": "AR2fGi7K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 944.7660087052858,
			"y": -78.78886674510136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 166.99269104003906,
			"height": 35,
			"seed": 10577002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DuHXJgGJX8jnHVgTDJSvZ",
					"type": "arrow"
				}
			],
			"updated": 1702828263992,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "BV-Heirarchy",
			"rawText": "BV-Heirarchy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BV-Heirarchy",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 512,
			"versionNonce": 2009769578,
			"isDeleted": false,
			"id": "1Fr7UcME",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 779.4036161839994,
			"y": -4.937473240773613,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 510.859375,
			"height": 175,
			"seed": 319383210,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052827,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Collect bounding boxes of local ecosystems using \nmin and max values of their vertices.\nbuild a hierarchy tree using those boxes and render\naccording to the hierarchy\n\nIf BV within view => check rendering of children\nif BV not within view => dont render",
			"rawText": "Collect bounding boxes of local ecosystems using \nmin and max values of their vertices.\nbuild a hierarchy tree using those boxes and render\naccording to the hierarchy\n\nIf BV within view => check rendering of children\nif BV not within view => dont render",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Collect bounding boxes of local ecosystems using \nmin and max values of their vertices.\nbuild a hierarchy tree using those boxes and render\naccording to the hierarchy\n\nIf BV within view => check rendering of children\nif BV not within view => dont render",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 1951875958,
			"isDeleted": false,
			"id": "G3evEN23",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 305.83106735701557,
			"y": -66.62654423000299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 220.30491638183594,
			"height": 35,
			"seed": 559096694,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Cy8v903bdkJnZIiwZfzLG",
					"type": "arrow"
				}
			],
			"updated": 1702828259850,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Backface culling",
			"rawText": "Backface culling",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Backface culling",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 386,
			"versionNonce": 893274410,
			"isDeleted": false,
			"id": "AOPADBRA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 84.80804689939436,
			"y": 7.83777861904764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 641.6994018554688,
			"height": 175,
			"seed": 1397071338,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702827052827,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We dont want to render vertices that are not facing the viewer\nto have less primitives within the scene\n\nbut how do we detect backfaces?\nwe shoot a ray from the viewer to the object and check\nthe sign of the dot-product of that ray and the points\nit intersects",
			"rawText": "We dont want to render vertices that are not facing the viewer\nto have less primitives within the scene\n\nbut how do we detect backfaces?\nwe shoot a ray from the viewer to the object and check\nthe sign of the dot-product of that ray and the points\nit intersects",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We dont want to render vertices that are not facing the viewer\nto have less primitives within the scene\n\nbut how do we detect backfaces?\nwe shoot a ray from the viewer to the object and check\nthe sign of the dot-product of that ray and the points\nit intersects",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "arrow",
			"version": 47,
			"versionNonce": 833845174,
			"isDeleted": false,
			"id": "Cy8v903bdkJnZIiwZfzLG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 409.0965524075036,
			"y": -157.92283453563368,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.9271068981329904,
			"height": 86.71981041598292,
			"seed": 536694198,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702827052827,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "U1J1pLnB",
				"focus": -0.022193856241706743,
				"gap": 12.64050997235995
			},
			"endBinding": {
				"elementId": "G3evEN23",
				"focus": -0.11784372098994701,
				"gap": 9.576479889647771
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
					-1.9271068981329904,
					86.71981041598292
				]
			]
		},
		{
			"type": "arrow",
			"version": 266,
			"versionNonce": 254379690,
			"isDeleted": false,
			"id": "DuHXJgGJX8jnHVgTDJSvZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 418.7320868981684,
			"y": -153.1050672903013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 642.6901505273398,
			"height": 84.79270351784993,
			"seed": 956156342,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702827052827,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "U1J1pLnB",
				"focus": 1.3058694949259226,
				"gap": 17.45827721769234
			},
			"endBinding": {
				"elementId": "AR2fGi7K",
				"focus": 0.7142579373045099,
				"gap": 6.086138416147719
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
					559.824553907623,
					-11.562641388797715
				],
				[
					642.6901505273398,
					73.23006212905221
				]
			]
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 106729130,
			"isDeleted": false,
			"id": "g2KBNTm6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -304.33753755458315,
			"y": -59.82021651995859,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 164.27667236328125,
			"height": 35,
			"seed": 997338230,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rvPWIYpoheqWJmz1KpIN0",
					"type": "arrow"
				}
			],
			"updated": 1702828256573,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "NDC Clipping",
			"rawText": "NDC Clipping",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "NDC Clipping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 1233754294,
			"isDeleted": false,
			"id": "CwjZmaTU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -478.0936340626498,
			"y": 1.9478618301497477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 528.2994384765625,
			"height": 125,
			"seed": 920144310,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702828217566,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We always turn our scene\n(whether its perspective or parallel)\ninto the NDC space, thus clipping primitives from the \nsix faces of the canonical box is quite easy\nintersections with planes!",
			"rawText": "We always turn our scene\n(whether its perspective or parallel)\ninto the NDC space, thus clipping primitives from the \nsix faces of the canonical box is quite easy\nintersections with planes!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We always turn our scene\n(whether its perspective or parallel)\ninto the NDC space, thus clipping primitives from the \nsix faces of the canonical box is quite easy\nintersections with planes!",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"id": "TSQzaHSl",
			"type": "text",
			"x": -902.9902595305664,
			"y": -63.445237235288005,
			"width": 248.08103942871094,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1068101750,
			"version": 34,
			"versionNonce": 981049194,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Lr80h8X7b0F8xLnO_PB-A",
					"type": "arrow"
				}
			],
			"updated": 1702828267684,
			"link": null,
			"locked": false,
			"text": "Perspective culling",
			"rawText": "Perspective culling",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Perspective culling",
			"lineHeight": 1.25
		},
		{
			"id": "uH8C8ux7",
			"type": "text",
			"x": -1067.515620650711,
			"y": -13.849734904435763,
			"width": 580.6994018554688,
			"height": 325,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1724116790,
			"version": 663,
			"versionNonce": 1292301546,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ei6VGqnauHgwsrhalpYVS",
					"type": "arrow"
				}
			],
			"updated": 1702828178731,
			"link": null,
			"locked": false,
			"text": "Lets say we had some object behind the the eye\nthat object intuitively should be not rendered\nbut when we preform our perspective transformation\nwe warp space to look like perspective\nbut in reality we go to parallel where the \neye is at infinity, and thus those objects will be morphed\nbut will be in front of the eye and we do not want that\n\nUsing homogeneous coordinates and using the convention of\nw=1 we can actually tell whether this object was\nwithin our view or not, because the sign of w\nindicates whether it is in our finite view or not\nso we clip all points that have w<0",
			"rawText": "Lets say we had some object behind the the eye\nthat object intuitively should be not rendered\nbut when we preform our perspective transformation\nwe warp space to look like perspective\nbut in reality we go to parallel where the \neye is at infinity, and thus those objects will be morphed\nbut will be in front of the eye and we do not want that\n\nUsing homogeneous coordinates and using the convention of\nw=1 we can actually tell whether this object was\nwithin our view or not, because the sign of w\nindicates whether it is in our finite view or not\nso we clip all points that have w<0",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 318,
			"containerId": null,
			"originalText": "Lets say we had some object behind the the eye\nthat object intuitively should be not rendered\nbut when we preform our perspective transformation\nwe warp space to look like perspective\nbut in reality we go to parallel where the \neye is at infinity, and thus those objects will be morphed\nbut will be in front of the eye and we do not want that\n\nUsing homogeneous coordinates and using the convention of\nw=1 we can actually tell whether this object was\nwithin our view or not, because the sign of w\nindicates whether it is in our finite view or not\nso we clip all points that have w<0",
			"lineHeight": 1.25
		},
		{
			"id": "ei6VGqnauHgwsrhalpYVS",
			"type": "arrow",
			"x": -805.8600543412434,
			"y": 331.5520725269281,
			"width": 491.8861132704691,
			"height": 91.33014776935869,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 1506331510,
			"version": 201,
			"versionNonce": 1912974262,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702828293877,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					92.78610778072402,
					91.33014776935869
				],
				[
					491.8861132704691,
					58.96724460197356
				]
			],
			"lastCommittedPoint": [
				303.788744653854,
				210.6921938728343
			],
			"startBinding": {
				"elementId": "uH8C8ux7",
				"focus": 0.47099860211819744,
				"gap": 20.401807431363864
			},
			"endBinding": {
				"elementId": "BB0nBEQP",
				"focus": 0.2980068892621536,
				"gap": 13.853478347053567
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "rvPWIYpoheqWJmz1KpIN0",
			"type": "arrow",
			"x": -211.52605664961015,
			"y": -152.43797061532757,
			"width": 1.4039667476986324,
			"height": 91.25783860040997,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 484728822,
			"version": 50,
			"versionNonce": 1900642666,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702828187806,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.4039667476986324,
					91.25783860040997
				]
			],
			"lastCommittedPoint": [
				1.4039667476986324,
				91.25783860040997
			],
			"startBinding": {
				"elementId": "YbM8aBtZ",
				"focus": 0.13586545282475482,
				"gap": 15.069366114162165
			},
			"endBinding": {
				"elementId": "g2KBNTm6",
				"focus": 0.21010520501970786,
				"gap": 6.3599154949590115
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Lr80h8X7b0F8xLnO_PB-A",
			"type": "arrow",
			"x": -212.9300233973088,
			"y": -151.03400386762894,
			"width": 551.7589318455556,
			"height": 88.44990510501282,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 1207366902,
			"version": 155,
			"versionNonce": 152467498,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702828217557,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-49.13883616945168,
					61.77453689873903
				],
				[
					-497.0042286853097,
					46.3309026740543
				],
				[
					-551.7589318455556,
					88.44990510501282
				]
			],
			"lastCommittedPoint": [
				-553.1628985932542,
				102.48957258199891
			],
			"startBinding": {
				"elementId": "YbM8aBtZ",
				"focus": -0.04707291321989712,
				"gap": 16.473332861860797
			},
			"endBinding": {
				"elementId": "TSQzaHSl",
				"focus": -0.07028843577289724,
				"gap": 4.1388615273281175
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "BB0nBEQP",
			"type": "text",
			"x": -300.1204627237208,
			"y": 360.73334227599133,
			"width": 390.4395751953125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1991729974,
			"version": 260,
			"versionNonce": 1759333430,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ei6VGqnauHgwsrhalpYVS",
					"type": "arrow"
				},
				{
					"id": "dfK9afiN1ay1oyFYS3Vc5",
					"type": "arrow"
				}
			],
			"updated": 1702828608155,
			"link": null,
			"locked": false,
			"text": "But what if half of my object is behind\nme and the other half is in front???",
			"rawText": "But what if half of my object is behind\nme and the other half is in front???",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "But what if half of my object is behind\nme and the other half is in front???",
			"lineHeight": 1.25
		},
		{
			"id": "gmUU2JgE",
			"type": "text",
			"x": -500.3119390539067,
			"y": 465.9192685188745,
			"width": 439.5688781738281,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 590392682,
			"version": 294,
			"versionNonce": 310685802,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "dfK9afiN1ay1oyFYS3Vc5",
					"type": "arrow"
				},
				{
					"id": "Wa1PIXaAqWxKZOCQILwJe",
					"type": "arrow"
				}
			],
			"updated": 1702828614621,
			"link": null,
			"locked": false,
			"text": "Firstly we Need to detect such objects\nand using homogeneous coordinates we can actually see\nthat a point at the view line goes to infinity and we\ncan detect that point of the line that intersects\nthe view plane",
			"rawText": "Firstly we Need to detect such objects\nand using homogeneous coordinates we can actually see\nthat a point at the view line goes to infinity and we\ncan detect that point of the line that intersects\nthe view plane",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "Firstly we Need to detect such objects\nand using homogeneous coordinates we can actually see\nthat a point at the view line goes to infinity and we\ncan detect that point of the line that intersects\nthe view plane",
			"lineHeight": 1.25
		},
		{
			"id": "eYXH0hglboEZbr3xREyQi",
			"type": "image",
			"x": -397.85189634109247,
			"y": 569.2624357041014,
			"width": 232.5703687855852,
			"height": 105.15664386144351,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2110438954,
			"version": 121,
			"versionNonce": 1765058742,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702828595492,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f28f688f89ecb2996525e33d9d73f79fb7b0ecd6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "dfK9afiN1ay1oyFYS3Vc5",
			"type": "arrow",
			"x": -135.03782258397553,
			"y": 424.1252731357347,
			"width": 104.96041011203386,
			"height": 38.45084330836886,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 1403175082,
			"version": 84,
			"versionNonce": 1063760490,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702828608159,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					21.823451607452625,
					28.058723495296192
				],
				[
					-56.117446990592384,
					27.019511513988903
				],
				[
					-83.13695850458123,
					38.45084330836886
				]
			],
			"lastCommittedPoint": [
				-83.13695850458123,
				38.45084330836886
			],
			"startBinding": {
				"elementId": "BB0nBEQP",
				"focus": 0.2794948071033714,
				"gap": 13.391930859743354
			},
			"endBinding": {
				"elementId": "gmUU2JgE",
				"focus": -0.18857236113308615,
				"gap": 3.343152074770984
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Wa1PIXaAqWxKZOCQILwJe",
			"type": "arrow",
			"x": -128.8025506961319,
			"y": 585.2031302383608,
			"width": 199.52870041099493,
			"height": 143.41125342040266,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 1572399734,
			"version": 106,
			"versionNonce": 1592503658,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702828696176,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					145.48967738301712,
					51.96059906536334
				],
				[
					124.70543775687179,
					-37.411631327061514
				],
				[
					199.52870041099493,
					-91.45065435503932
				]
			],
			"lastCommittedPoint": [
				199.52870041099493,
				-91.45065435503932
			],
			"startBinding": {
				"elementId": "gmUU2JgE",
				"focus": 0.1174866363063837,
				"gap": 19.283861719486225
			},
			"endBinding": {
				"elementId": "8HvkVrP3",
				"focus": 0.922778738521156,
				"gap": 13.757461090774314
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "8HvkVrP3",
			"type": "text",
			"x": 84.48361080563734,
			"y": 462.5761164441035,
			"width": 678.6253662109375,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1437729462,
			"version": 404,
			"versionNonce": 1084649514,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Wa1PIXaAqWxKZOCQILwJe",
					"type": "arrow"
				}
			],
			"updated": 1702828696176,
			"link": null,
			"locked": false,
			"text": "Then we cut the line into two segments, one with w= epsilon the other with w=-epsilon\nand we render each segment on its own using previous methodology such that\nthe one in front is rendered normally and the one at the back is culled",
			"rawText": "Then we cut the line into two segments, one with w= epsilon the other with w=-epsilon\nand we render each segment on its own using previous methodology such that\nthe one in front is rendered normally and the one at the back is culled",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Then we cut the line into two segments, one with w= epsilon the other with w=-epsilon\nand we render each segment on its own using previous methodology such that\nthe one in front is rendered normally and the one at the back is culled",
			"lineHeight": 1.25
		},
		{
			"id": "DISzDELF",
			"type": "text",
			"x": 85.27511745316485,
			"y": 535.320955135612,
			"width": 537.6490478515625,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 576987318,
			"version": 298,
			"versionNonce": 1215588278,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702828746135,
			"link": null,
			"locked": false,
			"text": "These two segments can never intersect at a finite point anymore!!\nthey only intersect at infinity as if they're both going the opposite\ndirection of each other to meet all the way around the world",
			"rawText": "These two segments can never intersect at a finite point anymore!!\nthey only intersect at infinity as if they're both going the opposite\ndirection of each other to meet all the way around the world",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "These two segments can never intersect at a finite point anymore!!\nthey only intersect at infinity as if they're both going the opposite\ndirection of each other to meet all the way around the world",
			"lineHeight": 1.25
		},
		{
			"id": "YFWJiYAW",
			"type": "text",
			"x": -215.8240656463663,
			"y": -119.30905131512259,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 382031478,
			"version": 2,
			"versionNonce": 1881785386,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702828187810,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "rvPWIYpoheqWJmz1KpIN0",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "qGLe_oyxyUG7FvH5qrd5x",
			"type": "line",
			"x": -214.33399014500742,
			"y": -153.8419373630262,
			"width": 568.6065328179391,
			"height": 88.4499051050127,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 236096694,
			"version": 200,
			"versionNonce": 2042616758,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702828204315,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-51.946769664848944,
					54.75470316024598
				],
				[
					-495.6002619376111,
					54.75470316024598
				],
				[
					-568.6065328179391,
					88.4499051050127
				]
			],
			"lastCommittedPoint": [
				-568.6065328179391,
				88.4499051050127
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "tnb3EkLJ",
			"type": "text",
			"x": -787.940515333552,
			"y": -65.3920322580135,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 35220150,
			"version": 2,
			"versionNonce": 2078162538,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702828196403,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "xOCY4ivU",
			"type": "text",
			"x": -501.0725781415011,
			"y": -103.8434364140094,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 777515190,
			"version": 2,
			"versionNonce": 1598572010,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702828211954,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "Lr80h8X7b0F8xLnO_PB-A",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "IxDtdDsW",
			"type": "text",
			"x": 4.279288307349589,
			"y": 581.9786516919955,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 132549750,
			"version": 2,
			"versionNonce": 1974939178,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702828616073,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "Wa1PIXaAqWxKZOCQILwJe",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#ffec99",
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
		"scrollX": 1125.6195207174287,
		"scrollY": 705.319497848039,
		"zoom": {
			"value": 0.5122675815785537
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