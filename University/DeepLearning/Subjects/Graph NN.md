---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Graph Neural Networks ^aW8lf5LW

Graph neural networks are
used to represent:

Knowledge Graphs
Chemical compounds
Social network
Topology ^9rHjKFvq

Lets take a few 
1) A graph is invariant to the order of nodes and edges
{v1,v2,v3} = {v3,v2,v1}

2) Edges are symmetric in their representation
(u,v) = (v,u)

3) Input graphs may have a varying number of nodes and edges

4) Labels may be attached to nodes and edges which provide us
with extra information
 ^e3onwHrL

Graph Properties ^2L1fgXPO

Subgraphs ^A74Lulfu

Random walks ^DvaQf7hg

Represent the graph as a bunch
of sub-graphs

This number exponentially grows with
the size of the graph

This does not capture global information ^g3lnGk1E

Sample a random walk in a random direction
alongside the graph

information about (non)locality
of walks may be hard to recover

many walks are required to represent
the graph ^5jMLhFcc

Similar to RNN ^FJJgnZjV

Same as embedding into
a feature space ^xvhwdoKh


Weisfeiler-Lehman
isomorphism test ^cxKgBSbJ

Step 1:
if nodes are not labeled, assign the same label to each node. ^Lzr6egqH

Step 2:
Relabel nodes with tuple of own label and
sorted multi-set of neighbor labels. ^IEQZjcYh

Step 3:
Compress labels using hash function (here: sequential id). ^eBLV6iL7

Step 4:
If sorted labels of both graphs are not equal, the graphs are not isomorphic
 ^za4I4aPx

WIP ^HjOyGz68

# Embedded files
059468076d5f8a425d17725236e7cf7d981e4789: [[Pasted Image 20240503184422_662.png]]
c353a70af325f9ef7e8cf9c7e536647dbdf86414: [[Pasted Image 20240503184527_852.png]]
d115c8e13badfc51411be92ff2d4fb73af18fbf5: [[Pasted Image 20240503184643_860.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "line",
			"version": 50,
			"versionNonce": 1372626316,
			"isDeleted": false,
			"id": "CrCwxbtpw9GjA-lcWkr70",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -45.28623342872814,
			"y": -421.963060709748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.32945055872776,
			"height": 35.55251024213942,
			"seed": 956418228,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748473916,
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
					45.32945055872776,
					35.55251024213942
				]
			]
		},
		{
			"type": "line",
			"version": 437,
			"versionNonce": 1731907892,
			"isDeleted": false,
			"id": "HQpyN8fxzUWVn3QzUQgJj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 38.558436558984,
			"y": -332.2016355435435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.47313224719892,
			"height": 127.9890368717019,
			"seed": 1302470068,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748473916,
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
					-38.21894851029987,
					-54.513849037947125
				],
				[
					2.370167349475963,
					-57.77282914347654
				],
				[
					-54.513849037947125,
					-78.51179345139121
				],
				[
					-57.47655822479206,
					-10.962023991326305
				],
				[
					-55.40266179400061,
					-80.58568988218269
				],
				[
					-95.10296489772296,
					-127.9890368717019
				],
				[
					-54.21757811926261,
					-109.3239689945787
				]
			]
		},
		{
			"type": "line",
			"version": 751,
			"versionNonce": 1534921740,
			"isDeleted": false,
			"id": "IUVNRurJkYud56mRQ8TO4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.73303799107009,
			"y": -496.62333221824076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.47176185616166,
			"height": 161.4676506830499,
			"seed": 1078434100,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748473916,
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
					53.328765363209186
				],
				[
					-17.77625512106971,
					111.39786542537018
				],
				[
					-1.1850836747379674,
					151.39443944777702
				],
				[
					17.479984202385225,
					111.99040726273915
				],
				[
					-0.29627091868448474,
					54.513849037947125
				],
				[
					36.14505207950842,
					37.92267759161541
				],
				[
					30.219633705818524,
					74.0677296711238
				],
				[
					-27.553195437658047,
					75.54908426454631
				],
				[
					-55.99520363136958,
					103.10227970220433
				],
				[
					-0.5925418373689695,
					86.2148373371881
				],
				[
					56.88401638742309,
					106.36125980773375
				],
				[
					30.812175543187493,
					77.32670977665327
				],
				[
					-15.109816852909233,
					108.13888531984071
				],
				[
					-53.32876536320913,
					161.4676506830499
				],
				[
					-17.183713283700712,
					110.21278175063219
				],
				[
					-56.587745468738575,
					106.95380164510277
				]
			]
		},
		{
			"type": "line",
			"version": 264,
			"versionNonce": 1873971892,
			"isDeleted": false,
			"id": "gz0IlyxMeRQ6By52qh2BQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 69.96315393954046,
			"y": -438.5542321560797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 179.24390580411955,
			"height": 45.9219923960967,
			"seed": 62567604,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748473916,
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
					-58.06910006216103,
					17.479984202385253
				],
				[
					-51.25486893241765,
					-20.146422470545645
				],
				[
					-87.10365009324155,
					25.775569925551054
				],
				[
					-124.13751492880345,
					-18.665067877123192
				],
				[
					-118.80463839248253,
					15.109816852909262
				],
				[
					-179.24390580411955,
					1.4813545934224521
				]
			]
		},
		{
			"type": "line",
			"version": 239,
			"versionNonce": 43494028,
			"isDeleted": false,
			"id": "_YDPyeriv-hCuJTCv5-Ss",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -16.892431175911952,
			"y": -503.17124695551865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.11347901157683,
			"height": 172.11405148305118,
			"seed": 1559702452,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748473916,
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
					87.7444184031242,
					64.68338536127737
				],
				[
					55.121493612218956,
					172.11405148305118
				],
				[
					-58.496278935416115,
					172.11405148305118
				],
				[
					-93.36906060845263,
					64.68338536127743
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 833,
			"versionNonce": 1408701492,
			"isDeleted": false,
			"id": "jV1Qv_YgQE5cB64sSvANi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.791818344629434,
			"y": -498.8690238386681,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.54668542990925,
			"height": 168.18387194044135,
			"seed": 2043393076,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748473917,
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
					59.64458963661016,
					112.35376187361442
				],
				[
					-55.48333919684666,
					165.40970498059903
				],
				[
					-36.41094134793062,
					39.53187917775324
				],
				[
					87.38625923503346,
					60.338131376570686
				],
				[
					-1.3870834799211593,
					153.61949540126915
				],
				[
					-90.1604261948758,
					61.37844398651157
				],
				[
					36.06417047795031,
					40.57219178769412
				],
				[
					55.48333919684663,
					168.18387194044135
				],
				[
					-59.29781876662986,
					106.11188621396917
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 201,
			"versionNonce": 1507490060,
			"isDeleted": false,
			"id": "M7sM_EHh2lgPqhrQR6-Yr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.48752276662077,
			"y": -509.43099144293285,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1627220364,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 215,
			"versionNonce": 569273780,
			"isDeleted": false,
			"id": "PfgMkorYyqljdfkN_5wwa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 10.406378336176886,
			"y": -466.27020611534067,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 937265844,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 230,
			"versionNonce": 213874572,
			"isDeleted": false,
			"id": "MyzTb6lYAVbo2VJeRdzkv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 63.84047928679735,
			"y": -445.4590299556253,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 2042256692,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 239,
			"versionNonce": 985569076,
			"isDeleted": false,
			"id": "KtX8QTS_2RenMgA8mLx0h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.591331777925348,
			"y": -449.3962794993552,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1139189940,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 241,
			"versionNonce": 1199613452,
			"isDeleted": false,
			"id": "PXAZyKP4EEzowbUQvDyiz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -61.589041892027524,
			"y": -465.7077418948079,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 385602228,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 245,
			"versionNonce": 1791856820,
			"isDeleted": false,
			"id": "gjBqE9W1oSpIgrAAS1Sc_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.83546394531226,
			"y": -446.58395839669106,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 45312820,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 233,
			"versionNonce": 521667724,
			"isDeleted": false,
			"id": "y6aQWyiPuzYnqfEoSRwnu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -26.153795998458122,
			"y": -418.46074737004864,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1223554868,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 233,
			"versionNonce": 29448756,
			"isDeleted": false,
			"id": "Ms55q5pij1jTpczvu6df6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3.656807689782795,
			"y": -428.02263911910705,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1183016844,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 218,
			"versionNonce": 2034209548,
			"isDeleted": false,
			"id": "yDaBd-xe3Xz7VD9Jl3545",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -54.27700702510049,
			"y": -429.1475675601728,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 211702540,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 230,
			"versionNonce": 1786770356,
			"isDeleted": false,
			"id": "AUg3RBtYEJ6oQsZaYjVAG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -8.717405161939894,
			"y": -394.2747858871363,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 401068468,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 245,
			"versionNonce": 1953583500,
			"isDeleted": false,
			"id": "eXNwnqAY2Ay8Api5pG4A3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 30.655090275359328,
			"y": -339.1532922749172,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1055990668,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 254,
			"versionNonce": 1127177524,
			"isDeleted": false,
			"id": "teyi1giQGQaCfEhxCZM-f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -81.27528961067713,
			"y": -339.71575649545014,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1149520308,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 243,
			"versionNonce": 1340555276,
			"isDeleted": false,
			"id": "E4dj7sO5ZcOI6UYsuTTDI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 34.02987559855649,
			"y": -396.5246427692677,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1486112652,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 243,
			"versionNonce": 1966446260,
			"isDeleted": false,
			"id": "DjnZdjONVqQau6juz5tTu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -26.153795998458122,
			"y": -350.96504090610705,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 761463476,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 238,
			"versionNonce": 1402691212,
			"isDeleted": false,
			"id": "9rosZc7HW8N6XBvVeDR3U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -85.77500337494001,
			"y": -397.08710698980053,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1037934348,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 246,
			"versionNonce": 1295556660,
			"isDeleted": false,
			"id": "P3H3CDnLtR1j9bLtnvxa5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -43.59018683497641,
			"y": -394.27478588713626,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 13558708,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714748473917,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 198,
			"versionNonce": 1639150644,
			"isDeleted": false,
			"id": "aW8lf5LW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -178.6181917779269,
			"y": -324.08602748629244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 318.38934326171875,
			"height": 35,
			"seed": 173161780,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714748476635,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Graph Neural Networks",
			"rawText": "Graph Neural Networks",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph Neural Networks",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 641,
			"versionNonce": 1325333428,
			"isDeleted": false,
			"id": "jcQmvpyaPUxiYnlpB5Y2I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -508.3714377201957,
			"y": -25.33371663078981,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 49.454167879081595,
			"height": 40.75389760405794,
			"seed": 417586316,
			"groupIds": [
				"36_9Y4p4htyMV0nArt8lU",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-15.568904702673773,
					-4.808044099355162
				],
				[
					-31.137809405347614,
					-2.7474537710600906
				],
				[
					-44.41716929880468,
					14.65308677898712
				],
				[
					-46.477759627099765,
					28.84826459613089
				],
				[
					-26.32976530599245,
					35.487944542859424
				],
				[
					-13.279359893457,
					35.945853504702775
				],
				[
					2.976408251981825,
					27.24558322967917
				],
				[
					2.7474537710600737,
					10.302951641475309
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 584,
			"versionNonce": 1384998196,
			"isDeleted": false,
			"id": "WFqJYWDouk3Km_bI-TbiG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -508.3714377201957,
			"y": -25.791625592633125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 35.48794454285947,
			"height": 26.329765305992485,
			"seed": 2077256460,
			"groupIds": [
				"36_9Y4p4htyMV0nArt8lU",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-17.858449511890544,
					-3.89222617566846
				],
				[
					-30.221991481660943,
					-2.7474537710600906
				],
				[
					-32.51153629087765,
					10.76086060331866
				],
				[
					-25.413947382305782,
					20.147994321107284
				],
				[
					-10.989815084240295,
					22.437539130324023
				],
				[
					2.976408251981825,
					16.94263158820386
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 772,
			"versionNonce": 2073206452,
			"isDeleted": false,
			"id": "6VV9cmTNAmFFz9DqEEeIe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -522.5666155373394,
			"y": 5.346183812714514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 92.26865581143456,
			"height": 50.36998580276823,
			"seed": 522660236,
			"groupIds": [
				"hFgKK480UbYdIsx3VOyAs",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					14.653086778987104,
					-13.50831437437875
				],
				[
					39.609125199449586,
					-34.343172138251056
				],
				[
					54.26221197843675,
					-41.21180656590127
				],
				[
					68.68634427650211,
					-42.35657897050964
				],
				[
					89.52120204037448,
					-20.834857763872304
				],
				[
					92.26865581143456,
					-6.410725465806866
				],
				[
					71.66275252848394,
					5.265953061198497
				],
				[
					29.993037000739328,
					8.013406832258587
				],
				[
					0.9158179236867361,
					5.723862023041848
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 710,
			"versionNonce": 313829428,
			"isDeleted": false,
			"id": "XERs-mVAtGJBP1VFBOmkK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -522.3376610564178,
			"y": 7.635728621931207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 91.5817923686695,
			"height": 38.23539831391953,
			"seed": 1445074956,
			"groupIds": [
				"hFgKK480UbYdIsx3VOyAs",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					8.471315794101905,
					-1.3737268855300369
				],
				[
					20.376948802028934,
					0
				],
				[
					35.71689902378109,
					-6.181770984885199
				],
				[
					52.43057613106328,
					-16.94263158820386
				],
				[
					65.70993602452035,
					-29.764082519817592
				],
				[
					75.55497870415229,
					-31.824672848112666
				],
				[
					85.17106690286262,
					-28.84826459613089
				],
				[
					91.5817923686695,
					-14.195177817143769
				],
				[
					86.08688482654935,
					-2.9764082519817574
				],
				[
					64.565163619912,
					2.9764082519817574
				],
				[
					38.23539831391948,
					5.952816503963515
				],
				[
					11.90563300792703,
					6.410725465806866
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1389,
			"versionNonce": 1540981172,
			"isDeleted": false,
			"id": "ag2ePSNbUmzcGI-3usQjf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -504.5574306497261,
			"y": -11.462456549266221,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#7e3f09",
			"width": 62.76608777371724,
			"height": 390.1802322052721,
			"seed": 2092643980,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-7.026054601535481,
					-70.72894965545747
				],
				[
					-8.431265521842564,
					-122.72175370682025
				],
				[
					-15.223118303326865,
					-165.3464849561357
				],
				[
					-20.37555834445297,
					-205.62919800493927
				],
				[
					-32.08564934701213,
					-335.8454099533975
				],
				[
					-32.55405298711449,
					-358.3287846783111
				],
				[
					-37.47229120818935,
					-374.722912081894
				],
				[
					-33.95926390742157,
					-384.5593885240437
				],
				[
					-20.60976016450415,
					-390.1802322052721
				],
				[
					-14.988916483275684,
					-387.83821400476023
				],
				[
					-9.133870981996106,
					-356.4551701179017
				],
				[
					6.089247321330827,
					-172.13833773762
				],
				[
					16.15992558353172,
					-98.36476442149713
				],
				[
					17.799338323889984,
					-60.892473213307746
				],
				[
					25.293796565527895,
					-19.907154704350592
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1391,
			"versionNonce": 774318900,
			"isDeleted": false,
			"id": "slA09Djy8oFL5I40kMM-2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -518.6154571496877,
			"y": -173.73238788391933,
			"strokeColor": "transparent",
			"backgroundColor": "#6e3907",
			"width": 34.16254141944461,
			"height": 114.62853143454836,
			"seed": 1605141772,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-3.665972190198041,
					-25.050451064776514
				],
				[
					-3.8333780749100597,
					-28.914942047508056
				],
				[
					-2.607914297285965,
					-32.54290274121007
				],
				[
					7.718953060063368,
					-33.5731400858038
				],
				[
					17.001154986357253,
					-34.33941404654336
				],
				[
					18.185631164522302,
					-25.95543536064383
				],
				[
					23.854916223830823,
					24.4220629384446
				],
				[
					28.6808442323942,
					54.00098303415614
				],
				[
					30.32916334453455,
					80.289117388005
				],
				[
					20.427844242472787,
					36.59633823511649
				],
				[
					13.313193906247108,
					18.568516251234556
				],
				[
					7.871992925936983,
					6.215582836034514
				],
				[
					1.742587064089289,
					0.4752510174789062
				]
			]
		},
		{
			"type": "line",
			"version": 613,
			"versionNonce": 201565364,
			"isDeleted": false,
			"id": "ZqoxDFb5hYGv0RUSm9e1y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -531.0345467440447,
			"y": -366.58310397318917,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 4.392330848271322,
			"height": 24.23163736195687,
			"seed": 611320716,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					2.0619818974496806,
					-9.349024729222403
				],
				[
					-2.3303489508216413,
					-24.23163736195687
				]
			]
		},
		{
			"type": "line",
			"version": 534,
			"versionNonce": 991227444,
			"isDeleted": false,
			"id": "7oVp0HAANTqYWXKsMVsVV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -515.0854814933817,
			"y": -206.356889421947,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 6.583673741404226,
			"height": 59.95345449619171,
			"seed": 826257932,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-0.14007816471065934,
					18.630395906526864
				],
				[
					6.443595576693567,
					36.56040098950009
				],
				[
					4.6225794354540515,
					59.95345449619171
				]
			]
		},
		{
			"type": "line",
			"version": 434,
			"versionNonce": 1547765684,
			"isDeleted": false,
			"id": "HTLGpHtYc7qtVaVcnMsWN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -502.599847399474,
			"y": -160.35566059367045,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 5.1394523958532305,
			"height": 34.30285668860183,
			"seed": 353734796,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					5.1394523958532305,
					16.135490080004345
				],
				[
					0,
					34.30285668860183
				]
			]
		},
		{
			"type": "line",
			"version": 525,
			"versionNonce": 61731124,
			"isDeleted": false,
			"id": "f1Zqoh9Vqryv9I9tUb0ke",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -505.1784000589855,
			"y": -135.95831158654084,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 16.32641249812652,
			"height": 49.98704073500464,
			"seed": 1873518348,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-3.62809166625033,
					29.83097592250277
				],
				[
					6.853062036250654,
					49.98704073500464
				],
				[
					12.698320831876188,
					28.823172681877672
				],
				[
					0.6046819443750437,
					23.179474534377157
				],
				[
					5.039016203125454,
					37.691841199378494
				]
			]
		},
		{
			"type": "freedraw",
			"version": 436,
			"versionNonce": 1354869428,
			"isDeleted": false,
			"id": "G29AZE6FkGNVC2jRNB0dd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -491.2707153383592,
			"y": -77.9088449265355,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 10.88427499875099,
			"height": 36.48247731062839,
			"seed": 1501289868,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					-2.4187277775002425,
					21.566989349376993
				],
				[
					8.465547221250748,
					36.48247731062839
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
			"version": 455,
			"versionNonce": 102904884,
			"isDeleted": false,
			"id": "YSBMCE0kejz4Xk7Q6XBNe",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -504.1908011261776,
			"y": -74.28075326028517,
			"strokeColor": "#90511c",
			"backgroundColor": "#672f14",
			"width": 15.11704860937643,
			"height": 47.56831295750442,
			"seed": 1270893580,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					0.40312129625007415,
					20.55918610875191
				],
				[
					5.643698147500499,
					42.32773610625392
				],
				[
					15.11704860937643,
					47.56831295750442
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
			"version": 424,
			"versionNonce": 565546420,
			"isDeleted": false,
			"id": "tBz9QOlkCiiQqb2kCBjVs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -526.113939430923,
			"y": -396.2200236054431,
			"strokeColor": "#90511c",
			"backgroundColor": "#672f14",
			"width": 7.542820682825842,
			"height": 20.011565076885013,
			"seed": 141748876,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					7.388885566849841,
					10.62152300234666
				],
				[
					7.542820682825842,
					20.011565076885013
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
			"type": "line",
			"version": 2980,
			"versionNonce": 1956755252,
			"isDeleted": false,
			"id": "GHFEzN2bDQXRBvi4ZiBGN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -388.9563872363198,
			"y": -209.46894154888622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 268.18598082559777,
			"height": 170.32836614427762,
			"seed": 38648076,
			"groupIds": [
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-15.522548150365772,
					11.343400571421165
				],
				[
					-38.507859834561316,
					13.731484902246674
				],
				[
					-53.13487636086755,
					7.761274075182903
				],
				[
					-100.89656297737773,
					13.134463819540315
				],
				[
					-131.3446381954029,
					17.015100857131756
				],
				[
					-164.18079774425368,
					19.403185187957266
				],
				[
					-210.74844219535112,
					23.58233276690189
				],
				[
					-232.5397117141338,
					22.68680114284235
				],
				[
					-246.24270647836673,
					18.263643135772373
				],
				[
					-248.84080145497632,
					7.703242327004764
				],
				[
					-250.56408486590377,
					1.0255191096605671
				],
				[
					-244.10177207492558,
					-5.652204107683629
				],
				[
					-246.2919166747582,
					-17.068956705078563
				],
				[
					-245.39423463312124,
					-25.900784186082188
				],
				[
					-249.34370298005467,
					-34.30752034015829
				],
				[
					-255.0877038195886,
					-47.01100596994452
				],
				[
					-244.29343280740054,
					-59.76199098751274
				],
				[
					-255.7339350986864,
					-78.24551779300613
				],
				[
					-255.96736569313885,
					-94.48483949440701
				],
				[
					-265.2119938587879,
					-102.5868959723576
				],
				[
					-261.119195757835,
					-110.7724921742634
				],
				[
					-262.84247916876257,
					-127.14368457807498
				],
				[
					-250.13326401317195,
					-137.05256419090833
				],
				[
					-200.37345552263935,
					-137.48338504364023
				],
				[
					-67.68063288121894,
					-145.88439167191197
				],
				[
					-15.766720127026929,
					-146.74603337737574
				],
				[
					-5.4270196614617605,
					-133.8214077954192
				],
				[
					2.9739869668099135,
					-115.29611112794818
				],
				[
					-1.3342215605088732,
					-105.60264194148078
				],
				[
					2.7585765404440146,
					-98.0632770186728
				],
				[
					-4.349967529632131,
					-91.60096422769452
				],
				[
					-8.227355204219053,
					-78.89174907210396
				],
				[
					0.6044722767846213,
					-64.67466093195178
				],
				[
					-1.9804528396067045,
					-46.58018511721266
				],
				[
					2.1123452613461833,
					-40.548693178966275
				],
				[
					-1.7650424132408058,
					-27.408657170643814
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2817,
			"versionNonce": 994881716,
			"isDeleted": false,
			"id": "tyisHYBiBxB5RkTV15BGP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -388.66958161715945,
			"y": -213.17910463122388,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f0a548",
			"width": 268.18598082559777,
			"height": 170.32836614427762,
			"seed": 1154135948,
			"groupIds": [
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-15.522548150365772,
					11.343400571421165
				],
				[
					-38.507859834561316,
					13.731484902246674
				],
				[
					-53.13487636086755,
					7.761274075182903
				],
				[
					-100.89656297737773,
					13.134463819540315
				],
				[
					-131.3446381954029,
					17.015100857131756
				],
				[
					-164.18079774425368,
					19.403185187957266
				],
				[
					-210.74844219535112,
					23.58233276690189
				],
				[
					-232.5397117141338,
					22.68680114284235
				],
				[
					-248.3607704058529,
					17.910632481191332
				],
				[
					-248.84080145497632,
					7.703242327004764
				],
				[
					-250.56408486590377,
					1.0255191096605671
				],
				[
					-244.10177207492558,
					-5.652204107683629
				],
				[
					-248.40998060224436,
					-17.068956705078563
				],
				[
					-245.39423463312124,
					-25.900784186082188
				],
				[
					-253.57983083502702,
					-30.424403139766973
				],
				[
					-255.0877038195886,
					-47.01100596994452
				],
				[
					-247.1175180440487,
					-57.99693771460759
				],
				[
					-255.7339350986864,
					-78.24551779300613
				],
				[
					-257.02639765688207,
					-90.95473294859673
				],
				[
					-265.2119938587879,
					-102.5868959723576
				],
				[
					-261.119195757835,
					-110.7724921742634
				],
				[
					-262.84247916876257,
					-127.14368457807498
				],
				[
					-250.13326401317195,
					-137.05256419090833
				],
				[
					-200.37345552263935,
					-137.48338504364023
				],
				[
					-67.68063288121894,
					-145.88439167191197
				],
				[
					-15.766720127026929,
					-146.74603337737574
				],
				[
					-5.4270196614617605,
					-133.8214077954192
				],
				[
					2.9739869668099135,
					-115.29611112794818
				],
				[
					-1.3342215605088732,
					-105.60264194148078
				],
				[
					2.7585765404440146,
					-98.0632770186728
				],
				[
					-4.349967529632131,
					-91.60096422769452
				],
				[
					-8.227355204219053,
					-78.89174907210396
				],
				[
					0.6044722767846213,
					-64.67466093195178
				],
				[
					-1.9804528396067045,
					-46.58018511721266
				],
				[
					2.1123452613461833,
					-40.548693178966275
				],
				[
					-1.7650424132408058,
					-27.408657170643814
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1822,
			"versionNonce": 895253044,
			"isDeleted": false,
			"id": "CJiWdIRqWuQoBf1kdgbhh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -636.1622768146716,
			"y": -194.92719478955877,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bb7b1d",
			"width": 27.44861594293937,
			"height": 156.73736450651668,
			"seed": 1545856524,
			"groupIds": [
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-3.196071719383391,
					-7.896177189064788
				],
				[
					3.0080675005960456,
					-16.92037969085311
				],
				[
					-0.7520168751491125,
					-26.69659906779046
				],
				[
					1.8800421878725115,
					-36.09681000715329
				],
				[
					-6.956156095128549,
					-43.24097032106904
				],
				[
					-6.580147657553993,
					-60.16135001192215
				],
				[
					0.9400210939361883,
					-68.6215398573487
				],
				[
					-8.272185626639294,
					-88.36198283001067
				],
				[
					-8.836198283001195,
					-100.9582654887569
				],
				[
					-17.108383909640352,
					-110.35847642811972
				],
				[
					-14.332932257265957,
					-121.85196074955834
				],
				[
					-15.792354378129609,
					-137.0550754959102
				],
				[
					-9.201083240299699,
					-145.93943578488887
				],
				[
					-1.1280253127236688,
					-146.83129487284754
				],
				[
					-7.520168751490315,
					-135.1750333080376
				],
				[
					-4.888109688468692,
					-120.51070424263159
				],
				[
					-7.708172970277526,
					-111.29849752205601
				],
				[
					-2.8200632818088347,
					-103.59032455177848
				],
				[
					-1.1280253127236688,
					-89.30200392394696
				],
				[
					7.708172970277526,
					-77.26973392156255
				],
				[
					6.956156095128414,
					-64.29744282524183
				],
				[
					1.5040337502979553,
					-53.017189698006426
				],
				[
					4.888109688468692,
					-39.48088594532394
				],
				[
					8.83619828300106,
					-34.21676781928074
				],
				[
					6.392143438766647,
					-21.43248094174728
				],
				[
					10.340232033299015,
					-13.160295315107986
				],
				[
					6.353082220130187,
					-0.35244707526476476
				],
				[
					7.688788316258965,
					9.906069633669148
				],
				[
					0.24615818084262298,
					8.064796753833573
				],
				[
					-0.9400210939363232,
					2.2560506254470676
				]
			]
		},
		{
			"type": "line",
			"version": 1663,
			"versionNonce": 1035408308,
			"isDeleted": false,
			"id": "8ux1MpPYr-2WsomhNbmT4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -522.8247098559643,
			"y": -343.06052326187574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bfc2c9",
			"width": 4.7583393648275765,
			"height": 9.324144766916493,
			"seed": 1028867212,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					3.6856501438548923,
					-3.6306404402152728
				],
				[
					2.94301914471995,
					-7.233776028610724
				],
				[
					1.8153202201076262,
					-9.324144766916493
				],
				[
					1.3202328873510045,
					-7.481319694989046
				],
				[
					1.5952814055491256,
					-3.7681646993143527
				],
				[
					-1.0726892209726837,
					-1.3477377391708247
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1870,
			"versionNonce": 1652718900,
			"isDeleted": false,
			"id": "nKvIuOFfy7GEDwm62wlcl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -519.0280656793736,
			"y": -346.5445305825035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 4.361662741519731,
			"height": 5.271922791923865,
			"seed": 772985612,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					1.9343026071087412,
					-0.45513002520205686
				],
				[
					3.8306777121173115,
					1.3274625735060386
				],
				[
					4.361662741519731,
					3.7927502100171795
				],
				[
					3.034200168013712,
					4.816792766721808
				],
				[
					2.654925147011998,
					3.944460218417865
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1781,
			"versionNonce": 2099558068,
			"isDeleted": false,
			"id": "Fi5u-UzZr04Q0Ihx2pNTM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.695950991298414,
			"x": -519.3026181765978,
			"y": -344.8446627488624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d8de",
			"width": 5.8496183240156485,
			"height": 3.08529683268918,
			"seed": 752652684,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1241,
			"versionNonce": 1245954100,
			"isDeleted": false,
			"id": "MVKZ3FrurJQ7SWqIDmmVs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -518.8897522836769,
			"y": -344.10184855403503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5846447270415157,
			"height": 0.42224341397442033,
			"seed": 1491763212,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					0.5846447270415157,
					-0.42224341397442033
				]
			]
		},
		{
			"type": "line",
			"version": 1248,
			"versionNonce": 29727156,
			"isDeleted": false,
			"id": "iJJFB8Ukl2_EVWnEZin1h",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -518.4136144927826,
			"y": -344.6822873271077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5846447270415157,
			"height": 0.42224341397442033,
			"seed": 1513528972,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					0.5846447270415157,
					-0.42224341397442033
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1254,
			"versionNonce": 1859142452,
			"isDeleted": false,
			"id": "k2t17i8KNaHY60h6685Q2",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.163527388836053,
			"x": -516.1254018108868,
			"y": -344.66007735698065,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f9fb",
			"width": 1.46161181760374,
			"height": 2.0509849273307346,
			"seed": 1232792844,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2134,
			"versionNonce": 130661556,
			"isDeleted": false,
			"id": "FT2z1-G9HxuvWpl3FIjId",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -522.0837868612771,
			"y": -343.0761461665074,
			"strokeColor": "transparent",
			"backgroundColor": "#9ca2ad",
			"width": 2.804532686468228,
			"height": 8.240253842546117,
			"seed": 405891980,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					-0.6592190224049781,
					-1.2965560194709926
				],
				[
					1.5567395434369034,
					-3.3217780542430075
				],
				[
					1.3035543557284017,
					-6.760538454249467
				],
				[
					1.394200224343422,
					-8.240253842546117
				],
				[
					2.1453136640632504,
					-3.7319134961512406
				],
				[
					0.07641673116997168,
					-1.3445397008114737
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1157,
			"versionNonce": 106432052,
			"isDeleted": false,
			"id": "kSTJMcDlrtIETvdtH0-V6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -526.4302366957628,
			"y": -348.68682171607475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9ca2ad",
			"width": 2.949133760561057,
			"height": 0.4870186020583785,
			"seed": 2022971916,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					1.1588761711542,
					0.3772252964002685
				],
				[
					2.0965935904378203,
					0.0862095455882212
				],
				[
					2.949133760561057,
					0.4870186020583785
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1069,
			"versionNonce": 2137071540,
			"isDeleted": false,
			"id": "FTwYHrpisNICCUJ-JrjwV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -527.7757037884114,
			"y": -349.4383594118345,
			"strokeColor": "#f0a548",
			"backgroundColor": "#f0a548",
			"width": 2.5665145560719322,
			"height": 2.4277840395274923,
			"seed": 1167915148,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 407,
			"versionNonce": 2064320820,
			"isDeleted": false,
			"id": "sVLRwdrvMUsCdYnB6eaYf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -600.9377037801293,
			"y": -272.6088655123241,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 49.9634588412713,
			"height": 16.007710114193728,
			"seed": 1795557132,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714751148779,
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
					20.858531360919113,
					-16.007710114193728
				],
				[
					49.9634588412713,
					-10.186724618123284
				]
			]
		},
		{
			"type": "line",
			"version": 575,
			"versionNonce": 213631668,
			"isDeleted": false,
			"id": "_RfzABGexbRVcTN8Q_3XU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -501.4958682222591,
			"y": -296.3778896212784,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 98.47167130852509,
			"height": 26.67951685698959,
			"seed": 1296647564,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
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
					36.86624147511291,
					4.365739122052841
				],
				[
					77.1280578229335,
					-11.641970992140887
				],
				[
					98.47167130852509,
					4.850821246725387
				],
				[
					58.69493708537705,
					15.037545864848704
				],
				[
					74.70264719957078,
					0.48508212467254536
				]
			]
		},
		{
			"type": "line",
			"version": 516,
			"versionNonce": 1796820020,
			"isDeleted": false,
			"id": "yPSeGbBjuFRRIHKQCNX8N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -511.1975107157098,
			"y": -268.24312639027124,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 100.41199980721528,
			"height": 62.0905119580848,
			"seed": 832615436,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
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
					-31.53033810371498,
					18.91820286222893
				],
				[
					-83.919207568349,
					20.858531360919113
				],
				[
					-100.41199980721528,
					46.56788396856361
				],
				[
					-65.48608683079254,
					62.0905119580848
				],
				[
					-53.844115838651724,
					43.172309095855866
				],
				[
					-78.09822207227859,
					44.14247334520089
				]
			]
		},
		{
			"type": "freedraw",
			"version": 451,
			"versionNonce": 134849972,
			"isDeleted": false,
			"id": "Mk44r7ZLAT8OehoJDN7Z7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -537.2500701279431,
			"y": -224.5857351697428,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 134.8528306589654,
			"height": 16.492792238866272,
			"seed": 637948556,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					50.44854096594391,
					6.791149745415501
				],
				[
					75.67281144891587,
					-9.701642493450773
				],
				[
					119.3302026694442,
					1.4552463740175687
				],
				[
					134.8528306589654,
					-8.731478244105682
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 467,
			"versionNonce": 682807092,
			"isDeleted": false,
			"id": "aPvpcBwOyZ61T-b3oweNh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -412.09888196242844,
			"y": -255.63099114878526,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 87.7998645657293,
			"height": 11.641970992140887,
			"seed": 1765024012,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					-37.35132359978539,
					-11.641970992140887
				],
				[
					-58.209854960704504,
					-4.365739122052841
				],
				[
					-87.7998645657293,
					-3.880656997380296
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
			"version": 436,
			"versionNonce": 2105198772,
			"isDeleted": false,
			"id": "Wjk3sv7STeMQHClORA03F",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -506.68989627357325,
			"y": -335.66954171975397,
			"strokeColor": "#d4831a",
			"backgroundColor": "#c07912",
			"width": 94.59101431114486,
			"height": 15.522627989521183,
			"seed": 1386487692,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					30.560173854369886,
					-12.612135241485978
				],
				[
					69.36674382817291,
					-2.910492748035205
				],
				[
					94.59101431114486,
					-15.522627989521183
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
			"version": 489,
			"versionNonce": 973574708,
			"isDeleted": false,
			"id": "G57mtP3w0F3Vwbal4IXQO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -625.535016818345,
			"y": -316.751338857525,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 127.09151666420473,
			"height": 12.127053116813432,
			"seed": 982535692,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					50.933623090616386,
					-12.127053116813432
				],
				[
					87.79986456572922,
					-2.910492748035205
				],
				[
					127.09151666420473,
					-7.761313994760592
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
			"version": 422,
			"versionNonce": 759114676,
			"isDeleted": false,
			"id": "LlUFN9qtXMlFi_uwvsxdP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -623.7776640086893,
			"y": -285.150654395161,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 89.9080957268816,
			"height": 26.54429492888883,
			"seed": 1643293836,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
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
					41.10084376086011,
					-26.54429492888883
				],
				[
					89.9080957268816,
					-15.412816410322558
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
			"type": "text",
			"version": 436,
			"versionNonce": 1497863476,
			"isDeleted": false,
			"id": "9rHjKFvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.151000877772952,
			"x": -607.913215558998,
			"y": -342.13792236581924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 190.01113891601562,
			"height": 126.5222472784381,
			"seed": 1347302924,
			"groupIds": [
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714751148779,
			"link": null,
			"locked": false,
			"fontSize": 14.45968540325007,
			"fontFamily": 1,
			"text": "Graph neural networks are\nused to represent:\n\nKnowledge Graphs\nChemical compounds\nSocial network\nTopology",
			"rawText": "Graph neural networks are\nused to represent:\n\nKnowledge Graphs\nChemical compounds\nSocial network\nTopology",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph neural networks are\nused to represent:\n\nKnowledge Graphs\nChemical compounds\nSocial network\nTopology",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 292,
			"versionNonce": 366072372,
			"isDeleted": false,
			"id": "e3onwHrL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.2031832620507,
			"y": -256.35263005563814,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 639.559326171875,
			"height": 300,
			"seed": 1004891956,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714752575110,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets take a few \n1) A graph is invariant to the order of nodes and edges\n{v1,v2,v3} = {v3,v2,v1}\n\n2) Edges are symmetric in their representation\n(u,v) = (v,u)\n\n3) Input graphs may have a varying number of nodes and edges\n\n4) Labels may be attached to nodes and edges which provide us\nwith extra information\n",
			"rawText": "Lets take a few \n1) A graph is invariant to the order of nodes and edges\n{v1,v2,v3} = {v3,v2,v1}\n\n2) Edges are symmetric in their representation\n(u,v) = (v,u)\n\n3) Input graphs may have a varying number of nodes and edges\n\n4) Labels may be attached to nodes and edges which provide us\nwith extra information\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take a few \n1) A graph is invariant to the order of nodes and edges\n{v1,v2,v3} = {v3,v2,v1}\n\n2) Edges are symmetric in their representation\n(u,v) = (v,u)\n\n3) Input graphs may have a varying number of nodes and edges\n\n4) Labels may be attached to nodes and edges which provide us\nwith extra information\n",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 70,
			"versionNonce": 317415564,
			"isDeleted": false,
			"id": "sbLlxQ2ri_z1qwoPw1883",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -352.2936251184638,
			"y": 28.278458673738267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 665.7402097891381,
			"height": 1.3586534893656221,
			"seed": 437798924,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714752585003,
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
					665.7402097891381,
					1.3586534893656221
				]
			]
		},
		{
			"type": "text",
			"version": 76,
			"versionNonce": 980214068,
			"isDeleted": false,
			"id": "2L1fgXPO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -146.88898337500677,
			"y": 61.763081737910156,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 234.13699340820312,
			"height": 35,
			"seed": 1973951500,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754513818,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Graph Properties",
			"rawText": "Graph Properties",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph Properties",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 423,
			"versionNonce": 689108364,
			"isDeleted": false,
			"id": "1KzszdM2j96SfxAwztlW4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -32.92599113881943,
			"y": 113.16746975917887,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 224.5372516464995,
			"height": 186.16502272488367,
			"seed": 711744308,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714754514222,
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
					31.24903025540857,
					80.44961622004871
				],
				[
					205.7688046888652,
					85.74820177869742
				],
				[
					224.5372516464995,
					186.16502272488367
				]
			]
		},
		{
			"type": "arrow",
			"version": 376,
			"versionNonce": 2133066380,
			"isDeleted": false,
			"id": "0iOELPpawCvZNz8qYH9VM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -31.567337649453748,
			"y": 115.88477673791012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.7738012594541,
			"height": 174.01129843667593,
			"seed": 1173445772,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714754514222,
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
					-23.097109319215065,
					75.202041310955
				],
				[
					-194.99228104873956,
					93.36532614394753
				],
				[
					-212.7738012594541,
					174.01129843667593
				]
			]
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 857461004,
			"isDeleted": false,
			"id": "A74Lulfu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -312.38838456022506,
			"y": 297.1431827724796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.736572265625,
			"height": 35,
			"seed": 1556188980,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754514222,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Subgraphs",
			"rawText": "Subgraphs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Subgraphs",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1219781644,
			"isDeleted": false,
			"id": "DvaQf7hg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 99.69123787557585,
			"y": 302.25036356423306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 185.83677673339844,
			"height": 35,
			"seed": 1654285324,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754514222,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Random walks",
			"rawText": "Random walks",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Random walks",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 257,
			"versionNonce": 1034159028,
			"isDeleted": false,
			"id": "g3lnGk1E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -447.73127582402316,
			"y": 338.62128720156875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 402.9595031738281,
			"height": 175,
			"seed": 1574412340,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754513818,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Represent the graph as a bunch\nof sub-graphs\n\nThis number exponentially grows with\nthe size of the graph\n\nThis does not capture global information",
			"rawText": "Represent the graph as a bunch\nof sub-graphs\n\nThis number exponentially grows with\nthe size of the graph\n\nThis does not capture global information",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Represent the graph as a bunch\nof sub-graphs\n\nThis number exponentially grows with\nthe size of the graph\n\nThis does not capture global information",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 461,
			"versionNonce": 928083252,
			"isDeleted": false,
			"id": "5jMLhFcc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -21.057715131842208,
			"y": 340.55740914053575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 429.3794860839844,
			"height": 200,
			"seed": 1202975244,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754513818,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sample a random walk in a random direction\nalongside the graph\n\ninformation about (non)locality\nof walks may be hard to recover\n\nmany walks are required to represent\nthe graph",
			"rawText": "Sample a random walk in a random direction\nalongside the graph\n\ninformation about (non)locality\nof walks may be hard to recover\n\nmany walks are required to represent\nthe graph",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sample a random walk in a random direction\nalongside the graph\n\ninformation about (non)locality\nof walks may be hard to recover\n\nmany walks are required to represent\nthe graph",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 1129196468,
			"isDeleted": false,
			"id": "FJJgnZjV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 135.61749974336416,
			"y": 555.9820235303429,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 113.9842529296875,
			"height": 20,
			"seed": 386921356,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "B_YkoMY9eQmKMvMDrHLYt",
					"type": "arrow"
				}
			],
			"updated": 1714754611878,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Similar to RNN",
			"rawText": "Similar to RNN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Similar to RNN",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 202813492,
			"isDeleted": false,
			"id": "xvhwdoKh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -338.4917277680524,
			"y": 540.5574094626363,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 184.48040771484375,
			"height": 40,
			"seed": 299733772,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754513818,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Same as embedding into\na feature space",
			"rawText": "Same as embedding into\na feature space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Same as embedding into\na feature space",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 257318964,
			"isDeleted": false,
			"id": "cxKgBSbJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -149.67533599347868,
			"y": 616.3774797461565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 234.22097778320312,
			"height": 105,
			"seed": 117684404,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "B_YkoMY9eQmKMvMDrHLYt",
					"type": "arrow"
				},
				{
					"id": "JORTZXfAetttBm0N9jeK4",
					"type": "arrow"
				}
			],
			"updated": 1714754599491,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "\nWeisfeiler-Lehman\nisomorphism test",
			"rawText": "\nWeisfeiler-Lehman\nisomorphism test",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\nWeisfeiler-Lehman\nisomorphism test",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 174,
			"versionNonce": 703539468,
			"isDeleted": false,
			"id": "B_YkoMY9eQmKMvMDrHLYt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 200.04404161267848,
			"y": 586.3174109128806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.78360242713222,
			"height": 96.27273226501143,
			"seed": 1291521204,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714754613608,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FJJgnZjV",
				"focus": -0.14550453342736983,
				"gap": 10.33538738253776
			},
			"endBinding": {
				"elementId": "cxKgBSbJ",
				"focus": 0.3277221756688303,
				"gap": 7.714797395821819
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
					-4.185770968043926,
					92.08696129696727
				],
				[
					-107.78360242713222,
					96.27273226501143
				]
			]
		},
		{
			"type": "arrow",
			"version": 125,
			"versionNonce": 513705780,
			"isDeleted": false,
			"id": "JORTZXfAetttBm0N9jeK4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -273.99452051830013,
			"y": 596.7818383329907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115.10870162120904,
			"height": 91.04051855495618,
			"seed": 1101875084,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714754603062,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "cxKgBSbJ",
				"focus": -0.4677367358315535,
				"gap": 9.210482903612416
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
					8.371541936087908,
					82.66897661886821
				],
				[
					115.10870162120904,
					91.04051855495618
				]
			]
		},
		{
			"type": "text",
			"version": 33,
			"versionNonce": 51953676,
			"isDeleted": false,
			"id": "Lzr6egqH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.1644866844383,
			"y": 754.3302650867053,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 613.1992797851562,
			"height": 50,
			"seed": 340254900,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754641630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 1:\nif nodes are not labeled, assign the same label to each node.",
			"rawText": "Step 1:\nif nodes are not labeled, assign the same label to each node.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 1:\nif nodes are not labeled, assign the same label to each node.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 90,
			"versionNonce": 1232642228,
			"isDeleted": false,
			"id": "zkD4ftaKprHB6CzBAwnvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -166.27333620962932,
			"y": 804.3302647952949,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 267.4169790085489,
			"height": 160.62966188768542,
			"seed": 1830366476,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754655906,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "059468076d5f8a425d17725236e7cf7d981e4789",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 588563596,
			"isDeleted": false,
			"id": "IEQZjcYh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -237.86186038147122,
			"y": 978.1031205740453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 411.9395446777344,
			"height": 75,
			"seed": 1190423860,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754712497,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 2:\nRelabel nodes with tuple of own label and\nsorted multi-set of neighbor labels.",
			"rawText": "Step 2:\nRelabel nodes with tuple of own label and\nsorted multi-set of neighbor labels.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 2:\nRelabel nodes with tuple of own label and\nsorted multi-set of neighbor labels.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 231,
			"versionNonce": 928599948,
			"isDeleted": false,
			"id": "OAeOAVD1yKL3bWJ5NVLdu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -176.9586037531647,
			"y": 1066.246315104743,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 288.7875131136889,
			"height": 173.46632499110842,
			"seed": 809374092,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754731854,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c353a70af325f9ef7e8cf9c7e536647dbdf86414",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 16,
			"versionNonce": 353669516,
			"isDeleted": false,
			"id": "eBLV6iL7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -312.65456865527455,
			"y": 1252.8558337675097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 560.179443359375,
			"height": 50,
			"seed": 2064149260,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754773619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 3:\nCompress labels using hash function (here: sequential id).",
			"rawText": "Step 3:\nCompress labels using hash function (here: sequential id).",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 3:\nCompress labels using hash function (here: sequential id).",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 204,
			"versionNonce": 322843916,
			"isDeleted": false,
			"id": "hrRna-N7mLv1OrkPTEchD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -173.9323959663378,
			"y": 1302.8558336103351,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 282.73509802988673,
			"height": 169.83081391728095,
			"seed": 342793868,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754808719,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d115c8e13badfc51411be92ff2d4fb73af18fbf5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1036978828,
			"isDeleted": false,
			"id": "za4I4aPx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -431.8181900227968,
			"y": 1510.4815898580064,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 770.0390625,
			"height": 75,
			"seed": 1808089228,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714754924454,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 4:\nIf sorted labels of both graphs are not equal, the graphs are not isomorphic\n",
			"rawText": "Step 4:\nIf sorted labels of both graphs are not equal, the graphs are not isomorphic\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 4:\nIf sorted labels of both graphs are not equal, the graphs are not isomorphic\n",
			"lineHeight": 1.25
		},
		{
			"id": "HjOyGz68",
			"type": "text",
			"x": -71.51878678337062,
			"y": 1621.35863254087,
			"width": 70.27201843261719,
			"height": 45,
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
			"seed": 1143293666,
			"version": 8,
			"versionNonce": 1651689918,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1714815829924,
			"link": null,
			"locked": false,
			"text": "WIP",
			"rawText": "WIP",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "WIP",
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
		"currentItemFontSize": 36,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1783.0494442337285,
		"scrollY": -231.35863254087013,
		"zoom": {
			"value": 0.45
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
		},
		"objectsSnapModeEnabled": false
	},
	"files": {}
}
```
%%