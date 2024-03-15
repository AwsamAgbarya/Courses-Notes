---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - Subject
  - ComputerGraphics
---
Child of [[CGRoadmap]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Rasterization ^MU8xv2io

What is a Raster and what is Rasterization? ^jpFXyA2P

a raster represents a two-dimensional picture as a
rectangular matrix or grid of square pixels.
Rasterization is The process of identifying the pixels
covered by a triangle (or other primitives). ^KxDBhVBG

Drawing pixels ^4mqj9PEa

Visibility/Occlusion ^Gs5Wvxkl

Shading ^zI0jNrs3

Texturing ^ZBzpA3I4

Lets start with the simplest Primitive... a Line! ^gTvdxqTW

Lets consider a line ( going from one vertex to another)

y = ax + b ^iI8k6S6O

we reduce all cases down to 0 < a < 1 ^gHoHwLjP

Why's that? ^7ObdZYgJ

a = 1 ^EfswXxjN

a < 0 ^kxwmW5Hm

a > 1 ^Dwb8M2Fu

Flip y sign ^DPWDjdf6

Switch x and y ^8Cke0bxc

0 < a < 1 ^kfeTvn9D

Naive Solution ^euoO0Miv

Iterate over integer xi

compute y = axi + b

Draw pixel at ( x , round (y) ) ^xVhD09wO

We practically never skip
over x, we just go over
them one by one and then
decide whether to stay on
the same y level or go up
and that decision is based
off of whether y is closer 
to the upper or lower
pixel ^vGkrxDrg

Bresenham's algorithm ^M2IlOEZP

We consider a more computationally efficient algorithm that only deals with constants!
The main idea is 'What pixel center is closest to my real value?' ^GW1NEVBW

We introduce a constant E into our calculations
E's sign will indicate whether we have to go up or not with our y value
x value will always increment with whole numbers ^BkVRVTCc

E = a - 1/2

for i ... n :
    if E is positive:
        E = E + a - 1
    else:
        E = E + a ^6kTWy66o

If a is relatively high (Closer to 1)
we draw our next pixel up
else we continue in a straight line ^KZDuydlo

If we already went up by 1 and our E is positive
and we add a positive value a to it, it will always 
be positive, thus we need to reduce it by 1 and
calculate ^RPQ5k7V2

We can improve this even more
by avoiding division and multiplying
everything by 2 delta x  ^wmM9CZhA

1. What about Rasterization of polygons? ^aIVC7f9A

We can use a scanline algorithm that scans a line
horizontally down the polygon and intersects it with the
polygon and only draws pixels when a parity bit is odd
parity bit starts at 0 and increases each intersection ^qxCUZT2H

2. What about Rasterization of Triangles?? ^T1nbMfHh

We can define each vertex as a line that seperates
pixels into two half spaces, assuming all normals point inward
we only draw pixels that are contained in all positive half spaces
aka their distances are all positive ^L5b75CVZ

There are a lot of strategies on how to traverse
the pixels since we do not want to go over every single pixel
one of which is edge tracing which turns around after we encounter
a pixel that is not drawn inside the triangle! ^CXSdbHIc

* Sometimes triangles are too deformed to bother
   drawing them such as triangles smaller 
   than pixels or triangles that are practically just
   just a straight line. ^7jnFAKel

* We form pixels in a heirarchial matter
   of ecosystems that way we do not have
   to check every single pixel every single time
 ^pLRg6jFW

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"id": "dYZNb5hsAjTRo8On0NkQB",
			"type": "ellipse",
			"x": -239,
			"y": -416.2578125,
			"width": 467,
			"height": 208,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 1384397482,
			"version": 43,
			"versionNonce": 2111476714,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "MU8xv2io"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false
		},
		{
			"id": "MU8xv2io",
			"type": "text",
			"x": -126.08347820686356,
			"y": -334.79691774340097,
			"width": 240.94808959960938,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2101580918,
			"version": 24,
			"versionNonce": 1371043766,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Rasterization",
			"rawText": "Rasterization",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 32,
			"containerId": "dYZNb5hsAjTRo8On0NkQB",
			"originalText": "Rasterization",
			"lineHeight": 1.25
		},
		{
			"id": "jpFXyA2P",
			"type": "text",
			"x": -319,
			"y": -192.2578125,
			"width": 638.1226806640625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1286992950,
			"version": 121,
			"versionNonce": 502564522,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "What is a Raster and what is Rasterization?",
			"rawText": "What is a Raster and what is Rasterization?",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "What is a Raster and what is Rasterization?",
			"lineHeight": 1.25
		},
		{
			"id": "KxDBhVBG",
			"type": "text",
			"x": -307,
			"y": -158.2578125,
			"width": 528.2593383789062,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 430226474,
			"version": 89,
			"versionNonce": 1316753654,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "a raster represents a two-dimensional picture as a\nrectangular matrix or grid of square pixels.\nRasterization is The process of identifying the pixels\ncovered by a triangle (or other primitives).",
			"rawText": "a raster represents a two-dimensional picture as a\nrectangular matrix or grid of square pixels.\nRasterization is The process of identifying the pixels\ncovered by a triangle (or other primitives).",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "a raster represents a two-dimensional picture as a\nrectangular matrix or grid of square pixels.\nRasterization is The process of identifying the pixels\ncovered by a triangle (or other primitives).",
			"lineHeight": 1.25
		},
		{
			"id": "4mqj9PEa",
			"type": "text",
			"x": -385.86890885143515,
			"y": -41.0975409959284,
			"width": 135.99984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 653095914,
			"version": 90,
			"versionNonce": 1942102378,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bNF-aIx5_6qoQrx0V4dV8",
					"type": "arrow"
				},
				{
					"id": "hlk-SCM--xRpEvISOy8Sn",
					"type": "arrow"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Drawing pixels",
			"rawText": "Drawing pixels",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Drawing pixels",
			"lineHeight": 1.25
		},
		{
			"id": "Gs5Wvxkl",
			"type": "text",
			"x": -164.84727350836215,
			"y": -39.42945318201845,
			"width": 171.69979858398438,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 388509098,
			"version": 119,
			"versionNonce": 972718646,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bNF-aIx5_6qoQrx0V4dV8",
					"type": "arrow"
				},
				{
					"id": "IIydb4m_JQHX6FxvNR57b",
					"type": "arrow"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Visibility/Occlusion",
			"rawText": "Visibility/Occlusion",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Visibility/Occlusion",
			"lineHeight": 1.25
		},
		{
			"id": "zI0jNrs3",
			"type": "text",
			"x": 84.53185467118078,
			"y": -40.26349708897345,
			"width": 70.49992370605469,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 59412266,
			"version": 104,
			"versionNonce": 1519281194,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "IIydb4m_JQHX6FxvNR57b",
					"type": "arrow"
				},
				{
					"id": "o7qZHW6_RoJeA1dEth2ZN",
					"type": "arrow"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Shading",
			"rawText": "Shading",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Shading",
			"lineHeight": 1.25
		},
		{
			"id": "ZBzpA3I4",
			"type": "text",
			"x": 231.32358229525937,
			"y": -40.919995325628236,
			"width": 93.25990295410156,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 205333674,
			"version": 133,
			"versionNonce": 655936374,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "o7qZHW6_RoJeA1dEth2ZN",
					"type": "arrow"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Texturing",
			"rawText": "Texturing",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Texturing",
			"lineHeight": 1.25
		},
		{
			"id": "bNF-aIx5_6qoQrx0V4dV8",
			"type": "arrow",
			"x": -241.20609797464317,
			"y": -26.715004303686868,
			"width": 71.47322348546516,
			"height": 1.8444702834958662,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 1016989290,
			"version": 120,
			"versionNonce": 205803242,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					43.345051662153026,
					-0.46111757087396654
				],
				[
					71.47322348546516,
					1.3833527126218996
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "4mqj9PEa",
				"focus": 0.20403970378796046,
				"gap": 8.662963464682605
			},
			"endBinding": {
				"elementId": "Gs5Wvxkl",
				"focus": -0.41631979911957995,
				"gap": 4.885600980815866
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "IIydb4m_JQHX6FxvNR57b",
			"type": "arrow",
			"x": 11.48633086429163,
			"y": -24.870534020191002,
			"width": 69.62875320196923,
			"height": 0.9222351417479331,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 201587958,
			"version": 140,
			"versionNonce": 68938934,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					49.80069765438856,
					0.46111757087396654
				],
				[
					69.62875320196923,
					0.9222351417479331
				]
			],
			"lastCommittedPoint": [
				69.62875320196923,
				0.9222351417479331
			],
			"startBinding": {
				"elementId": "Gs5Wvxkl",
				"focus": 0.09184773733085327,
				"gap": 4.633805788669406
			},
			"endBinding": {
				"elementId": "zI0jNrs3",
				"focus": -0.353941979943376,
				"gap": 3.4167706049199182
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "o7qZHW6_RoJeA1dEth2ZN",
			"type": "arrow",
			"x": 161.34954139833116,
			"y": -24.016042024095345,
			"width": 68.7065180602213,
			"height": 0.6192796831842244,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 695892202,
			"version": 192,
			"versionNonce": 1299112362,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					39.095207015939195,
					-0.26229464913084044
				],
				[
					68.7065180602213,
					0.356985034053384
				]
			],
			"lastCommittedPoint": [
				68.7065180602213,
				2.7667054252438277
			],
			"startBinding": {
				"elementId": "zI0jNrs3",
				"focus": 0.3161260377078188,
				"gap": 6.317763021095686
			},
			"endBinding": {
				"elementId": "ZBzpA3I4",
				"focus": -0.42764837817814483,
				"gap": 1.2675228367069167
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "hlk-SCM--xRpEvISOy8Sn",
			"type": "arrow",
			"x": -326.6607886387171,
			"y": -5.236919725684459,
			"width": 317.9926230495986,
			"height": 139.17557580777128,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 859894134,
			"version": 318,
			"versionNonce": 782820854,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					72.683502555882,
					87.57048500708675
				],
				[
					297.8392770048989,
					82.98459511985811
				],
				[
					317.9926230495986,
					139.17557580777128
				]
			],
			"lastCommittedPoint": [
				389.68865828153616,
				150.62123421218922
			],
			"startBinding": {
				"elementId": "4mqj9PEa",
				"focus": 0.35956805844344386,
				"gap": 10.86062127024394
			},
			"endBinding": {
				"elementId": "gTvdxqTW",
				"focus": 0.04375244907181985,
				"gap": 10.647852337827715
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "gTvdxqTW",
			"type": "text",
			"x": -245.38445587599648,
			"y": 144.58650841991454,
			"width": 469.1194763183594,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2135105654,
			"version": 165,
			"versionNonce": 423173226,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "hlk-SCM--xRpEvISOy8Sn",
					"type": "arrow"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Lets start with the simplest Primitive... a Line!",
			"rawText": "Lets start with the simplest Primitive... a Line!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Lets start with the simplest Primitive... a Line!",
			"lineHeight": 1.25
		},
		{
			"id": "iI8k6S6O",
			"type": "text",
			"x": -231.9721157258499,
			"y": 184.42377815410975,
			"width": 446.89691162109375,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 666113078,
			"version": 120,
			"versionNonce": 130332470,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "Lets consider a line ( going from one vertex to another)\n\ny = ax + b",
			"rawText": "Lets consider a line ( going from one vertex to another)\n\ny = ax + b",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Lets consider a line ( going from one vertex to another)\n\ny = ax + b",
			"lineHeight": 1.25
		},
		{
			"id": "gHoHwLjP",
			"type": "text",
			"x": -182.5233404789451,
			"y": 255.7622039224828,
			"width": 311.4886474609375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1527561898,
			"version": 100,
			"versionNonce": 1299054378,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-tgGhtXhLz7PLPaQgAJFo",
					"type": "arrow"
				}
			],
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"text": "we reduce all cases down to 0 < a < 1",
			"rawText": "we reduce all cases down to 0 < a < 1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "we reduce all cases down to 0 < a < 1",
			"lineHeight": 1.25
		},
		{
			"id": "Sn61ToflDdY8BOkT4-sWo",
			"type": "freedraw",
			"x": 70.27315608349986,
			"y": 269.0774147752921,
			"width": 6.237228600515877,
			"height": 3.3336911485516225,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1759137014,
			"version": 49,
			"versionNonce": 131358838,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784631,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.43015369658729696,
					0
				],
				[
					0.8603073931745939,
					0.10753842414686687
				],
				[
					1.1829226656150666,
					0.32261527244048693
				],
				[
					1.6130763622023778,
					0.5376921207341638
				],
				[
					1.8281532104960263,
					0.6452305448809739
				],
				[
					2.043230058789675,
					0.8603073931745939
				],
				[
					2.2583069070833233,
					0.9678458173214608
				],
				[
					2.3658453312301475,
					1.0753842414682708
				],
				[
					2.58092217952381,
					1.1829226656150809
				],
				[
					2.6884606036706344,
					1.290461089761891
				],
				[
					2.903537451964283,
					1.3979995139087578
				],
				[
					3.1186143002579314,
					1.5055379380555678
				],
				[
					3.2261527244047556,
					1.6130763622023778
				],
				[
					3.33369114855158,
					1.6130763622023778
				],
				[
					3.441229572698404,
					1.7206147863492447
				],
				[
					3.6563064209920526,
					1.8281532104960547
				],
				[
					3.6563064209920526,
					1.9356916346428648
				],
				[
					3.8713832692857153,
					2.043230058789675
				],
				[
					3.9789216934325395,
					2.1507684829365417
				],
				[
					4.086460117579364,
					2.2583069070833517
				],
				[
					4.193998541726188,
					2.3658453312301617
				],
				[
					4.4090753900198365,
					2.4733837553770286
				],
				[
					4.516613814166661,
					2.4733837553770286
				],
				[
					4.624152238313485,
					2.5809221795238386
				],
				[
					4.731690662460309,
					2.5809221795238386
				],
				[
					4.8392290866071335,
					2.5809221795238386
				],
				[
					4.8392290866071335,
					2.6884606036706487
				],
				[
					4.946767510753972,
					2.6884606036706487
				],
				[
					5.054305934900796,
					2.6884606036706487
				],
				[
					5.16184435904762,
					2.7959990278174587
				],
				[
					5.269382783194445,
					2.9035374519642687
				],
				[
					5.376921207341269,
					2.9035374519642687
				],
				[
					5.484459631488093,
					3.0110758761111356
				],
				[
					5.591998055634917,
					3.1186143002579456
				],
				[
					5.699536479781742,
					3.2261527244047556
				],
				[
					5.807074903928566,
					3.2261527244047556
				],
				[
					5.91461332807539,
					3.3336911485516225
				],
				[
					6.022151752222214,
					3.3336911485516225
				],
				[
					6.129690176369039,
					3.3336911485516225
				],
				[
					6.237228600515877,
					3.3336911485516225
				],
				[
					6.237228600515877,
					3.3336911485516225
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				6.237228600515877,
				3.3336911485516225
			]
		},
		{
			"id": "wvDXASGmJqq5CO-Nf3prj",
			"type": "freedraw",
			"x": 106.08345132439273,
			"y": 269.61510689602625,
			"width": 6.667382297103188,
			"height": 3.5487679968452426,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 534821558,
			"version": 41,
			"versionNonce": 1450740202,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.10753842414682424,
					0
				],
				[
					0.32261527244048693,
					0
				],
				[
					0.6452305448809597,
					0
				],
				[
					1.1829226656150809,
					0
				],
				[
					1.613076362202392,
					0
				],
				[
					1.9356916346428648,
					0.10753842414681003
				],
				[
					2.2583069070833375,
					0.21507684829362006
				],
				[
					2.473383755376986,
					0.3226152724404301
				],
				[
					2.6884606036706487,
					0.537692120734107
				],
				[
					3.0110758761111214,
					0.8603073931745939
				],
				[
					3.4412295726984183,
					1.075384241468214
				],
				[
					3.656306420992067,
					1.1829226656150809
				],
				[
					3.8713832692857153,
					1.290461089761891
				],
				[
					4.086460117579378,
					1.397999513908701
				],
				[
					4.3015369658730265,
					1.6130763622023778
				],
				[
					4.516613814166675,
					1.7206147863491879
				],
				[
					4.731690662460323,
					1.8281532104959979
				],
				[
					4.946767510753972,
					1.9356916346428648
				],
				[
					5.054305934900796,
					2.150768482936485
				],
				[
					5.269382783194459,
					2.365845331230105
				],
				[
					5.376921207341283,
					2.580922179523782
				],
				[
					5.591998055634932,
					2.688460603670592
				],
				[
					5.699536479781756,
					2.9035374519642687
				],
				[
					5.80707490392858,
					3.0110758761110787
				],
				[
					6.0221517522222285,
					3.1186143002578888
				],
				[
					6.129690176369053,
					3.3336911485515657
				],
				[
					6.237228600515877,
					3.3336911485515657
				],
				[
					6.344767024662701,
					3.3336911485515657
				],
				[
					6.344767024662701,
					3.4412295726983757
				],
				[
					6.45230544880954,
					3.5487679968452426
				],
				[
					6.559843872956364,
					3.5487679968452426
				],
				[
					6.667382297103188,
					3.5487679968452426
				],
				[
					6.667382297103188,
					3.5487679968452426
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				6.667382297103188,
				3.5487679968452426
			]
		},
		{
			"id": "-tgGhtXhLz7PLPaQgAJFo",
			"type": "arrow",
			"x": 137.8817079932025,
			"y": 267.68816103936297,
			"width": 218.45476239621865,
			"height": 154.19346089523657,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 4002922,
			"version": 256,
			"versionNonce": 1386013110,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					188.24424806083687,
					16.684461292482638
				],
				[
					152.5697813363069,
					-130.72672214070417
				],
				[
					218.45476239621865,
					-137.50899960275393
				]
			],
			"lastCommittedPoint": [
				218.45476239621865,
				-137.50899960275393
			],
			"startBinding": {
				"elementId": "gHoHwLjP",
				"focus": -0.5321915540200531,
				"gap": 8.916401011210098
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7ObdZYgJ",
			"type": "text",
			"x": 226.60742639872512,
			"y": 262.1395628715703,
			"width": 92.40020751953125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2049246954,
			"version": 77,
			"versionNonce": 1533263018,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "Why's that?",
			"rawText": "Why's that?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Why's that?",
			"lineHeight": 1.25
		},
		{
			"id": "bH9CR3JpA3ELKRPLXhZJ6",
			"type": "line",
			"x": 501.1887129228912,
			"y": 45.27642478071131,
			"width": 2.8918536051038473,
			"height": 207.8003376238907,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 1255471722,
			"version": 125,
			"versionNonce": 1262697206,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8918536051038473,
					207.8003376238907
				]
			],
			"lastCommittedPoint": [
				2.8918536051038473,
				207.8003376238907
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "oCNyzYmWGypkC5KgWaP4B",
			"type": "line",
			"x": 377.6652517905984,
			"y": 149.79627650803607,
			"width": 252.83062947479345,
			"height": 0.41312194358624765,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
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
			"seed": 952760426,
			"version": 182,
			"versionNonce": 1775933290,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					252.83062947479345,
					0.41312194358624765
				]
			],
			"lastCommittedPoint": [
				297.4477993821099,
				2.0656097179313235
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "HXL52-FP2Lp_34O_5eyid",
			"type": "line",
			"x": 502.35730033482656,
			"y": 149.00640604980347,
			"width": 126.78394877763589,
			"height": 104.46283103509438,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
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
			"seed": 1157421878,
			"version": 135,
			"versionNonce": 676097078,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					126.78394877763589,
					-104.46283103509438
				]
			],
			"lastCommittedPoint": [
				144.34322806843528,
				-39.58278213010699
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "EfswXxjN",
			"type": "text",
			"x": 628.9390143145935,
			"y": 28.174755336845294,
			"width": 40.880096435546875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1633533878,
			"version": 33,
			"versionNonce": 573053482,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "a = 1",
			"rawText": "a = 1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "a = 1",
			"lineHeight": 1.25
		},
		{
			"id": "kxwmW5Hm",
			"type": "text",
			"x": 599.8065122400811,
			"y": 229.95765972942075,
			"width": 47.360107421875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 169433386,
			"version": 126,
			"versionNonce": 127759734,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "2k6zq1KGFZ91qHhtXwa6M",
					"type": "arrow"
				}
			],
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "a < 0",
			"rawText": "a < 0",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "a < 0",
			"lineHeight": 1.25
		},
		{
			"id": "7YaDevEj7EmdwJ3lGc_fG",
			"type": "line",
			"x": 503.5477599477621,
			"y": 151.68494017890845,
			"width": 104.7604459383283,
			"height": 72.91565129230236,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#d0bfff",
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
			"seed": 336511146,
			"version": 69,
			"versionNonce": 1664566506,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					104.7604459383283,
					72.91565129230236
				]
			],
			"lastCommittedPoint": [
				104.7604459383283,
				72.91565129230236
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "TO1crAYoT8LBdzDKhGxix",
			"type": "line",
			"x": 503.5477599477621,
			"y": 147.8159464368679,
			"width": 54.46352729180137,
			"height": 106.54613535773157,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
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
			"seed": 233553386,
			"version": 60,
			"versionNonce": 41637558,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					54.46352729180137,
					-106.54613535773157
				]
			],
			"lastCommittedPoint": [
				54.46352729180137,
				-106.54613535773157
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Dwb8M2Fu",
			"type": "text",
			"x": 540.1153209232134,
			"y": 22.222457272167546,
			"width": 38.76808166503906,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 960948906,
			"version": 26,
			"versionNonce": 1989351338,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "8t7O8PdQHkwlF-nidJsI-",
					"type": "arrow"
				}
			],
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "a > 1",
			"rawText": "a > 1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "a > 1",
			"lineHeight": 1.25
		},
		{
			"id": "2k6zq1KGFZ91qHhtXwa6M",
			"type": "arrow",
			"x": 609.2446255631671,
			"y": 214.7657392104546,
			"width": 45.60160984773029,
			"height": 72.20254892557276,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1542623350,
			"version": 220,
			"versionNonce": 1099632630,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					43.1586664630305,
					-48.858867693996615
				],
				[
					45.60160984773029,
					-72.20254892557276
				]
			],
			"lastCommittedPoint": [
				45.60160984773029,
				-72.20254892557276
			],
			"startBinding": {
				"elementId": "kxwmW5Hm",
				"focus": -1.1224546819205985,
				"gap": 15.191920518966157
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "DPWDjdf6",
			"type": "text",
			"x": 649.1632906366981,
			"y": 178.39302659381266,
			"width": 45.99589538574219,
			"height": 12.128293538189423,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1138229546,
			"version": 71,
			"versionNonce": 1013355114,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "Flip y sign",
			"rawText": "Flip y sign",
			"fontSize": 9.702634830551538,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 8,
			"containerId": null,
			"originalText": "Flip y sign",
			"lineHeight": 1.25
		},
		{
			"id": "8t7O8PdQHkwlF-nidJsI-",
			"type": "arrow",
			"x": 583.4580009468912,
			"y": 7.929865972535609,
			"width": 115.08977723474754,
			"height": 77.35987384882799,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1791657066,
			"version": 170,
			"versionNonce": 282173750,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					92.56041046473808,
					-12.486155077354695
				],
				[
					115.08977723474754,
					46.415924309296784
				],
				[
					112.91827200390333,
					64.87371877147329
				]
			],
			"lastCommittedPoint": [
				112.91827200390333,
				64.87371877147329
			],
			"startBinding": {
				"elementId": "Dwb8M2Fu",
				"focus": -1.6695104718886788,
				"gap": 14.292591299631937
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "8Cke0bxc",
			"type": "text",
			"x": 624.9562359855566,
			"y": -18.128196797595926,
			"width": 67.79132080078125,
			"height": 11.741631807388924,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1890499114,
			"version": 87,
			"versionNonce": 1467790634,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "Switch x and y",
			"rawText": "Switch x and y",
			"fontSize": 9.393305445911139,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 7,
			"containerId": null,
			"originalText": "Switch x and y",
			"lineHeight": 1.25
		},
		{
			"id": "qnb6EvQFmSKzihqttX-bE",
			"type": "line",
			"x": 504.7062882432567,
			"y": 147.72121147586762,
			"width": 128.66196144900061,
			"height": 49.80463023832277,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#d0bfff",
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
			"seed": 1268453174,
			"version": 52,
			"versionNonce": 1941178998,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					128.66196144900061,
					-49.80463023832277
				]
			],
			"lastCommittedPoint": [
				128.66196144900061,
				-49.80463023832277
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "kfeTvn9D",
			"type": "text",
			"x": 617.803740553814,
			"y": 105.62444067919006,
			"width": 58.93864440917969,
			"height": 15.256701882064476,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 691978422,
			"version": 72,
			"versionNonce": 1497399274,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "0 < a < 1",
			"rawText": "0 < a < 1",
			"fontSize": 12.205361505651581,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 10,
			"containerId": null,
			"originalText": "0 < a < 1",
			"lineHeight": 1.25
		},
		{
			"id": "euoO0Miv",
			"type": "text",
			"x": -613.1941111745522,
			"y": 321.88984928218355,
			"width": 193.14480590820312,
			"height": 35,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 593573418,
			"version": 303,
			"versionNonce": 955730870,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "M21qzQH9wBFR3Yi6wnJSs",
					"type": "arrow"
				}
			],
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "Naive Solution",
			"rawText": "Naive Solution",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Naive Solution",
			"lineHeight": 1.25
		},
		{
			"id": "xVhD09wO",
			"type": "text",
			"x": -641.6209619963191,
			"y": 370.70455732455304,
			"width": 242.9445037841797,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 978055402,
			"version": 259,
			"versionNonce": 1841099434,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"text": "Iterate over integer xi\n\ncompute y = axi + b\n\nDraw pixel at ( x , round (y) )",
			"rawText": "Iterate over integer xi\n\ncompute y = axi + b\n\nDraw pixel at ( x , round (y) )",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "Iterate over integer xi\n\ncompute y = axi + b\n\nDraw pixel at ( x , round (y) )",
			"lineHeight": 1.25
		},
		{
			"id": "q-Jfu0OYuMGYmMFfAQOiE",
			"type": "rectangle",
			"x": -662.0685814826201,
			"y": 483.21058068928767,
			"width": 278.80030357954183,
			"height": 198.37713908544322,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1501609782,
			"version": 153,
			"versionNonce": 247489782,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false
		},
		{
			"id": "pY0D0UeAYm6X1GXADqgJO",
			"type": "line",
			"x": -628.6620362312253,
			"y": 484.44786014304316,
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 505415222,
			"version": 183,
			"versionNonce": 127733098,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			],
			"lastCommittedPoint": [
				1.2372794537553773,
				199.20199205461347
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 230,
			"versionNonce": 378820150,
			"isDeleted": false,
			"id": "o6Ek8QOt-Y9gcKc_m4D0p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -593.3995717991975,
			"y": 482.1795144778248,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 33776886,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784632,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 196,
			"versionNonce": 204197930,
			"isDeleted": false,
			"id": "imQ8EcT6l97-IKSKu6upA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -557.1060411557067,
			"y": 483.8292204161654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1502139062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 241,
			"versionNonce": 2035818358,
			"isDeleted": false,
			"id": "Lji__dMcOaq0dnDzKhhkK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -519.9876575430458,
			"y": 483.0043674469954,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1731307190,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 245,
			"versionNonce": 2136226538,
			"isDeleted": false,
			"id": "n2UtbK_6rhriS_3U4vDZk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -483.69412689955504,
			"y": 484.24164690075054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 391021366,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 222,
			"versionNonce": 2068889782,
			"isDeleted": false,
			"id": "t4nAmB11SG35Vlq_6tAmj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -449.05030219440516,
			"y": 484.24164690075054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1964420342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 221,
			"versionNonce": 799100330,
			"isDeleted": false,
			"id": "sEbUBZhxLK-KfqeiMgTYF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -416.05618342759533,
			"y": 482.179514477825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 264089782,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"id": "RXxVnbB5othcWrEbmdIq0",
			"type": "line",
			"x": -383.90097155385706,
			"y": 511.3405904119152,
			"width": 279.70686826140786,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 531868138,
			"version": 191,
			"versionNonce": 270744054,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			],
			"lastCommittedPoint": [
				-279.70686826140786,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 267,
			"versionNonce": 1648232554,
			"isDeleted": false,
			"id": "8E1hyBbEJBLBee3lqT9xl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -382.8268284345737,
			"y": 542.7055694949918,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 294973738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 260,
			"versionNonce": 1859423030,
			"isDeleted": false,
			"id": "Bh97D_My-K8TaV5VizGaj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -382.3971711868603,
			"y": 571.9222623395012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 457894506,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 272,
			"versionNonce": 2130012970,
			"isDeleted": false,
			"id": "jEpL8aWcIgU8NBdlnsEjJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -383.6861429300003,
			"y": 603.2872414225777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 1643271594,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 245,
			"versionNonce": 633975926,
			"isDeleted": false,
			"id": "yvR451gQEeD5nmJFvfeH0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -384.54545742542723,
			"y": 634.2225632579409,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 1374296554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 276,
			"versionNonce": 1009939946,
			"isDeleted": false,
			"id": "Ew-fqCrCSnW-dpC1AJxl8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -383.256485682287,
			"y": 659.1426836253164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 2095305706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"id": "j3L_Ussy3B-gAGZzoKabd",
			"type": "line",
			"x": -615.7224300977773,
			"y": 647.4902950803672,
			"width": 213.64373590291405,
			"height": 93.77260567329608,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 945127286,
			"version": 252,
			"versionNonce": 135618166,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784633,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					213.64373590291405,
					-93.77260567329608
				]
			],
			"lastCommittedPoint": [
				207.87778280326143,
				-91.64830716289782
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "vGkrxDrg",
			"type": "text",
			"x": -367.3414042310303,
			"y": 486.34707950586807,
			"width": 213.15243530273438,
			"height": 180,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 198020598,
			"version": 488,
			"versionNonce": 894331882,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "LPEa3nTH80ee2xsFIj88D",
					"type": "arrow"
				}
			],
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "We practically never skip\nover x, we just go over\nthem one by one and then\ndecide whether to stay on\nthe same y level or go up\nand that decision is based\noff of whether y is closer \nto the upper or lower\npixel",
			"rawText": "We practically never skip\nover x, we just go over\nthem one by one and then\ndecide whether to stay on\nthe same y level or go up\nand that decision is based\noff of whether y is closer \nto the upper or lower\npixel",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 174,
			"containerId": null,
			"originalText": "We practically never skip\nover x, we just go over\nthem one by one and then\ndecide whether to stay on\nthe same y level or go up\nand that decision is based\noff of whether y is closer \nto the upper or lower\npixel",
			"lineHeight": 1.25
		},
		{
			"id": "6DS5l9GfJhWm5n6Fb0hoS",
			"type": "freedraw",
			"x": -610.8668906454383,
			"y": 650.8284784538503,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1667589226,
			"version": 112,
			"versionNonce": 1577983926,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "cH7fe6jBq961AXdHY5WVY",
			"type": "freedraw",
			"x": -571.4156325951843,
			"y": 624.7299538975283,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 244647082,
			"version": 112,
			"versionNonce": 1764581034,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "-BRsHMJg4Io4DYv49phxM",
			"type": "freedraw",
			"x": -539.2476837234386,
			"y": 615.3223462086216,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 26053866,
			"version": 112,
			"versionNonce": 299677942,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "1Te9BsT0ZplVFvlAMM3cL",
			"type": "freedraw",
			"x": -497.065184731244,
			"y": 594.6863035361811,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 387448106,
			"version": 112,
			"versionNonce": 304085354,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "8pOux3zV1QSzlfbeRrAkz",
			"type": "freedraw",
			"x": -463.37987978064245,
			"y": 581.6370412580201,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1386042730,
			"version": 112,
			"versionNonce": 453388854,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "uyKXjBFGKuLsA6B8Y1bR1",
			"type": "freedraw",
			"x": -425.7494490250157,
			"y": 564.0357107432914,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 606508458,
			"version": 112,
			"versionNonce": 527514666,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "_vJVO4fvLFQDt5ATSpw77",
			"type": "freedraw",
			"x": -398.1335683898377,
			"y": 554.9315742701558,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 744275434,
			"version": 112,
			"versionNonce": 946828150,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
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
			"id": "LPEa3nTH80ee2xsFIj88D",
			"type": "arrow",
			"x": -131.7840873727971,
			"y": 517.5912416426644,
			"width": 397.1299043844799,
			"height": 1.3674240118264152,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2137353462,
			"version": 149,
			"versionNonce": 1594631914,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					397.1299043844799,
					-1.3674240118264152
				]
			],
			"lastCommittedPoint": [
				383.939080255873,
				-1.3059152389655537
			],
			"startBinding": {
				"elementId": "vGkrxDrg",
				"focus": -0.6452769347096259,
				"gap": 22.404881555498832
			},
			"endBinding": {
				"elementId": "6kTWy66o",
				"focus": 0.8539462904882891,
				"gap": 31.406998440470744
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "M2IlOEZP",
			"type": "text",
			"x": 405.07874758099683,
			"y": 332.0897689366947,
			"width": 299.32122802734375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1946913590,
			"version": 63,
			"versionNonce": 73241782,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "Bresenham's algorithm",
			"rawText": "Bresenham's algorithm",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Bresenham's algorithm",
			"lineHeight": 1.25
		},
		{
			"id": "GW1NEVBW",
			"type": "text",
			"x": 244.35577965638834,
			"y": 374.0033037563875,
			"width": 687.3134155273438,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1629291574,
			"version": 354,
			"versionNonce": 695974314,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "We consider a more computationally efficient algorithm that only deals with constants!\nThe main idea is 'What pixel center is closest to my real value?'",
			"rawText": "We consider a more computationally efficient algorithm that only deals with constants!\nThe main idea is 'What pixel center is closest to my real value?'",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "We consider a more computationally efficient algorithm that only deals with constants!\nThe main idea is 'What pixel center is closest to my real value?'",
			"lineHeight": 1.25
		},
		{
			"id": "BkVRVTCc",
			"type": "text",
			"x": 314.2115002188066,
			"y": 425.82514811183677,
			"width": 562.8170776367188,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1508678634,
			"version": 275,
			"versionNonce": 141921782,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "We introduce a constant E into our calculations\nE's sign will indicate whether we have to go up or not with our y value\nx value will always increment with whole numbers",
			"rawText": "We introduce a constant E into our calculations\nE's sign will indicate whether we have to go up or not with our y value\nx value will always increment with whole numbers",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "We introduce a constant E into our calculations\nE's sign will indicate whether we have to go up or not with our y value\nx value will always increment with whole numbers",
			"lineHeight": 1.25
		},
		{
			"id": "6kTWy66o",
			"type": "text",
			"x": 296.7528154521536,
			"y": 503.28096304103894,
			"width": 218.77967834472656,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 388965098,
			"version": 309,
			"versionNonce": 233501802,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "LPEa3nTH80ee2xsFIj88D",
					"type": "arrow"
				},
				{
					"id": "IO5VCiLjDULYxzfZtUJVZ",
					"type": "arrow"
				}
			],
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "E = a - 1/2\n\nfor i ... n :\n    if E is positive:\n        E = E + a - 1\n    else:\n        E = E + a",
			"rawText": "E = a - 1/2\n\nfor i ... n :\n    if E is positive:\n        E = E + a - 1\n    else:\n        E = E + a",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 168,
			"containerId": null,
			"originalText": "E = a - 1/2\n\nfor i ... n :\n    if E is positive:\n        E = E + a - 1\n    else:\n        E = E + a",
			"lineHeight": 1.25
		},
		{
			"id": "zrbJqbKVODPvjsk9czMKm",
			"type": "arrow",
			"x": 425.00495900612816,
			"y": 520.9188465400309,
			"width": 140.88673087707184,
			"height": 15.308383659965784,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 214662390,
			"version": 408,
			"versionNonce": 1371299638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					121.4293743372051,
					12.766413438874906
				],
				[
					140.88673087707184,
					15.308383659965784
				]
			],
			"lastCommittedPoint": [
				143.39948118550137,
				15.735346796752765
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "KZDuydlo",
				"focus": -0.6112397290088061,
				"gap": 10.739433022679805
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "KZDuydlo",
			"type": "text",
			"x": 576.6311229058798,
			"y": 512.5320681233111,
			"width": 167.7190704345703,
			"height": 36.44983192412899,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 311762986,
			"version": 246,
			"versionNonce": 2116343594,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "zrbJqbKVODPvjsk9czMKm",
					"type": "arrow"
				}
			],
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "If a is relatively high (Closer to 1)\nwe draw our next pixel up\nelse we continue in a straight line",
			"rawText": "If a is relatively high (Closer to 1)\nwe draw our next pixel up\nelse we continue in a straight line",
			"fontSize": 9.719955179767732,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 32,
			"containerId": null,
			"originalText": "If a is relatively high (Closer to 1)\nwe draw our next pixel up\nelse we continue in a straight line",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 709,
			"versionNonce": 77006966,
			"isDeleted": false,
			"id": "IO5VCiLjDULYxzfZtUJVZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 528.8025102432093,
			"y": 612.4363398025401,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 90.20431471692768,
			"height": 0.9270373580116029,
			"seed": 1220911286,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6kTWy66o",
				"focus": 0.22988258806991554,
				"gap": 13.270016446329265
			},
			"endBinding": {
				"elementId": "RPQ5k7V2",
				"focus": -0.21504878151264858,
				"gap": 10.533519577153925
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
					67.65651773681395,
					0.7052119584133152
				],
				[
					90.20431471692768,
					0.9270373580116029
				]
			]
		},
		{
			"type": "text",
			"version": 531,
			"versionNonce": 2056544746,
			"isDeleted": false,
			"id": "RPQ5k7V2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.25966775533842,
			"x": 629.4652044671592,
			"y": 584.276363511452,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.8077392578125,
			"height": 48.59977589883866,
			"seed": 485736554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IO5VCiLjDULYxzfZtUJVZ",
					"type": "arrow"
				}
			],
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"fontSize": 9.719955179767732,
			"fontFamily": 1,
			"text": "If we already went up by 1 and our E is positive\nand we add a positive value a to it, it will always \nbe positive, thus we need to reduce it by 1 and\ncalculate",
			"rawText": "If we already went up by 1 and our E is positive\nand we add a positive value a to it, it will always \nbe positive, thus we need to reduce it by 1 and\ncalculate",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we already went up by 1 and our E is positive\nand we add a positive value a to it, it will always \nbe positive, thus we need to reduce it by 1 and\ncalculate",
			"lineHeight": 1.25,
			"baseline": 44
		},
		{
			"id": "xn1w7ewa7yAl3TrjCCn3t",
			"type": "freedraw",
			"x": 750.3485972131012,
			"y": 502.2677205517317,
			"width": 142.5425894494041,
			"height": 124.89025639065426,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1852810358,
			"version": 134,
			"versionNonce": 1892321718,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.5304666117499437,
					0.8826166529374859
				],
				[
					7.50224154996863,
					1.3239249794062289
				],
				[
					10.591399835249831,
					3.0891582852812007
				],
				[
					13.239249794062289,
					5.2956999176249155
				],
				[
					14.563174773468518,
					6.619624897031144
				],
				[
					15.00448309993726,
					7.943549876437373
				],
				[
					15.445791426406004,
					10.150091508781088
				],
				[
					15.887099752874747,
					11.91532481465606
				],
				[
					15.887099752874747,
					14.121866446999775
				],
				[
					15.887099752874747,
					15.887099752874747
				],
				[
					15.887099752874747,
					17.65233305874972
				],
				[
					15.445791426406004,
					19.41756636462469
				],
				[
					14.563174773468518,
					22.065416323437148
				],
				[
					14.121866446999775,
					23.83064962931212
				],
				[
					13.239249794062289,
					26.478499588124578
				],
				[
					13.239249794062289,
					28.685041220468293
				],
				[
					12.797941467593546,
					30.891582852812007
				],
				[
					12.797941467593546,
					33.539432811624465
				],
				[
					12.797941467593546,
					35.30466611749944
				],
				[
					12.797941467593546,
					37.06989942337441
				],
				[
					13.680558120531032,
					38.83513272924938
				],
				[
					14.121866446999775,
					40.60036603512435
				],
				[
					15.00448309993726,
					41.48298268806184
				],
				[
					15.887099752874747,
					43.24821599393681
				],
				[
					16.769716405812233,
					43.68952432040555
				],
				[
					18.09364138521846,
					44.57214097334304
				],
				[
					19.858874691093433,
					45.454757626280525
				],
				[
					20.300183017562176,
					45.454757626280525
				],
				[
					21.624107996968405,
					45.89606595274927
				],
				[
					22.50672464990589,
					45.89606595274927
				],
				[
					23.389341302843377,
					46.33737427921801
				],
				[
					24.271957955780863,
					46.33737427921801
				],
				[
					24.713266282249606,
					46.33737427921801
				],
				[
					26.037191261655835,
					46.33737427921801
				],
				[
					26.478499588124578,
					46.33737427921801
				],
				[
					26.91980791459332,
					46.33737427921801
				],
				[
					27.361116241062064,
					46.33737427921801
				],
				[
					28.24373289399955,
					46.33737427921801
				],
				[
					28.685041220468293,
					46.778682605686754
				],
				[
					29.126349546937035,
					46.778682605686754
				],
				[
					30.00896619987452,
					47.2199909321555
				],
				[
					30.450274526343264,
					47.2199909321555
				],
				[
					30.891582852812007,
					47.2199909321555
				],
				[
					31.33289117928075,
					47.2199909321555
				],
				[
					31.774199505749493,
					47.2199909321555
				],
				[
					32.215507832218236,
					47.2199909321555
				],
				[
					31.774199505749493,
					47.66129925862424
				],
				[
					30.891582852812007,
					48.10260758509298
				],
				[
					30.450274526343264,
					48.98522423803047
				],
				[
					30.450274526343264,
					49.42653256449921
				],
				[
					30.00896619987452,
					50.75045754390544
				],
				[
					29.56765787340578,
					51.63307419684293
				],
				[
					29.126349546937035,
					52.956999176249155
				],
				[
					29.126349546937035,
					53.83961582918664
				],
				[
					29.126349546937035,
					55.16354080859287
				],
				[
					29.126349546937035,
					56.046157461530356
				],
				[
					29.126349546937035,
					57.81139076740533
				],
				[
					29.126349546937035,
					59.13531574681156
				],
				[
					29.126349546937035,
					60.01793239974904
				],
				[
					29.56765787340578,
					60.90054905268653
				],
				[
					29.56765787340578,
					61.783165705624015
				],
				[
					30.450274526343264,
					62.22447403209276
				],
				[
					30.891582852812007,
					63.10709068503024
				],
				[
					31.774199505749493,
					63.54839901149899
				],
				[
					32.65681615868698,
					63.98970733796773
				],
				[
					33.539432811624465,
					64.43101566443647
				],
				[
					34.863357791030694,
					65.31363231737396
				],
				[
					36.18728277043692,
					65.31363231737396
				],
				[
					37.952516076311895,
					65.7549406438427
				],
				[
					39.71774938218687,
					65.7549406438427
				],
				[
					41.041674361593095,
					65.7549406438427
				],
				[
					42.365599340999324,
					65.7549406438427
				],
				[
					43.68952432040555,
					65.7549406438427
				],
				[
					45.454757626280525,
					65.7549406438427
				],
				[
					46.778682605686754,
					65.7549406438427
				],
				[
					48.98522423803047,
					65.7549406438427
				],
				[
					50.75045754390544,
					65.7549406438427
				],
				[
					52.51569084978041,
					65.7549406438427
				],
				[
					54.280924155655384,
					65.31363231737396
				],
				[
					56.4874657879991,
					64.87232399090522
				],
				[
					58.694007420342814,
					64.87232399090522
				],
				[
					60.459240726217786,
					64.43101566443647
				],
				[
					61.783165705624015,
					64.43101566443647
				],
				[
					63.10709068503024,
					64.43101566443647
				],
				[
					64.87232399090522,
					64.43101566443647
				],
				[
					67.07886562324893,
					64.87232399090522
				],
				[
					68.8440989291239,
					64.87232399090522
				],
				[
					71.9332572144051,
					65.31363231737396
				],
				[
					73.69849052028007,
					65.31363231737396
				],
				[
					75.90503215262379,
					65.31363231737396
				],
				[
					78.1115737849675,
					65.7549406438427
				],
				[
					80.75942374377996,
					65.7549406438427
				],
				[
					86.93774031434236,
					66.19624897031144
				],
				[
					91.3508235790298,
					67.07886562324893
				],
				[
					94.88129019077974,
					67.96148227618642
				],
				[
					97.5291401495922,
					68.40279060265516
				],
				[
					100.61829843487351,
					69.28540725559265
				],
				[
					104.14876504662345,
					70.60933223499887
				],
				[
					107.23792333190465,
					71.49194888793636
				],
				[
					109.88577329071711,
					72.81587386734259
				],
				[
					113.8575482289358,
					73.25718219381133
				],
				[
					119.15324814656071,
					75.0224154996863
				],
				[
					120.47717312596694,
					75.90503215262379
				],
				[
					122.24240643184191,
					77.67026545849876
				],
				[
					125.33156471712311,
					79.43549876437373
				],
				[
					127.97941467593557,
					82.08334872318619
				],
				[
					131.06857296121677,
					84.73119868199865
				],
				[
					133.2751145935605,
					86.93774031434236
				],
				[
					135.92296455237295,
					89.58559027315482
				],
				[
					138.5708145111854,
					92.67474855843602
				],
				[
					139.89473949059163,
					96.20521517018597
				],
				[
					141.6599727964666,
					99.73568178193591
				],
				[
					142.10128112293535,
					101.94222341427962
				],
				[
					142.5425894494041,
					104.59007337309208
				],
				[
					142.5425894494041,
					106.35530667896705
				],
				[
					142.5425894494041,
					109.00315663777951
				],
				[
					142.5425894494041,
					111.20969827012323
				],
				[
					142.10128112293535,
					112.9749315759982
				],
				[
					141.21866446999786,
					115.62278153481066
				],
				[
					140.77735614352912,
					116.0640898612794
				],
				[
					140.33604781706038,
					118.27063149362311
				],
				[
					139.89473949059163,
					119.59455647302934
				],
				[
					139.4534311641229,
					121.35978977890431
				],
				[
					139.01212283765415,
					122.2424064318418
				],
				[
					138.5708145111854,
					123.12502308477929
				],
				[
					138.12950618471666,
					124.00763973771677
				],
				[
					137.68819785824792,
					124.44894806418552
				],
				[
					137.24688953177917,
					124.89025639065426
				],
				[
					136.80558120531043,
					124.89025639065426
				],
				[
					136.3642728788417,
					124.89025639065426
				],
				[
					136.3642728788417,
					124.89025639065426
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				136.3642728788417,
				124.89025639065426
			]
		},
		{
			"id": "wmM9CZhA",
			"type": "text",
			"x": 791.5195110449646,
			"y": 527.4678412131673,
			"width": 135.58023071289062,
			"height": 31.12118852416114,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1878178486,
			"version": 312,
			"versionNonce": 1044681898,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"text": "We can improve this even more\nby avoiding division and multiplying\neverything by 2 delta x ",
			"rawText": "We can improve this even more\nby avoiding division and multiplying\neverything by 2 delta x ",
			"fontSize": 8.29898360644297,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 28,
			"containerId": null,
			"originalText": "We can improve this even more\nby avoiding division and multiplying\neverything by 2 delta x ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 437,
			"versionNonce": 395585642,
			"isDeleted": false,
			"id": "aIVC7f9A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 375.9553358058057,
			"y": 769.319862802376,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 408.43951416015625,
			"height": 25,
			"seed": 1937067830,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hr-usKbS6luYRoXYvKAfM",
					"type": "arrow"
				}
			],
			"updated": 1702836858482,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. What about Rasterization of polygons?",
			"rawText": "1. What about Rasterization of polygons?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. What about Rasterization of polygons?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 648,
			"versionNonce": 563198646,
			"isDeleted": false,
			"id": "qxCUZT2H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 381.42430876571495,
			"y": 794.7425513251421,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 440.4969482421875,
			"height": 80,
			"seed": 1639053430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kHgpieE4woNS3E0TLCZqf",
					"type": "arrow"
				}
			],
			"updated": 1702837039732,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can use a scanline algorithm that scans a line\nhorizontally down the polygon and intersects it with the\npolygon and only draws pixels when a parity bit is odd\nparity bit starts at 0 and increases each intersection",
			"rawText": "We can use a scanline algorithm that scans a line\nhorizontally down the polygon and intersects it with the\npolygon and only draws pixels when a parity bit is odd\nparity bit starts at 0 and increases each intersection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can use a scanline algorithm that scans a line\nhorizontally down the polygon and intersects it with the\npolygon and only draws pixels when a parity bit is odd\nparity bit starts at 0 and increases each intersection",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"id": "M21qzQH9wBFR3Yi6wnJSs",
			"type": "arrow",
			"x": -75.08191167758434,
			"y": 295.39717704695886,
			"width": 434.1691116962232,
			"height": 92.23281647432714,
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
			"seed": 2161526,
			"version": 228,
			"versionNonce": 87036982,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702836784634,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-118.10299670493123,
					53.98994135082569
				],
				[
					-334.06276210823387,
					-38.24287512350145
				],
				[
					-434.1691116962232,
					17.996647116941972
				]
			],
			"lastCommittedPoint": [
				-434.1691116962232,
				17.996647116941972
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "euoO0Miv",
				"focus": -0.3045843091276642,
				"gap": 8.496025118282716
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "hr-usKbS6luYRoXYvKAfM",
			"type": "arrow",
			"x": 651.5327156689452,
			"y": 655.3301193857967,
			"width": 79.94692350222044,
			"height": 112.47904448088684,
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
			"seed": 245832938,
			"version": 113,
			"versionNonce": 1686604586,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702836858484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-3.3743713344265416,
					60.738684019678885
				],
				[
					-79.86012158142955,
					65.23784579891435
				],
				[
					-79.94692350222044,
					112.47904448088684
				]
			],
			"lastCommittedPoint": [
				-87.73365469509167,
				112.47904448088684
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "aIVC7f9A",
				"focus": -0.04218042167256471,
				"gap": 1.5106989356924032
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 587,
			"versionNonce": 1815151850,
			"isDeleted": false,
			"id": "T1nbMfHh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 953.1870240306712,
			"y": 764.9887818824816,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 438.51953125,
			"height": 25,
			"seed": 1728507882,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837032260,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2. What about Rasterization of Triangles??",
			"rawText": "2. What about Rasterization of Triangles??",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2. What about Rasterization of Triangles??",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "L5b75CVZ",
			"type": "text",
			"x": 961.7812054671645,
			"y": 794.270320084575,
			"width": 520.8010864257812,
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
			"seed": 832870646,
			"version": 348,
			"versionNonce": 339956202,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "kHgpieE4woNS3E0TLCZqf",
					"type": "arrow"
				},
				{
					"id": "LBlzyUtUyI1nrav30biHh",
					"type": "arrow"
				},
				{
					"id": "bMSFbbcNFg-Zy3ApHO-hV",
					"type": "arrow"
				}
			],
			"updated": 1702837175852,
			"link": null,
			"locked": false,
			"text": "We can define each vertex as a line that seperates\npixels into two half spaces, assuming all normals point inward\nwe only draw pixels that are contained in all positive half spaces\naka their distances are all positive",
			"rawText": "We can define each vertex as a line that seperates\npixels into two half spaces, assuming all normals point inward\nwe only draw pixels that are contained in all positive half spaces\naka their distances are all positive",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "We can define each vertex as a line that seperates\npixels into two half spaces, assuming all normals point inward\nwe only draw pixels that are contained in all positive half spaces\naka their distances are all positive",
			"lineHeight": 1.25
		},
		{
			"id": "CXSdbHIc",
			"type": "text",
			"x": 962.3598791982711,
			"y": 875.2846424395075,
			"width": 533.5531005859375,
			"height": 80,
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
			"seed": 707385590,
			"version": 366,
			"versionNonce": 569397866,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702837032260,
			"link": null,
			"locked": false,
			"text": "There are a lot of strategies on how to traverse\nthe pixels since we do not want to go over every single pixel\none of which is edge tracing which turns around after we encounter\na pixel that is not drawn inside the triangle!",
			"rawText": "There are a lot of strategies on how to traverse\nthe pixels since we do not want to go over every single pixel\none of which is edge tracing which turns around after we encounter\na pixel that is not drawn inside the triangle!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "There are a lot of strategies on how to traverse\nthe pixels since we do not want to go over every single pixel\none of which is edge tracing which turns around after we encounter\na pixel that is not drawn inside the triangle!",
			"lineHeight": 1.25
		},
		{
			"id": "kHgpieE4woNS3E0TLCZqf",
			"type": "arrow",
			"x": 833.9071095829611,
			"y": 837.8569691061863,
			"width": 116.18039739245114,
			"height": 2.234238411393221,
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
			"seed": 928661482,
			"version": 80,
			"versionNonce": 1994444458,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702837041042,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					86.57673844149008,
					1.6756788085449443
				],
				[
					116.18039739245114,
					2.234238411393221
				]
			],
			"lastCommittedPoint": [
				116.18039739245114,
				2.234238411393221
			],
			"startBinding": {
				"elementId": "qxCUZT2H",
				"focus": -0.031187314330182337,
				"gap": 11.98585257505863
			},
			"endBinding": {
				"elementId": "L5b75CVZ",
				"focus": -0.24390906703046325,
				"gap": 11.69369849175223
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7jnFAKel",
			"type": "text",
			"x": 1326.2607176713936,
			"y": 630.4665144742166,
			"width": 415.76092529296875,
			"height": 80,
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
			"roundness": null,
			"seed": 1922021942,
			"version": 386,
			"versionNonce": 2123398186,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "LBlzyUtUyI1nrav30biHh",
					"type": "arrow"
				}
			],
			"updated": 1702837141594,
			"link": null,
			"locked": false,
			"text": "* Sometimes triangles are too deformed to bother\n   drawing them such as triangles smaller \n   than pixels or triangles that are practically just\n   just a straight line.",
			"rawText": "* Sometimes triangles are too deformed to bother\n   drawing them such as triangles smaller \n   than pixels or triangles that are practically just\n   just a straight line.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "* Sometimes triangles are too deformed to bother\n   drawing them such as triangles smaller \n   than pixels or triangles that are practically just\n   just a straight line.",
			"lineHeight": 1.25
		},
		{
			"id": "LBlzyUtUyI1nrav30biHh",
			"type": "arrow",
			"x": 1439.9772306748687,
			"y": 788.0655367356687,
			"width": 109.69909094915374,
			"height": 66.21476660894882,
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
			"seed": 642513334,
			"version": 61,
			"versionNonce": 1043046890,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702837142085,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					109.69909094915374,
					-5.929680591846136
				],
				[
					106.73425065323067,
					-66.21476660894882
				]
			],
			"lastCommittedPoint": [
				106.73425065323067,
				-66.21476660894882
			],
			"startBinding": {
				"elementId": "L5b75CVZ",
				"focus": -0.6367379688881258,
				"gap": 6.20478334890629
			},
			"endBinding": {
				"elementId": "7jnFAKel",
				"focus": -0.047859507776303926,
				"gap": 11.38425565250327
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "bMSFbbcNFg-Zy3ApHO-hV",
			"type": "arrow",
			"x": 1441.3354901171429,
			"y": 789.8151097957904,
			"width": 232.81351775575058,
			"height": 2.8920933882701547,
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
			"seed": 1904006198,
			"version": 65,
			"versionNonce": 1382678250,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702837215164,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					232.81351775575058,
					-2.8920933882701547
				]
			],
			"lastCommittedPoint": [
				232.81351775575058,
				-2.8920933882701547
			],
			"startBinding": {
				"elementId": "L5b75CVZ",
				"focus": -0.9652597869407321,
				"gap": 4.455210288784656
			},
			"endBinding": {
				"elementId": "pLRg6jFW",
				"focus": 0.05916331016975363,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "pLRg6jFW",
			"type": "text",
			"x": 1674.1490078728934,
			"y": 747.1567323188051,
			"width": 364.9766845703125,
			"height": 80,
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
			"roundness": null,
			"seed": 1387822378,
			"version": 212,
			"versionNonce": 593400234,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bMSFbbcNFg-Zy3ApHO-hV",
					"type": "arrow"
				}
			],
			"updated": 1702837215164,
			"link": null,
			"locked": false,
			"text": "* We form pixels in a heirarchial matter\n   of ecosystems that way we do not have\n   to check every single pixel every single time\n",
			"rawText": "* We form pixels in a heirarchial matter\n   of ecosystems that way we do not have\n   to check every single pixel every single time\n",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "* We form pixels in a heirarchial matter\n   of ecosystems that way we do not have\n   to check every single pixel every single time\n",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 52,
			"versionNonce": 1509725546,
			"isDeleted": true,
			"id": "llrgUsND1SNSde50L4JKL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1404.485973393786,
			"y": 216.78281035782618,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 278.80030357954183,
			"height": 198.37713908544322,
			"seed": 1986724906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 82,
			"versionNonce": 1104236086,
			"isDeleted": true,
			"id": "WjgO4nh2HNqA-U78FRwrp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1371.0794281423914,
			"y": 218.02008981158167,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1133309674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 2035963946,
			"isDeleted": true,
			"id": "2LWcKFoaGxGaalYq1OXPf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1335.8169637103638,
			"y": 215.7517441463633,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1386447274,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 95,
			"versionNonce": 573970294,
			"isDeleted": true,
			"id": "vz1RlVehPkp_PmtPvp3lr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1299.5234330668732,
			"y": 217.40145008470392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1322892394,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 140,
			"versionNonce": 1433518826,
			"isDeleted": true,
			"id": "ptgWHzpM10LtXacg1CV3c",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1262.405049454212,
			"y": 216.5765971155339,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1174052650,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 144,
			"versionNonce": 1169143990,
			"isDeleted": true,
			"id": "GvvTzNjgxZgs3W5RmLr7q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1226.111518810721,
			"y": 217.81387656928905,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1416702442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 121,
			"versionNonce": 2026755498,
			"isDeleted": true,
			"id": "7PSydH9iMUiz-t883qv3T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1191.4676941055714,
			"y": 217.81387656928905,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 1363696810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 120,
			"versionNonce": 602092022,
			"isDeleted": true,
			"id": "IA1CYtKHsM8DTasAyL2z_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1158.4735753387617,
			"y": 215.75174414636354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2372794537553773,
			"height": 199.20199205461347,
			"seed": 2049652586,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2372794537553773,
					199.20199205461347
				]
			]
		},
		{
			"type": "line",
			"version": 90,
			"versionNonce": 1687785578,
			"isDeleted": true,
			"id": "kvn4DD5PgtXiaf-CkcIft",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1126.3183634650231,
			"y": 244.91282008045368,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 526694954,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 166,
			"versionNonce": 2010481462,
			"isDeleted": true,
			"id": "EcLWPqdtUCMnD-ZgCLXmk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1125.24422034574,
			"y": 276.2777991635303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 1340073194,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 159,
			"versionNonce": 1017115434,
			"isDeleted": true,
			"id": "MECzpIT4vb4sy_Bdg-_mS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1124.8145630980266,
			"y": 305.49449200803974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 86489002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 171,
			"versionNonce": 1407954038,
			"isDeleted": true,
			"id": "e7OgK3cxnMYMdoWe7lmlm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1126.1035348411665,
			"y": 336.85947109111623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 1332163178,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 144,
			"versionNonce": 1934360042,
			"isDeleted": true,
			"id": "b_KvWqgo_DMlzN6RjsVof",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1126.9628493365935,
			"y": 367.79479292647943,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 23680298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 175,
			"versionNonce": 904572342,
			"isDeleted": true,
			"id": "sdUQuAKv_CcxE_Ot-cUwo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1125.6738775934532,
			"y": 392.7149132938549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.70686826140786,
			"height": 0,
			"seed": 1553539050,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702837284548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-279.70686826140786,
					0
				]
			]
		},
		{
			"id": "ES2ynHSv",
			"type": "text",
			"x": 400.74323396621605,
			"y": 950.3366015801503,
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
			"seed": 1208152054,
			"version": 2,
			"versionNonce": 690935082,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702836855941,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "q66Pngxk",
			"type": "text",
			"x": 1545.676313994628,
			"y": 772.1358561438226,
			"width": 8.000015258789062,
			"height": 20,
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
			"roundness": null,
			"seed": 1471827446,
			"version": 2,
			"versionNonce": 217306282,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702837142086,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "LBlzyUtUyI1nrav30biHh",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "UpZhWiUR",
			"type": "text",
			"x": 1553.7422413656236,
			"y": 778.3690631016552,
			"width": 8.000015258789062,
			"height": 20,
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
			"roundness": null,
			"seed": 1022489334,
			"version": 2,
			"versionNonce": 1419829162,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1702837179076,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "bMSFbbcNFg-Zy3ApHO-hV",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1971c2",
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
		"scrollX": 1686.4324852431757,
		"scrollY": 1399.5980040815225,
		"zoom": {
			"value": 0.2881670614166644
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