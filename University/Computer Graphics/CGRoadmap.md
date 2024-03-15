---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - parent
  - roadmap
  - ComputerGraphics
---
Parent of [[Computer Graphics/CookBook|CookBook]] and [[Final-Cookbook]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==

#roadmap
# Text Elements
Computer Graphics! ^I8ncHk0f

Mathematical Background ^W96E1tvd

Rasterization ^KEAAzOnh

Lighting and Shading ^hFs5031u

Representation
 ^cIGSOnwh

. How does the 'World' get into the Computer?


. how do we measure geometry?
 ^s4eQ52al

Transformations ^IOaWHOaW

. How do we control Geometry in the scene?

. How to combine different transformations?

. What is orientation? ^bpezGxlJ

Incidence Geometry ^o16dFJ3k

Clipping and Culling ^J92zzKvI

Visibility ^4ILb34Hn

Resterization ^FVzxnaiy

Lighting and Shading ^bg4waFI8

How can we find intersections of two objects? ^fDezc7nM

When do we clip objects? ^vJpuB59B

When do we cull objects? ^OsoCBSCs

What is rasterization? ^xsVBE498

How can we decide what to draw on each pixel? ^RdTxmWqS

How can we check the depth of two objects
that lie on the same pixel in 2D? ^X655h03C

What are the different types of lighting? ^yhVYadKO

How do we compute and simulate lighting on an object? ^9cdrK56u

Light and color ^M0cgp447

What is color? ^APvY3VaL

How do we decide and come up with color? ^xXep0RMt

Texturing ^JkdkPrVH

Animation ^GIl3sHDg

RayTracing ^5Q6yCvKe

Animation ^ULPv8a61

Simulation ^NKYDl6H0

Global Illumination ^m3N17Ww0

Ray Tracing ^ryVWyTM5

How do we texture common primitives? ^lJcEJBGL

What are textures? ^qiFpv1Xu

How can we simulate the effects of reflection and
refraction? ^zFPrhCFi

How do we make raytracing computationally feasible? ^u2Hr5AY5

How do we fix previous issues encountered by
raytracing? ^Q61wRumn

From intractable to approximations ^gn6GZFoT

How do we animate different parts of a body in
different ways? ^tQtxQQwD

How can we simulate phyiscal models governed by energy? ^SCMWsKHZ

Output Mapping ^QfPXYYd3

We now have an image, what can we do with it? ^kTAjnrlI

[[Representations]] ^cKWL0ema

[[Transformation]] ^XgPuLt2A

[[Incidence geometry]] ^we6y2Sjz

[[Clipping and Culling]] ^pZqpmxgY

[[Rasterization]] ^Ib3UEp2a

[[Visibility]] ^x1PvxgDA

[[Lighting and Shading]] ^i83Iw6LV

[[Lighting and Shading]] ^BuZVr7lr

[[Lighting and Shading]] ^tNI3N1PS

[[RayTracing]] ^r6BkOsS5

[[RayTracing]] ^FFgTvcpY

[[Animation]] ^RBYacjmr

[[Simulation]] ^tEfLqMHN

[[Output mapping]] ^P7OVQfE3

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"type": "rectangle",
			"version": 566,
			"versionNonce": 1412201560,
			"isDeleted": false,
			"id": "bvWzF6stu_D8oISf-TmpL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -84.18388918090159,
			"y": -740.4712931233686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1246.5663849428622,
			"height": 298.2720369396995,
			"seed": 947806051,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "I8ncHk0f"
				}
			],
			"updated": 1704892984074,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 596,
			"versionNonce": 808064296,
			"isDeleted": false,
			"id": "I8ncHk0f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 370.49325470654514,
			"y": -613.8352746535188,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 337.21209716796875,
			"height": 45,
			"seed": 1842180611,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Computer Graphics!",
			"rawText": "Computer Graphics!",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "bvWzF6stu_D8oISf-TmpL",
			"originalText": "Computer Graphics!",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "ellipse",
			"version": 410,
			"versionNonce": 1326133592,
			"isDeleted": false,
			"id": "V2nbi3b7Z6pyCuUYV-KUf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1104.1180524855665,
			"y": -308.85378888532955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 300.6399719436532,
			"height": 287.6252545434951,
			"seed": 1404027363,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "W96E1tvd"
				},
				{
					"id": "O4qzlBeKZmw915EyBl_cy",
					"type": "arrow"
				}
			],
			"updated": 1704892984074,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 1602039848,
			"isDeleted": false,
			"id": "W96E1tvd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1045.3607260550782,
			"y": -200.2320455776881,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 183.54075622558594,
			"height": 70,
			"seed": 924370285,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Mathematical\nBackground",
			"rawText": "Mathematical Background",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "V2nbi3b7Z6pyCuUYV-KUf",
			"originalText": "Mathematical Background",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "arrow",
			"version": 1000,
			"versionNonce": 512083898,
			"isDeleted": false,
			"id": "O4qzlBeKZmw915EyBl_cy",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -802.4791625027524,
			"y": -165.58878032522267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1174.4350536825978,
			"height": 17.756335409049626,
			"seed": 466883501,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "V2nbi3b7Z6pyCuUYV-KUf",
				"gap": 1,
				"focus": 0.012098806996471392
			},
			"endBinding": {
				"elementId": "69mbDzOPi8No2Zw9sCeVm",
				"gap": 1,
				"focus": 0.09851194293687622
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
					1174.4350536825978,
					-17.756335409049626
				]
			]
		},
		{
			"type": "ellipse",
			"version": 415,
			"versionNonce": 196406056,
			"isDeleted": false,
			"id": "69mbDzOPi8No2Zw9sCeVm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 372.3946297269672,
			"y": -327.81338484492545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 330.57382196401704,
			"height": 314.95616108382717,
			"seed": 2003610563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "O4qzlBeKZmw915EyBl_cy",
					"type": "arrow"
				},
				{
					"id": "iLDxDMcmbVEAfoMK75CRA",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "KEAAzOnh"
				}
			],
			"updated": 1704892984074,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 255,
			"versionNonce": 1723906904,
			"isDeleted": false,
			"id": "KEAAzOnh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 444.1036601634898,
			"y": -187.6891229424403,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 187.40476989746094,
			"height": 35,
			"seed": 1487030125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Rasterization",
			"rawText": "Rasterization",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "69mbDzOPi8No2Zw9sCeVm",
			"originalText": "Rasterization",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 1038,
			"versionNonce": 1536144250,
			"isDeleted": false,
			"id": "iLDxDMcmbVEAfoMK75CRA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 706.8508412955081,
			"y": -174.01709293286484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 1196.3810587260605,
			"height": 1.1271690054226156,
			"seed": 1687753389,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "69mbDzOPi8No2Zw9sCeVm",
				"gap": 3.926419485399805,
				"focus": -0.022367584353459907
			},
			"endBinding": {
				"elementId": "-CnQ5pJ_G78J8GNPPWNRN",
				"gap": 2.652409083920503,
				"focus": 0.018520095370555
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
					1196.3810587260605,
					-1.1271690054226156
				]
			]
		},
		{
			"type": "ellipse",
			"version": 476,
			"versionNonce": 1882876410,
			"isDeleted": false,
			"id": "-CnQ5pJ_G78J8GNPPWNRN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1905.8588185890933,
			"y": -332.42244701544365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 338.3826524041119,
			"height": 320.1620480438905,
			"seed": 568938605,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iLDxDMcmbVEAfoMK75CRA",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "hFs5031u"
				},
				{
					"id": "VD3W6-EfDxKeHHyWu8OKY",
					"type": "arrow"
				}
			],
			"updated": 1710508447978,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 2118163706,
			"isDeleted": false,
			"id": "hFs5031u",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1994.1614837503982,
			"y": -207.53580061870252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 161.50465393066406,
			"height": 70,
			"seed": 24492867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Lighting and\nShading",
			"rawText": "Lighting and Shading",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "-CnQ5pJ_G78J8GNPPWNRN",
			"originalText": "Lighting and Shading",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "line",
			"version": 128,
			"versionNonce": 35374424,
			"isDeleted": false,
			"id": "TNCpptZVcU62rZqkiXA-g",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -950.7968531172394,
			"y": -24.767754635231263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10,
			"height": 281.6741036878211,
			"seed": 1173404643,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-10,
					281.6741036878211
				]
			]
		},
		{
			"type": "diamond",
			"version": 586,
			"versionNonce": 309320744,
			"isDeleted": false,
			"id": "5Cjq_N5pgYgxbv6l7Dljj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1006.8165024244756,
			"y": 253.57301571925655,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.50007832107542,
			"height": 81.99271962099635,
			"seed": 1531786157,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1430,
			"versionNonce": 1915312728,
			"isDeleted": false,
			"id": "gO9uHVpVbKaazKUA3d9Ak",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1002.9854841482883,
			"y": 295.25197299308024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 400.1880628955888,
			"height": 224.34555711093032,
			"seed": 1675105123,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-349.276363404162,
					23.302769340129856
				],
				[
					-400.1880628955888,
					224.34555711093032
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1384,
			"versionNonce": 1076081338,
			"isDeleted": false,
			"id": "cKWL0ema",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1684.8056524626995,
			"y": 523.7842662920564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 608148205,
			"groupIds": [],
			"frameId": "z6wB6rmrWpI81GLVFyqiC",
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710508461934,
			"link": "[[Respresentations]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 1046,
			"versionNonce": 364662616,
			"isDeleted": false,
			"id": "cIGSOnwh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1527.5303955077875,
			"y": 526.2250856575395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 262.4040832519531,
			"height": 90,
			"seed": 880337379,
			"groupIds": [],
			"frameId": "z6wB6rmrWpI81GLVFyqiC",
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Representation\n",
			"rawText": "Representation\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Representation\n",
			"lineHeight": 1.25,
			"baseline": 77
		},
		{
			"type": "text",
			"version": 587,
			"versionNonce": 1853157928,
			"isDeleted": false,
			"id": "s4eQ52al",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1652.5971018754549,
			"y": 615.5873295810029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 456.49945068359375,
			"height": 125,
			"seed": 353468035,
			"groupIds": [],
			"frameId": "z6wB6rmrWpI81GLVFyqiC",
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984074,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": ". How does the 'World' get into the Computer?\n\n\n. how do we measure geometry?\n",
			"rawText": ". How does the 'World' get into the Computer?\n\n\n. how do we measure geometry?\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ". How does the 'World' get into the Computer?\n\n\n. how do we measure geometry?\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "frame",
			"version": 1043,
			"versionNonce": 758834513,
			"isDeleted": false,
			"id": "z6wB6rmrWpI81GLVFyqiC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1689.949606020501,
			"y": 521.5155139204762,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 590.8681699671798,
			"height": 240.56330263790173,
			"seed": 1119048259,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rk192JrqFpeKApFkdVLsi",
					"type": "arrow"
				}
			],
			"updated": 1708109398499,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": null
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 711224616,
			"isDeleted": false,
			"id": "9EH-tNEmTdQUVF0sDMwMB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -959.0283099378914,
			"y": 333.47042838417116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8,
			"height": 473.3333333333333,
			"seed": 1836444685,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3333333333330302,
					176
				],
				[
					-8,
					473.3333333333333
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1332,
			"versionNonce": 1849842008,
			"isDeleted": false,
			"id": "XgPuLt2A",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1252.8184413636789,
			"y": 808.1241961034669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 1655809219,
			"groupIds": [],
			"frameId": "rMkY5h8mVlI_qLkfoLEVi",
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": "[[Transformation]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 988,
			"versionNonce": 1353484328,
			"isDeleted": false,
			"id": "IOaWHOaW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1094.7098510754338,
			"y": 813.8983488022835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.0440979003906,
			"height": 45,
			"seed": 793121891,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Transformations",
			"rawText": "Transformations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Transformations",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 785,
			"versionNonce": 1146973784,
			"isDeleted": false,
			"id": "bpezGxlJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1219.7765574431012,
			"y": 903.260592725747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 432.17950439453125,
			"height": 125,
			"seed": 988516355,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": ". How do we control Geometry in the scene?\n\n. How to combine different transformations?\n\n. What is orientation?",
			"rawText": ". How do we control Geometry in the scene?\n\n. How to combine different transformations?\n\n. What is orientation?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ". How do we control Geometry in the scene?\n\n. How to combine different transformations?\n\n. What is orientation?",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "frame",
			"version": 922,
			"versionNonce": 1614025521,
			"isDeleted": false,
			"id": "rMkY5h8mVlI_qLkfoLEVi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1256.2957282548143,
			"y": 809.1887770652203,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 590.8681699671798,
			"height": 240.56330263790173,
			"seed": 396400547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rk192JrqFpeKApFkdVLsi",
					"type": "arrow"
				},
				{
					"id": "_F5WQd7u85ubAFSunz7IM",
					"type": "arrow"
				}
			],
			"updated": 1708109398499,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": null
		},
		{
			"type": "arrow",
			"version": 420,
			"versionNonce": 810410840,
			"isDeleted": false,
			"id": "rk192JrqFpeKApFkdVLsi",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1416.3616432712247,
			"y": 766.8037617175045,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 158.66666666666674,
			"height": 175.9999999999999,
			"seed": 1891924355,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "z6wB6rmrWpI81GLVFyqiC",
				"focus": 0.10633494482221854,
				"gap": 4.724945159126435
			},
			"endBinding": {
				"elementId": "rMkY5h8mVlI_qLkfoLEVi",
				"focus": -0.16794313783597037,
				"gap": 1.3992483497435728
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
					14.666666666666742,
					172
				],
				[
					158.66666666666674,
					175.9999999999999
				]
			]
		},
		{
			"type": "line",
			"version": 212,
			"versionNonce": 1642562136,
			"isDeleted": false,
			"id": "Kl7ZEntfQlIoSR3Czc_sM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -919.2433171528978,
			"y": 291.4646740438452,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 387.4999999999998,
			"height": 237.4999999999999,
			"seed": 2053269579,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					343.7499999999998,
					20
				],
				[
					387.4999999999998,
					237.4999999999999
				]
			]
		},
		{
			"type": "arrow",
			"version": 134,
			"versionNonce": 997554008,
			"isDeleted": false,
			"id": "_F5WQd7u85ubAFSunz7IM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -661.7433171528979,
			"y": 938.964674043845,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 195.49656058521845,
			"height": 175,
			"seed": 1170721259,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rMkY5h8mVlI_qLkfoLEVi",
				"focus": 0.15046225594248808,
				"gap": 3.6842411347366237
			},
			"endBinding": {
				"elementId": "we6y2Sjz",
				"focus": -0.2252521391043008,
				"gap": 3.0061225115725847
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
					184.9999999999999,
					-6.25
				],
				[
					195.49656058521845,
					-175
				]
			]
		},
		{
			"type": "line",
			"version": 251,
			"versionNonce": 453238824,
			"isDeleted": false,
			"id": "GzsmWDz7hXCheMHzI-16V",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 535.363882823925,
			"y": -13.454615585926263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 4,
			"height": 241.67410368782112,
			"seed": 326632709,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4,
					241.67410368782112
				]
			]
		},
		{
			"type": "diamond",
			"version": 706,
			"versionNonce": 1875351128,
			"isDeleted": false,
			"id": "yJcxAfp1wIJFdgTWHqcmc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 495.34423351668875,
			"y": 224.88615476856154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.50007832107542,
			"height": 81.99271962099635,
			"seed": 110828645,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1509,
			"versionNonce": 48601896,
			"isDeleted": false,
			"id": "L1MGgS77gPuegtt1ttFqj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 487.1752517928761,
			"y": 266.56511204238524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 396.1880628955888,
			"height": 248.34555711093032,
			"seed": 136595397,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-349.276363404162,
					23.302769340129856
				],
				[
					-396.1880628955888,
					248.34555711093032
				]
			]
		},
		{
			"type": "line",
			"version": 316,
			"versionNonce": 1009978200,
			"isDeleted": false,
			"id": "SXDW14V6RV0GT_UkGl8CY",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 586.9174187882666,
			"y": 264.7778130931502,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 387.4999999999998,
			"height": 237.4999999999999,
			"seed": 170985253,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					343.7499999999998,
					20
				],
				[
					387.4999999999998,
					237.4999999999999
				]
			]
		},
		{
			"type": "line",
			"version": 544,
			"versionNonce": 483915304,
			"isDeleted": false,
			"id": "Lv64DL0gmDW1lWan3Cn2k",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 540.2438111072709,
			"y": 305.1901587276155,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8,
			"height": 473.3333333333333,
			"seed": 1818247589,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3333333333330302,
					176
				],
				[
					-8,
					473.3333333333333
				]
			]
		},
		{
			"type": "arrow",
			"version": 431,
			"versionNonce": 896000088,
			"isDeleted": false,
			"id": "3tzLbLQqA1bVnfEiD_y4_",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 78.32524845363287,
			"y": 767.2934555793098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 158.66666666666674,
			"height": 175.9999999999999,
			"seed": 180715947,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pZqpmxgY",
				"focus": 0.2845037221989835,
				"gap": 6.940964653098149
			},
			"endBinding": {
				"elementId": "Ib3UEp2a",
				"focus": -0.40603705980219923,
				"gap": 2.358837900490869
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
					14.666666666666742,
					172
				],
				[
					158.66666666666674,
					175.9999999999999
				]
			]
		},
		{
			"type": "arrow",
			"version": 166,
			"versionNonce": 499577128,
			"isDeleted": false,
			"id": "uM5TCoxu0p0XR86vfaxaq",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 832.3536401608645,
			"y": 929.6958728064362,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 194.89874571006965,
			"height": 176.0536405618151,
			"seed": 137841579,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Ib3UEp2a",
				"focus": 0.3102045380869081,
				"gap": 9.791316087739517
			},
			"endBinding": {
				"elementId": "x1PvxgDA",
				"focus": -0.2829720491378128,
				"gap": 5.403987940830291
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
					184.9999999999999,
					-6.25
				],
				[
					194.89874571006965,
					-176.0536405618151
				]
			]
		},
		{
			"type": "line",
			"version": 312,
			"versionNonce": 993662296,
			"isDeleted": false,
			"id": "CcxK_ZmkNL3RmpIrFv8iT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2073.968247940466,
			"y": -20.50245005599615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 4,
			"height": 241.67410368782112,
			"seed": 1626315653,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4,
					241.67410368782112
				]
			]
		},
		{
			"type": "diamond",
			"version": 767,
			"versionNonce": 1025412136,
			"isDeleted": false,
			"id": "xxvsUH2yt62SXxqzqVvJt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2033.9485986332297,
			"y": 217.83832029849165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.50007832107542,
			"height": 81.99271962099635,
			"seed": 500949733,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1570,
			"versionNonce": 318614104,
			"isDeleted": false,
			"id": "T5cPWvJjB9T_BhiiZH1CM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2025.7796169094172,
			"y": 259.5172775723154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 396.1880628955888,
			"height": 248.34555711093032,
			"seed": 948452933,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-349.276363404162,
					23.302769340129856
				],
				[
					-396.1880628955888,
					248.34555711093032
				]
			]
		},
		{
			"type": "line",
			"version": 377,
			"versionNonce": 1691010856,
			"isDeleted": false,
			"id": "CSP0GFupUaz_5FiuyJO4P",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2125.5217839048078,
			"y": 257.72997862308034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 387.4999999999998,
			"height": 237.4999999999999,
			"seed": 668085669,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984075,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					343.7499999999998,
					20
				],
				[
					387.4999999999998,
					237.4999999999999
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1327,
			"versionNonce": 1450950822,
			"isDeleted": false,
			"id": "we6y2Sjz",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -817.6438993856262,
			"y": 524.1295267141475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 1781935179,
			"groupIds": [
				"DyKHhgLXylJ0_q49kXS2l"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "_F5WQd7u85ubAFSunz7IM",
					"type": "arrow"
				}
			],
			"updated": 1710506844498,
			"link": "[[Incidence geometry]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 815432890,
			"isDeleted": false,
			"id": "o16dFJ3k",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -687.993317152898,
			"y": 537.7146740438451,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 338.3641052246094,
			"height": 45,
			"seed": 1970699851,
			"groupIds": [
				"DyKHhgLXylJ0_q49kXS2l"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506844498,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Incidence Geometry",
			"rawText": "Incidence Geometry",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Incidence Geometry",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 533248998,
			"isDeleted": false,
			"id": "fDezc7nM",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -773.2470298786767,
			"y": 606.7702660723232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 453.9195251464844,
			"height": 25,
			"seed": 1194645494,
			"groupIds": [
				"DyKHhgLXylJ0_q49kXS2l"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506844498,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How can we find intersections of two objects?",
			"rawText": "How can we find intersections of two objects?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How can we find intersections of two objects?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 1424,
			"versionNonce": 1749123706,
			"isDeleted": false,
			"id": "pZqpmxgY",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.13409546405774,
			"y": 523.5234661080867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 1131270443,
			"groupIds": [
				"TkBhT6yWR7QJr1mJvbiFz"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "3tzLbLQqA1bVnfEiD_y4_",
					"type": "arrow"
				}
			],
			"updated": 1710506849709,
			"link": "[[Clipping and Culling]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 1483307558,
			"isDeleted": false,
			"id": "J92zzKvI",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0.6714070118266591,
			"y": 537.2620710912424,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 321.37213134765625,
			"height": 45,
			"seed": 137930059,
			"groupIds": [
				"TkBhT6yWR7QJr1mJvbiFz"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506849709,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Clipping and Culling",
			"rawText": "Clipping and Culling",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Clipping and Culling",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1486824250,
			"isDeleted": false,
			"id": "vJpuB59B",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -87.36467693750228,
			"y": 609.7114425429115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 240.45973205566406,
			"height": 25,
			"seed": 1394458090,
			"groupIds": [
				"TkBhT6yWR7QJr1mJvbiFz"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506849709,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "When do we clip objects?",
			"rawText": "When do we clip objects?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "When do we clip objects?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 1589855590,
			"isDeleted": false,
			"id": "OsoCBSCs",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -88.54114752573776,
			"y": 683.8290896017352,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 242.83973693847656,
			"height": 25,
			"seed": 1343471350,
			"groupIds": [
				"TkBhT6yWR7QJr1mJvbiFz"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506849709,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "When do we cull objects?",
			"rawText": "When do we cull objects?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "When do we cull objects?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 1391,
			"versionNonce": 1355835430,
			"isDeleted": false,
			"id": "Ib3UEp2a",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 239.35075302079053,
			"y": 781.6749812596021,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 57797003,
			"groupIds": [
				"9aQef3gIAg-i59BWdCysl"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "3tzLbLQqA1bVnfEiD_y4_",
					"type": "arrow"
				},
				{
					"id": "uM5TCoxu0p0XR86vfaxaq",
					"type": "arrow"
				}
			],
			"updated": 1710506855980,
			"link": "[[Rasterization]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 820385082,
			"isDeleted": false,
			"id": "FVzxnaiy",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 418.4491847896045,
			"y": 796.1509599801311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 236.62808227539062,
			"height": 45,
			"seed": 220485707,
			"groupIds": [
				"9aQef3gIAg-i59BWdCysl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506855980,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Resterization",
			"rawText": "Resterization",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Resterization",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 1209824102,
			"isDeleted": false,
			"id": "xsVBE498",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 278.8874239028386,
			"y": 852.7441222814732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 222.89971923828125,
			"height": 25,
			"seed": 965356650,
			"groupIds": [
				"9aQef3gIAg-i59BWdCysl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506855980,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What is rasterization?",
			"rawText": "What is rasterization?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is rasterization?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 748903930,
			"isDeleted": false,
			"id": "RdTxmWqS",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 274.1815415498975,
			"y": 937.4500046344142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 469.3795166015625,
			"height": 25,
			"seed": 627122922,
			"groupIds": [
				"9aQef3gIAg-i59BWdCysl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506855980,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How can we decide what to draw on each pixel?",
			"rawText": "How can we decide what to draw on each pixel?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How can we decide what to draw on each pixel?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 1354,
			"versionNonce": 904965434,
			"isDeleted": false,
			"id": "x1PvxgDA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 658.3949870486754,
			"y": 511.40921948566586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 120780837,
			"groupIds": [
				"eczk0MTjUklZe6I9cRrE0"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "uM5TCoxu0p0XR86vfaxaq",
					"type": "arrow"
				}
			],
			"updated": 1710506861729,
			"link": "[[Visibility]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1621580646,
			"isDeleted": false,
			"id": "4ILb34Hn",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 869.5602959007156,
			"y": 517.2620710912423,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 134.67604064941406,
			"height": 45,
			"seed": 1060232229,
			"groupIds": [
				"eczk0MTjUklZe6I9cRrE0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506861729,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Visibility",
			"rawText": "Visibility",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Visibility",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 1687877114,
			"isDeleted": false,
			"id": "X655h03C",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 685.0840371513643,
			"y": 578.2158503860855,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 432.53955078125,
			"height": 50,
			"seed": 1465977706,
			"groupIds": [
				"eczk0MTjUklZe6I9cRrE0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506861729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How can we check the depth of two objects\nthat lie on the same pixel in 2D?",
			"rawText": "How can we check the depth of two objects\nthat lie on the same pixel in 2D?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How can we check the depth of two objects\nthat lie on the same pixel in 2D?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 1329,
			"versionNonce": 1697836134,
			"isDeleted": false,
			"id": "i83Iw6LV",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1371.4113590813968,
			"y": 507.7658903505113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 539285957,
			"groupIds": [
				"dB6fl69_a1TeMTyYvSgCB"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "ppFbn-jqZhYSDgbJaq09e",
					"type": "arrow"
				}
			],
			"updated": 1710506868047,
			"link": "[[Lighting and Shading]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1829565690,
			"isDeleted": false,
			"id": "bg4waFI8",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1489.5602959007156,
			"y": 519.4842933134645,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 352.54815673828125,
			"height": 45,
			"seed": 2116959979,
			"groupIds": [
				"dB6fl69_a1TeMTyYvSgCB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506868047,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Lighting and Shading",
			"rawText": "Lighting and Shading",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lighting and Shading",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 69,
			"versionNonce": 1847881638,
			"isDeleted": false,
			"id": "yhVYadKO",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1401.3257623961306,
			"y": 590.6644467110862,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 407.79949951171875,
			"height": 25,
			"seed": 322490247,
			"groupIds": [
				"dB6fl69_a1TeMTyYvSgCB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506868047,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What are the different types of lighting?",
			"rawText": "What are the different types of lighting?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What are the different types of lighting?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 1213744570,
			"isDeleted": false,
			"id": "9cdrK56u",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1395.0099729224464,
			"y": 664.3486572374018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 538.3394775390625,
			"height": 25,
			"seed": 523687177,
			"groupIds": [
				"dB6fl69_a1TeMTyYvSgCB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506868047,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we compute and simulate lighting on an object?",
			"rawText": "How do we compute and simulate lighting on an object?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we compute and simulate lighting on an object?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 581,
			"versionNonce": 846213976,
			"isDeleted": false,
			"id": "7FXSCTOR0Kl3qvaU7ZxMV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2078.128970128052,
			"y": 288.68815378848745,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8,
			"height": 473.3333333333333,
			"seed": 1406533474,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984076,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.3333333333330302,
					176
				],
				[
					-8,
					473.3333333333333
				]
			]
		},
		{
			"type": "arrow",
			"version": 453,
			"versionNonce": 308366888,
			"isDeleted": false,
			"id": "ppFbn-jqZhYSDgbJaq09e",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1613.9405527701842,
			"y": 748.3837057940061,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 158.66666666666674,
			"height": 175.9999999999999,
			"seed": 1798892962,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984076,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "i83Iw6LV",
				"focus": 0.19720387112996338,
				"gap": 3.788790625369927
			},
			"endBinding": {
				"elementId": "BuZVr7lr",
				"focus": -0.3659275583518735,
				"gap": 11.85610979798173
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
					14.666666666666742,
					172
				],
				[
					158.66666666666674,
					175.9999999999999
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1447,
			"versionNonce": 2011936614,
			"isDeleted": false,
			"id": "BuZVr7lr",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1784.4633292348328,
			"y": 768.1034850474808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 719773090,
			"groupIds": [
				"p5OKRQsrPmZN5ZI27L1v2"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "ppFbn-jqZhYSDgbJaq09e",
					"type": "arrow"
				},
				{
					"id": "cBE5yInOIymrhDztSnFnB",
					"type": "arrow"
				}
			],
			"updated": 1710506872992,
			"link": "[[Lighting and Shading]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 274,
			"versionNonce": 391797242,
			"isDeleted": false,
			"id": "M0cgp447",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1934.2284276703133,
			"y": 774.5794637680098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 265.8240966796875,
			"height": 45,
			"seed": 658430306,
			"groupIds": [
				"p5OKRQsrPmZN5ZI27L1v2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506872992,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Light and color",
			"rawText": "Light and color",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Light and color",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 1703664294,
			"isDeleted": false,
			"id": "APvY3VaL",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1820.0000001168808,
			"y": 860.5059594026851,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 140.05982971191406,
			"height": 25,
			"seed": 379673890,
			"groupIds": [
				"p5OKRQsrPmZN5ZI27L1v2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506872992,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What is color?",
			"rawText": "What is color?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is color?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 215,
			"versionNonce": 1840319162,
			"isDeleted": false,
			"id": "xXep0RMt",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1819.2941177639398,
			"y": 923.8785084222928,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 412.03955078125,
			"height": 25,
			"seed": 1182623970,
			"groupIds": [
				"p5OKRQsrPmZN5ZI27L1v2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506872992,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we decide and come up with color?",
			"rawText": "How do we decide and come up with color?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we decide and come up with color?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 202,
			"versionNonce": 837797720,
			"isDeleted": false,
			"id": "cBE5yInOIymrhDztSnFnB",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2385.849873651182,
			"y": 920.1231421835427,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 194.89874571006965,
			"height": 176.0536405618151,
			"seed": 1584405837,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892984076,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "BuZVr7lr",
				"focus": 0.3435882506613296,
				"gap": 18.17497336401459
			},
			"endBinding": {
				"elementId": "tNI3N1PS",
				"focus": -0.2841181668703335,
				"gap": 10.950337264779591
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
					184.9999999999999,
					-6.25
				],
				[
					194.89874571006965,
					-176.0536405618151
				]
			]
		},
		{
			"type": "ellipse",
			"version": 605,
			"versionNonce": 1573494822,
			"isDeleted": false,
			"id": "MPQ95pL3MvNiEVQWPhWvW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 349.9975677269672,
			"y": 1375.5990867677774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 330.57382196401704,
			"height": 314.95616108382717,
			"seed": 1483330136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "GIl3sHDg"
				},
				{
					"id": "X26BWj9A_uoEuKJ0Eo2XW",
					"type": "arrow"
				},
				{
					"id": "nNs5w5p-PNtV3YVoj3-AF",
					"type": "arrow"
				}
			],
			"updated": 1710506762264,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 457,
			"versionNonce": 954945830,
			"isDeleted": false,
			"id": "GIl3sHDg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 453.150735736732,
			"y": 1515.7233486702626,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 124.51649475097656,
			"height": 35,
			"seed": 1294845784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506770111,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Animation",
			"rawText": "Animation",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "MPQ95pL3MvNiEVQWPhWvW",
			"originalText": "Animation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 1609,
			"versionNonce": 1102830138,
			"isDeleted": false,
			"id": "X26BWj9A_uoEuKJ0Eo2XW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1880.7599452210288,
			"y": 1529.3953786802685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#99e9f2",
			"width": 1196.3810633138512,
			"height": 1.1271690097448754,
			"seed": 1336613976,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ekNxCQzAww0JJryitBd2-",
				"gap": 2.7109183442928213,
				"focus": 0.009455963194929735
			},
			"endBinding": {
				"elementId": "MPQ95pL3MvNiEVQWPhWvW",
				"gap": 3.88263632384232,
				"focus": -0.03154894500721106
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
					-1196.3810633138512,
					-1.1271690097448754
				]
			]
		},
		{
			"type": "ellipse",
			"version": 664,
			"versionNonce": 698171578,
			"isDeleted": false,
			"id": "ekNxCQzAww0JJryitBd2-",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1883.461756589093,
			"y": 1370.9900245972594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 338.3826524041119,
			"height": 320.1620480438905,
			"seed": 565563736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "5Q6yCvKe"
				},
				{
					"id": "X26BWj9A_uoEuKJ0Eo2XW",
					"type": "arrow"
				},
				{
					"id": "VD3W6-EfDxKeHHyWu8OKY",
					"type": "arrow"
				}
			],
			"updated": 1710508447978,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 374,
			"versionNonce": 1260524474,
			"isDeleted": false,
			"id": "5Q6yCvKe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1976.8604376805738,
			"y": 1513.3766709940005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 151.3126220703125,
			"height": 35,
			"seed": 715253336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "RayTracing",
			"rawText": "RayTracing",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ekNxCQzAww0JJryitBd2-",
			"originalText": "RayTracing",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 435,
			"versionNonce": 1923410008,
			"isDeleted": false,
			"id": "GhZ1OYDaY4JuUBgnCDdtE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 512.966820823925,
			"y": 1689.9578560267767,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 4,
			"height": 241.67410368782112,
			"seed": 1594796120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4,
					241.67410368782112
				]
			]
		},
		{
			"type": "diamond",
			"version": 890,
			"versionNonce": 1536564568,
			"isDeleted": false,
			"id": "y_5BXxm1uWgbZWunjCss2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 472.94717151668874,
			"y": 1928.2986263812645,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.50007832107542,
			"height": 81.99271962099635,
			"seed": 348642648,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1693,
			"versionNonce": 1519956568,
			"isDeleted": false,
			"id": "QVIrdQByEtA_F014-YSap",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 464.7781897928762,
			"y": 1969.9775836550882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 396.1880628955888,
			"height": 248.34555711093032,
			"seed": 127038040,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-349.276363404162,
					23.302769340129856
				],
				[
					-396.1880628955888,
					248.34555711093032
				]
			]
		},
		{
			"type": "line",
			"version": 500,
			"versionNonce": 1719707480,
			"isDeleted": false,
			"id": "NK0g425X3GRZAkSuHEO7q",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 564.5203567882666,
			"y": 1968.1902847058532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 387.4999999999998,
			"height": 237.4999999999999,
			"seed": 1312974680,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					343.7499999999998,
					20
				],
				[
					387.4999999999998,
					237.4999999999999
				]
			]
		},
		{
			"type": "line",
			"version": 496,
			"versionNonce": 807811928,
			"isDeleted": false,
			"id": "as7mcV5fn1jSf1uxjsVk1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2051.571185940466,
			"y": 1682.9100215567069,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 4,
			"height": 241.67410368782112,
			"seed": 1225259864,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4,
					241.67410368782112
				]
			]
		},
		{
			"type": "diamond",
			"version": 951,
			"versionNonce": 594874456,
			"isDeleted": false,
			"id": "3BVYkPk2zd-jZ76tovhh9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2011.5515366332297,
			"y": 1921.2507919111947,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.50007832107542,
			"height": 81.99271962099635,
			"seed": 975097944,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1754,
			"versionNonce": 1344357720,
			"isDeleted": false,
			"id": "GpKe7lLWOhF1PAtKIrZH3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2003.3825549094172,
			"y": 1962.9297491850184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 396.1880628955888,
			"height": 248.34555711093032,
			"seed": 1804797272,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-349.276363404162,
					23.302769340129856
				],
				[
					-396.1880628955888,
					248.34555711093032
				]
			]
		},
		{
			"type": "line",
			"version": 561,
			"versionNonce": 1669257816,
			"isDeleted": false,
			"id": "Z-hDLmfXCjlhJJwJCHNlT",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2103.1247219048078,
			"y": 1961.1424502357834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 387.4999999999998,
			"height": 237.4999999999999,
			"seed": 716741208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704892987753,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					343.7499999999998,
					20
				],
				[
					387.4999999999998,
					237.4999999999999
				]
			]
		},
		{
			"type": "arrow",
			"version": 432,
			"versionNonce": 142115578,
			"isDeleted": false,
			"id": "VD3W6-EfDxKeHHyWu8OKY",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2248.1623936065544,
			"y": -184.31422807742365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 737.142924669819,
			"height": 1728.5714533915993,
			"seed": 1862180696,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "-CnQ5pJ_G78J8GNPPWNRN",
				"gap": 4.381482673574141,
				"focus": -0.3076246912098135
			},
			"endBinding": {
				"elementId": "ekNxCQzAww0JJryitBd2-",
				"gap": 6.867973598268804,
				"focus": 0.3398357016116437
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
					717.1428942194198,
					160.0000082720619
				],
				[
					702.8571799337051,
					1551.4285797006328
				],
				[
					-20.00003045039921,
					1728.5714533915993
				]
			]
		},
		{
			"type": "arrow",
			"version": 43,
			"versionNonce": 451104808,
			"isDeleted": false,
			"id": "d0ftBOK8kyYSyRG4oRl2M",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2185.9430944637807,
			"y": 2316.606415115273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 260,
			"height": 3.6363636363635123,
			"seed": 148419928,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704893087136,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "r6BkOsS5",
				"focus": 0.04603134254044772,
				"gap": 3.532263680142705
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
					-260,
					3.6363636363635123
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1490,
			"versionNonce": 677507578,
			"isDeleted": false,
			"id": "tNI3N1PS",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2211.8724201439236,
			"y": 496.29013953882304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 15012803,
			"groupIds": [
				"id-PvcpEnd64-_ejdsfNl"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "cBE5yInOIymrhDztSnFnB",
					"type": "arrow"
				}
			],
			"updated": 1710506878740,
			"link": "[[Lighting and Shading]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 346,
			"versionNonce": 2087305894,
			"isDeleted": false,
			"id": "JkdkPrVH",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2428.304185246071,
			"y": 497.76611825935197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 167.8680877685547,
			"height": 45,
			"seed": 859022179,
			"groupIds": [
				"id-PvcpEnd64-_ejdsfNl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506878740,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Texturing",
			"rawText": "Texturing",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Texturing",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 705012410,
			"isDeleted": false,
			"id": "lJcEJBGL",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2249.2388444733715,
			"y": 671.1004331926215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 369.53961181640625,
			"height": 25,
			"seed": 369046842,
			"groupIds": [
				"id-PvcpEnd64-_ejdsfNl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506878740,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we texture common primitives?",
			"rawText": "How do we texture common primitives?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we texture common primitives?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 480673254,
			"isDeleted": false,
			"id": "qiFpv1Xu",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2250.2388444733715,
			"y": 567.1004331926216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 198.1797637939453,
			"height": 25,
			"seed": 1372203110,
			"groupIds": [
				"id-PvcpEnd64-_ejdsfNl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506878740,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What are textures?",
			"rawText": "What are textures?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What are textures?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 1571,
			"versionNonce": 600912806,
			"isDeleted": false,
			"id": "r6BkOsS5",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2189.4753581439236,
			"y": 2199.702611151526,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 774985048,
			"groupIds": [
				"JkgJ92VEUCpPxzGpQMNCV"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "d0ftBOK8kyYSyRG4oRl2M",
					"type": "arrow"
				}
			],
			"updated": 1710506884543,
			"link": "[[RayTracing]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 551,
			"versionNonce": 600424890,
			"isDeleted": false,
			"id": "ryVWyTM5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2376.816214155162,
			"y": 2201.178589872055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 212.54408264160156,
			"height": 45,
			"seed": 621603416,
			"groupIds": [
				"JkgJ92VEUCpPxzGpQMNCV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506884543,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Ray Tracing",
			"rawText": "Ray Tracing",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ray Tracing",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 670551782,
			"isDeleted": false,
			"id": "zFPrhCFi",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2202.7215411221223,
			"y": 2260.864494512544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 502.3194885253906,
			"height": 50,
			"seed": 35204582,
			"groupIds": [
				"JkgJ92VEUCpPxzGpQMNCV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506884543,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How can we simulate the effects of reflection and\nrefraction?",
			"rawText": "How can we simulate the effects of reflection and\nrefraction?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How can we simulate the effects of reflection and\nrefraction?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1331526266,
			"isDeleted": false,
			"id": "u2Hr5AY5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2210.1439867449226,
			"y": 2367.8509213295315,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 518.7794189453125,
			"height": 25,
			"seed": 1772767590,
			"groupIds": [
				"JkgJ92VEUCpPxzGpQMNCV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506884543,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we make raytracing computationally feasible?",
			"rawText": "How do we make raytracing computationally feasible?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we make raytracing computationally feasible?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 1409,
			"versionNonce": 767848442,
			"isDeleted": false,
			"id": "FFgTvcpY",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1349.0142970813968,
			"y": 2211.1783619632142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 727089240,
			"groupIds": [
				"oreMCCd3WFO3gDDDti1f8"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710506888008,
			"link": "[[RayTracing]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 258,
			"versionNonce": 1391862950,
			"isDeleted": false,
			"id": "m3N17Ww0",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1467.1632339007156,
			"y": 2222.8967649261676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 323.0641174316406,
			"height": 45,
			"seed": 85119832,
			"groupIds": [
				"oreMCCd3WFO3gDDDti1f8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506888008,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Global Illumination",
			"rawText": "Global Illumination",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Global Illumination",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 443048122,
			"isDeleted": false,
			"id": "Q61wRumn",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1367.4643447917579,
			"y": 2284.792418270364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 446.79949951171875,
			"height": 50,
			"seed": 1733871098,
			"groupIds": [
				"oreMCCd3WFO3gDDDti1f8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506888008,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we fix previous issues encountered by\nraytracing?",
			"rawText": "How do we fix previous issues encountered by\nraytracing?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we fix previous issues encountered by\nraytracing?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 1733730278,
			"isDeleted": false,
			"id": "gn6GZFoT",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1370.0522497398622,
			"y": 2381.838853824273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 345.51959228515625,
			"height": 25,
			"seed": 1586280378,
			"groupIds": [
				"oreMCCd3WFO3gDDDti1f8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506888008,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "From intractable to approximations",
			"rawText": "From intractable to approximations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "From intractable to approximations",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 1434,
			"versionNonce": 1799143910,
			"isDeleted": false,
			"id": "RBYacjmr",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 635.9979250486754,
			"y": 2214.8216910983692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#96f2d7",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 48117336,
			"groupIds": [
				"N5POVvXxM4CM52jEqDYbC"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710506896127,
			"link": "[[Animation]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 89470842,
			"isDeleted": false,
			"id": "ULPv8a61",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 847.1632339007156,
			"y": 2220.674542703945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 160.09263610839844,
			"height": 45,
			"seed": 176376152,
			"groupIds": [
				"N5POVvXxM4CM52jEqDYbC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506896127,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Animation",
			"rawText": "Animation",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Animation",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 171,
			"versionNonce": 257398054,
			"isDeleted": false,
			"id": "tQtxQQwD",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 653.2025791149813,
			"y": 2282.2045133222587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 475.2994384765625,
			"height": 50,
			"seed": 638797370,
			"groupIds": [
				"N5POVvXxM4CM52jEqDYbC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506896127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we animate different parts of a body in\ndifferent ways?",
			"rawText": "How do we animate different parts of a body in\ndifferent ways?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we animate different parts of a body in\ndifferent ways?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 1547,
			"versionNonce": 1388538235,
			"isDeleted": false,
			"id": "tEfLqMHN",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -224.86449079739128,
			"y": 2226.9056346904867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 1937091416,
			"groupIds": [
				"oQHCNiTI-cTUKiFYpLXS9"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710506900870,
			"link": "[[Simulation]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 1016955686,
			"isDeleted": false,
			"id": "NKYDl6H0",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -27.584240846759258,
			"y": 2246.836158865562,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 171.46807861328125,
			"height": 45,
			"seed": 184573528,
			"groupIds": [
				"oQHCNiTI-cTUKiFYpLXS9"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506900870,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Simulation",
			"rawText": "Simulation",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Simulation",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 139209274,
			"isDeleted": false,
			"id": "SCMWsKHZ",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -212.45162602589477,
			"y": 2300.319847958989,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 556.2393798828125,
			"height": 25,
			"seed": 873562470,
			"groupIds": [
				"oQHCNiTI-cTUKiFYpLXS9"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506900870,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How can we simulate phyiscal models governed by energy?",
			"rawText": "How can we simulate phyiscal models governed by energy?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How can we simulate phyiscal models governed by energy?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 89,
			"versionNonce": 974475258,
			"isDeleted": false,
			"id": "nNs5w5p-PNtV3YVoj3-AF",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 340.0661382716486,
			"y": 1521.3604590000216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 534.4024296608133,
			"height": 3.8818578425723445,
			"seed": 1868008826,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710508447978,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MPQ95pL3MvNiEVQWPhWvW",
				"gap": 10.359949336900115,
				"focus": 0.06631800629076899
			},
			"endBinding": {
				"elementId": "P7OVQfE3",
				"gap": 5.5398099335363895,
				"focus": -0.0096660860730815
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
					-534.4024296608133,
					-3.8818578425723445
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1614,
			"versionNonce": 1832672358,
			"isDeleted": false,
			"id": "P7OVQfE3",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -783.0876723750356,
			"y": 1398.0707257568306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 583.2115710523345,
			"height": 236.82902481812488,
			"seed": 1151194810,
			"groupIds": [
				"S39GQ8s_IXPZLnkuSvaCx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "nNs5w5p-PNtV3YVoj3-AF",
					"type": "arrow"
				}
			],
			"updated": 1710506905443,
			"link": "[[Output mapping]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 1485997306,
			"isDeleted": false,
			"id": "QfPXYYd3",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -590.429255269921,
			"y": 1409.3799750079982,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 212.54888916015625,
			"height": 35,
			"seed": 759630246,
			"groupIds": [
				"S39GQ8s_IXPZLnkuSvaCx"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506905443,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Output Mapping",
			"rawText": "Output Mapping",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Output Mapping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 327147430,
			"isDeleted": false,
			"id": "kTAjnrlI",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -765.166097375184,
			"y": 1462.5378697448402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"width": 469.9795227050781,
			"height": 25,
			"seed": 75404902,
			"groupIds": [
				"S39GQ8s_IXPZLnkuSvaCx"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710506905443,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We now have an image, what can we do with it?",
			"rawText": "We now have an image, what can we do with it?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We now have an image, what can we do with it?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "Xrav1waO",
			"type": "text",
			"x": -1398.1998593071378,
			"y": 629.6987787011188,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": "z6wB6rmrWpI81GLVFyqiC",
			"roundness": null,
			"seed": 1905591334,
			"version": 2,
			"versionNonce": 223431546,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1710508461935,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "cKWL0ema",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "IzzbN5Oi",
			"type": "text",
			"x": -1398.1998593071378,
			"y": 629.6987787011188,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": "z6wB6rmrWpI81GLVFyqiC",
			"roundness": null,
			"seed": 275246394,
			"version": 2,
			"versionNonce": 1521012006,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1710508453701,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "cKWL0ema",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "ACayNiCL",
			"type": "text",
			"x": -1217.5506292108391,
			"y": 461.6530647715689,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c2255c",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 151534502,
			"version": 8,
			"versionNonce": 982929146,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1710508458456,
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
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#c2255c",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1670.8401028950495,
		"scrollY": 150.82637601790472,
		"zoom": {
			"value": 0.7600000000000001
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