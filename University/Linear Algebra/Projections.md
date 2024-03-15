---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - LinearAlgebra
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Vector projections ^v8P0DImW

How do we project a vector onto another?
and how do we project a point onto a line? ^Yb785mWJ

v ^SQfCloII

u ^sk60YExU

projection of u onto v ^OvwoeVVK

We know that the dot product of two vectors
u and v is in-fact just the length of v times the
length of the projection of u onto v ^5DZ10qJQ

We also know that the projection of u onto v
is just v scaled up or down, and thus we can get
the direction of v by normalizing it (setting
its magnitude to 1) and thus we are left with its
direction and the equation should look like
                c * normalized_v ^ljfqMuIH

We can use this information to formulate an equation ^PjoH8n0q

what about projecting a point ^S9qMx3hL

Projecting a point is quite easy, because a point
on a vector is just the magnitude without the direction
and thus we can completely get rid of the second component
leaving us with the dot product divided by the magnitude ^ZSNb49BD


# Embedded files
a805ff7d28b231e1607e7502b7f47a3963320a0b: $$\text{Projection of u} = c * v = \frac{u^Tv}{\|v\|} * \frac{v}{\|v\|} = \frac{u^Tv}{\|v\|^2}v$$

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
			"version": 171,
			"versionNonce": 1332915193,
			"isDeleted": false,
			"id": "v8P0DImW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -104.07371833790296,
			"y": -538.0368591689515,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 246.87705993652344,
			"height": 35,
			"seed": 1351825145,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703671791402,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Vector projections",
			"rawText": "Vector projections",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector projections",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"id": "Yb785mWJ",
			"type": "text",
			"x": -139.42846153538164,
			"y": -497.4629097278828,
			"width": 340.6726989746094,
			"height": 40,
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
			"seed": 1126316023,
			"version": 233,
			"versionNonce": 1477231833,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671791402,
			"link": null,
			"locked": false,
			"text": "How do we project a vector onto another?\nand how do we project a point onto a line?",
			"rawText": "How do we project a vector onto another?\nand how do we project a point onto a line?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "How do we project a vector onto another?\nand how do we project a point onto a line?",
			"lineHeight": 1.25
		},
		{
			"id": "zGwqGDinmFiNEmIInSTq5",
			"type": "arrow",
			"x": -606.6378235806313,
			"y": -250.57202245468528,
			"width": 236.88402820168005,
			"height": 149.82408621302835,
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
			"roundness": {
				"type": 2
			},
			"seed": 616732183,
			"version": 163,
			"versionNonce": 204356665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					236.88402820168005,
					-149.82408621302835
				]
			],
			"lastCommittedPoint": [
				236.88402820168005,
				-149.82408621302835
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "qcSKOOROEErbT-Z64G6mH",
			"type": "arrow",
			"x": -606.6378235806313,
			"y": -251.58434736153004,
			"width": 31.38207211218844,
			"height": 217.6498549716291,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 2108946007,
			"version": 179,
			"versionNonce": 1332497689,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					31.38207211218844,
					-217.6498549716291
				]
			],
			"lastCommittedPoint": [
				31.38207211218844,
				-217.6498549716291
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "4IngQDD8Qn7KMocmpYO-k",
			"type": "arrow",
			"x": -575.2557514684429,
			"y": -465.18490270577996,
			"width": 101.23249068447853,
			"height": 132.61456279666703,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 689633847,
			"version": 164,
			"versionNonce": 645218809,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					101.23249068447853,
					132.61456279666703
				]
			],
			"lastCommittedPoint": [
				101.23249068447853,
				132.61456279666703
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "6-nbgqmhmJyk9U83QZp2-",
			"type": "arrow",
			"x": -604.6131737669418,
			"y": -250.57202245468528,
			"width": 132.61456279666703,
			"height": 87.05994198865159,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 658128217,
			"version": 114,
			"versionNonce": 508336857,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					132.61456279666703,
					-87.05994198865159
				]
			],
			"lastCommittedPoint": [
				132.61456279666703,
				-87.05994198865159
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "SQfCloII",
			"type": "text",
			"x": -363.67984593788265,
			"y": -376.10031090343875,
			"width": 14.644058227539062,
			"height": 35,
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
			"seed": 645289431,
			"version": 84,
			"versionNonce": 1468389305,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"text": "v",
			"rawText": "v",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "v",
			"lineHeight": 1.25
		},
		{
			"id": "sk60YExU",
			"type": "text",
			"x": -643.0815202270437,
			"y": -408.49470792247195,
			"width": 15.904067993164062,
			"height": 35,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1599238455,
			"version": 83,
			"versionNonce": 340031641,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"text": "u",
			"rawText": "u",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "u",
			"lineHeight": 1.25
		},
		{
			"id": "OvwoeVVK",
			"type": "text",
			"x": -553.8830434919265,
			"y": -283.35630415181964,
			"width": 174.88034057617188,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 172967191,
			"version": 140,
			"versionNonce": 104594809,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"text": "projection of u onto v",
			"rawText": "projection of u onto v",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "projection of u onto v",
			"lineHeight": 1.25
		},
		{
			"id": "5DZ10qJQ",
			"type": "text",
			"x": -621.7040810495492,
			"y": -215.2381289376887,
			"width": 391.93682861328125,
			"height": 60,
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
			"seed": 408637657,
			"version": 357,
			"versionNonce": 1555031641,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VQtLGFh5OGGDzQ2vtxZwg",
					"type": "arrow"
				}
			],
			"updated": 1703671426249,
			"link": null,
			"locked": false,
			"text": "We know that the dot product of two vectors\nu and v is in-fact just the length of v times the\nlength of the projection of u onto v",
			"rawText": "We know that the dot product of two vectors\nu and v is in-fact just the length of v times the\nlength of the projection of u onto v",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "We know that the dot product of two vectors\nu and v is in-fact just the length of v times the\nlength of the projection of u onto v",
			"lineHeight": 1.25
		},
		{
			"id": "VQtLGFh5OGGDzQ2vtxZwg",
			"type": "arrow",
			"x": -476.41450116522617,
			"y": -144.69865038438797,
			"width": 0.23837431332657388,
			"height": 86.81781975790864,
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
			"seed": 1386835255,
			"version": 632,
			"versionNonce": 336673271,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703671642453,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.23837431332657388,
					86.81781975790864
				]
			],
			"lastCommittedPoint": [
				-0.9043522891448674,
				86.81781975790864
			],
			"startBinding": {
				"elementId": "5DZ10qJQ",
				"focus": 0.2590662570946113,
				"gap": 10.53947855330074
			},
			"endBinding": {
				"elementId": "ljfqMuIH",
				"focus": -0.24277346439249026,
				"gap": 10.852227469738523
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "ljfqMuIH",
			"type": "text",
			"x": -625.3214902061287,
			"y": -47.028603156740814,
			"width": 394.5447998046875,
			"height": 120,
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
			"seed": 753942105,
			"version": 479,
			"versionNonce": 131169207,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VQtLGFh5OGGDzQ2vtxZwg",
					"type": "arrow"
				},
				{
					"id": "GdsOOZFCZYzgQRwItDdYV",
					"type": "arrow"
				}
			],
			"updated": 1703671642451,
			"link": null,
			"locked": false,
			"text": "We also know that the projection of u onto v\nis just v scaled up or down, and thus we can get\nthe direction of v by normalizing it (setting\nits magnitude to 1) and thus we are left with its\ndirection and the equation should look like\n                c * normalized_v",
			"rawText": "We also know that the projection of u onto v\nis just v scaled up or down, and thus we can get\nthe direction of v by normalizing it (setting\nits magnitude to 1) and thus we are left with its\ndirection and the equation should look like\n                c * normalized_v",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "We also know that the projection of u onto v\nis just v scaled up or down, and thus we can get\nthe direction of v by normalizing it (setting\nits magnitude to 1) and thus we are left with its\ndirection and the equation should look like\n                c * normalized_v",
			"lineHeight": 1.25
		},
		{
			"id": "GdsOOZFCZYzgQRwItDdYV",
			"type": "arrow",
			"x": -222.04327982380175,
			"y": 16.32438984251135,
			"width": 297.59481370495575,
			"height": 94.100970830178,
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
			"seed": 1573707417,
			"version": 550,
			"versionNonce": 513429495,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703671646907,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					277.69906334376844,
					-5.474446493979741
				],
				[
					297.59481370495575,
					-94.100970830178
				]
			],
			"lastCommittedPoint": [
				139.27025252831163,
				-163.6877643352234
			],
			"startBinding": {
				"elementId": "ljfqMuIH",
				"focus": 0.116046798050055,
				"gap": 8.73341057763946
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "PjoH8n0q",
			"type": "text",
			"x": -193.94544828402059,
			"y": 28.223238911751473,
			"width": 308.0100554558402,
			"height": 14.38328419566353,
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
			"seed": 1516380055,
			"version": 355,
			"versionNonce": 1534491351,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671437226,
			"link": null,
			"locked": false,
			"text": "We can use this information to formulate an equation",
			"rawText": "We can use this information to formulate an equation",
			"fontSize": 11.506627356530824,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 9.999999999999998,
			"containerId": null,
			"originalText": "We can use this information to formulate an equation",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 289556023,
			"isDeleted": false,
			"id": "6OXthwV5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.94442178069806,
			"y": -149.8600728537409,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 383.54808048125824,
			"height": 47.36587740883008,
			"seed": 93273,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703671572744,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a805ff7d28b231e1607e7502b7f47a3963320a0b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "KUQFh3_fHkvEPmBwH0nNa",
			"type": "arrow",
			"x": 35.36111113501261,
			"y": -169.43763893837178,
			"width": 310.09301581193347,
			"height": 112.68168743588575,
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
			"seed": 610387929,
			"version": 120,
			"versionNonce": 2015853527,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1703671783687,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-112.68168743588575
				],
				[
					310.09301581193347,
					-110.934684529903
				]
			],
			"lastCommittedPoint": [
				310.09301581193347,
				-110.934684529903
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "ZSNb49BD",
				"focus": 0.15072787631453347,
				"gap": 17.47002905982717
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "S9qMx3hL",
			"type": "text",
			"x": 44.96962711791764,
			"y": -321.4268917588688,
			"width": 236.2885284423828,
			"height": 20,
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
			"seed": 516404823,
			"version": 79,
			"versionNonce": 1875813529,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1703671717521,
			"link": null,
			"locked": false,
			"text": "what about projecting a point",
			"rawText": "what about projecting a point",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "what about projecting a point",
			"lineHeight": 1.25
		},
		{
			"id": "ZSNb49BD",
			"type": "text",
			"x": 362.9241560067732,
			"y": -312.6918772289552,
			"width": 479.0728759765625,
			"height": 80,
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
			"seed": 1688146521,
			"version": 300,
			"versionNonce": 1066920183,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "KUQFh3_fHkvEPmBwH0nNa",
					"type": "arrow"
				}
			],
			"updated": 1703671783687,
			"link": null,
			"locked": false,
			"text": "Projecting a point is quite easy, because a point\non a vector is just the magnitude without the direction\nand thus we can completely get rid of the second component\nleaving us with the dot product divided by the magnitude",
			"rawText": "Projecting a point is quite easy, because a point\non a vector is just the magnitude without the direction\nand thus we can completely get rid of the second component\nleaving us with the dot product divided by the magnitude",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Projecting a point is quite easy, because a point\non a vector is just the magnitude without the direction\nand thus we can completely get rid of the second component\nleaving us with the dot product divided by the magnitude",
			"lineHeight": 1.25
		},
		{
			"id": "JGGP6RPn",
			"type": "text",
			"x": 31.361103505618075,
			"y": -292.1193263742575,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1139032633,
			"version": 2,
			"versionNonce": 295531831,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1703671705580,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "KUQFh3_fHkvEPmBwH0nNa",
			"originalText": "",
			"lineHeight": 1.25
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
		"scrollX": 877.2332280143258,
		"scrollY": 813.5463862630598,
		"zoom": {
			"value": 0.7706875334360888
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