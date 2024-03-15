---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - databases
---

Next[[Query Optimization]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Query Execution ^ChComJqg

* Query plans consist of logical operators, Physical operators are implementations of logical operators
  there is usually multiple physical operators per logical operator.



* Processing models:
    1) Inter operator execution:


    2) Intra operator execution:















    3) Executing Method:
        ^fdYRx1Nd

* Pipelining The operator can start producing output tuples by just seeing input tuples ^fQk6zg5q

* Blocking The operator can only start producing output tuples by first seeing all the input tuples ^DCfx0YEc

Pull based execution: Each operator pulls a request from the one under for tuples and pulls it ^QUMw5Hmh

Pull based execution: Bottom up execution, each operator pushes its results to the one above it ^4FOjJwWg

Iterator model: each operator processes a tuple at a time with three functions (open, close, fetch)
its quite easy to implement and doesnt need a scheduler, it also allows for processing without all data being in memory
Has large instruction footprint, all operators are interleaved thus resulting in many cache misses ^qZeTVftL

Materialization model: each operator processes all its input all at once and stores all its output at once thus fully
materializing their intermediate results. Pipelining is NOT possible. Only one operator active at a time so less function
calls, cache efficient and can be optimized with modern hardware BUT high demand on memory due to footprint ^xFHQGwdA

Vectorization Model: use the iterator model to call a batch at a time that doesnt trash the data cache and doesnt
have a lot of footprint. This enables batch processing which is the best of both worlds. but its not easy to determine
the right batch size! ^CaYY6kBO

Iterator ^tAsKHNab

Material ^uCHZ0ZhN

Vector ^HXifWmSz

Plans

Easy


Complex


easy ^6s0JGvHL

Instruction
cache Utilization

poor



Very good


good ^QTASeVUT

Function
calls

Many calls

extremely
few


very few
 ^g1MrnZL4

Attribute
access

Complex


Direct

Direct ^YoUXtgK3

Most time
spent on

Interpretation



Processing



Processing
 ^TJkniMLZ

CPU Util

poor


good


very good ^cMok0JII

optimization


limited


applicable


applicable ^6ntQ2pIL

Material-
ization

very cheap


expensive


cheap ^KRCgVZU2

Scalability

good


limited


good ^Ku9oOsRS

So far we have only discussed interpretation based models, next we are gonna talk about compilation based models
that aim to spend the CPU cycles on useful work not overhead. The drawbacks of this approach is compilation time
needed to compile the generated code may be too expensive for real time analytics and is also really complex to develop
and debug ^LBVmPWkz

Compilation model: this model is split into two phases, the produce phase divides the query into pipelines such that
intersections create new pipelines and the current operator is asked to produce results recursively, and the consume
phase fills the current pipeline with operators and bubbles up the results from the produce phase. its a push based 
model that is data centric ^KUpDLOA2

data centric: Pick one tuple, apply all operations ^jbJ0EbCX

Operator-centric: Pick one operator, apply it for all tuples ^r0EaaTq7

Compilation ^C19uGiSj

Comput-
ation

Efficient



less
Efficient ^P3PyORyt

parallel
data access

bad at hiding
memory 
latencies


can generate
more parallel
requests ^j8TIDuBO

SIMD
vectorization

good but
complex




very good ^6QxcyzJe

Parallel-
ization

good




good ^JUTiSBtT

OLTP



fast





slower ^QgfbfRBG

Lang
support

easily
portable



complex ^NW4LK9yv

Compilation
time

has
overhead




precompiled ^9mSGVpLo

profiling


complex
to
debug

attributes
profiling
to primitives ^QZUdIOkY

Adaptivity

possible to
switch from 
inter to comp

possible to
swap exec
primitives ^9dcXDSJk

Vectorized ^vytda8Tt

selection, Projection, difference, Union, Cartesian product ^50zQtSkk

* With high disk-access latencies gone, the function-call overhead for tuple-at-a-time processing becomes a more severe
performance issue in a main-memory-resident database than in a disk-resident database TRUE
* Query compilation both requires fewer CPU instructions and can hide cache misses better than vectorized query processing.
FALSE ^BkskB0lt

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.20",
	"elements": [
		{
			"type": "text",
			"version": 712,
			"versionNonce": 285153408,
			"isDeleted": false,
			"id": "ChComJqg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -322.0338737534362,
			"y": -933.8331682537163,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 220.55694580078125,
			"height": 35,
			"seed": 1596536960,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Query Execution",
			"rawText": "Query Execution",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Query Execution",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 563,
			"versionNonce": 1417457536,
			"isDeleted": false,
			"id": "fdYRx1Nd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -705.1639418644289,
			"y": -868.7843269007413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1020.578857421875,
			"height": 675,
			"seed": 854481024,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Query plans consist of logical operators, Physical operators are implementations of logical operators\n  there is usually multiple physical operators per logical operator.\n\n\n\n* Processing models:\n    1) Inter operator execution:\n\n\n    2) Intra operator execution:\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n    3) Executing Method:\n       ",
			"rawText": "* Query plans consist of logical operators, Physical operators are implementations of logical operators\n  there is usually multiple physical operators per logical operator.\n\n\n\n* Processing models:\n    1) Inter operator execution:\n\n\n    2) Intra operator execution:\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n    3) Executing Method:\n       ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Query plans consist of logical operators, Physical operators are implementations of logical operators\n  there is usually multiple physical operators per logical operator.\n\n\n\n* Processing models:\n    1) Inter operator execution:\n\n\n    2) Intra operator execution:\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n    3) Executing Method:\n       ",
			"lineHeight": 1.25,
			"baseline": 668
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 1116211328,
			"isDeleted": false,
			"id": "fQk6zg5q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -705.0116918194709,
			"y": -814.2309954867355,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 865.0789794921875,
			"height": 25,
			"seed": 1559003008,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Pipelining The operator can start producing output tuples by just seeing input tuples",
			"rawText": "* Pipelining The operator can start producing output tuples by just seeing input tuples",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Pipelining The operator can start producing output tuples by just seeing input tuples",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 297,
			"versionNonce": 272285568,
			"isDeleted": false,
			"id": "QUMw5Hmh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -642.7445455168098,
			"y": -696.4903068071832,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 758.4974365234375,
			"height": 20,
			"seed": 1651289984,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Pull based execution: Each operator pulls a request from the one under for tuples and pulls it",
			"rawText": "Pull based execution: Each operator pulls a request from the one under for tuples and pulls it",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Pull based execution: Each operator pulls a request from the one under for tuples and pulls it",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 896727168,
			"isDeleted": false,
			"id": "4FOjJwWg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -642.7445460871179,
			"y": -671.4903063853345,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 777.7454833984375,
			"height": 20,
			"seed": 680949888,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Pull based execution: Bottom up execution, each operator pushes its results to the one above it",
			"rawText": "Pull based execution: Bottom up execution, each operator pushes its results to the one above it",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Pull based execution: Bottom up execution, each operator pushes its results to the one above it",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 538,
			"versionNonce": 1236717440,
			"isDeleted": false,
			"id": "qZeTVftL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -635.3096623761934,
			"y": -617.4946734381356,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 949.7138671875,
			"height": 60,
			"seed": 1640900736,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Iterator model: each operator processes a tuple at a time with three functions (open, close, fetch)\nits quite easy to implement and doesnt need a scheduler, it also allows for processing without all data being in memory\nHas large instruction footprint, all operators are interleaved thus resulting in many cache misses",
			"rawText": "Iterator model: each operator processes a tuple at a time with three functions (open, close, fetch)\nits quite easy to implement and doesnt need a scheduler, it also allows for processing without all data being in memory\nHas large instruction footprint, all operators are interleaved thus resulting in many cache misses",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Iterator model: each operator processes a tuple at a time with three functions (open, close, fetch)\nits quite easy to implement and doesnt need a scheduler, it also allows for processing without all data being in memory\nHas large instruction footprint, all operators are interleaved thus resulting in many cache misses",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 466,
			"versionNonce": 1837099136,
			"isDeleted": false,
			"id": "xFHQGwdA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -636.0382626816128,
			"y": -556.1567338681375,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 940.9297485351562,
			"height": 60,
			"seed": 701439872,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Materialization model: each operator processes all its input all at once and stores all its output at once thus fully\nmaterializing their intermediate results. Pipelining is NOT possible. Only one operator active at a time so less function\ncalls, cache efficient and can be optimized with modern hardware BUT high demand on memory due to footprint",
			"rawText": "Materialization model: each operator processes all its input all at once and stores all its output at once thus fully\nmaterializing their intermediate results. Pipelining is NOT possible. Only one operator active at a time so less function\ncalls, cache efficient and can be optimized with modern hardware BUT high demand on memory due to footprint",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Materialization model: each operator processes all its input all at once and stores all its output at once thus fully\nmaterializing their intermediate results. Pipelining is NOT possible. Only one operator active at a time so less function\ncalls, cache efficient and can be optimized with modern hardware BUT high demand on memory due to footprint",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 406,
			"versionNonce": 422633344,
			"isDeleted": false,
			"id": "CaYY6kBO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -635.3096616063912,
			"y": -498.49904081898137,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 947.8258056640625,
			"height": 60,
			"seed": 2134382720,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vectorization Model: use the iterator model to call a batch at a time that doesnt trash the data cache and doesnt\nhave a lot of footprint. This enables batch processing which is the best of both worlds. but its not easy to determine\nthe right batch size!",
			"rawText": "Vectorization Model: use the iterator model to call a batch at a time that doesnt trash the data cache and doesnt\nhave a lot of footprint. This enables batch processing which is the best of both worlds. but its not easy to determine\nthe right batch size!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vectorization Model: use the iterator model to call a batch at a time that doesnt trash the data cache and doesnt\nhave a lot of footprint. This enables batch processing which is the best of both worlds. but its not easy to determine\nthe right batch size!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "rectangle",
			"version": 304,
			"versionNonce": 1986975872,
			"isDeleted": false,
			"id": "PsbE3SPqTE_malswuzrI0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -632.5227981178209,
			"y": -437.6363243247627,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 888.8264287150682,
			"height": 191.7075570200803,
			"seed": 2131824512,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 137,
			"versionNonce": 250146688,
			"isDeleted": false,
			"id": "etDO2-MjJWb0kJMiHVp8k",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -551.0156817517775,
			"y": -437.19947330787335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1007929472,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 176,
			"versionNonce": 1677707392,
			"isDeleted": false,
			"id": "PEG-Ib4BLFuFyRZnqGSBB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -633.385486328606,
			"y": -403.6908493910623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 892.3975762864105,
			"height": 5.652314585341173,
			"seed": 265484416,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					892.3975762864105,
					-5.652314585341173
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 857669504,
			"isDeleted": false,
			"id": "tAsKHNab",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -625.3867473588507,
			"y": -388.43543765509264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 68.84815979003906,
			"height": 20,
			"seed": 1619836800,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Iterator",
			"rawText": "Iterator",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Iterator",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 1374861440,
			"isDeleted": false,
			"id": "uCHZ0ZhN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -624.4477260358814,
			"y": -335.22422935349135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 65.98416137695312,
			"height": 20,
			"seed": 936734592,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Material",
			"rawText": "Material",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Material",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 114,
			"versionNonce": 101912448,
			"isDeleted": false,
			"id": "HCduN5l1zNCmZBBYXVjc_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -632.5124094235848,
			"y": -437.7880420634268,
			"strokeColor": "transparent",
			"backgroundColor": "#1e1e1e",
			"width": 81.87766396029429,
			"height": 33.57225749404398,
			"seed": 1274542208,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 134,
			"versionNonce": 1678223488,
			"isDeleted": false,
			"id": "6s0JGvHL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -538.1655417229053,
			"y": -431.4611338579809,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 59.1361083984375,
			"height": 180,
			"seed": 1593479040,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Plans\n\nEasy\n\n\nComplex\n\n\neasy",
			"rawText": "Plans\n\nEasy\n\n\nComplex\n\n\neasy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Plans\n\nEasy\n\n\nComplex\n\n\neasy",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 275,
			"versionNonce": 335744,
			"isDeleted": false,
			"id": "QTASeVUT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -443.7500392659451,
			"y": -441.7109805022121,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 105.13783264160156,
			"height": 175.68087845496063,
			"seed": 328345728,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 12.776791160360775,
			"fontFamily": 1,
			"text": "Instruction\ncache Utilization\n\npoor\n\n\n\nVery good\n\n\ngood",
			"rawText": "Instruction\ncache Utilization\n\npoor\n\n\n\nVery good\n\n\ngood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Instruction\ncache Utilization\n\npoor\n\n\n\nVery good\n\n\ngood",
			"lineHeight": 1.25,
			"baseline": 170
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 1174313088,
			"isDeleted": false,
			"id": "g1MrnZL4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -310.6043082397826,
			"y": -438.44060855561156,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 75.24790954589844,
			"height": 202.79463692171586,
			"seed": 886431616,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 14.748700867033882,
			"fontFamily": 1,
			"text": "Function\ncalls\n\nMany calls\n\nextremely\nfew\n\n\nvery few\n",
			"rawText": "Function\ncalls\n\nMany calls\n\nextremely\nfew\n\n\nvery few\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Function\ncalls\n\nMany calls\n\nextremely\nfew\n\n\nvery few\n",
			"lineHeight": 1.25,
			"baseline": 196
		},
		{
			"type": "text",
			"version": 195,
			"versionNonce": 288698240,
			"isDeleted": false,
			"id": "YoUXtgK3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -231.85241468808084,
			"y": -442.4268860522175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 73.96817016601562,
			"height": 180,
			"seed": 1989912704,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Attribute\naccess\n\nComplex\n\n\nDirect\n\nDirect",
			"rawText": "Attribute\naccess\n\nComplex\n\n\nDirect\n\nDirect",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Attribute\naccess\n\nComplex\n\n\nDirect\n\nDirect",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 731351168,
			"isDeleted": false,
			"id": "TJkniMLZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -156.14282683124333,
			"y": -438.67530503268915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 84.40098571777344,
			"height": 194.50381384551716,
			"seed": 1055983744,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 11.96946546741644,
			"fontFamily": 1,
			"text": "Most time\nspent on\n\nInterpretation\n\n\n\nProcessing\n\n\n\nProcessing\n",
			"rawText": "Most time\nspent on\n\nInterpretation\n\n\n\nProcessing\n\n\n\nProcessing\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Most time\nspent on\n\nInterpretation\n\n\n\nProcessing\n\n\n\nProcessing\n",
			"lineHeight": 1.25,
			"baseline": 189
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 568541056,
			"isDeleted": false,
			"id": "cMok0JII",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -71.28513827454395,
			"y": -433.6371368669597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 74.35214233398438,
			"height": 180,
			"seed": 44887936,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "CPU Util\n\npoor\n\n\ngood\n\n\nvery good",
			"rawText": "CPU Util\n\npoor\n\n\ngood\n\n\nvery good",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CPU Util\n\npoor\n\n\ngood\n\n\nvery good",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 241,
			"versionNonce": 1351776384,
			"isDeleted": false,
			"id": "6ntQ2pIL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4.802263714927506,
			"y": -433.77559591652783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 79.37208557128906,
			"height": 173.4924247673302,
			"seed": 1214459776,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 13.879393981386414,
			"fontFamily": 1,
			"text": "optimization\n\n\nlimited\n\n\napplicable\n\n\napplicable",
			"rawText": "optimization\n\n\nlimited\n\n\napplicable\n\n\napplicable",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "optimization\n\n\nlimited\n\n\napplicable\n\n\napplicable",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 202,
			"versionNonce": 307187584,
			"isDeleted": false,
			"id": "KRCgVZU2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 89.23254254916185,
			"y": -441.98032158378265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 78.9542236328125,
			"height": 190.88363814749454,
			"seed": 1968998528,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 15.270691051799561,
			"fontFamily": 1,
			"text": "Material-\nization\n\nvery cheap\n\n\nexpensive\n\n\ncheap",
			"rawText": "Material-\nization\n\nvery cheap\n\n\nexpensive\n\n\ncheap",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Material-\nization\n\nvery cheap\n\n\nexpensive\n\n\ncheap",
			"lineHeight": 1.25,
			"baseline": 185
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 2024761472,
			"isDeleted": false,
			"id": "Ku9oOsRS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 169.92398221771862,
			"y": -434.31445200412753,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 79.2001953125,
			"height": 180,
			"seed": 1677512576,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Scalability\n\ngood\n\n\nlimited\n\n\ngood",
			"rawText": "Scalability\n\ngood\n\n\nlimited\n\n\ngood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Scalability\n\ngood\n\n\nlimited\n\n\ngood",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 452,
			"versionNonce": 985227136,
			"isDeleted": false,
			"id": "KUpDLOA2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -632.037578875061,
			"y": -129.52452043883738,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1e1e1e",
			"width": 930.2577514648438,
			"height": 80,
			"seed": 1301340032,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Compilation model: this model is split into two phases, the produce phase divides the query into pipelines such that\nintersections create new pipelines and the current operator is asked to produce results recursively, and the consume\nphase fills the current pipeline with operators and bubbles up the results from the produce phase. its a push based \nmodel that is data centric",
			"rawText": "Compilation model: this model is split into two phases, the produce phase divides the query into pipelines such that\nintersections create new pipelines and the current operator is asked to produce results recursively, and the consume\nphase fills the current pipeline with operators and bubbles up the results from the produce phase. its a push based \nmodel that is data centric",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Compilation model: this model is split into two phases, the produce phase divides the query into pipelines such that\nintersections create new pipelines and the current operator is asked to produce results recursively, and the consume\nphase fills the current pipeline with operators and bubbles up the results from the produce phase. its a push based \nmodel that is data centric",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 1873696896,
			"isDeleted": false,
			"id": "jbJ0EbCX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -633.1751062509594,
			"y": -49.89175993628561,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#1e1e1e",
			"width": 387.0248107910156,
			"height": 20,
			"seed": 1409812608,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "data centric: Pick one tuple, apply all operations",
			"rawText": "data centric: Pick one tuple, apply all operations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "data centric: Pick one tuple, apply all operations",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 1801547648,
			"isDeleted": false,
			"id": "r0EaaTq7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -637.342542692156,
			"y": -30.443723210700853,
			"strokeColor": "#f08c00",
			"backgroundColor": "#1e1e1e",
			"width": 464.6730651855469,
			"height": 20,
			"seed": 1328527488,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Operator-centric: Pick one operator, apply it for all tuples",
			"rawText": "Operator-centric: Pick one operator, apply it for all tuples",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Operator-centric: Pick one operator, apply it for all tuples",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "frame",
			"version": 1182,
			"versionNonce": 247662865,
			"isDeleted": false,
			"id": "5WEZ7PuZMlbxgTCfCutHM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -712.5988249471662,
			"y": -933.833168341694,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 1238.8821166634057,
			"seed": 2037221504,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708099388220,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "QueryExecution"
		},
		{
			"type": "text",
			"version": 255,
			"versionNonce": 1820819328,
			"isDeleted": false,
			"id": "DCfx0YEc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -703.84481752505,
			"y": -785.839138213346,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 984.1788330078125,
			"height": 25,
			"seed": 1628000128,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Blocking The operator can only start producing output tuples by first seeing all the input tuples",
			"rawText": "* Blocking The operator can only start producing output tuples by first seeing all the input tuples",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Blocking The operator can only start producing output tuples by first seeing all the input tuples",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 208,
			"versionNonce": 559036544,
			"isDeleted": false,
			"id": "L81zG0pLOnvPkqq1eEQ3G",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -472.0364843914853,
			"y": -437.63632441305697,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1885743232,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 259,
			"versionNonce": 2120978304,
			"isDeleted": false,
			"id": "AzeZaoncJKQsxb6i9xBxh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -313.69563897008345,
			"y": -436.912283728274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1692715136,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 191,
			"versionNonce": 460793984,
			"isDeleted": false,
			"id": "o2jK8Inus7IMuL7Bn_YAD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -234.20911591628413,
			"y": -436.9122834125072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 2127540096,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 236,
			"versionNonce": 1498259328,
			"isDeleted": false,
			"id": "oZyQ6noNrgFz27TF_UEPQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -152.870401390425,
			"y": -436.9122837282348,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1534630016,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 195,
			"versionNonce": 1669208192,
			"isDeleted": false,
			"id": "S5XDqBTWS7AUcC2r2iGUJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -74.00601107422638,
			"y": -436.91228304388375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1791375488,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 184,
			"versionNonce": 762163072,
			"isDeleted": false,
			"id": "nI5GCuNu1jJ54kr2a59sp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4.758006925969967,
			"y": -436.91228272815624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 958359680,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 201,
			"versionNonce": 1831274624,
			"isDeleted": false,
			"id": "i5WscpF7wOTAJr8SkjfLe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 86.81729366282448,
			"y": -436.91228325436873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 670850944,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 193,
			"versionNonce": 587972480,
			"isDeleted": false,
			"id": "h8gY6P-WB0TCgXXVlW060",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 167.90147008395147,
			"y": -436.91228193864123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1687701632,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 286,
			"versionNonce": 875690112,
			"isDeleted": false,
			"id": "uKnE3wvxeek-xJpPOHPxT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -635.3096621505318,
			"y": -354.61954966104446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 894.4608618215274,
			"height": 3.073207666445171,
			"seed": 886640512,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					894.4608618215274,
					-3.073207666445171
				]
			]
		},
		{
			"type": "line",
			"version": 272,
			"versionNonce": 1516752768,
			"isDeleted": false,
			"id": "ms4xZ8XWSaf_WaUC0xgLZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -634.1537882452169,
			"y": -291.6187924122074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 888.271005216177,
			"height": 4.62067181778275,
			"seed": 1282482048,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					888.271005216177,
					-4.62067181778275
				]
			]
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 1012852864,
			"isDeleted": false,
			"id": "HXifWmSz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -614.4314985908741,
			"y": -275.75287889876034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 49.84010314941406,
			"height": 20,
			"seed": 1398569088,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vector",
			"rawText": "Vector",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 517,
			"versionNonce": 1807867776,
			"isDeleted": false,
			"id": "LBVmPWkz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -635.7367495843732,
			"y": -217.04882553238508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 962.2738647460938,
			"height": 80,
			"seed": 358058112,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "So far we have only discussed interpretation based models, next we are gonna talk about compilation based models\nthat aim to spend the CPU cycles on useful work not overhead. The drawbacks of this approach is compilation time\nneeded to compile the generated code may be too expensive for real time analytics and is also really complex to develop\nand debug",
			"rawText": "So far we have only discussed interpretation based models, next we are gonna talk about compilation based models\nthat aim to spend the CPU cycles on useful work not overhead. The drawbacks of this approach is compilation time\nneeded to compile the generated code may be too expensive for real time analytics and is also really complex to develop\nand debug",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So far we have only discussed interpretation based models, next we are gonna talk about compilation based models\nthat aim to spend the CPU cycles on useful work not overhead. The drawbacks of this approach is compilation time\nneeded to compile the generated code may be too expensive for real time analytics and is also really complex to develop\nand debug",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "rectangle",
			"version": 386,
			"versionNonce": 292411520,
			"isDeleted": false,
			"id": "Vv7ZcmopVj17Yn8pdwM6o",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -632.3631720133221,
			"y": 4.547357061538577,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 888.8264287150682,
			"height": 191.7075570200803,
			"seed": 60311680,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 233,
			"versionNonce": 1733947264,
			"isDeleted": false,
			"id": "BXw7jAOpxaXngTmBlOc5U",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -536.9308154189778,
			"y": 6.450022839301681,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1786460288,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 253,
			"versionNonce": 1193199744,
			"isDeleted": false,
			"id": "VT1tPiOJRnHM97vP6u53W",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -632.4929528436703,
			"y": 39.225739375675886,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 892.3975762864105,
			"height": 5.652314585341173,
			"seed": 1468016768,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					892.3975762864105,
					-5.652314585341173
				]
			]
		},
		{
			"type": "text",
			"version": 206,
			"versionNonce": 1433403264,
			"isDeleted": false,
			"id": "C19uGiSj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -629.6245655369731,
			"y": 64.00894705732506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 84.44818115234375,
			"height": 20,
			"seed": 912726144,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Compilation",
			"rawText": "Compilation",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Compilation",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 197,
			"versionNonce": 910430080,
			"isDeleted": false,
			"id": "ApGfNQyjCq_BRp-KvALwo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -630.8869685582122,
			"y": 5.128546703311343,
			"strokeColor": "transparent",
			"backgroundColor": "#1e1e1e",
			"width": 89.2067377646632,
			"height": 33.57225749404398,
			"seed": 551221376,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 322,
			"versionNonce": 1265019008,
			"isDeleted": false,
			"id": "P3PyORyt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.5656045600933,
			"y": -0.2710631782329358,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 66.64015197753906,
			"height": 180,
			"seed": 736618624,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Comput-\nation\n\nEfficient\n\n\n\nless\nEfficient",
			"rawText": "Comput-\nation\n\nEfficient\n\n\n\nless\nEfficient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Comput-\nation\n\nEfficient\n\n\n\nless\nEfficient",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 443,
			"versionNonce": 35004288,
			"isDeleted": false,
			"id": "j8TIDuBO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -431.4258804147985,
			"y": 1.2056082645260346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 82.27458190917969,
			"height": 175.68087845496063,
			"seed": 668391552,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 12.776791160360775,
			"fontFamily": 1,
			"text": "parallel\ndata access\n\nbad at hiding\nmemory \nlatencies\n\n\ncan generate\nmore parallel\nrequests",
			"rawText": "parallel\ndata access\n\nbad at hiding\nmemory \nlatencies\n\n\ncan generate\nmore parallel\nrequests",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "parallel\ndata access\n\nbad at hiding\nmemory \nlatencies\n\n\ncan generate\nmore parallel\nrequests",
			"lineHeight": 1.25,
			"baseline": 170
		},
		{
			"type": "text",
			"version": 532,
			"versionNonce": 1769838720,
			"isDeleted": false,
			"id": "6QxcyzJe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -314.2358472785771,
			"y": 6.506108928839637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 78.50347900390625,
			"height": 153.90683007222796,
			"seed": 677890176,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 12.312546405778237,
			"fontFamily": 1,
			"text": "SIMD\nvectorization\n\ngood but\ncomplex\n\n\n\n\nvery good",
			"rawText": "SIMD\nvectorization\n\ngood but\ncomplex\n\n\n\n\nvery good",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SIMD\nvectorization\n\ngood but\ncomplex\n\n\n\n\nvery good",
			"lineHeight": 1.25,
			"baseline": 149
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 690368384,
			"isDeleted": false,
			"id": "JUTiSBtT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -223.7947699986365,
			"y": -2.3559787783831894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 66.75215148925781,
			"height": 180,
			"seed": 1230682240,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Parallel-\nization\n\ngood\n\n\n\n\ngood",
			"rawText": "Parallel-\nization\n\ngood\n\n\n\n\ngood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parallel-\nization\n\ngood\n\n\n\n\ngood",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 121014400,
			"isDeleted": false,
			"id": "QgfbfRBG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -127.95349681422422,
			"y": 5.01364159854495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 35.213897705078125,
			"height": 164.58015017697605,
			"seed": 779069568,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 11.96946546741644,
			"fontFamily": 1,
			"text": "OLTP\n\n\n\nfast\n\n\n\n\n\nslower",
			"rawText": "OLTP\n\n\n\nfast\n\n\n\n\n\nslower",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "OLTP\n\n\n\nfast\n\n\n\n\n\nslower",
			"lineHeight": 1.25,
			"baseline": 160
		},
		{
			"type": "text",
			"version": 324,
			"versionNonce": 330579840,
			"isDeleted": false,
			"id": "NW4LK9yv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -66.20496356963145,
			"y": -5.009168593396453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 64.43214416503906,
			"height": 180,
			"seed": 57055360,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lang\nsupport\n\neasily\nportable\n\n\n\ncomplex",
			"rawText": "Lang\nsupport\n\neasily\nportable\n\n\n\ncomplex",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lang\nsupport\n\neasily\nportable\n\n\n\ncomplex",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "text",
			"version": 394,
			"versionNonce": 1615952000,
			"isDeleted": false,
			"id": "9mSGVpLo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.578567112698977,
			"y": -2.0581961849808437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 73.14926147460938,
			"height": 173.4924247673302,
			"seed": 2080344192,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 13.879393981386414,
			"fontFamily": 1,
			"text": "Compilation\ntime\n\nhas\noverhead\n\n\n\n\nprecompiled",
			"rawText": "Compilation\ntime\n\nhas\noverhead\n\n\n\n\nprecompiled",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Compilation\ntime\n\nhas\noverhead\n\n\n\n\nprecompiled",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 353,
			"versionNonce": 570445696,
			"isDeleted": false,
			"id": "QZUdIOkY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 83.72875187638272,
			"y": 0.936267182955504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 91.74687194824219,
			"height": 190.88363814749454,
			"seed": 1408923776,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 15.270691051799561,
			"fontFamily": 1,
			"text": "profiling\n\n\ncomplex\nto\ndebug\n\nattributes\nprofiling\nto primitives",
			"rawText": "profiling\n\n\ncomplex\nto\ndebug\n\nattributes\nprofiling\nto primitives",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "profiling\n\n\ncomplex\nto\ndebug\n\nattributes\nprofiling\nto primitives",
			"lineHeight": 1.25,
			"baseline": 185
		},
		{
			"type": "text",
			"version": 390,
			"versionNonce": 948856960,
			"isDeleted": false,
			"id": "9dcXDSJk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 170.4056639951026,
			"y": 7.438216790608493,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 104.46421813964844,
			"height": 180,
			"seed": 1326934144,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Adaptivity\n\npossible to\nswitch from \ninter to comp\n\npossible to\nswap exec\nprimitives",
			"rawText": "Adaptivity\n\npossible to\nswitch from \ninter to comp\n\npossible to\nswap exec\nprimitives",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Adaptivity\n\npossible to\nswitch from \ninter to comp\n\npossible to\nswap exec\nprimitives",
			"lineHeight": 1.25,
			"baseline": 174
		},
		{
			"type": "line",
			"version": 308,
			"versionNonce": 743071616,
			"isDeleted": false,
			"id": "_hJVJEhOUWJtrbXewL2_9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -451.3554516347537,
			"y": 4.547356973244291,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 957765760,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 336,
			"versionNonce": 1538087040,
			"isDeleted": false,
			"id": "O0b4CRpfVOOmMYdRWHnCc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -312.8031054851476,
			"y": 6.004305038464139,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1706510464,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 268,
			"versionNonce": 47345536,
			"isDeleted": false,
			"id": "KCTDqaqjzET8kHI-6LxVX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -233.31658243134848,
			"y": 6.004305354230979,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 817510528,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 313,
			"versionNonce": 493766784,
			"isDeleted": false,
			"id": "B3Jx3IkqQBxZYYiWCnZmj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.97786790548935,
			"y": 6.004305038503361,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 2111776896,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 272,
			"versionNonce": 1842904960,
			"isDeleted": false,
			"id": "Gg_0EpK2fCx-D_PNLf9ZB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -73.11347758929071,
			"y": 6.004305722854411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 954603648,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 261,
			"versionNonce": 1502689408,
			"isDeleted": false,
			"id": "Qy2_BdA8cVIk2sOvnBxAH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5.650540410905705,
			"y": 6.004306038581916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1435437184,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 278,
			"versionNonce": 765235072,
			"isDeleted": false,
			"id": "-z9lwkNu5IF6iBnQREHB2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 87.70982714776017,
			"y": 6.004305512369427,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 1335490688,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 270,
			"versionNonce": 1943414912,
			"isDeleted": false,
			"id": "Ssb0N2y1AesckaF8CWteV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 168.7940035688872,
			"y": 6.004306828096929,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1.08205957895143,
			"height": 190.98351568494002,
			"seed": 717678720,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					1.08205957895143,
					190.98351568494002
				]
			]
		},
		{
			"type": "line",
			"version": 388,
			"versionNonce": 2053021568,
			"isDeleted": false,
			"id": "IC2CnMUWPfcFEOGsyNNAV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -633.6842212851592,
			"y": 120.5449638449168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 894.4608618215274,
			"height": 3.073207666445171,
			"seed": 1926617216,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
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
					894.4608618215274,
					-3.073207666445171
				]
			]
		},
		{
			"type": "text",
			"version": 235,
			"versionNonce": 73314176,
			"isDeleted": false,
			"id": "vytda8Tt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -626.7312979538024,
			"y": 151.7726548788032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 80.3521728515625,
			"height": 20,
			"seed": 546945152,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vectorized",
			"rawText": "Vectorized",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vectorized",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 96,
			"versionNonce": 2043021440,
			"isDeleted": false,
			"id": "50zQtSkk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -437.4598687209336,
			"y": -888.7843273817685,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 451.408935546875,
			"height": 20,
			"seed": 796706944,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240657508,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "selection, Projection, difference, Union, Cartesian product",
			"rawText": "selection, Projection, difference, Union, Cartesian product",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "selection, Projection, difference, Union, Cartesian product",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 176,
			"versionNonce": 1154844800,
			"isDeleted": false,
			"id": "BkskB0lt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -668.319674876939,
			"y": 205.2953786996012,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 992.41796875,
			"height": 80,
			"seed": 1612767104,
			"groupIds": [],
			"frameId": "5WEZ7PuZMlbxgTCfCutHM",
			"roundness": null,
			"boundElements": [],
			"updated": 1707240660800,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* With high disk-access latencies gone, the function-call overhead for tuple-at-a-time processing becomes a more severe\nperformance issue in a main-memory-resident database than in a disk-resident database TRUE\n* Query compilation both requires fewer CPU instructions and can hide cache misses better than vectorized query processing.\nFALSE",
			"rawText": "* With high disk-access latencies gone, the function-call overhead for tuple-at-a-time processing becomes a more severe\nperformance issue in a main-memory-resident database than in a disk-resident database TRUE\n* Query compilation both requires fewer CPU instructions and can hide cache misses better than vectorized query processing.\nFALSE",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* With high disk-access latencies gone, the function-call overhead for tuple-at-a-time processing becomes a more severe\nperformance issue in a main-memory-resident database than in a disk-resident database TRUE\n* Query compilation both requires fewer CPU instructions and can hide cache misses better than vectorized query processing.\nFALSE",
			"lineHeight": 1.25,
			"baseline": 74
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#b2f2bb",
		"currentItemFillStyle": "cross-hatch",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1208.7621500185946,
		"scrollY": 1006.8809492957054,
		"zoom": {
			"value": 0.7000000000000001
		},
		"currentItemRoundness": "sharp",
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