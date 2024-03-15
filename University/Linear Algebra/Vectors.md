---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - LinearAlgebra
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
What is a vector? ^B9Z5NoIr

A vector is a line in space
that has a length/magnitude
and has a direction! ^JOlbrz37

In linear algebra, we almost always
assume that the vector originates
at the origin point of our coordinate
system ^sWGQeDFP

The coordinate vector, or numerical vector
representation is a way to tell you how to
get to its tip from the origin! 

e.g [2,5] is a vector that starts at (0,0) and
ends at (2,5) ^sBwMH92H

Vector addition is an element-wise operation
that visually puts the start of the 2nd vector
on the end of the first (and draws a line from
start to finish) ^bOHuz1zo

And this is clearly commutative because vectors
in space are just instructions on where to move
which can be combined to go to the same point ^f5sqbQdR

Vector scalar multiplication is an element-wise
broadcasted operation that scales the vectors
length up or down! ^AAFBXyXT

Negative numbers reverse the direction! ^VsG71XhF

Our coordinate system is composes of the "basis"
which are unit vectors (length = 1) that go in x
and y direction respectively.

Vectors can be described as scaling factors for
those vectors ^IdlUItUO

Which means we can always choose a different basis vector
and refer to our vectors using those coordinates! ^axwR0u6q

LINEAR COMBINATIONS ^TELacaQS

SCALAR PRODUCT ^Ms6R9WWI

vECTOR ADDITION ^MCWoOH94

The set of all possible combinations you can reach
given the basis is the span of that basis ^33XHyN7q

The span of two vectors that have the same direction is just a line! LINEARLY DEPENDENT

The span of 2 vectors in 3d space is a plane! ^zNUSTpL0

%%***>>>text element-link:[[Subspaces]]<<<***%%The determinant of a matrix is a measure of how
much did the linear transformation associated with that
matrix alter the area of a fixed object in that space.
(Namely the 1x1x1 cube)

 ^yxKhhPp5

The determinant of a matrix is zero only when that
transformation squishes space into a lower dimension!! ^gLWIdXEn

If the determinant is negative,
then the orientation of space has
been flipped around like a sheet
of paper

if this is in 3d space, it flips it from right hand
to left hand rule  ^12DI9H0m

This is computed as follows:

1. Take first element in first row
2. eliminate its row and column and recursively
   compute the lower dimension's matrix determinant
3. multiply the result with the first element
   times reversing the sign at each iteration 
   starting with +
4. Iterate over 2-3 with the next element ^dEJdEiCD

The inverse matrix is the transformation
that preforms the reverse action that the
mentioned matrix preforms.

The identity matrix does not do anything!

 ^vN6ivfBi

The rank of a matrix is the amount of dimensions
that it squishes space onto.
meaning it squishes down a vector by rank dimensions.

More precisely it is the number of dimensions of 
the span of your column basis vectors ^OOOK2B3P

Vector subspace ^QrFSkuL9

Let F be a field, a set V together with two operations + and .
Is called F-vector space if

1) V forms a commutative group with + such that their identity element is the vector 0

2) scalar and field multiplication are compatible (same operation)

3) there exists a unique identity element for V in F

4) scalar multiplication is distributive
a (v+w) = av + aw ^B2Smn4SG

Vector addition ^zmygx4Ki

Scalar multiplication ^p7l1yjhO

%%***>>>text element-link:[[Group theory]]<<<***%%Whats a field? ^wjpV3PS2

If V is a vector subspace, and U is contained in V
then U is called a vector subspace with V's two operations
and U is itself a vector space ^kqVSPa9u

We usually talk about column vectors when we mention vectors
but for the sake of simplicity we write it as a row vector ^hk6WOnyi

M is a spanning set of V if span(M) = V

M is a basis of V if it is a spanning set of V and the vectors in M are linearly
independent

V isfinitely generated if it has a finite spanning set ^6eAq3mIh

Any two bases of a finitely generated vector space V
have the same size, which is called the dimension of the
space! ^cEUtgb0o

[[Dot Products]] ^JVIHVdSQ

[[Cross-Product]] ^1xFvN3mZ

[[EigenVectors]] ^VFkojYFB


# Embedded files
a12075da8fbc0e6adea2838e69bb19ad374added: $$\mathcal{i}
$$
0846d0cc3ae11a42afed7a6206f5dc55de54fa80: $$\mathcal{j}
$$
a7c03d01419f4c6cffda87ed4cdad0b548d67b19: $$\mathcal{k}
$$
4056f4253be958a1f59e01538074a1824b81903b: [[Dot Products]]
6bb0f151ba3e2bbab811c037de9e370140a35ed8: [[Cross-Product]]
33c1a268262dc2dc81aa3ac820e00d421bcd078a: [[EigenVectors]]
c75eb712d84d10656ec23fac6e290982b2c05aa3: [[Orthonormal]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"type": "freedraw",
			"version": 204,
			"versionNonce": 1182071283,
			"isDeleted": false,
			"id": "1JxATb_ZZRd2gfFDIjynM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 136.2646833194002,
			"y": -843.2028514802976,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 503.63636363636346,
			"height": 754.5454545454547,
			"seed": 1965507869,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168579957,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					3.1929046563192554,
					21.818181818181756
				],
				[
					-9.090909090909008,
					-184.1371531694114
				],
				[
					379.07760532150763,
					-410.6880216557636
				],
				[
					494.5454545454544,
					-732.727272727273
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 113,
			"versionNonce": 1593858227,
			"isDeleted": false,
			"id": "JifIQJUjRsqFedyMruh7E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -914.9701541712831,
			"y": -831.7666556987415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 526.904761904762,
			"height": 550.238095238095,
			"seed": 110346411,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168550421,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					148.33333333333348,
					191.66666666666652
				],
				[
					-303.0152740341417,
					93.01840258015535
				],
				[
					-378.57142857142856,
					-358.57142857142844
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 118,
			"versionNonce": 574667069,
			"isDeleted": false,
			"id": "v45YhstNUInQRkWYrQOnj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1202.4064585835797,
			"y": -456.6988328965436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1189.1025641025642,
			"height": 192.3076923076922,
			"seed": 630092837,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168541192,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					418.3333333333335,
					0
				],
				[
					-34.997185116945445,
					192.3076923076922
				],
				[
					-770.7692307692307,
					84.61538461538458
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 227,
			"versionNonce": 765242355,
			"isDeleted": false,
			"id": "bUZuD-Y4KC_QqfC9FbdWL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -856.7995939963852,
			"y": -336.1050717146392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 930.1797816044162,
			"height": 1044.4771760618348,
			"seed": 187279813,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168529974,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					251.66666666666674,
					0
				],
				[
					239.3464046586612,
					461.02380848150585
				],
				[
					-569.684133867034,
					677.1884987653657
				],
				[
					-678.5131149377495,
					1044.4771760618348
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 204,
			"versionNonce": 1189563293,
			"isDeleted": false,
			"id": "ml9LWWTyCjfF_hXjlhhOt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -212.47678200694622,
			"y": -238.70042193577746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 350.32924194122586,
			"height": 1038.5552311733238,
			"seed": 519044651,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168521020,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					95,
					0
				],
				[
					37.803389070820366,
					350.7029899720685
				],
				[
					-255.32924194122586,
					691.2406758869756
				],
				[
					-235.66790693432023,
					1038.5552311733238
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 652384733,
			"isDeleted": false,
			"id": "WdGXy83o9o8Y1OU5pL7y8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 285.057584114681,
			"y": -253.3940907423027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 156.0979923478468,
			"height": 648.714241615929,
			"seed": 1079198309,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168505340,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					-29.96210492167438,
					230.5779378754948
				],
				[
					126.13588742617242,
					648.714241615929
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 164,
			"versionNonce": 1051736093,
			"isDeleted": false,
			"id": "aBfjrN4MOYjMv3T1IHED_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 770.4580769517029,
			"y": -412.99475924842375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 302.142857142857,
			"height": 679.9999999999998,
			"seed": 47209253,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168494850,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					302.142857142857,
					289.9999999999999
				],
				[
					291.7752100840333,
					679.9999999999998
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 155,
			"versionNonce": 1599539197,
			"isDeleted": false,
			"id": "lRBG7LsTfmmWxYSmJkxHn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 835.017408424852,
			"y": -532.8176053024722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.3147049794043,
			"height": 91.15230163681565,
			"seed": 447480683,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168482520,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					299.9546670141726,
					-10.599104841490089
				],
				[
					536.3147049794043,
					80.55319679532556
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 500,
			"versionNonce": 900285395,
			"isDeleted": false,
			"id": "Q67xP3ODKfxVdOmwIsobN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 5.9673188212125785,
			"x": 733.5779491844218,
			"y": -712.664010586459,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 568.3852514004618,
			"height": 50.26976646669251,
			"seed": 1174185221,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168474151,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					-46.87309067616472
				],
				[
					292.3844308756255,
					-64.27416368386594
				],
				[
					568.3852514004618,
					-14.004397217173427
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 177,
			"versionNonce": 580652413,
			"isDeleted": false,
			"id": "Rgj_jDOs5ikyXBR4ocsF6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -333.92236138435953,
			"y": -975.2065850918117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140.84886128364394,
			"height": 590.4347826086955,
			"seed": 1424363883,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168445474,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					170.43478260869563
				],
				[
					140.84886128364394,
					-80.26570048309169
				],
				[
					73.94565217391334,
					-419.9999999999999
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 142,
			"versionNonce": 1473678365,
			"isDeleted": false,
			"id": "yVvE4htf_D_hm-nmKDVcC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 382.5068042304108,
			"y": -888.2958464846262,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 559.6311345332797,
			"height": 427.1406002305756,
			"seed": 623043301,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710168454042,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					86.95652173913055
				],
				[
					184.05646202427857,
					-191.902108463214
				],
				[
					559.6311345332797,
					-340.1840784914451
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 162,
			"versionNonce": 1727993291,
			"isDeleted": false,
			"id": "0V4GjZ8xqI7GdI8KvHwmw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -611.3249127793194,
			"y": -528.275971485994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.41139840958874,
			"height": 94.14676758795173,
			"seed": 514053771,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038651,
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
					118.41139840958874,
					-94.14676758795173
				]
			]
		},
		{
			"type": "text",
			"version": 169,
			"versionNonce": 1551777893,
			"isDeleted": false,
			"id": "B9Z5NoIr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -61.0030857445912,
			"y": -743.7458931821309,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 179.75978088378906,
			"height": 25,
			"seed": 885493477,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038651,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What is a vector?",
			"rawText": "What is a vector?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is a vector?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 1641030763,
			"isDeleted": false,
			"id": "JOlbrz37",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -460.8842016851697,
			"y": -606.893375348098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 284.69964599609375,
			"height": 75,
			"seed": 525098603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A vector is a line in space\nthat has a length/magnitude\nand has a direction!",
			"rawText": "A vector is a line in space\nthat has a length/magnitude\nand has a direction!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A vector is a line in space\nthat has a length/magnitude\nand has a direction!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 236,
			"versionNonce": 2114120645,
			"isDeleted": false,
			"id": "sWGQeDFP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -626.8542765051671,
			"y": -490.4231474042401,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 363.8395690917969,
			"height": 100,
			"seed": 1129690283,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In linear algebra, we almost always\nassume that the vector originates\nat the origin point of our coordinate\nsystem",
			"rawText": "In linear algebra, we almost always\nassume that the vector originates\nat the origin point of our coordinate\nsystem",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In linear algebra, we almost always\nassume that the vector originates\nat the origin point of our coordinate\nsystem",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 147218187,
			"isDeleted": false,
			"id": "ajEcjrgiyIGM0ypgtgw9h",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.29702925078914,
			"y": -509.8348520615498,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 137.8231030668984,
			"height": 0,
			"seed": 1881809995,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					137.8231030668984,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 265,
			"versionNonce": 345713445,
			"isDeleted": false,
			"id": "sBwMH92H",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 102.05523337680972,
			"y": -623.3933243068111,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 477.4994812011719,
			"height": 150,
			"seed": 1493933701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The coordinate vector, or numerical vector\nrepresentation is a way to tell you how to\nget to its tip from the origin! \n\ne.g [2,5] is a vector that starts at (0,0) and\nends at (2,5)",
			"rawText": "The coordinate vector, or numerical vector\nrepresentation is a way to tell you how to\nget to its tip from the origin! \n\ne.g [2,5] is a vector that starts at (0,0) and\nends at (2,5)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The coordinate vector, or numerical vector\nrepresentation is a way to tell you how to\nget to its tip from the origin! \n\ne.g [2,5] is a vector that starts at (0,0) and\nends at (2,5)",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "ellipse",
			"version": 180,
			"versionNonce": 1985758635,
			"isDeleted": false,
			"id": "f_7PD8CzjNxgHc0X6CCdm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -805.4935527811647,
			"y": -826.0158900246677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1635.7037556479852,
			"height": 581.6618958662018,
			"seed": 1125357227,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 269,
			"versionNonce": 297556043,
			"isDeleted": false,
			"id": "bOHuz1zo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 808.3546279986765,
			"y": -1311.6602099926004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 477.3194580078125,
			"height": 100,
			"seed": 1230581157,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Vector addition is an element-wise operation\nthat visually puts the start of the 2nd vector\non the end of the first (and draws a line from\nstart to finish)",
			"rawText": "Vector addition is an element-wise operation\nthat visually puts the start of the 2nd vector\non the end of the first (and draws a line from\nstart to finish)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector addition is an element-wise operation\nthat visually puts the start of the 2nd vector\non the end of the first (and draws a line from\nstart to finish)",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 957113829,
			"isDeleted": false,
			"id": "61Dycu3mZxvSV_4TK1HsG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 822.3106352894774,
			"y": -1084.6424913955727,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 141.42087388011555,
			"height": 94.90084957744602,
			"seed": 2020247397,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					141.42087388011555,
					-94.90084957744602
				]
			]
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 2025920235,
			"isDeleted": false,
			"id": "hdYo7tZ2FBdmOoz6bv8aQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 961.8707081974862,
			"y": -1176.7521395148585,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 201.896905473586,
			"height": 36.28561895608232,
			"seed": 600905003,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					201.896905473586,
					36.28561895608232
				]
			]
		},
		{
			"type": "arrow",
			"version": 100,
			"versionNonce": 1085301061,
			"isDeleted": false,
			"id": "g44fpgPuGuMwhASC62DlC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 821.380234803424,
			"y": -1080.920889451359,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 336.80497595132806,
			"height": 52.10242721898999,
			"seed": 1345956965,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					336.80497595132806,
					-52.10242721898999
				]
			]
		},
		{
			"type": "text",
			"version": 336,
			"versionNonce": 703922571,
			"isDeleted": false,
			"id": "f5sqbQdR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 6.116856855988762,
			"x": 827.532765438171,
			"y": -1089.0671768635043,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 478.75946044921875,
			"height": 75,
			"seed": 196966757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And this is clearly commutative because vectors\nin space are just instructions on where to move\nwhich can be combined to go to the same point",
			"rawText": "And this is clearly commutative because vectors\nin space are just instructions on where to move\nwhich can be combined to go to the same point",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And this is clearly commutative because vectors\nin space are just instructions on where to move\nwhich can be combined to go to the same point",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 1855100971,
			"isDeleted": false,
			"id": "AAFBXyXT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1174.7458220889266,
			"y": -888.0777282291237,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 474.85943603515625,
			"height": 75,
			"seed": 262782667,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Vector scalar multiplication is an element-wise\nbroadcasted operation that scales the vectors\nlength up or down!",
			"rawText": "Vector scalar multiplication is an element-wise\nbroadcasted operation that scales the vectors\nlength up or down!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector scalar multiplication is an element-wise\nbroadcasted operation that scales the vectors\nlength up or down!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 1805816837,
			"isDeleted": false,
			"id": "VsG71XhF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1244.0610966499587,
			"y": -777.1732889314725,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 388.99957275390625,
			"height": 25,
			"seed": 1381844267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Negative numbers reverse the direction!",
			"rawText": "Negative numbers reverse the direction!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Negative numbers reverse the direction!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 362,
			"versionNonce": 949734245,
			"isDeleted": false,
			"id": "IdlUItUO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1407.7020582167765,
			"y": -630.9029439583946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 490.21942138671875,
			"height": 150,
			"seed": 1115077931,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Our coordinate system is composes of the \"basis\"\nwhich are unit vectors (length = 1) that go in x\nand y direction respectively.\n\nVectors can be described as scaling factors for\nthose vectors",
			"rawText": "Our coordinate system is composes of the \"basis\"\nwhich are unit vectors (length = 1) that go in x\nand y direction respectively.\n\nVectors can be described as scaling factors for\nthose vectors",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our coordinate system is composes of the \"basis\"\nwhich are unit vectors (length = 1) that go in x\nand y direction respectively.\n\nVectors can be described as scaling factors for\nthose vectors",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "line",
			"version": 90,
			"versionNonce": 140822891,
			"isDeleted": false,
			"id": "3rLlvwxy3tBaHVovQDaBe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2081.617077020428,
			"y": -485.5421828331318,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.755242101937256,
			"height": 236.08006271051266,
			"seed": 1157553931,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					1.755242101937256,
					-236.08006271051266
				]
			]
		},
		{
			"type": "line",
			"version": 69,
			"versionNonce": 876025541,
			"isDeleted": false,
			"id": "VGEV-PN60ZpyQOgJFJJ2i",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2086.0051822752703,
			"y": -488.17504598603716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 259.7758310866607,
			"height": 0.8776210509684574,
			"seed": 298713611,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					259.7758310866607,
					-0.8776210509684574
				]
			]
		},
		{
			"type": "line",
			"version": 103,
			"versionNonce": 528376843,
			"isDeleted": false,
			"id": "CxYkhTJxi3QfXTQCcTvFc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2082.4946980713967,
			"y": -486.41980388410025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 83.37399984200283,
			"height": 113.21311557492982,
			"seed": 634347237,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					-83.37399984200283,
					113.21311557492982
				]
			]
		},
		{
			"type": "arrow",
			"version": 82,
			"versionNonce": 1762784805,
			"isDeleted": false,
			"id": "hMLBXCZSpv6SBRCEHpawn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2085.1275612243016,
			"y": -489.0526670370056,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 2.6328631529049744,
			"height": 94.78307350459244,
			"seed": 395036613,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					-2.6328631529049744,
					-94.78307350459244
				]
			]
		},
		{
			"type": "arrow",
			"version": 87,
			"versionNonce": 1640737451,
			"isDeleted": false,
			"id": "i4NWASCpABhR9Y6ZYXQZq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2089.515666479144,
			"y": -486.41980388410025,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 85.12924194393963,
			"height": 0,
			"seed": 1768449643,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					85.12924194393963,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 840558981,
			"isDeleted": false,
			"id": "uR1xG3zGKOjEFp10yGYyf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2084.2499401733335,
			"y": -486.41980388410025,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 47.39153675229636,
			"height": 65.82157882263363,
			"seed": 2130002245,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725038652,
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
					-47.39153675229636,
					65.82157882263363
				]
			]
		},
		{
			"type": "image",
			"version": 96,
			"versionNonce": 66526539,
			"isDeleted": false,
			"id": "fPKMOkJy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2169.9001505250208,
			"y": -514.0865918355139,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 13,
			"height": 11,
			"seed": 98721,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a12075da8fbc0e6adea2838e69bb19ad374added",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 59,
			"versionNonce": 814510309,
			"isDeleted": false,
			"id": "twuPZJNq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2030.7360244720055,
			"y": -468.19505508321794,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14,
			"height": 14,
			"seed": 414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0846d0cc3ae11a42afed7a6206f5dc55de54fa80",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 79,
			"versionNonce": 1096498155,
			"isDeleted": false,
			"id": "dkKRNSRD",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2099.068087498513,
			"y": -588.3067601168639,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 16,
			"height": 12,
			"seed": 63464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038652,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a7c03d01419f4c6cffda87ed4cdad0b548d67b19",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 142,
			"versionNonce": 91913989,
			"isDeleted": false,
			"id": "nJ87CnZ_4LCJAkDnUc154",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1420.9070440731064,
			"y": -459.34268982229867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.07195284061845,
			"height": 93.4779724412515,
			"seed": 299433643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.33504649620522287,
					0
				],
				[
					-1.0051394886156686,
					-0.33504649620522287
				],
				[
					-2.6803719696415556,
					-0.6700929924103889
				],
				[
					-3.3504649620520013,
					-0.6700929924103889
				],
				[
					-5.025697443077888,
					-0.6700929924103889
				],
				[
					-6.030836931693557,
					-0.6700929924103889
				],
				[
					-6.700929924104003,
					-0.6700929924103889
				],
				[
					-7.035976420309225,
					-0.6700929924103889
				],
				[
					-7.371022916514448,
					-0.6700929924103889
				],
				[
					-7.706069412719671,
					-0.6700929924103889
				],
				[
					-8.376162405130117,
					-0.6700929924103889
				],
				[
					-8.711208901335112,
					-0.6700929924103889
				],
				[
					-9.381301893745558,
					-0.6700929924103889
				],
				[
					-9.716348389950781,
					-0.6700929924103889
				],
				[
					-10.386441382361227,
					-0.6700929924103889
				],
				[
					-10.72148787856645,
					-0.6700929924103889
				],
				[
					-11.056534374771672,
					-0.6700929924103889
				],
				[
					-11.391580870976895,
					-0.6700929924103889
				],
				[
					-11.726627367182118,
					-0.6700929924103889
				],
				[
					-12.061673863387341,
					-0.6700929924103889
				],
				[
					-12.396720359592337,
					-0.6700929924103889
				],
				[
					-12.396720359592337,
					0.33504649620522287
				],
				[
					-12.396720359592337,
					2.3453254734364464
				],
				[
					-12.396720359592337,
					3.3504649620520013
				],
				[
					-12.396720359592337,
					5.695790435488448
				],
				[
					-12.396720359592337,
					7.371022916514448
				],
				[
					-12.396720359592337,
					8.041115908924894
				],
				[
					-12.396720359592337,
					9.716348389950895
				],
				[
					-12.061673863387341,
					12.396720359592507
				],
				[
					-12.061673863387341,
					14.742045833028897
				],
				[
					-12.061673863387341,
					16.08223181784973
				],
				[
					-11.726627367182118,
					17.757464298875732
				],
				[
					-11.726627367182118,
					19.767743276106955
				],
				[
					-11.391580870976895,
					21.442975757132956
				],
				[
					-11.391580870976895,
					23.118208238159013
				],
				[
					-11.391580870976895,
					25.12848721539018
				],
				[
					-11.391580870976895,
					26.803719696416238
				],
				[
					-11.056534374771672,
					28.813998673647404
				],
				[
					-11.056534374771672,
					30.15418465846824
				],
				[
					-11.056534374771672,
					31.494370643289017
				],
				[
					-11.056534374771672,
					32.83455662810985
				],
				[
					-10.72148787856645,
					34.174742612930686
				],
				[
					-10.72148787856645,
					35.84997509395669
				],
				[
					-10.72148787856645,
					36.8551145825723
				],
				[
					-10.72148787856645,
					37.86025407118791
				],
				[
					-10.72148787856645,
					39.20044005600869
				],
				[
					-10.72148787856645,
					40.2055795446243
				],
				[
					-10.72148787856645,
					42.21585852185552
				],
				[
					-10.72148787856645,
					43.55604450667636
				],
				[
					-10.72148787856645,
					45.56632348390758
				],
				[
					-10.72148787856645,
					46.90650946872836
				],
				[
					-10.72148787856645,
					48.58174194975436
				],
				[
					-10.72148787856645,
					50.25697443078036
				],
				[
					-10.72148787856645,
					51.26211391939603
				],
				[
					-10.72148787856645,
					52.267253408011584
				],
				[
					-10.72148787856645,
					53.60743939283242
				],
				[
					-10.72148787856645,
					54.94762537765325
				],
				[
					-10.72148787856645,
					55.95276486626881
				],
				[
					-10.72148787856645,
					56.622857858679254
				],
				[
					-10.72148787856645,
					57.96304384350003
				],
				[
					-10.72148787856645,
					59.303229828320866
				],
				[
					-10.72148787856645,
					60.30836931693648
				],
				[
					-10.72148787856645,
					61.648555301757256
				],
				[
					-10.72148787856645,
					63.323787782783256
				],
				[
					-10.72148787856645,
					64.66397376760409
				],
				[
					-10.72148787856645,
					66.33920624863015
				],
				[
					-10.72148787856645,
					67.67939223345093
				],
				[
					-10.72148787856645,
					69.0195782182717
				],
				[
					-10.72148787856645,
					70.35976420309254
				],
				[
					-10.72148787856645,
					71.69995018791337
				],
				[
					-10.72148787856645,
					73.37518266893937
				],
				[
					-10.72148787856645,
					74.71536865376015
				],
				[
					-11.056534374771672,
					76.72564763099138
				],
				[
					-11.056534374771672,
					78.06583361581221
				],
				[
					-11.391580870976895,
					79.07097310442782
				],
				[
					-11.391580870976895,
					80.4111590892486
				],
				[
					-11.391580870976895,
					81.75134507406943
				],
				[
					-11.391580870976895,
					82.75648456268505
				],
				[
					-11.391580870976895,
					84.09667054750582
				],
				[
					-11.391580870976895,
					84.76676353991627
				],
				[
					-11.391580870976895,
					86.10694952473705
				],
				[
					-11.391580870976895,
					87.44713550955788
				],
				[
					-11.391580870976895,
					88.4522749981735
				],
				[
					-11.391580870976895,
					88.78732149437872
				],
				[
					-11.391580870976895,
					89.12236799058388
				],
				[
					-11.391580870976895,
					89.79246098299427
				],
				[
					-11.391580870976895,
					90.46255397540472
				],
				[
					-11.391580870976895,
					90.79760047160988
				],
				[
					-11.391580870976895,
					91.46769346402027
				],
				[
					-11.056534374771672,
					91.8027399602255
				],
				[
					-11.056534374771672,
					92.13778645643072
				],
				[
					-10.72148787856645,
					92.47283295263594
				],
				[
					-10.386441382361227,
					92.8078794488411
				],
				[
					-10.051394886156004,
					92.8078794488411
				],
				[
					-8.711208901335112,
					92.8078794488411
				],
				[
					-7.371022916514448,
					92.8078794488411
				],
				[
					-6.030836931693557,
					92.8078794488411
				],
				[
					-4.690650946872893,
					92.8078794488411
				],
				[
					-3.685511458257224,
					92.8078794488411
				],
				[
					-2.6803719696415556,
					92.8078794488411
				],
				[
					-1.675232481025887,
					92.47283295263594
				],
				[
					-0.6700929924104457,
					92.47283295263594
				],
				[
					0.6700929924104457,
					92.13778645643072
				],
				[
					1.0051394886156686,
					92.13778645643072
				],
				[
					1.3401859848208915,
					92.13778645643072
				],
				[
					1.6752324810261143,
					92.13778645643072
				],
				[
					1.6752324810261143,
					91.8027399602255
				],
				[
					1.6752324810261143,
					90.79760047160988
				],
				[
					1.6752324810261143,
					90.79760047160988
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 74,
			"versionNonce": 969837605,
			"isDeleted": false,
			"id": "U6i3QkXpRSNpbxYYayeLr",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1436.9892758909562,
			"y": -452.6417598981946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.061673863387341,
			"height": 16.417278314054954,
			"seed": 1858565003,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.33504649620522287,
					0
				],
				[
					-0.6700929924104457,
					0
				],
				[
					-1.3401859848208915,
					0
				],
				[
					-2.010278977231337,
					0.33504649620522287
				],
				[
					-3.3504649620520013,
					0.33504649620522287
				],
				[
					-4.020557954462447,
					0.33504649620522287
				],
				[
					-4.690650946872893,
					0.33504649620522287
				],
				[
					-6.36588342789878,
					0.33504649620522287
				],
				[
					-6.700929924104003,
					0.33504649620522287
				],
				[
					-8.041115908924894,
					0.33504649620522287
				],
				[
					-8.71120890133534,
					0.33504649620522287
				],
				[
					-9.381301893745785,
					0.33504649620522287
				],
				[
					-9.716348389951008,
					0.33504649620522287
				],
				[
					-10.386441382361227,
					0.33504649620522287
				],
				[
					-10.72148787856645,
					0.33504649620522287
				],
				[
					-11.056534374771672,
					0.33504649620522287
				],
				[
					-11.391580870976895,
					1.3401859848208346
				],
				[
					-11.391580870976895,
					1.6752324810260006
				],
				[
					-11.726627367182118,
					2.6803719696416124
				],
				[
					-11.726627367182118,
					3.685511458257224
				],
				[
					-11.726627367182118,
					4.690650946872836
				],
				[
					-11.726627367182118,
					6.030836931693614
				],
				[
					-11.726627367182118,
					7.035976420309282
				],
				[
					-11.726627367182118,
					7.706069412719671
				],
				[
					-11.726627367182118,
					8.37616240513006
				],
				[
					-11.726627367182118,
					8.711208901335283
				],
				[
					-11.726627367182118,
					9.046255397540449
				],
				[
					-11.391580870976895,
					9.046255397540449
				],
				[
					-10.386441382361227,
					9.046255397540449
				],
				[
					-9.381301893745785,
					9.046255397540449
				],
				[
					-8.376162405130117,
					8.711208901335283
				],
				[
					-7.706069412719671,
					8.711208901335283
				],
				[
					-6.36588342789878,
					8.711208901335283
				],
				[
					-5.3607439392833385,
					8.711208901335283
				],
				[
					-4.35560445066767,
					9.046255397540449
				],
				[
					-4.020557954462447,
					9.381301893745672
				],
				[
					-3.3504649620520013,
					10.05139488615606
				],
				[
					-3.0154184658467784,
					10.721487878566506
				],
				[
					-2.6803719696415556,
					11.726627367182061
				],
				[
					-2.010278977231337,
					12.396720359592507
				],
				[
					-1.6752324810261143,
					13.066813352002896
				],
				[
					-1.6752324810261143,
					13.736906344413285
				],
				[
					-1.6752324810261143,
					14.071952840618508
				],
				[
					-2.010278977231337,
					14.40699933682373
				],
				[
					-2.34532547343656,
					14.742045833028897
				],
				[
					-2.6803719696415556,
					15.07709232923412
				],
				[
					-3.3504649620520013,
					15.747185321644508
				],
				[
					-4.35560445066767,
					16.08223181784973
				],
				[
					-5.025697443078116,
					16.417278314054954
				],
				[
					-6.030836931693784,
					16.417278314054954
				],
				[
					-7.035976420309225,
					16.417278314054954
				],
				[
					-7.706069412719671,
					16.417278314054954
				],
				[
					-8.71120890133534,
					16.417278314054954
				],
				[
					-9.381301893745785,
					16.417278314054954
				],
				[
					-9.716348389951008,
					16.417278314054954
				],
				[
					-10.051394886156004,
					16.417278314054954
				],
				[
					-10.72148787856645,
					16.417278314054954
				],
				[
					-11.056534374771672,
					16.08223181784973
				],
				[
					-11.391580870976895,
					15.747185321644508
				],
				[
					-11.726627367182118,
					15.747185321644508
				],
				[
					-12.061673863387341,
					15.747185321644508
				],
				[
					-12.061673863387341,
					15.747185321644508
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 57,
			"versionNonce": 2034988203,
			"isDeleted": false,
			"id": "yN-5t7fGe-eoTO2T2ODyh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1426.602834508595,
			"y": -422.48757523972637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.035976420309225,
			"height": 19.767743276106955,
			"seed": 441949067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.335046496205166
				],
				[
					0,
					1.0051394886156118
				],
				[
					0,
					1.3401859848208346
				],
				[
					0.33504649620522287,
					2.6803719696416124
				],
				[
					0.6700929924102184,
					4.690650946872836
				],
				[
					1.0051394886154412,
					6.030836931693614
				],
				[
					1.340185984820664,
					7.035976420309282
				],
				[
					2.01027897723111,
					8.37616240513006
				],
				[
					2.6803719696415556,
					8.711208901335283
				],
				[
					3.0154184658467784,
					8.711208901335283
				],
				[
					3.685511458257224,
					8.711208901335283
				],
				[
					4.3556044506674425,
					8.711208901335283
				],
				[
					5.025697443077888,
					8.041115908924837
				],
				[
					5.695790435488334,
					7.706069412719614
				],
				[
					6.36588342789878,
					6.3658834278988365
				],
				[
					6.36588342789878,
					5.360743939283225
				],
				[
					6.700929924104003,
					4.02055795446239
				],
				[
					6.700929924104003,
					3.0154184658468353
				],
				[
					6.700929924104003,
					2.3453254734363895
				],
				[
					6.700929924104003,
					2.0102789772311667
				],
				[
					6.700929924104003,
					1.3401859848208346
				],
				[
					6.700929924104003,
					1.6752324810260006
				],
				[
					6.700929924104003,
					2.6803719696416124
				],
				[
					6.700929924104003,
					3.685511458257224
				],
				[
					6.700929924104003,
					4.690650946872836
				],
				[
					6.700929924104003,
					5.695790435488391
				],
				[
					6.700929924104003,
					6.700929924104059
				],
				[
					6.700929924104003,
					7.371022916514448
				],
				[
					6.700929924104003,
					8.37616240513006
				],
				[
					6.700929924104003,
					9.046255397540449
				],
				[
					6.700929924104003,
					10.386441382361284
				],
				[
					6.700929924104003,
					11.391580870976838
				],
				[
					6.700929924104003,
					12.731766855797673
				],
				[
					7.035976420309225,
					13.736906344413285
				],
				[
					7.035976420309225,
					14.40699933682373
				],
				[
					7.035976420309225,
					15.412138825439285
				],
				[
					7.035976420309225,
					16.08223181784973
				],
				[
					7.035976420309225,
					17.087371306465286
				],
				[
					7.035976420309225,
					17.757464298875732
				],
				[
					7.035976420309225,
					18.092510795080955
				],
				[
					7.035976420309225,
					18.762603787491344
				],
				[
					7.035976420309225,
					19.09765028369651
				],
				[
					7.035976420309225,
					19.432696779901732
				],
				[
					7.035976420309225,
					19.767743276106955
				],
				[
					7.035976420309225,
					19.767743276106955
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 76,
			"versionNonce": 718520197,
			"isDeleted": false,
			"id": "Bf24JZYadNdYflrPBvghO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1430.9584389592624,
			"y": -389.6530186116165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.396720359592564,
			"height": 11.726627367182061,
			"seed": 9752299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.0051394886156686,
					0
				],
				[
					2.34532547343656,
					0
				],
				[
					3.685511458257224,
					0
				],
				[
					4.690650946872893,
					0
				],
				[
					5.3607439392833385,
					0
				],
				[
					6.365883427899007,
					0
				],
				[
					6.70092992410423,
					0
				],
				[
					7.035976420309453,
					0.6700929924103889
				],
				[
					7.371022916514448,
					1.3401859848207778
				],
				[
					7.706069412719671,
					2.3453254734363895
				],
				[
					8.041115908924894,
					3.0154184658467784
				],
				[
					8.041115908924894,
					3.685511458257224
				],
				[
					8.041115908924894,
					4.355604450667613
				],
				[
					8.041115908924894,
					5.360743939283225
				],
				[
					8.041115908924894,
					6.3658834278988365
				],
				[
					7.706069412719671,
					7.035976420309225
				],
				[
					7.371022916514448,
					8.041115908924837
				],
				[
					6.70092992410423,
					8.711208901335226
				],
				[
					5.695790435488561,
					9.716348389950895
				],
				[
					5.3607439392833385,
					10.05139488615606
				],
				[
					4.35560445066767,
					10.05139488615606
				],
				[
					4.020557954462447,
					10.05139488615606
				],
				[
					3.3504649620522287,
					10.386441382361227
				],
				[
					2.680371969641783,
					10.386441382361227
				],
				[
					2.010278977231337,
					10.386441382361227
				],
				[
					1.6752324810261143,
					10.386441382361227
				],
				[
					1.0051394886156686,
					10.386441382361227
				],
				[
					0.33504649620522287,
					10.386441382361227
				],
				[
					0,
					10.05139488615606
				],
				[
					-0.3350464962049955,
					10.05139488615606
				],
				[
					-0.6700929924102184,
					9.716348389950895
				],
				[
					-1.0051394886154412,
					9.381301893745672
				],
				[
					-1.340185984820664,
					9.046255397540449
				],
				[
					-1.340185984820664,
					8.37616240513006
				],
				[
					-1.675232481025887,
					7.706069412719671
				],
				[
					-1.675232481025887,
					7.371022916514448
				],
				[
					-1.0051394886154412,
					7.371022916514448
				],
				[
					-0.3350464962049955,
					7.035976420309225
				],
				[
					0.33504649620522287,
					7.035976420309225
				],
				[
					0.6700929924104457,
					7.035976420309225
				],
				[
					1.3401859848208915,
					7.035976420309225
				],
				[
					1.6752324810261143,
					7.035976420309225
				],
				[
					2.010278977231337,
					7.035976420309225
				],
				[
					2.680371969641783,
					7.035976420309225
				],
				[
					2.680371969641783,
					7.371022916514448
				],
				[
					3.015418465847006,
					7.371022916514448
				],
				[
					3.3504649620522287,
					7.706069412719671
				],
				[
					3.685511458257224,
					8.041115908924837
				],
				[
					4.020557954462447,
					8.37616240513006
				],
				[
					4.35560445066767,
					8.711208901335226
				],
				[
					4.690650946872893,
					9.381301893745672
				],
				[
					5.025697443078116,
					9.716348389950895
				],
				[
					5.695790435488561,
					10.386441382361227
				],
				[
					6.030836931693784,
					10.72148787856645
				],
				[
					6.70092992410423,
					11.056534374771672
				],
				[
					7.035976420309453,
					11.056534374771672
				],
				[
					7.706069412719671,
					11.391580870976895
				],
				[
					8.041115908924894,
					11.391580870976895
				],
				[
					8.376162405130117,
					11.726627367182061
				],
				[
					9.046255397540563,
					11.726627367182061
				],
				[
					9.716348389951008,
					11.726627367182061
				],
				[
					10.386441382361454,
					11.726627367182061
				],
				[
					10.721487878566677,
					11.726627367182061
				],
				[
					10.721487878566677,
					11.726627367182061
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 96,
			"versionNonce": 1827514187,
			"isDeleted": false,
			"id": "xRTyhx-HtoPt1oGiNeUbK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1438.3294618757768,
			"y": -459.34268982229867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.051394886156231,
			"height": 92.13778645643072,
			"seed": 989034539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					1.0051394886156686,
					0.33504649620522287
				],
				[
					2.010278977231337,
					0.6700929924104457
				],
				[
					3.685511458257224,
					1.3401859848208346
				],
				[
					4.690650946872893,
					2.3453254734364464
				],
				[
					5.025697443078116,
					2.6803719696416124
				],
				[
					5.3607439392833385,
					2.6803719696416124
				],
				[
					6.365883427899007,
					3.3504649620520013
				],
				[
					6.70092992410423,
					3.685511458257224
				],
				[
					7.371022916514448,
					4.020557954462447
				],
				[
					7.7060694127198985,
					4.35560445066767
				],
				[
					8.041115908924894,
					5.695790435488448
				],
				[
					8.041115908924894,
					7.371022916514448
				],
				[
					8.041115908924894,
					9.381301893745672
				],
				[
					8.376162405130117,
					11.056534374771672
				],
				[
					8.376162405130117,
					13.066813352002896
				],
				[
					8.71120890133534,
					15.07709232923412
				],
				[
					8.71120890133534,
					17.422417802670566
				],
				[
					9.046255397540563,
					19.767743276106955
				],
				[
					9.046255397540563,
					22.448115245748568
				],
				[
					9.381301893745785,
					26.133626704005792
				],
				[
					9.381301893745785,
					29.149045169852627
				],
				[
					9.381301893745785,
					32.83455662810985
				],
				[
					9.381301893745785,
					36.18502159016191
				],
				[
					9.381301893745785,
					39.53548655221391
				],
				[
					9.381301893745785,
					42.55090501806069
				],
				[
					9.381301893745785,
					45.23127698770236
				],
				[
					9.381301893745785,
					46.90650946872836
				],
				[
					9.381301893745785,
					48.91678844595958
				],
				[
					9.381301893745785,
					50.927067423190806
				],
				[
					9.381301893745785,
					52.60229990421681
				],
				[
					9.381301893745785,
					54.61257888144803
				],
				[
					9.381301893745785,
					56.28781136247403
				],
				[
					9.381301893745785,
					57.62799734729481
				],
				[
					9.381301893745785,
					59.303229828320866
				],
				[
					9.381301893745785,
					61.31350880555203
				],
				[
					9.381301893745785,
					62.98874128657809
				],
				[
					9.716348389951008,
					64.66397376760409
				],
				[
					9.716348389951008,
					66.33920624863015
				],
				[
					9.716348389951008,
					68.01443872965615
				],
				[
					10.051394886156231,
					69.68967121068215
				],
				[
					10.051394886156231,
					71.02985719550293
				],
				[
					10.051394886156231,
					72.37004318032376
				],
				[
					10.051394886156231,
					73.37518266893937
				],
				[
					10.051394886156231,
					74.71536865376015
				],
				[
					9.716348389951008,
					75.3854616461706
				],
				[
					9.381301893745785,
					76.72564763099138
				],
				[
					9.046255397540563,
					77.39574062340182
				],
				[
					9.046255397540563,
					78.7359266082226
				],
				[
					9.046255397540563,
					79.40601960063304
				],
				[
					9.046255397540563,
					80.74620558545382
				],
				[
					9.046255397540563,
					81.41629857786421
				],
				[
					9.046255397540563,
					82.42143806647982
				],
				[
					9.046255397540563,
					83.42657755509543
				],
				[
					9.046255397540563,
					84.43171704371105
				],
				[
					9.046255397540563,
					85.10181003612149
				],
				[
					9.381301893745785,
					85.77190302853182
				],
				[
					9.381301893745785,
					86.44199602094227
				],
				[
					9.381301893745785,
					87.11208901335266
				],
				[
					9.716348389951008,
					87.44713550955788
				],
				[
					9.716348389951008,
					87.78218200576305
				],
				[
					9.716348389951008,
					88.11722850196827
				],
				[
					9.716348389951008,
					88.4522749981735
				],
				[
					9.381301893745785,
					88.78732149437872
				],
				[
					9.046255397540563,
					89.12236799058388
				],
				[
					8.71120890133534,
					89.45741448678905
				],
				[
					8.376162405130117,
					90.1275074791995
				],
				[
					8.041115908924894,
					90.79760047160988
				],
				[
					7.7060694127198985,
					91.1326469678151
				],
				[
					7.371022916514448,
					91.46769346402027
				],
				[
					6.70092992410423,
					91.8027399602255
				],
				[
					6.030836931693784,
					91.8027399602255
				],
				[
					5.3607439392833385,
					91.8027399602255
				],
				[
					5.025697443078116,
					91.8027399602255
				],
				[
					3.685511458257224,
					91.8027399602255
				],
				[
					3.3504649620522287,
					91.8027399602255
				],
				[
					2.680371969641783,
					91.8027399602255
				],
				[
					2.34532547343656,
					91.8027399602255
				],
				[
					1.6752324810261143,
					92.13778645643072
				],
				[
					1.3401859848208915,
					92.13778645643072
				],
				[
					1.0051394886156686,
					92.13778645643072
				],
				[
					0.6700929924104457,
					92.13778645643072
				],
				[
					0.33504649620522287,
					92.13778645643072
				],
				[
					0.33504649620522287,
					92.13778645643072
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 20,
			"versionNonce": 1604028133,
			"isDeleted": false,
			"id": "ZAR7xvi8TyzsILvZV_bt0",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1470.8289720076816,
			"y": -413.4413198421859,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.72148787856645,
			"height": 0,
			"seed": 2121698795,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					1.675232481025887,
					0
				],
				[
					3.685511458257224,
					0
				],
				[
					5.695790435488334,
					0
				],
				[
					8.711208901335112,
					0
				],
				[
					10.051394886156004,
					0
				],
				[
					10.72148787856645,
					0
				],
				[
					10.72148787856645,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 25,
			"versionNonce": 519079403,
			"isDeleted": false,
			"id": "yBRIoMxfubFlvETSuGwER",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1470.8289720076816,
			"y": -409.7558083839287,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.711208901335112,
			"height": 1.0051394886156118,
			"seed": 843330603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038653,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.0051394886156686,
					0
				],
				[
					2.3453254734363327,
					0.33504649620522287
				],
				[
					3.685511458257224,
					0.33504649620522287
				],
				[
					4.35560445066767,
					0.6700929924103889
				],
				[
					5.360743939283111,
					0.6700929924103889
				],
				[
					6.030836931693557,
					0.6700929924103889
				],
				[
					7.035976420309225,
					0.6700929924103889
				],
				[
					7.706069412719671,
					0.6700929924103889
				],
				[
					8.041115908924894,
					0.6700929924103889
				],
				[
					8.376162405130117,
					0.6700929924103889
				],
				[
					8.376162405130117,
					1.0051394886156118
				],
				[
					8.711208901335112,
					1.0051394886156118
				],
				[
					8.711208901335112,
					1.0051394886156118
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 57,
			"versionNonce": 266647659,
			"isDeleted": false,
			"id": "pk-fSlWAGl4pNFRUr1HbY",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1503.6635286357914,
			"y": -422.8226217359316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.731766855797787,
			"height": 18.762603787491344,
			"seed": 620838725,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.0051394886156686,
					0
				],
				[
					-2.3453254734363327,
					0
				],
				[
					-3.3504649620520013,
					0
				],
				[
					-4.690650946872893,
					0
				],
				[
					-5.695790435488334,
					0
				],
				[
					-7.035976420309225,
					0
				],
				[
					-7.371022916514448,
					0
				],
				[
					-7.706069412719671,
					0
				],
				[
					-8.041115908924894,
					0.33504649620522287
				],
				[
					-8.376162405130117,
					0.33504649620522287
				],
				[
					-8.376162405130117,
					0.6700929924103889
				],
				[
					-8.376162405130117,
					1.0051394886156118
				],
				[
					-8.376162405130117,
					1.6752324810260575
				],
				[
					-8.376162405130117,
					2.0102789772312235
				],
				[
					-8.376162405130117,
					3.350464962052058
				],
				[
					-7.706069412719671,
					4.355604450667613
				],
				[
					-7.371022916514448,
					5.695790435488448
				],
				[
					-7.035976420309225,
					6.700929924104059
				],
				[
					-6.700929924104003,
					8.041115908924837
				],
				[
					-6.36588342789878,
					8.711208901335283
				],
				[
					-6.030836931693557,
					9.381301893745672
				],
				[
					-6.030836931693557,
					10.386441382361284
				],
				[
					-6.030836931693557,
					10.721487878566506
				],
				[
					-6.030836931693557,
					11.391580870976895
				],
				[
					-6.030836931693557,
					11.726627367182061
				],
				[
					-5.695790435488334,
					11.726627367182061
				],
				[
					-4.690650946872893,
					11.726627367182061
				],
				[
					-3.3504649620520013,
					11.726627367182061
				],
				[
					-1.675232481025887,
					11.726627367182061
				],
				[
					0.33504649620522287,
					11.726627367182061
				],
				[
					1.6752324810261143,
					11.726627367182061
				],
				[
					2.6803719696415556,
					12.061673863387284
				],
				[
					3.3504649620520013,
					12.061673863387284
				],
				[
					3.685511458257224,
					12.396720359592507
				],
				[
					4.020557954462447,
					13.066813352002896
				],
				[
					4.35560445066767,
					14.071952840618508
				],
				[
					4.35560445066767,
					14.742045833028953
				],
				[
					4.35560445066767,
					15.412138825439285
				],
				[
					4.35560445066767,
					16.08223181784973
				],
				[
					3.685511458257224,
					17.087371306465343
				],
				[
					3.0154184658467784,
					17.757464298875732
				],
				[
					1.3401859848208915,
					18.427557291286178
				],
				[
					0.33504649620522287,
					18.427557291286178
				],
				[
					-0.6700929924104457,
					18.762603787491344
				],
				[
					-1.675232481025887,
					18.762603787491344
				],
				[
					-2.6803719696415556,
					18.762603787491344
				],
				[
					-3.3504649620520013,
					18.762603787491344
				],
				[
					-4.020557954462447,
					18.762603787491344
				],
				[
					-4.690650946872893,
					18.762603787491344
				],
				[
					-5.360743939283111,
					18.427557291286178
				],
				[
					-6.030836931693557,
					18.427557291286178
				],
				[
					-6.030836931693557,
					18.427557291286178
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 1479645125,
			"isDeleted": false,
			"id": "oDWe_VLYkozgKXSjsf1Co",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1513.7149235219474,
			"y": -414.44645933080153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1193396613,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 21,
			"versionNonce": 791180043,
			"isDeleted": false,
			"id": "ob5kNyzovgBaHbR98fT4z",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1523.7663184081036,
			"y": -421.14738925490553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.340185984820664,
			"height": 15.747185321644452,
			"seed": 1976245157,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.005139488615555
				],
				[
					0,
					2.3453254734363895
				],
				[
					0.33504649620522287,
					3.685511458257224
				],
				[
					0.33504649620522287,
					4.690650946872779
				],
				[
					0.33504649620522287,
					5.695790435488448
				],
				[
					0.33504649620522287,
					7.371022916514448
				],
				[
					0.33504649620522287,
					8.711208901335226
				],
				[
					0.33504649620522287,
					10.72148787856645
				],
				[
					0.33504649620522287,
					12.061673863387227
				],
				[
					0.6700929924102184,
					13.066813352002896
				],
				[
					0.6700929924102184,
					14.07195284061845
				],
				[
					1.0051394886156686,
					14.742045833028897
				],
				[
					1.0051394886156686,
					15.412138825439285
				],
				[
					1.0051394886156686,
					15.747185321644452
				],
				[
					1.340185984820664,
					15.747185321644452
				],
				[
					1.340185984820664,
					15.747185321644452
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 202659621,
			"isDeleted": false,
			"id": "JlHinwEADqali4JSe0S2o",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1524.7714578967193,
			"y": -426.5081331941888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 309218405,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 14,
			"versionNonce": 794548651,
			"isDeleted": false,
			"id": "P9G0zK0xq3UVu3EQZplSN",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1543.1990151880054,
			"y": -414.44645933080153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.401859848208005,
			"height": 0,
			"seed": 1401948805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.340185984820664,
					0
				],
				[
					3.0154184658467784,
					0
				],
				[
					5.025697443077888,
					0
				],
				[
					7.035976420309225,
					0
				],
				[
					9.716348389950781,
					0
				],
				[
					11.726627367182118,
					0
				],
				[
					13.066813352002782,
					0
				],
				[
					13.401859848208005,
					0
				],
				[
					13.401859848208005,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 24,
			"versionNonce": 1747462789,
			"isDeleted": false,
			"id": "sdbtaAtMgJ91zNrwiSylD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1550.5700381045199,
			"y": -419.13711027767437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.01027897723111,
			"height": 11.391580870976895,
			"seed": 1122125733,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.33504649620522287
				],
				[
					0,
					1.0051394886156118
				],
				[
					0.3350464962049955,
					2.0102789772312235
				],
				[
					0.3350464962049955,
					3.0154184658468353
				],
				[
					0.3350464962049955,
					4.355604450667613
				],
				[
					0.3350464962049955,
					4.690650946872836
				],
				[
					0.3350464962049955,
					5.360743939283282
				],
				[
					0.3350464962049955,
					6.3658834278988365
				],
				[
					0.3350464962049955,
					7.035976420309282
				],
				[
					0.3350464962049955,
					7.706069412719671
				],
				[
					0.3350464962049955,
					8.37616240513006
				],
				[
					0.6700929924102184,
					8.711208901335283
				],
				[
					0.6700929924102184,
					9.381301893745672
				],
				[
					0.6700929924102184,
					9.716348389950895
				],
				[
					1.0051394886154412,
					10.386441382361284
				],
				[
					1.340185984820664,
					10.721487878566506
				],
				[
					1.675232481025887,
					11.391580870976895
				],
				[
					2.01027897723111,
					11.391580870976895
				],
				[
					2.01027897723111,
					11.391580870976895
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 42,
			"versionNonce": 766078027,
			"isDeleted": false,
			"id": "H8RRZRtX-C-nE9FEJIFqH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1570.3377813806267,
			"y": -424.8329007131628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.051394886156004,
			"height": 20.4378362685174,
			"seed": 768849541,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.33504649620522287
				],
				[
					0.6700929924104457,
					1.3401859848208346
				],
				[
					1.0051394886156686,
					2.6803719696416124
				],
				[
					1.6752324810261143,
					4.020557954462447
				],
				[
					2.34532547343656,
					6.0308369316936705
				],
				[
					3.3504649620520013,
					7.706069412719671
				],
				[
					4.690650946872893,
					8.37616240513006
				],
				[
					5.025697443078116,
					8.37616240513006
				],
				[
					5.695790435488561,
					8.37616240513006
				],
				[
					6.030836931693784,
					8.37616240513006
				],
				[
					6.70092992410423,
					8.37616240513006
				],
				[
					7.371022916514448,
					8.041115908924837
				],
				[
					7.706069412719671,
					7.706069412719671
				],
				[
					8.041115908924894,
					6.700929924104059
				],
				[
					8.376162405130117,
					6.0308369316936705
				],
				[
					8.71120890133534,
					5.025697443078059
				],
				[
					8.71120890133534,
					3.685511458257281
				],
				[
					8.71120890133534,
					3.0154184658468353
				],
				[
					8.71120890133534,
					2.3453254734364464
				],
				[
					8.71120890133534,
					3.0154184658468353
				],
				[
					8.71120890133534,
					4.355604450667613
				],
				[
					8.71120890133534,
					5.695790435488448
				],
				[
					8.71120890133534,
					7.035976420309282
				],
				[
					8.71120890133534,
					9.046255397540506
				],
				[
					8.71120890133534,
					11.391580870976895
				],
				[
					8.71120890133534,
					12.73176685579773
				],
				[
					8.71120890133534,
					13.736906344413285
				],
				[
					8.71120890133534,
					15.07709232923412
				],
				[
					8.71120890133534,
					16.417278314054954
				],
				[
					9.046255397540563,
					17.757464298875732
				],
				[
					9.381301893745785,
					18.427557291286178
				],
				[
					9.381301893745785,
					19.097650283696566
				],
				[
					9.716348389951008,
					19.767743276106955
				],
				[
					9.716348389951008,
					20.10278977231218
				],
				[
					10.051394886156004,
					20.10278977231218
				],
				[
					10.051394886156004,
					20.4378362685174
				],
				[
					10.051394886156004,
					20.4378362685174
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 1831506405,
			"isDeleted": false,
			"id": "kp9Eq95Oa_X9w11o5yjWm",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1588.0952456795026,
			"y": -415.1165523232119,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1873631781,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 31,
			"versionNonce": 1038854891,
			"isDeleted": false,
			"id": "E77uYSipKvXexu-s4ER8L",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1598.1466405656586,
			"y": -420.81234275870037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.700929924104003,
			"height": 19.767743276106955,
			"seed": 1948053573,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.335046496205166
				],
				[
					0,
					1.6752324810260006
				],
				[
					0,
					3.350464962052058
				],
				[
					0,
					5.360743939283282
				],
				[
					0,
					7.371022916514448
				],
				[
					-0.33504649620522287,
					11.056534374771672
				],
				[
					-0.6700929924104457,
					12.73176685579773
				],
				[
					-0.6700929924104457,
					14.071952840618508
				],
				[
					-0.6700929924104457,
					15.412138825439285
				],
				[
					-1.0051394886156686,
					16.75232481026012
				],
				[
					-1.3401859848208915,
					18.092510795080955
				],
				[
					-1.6752324810261143,
					19.09765028369651
				],
				[
					-2.34532547343656,
					19.432696779901732
				],
				[
					-3.0154184658467784,
					19.767743276106955
				],
				[
					-3.685511458257224,
					19.767743276106955
				],
				[
					-4.35560445066767,
					19.767743276106955
				],
				[
					-4.690650946872893,
					19.767743276106955
				],
				[
					-5.3607439392833385,
					19.767743276106955
				],
				[
					-6.030836931693784,
					19.09765028369651
				],
				[
					-6.36588342789878,
					18.762603787491344
				],
				[
					-6.700929924104003,
					18.427557291286178
				],
				[
					-6.700929924104003,
					17.757464298875732
				],
				[
					-6.700929924104003,
					17.087371306465343
				],
				[
					-6.700929924104003,
					16.08223181784973
				],
				[
					-6.700929924104003,
					15.412138825439285
				],
				[
					-6.700929924104003,
					15.412138825439285
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 673779013,
			"isDeleted": false,
			"id": "W81XszdYU2iESTcwGQz5C",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1596.8064545808377,
			"y": -428.51841217142004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1990305477,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 17,
			"versionNonce": 346887563,
			"isDeleted": false,
			"id": "KtR1z7YYL2_eJcSn1Vuml",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1610.543360925251,
			"y": -415.1165523232119,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.736906344413455,
			"height": 1.6752324810260575,
			"seed": 1715536101,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620545024,
					0
				],
				[
					2.010278977231337,
					0
				],
				[
					3.3504649620522287,
					0
				],
				[
					5.3607439392833385,
					0
				],
				[
					7.7060694127198985,
					-0.335046496205166
				],
				[
					11.056534374771672,
					-0.6700929924103889
				],
				[
					11.726627367182118,
					-1.0051394886156118
				],
				[
					12.396720359592564,
					-1.3401859848208346
				],
				[
					13.06681335200301,
					-1.6752324810260575
				],
				[
					13.401859848208233,
					-1.6752324810260575
				],
				[
					13.736906344413455,
					-1.6752324810260575
				],
				[
					13.736906344413455,
					-1.6752324810260575
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 16,
			"versionNonce": 679550117,
			"isDeleted": false,
			"id": "9VrYoWfMgvcoybRltxzqe",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1617.9143838417654,
			"y": -419.13711027767437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.33504649620545024,
			"height": 8.711208901335283,
			"seed": 1699159077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.6700929924103889
				],
				[
					0.33504649620545024,
					1.3401859848208346
				],
				[
					0.33504649620545024,
					2.3453254734363895
				],
				[
					0.33504649620545024,
					3.350464962052058
				],
				[
					0.33504649620545024,
					4.020557954462447
				],
				[
					0.33504649620545024,
					5.360743939283282
				],
				[
					0.33504649620545024,
					6.3658834278988365
				],
				[
					0.33504649620545024,
					7.706069412719671
				],
				[
					0.33504649620545024,
					8.041115908924837
				],
				[
					0.33504649620545024,
					8.711208901335283
				],
				[
					0.33504649620545024,
					8.711208901335283
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 51,
			"versionNonce": 1898458155,
			"isDeleted": false,
			"id": "53OjHECDcV1mPkGJD1bfQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1630.9811971937684,
			"y": -421.817482247316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.747185321644565,
			"height": 16.75232481026012,
			"seed": 1617874949,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					1.6752324810261143,
					-0.33504649620522287
				],
				[
					2.6803719696415556,
					-0.33504649620522287
				],
				[
					4.690650946872893,
					-0.33504649620522287
				],
				[
					6.700929924104003,
					-0.33504649620522287
				],
				[
					9.046255397540563,
					-0.33504649620522287
				],
				[
					11.056534374771672,
					0.33504649620522287
				],
				[
					12.061673863387341,
					0.6700929924104457
				],
				[
					13.401859848208005,
					1.6752324810260006
				],
				[
					13.736906344413455,
					2.6803719696416124
				],
				[
					14.07195284061845,
					3.685511458257224
				],
				[
					14.406999336823674,
					5.025697443078002
				],
				[
					14.406999336823674,
					6.365883427898893
				],
				[
					13.736906344413455,
					7.706069412719671
				],
				[
					13.401859848208005,
					8.711208901335283
				],
				[
					11.391580870976895,
					11.056534374771672
				],
				[
					9.381301893745785,
					13.066813352002896
				],
				[
					7.371022916514448,
					14.071952840618508
				],
				[
					6.030836931693557,
					14.742045833028897
				],
				[
					4.690650946872893,
					15.412138825439342
				],
				[
					3.685511458257224,
					16.08223181784973
				],
				[
					3.0154184658467784,
					15.747185321644565
				],
				[
					2.6803719696415556,
					15.412138825439342
				],
				[
					2.6803719696415556,
					15.07709232923412
				],
				[
					2.6803719696415556,
					14.071952840618508
				],
				[
					2.6803719696415556,
					13.066813352002896
				],
				[
					2.6803719696415556,
					12.396720359592507
				],
				[
					3.685511458257224,
					12.061673863387284
				],
				[
					5.695790435488561,
					11.726627367182118
				],
				[
					6.365883427899007,
					11.726627367182118
				],
				[
					7.035976420309225,
					11.726627367182118
				],
				[
					7.706069412719671,
					11.726627367182118
				],
				[
					8.041115908924894,
					12.061673863387284
				],
				[
					8.71120890133534,
					12.731766855797673
				],
				[
					9.716348389950781,
					13.401859848208119
				],
				[
					10.051394886156231,
					14.071952840618508
				],
				[
					10.72148787856645,
					14.406999336823674
				],
				[
					11.056534374771672,
					15.07709232923412
				],
				[
					12.061673863387341,
					15.747185321644565
				],
				[
					12.731766855797787,
					16.08223181784973
				],
				[
					13.401859848208005,
					16.417278314054897
				],
				[
					14.07195284061845,
					16.417278314054897
				],
				[
					14.742045833028897,
					16.417278314054897
				],
				[
					15.412138825439342,
					16.417278314054897
				],
				[
					15.747185321644565,
					16.417278314054897
				],
				[
					15.747185321644565,
					16.417278314054897
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 903888901,
			"isDeleted": false,
			"id": "B-_nlqa2rf5Ax2zJNYO1c",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1650.4138939736702,
			"y": -414.78150582700675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1992380933,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 21,
			"versionNonce": 1195863755,
			"isDeleted": false,
			"id": "wHczAAStB0pRoDkpPS3ii",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1657.4498703939794,
			"y": -424.8329007131628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.3453254734363327,
			"height": 20.772882764722567,
			"seed": 109147173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					0.6700929924104457,
					0.33504649620522287
				],
				[
					1.0051394886156686,
					1.0051394886156118
				],
				[
					1.0051394886156686,
					2.0102789772312235
				],
				[
					1.3401859848208915,
					4.690650946872836
				],
				[
					1.3401859848208915,
					6.3658834278988365
				],
				[
					1.675232481025887,
					8.711208901335283
				],
				[
					1.675232481025887,
					10.721487878566506
				],
				[
					1.675232481025887,
					13.066813352002953
				],
				[
					1.675232481025887,
					15.412138825439342
				],
				[
					1.675232481025887,
					17.087371306465343
				],
				[
					2.010278977231337,
					18.427557291286178
				],
				[
					2.010278977231337,
					19.432696779901732
				],
				[
					2.010278977231337,
					20.4378362685174
				],
				[
					2.3453254734363327,
					20.772882764722567
				],
				[
					2.3453254734363327,
					20.772882764722567
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 40,
			"versionNonce": 1178859365,
			"isDeleted": false,
			"id": "IGO_nwNkDL6rZ4V3dNH81",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1669.5115442573667,
			"y": -417.4618777966483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.726627367182118,
			"height": 8.711208901335226,
			"seed": 1527219429,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6700929924104457,
					0
				],
				[
					-2.010278977231337,
					0.335046496205166
				],
				[
					-3.3504649620520013,
					1.005139488615555
				],
				[
					-4.690650946872893,
					2.0102789772312235
				],
				[
					-6.030836931693784,
					2.3453254734363895
				],
				[
					-7.371022916514448,
					3.3504649620520013
				],
				[
					-8.376162405130117,
					4.02055795446239
				],
				[
					-9.046255397540563,
					4.690650946872779
				],
				[
					-9.381301893745785,
					5.360743939283225
				],
				[
					-9.716348389951008,
					5.360743939283225
				],
				[
					-10.051394886156004,
					5.695790435488448
				],
				[
					-10.051394886156004,
					6.030836931693614
				],
				[
					-10.386441382361454,
					6.36588342789878
				],
				[
					-9.381301893745785,
					6.36588342789878
				],
				[
					-8.376162405130117,
					6.36588342789878
				],
				[
					-7.706069412719671,
					6.36588342789878
				],
				[
					-6.70092992410423,
					6.700929924104003
				],
				[
					-6.030836931693784,
					6.700929924104003
				],
				[
					-5.3607439392833385,
					6.700929924104003
				],
				[
					-4.35560445066767,
					7.035976420309225
				],
				[
					-3.685511458257224,
					7.035976420309225
				],
				[
					-3.3504649620520013,
					7.035976420309225
				],
				[
					-3.015418465847006,
					7.035976420309225
				],
				[
					-2.34532547343656,
					7.035976420309225
				],
				[
					-2.010278977231337,
					7.035976420309225
				],
				[
					-1.6752324810261143,
					7.706069412719614
				],
				[
					-1.3401859848208915,
					7.706069412719614
				],
				[
					-1.0051394886156686,
					8.376162405130003
				],
				[
					-0.6700929924104457,
					8.376162405130003
				],
				[
					-0.33504649620522287,
					8.376162405130003
				],
				[
					0,
					8.376162405130003
				],
				[
					0.6700929924102184,
					8.376162405130003
				],
				[
					1.0051394886156686,
					8.711208901335226
				],
				[
					1.340185984820664,
					8.711208901335226
				],
				[
					1.340185984820664,
					8.711208901335226
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 18,
			"versionNonce": 698703211,
			"isDeleted": false,
			"id": "1_PONMLXRWItriKiFmmUj",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1682.9134041055747,
			"y": -417.4618777966483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.72148787856645,
			"height": 0.670092992410332,
			"seed": 677740997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					1.0051394886156686,
					0
				],
				[
					2.6803719696415556,
					0.335046496205166
				],
				[
					3.685511458257224,
					0.335046496205166
				],
				[
					4.35560445066767,
					0.335046496205166
				],
				[
					5.695790435488561,
					0.670092992410332
				],
				[
					6.70092992410423,
					0.670092992410332
				],
				[
					8.041115908924894,
					0.670092992410332
				],
				[
					9.381301893745785,
					0.670092992410332
				],
				[
					10.051394886156004,
					0.670092992410332
				],
				[
					10.386441382361454,
					0.670092992410332
				],
				[
					10.72148787856645,
					0.670092992410332
				],
				[
					10.72148787856645,
					0.670092992410332
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 872006341,
			"isDeleted": false,
			"id": "rcc269JX1hPZvpHQNO4NQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1684.2535900903956,
			"y": -411.76608736115986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.716348389950781,
			"height": 0,
			"seed": 776973413,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6700929924104457,
					0
				],
				[
					1.6752324810261143,
					0
				],
				[
					3.0154184658467784,
					0
				],
				[
					4.35560445066767,
					0
				],
				[
					6.030836931693557,
					0
				],
				[
					7.706069412719671,
					0
				],
				[
					8.711208901335112,
					0
				],
				[
					9.381301893745558,
					0
				],
				[
					9.716348389950781,
					0
				],
				[
					9.716348389950781,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 55,
			"versionNonce": 1938585611,
			"isDeleted": false,
			"id": "ZXZUvmn5EwUXSuXoFaDs6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1718.0932862071204,
			"y": -429.52355166003565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.71120890133534,
			"height": 22.448115245748568,
			"seed": 85712101,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.33504649620522287,
					0
				],
				[
					-1.6752324810261143,
					-1.0051394886156118
				],
				[
					-2.6803719696415556,
					-1.0051394886156118
				],
				[
					-3.685511458257224,
					-1.3401859848207778
				],
				[
					-4.35560445066767,
					-1.3401859848207778
				],
				[
					-5.3607439392833385,
					-1.3401859848207778
				],
				[
					-6.030836931693557,
					-1.3401859848207778
				],
				[
					-6.700929924104003,
					-1.3401859848207778
				],
				[
					-7.035976420309225,
					-1.0051394886156118
				],
				[
					-7.371022916514448,
					-0.6700929924103889
				],
				[
					-7.706069412719671,
					-0.335046496205166
				],
				[
					-8.041115908924894,
					0
				],
				[
					-8.376162405130117,
					0.6700929924104457
				],
				[
					-8.71120890133534,
					1.6752324810260006
				],
				[
					-8.71120890133534,
					2.6803719696416692
				],
				[
					-8.376162405130117,
					3.685511458257224
				],
				[
					-8.041115908924894,
					4.35560445066767
				],
				[
					-7.706069412719671,
					5.695790435488448
				],
				[
					-7.706069412719671,
					6.365883427898893
				],
				[
					-7.706069412719671,
					6.700929924104059
				],
				[
					-7.706069412719671,
					7.035976420309282
				],
				[
					-7.706069412719671,
					7.371022916514448
				],
				[
					-7.706069412719671,
					7.706069412719671
				],
				[
					-7.371022916514448,
					7.706069412719671
				],
				[
					-6.365883427899007,
					7.706069412719671
				],
				[
					-4.35560445066767,
					8.376162405130117
				],
				[
					-3.0154184658467784,
					9.046255397540449
				],
				[
					-1.6752324810261143,
					10.386441382361284
				],
				[
					-1.3401859848208915,
					11.726627367182118
				],
				[
					-1.3401859848208915,
					12.731766855797673
				],
				[
					-1.3401859848208915,
					13.066813352002896
				],
				[
					-1.3401859848208915,
					14.071952840618565
				],
				[
					-1.3401859848208915,
					15.07709232923412
				],
				[
					-1.6752324810261143,
					16.08223181784973
				],
				[
					-2.3453254734363327,
					17.422417802670566
				],
				[
					-2.6803719696415556,
					18.42755729128612
				],
				[
					-3.3504649620520013,
					19.097650283696566
				],
				[
					-4.020557954462447,
					19.767743276106955
				],
				[
					-5.025697443078116,
					20.437836268517344
				],
				[
					-5.695790435488561,
					20.772882764722567
				],
				[
					-7.035976420309225,
					21.10792926092779
				],
				[
					-7.706069412719671,
					21.10792926092779
				],
				[
					-8.041115908924894,
					21.10792926092779
				],
				[
					-8.376162405130117,
					21.10792926092779
				],
				[
					-8.376162405130117,
					20.772882764722567
				],
				[
					-8.71120890133534,
					20.437836268517344
				],
				[
					-8.71120890133534,
					19.767743276106955
				],
				[
					-8.71120890133534,
					19.43269677990179
				],
				[
					-8.71120890133534,
					19.097650283696566
				],
				[
					-8.71120890133534,
					19.097650283696566
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 866066981,
			"isDeleted": false,
			"id": "ApZQ4QfyYPCIzFJEsp32C",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1725.4643091236348,
			"y": -419.47215677387953,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1751647333,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 82,
			"versionNonce": 1385181515,
			"isDeleted": false,
			"id": "V1e7EGo6DHP6-bR2KRdKo",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1742.5516804301,
			"y": -452.6417598981946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.07195284061845,
			"height": 56.6228578586792,
			"seed": 804158795,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.340185984820664,
					0
				],
				[
					-2.3453254734363327,
					0
				],
				[
					-3.3504649620520013,
					0
				],
				[
					-4.35560445066767,
					0
				],
				[
					-5.360743939283111,
					0.33504649620522287
				],
				[
					-6.36588342789878,
					0.33504649620522287
				],
				[
					-6.700929924104003,
					0.33504649620522287
				],
				[
					-7.035976420309225,
					0.33504649620522287
				],
				[
					-7.035976420309225,
					0.6700929924103889
				],
				[
					-7.035976420309225,
					1.0051394886156118
				],
				[
					-7.371022916514448,
					1.6752324810260006
				],
				[
					-7.371022916514448,
					2.0102789772312235
				],
				[
					-7.371022916514448,
					3.0154184658468353
				],
				[
					-7.371022916514448,
					3.685511458257224
				],
				[
					-7.371022916514448,
					4.355604450667613
				],
				[
					-7.035976420309225,
					5.025697443078059
				],
				[
					-6.700929924104003,
					8.37616240513006
				],
				[
					-6.36588342789878,
					9.716348389950838
				],
				[
					-6.36588342789878,
					11.056534374771672
				],
				[
					-6.36588342789878,
					12.061673863387284
				],
				[
					-6.36588342789878,
					13.736906344413285
				],
				[
					-6.36588342789878,
					15.07709232923412
				],
				[
					-6.36588342789878,
					16.75232481026012
				],
				[
					-6.36588342789878,
					18.42755729128612
				],
				[
					-6.36588342789878,
					20.10278977231218
				],
				[
					-6.36588342789878,
					21.77802225333818
				],
				[
					-6.36588342789878,
					23.45325473436418
				],
				[
					-6.36588342789878,
					24.793440719184957
				],
				[
					-6.36588342789878,
					26.468673200211015
				],
				[
					-6.36588342789878,
					27.808859185031793
				],
				[
					-6.36588342789878,
					29.149045169852627
				],
				[
					-6.36588342789878,
					30.824277650878628
				],
				[
					-6.700929924104003,
					32.49951013190463
				],
				[
					-6.700929924104003,
					34.17474261293063
				],
				[
					-7.035976420309225,
					35.84997509395663
				],
				[
					-7.035976420309225,
					36.8551145825723
				],
				[
					-7.035976420309225,
					38.195300567393076
				],
				[
					-7.035976420309225,
					39.53548655221391
				],
				[
					-7.035976420309225,
					40.2055795446243
				],
				[
					-6.700929924104003,
					40.875672537034745
				],
				[
					-6.700929924104003,
					41.8808120256503
				],
				[
					-6.36588342789878,
					42.88595151426591
				],
				[
					-6.36588342789878,
					43.5560445066763
				],
				[
					-6.36588342789878,
					44.56118399529197
				],
				[
					-6.030836931693557,
					45.2312769877023
				],
				[
					-6.030836931693557,
					46.23641647631797
				],
				[
					-5.695790435488334,
					47.91164895734397
				],
				[
					-5.695790435488334,
					48.58174194975436
				],
				[
					-5.695790435488334,
					49.58688143836997
				],
				[
					-5.695790435488334,
					50.25697443078042
				],
				[
					-5.695790435488334,
					51.26211391939597
				],
				[
					-5.695790435488334,
					52.267253408011584
				],
				[
					-5.695790435488334,
					53.272392896627196
				],
				[
					-5.695790435488334,
					53.94248588903764
				],
				[
					-5.695790435488334,
					54.27753238524281
				],
				[
					-5.695790435488334,
					54.61257888144797
				],
				[
					-5.695790435488334,
					54.947625377653196
				],
				[
					-5.695790435488334,
					55.28267187385842
				],
				[
					-5.695790435488334,
					55.61771837006364
				],
				[
					-5.695790435488334,
					55.95276486626881
				],
				[
					-5.695790435488334,
					56.28781136247403
				],
				[
					-5.025697443077888,
					56.6228578586792
				],
				[
					-4.35560445066767,
					56.6228578586792
				],
				[
					-3.0154184658467784,
					56.6228578586792
				],
				[
					-1.675232481025887,
					56.6228578586792
				],
				[
					-0.6700929924104457,
					56.6228578586792
				],
				[
					0.33504649620522287,
					56.6228578586792
				],
				[
					1.6752324810261143,
					56.6228578586792
				],
				[
					2.34532547343656,
					56.6228578586792
				],
				[
					3.3504649620522287,
					56.6228578586792
				],
				[
					3.685511458257224,
					56.6228578586792
				],
				[
					4.35560445066767,
					56.6228578586792
				],
				[
					4.690650946872893,
					56.6228578586792
				],
				[
					5.025697443078116,
					56.6228578586792
				],
				[
					5.3607439392833385,
					56.6228578586792
				],
				[
					6.030836931693784,
					56.6228578586792
				],
				[
					6.365883427899007,
					56.6228578586792
				],
				[
					6.700929924104003,
					56.6228578586792
				],
				[
					6.700929924104003,
					56.6228578586792
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 17,
			"versionNonce": 46046437,
			"isDeleted": false,
			"id": "NkTQful_f6a0cR4xSNRWO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1750.9278428352302,
			"y": -448.62120194373216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.0051394886156686,
			"height": 10.386441382361284,
			"seed": 1699286507,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					1.0051394886156118
				],
				[
					0.33504649620522287,
					2.0102789772311667
				],
				[
					0.6700929924104457,
					2.6803719696416124
				],
				[
					0.6700929924104457,
					4.02055795446239
				],
				[
					1.0051394886156686,
					5.025697443078002
				],
				[
					1.0051394886156686,
					6.3658834278988365
				],
				[
					1.0051394886156686,
					7.706069412719614
				],
				[
					1.0051394886156686,
					8.041115908924837
				],
				[
					1.0051394886156686,
					8.711208901335283
				],
				[
					1.0051394886156686,
					9.381301893745672
				],
				[
					1.0051394886156686,
					9.716348389950838
				],
				[
					1.0051394886156686,
					10.05139488615606
				],
				[
					1.0051394886156686,
					10.386441382361284
				],
				[
					1.0051394886156686,
					10.386441382361284
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 38,
			"versionNonce": 61984747,
			"isDeleted": false,
			"id": "c2u_MssG4N1y0xBcjcMaA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1749.252610354204,
			"y": -424.8329007131628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.700929924104003,
			"height": 8.711208901335226,
			"seed": 1140479979,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3350464962049955,
					-0.335046496205166
				],
				[
					-0.3350464962049955,
					-0.6700929924103889
				],
				[
					-0.3350464962049955,
					-1.0051394886156118
				],
				[
					-0.3350464962049955,
					-2.0102789772311667
				],
				[
					0,
					-3.3504649620520013
				],
				[
					0.6700929924104457,
					-3.685511458257224
				],
				[
					1.6752324810261143,
					-4.02055795446239
				],
				[
					2.34532547343656,
					-4.355604450667613
				],
				[
					3.685511458257224,
					-4.355604450667613
				],
				[
					4.020557954462674,
					-4.355604450667613
				],
				[
					4.35560445066767,
					-4.02055795446239
				],
				[
					4.690650946872893,
					-3.685511458257224
				],
				[
					5.3607439392833385,
					-3.3504649620520013
				],
				[
					6.030836931693784,
					-2.3453254734363895
				],
				[
					6.365883427899007,
					-2.0102789772311667
				],
				[
					6.365883427899007,
					-1.3401859848207778
				],
				[
					6.365883427899007,
					-0.6700929924103889
				],
				[
					6.365883427899007,
					1.0051394886156118
				],
				[
					6.365883427899007,
					1.6752324810260575
				],
				[
					6.030836931693784,
					3.0154184658468353
				],
				[
					5.695790435488561,
					3.685511458257281
				],
				[
					5.3607439392833385,
					4.355604450667613
				],
				[
					4.35560445066767,
					4.355604450667613
				],
				[
					3.685511458257224,
					4.355604450667613
				],
				[
					2.680371969641783,
					4.355604450667613
				],
				[
					2.010278977231337,
					4.355604450667613
				],
				[
					1.0051394886156686,
					4.355604450667613
				],
				[
					0.6700929924104457,
					4.020557954462447
				],
				[
					0.33504649620545024,
					3.685511458257281
				],
				[
					0.33504649620545024,
					3.350464962052058
				],
				[
					0.33504649620545024,
					2.6803719696416124
				],
				[
					0.33504649620545024,
					2.3453254734364464
				],
				[
					0.33504649620545024,
					1.3401859848208346
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
			"version": 41,
			"versionNonce": 621000773,
			"isDeleted": false,
			"id": "LrSJBFdikoaEkt4Jy-Z2a",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1750.592796339025,
			"y": -410.4259013763391,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.035976420309453,
			"height": 8.37616240513006,
			"seed": 1712920843,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725038654,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.33504649620522287
				],
				[
					0.33504649620522287,
					-1.0051394886156118
				],
				[
					1.0051394886156686,
					-1.3401859848207778
				],
				[
					1.6752324810261143,
					-1.6752324810260006
				],
				[
					2.3453254734363327,
					-2.0102789772312235
				],
				[
					2.680371969641783,
					-2.0102789772312235
				],
				[
					3.0154184658467784,
					-2.0102789772312235
				],
				[
					3.3504649620520013,
					-2.0102789772312235
				],
				[
					4.35560445066767,
					-1.6752324810260006
				],
				[
					5.025697443078116,
					-1.0051394886156118
				],
				[
					5.3607439392833385,
					0
				],
				[
					5.695790435488561,
					1.0051394886156118
				],
				[
					6.365883427899007,
					2.3453254734364464
				],
				[
					6.365883427899007,
					3.0154184658467784
				],
				[
					6.365883427899007,
					4.020557954462447
				],
				[
					6.365883427899007,
					5.025697443078002
				],
				[
					6.365883427899007,
					5.360743939283225
				],
				[
					5.695790435488561,
					6.0308369316936705
				],
				[
					4.690650946872893,
					6.0308369316936705
				],
				[
					3.685511458257224,
					6.0308369316936705
				],
				[
					2.680371969641783,
					6.3658834278988365
				],
				[
					2.010278977231337,
					6.3658834278988365
				],
				[
					1.0051394886156686,
					6.3658834278988365
				],
				[
					0.6700929924104457,
					6.3658834278988365
				],
				[
					0.33504649620522287,
					6.3658834278988365
				],
				[
					0,
					6.3658834278988365
				],
				[
					-0.33504649620522287,
					6.0308369316936705
				],
				[
					-0.6700929924104457,
					5.360743939283225
				],
				[
					-0.6700929924104457,
					4.690650946872836
				],
				[
					-0.6700929924104457,
					4.020557954462447
				],
				[
					-0.6700929924104457,
					3.3504649620520013
				],
				[
					-0.6700929924104457,
					3.0154184658467784
				],
				[
					-0.6700929924104457,
					2.3453254734364464
				],
				[
					-0.6700929924104457,
					2.0102789772312235
				],
				[
					-0.6700929924104457,
					1.6752324810260006
				],
				[
					-0.33504649620522287,
					1.0051394886156118
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
			"version": 65,
			"versionNonce": 1760346021,
			"isDeleted": false,
			"id": "OI80yVfsIoLLLwSUHJe9Z",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1750.592796339025,
			"y": -453.6468993868102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.056534374771672,
			"height": 60.6434158131417,
			"seed": 2104037675,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725040631,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6700929924104457,
					0
				],
				[
					2.010278977231337,
					0
				],
				[
					3.0154184658467784,
					0
				],
				[
					4.020557954462447,
					0
				],
				[
					4.690650946872893,
					0
				],
				[
					5.695790435488561,
					0
				],
				[
					6.365883427899007,
					0
				],
				[
					8.041115908924894,
					0.33504649620522287
				],
				[
					9.046255397540563,
					0.6700929924103889
				],
				[
					9.381301893745785,
					0.6700929924103889
				],
				[
					10.051394886156231,
					0.6700929924103889
				],
				[
					10.386441382361227,
					0.6700929924103889
				],
				[
					10.721487878566677,
					0.6700929924103889
				],
				[
					10.386441382361227,
					2.0102789772312235
				],
				[
					10.051394886156231,
					3.3504649620520013
				],
				[
					9.716348389951008,
					4.35560445066767
				],
				[
					9.381301893745785,
					6.0308369316936705
				],
				[
					9.381301893745785,
					7.371022916514448
				],
				[
					9.381301893745785,
					8.711208901335283
				],
				[
					9.381301893745785,
					10.72148787856645
				],
				[
					9.381301893745785,
					13.066813352002896
				],
				[
					9.381301893745785,
					15.07709232923412
				],
				[
					9.716348389951008,
					17.087371306465343
				],
				[
					9.716348389951008,
					20.10278977231212
				],
				[
					10.386441382361227,
					22.448115245748568
				],
				[
					10.386441382361227,
					25.12848721539018
				],
				[
					10.386441382361227,
					27.808859185031793
				],
				[
					10.386441382361227,
					29.819138162263016
				],
				[
					10.386441382361227,
					32.499510131904685
				],
				[
					10.721487878566677,
					35.17988210154624
				],
				[
					10.721487878566677,
					37.52520757498269
				],
				[
					10.721487878566677,
					39.870533048419134
				],
				[
					10.721487878566677,
					41.21071903323991
				],
				[
					10.721487878566677,
					42.88595151426591
				],
				[
					10.721487878566677,
					44.56118399529191
				],
				[
					10.721487878566677,
					45.90136998011275
				],
				[
					10.721487878566677,
					47.24155596493358
				],
				[
					10.721487878566677,
					48.58174194975436
				],
				[
					10.721487878566677,
					49.921927934575194
				],
				[
					10.721487878566677,
					51.26211391939603
				],
				[
					10.721487878566677,
					52.93734640042203
				],
				[
					10.721487878566677,
					54.27753238524281
				],
				[
					10.721487878566677,
					55.28267187385842
				],
				[
					10.721487878566677,
					56.28781136247403
				],
				[
					10.721487878566677,
					56.95790435488442
				],
				[
					10.721487878566677,
					57.29295085108964
				],
				[
					10.721487878566677,
					57.96304384350003
				],
				[
					11.056534374771672,
					58.96818333211564
				],
				[
					11.056534374771672,
					59.30322982832081
				],
				[
					11.056534374771672,
					59.973322820731255
				],
				[
					11.056534374771672,
					60.30836931693648
				],
				[
					11.056534374771672,
					60.6434158131417
				],
				[
					10.386441382361227,
					60.6434158131417
				],
				[
					10.051394886156231,
					60.6434158131417
				],
				[
					9.381301893745785,
					60.6434158131417
				],
				[
					8.71120890133534,
					60.6434158131417
				],
				[
					8.041115908924894,
					59.973322820731255
				],
				[
					6.030836931693784,
					58.96818333211564
				],
				[
					5.3607439392833385,
					58.96818333211564
				],
				[
					5.025697443078116,
					58.96818333211564
				],
				[
					4.35560445066767,
					58.96818333211564
				],
				[
					4.020557954462447,
					58.96818333211564
				],
				[
					4.020557954462447,
					58.96818333211564
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 10,
			"versionNonce": 1053189477,
			"isDeleted": false,
			"id": "ErMen2anfuh8cGEqkmfwC",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1773.711004577184,
			"y": -422.8226217359316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.391580870976895,
			"height": 0,
			"seed": 856808395,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725042063,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.6752324810261143,
					0
				],
				[
					3.0154184658467784,
					0
				],
				[
					5.025697443078116,
					0
				],
				[
					6.700929924104003,
					0
				],
				[
					9.046255397540563,
					0
				],
				[
					10.386441382361227,
					0
				],
				[
					11.391580870976895,
					0
				],
				[
					11.391580870976895,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 1652114437,
			"isDeleted": false,
			"id": "uqKs5cLwZHzp_NLDcjZmO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1778.4016555240569,
			"y": -429.8585981562408,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.01027897723111,
			"height": 13.401859848208062,
			"seed": 737257995,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725042651,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.0051394886156118
				],
				[
					0,
					3.0154184658468353
				],
				[
					0.33504649620522287,
					4.355604450667613
				],
				[
					0.33504649620522287,
					5.695790435488391
				],
				[
					0.33504649620522287,
					7.371022916514448
				],
				[
					0.6700929924104457,
					8.37616240513006
				],
				[
					0.6700929924104457,
					9.381301893745615
				],
				[
					1.0051394886154412,
					10.72148787856645
				],
				[
					1.3401859848208915,
					12.061673863387284
				],
				[
					1.675232481025887,
					12.731766855797673
				],
				[
					2.01027897723111,
					13.066813352002839
				],
				[
					2.01027897723111,
					13.401859848208062
				],
				[
					2.01027897723111,
					13.401859848208062
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 44,
			"versionNonce": 1431220357,
			"isDeleted": false,
			"id": "TyjnpydDCUbu5HJl95peg",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1793.1437013570858,
			"y": -433.2090631182929,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.381301893745785,
			"height": 22.448115245748568,
			"seed": 159848811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725044532,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.33504649620522287
				],
				[
					0,
					1.0051394886156118
				],
				[
					0,
					2.0102789772312235
				],
				[
					0,
					3.350464962052058
				],
				[
					0,
					5.025697443078059
				],
				[
					0,
					6.700929924104059
				],
				[
					0,
					8.711208901335283
				],
				[
					0.33504649620522287,
					11.056534374771672
				],
				[
					0.6700929924104457,
					11.391580870976895
				],
				[
					0.6700929924104457,
					11.726627367182118
				],
				[
					1.3401859848208915,
					11.391580870976895
				],
				[
					2.3453254734363327,
					10.721487878566506
				],
				[
					3.3504649620520013,
					10.051394886156118
				],
				[
					4.35560445066767,
					9.046255397540449
				],
				[
					5.025697443078116,
					8.37616240513006
				],
				[
					6.030836931693557,
					7.371022916514448
				],
				[
					7.035976420309225,
					6.0308369316936705
				],
				[
					7.706069412719671,
					5.025697443078059
				],
				[
					8.041115908924894,
					3.685511458257224
				],
				[
					8.71120890133534,
					2.3453254734364464
				],
				[
					9.046255397540335,
					1.0051394886156118
				],
				[
					9.381301893745785,
					0.33504649620522287
				],
				[
					9.381301893745785,
					0
				],
				[
					9.381301893745785,
					-0.33504649620522287
				],
				[
					9.046255397540335,
					0.6700929924104457
				],
				[
					8.71120890133534,
					1.6752324810260006
				],
				[
					8.71120890133534,
					3.350464962052058
				],
				[
					8.376162405130117,
					5.695790435488448
				],
				[
					8.376162405130117,
					7.371022916514448
				],
				[
					8.041115908924894,
					9.381301893745672
				],
				[
					8.041115908924894,
					11.391580870976895
				],
				[
					8.041115908924894,
					12.061673863387341
				],
				[
					8.041115908924894,
					13.401859848208119
				],
				[
					8.041115908924894,
					14.742045833028897
				],
				[
					8.041115908924894,
					16.08223181784973
				],
				[
					8.376162405130117,
					17.422417802670566
				],
				[
					8.376162405130117,
					18.42755729128612
				],
				[
					8.71120890133534,
					19.767743276106955
				],
				[
					9.046255397540335,
					21.10792926092779
				],
				[
					9.046255397540335,
					21.77802225333818
				],
				[
					9.046255397540335,
					22.113068749543345
				],
				[
					9.046255397540335,
					22.113068749543345
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 5,
			"versionNonce": 1284947301,
			"isDeleted": false,
			"id": "Fqrnb8E9RqHupQ1copj0e",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1806.880607701499,
			"y": -421.14738925490553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.33504649620522287,
			"seed": 36521195,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725044955,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.33504649620522287
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
			"version": 76,
			"versionNonce": 1656604133,
			"isDeleted": false,
			"id": "8Vj21OLE3nV6OPVD0AczW",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1821.6226535345272,
			"y": -453.98194588301544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.736906344413228,
			"height": 57.96304384350003,
			"seed": 428724747,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725048495,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.33504649620545024,
					0
				],
				[
					-0.6700929924104457,
					0
				],
				[
					-2.010278977231337,
					0
				],
				[
					-3.3504649620522287,
					0
				],
				[
					-4.35560445066767,
					0
				],
				[
					-5.695790435488561,
					0
				],
				[
					-7.035976420309453,
					0
				],
				[
					-8.041115908924894,
					0
				],
				[
					-8.041115908924894,
					0.33504649620522287
				],
				[
					-8.041115908924894,
					0.6700929924104457
				],
				[
					-7.7060694127198985,
					1.6752324810260575
				],
				[
					-7.371022916514448,
					2.3453254734364464
				],
				[
					-7.035976420309453,
					3.350464962052058
				],
				[
					-7.035976420309453,
					4.690650946872893
				],
				[
					-6.70092992410423,
					6.365883427898893
				],
				[
					-6.70092992410423,
					7.706069412719671
				],
				[
					-6.365883427899007,
					9.716348389950895
				],
				[
					-6.365883427899007,
					11.056534374771672
				],
				[
					-6.365883427899007,
					12.396720359592507
				],
				[
					-6.365883427899007,
					13.736906344413342
				],
				[
					-6.365883427899007,
					15.07709232923412
				],
				[
					-6.365883427899007,
					16.75232481026012
				],
				[
					-6.365883427899007,
					18.427557291286178
				],
				[
					-6.365883427899007,
					21.10792926092779
				],
				[
					-6.365883427899007,
					23.45325473436418
				],
				[
					-6.70092992410423,
					26.133626704005792
				],
				[
					-7.035976420309453,
					28.143905681237015
				],
				[
					-7.035976420309453,
					30.15418465846824
				],
				[
					-7.035976420309453,
					31.82941713949424
				],
				[
					-7.035976420309453,
					32.83455662810991
				],
				[
					-7.035976420309453,
					34.174742612930686
				],
				[
					-7.035976420309453,
					35.514928597751464
				],
				[
					-7.035976420309453,
					36.18502159016191
				],
				[
					-7.035976420309453,
					37.190161078777464
				],
				[
					-7.035976420309453,
					38.86539355980352
				],
				[
					-7.035976420309453,
					40.54062604082952
				],
				[
					-7.035976420309453,
					41.88081202565036
				],
				[
					-7.371022916514448,
					43.220998010471135
				],
				[
					-7.371022916514448,
					44.56118399529197
				],
				[
					-7.371022916514448,
					45.901369980112804
				],
				[
					-7.371022916514448,
					46.90650946872836
				],
				[
					-7.371022916514448,
					47.91164895734403
				],
				[
					-7.371022916514448,
					48.91678844595958
				],
				[
					-7.371022916514448,
					49.58688143837003
				],
				[
					-7.371022916514448,
					50.25697443078042
				],
				[
					-7.371022916514448,
					50.59202092698558
				],
				[
					-7.371022916514448,
					51.59716041560125
				],
				[
					-7.371022916514448,
					52.267253408011584
				],
				[
					-7.371022916514448,
					52.93734640042203
				],
				[
					-7.371022916514448,
					53.94248588903764
				],
				[
					-7.371022916514448,
					54.61257888144803
				],
				[
					-7.371022916514448,
					55.61771837006364
				],
				[
					-7.371022916514448,
					56.28781136247403
				],
				[
					-7.371022916514448,
					56.622857858679254
				],
				[
					-7.371022916514448,
					56.95790435488448
				],
				[
					-7.371022916514448,
					57.29295085108964
				],
				[
					-7.371022916514448,
					57.627997347294865
				],
				[
					-7.371022916514448,
					57.96304384350003
				],
				[
					-6.365883427899007,
					57.96304384350003
				],
				[
					-4.690650946872893,
					57.96304384350003
				],
				[
					-3.3504649620522287,
					57.96304384350003
				],
				[
					-2.010278977231337,
					57.96304384350003
				],
				[
					-1.0051394886156686,
					57.96304384350003
				],
				[
					0,
					57.96304384350003
				],
				[
					1.0051394886154412,
					57.96304384350003
				],
				[
					1.675232481025887,
					57.96304384350003
				],
				[
					2.6803719696415556,
					57.96304384350003
				],
				[
					3.685511458257224,
					57.96304384350003
				],
				[
					4.690650946872665,
					57.96304384350003
				],
				[
					5.025697443077888,
					57.96304384350003
				],
				[
					5.360743939283111,
					57.96304384350003
				],
				[
					5.695790435488334,
					57.96304384350003
				],
				[
					5.695790435488334,
					57.29295085108964
				],
				[
					5.695790435488334,
					57.29295085108964
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 52,
			"versionNonce": 200764773,
			"isDeleted": false,
			"id": "AOoZ_ezQwOS8mpTU34zJp",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1828.3235834586312,
			"y": -442.59036501203855,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.041115908924894,
			"height": 8.041115908924894,
			"seed": 2062918027,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725049946,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.33504649620522287,
					0
				],
				[
					-0.6700929924104457,
					-0.33504649620522287
				],
				[
					-1.0051394886156686,
					-0.33504649620522287
				],
				[
					-1.3401859848208915,
					-1.0051394886156118
				],
				[
					-1.3401859848208915,
					-1.3401859848207778
				],
				[
					-1.3401859848208915,
					-1.6752324810260006
				],
				[
					-0.33504649620522287,
					-1.6752324810260006
				],
				[
					0,
					-1.6752324810260006
				],
				[
					1.3401859848208915,
					-1.6752324810260006
				],
				[
					2.01027897723111,
					-1.6752324810260006
				],
				[
					3.0154184658467784,
					-1.6752324810260006
				],
				[
					3.685511458257224,
					-1.3401859848207778
				],
				[
					4.35560445066767,
					-0.6700929924103889
				],
				[
					5.025697443078116,
					0.33504649620522287
				],
				[
					5.695790435488334,
					1.0051394886156118
				],
				[
					5.695790435488334,
					1.6752324810260006
				],
				[
					6.030836931693557,
					2.6803719696416692
				],
				[
					6.030836931693557,
					3.685511458257224
				],
				[
					6.030836931693557,
					5.025697443078059
				],
				[
					6.030836931693557,
					6.0308369316936705
				],
				[
					6.030836931693557,
					6.365883427898893
				],
				[
					5.360743939283111,
					6.365883427898893
				],
				[
					4.35560445066767,
					6.365883427898893
				],
				[
					3.0154184658467784,
					6.365883427898893
				],
				[
					2.01027897723111,
					6.365883427898893
				],
				[
					0.6700929924104457,
					6.365883427898893
				],
				[
					0,
					6.0308369316936705
				],
				[
					-0.33504649620522287,
					5.695790435488448
				],
				[
					-0.6700929924104457,
					5.360743939283225
				],
				[
					-1.0051394886156686,
					4.690650946872836
				],
				[
					-1.3401859848208915,
					4.020557954462447
				],
				[
					-1.3401859848208915,
					3.685511458257224
				],
				[
					-1.6752324810261143,
					3.350464962052058
				],
				[
					-2.010278977231337,
					3.0154184658468353
				],
				[
					-2.010278977231337,
					2.3453254734364464
				],
				[
					-2.010278977231337,
					2.0102789772312235
				],
				[
					-2.010278977231337,
					1.6752324810260006
				],
				[
					-2.010278977231337,
					1.3401859848208346
				],
				[
					-2.010278977231337,
					1.0051394886156118
				],
				[
					-2.010278977231337,
					0.6700929924104457
				],
				[
					-2.010278977231337,
					0
				],
				[
					-2.010278977231337,
					-0.33504649620522287
				],
				[
					-1.6752324810261143,
					-0.33504649620522287
				],
				[
					-1.6752324810261143,
					-1.0051394886156118
				],
				[
					-1.3401859848208915,
					-1.3401859848207778
				],
				[
					-1.0051394886156686,
					-1.3401859848207778
				],
				[
					-0.6700929924104457,
					-1.3401859848207778
				],
				[
					-0.33504649620522287,
					-1.3401859848207778
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
			"version": 20,
			"versionNonce": 1687300325,
			"isDeleted": false,
			"id": "cKbk3scJ3Xh7K7HEhODMY",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1830.6689089320676,
			"y": -427.84831917900965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.33504649620522287,
			"height": 12.73176685579773,
			"seed": 1694900747,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725050849,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.33504649620522287
				],
				[
					0,
					1.0051394886156686
				],
				[
					0,
					1.6752324810260575
				],
				[
					0,
					3.0154184658468353
				],
				[
					0,
					3.685511458257224
				],
				[
					0,
					5.025697443078059
				],
				[
					0,
					6.0308369316936705
				],
				[
					0,
					7.035976420309282
				],
				[
					0,
					8.376162405130117
				],
				[
					0,
					9.046255397540506
				],
				[
					0,
					9.381301893745672
				],
				[
					0.33504649620522287,
					10.051394886156118
				],
				[
					0.33504649620522287,
					10.38644138236134
				],
				[
					0.33504649620522287,
					11.056534374771672
				],
				[
					0.33504649620522287,
					11.726627367182118
				],
				[
					0.33504649620522287,
					12.396720359592564
				],
				[
					0.33504649620522287,
					12.73176685579773
				],
				[
					0.33504649620522287,
					12.73176685579773
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 54,
			"versionNonce": 1793669925,
			"isDeleted": false,
			"id": "K5C3NoasSIlgFz_l5Xr9r",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1828.6586299548364,
			"y": -406.40534342187664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.716348389951008,
			"height": 7.035976420309282,
			"seed": 719015563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725052302,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.33504649620522287
				],
				[
					0.6700929924102184,
					-0.6700929924104457
				],
				[
					1.0051394886156686,
					-1.3401859848208346
				],
				[
					1.340185984820664,
					-1.3401859848208346
				],
				[
					2.01027897723111,
					-1.3401859848208346
				],
				[
					2.3453254734363327,
					-1.3401859848208346
				],
				[
					2.6803719696415556,
					-1.0051394886156686
				],
				[
					3.0154184658467784,
					-0.6700929924104457
				],
				[
					3.685511458257224,
					-0.33504649620522287
				],
				[
					3.685511458257224,
					0.33504649620522287
				],
				[
					4.020557954462447,
					1.3401859848207778
				],
				[
					4.020557954462447,
					1.6752324810260006
				],
				[
					4.020557954462447,
					2.3453254734363895
				],
				[
					4.020557954462447,
					2.6803719696416124
				],
				[
					4.020557954462447,
					3.0154184658467784
				],
				[
					3.685511458257224,
					3.685511458257224
				],
				[
					3.3504649620520013,
					4.355604450667613
				],
				[
					3.0154184658467784,
					4.690650946872779
				],
				[
					2.6803719696415556,
					5.025697443078002
				],
				[
					1.675232481025887,
					5.360743939283225
				],
				[
					1.340185984820664,
					5.360743939283225
				],
				[
					0.6700929924102184,
					5.360743939283225
				],
				[
					0.33504649620522287,
					5.695790435488448
				],
				[
					0,
					5.695790435488448
				],
				[
					-0.6700929924104457,
					5.695790435488448
				],
				[
					-1.3401859848208915,
					5.695790435488448
				],
				[
					-2.010278977231337,
					5.360743939283225
				],
				[
					-2.34532547343656,
					5.025697443078002
				],
				[
					-3.3504649620520013,
					4.355604450667613
				],
				[
					-3.685511458257224,
					4.020557954462447
				],
				[
					-4.020557954462447,
					3.685511458257224
				],
				[
					-4.690650946872893,
					3.3504649620520013
				],
				[
					-5.025697443078116,
					2.6803719696416124
				],
				[
					-5.695790435488561,
					2.0102789772312235
				],
				[
					-5.695790435488561,
					1.6752324810260006
				],
				[
					-5.695790435488561,
					1.3401859848207778
				],
				[
					-5.695790435488561,
					0.33504649620522287
				],
				[
					-5.025697443078116,
					0
				],
				[
					-4.690650946872893,
					-0.33504649620522287
				],
				[
					-4.020557954462447,
					-0.33504649620522287
				],
				[
					-3.685511458257224,
					-0.6700929924104457
				],
				[
					-3.3504649620520013,
					-0.6700929924104457
				],
				[
					-3.015418465847006,
					-0.6700929924104457
				],
				[
					-2.680371969641783,
					-0.6700929924104457
				],
				[
					-2.34532547343656,
					-0.6700929924104457
				],
				[
					-2.010278977231337,
					-0.6700929924104457
				],
				[
					-1.6752324810261143,
					-0.6700929924104457
				],
				[
					-1.0051394886156686,
					-0.6700929924104457
				],
				[
					-0.6700929924104457,
					-0.6700929924104457
				],
				[
					-0.33504649620522287,
					-0.6700929924104457
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
			"version": 62,
			"versionNonce": 2131273829,
			"isDeleted": false,
			"id": "O_qTW1bSdgCCrPSEDHLDD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1834.3544203903248,
			"y": -449.6263414323478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.71120890133534,
			"height": 54.947625377653196,
			"seed": 305743947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725054130,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6700929924104457,
					0
				],
				[
					1.6752324810261143,
					0
				],
				[
					2.680371969641783,
					0
				],
				[
					3.3504649620520013,
					0
				],
				[
					4.020557954462447,
					0.33504649620522287
				],
				[
					5.025697443078116,
					0.6700929924103889
				],
				[
					5.695790435488561,
					0.6700929924103889
				],
				[
					6.365883427899007,
					1.0051394886156118
				],
				[
					6.700929924104003,
					1.6752324810260006
				],
				[
					7.035976420309225,
					2.0102789772312235
				],
				[
					7.706069412719671,
					3.3504649620520013
				],
				[
					7.706069412719671,
					4.020557954462447
				],
				[
					7.706069412719671,
					5.025697443078002
				],
				[
					8.041115908924894,
					6.030836931693614
				],
				[
					8.041115908924894,
					7.035976420309225
				],
				[
					8.041115908924894,
					8.041115908924837
				],
				[
					8.041115908924894,
					11.726627367182061
				],
				[
					7.371022916514448,
					14.071952840618508
				],
				[
					7.371022916514448,
					16.417278314054897
				],
				[
					7.371022916514448,
					18.092510795080898
				],
				[
					7.371022916514448,
					21.107929260927733
				],
				[
					7.371022916514448,
					24.12334772677457
				],
				[
					7.371022916514448,
					26.133626704005792
				],
				[
					7.035976420309225,
					30.489231154673405
				],
				[
					7.035976420309225,
					31.82941713949424
				],
				[
					7.035976420309225,
					34.50978910913585
				],
				[
					7.035976420309225,
					37.52520757498269
				],
				[
					6.700929924104003,
					39.53548655221391
				],
				[
					6.365883427899007,
					41.21071903323991
				],
				[
					6.365883427899007,
					42.215858521855466
				],
				[
					6.030836931693557,
					43.220998010471135
				],
				[
					6.030836931693557,
					43.891091002881524
				],
				[
					5.695790435488561,
					44.56118399529191
				],
				[
					5.695790435488561,
					45.23127698770236
				],
				[
					5.3607439392833385,
					46.90650946872836
				],
				[
					5.3607439392833385,
					47.57660246113875
				],
				[
					5.3607439392833385,
					48.58174194975436
				],
				[
					5.3607439392833385,
					49.25183494216475
				],
				[
					5.3607439392833385,
					49.92192793457514
				],
				[
					5.3607439392833385,
					51.26211391939597
				],
				[
					5.3607439392833385,
					51.93220691180636
				],
				[
					5.3607439392833385,
					52.267253408011584
				],
				[
					5.3607439392833385,
					52.60229990421681
				],
				[
					5.695790435488561,
					52.93734640042197
				],
				[
					5.695790435488561,
					53.60743939283236
				],
				[
					5.695790435488561,
					53.942485889037584
				],
				[
					5.695790435488561,
					54.27753238524281
				],
				[
					5.3607439392833385,
					54.61257888144803
				],
				[
					5.025697443078116,
					54.947625377653196
				],
				[
					4.35560445066767,
					54.947625377653196
				],
				[
					3.3504649620520013,
					54.947625377653196
				],
				[
					2.3453254734363327,
					54.947625377653196
				],
				[
					1.6752324810261143,
					54.947625377653196
				],
				[
					1.0051394886156686,
					54.947625377653196
				],
				[
					0.6700929924104457,
					54.947625377653196
				],
				[
					0.33504649620522287,
					54.947625377653196
				],
				[
					0,
					54.947625377653196
				],
				[
					-0.33504649620522287,
					54.947625377653196
				],
				[
					-0.6700929924104457,
					54.947625377653196
				],
				[
					-0.6700929924104457,
					54.947625377653196
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 13,
			"versionNonce": 186152005,
			"isDeleted": false,
			"id": "O6j7exPNm09eKlnrUynmz",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1852.4469311854057,
			"y": -424.4978542169576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.056534374771672,
			"height": 1.6752324810260006,
			"seed": 984839947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725054966,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.335046496205166
				],
				[
					0.6700929924104457,
					0.335046496205166
				],
				[
					2.010278977231337,
					0.335046496205166
				],
				[
					3.3504649620520013,
					0.335046496205166
				],
				[
					4.690650946872893,
					0.335046496205166
				],
				[
					6.70092992410423,
					0.335046496205166
				],
				[
					8.71120890133534,
					0
				],
				[
					9.716348389951008,
					-0.33504649620522287
				],
				[
					10.72148787856645,
					-1.0051394886156118
				],
				[
					11.056534374771672,
					-1.3401859848208346
				],
				[
					11.056534374771672,
					-1.3401859848208346
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 15,
			"versionNonce": 754577125,
			"isDeleted": false,
			"id": "xuG7PmLl-jBiPGK1eqwu8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1859.14786110951,
			"y": -429.52355166003565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 9.381301893745672,
			"seed": 164468011,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725055466,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.33504649620522287
				],
				[
					0,
					0.6700929924104457
				],
				[
					0,
					1.3401859848208346
				],
				[
					0,
					2.3453254734364464
				],
				[
					0,
					3.0154184658468353
				],
				[
					0,
					4.020557954462447
				],
				[
					0,
					5.025697443078059
				],
				[
					0,
					5.695790435488448
				],
				[
					0,
					7.035976420309282
				],
				[
					0,
					8.041115908924894
				],
				[
					0,
					9.046255397540449
				],
				[
					0,
					9.381301893745672
				],
				[
					0,
					9.381301893745672
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 52,
			"versionNonce": 1199642213,
			"isDeleted": false,
			"id": "vErG-_bhlxjkqg3Xd6zd6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1872.2146744615127,
			"y": -433.5441096144981,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.391580870976895,
			"height": 15.747185321644508,
			"seed": 926394507,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725056849,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6700929924104457,
					-0.335046496205166
				],
				[
					1.0051394886156686,
					-0.335046496205166
				],
				[
					2.34532547343656,
					-0.335046496205166
				],
				[
					3.685511458257224,
					-0.335046496205166
				],
				[
					5.3607439392833385,
					-0.335046496205166
				],
				[
					7.035976420309225,
					0
				],
				[
					7.706069412719671,
					0.33504649620522287
				],
				[
					8.041115908924894,
					1.0051394886156686
				],
				[
					8.376162405130117,
					2.0102789772312235
				],
				[
					8.376162405130117,
					2.6803719696416692
				],
				[
					8.71120890133534,
					4.020557954462447
				],
				[
					8.041115908924894,
					5.695790435488448
				],
				[
					7.706069412719671,
					7.035976420309282
				],
				[
					6.36588342789878,
					9.046255397540506
				],
				[
					5.025697443078116,
					10.38644138236134
				],
				[
					4.020557954462447,
					11.726627367182118
				],
				[
					2.6803719696415556,
					13.066813352002896
				],
				[
					1.6752324810261143,
					13.401859848208119
				],
				[
					0.6700929924104457,
					13.736906344413342
				],
				[
					0,
					13.736906344413342
				],
				[
					-0.33504649620522287,
					13.736906344413342
				],
				[
					-1.340185984820664,
					13.736906344413342
				],
				[
					-1.6752324810261143,
					13.736906344413342
				],
				[
					-2.3453254734363327,
					13.736906344413342
				],
				[
					-2.6803719696415556,
					13.736906344413342
				],
				[
					-2.6803719696415556,
					13.401859848208119
				],
				[
					-2.6803719696415556,
					13.066813352002896
				],
				[
					-2.6803719696415556,
					12.73176685579773
				],
				[
					-2.6803719696415556,
					11.726627367182118
				],
				[
					-2.6803719696415556,
					11.391580870976895
				],
				[
					-2.01027897723111,
					10.38644138236134
				],
				[
					-1.6752324810261143,
					10.051394886156118
				],
				[
					-1.0051394886156686,
					10.051394886156118
				],
				[
					-0.33504649620522287,
					10.051394886156118
				],
				[
					0.33504649620522287,
					10.051394886156118
				],
				[
					1.0051394886156686,
					10.051394886156118
				],
				[
					1.6752324810261143,
					10.38644138236134
				],
				[
					2.34532547343656,
					10.38644138236134
				],
				[
					3.0154184658467784,
					10.721487878566506
				],
				[
					3.685511458257224,
					11.05653437477173
				],
				[
					4.020557954462447,
					12.061673863387341
				],
				[
					4.690650946872893,
					13.066813352002896
				],
				[
					5.025697443078116,
					14.071952840618565
				],
				[
					5.3607439392833385,
					14.40699933682373
				],
				[
					5.695790435488334,
					14.742045833028953
				],
				[
					5.695790435488334,
					15.07709232923412
				],
				[
					6.030836931693784,
					15.412138825439342
				],
				[
					6.36588342789878,
					15.412138825439342
				],
				[
					6.700929924104003,
					15.412138825439342
				],
				[
					6.700929924104003,
					15.412138825439342
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 3,
			"versionNonce": 643765381,
			"isDeleted": false,
			"id": "-ZaAjSUvOU_hXoc02I07s",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1884.9464413173105,
			"y": -422.8226217359316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1749199115,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725057146,
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
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 57,
			"versionNonce": 1474529509,
			"isDeleted": false,
			"id": "YRI4kNSF_kSy5wG2gjA-E",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1905.0492310896225,
			"y": -451.636620409579,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.752324810260006,
			"height": 56.95790435488442,
			"seed": 208249067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725058910,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					-1.3401859848208915,
					0
				],
				[
					-3.685511458257224,
					-0.33504649620522287
				],
				[
					-6.030836931693557,
					-1.0051394886156118
				],
				[
					-9.716348389950781,
					-1.0051394886156118
				],
				[
					-13.401859848208005,
					-1.0051394886156118
				],
				[
					-14.406999336823674,
					-1.0051394886156118
				],
				[
					-15.07709232923412,
					-0.6700929924103889
				],
				[
					-15.747185321644338,
					-0.33504649620522287
				],
				[
					-16.082231817849788,
					0
				],
				[
					-16.082231817849788,
					0.6700929924103889
				],
				[
					-16.417278314054784,
					2.3453254734364464
				],
				[
					-16.417278314054784,
					2.6803719696416124
				],
				[
					-16.082231817849788,
					4.020557954462447
				],
				[
					-15.747185321644338,
					5.025697443078002
				],
				[
					-15.412138825439342,
					6.3658834278988365
				],
				[
					-15.07709232923412,
					7.371022916514448
				],
				[
					-14.742045833028897,
					8.37616240513006
				],
				[
					-13.401859848208005,
					11.726627367182118
				],
				[
					-13.066813352002782,
					14.406999336823674
				],
				[
					-13.066813352002782,
					16.417278314054897
				],
				[
					-13.066813352002782,
					19.097650283696566
				],
				[
					-12.73176685579756,
					21.77802225333818
				],
				[
					-12.73176685579756,
					24.45839422297979
				],
				[
					-12.396720359592564,
					26.80371969641618
				],
				[
					-12.061673863387114,
					29.484091666057793
				],
				[
					-11.726627367182118,
					31.494370643289017
				],
				[
					-11.391580870976895,
					34.50978910913585
				],
				[
					-11.056534374771672,
					36.520068086367075
				],
				[
					-11.056534374771672,
					38.195300567393076
				],
				[
					-11.056534374771672,
					39.53548655221391
				],
				[
					-10.72148787856645,
					40.87567253703469
				],
				[
					-10.72148787856645,
					42.55090501806069
				],
				[
					-10.72148787856645,
					44.22613749908669
				],
				[
					-10.386441382361227,
					45.23127698770236
				],
				[
					-10.386441382361227,
					46.571462972523136
				],
				[
					-10.386441382361227,
					47.57660246113875
				],
				[
					-10.386441382361227,
					48.91678844595958
				],
				[
					-10.386441382361227,
					49.92192793457514
				],
				[
					-10.386441382361227,
					50.927067423190806
				],
				[
					-10.386441382361227,
					51.93220691180636
				],
				[
					-10.386441382361227,
					52.93734640042203
				],
				[
					-10.386441382361227,
					53.60743939283236
				],
				[
					-10.386441382361227,
					54.27753238524281
				],
				[
					-10.72148787856645,
					54.61257888144803
				],
				[
					-10.72148787856645,
					54.947625377653196
				],
				[
					-9.716348389950781,
					54.947625377653196
				],
				[
					-8.71120890133534,
					54.947625377653196
				],
				[
					-7.706069412719671,
					54.947625377653196
				],
				[
					-6.700929924104003,
					55.28267187385842
				],
				[
					-5.360743939283111,
					55.28267187385842
				],
				[
					-4.020557954462447,
					55.617718370063585
				],
				[
					-3.3504649620520013,
					55.95276486626881
				],
				[
					-3.0154184658467784,
					55.95276486626881
				],
				[
					-3.0154184658467784,
					55.95276486626881
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 43,
			"versionNonce": 1953705477,
			"isDeleted": false,
			"id": "dw3-jeq7_A4aT6QLD7wWb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1905.719324082033,
			"y": -440.5800860348073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.716348389951008,
			"height": 9.381301893745672,
			"seed": 272363147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725060120,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.0051394886156686,
					0
				],
				[
					-1.675232481025887,
					-0.33504649620522287
				],
				[
					-2.6803719696415556,
					-1.0051394886156118
				],
				[
					-3.3504649620520013,
					-1.3401859848207778
				],
				[
					-3.685511458257224,
					-1.3401859848207778
				],
				[
					-4.020557954462447,
					-2.0102789772312235
				],
				[
					-4.020557954462447,
					-2.3453254734364464
				],
				[
					-4.35560445066767,
					-3.0154184658468353
				],
				[
					-4.35560445066767,
					-3.685511458257224
				],
				[
					-4.020557954462447,
					-4.355604450667613
				],
				[
					-3.0154184658467784,
					-5.025697443078002
				],
				[
					-2.010278977231337,
					-5.360743939283225
				],
				[
					-0.6700929924104457,
					-5.695790435488448
				],
				[
					0,
					-6.0308369316936705
				],
				[
					1.0051394886156686,
					-6.0308369316936705
				],
				[
					2.010278977231337,
					-6.3658834278988365
				],
				[
					2.6803719696415556,
					-6.3658834278988365
				],
				[
					3.3504649620520013,
					-6.3658834278988365
				],
				[
					3.685511458257224,
					-6.3658834278988365
				],
				[
					4.35560445066767,
					-5.695790435488448
				],
				[
					4.35560445066767,
					-5.025697443078002
				],
				[
					4.690650946872893,
					-4.355604450667613
				],
				[
					5.025697443078116,
					-3.685511458257224
				],
				[
					5.025697443078116,
					-3.0154184658468353
				],
				[
					5.3607439392833385,
					-2.0102789772312235
				],
				[
					5.3607439392833385,
					-1.0051394886156118
				],
				[
					5.3607439392833385,
					0
				],
				[
					5.3607439392833385,
					0.6700929924104457
				],
				[
					5.3607439392833385,
					1.6752324810260006
				],
				[
					5.3607439392833385,
					2.3453254734364464
				],
				[
					4.690650946872893,
					3.0154184658468353
				],
				[
					4.020557954462447,
					3.0154184658468353
				],
				[
					3.3504649620520013,
					3.0154184658468353
				],
				[
					2.6803719696415556,
					2.6803719696416124
				],
				[
					2.3453254734363327,
					2.6803719696416124
				],
				[
					2.010278977231337,
					2.6803719696416124
				],
				[
					1.6752324810261143,
					2.6803719696416124
				],
				[
					1.3401859848208915,
					2.6803719696416124
				],
				[
					1.0051394886156686,
					2.6803719696416124
				],
				[
					0.6700929924104457,
					2.6803719696416124
				],
				[
					0.6700929924104457,
					2.6803719696416124
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 46,
			"versionNonce": 1261862213,
			"isDeleted": false,
			"id": "MwH1Ni3FHDm0Z5ZPDBRXl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1906.0543705782381,
			"y": -431.5338306372669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.0565343747719,
			"height": 9.046255397540449,
			"seed": 273813355,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725061495,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33504649620522287,
					0
				],
				[
					1.0051394886156686,
					0
				],
				[
					1.6752324810261143,
					0
				],
				[
					3.0154184658467784,
					0.33504649620522287
				],
				[
					3.685511458257224,
					0.33504649620522287
				],
				[
					4.35560445066767,
					0.6700929924104457
				],
				[
					4.690650946872893,
					1.3401859848208346
				],
				[
					5.025697443078116,
					2.0102789772312235
				],
				[
					5.025697443078116,
					2.6803719696416692
				],
				[
					5.025697443078116,
					3.350464962052058
				],
				[
					5.025697443078116,
					4.690650946872893
				],
				[
					4.690650946872893,
					5.025697443078059
				],
				[
					4.35560445066767,
					6.365883427898893
				],
				[
					3.685511458257224,
					7.035976420309282
				],
				[
					3.0154184658467784,
					7.706069412719671
				],
				[
					2.01027897723111,
					7.706069412719671
				],
				[
					1.0051394886156686,
					8.041115908924894
				],
				[
					0,
					8.041115908924894
				],
				[
					-1.3401859848208915,
					8.041115908924894
				],
				[
					-2.6803719696415556,
					8.041115908924894
				],
				[
					-3.3504649620520013,
					8.041115908924894
				],
				[
					-4.35560445066767,
					7.706069412719671
				],
				[
					-4.690650946872893,
					7.371022916514448
				],
				[
					-5.025697443078116,
					6.700929924104059
				],
				[
					-5.3607439392833385,
					6.0308369316936705
				],
				[
					-5.695790435488334,
					4.690650946872893
				],
				[
					-6.030836931693784,
					3.685511458257224
				],
				[
					-6.030836931693784,
					3.0154184658468353
				],
				[
					-6.030836931693784,
					2.3453254734364464
				],
				[
					-6.030836931693784,
					2.0102789772312235
				],
				[
					-5.3607439392833385,
					1.6752324810260575
				],
				[
					-5.025697443078116,
					1.3401859848208346
				],
				[
					-4.35560445066767,
					0.6700929924104457
				],
				[
					-3.685511458257224,
					0
				],
				[
					-3.3504649620520013,
					-0.335046496205166
				],
				[
					-2.6803719696415556,
					-0.6700929924103889
				],
				[
					-2.6803719696415556,
					-1.005139488615555
				],
				[
					-2.34532547343656,
					-0.6700929924103889
				],
				[
					-2.01027897723111,
					-0.335046496205166
				],
				[
					-1.3401859848208915,
					0
				],
				[
					-0.6700929924104457,
					0.33504649620522287
				],
				[
					-0.33504649620522287,
					0.33504649620522287
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
			"version": 26,
			"versionNonce": 246706437,
			"isDeleted": false,
			"id": "u7c0kDhnT0lS_dcmnTWQd",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1908.7347425478797,
			"y": -417.79692429285353,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.33504649620522287,
			"height": 15.747185321644508,
			"seed": 892845099,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725062368,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.33504649620522287
				],
				[
					0,
					0.6700929924103889
				],
				[
					0,
					1.3401859848207778
				],
				[
					0,
					2.0102789772312235
				],
				[
					0,
					4.020557954462447
				],
				[
					0,
					4.690650946872836
				],
				[
					0,
					6.0308369316936705
				],
				[
					0,
					7.371022916514448
				],
				[
					0,
					8.37616240513006
				],
				[
					0.33504649620522287,
					9.046255397540449
				],
				[
					0.33504649620522287,
					10.05139488615606
				],
				[
					0.33504649620522287,
					10.72148787856645
				],
				[
					0.33504649620522287,
					11.726627367182118
				],
				[
					0.33504649620522287,
					12.731766855797673
				],
				[
					0.33504649620522287,
					13.401859848208119
				],
				[
					0.33504649620522287,
					14.071952840618508
				],
				[
					0.33504649620522287,
					14.406999336823674
				],
				[
					0.33504649620522287,
					14.742045833028897
				],
				[
					0.33504649620522287,
					15.07709232923412
				],
				[
					0.33504649620522287,
					15.412138825439342
				],
				[
					0.33504649620522287,
					15.747185321644508
				],
				[
					0.33504649620522287,
					15.07709232923412
				],
				[
					0.33504649620522287,
					14.742045833028897
				],
				[
					0.33504649620522287,
					14.742045833028897
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 65,
			"versionNonce": 1487036517,
			"isDeleted": false,
			"id": "s1zMPyeZVSIvwRugtsv4J",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1912.7553005023422,
			"y": -451.636620409579,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.386441382361227,
			"height": 55.617718370063585,
			"seed": 1382341739,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725064093,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6700929924104457,
					0
				],
				[
					1.3401859848208915,
					0
				],
				[
					2.34532547343656,
					0.33504649620522287
				],
				[
					3.3504649620520013,
					0.6700929924103889
				],
				[
					3.685511458257224,
					0.6700929924103889
				],
				[
					5.025697443078116,
					1.0051394886156118
				],
				[
					5.3607439392833385,
					1.3401859848207778
				],
				[
					6.030836931693784,
					1.6752324810260006
				],
				[
					6.36588342789878,
					1.6752324810260006
				],
				[
					7.035976420309225,
					2.3453254734364464
				],
				[
					7.371022916514448,
					3.0154184658468353
				],
				[
					7.371022916514448,
					3.685511458257224
				],
				[
					7.371022916514448,
					5.025697443078002
				],
				[
					7.371022916514448,
					6.0308369316936705
				],
				[
					7.371022916514448,
					7.371022916514448
				],
				[
					7.371022916514448,
					9.381301893745672
				],
				[
					7.035976420309225,
					11.726627367182118
				],
				[
					7.035976420309225,
					13.401859848208119
				],
				[
					6.70092992410423,
					15.07709232923412
				],
				[
					6.030836931693784,
					17.42241780267051
				],
				[
					5.695790435488561,
					19.767743276106955
				],
				[
					5.3607439392833385,
					22.113068749543345
				],
				[
					4.690650946872893,
					25.12848721539018
				],
				[
					4.35560445066767,
					27.808859185031793
				],
				[
					4.35560445066767,
					29.819138162263016
				],
				[
					4.35560445066767,
					31.494370643289017
				],
				[
					4.020557954462447,
					33.50464962052024
				],
				[
					4.020557954462447,
					35.17988210154624
				],
				[
					4.020557954462447,
					36.520068086367075
				],
				[
					3.685511458257224,
					38.5303470635983
				],
				[
					3.685511458257224,
					39.53548655221391
				],
				[
					3.685511458257224,
					40.2055795446243
				],
				[
					3.685511458257224,
					41.21071903323991
				],
				[
					3.685511458257224,
					42.21585852185552
				],
				[
					3.685511458257224,
					42.88595151426591
				],
				[
					3.685511458257224,
					43.891091002881524
				],
				[
					3.685511458257224,
					44.56118399529191
				],
				[
					4.020557954462447,
					46.23641647631791
				],
				[
					4.020557954462447,
					46.90650946872836
				],
				[
					4.020557954462447,
					47.91164895734397
				],
				[
					4.020557954462447,
					48.24669545354914
				],
				[
					4.35560445066767,
					48.91678844595958
				],
				[
					4.35560445066767,
					49.251834942164805
				],
				[
					4.35560445066767,
					49.58688143836997
				],
				[
					4.35560445066767,
					49.92192793457514
				],
				[
					4.35560445066767,
					50.25697443078036
				],
				[
					4.35560445066767,
					50.59202092698558
				],
				[
					4.35560445066767,
					50.927067423190806
				],
				[
					4.020557954462447,
					51.26211391939597
				],
				[
					3.3504649620520013,
					51.93220691180636
				],
				[
					2.6803719696415556,
					52.267253408011584
				],
				[
					2.010278977231337,
					52.93734640042203
				],
				[
					1.6752324810261143,
					53.272392896627196
				],
				[
					1.0051394886156686,
					53.60743939283236
				],
				[
					0.33504649620522287,
					54.27753238524281
				],
				[
					-0.33504649620522287,
					54.947625377653196
				],
				[
					-1.0051394886156686,
					55.28267187385842
				],
				[
					-1.675232481025887,
					55.28267187385842
				],
				[
					-2.01027897723111,
					55.28267187385842
				],
				[
					-2.3453254734363327,
					55.617718370063585
				],
				[
					-2.6803719696415556,
					55.617718370063585
				],
				[
					-3.0154184658467784,
					55.617718370063585
				],
				[
					-3.0154184658467784,
					55.617718370063585
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 1005536651,
			"isDeleted": false,
			"id": "axwR0u6q",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1403.8276053170107,
			"y": -348.943814241189,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 591.9993286132812,
			"height": 50,
			"seed": 2008563467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725123248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which means we can always choose a different basis vector\nand refer to our vectors using those coordinates!",
			"rawText": "Which means we can always choose a different basis vector\nand refer to our vectors using those coordinates!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which means we can always choose a different basis vector\nand refer to our vectors using those coordinates!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 1080708683,
			"isDeleted": false,
			"id": "TELacaQS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1523.9564693506763,
			"y": -669.996176525853,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 246.61981201171875,
			"height": 25,
			"seed": 1203609291,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725179527,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "LINEAR COMBINATIONS",
			"rawText": "LINEAR COMBINATIONS",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LINEAR COMBINATIONS",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 1893204491,
			"isDeleted": false,
			"id": "Ms6R9WWI",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1298.5819633760116,
			"y": -916.6324283471841,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 186.9598388671875,
			"height": 25,
			"seed": 840791947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725194287,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SCALAR PRODUCT",
			"rawText": "SCALAR PRODUCT",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SCALAR PRODUCT",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 1766393195,
			"isDeleted": false,
			"id": "MCWoOH94",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 929.6906729363482,
			"y": -1346.1196944498472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 200.579833984375,
			"height": 25,
			"seed": 1711356747,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725204874,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "vECTOR ADDITION",
			"rawText": "vECTOR ADDITION",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "vECTOR ADDITION",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 47,
			"versionNonce": 1183584613,
			"isDeleted": false,
			"id": "hJoxm820ztIMJTgpoxET0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1462.2974063953434,
			"y": -277.71696565485627,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 196.67114908166513,
			"height": 113.75034027966569,
			"seed": 1615788581,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702725244574,
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
					31.8926187699999,
					90.36241984833259
				],
				[
					196.67114908166513,
					113.75034027966569
				]
			]
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 1571643115,
			"isDeleted": false,
			"id": "33XHyN7q",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1690.8611742470082,
			"y": -187.35454580652373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 503.359375,
			"height": 50,
			"seed": 1831484939,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725274883,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The set of all possible combinations you can reach\ngiven the basis is the span of that basis",
			"rawText": "The set of all possible combinations you can reach\ngiven the basis is the span of that basis",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The set of all possible combinations you can reach\ngiven the basis is the span of that basis",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 229,
			"versionNonce": 2032610597,
			"isDeleted": false,
			"id": "zNUSTpL0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1695.1135234163414,
			"y": -126.70018118985746,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 752.1295166015625,
			"height": 60,
			"seed": 722264107,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702725481916,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The span of two vectors that have the same direction is just a line! LINEARLY DEPENDENT\n\nThe span of 2 vectors in 3d space is a plane!",
			"rawText": "The span of two vectors that have the same direction is just a line! LINEARLY DEPENDENT\n\nThe span of 2 vectors in 3d space is a plane!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The span of two vectors that have the same direction is just a line! LINEARLY DEPENDENT\n\nThe span of 2 vectors in 3d space is a plane!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 585429684,
			"isDeleted": false,
			"id": "yxKhhPp5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 746.7080769517027,
			"y": 114.50524075157603,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 561.0792846679688,
			"height": 150,
			"seed": 62398923,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702727403472,
			"link": "[[Subspaces]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The determinant of a matrix is a measure of how\nmuch did the linear transformation associated with that\nmatrix alter the area of a fixed object in that space.\n(Namely the 1x1x1 cube)\n\n",
			"rawText": "The determinant of a matrix is a measure of how\nmuch did the linear transformation associated with that\nmatrix alter the area of a fixed object in that space.\n(Namely the 1x1x1 cube)\n\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The determinant of a matrix is a measure of how\nmuch did the linear transformation associated with that\nmatrix alter the area of a fixed object in that space.\n(Namely the 1x1x1 cube)\n\n",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 189,
			"versionNonce": 77186021,
			"isDeleted": false,
			"id": "gLWIdXEn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 749.2080769517029,
			"y": 227.00524075157603,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 533.7393798828125,
			"height": 50,
			"seed": 1251526309,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702726859504,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The determinant of a matrix is zero only when that\ntransformation squishes space into a lower dimension!!",
			"rawText": "The determinant of a matrix is zero only when that\ntransformation squishes space into a lower dimension!!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The determinant of a matrix is zero only when that\ntransformation squishes space into a lower dimension!!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 71,
			"versionNonce": 1300620779,
			"isDeleted": false,
			"id": "Ju84ucPHgZDnfaeqC7-j_",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 974.2080769517028,
			"y": 300.755240751576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 397.5,
			"height": 91.25,
			"seed": 256626341,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702726922822,
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
					104.99999999999989,
					88.75
				],
				[
					397.5,
					91.25
				]
			]
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 899838181,
			"isDeleted": false,
			"id": "12DI9H0m",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1393.2526897964003,
			"y": 325.9509677806754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 476.2794189453125,
			"height": 175,
			"seed": 1706010411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702727077146,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If the determinant is negative,\nthen the orientation of space has\nbeen flipped around like a sheet\nof paper\n\nif this is in 3d space, it flips it from right hand\nto left hand rule ",
			"rawText": "If the determinant is negative,\nthen the orientation of space has\nbeen flipped around like a sheet\nof paper\n\nif this is in 3d space, it flips it from right hand\nto left hand rule ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If the determinant is negative,\nthen the orientation of space has\nbeen flipped around like a sheet\nof paper\n\nif this is in 3d space, it flips it from right hand\nto left hand rule ",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "line",
			"version": 66,
			"versionNonce": 1470407979,
			"isDeleted": false,
			"id": "7Il7pbIA8AtjLpB4euyiz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 971.4583245636583,
			"y": 303.27740247636456,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.223037643960879,
			"height": 149.2105925632202,
			"seed": 1842166693,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702727163922,
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
					1.223037643960879,
					149.2105925632202
				]
			]
		},
		{
			"type": "text",
			"version": 459,
			"versionNonce": 1200712139,
			"isDeleted": false,
			"id": "dEJdEiCD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 880.9535389105574,
			"y": 463.49533383523215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 512.9993896484375,
			"height": 225,
			"seed": 1947702891,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702727321202,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This is computed as follows:\n\n1. Take first element in first row\n2. eliminate its row and column and recursively\n   compute the lower dimension's matrix determinant\n3. multiply the result with the first element\n   times reversing the sign at each iteration \n   starting with +\n4. Iterate over 2-3 with the next element",
			"rawText": "This is computed as follows:\n\n1. Take first element in first row\n2. eliminate its row and column and recursively\n   compute the lower dimension's matrix determinant\n3. multiply the result with the first element\n   times reversing the sign at each iteration \n   starting with +\n4. Iterate over 2-3 with the next element",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is computed as follows:\n\n1. Take first element in first row\n2. eliminate its row and column and recursively\n   compute the lower dimension's matrix determinant\n3. multiply the result with the first element\n   times reversing the sign at each iteration \n   starting with +\n4. Iterate over 2-3 with the next element",
			"lineHeight": 1.25,
			"baseline": 218
		},
		{
			"type": "text",
			"version": 219,
			"versionNonce": 2098649067,
			"isDeleted": false,
			"id": "vN6ivfBi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 122.22005736645025,
			"y": 183.01048094295595,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 429.0195007324219,
			"height": 175,
			"seed": 1084914757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702727588263,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The inverse matrix is the transformation\nthat preforms the reverse action that the\nmentioned matrix preforms.\n\nThe identity matrix does not do anything!\n\n",
			"rawText": "The inverse matrix is the transformation\nthat preforms the reverse action that the\nmentioned matrix preforms.\n\nThe identity matrix does not do anything!\n\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The inverse matrix is the transformation\nthat preforms the reverse action that the\nmentioned matrix preforms.\n\nThe identity matrix does not do anything!\n\n",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 1675924651,
			"isDeleted": false,
			"id": "OOOK2B3P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -569.5137562600348,
			"y": 566.0043438547948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 526.7593994140625,
			"height": 150,
			"seed": 748920139,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702727803449,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The rank of a matrix is the amount of dimensions\nthat it squishes space onto.\nmeaning it squishes down a vector by rank dimensions.\n\nMore precisely it is the number of dimensions of \nthe span of your column basis vectors",
			"rawText": "The rank of a matrix is the amount of dimensions\nthat it squishes space onto.\nmeaning it squishes down a vector by rank dimensions.\n\nMore precisely it is the number of dimensions of \nthe span of your column basis vectors",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The rank of a matrix is the amount of dimensions\nthat it squishes space onto.\nmeaning it squishes down a vector by rank dimensions.\n\nMore precisely it is the number of dimensions of \nthe span of your column basis vectors",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 145,
			"versionNonce": 1338388517,
			"isDeleted": false,
			"id": "JVIHVdSQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1655.9421115254727,
			"y": 500.8474428932542,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 729.1666812041407,
			"height": 360.6518164402939,
			"seed": 3341,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702729288608,
			"link": "[[Dot Products]]",
			"locked": false,
			"status": "pending",
			"fileId": "4056f4253be958a1f59e01538074a1824b81903b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 76,
			"versionNonce": 332381131,
			"isDeleted": false,
			"id": "adn-VPXMtGTVDe3rAJrDS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1663.7409388700387,
			"y": 488.12194652116784,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 737.1421767692794,
			"height": 395.74362609163575,
			"seed": 448629483,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702729283101,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 103,
			"versionNonce": 34089489,
			"isDeleted": false,
			"id": "1xFvN3mZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2227.700929737425,
			"y": -531.3142175119283,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 653.6278044871792,
			"height": 346.91510286534464,
			"seed": 7681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702731057038,
			"link": "[[Cross-Product]]",
			"locked": false,
			"status": "pending",
			"fileId": "6bb0f151ba3e2bbab811c037de9e370140a35ed8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 91,
			"versionNonce": 661154123,
			"isDeleted": false,
			"id": "siGDF_wH1iiMikw05kYtl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2236.3808175579384,
			"y": -533.6219098196204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 660,
			"height": 370.7692307692306,
			"seed": 1521187083,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702731062964,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 769314267,
			"isDeleted": false,
			"id": "VFkojYFB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1440.9225351236637,
			"y": -1349.2211591241187,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 689.9999999999999,
			"height": 339.2144748455428,
			"seed": 21333,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702735692427,
			"link": "[[EigenVectors]]",
			"locked": false,
			"status": "pending",
			"fileId": "33c1a268262dc2dc81aa3ac820e00d421bcd078a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 110,
			"versionNonce": 1643658725,
			"isDeleted": false,
			"id": "iWCwkwpqHS-_1LSt9icwr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1462.3511065522353,
			"y": -1355.8142747463605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 702.8571428571428,
			"height": 365.7142857142858,
			"seed": 1368822763,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702735706093,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 86,
			"versionNonce": 1882278469,
			"isDeleted": false,
			"id": "KfOnMzi9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -708.5082827094113,
			"y": -1451.0761503092026,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 758.4471218206158,
			"height": 239.66159052453472,
			"seed": 38032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702761735410,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c75eb712d84d10656ec23fac6e290982b2c05aa3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 57,
			"versionNonce": 1675536901,
			"isDeleted": false,
			"id": "qotXMl68a3ZXPbKusJNK4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -698.5082827094112,
			"y": -1467.7428169758696,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 781.6666666666666,
			"height": 280,
			"seed": 2092776709,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702761740272,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 1942389926,
			"isDeleted": false,
			"id": "QrFSkuL9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 518.7893430360937,
			"y": -1748.6592316937224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 223.60894775390625,
			"height": 35,
			"seed": 811555123,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513848676,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Vector subspace",
			"rawText": "Vector subspace",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector subspace",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 578,
			"versionNonce": 1327169510,
			"isDeleted": false,
			"id": "B2Smn4SG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 193.7966214770803,
			"y": -1710.4933869223846,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 869.839111328125,
			"height": 275,
			"seed": 680871421,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513848676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Let F be a field, a set V together with two operations + and .\nIs called F-vector space if\n\n1) V forms a commutative group with + such that their identity element is the vector 0\n\n2) scalar and field multiplication are compatible (same operation)\n\n3) there exists a unique identity element for V in F\n\n4) scalar multiplication is distributive\na (v+w) = av + aw",
			"rawText": "Let F be a field, a set V together with two operations + and .\nIs called F-vector space if\n\n1) V forms a commutative group with + such that their identity element is the vector 0\n\n2) scalar and field multiplication are compatible (same operation)\n\n3) there exists a unique identity element for V in F\n\n4) scalar multiplication is distributive\na (v+w) = av + aw",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let F be a field, a set V together with two operations + and .\nIs called F-vector space if\n\n1) V forms a commutative group with + such that their identity element is the vector 0\n\n2) scalar and field multiplication are compatible (same operation)\n\n3) there exists a unique identity element for V in F\n\n4) scalar multiplication is distributive\na (v+w) = av + aw",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "line",
			"version": 121,
			"versionNonce": 415109926,
			"isDeleted": false,
			"id": "lO-5D8kBJi1MXrVzbMwaj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 888.8900199162509,
			"y": -1724.0612325106592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.49753431401382,
			"height": 47.48745955896106,
			"seed": 1296759773,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710513848676,
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
					40.703536764823866,
					-41.45730596417229
				],
				[
					99.49753431401382,
					-47.48745955896106
				]
			]
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 991739494,
			"isDeleted": false,
			"id": "zmygx4Ki",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1001.9553998185397,
			"y": -1780.6316144552893,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 119.10426330566406,
			"height": 20,
			"seed": 380704605,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513848676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vector addition",
			"rawText": "Vector addition",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector addition",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 132,
			"versionNonce": 1258553766,
			"isDeleted": false,
			"id": "e9P9kCjAth1uCXltzwmtS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 968.0357858478528,
			"y": -1699.1868489321557,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 110.05030310489428,
			"height": 22.613075980457552,
			"seed": 122836435,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710513848676,
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
					55.778920751795795,
					-22.613075980457552
				],
				[
					110.05030310489428,
					-16.582922385669008
				]
			]
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 1000398054,
			"isDeleted": false,
			"id": "p7l1yjhO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1091.6539345410215,
			"y": -1727.0763093080534,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.3443603515625,
			"height": 20,
			"seed": 2025798931,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513848676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Scalar multiplication",
			"rawText": "Scalar multiplication",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Scalar multiplication",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 107,
			"versionNonce": 310399014,
			"isDeleted": false,
			"id": "cqUTtoA-Umpu6EBDMsk3y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 453.2114226927664,
			"y": -1724.8150017100077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 55.02515155244703,
			"height": 73.11561233681323,
			"seed": 1807170429,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710513848676,
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
					-60.30153594788726
				],
				[
					-55.02515155244703,
					-73.11561233681323
				]
			]
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 462379878,
			"isDeleted": false,
			"id": "wjpV3PS2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 270.04550725105923,
			"y": -1809.9909212363984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115.71224975585938,
			"height": 20,
			"seed": 727090621,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513848676,
			"link": "[[Group theory]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Whats a field?",
			"rawText": "Whats a field?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Whats a field?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 141,
			"versionNonce": 488308390,
			"isDeleted": false,
			"id": "cpsfhTIE2WV6Vy9Cmzxy-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 730.9530004500489,
			"y": -1767.0376754715714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 301.9230769230769,
			"height": 248.0769230769231,
			"seed": 215629853,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710513848676,
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
					10.576923076923094,
					-162.49999999999977
				],
				[
					301.9230769230769,
					-248.0769230769231
				]
			]
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 198195686,
			"isDeleted": false,
			"id": "kqVSPa9u",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 954.5759076484412,
			"y": -2071.845367779264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 471.9849548339844,
			"height": 60,
			"seed": 188662589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513848676,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "If V is a vector subspace, and U is contained in V\nthen U is called a vector subspace with V's two operations\nand U is itself a vector space",
			"rawText": "If V is a vector subspace, and U is contained in V\nthen U is called a vector subspace with V's two operations\nand U is itself a vector space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If V is a vector subspace, and U is contained in V\nthen U is called a vector subspace with V's two operations\nand U is itself a vector space",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 1841427677,
			"isDeleted": false,
			"id": "hk6WOnyi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 98.38546857091717,
			"y": -467.0926205265154,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 496.2889099121094,
			"height": 40,
			"seed": 930264765,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710169085843,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We usually talk about column vectors when we mention vectors\nbut for the sake of simplicity we write it as a row vector",
			"rawText": "We usually talk about column vectors when we mention vectors\nbut for the sake of simplicity we write it as a row vector",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We usually talk about column vectors when we mention vectors\nbut for the sake of simplicity we write it as a row vector",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 129,
			"versionNonce": 1069826963,
			"isDeleted": false,
			"id": "6eAq3mIh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1695.4194697332125,
			"y": -52.18234342655853,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 633.28125,
			"height": 120,
			"seed": 1509301853,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "oG-g8Yy0ItF28MpGZn4Sb",
					"type": "arrow"
				}
			],
			"updated": 1710169369773,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "M is a spanning set of V if span(M) = V\n\nM is a basis of V if it is a spanning set of V and the vectors in M are linearly\nindependent\n\nV isfinitely generated if it has a finite spanning set",
			"rawText": "M is a spanning set of V if span(M) = V\n\nM is a basis of V if it is a spanning set of V and the vectors in M are linearly\nindependent\n\nV isfinitely generated if it has a finite spanning set",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "M is a spanning set of V if span(M) = V\n\nM is a basis of V if it is a spanning set of V and the vectors in M are linearly\nindependent\n\nV isfinitely generated if it has a finite spanning set",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 1351546547,
			"isDeleted": false,
			"id": "oG-g8Yy0ItF28MpGZn4Sb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2339.0385465860536,
			"y": 0.03886207224934424,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 150.50440414175955,
			"height": 1.0827654974226562,
			"seed": 1731751453,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710169436621,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6eAq3mIh",
				"focus": -0.16267637164601917,
				"gap": 10.337826852841431
			},
			"endBinding": {
				"elementId": "cEUtgb0o",
				"focus": 0.28189515443920843,
				"gap": 1.0827654974227698
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
					150.50440414175955,
					1.0827654974226562
				]
			]
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 730048595,
			"isDeleted": false,
			"id": "cEUtgb0o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2490.625716225236,
			"y": -18.368151383937175,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 443.61688232421875,
			"height": 60,
			"seed": 255281021,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "oG-g8Yy0ItF28MpGZn4Sb",
					"type": "arrow"
				}
			],
			"updated": 1710169436621,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Any two bases of a finitely generated vector space V\nhave the same size, which is called the dimension of the\nspace!",
			"rawText": "Any two bases of a finitely generated vector space V\nhave the same size, which is called the dimension of the\nspace!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Any two bases of a finitely generated vector space V\nhave the same size, which is called the dimension of the\nspace!",
			"lineHeight": 1.25,
			"baseline": 54
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
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 835.8905380756704,
		"scrollY": 1103.8280672260862,
		"zoom": {
			"value": 0.7000000000000001
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