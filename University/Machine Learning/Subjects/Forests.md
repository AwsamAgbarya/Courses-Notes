---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Learning Theory..... for Decision trees ^ynaUvDk3

Consider the hypothesis space H ^GJbPtUan

%%***>>>text element-link:[[Hypothesis space]]<<<***%%hold on a sec,
what is that? ^qXaHp7Q5

The generalization of correct classifications (of hypothesis h)
can be bounded as ^L4QfFkcQ

Size of H space ^ewgIk630

number of i.i.d
samples in space ^L88m7FpM

We observe that the generalization of the error
grows with the number of hypotheses
and shrinks with the number of data ^m60rBZDV

IN OTHER WORDS ^yW6nB4Wl

Grows with model complexity |H|
Shrinks with training data set m ^pJmrqojI

BUT WAIT ^SUWin59l

This only applies to the set 
of hypotheses that perfectly
fit the data! ^VFzPASyV

Lets make a much simpler model
 ^4E6Wbi2l

How large is the hypothesis space
space of the decision tree? ^LSN5Ah8Q

How do we find that out? ^XLdmflhq

Complexity of decision tree ^WhMg1TRM

General decision Tree with n binary features
that is expanded untill it perfectly fits the data
has a complexity of ^vqOqwAyN

all possible lookup tables of n binary features ^4OR6Kkhy

Decision tree of depth 0
 ^eVAUaVpz

Decision tree of depth k ^PoXpSdET

Idea ^aeRJlZ3L

Combine the predictions of
several randomized trees into one model
Forest! ^xHQbQ5AH

Train each Bootstrap tree model on a dataset of length N (duplicates allowed)
We use majority vote for classification and averaging for regression
Smoother decision boundary via lower variance ^yOJMynJS

if datasets are highly overlapping
predictions of trees become highly corrolated ^lPkcYeWG

Lets lower the variance more! ^XP3bSZJQ

Random forests ^dWY33LM0

Control the error via out of bag Samples:
Since we only grow our bootstrapped trees according to our samples, We use the out of bag samples
as a measure of error rate and run them through our tree to see the results and build further upon it.
Once we know our error we can tweak parameters to get lowest error
 ^VPpOySqE

Picking random tuples from the
dataset with duplicates allowed
Note that we only will use a subset
of their features though! ^NbnepCkc


# Embedded files
bf39b2bd84e0e6c18233672213dbf712e0352db2: $$\delta = $$
aa4c9b9655715080fb0dfe63983acdd6656f6d6b: [[Pasted Image 20240113192900_466.png]]
401bcac604059b9d966dc67190cb88fc2c0a6038: [[Pasted Image 20240113193522_530.png]]
54507bd990d2170d48703a915afa61f027f0c4ac: [[Pasted Image 20240113194013_597.png]]
6b5617ad35ef5d5325954528dbc2ecca19dd3ae2: [[Pasted Image 20240113194345_635.png]]
fca36c55729033c69768d213f791319f284bcd26: [[Pasted Image 20240113194814_671.png]]
e7b675c921beb23d63d3566b14c2069bf5afea71: [[Pasted Image 20240113195204_686.png]]
7fa667adf004bf162d1e216e80eb8e7faede81f7: [[Pasted Image 20240113195406_706.png]]
6555ad0647ea5fdd123df01f8f37325c9c1d0b54: [[Pasted Image 20240113195637_716.png]]
515a20461f7019d886fdb605b9ff8cd419ad146a: [[Pasted Image 20240113195652_717.png]]
78e31c435840e945b43dc759482fe97fffd742c1: [[Pasted Image 20240113195738_726.png]]
c74e69a95f5da8e772d048911721c02c8054aaa8: [[Pasted Image 20240113200606_814.png]]
a00c4fb89974e7bdcd8ec7e20c9408d90fc4699d: [[Pasted Image 20240119165847_459.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"type": "image",
			"version": 246,
			"versionNonce": 1714666739,
			"isDeleted": false,
			"id": "nn8Qec0FpVHjwyDfE_lC2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2627.613116659495,
			"y": -2984.654605726059,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 472.96275388504466,
			"height": 194.83458008434457,
			"seed": 1118431497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a00c4fb89974e7bdcd8ec7e20c9408d90fc4699d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 269,
			"versionNonce": 363397053,
			"isDeleted": false,
			"id": "VmBU24j_lpFfReHSambc8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1624.691080642578,
			"y": -3745.5558298240308,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 75.7256500319389,
			"height": 205.91152782657358,
			"seed": 681206713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "515a20461f7019d886fdb605b9ff8cd419ad146a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 508,
			"versionNonce": 892708499,
			"isDeleted": false,
			"id": "EA8iN5_KYaqslsbGofezF",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1474.6256757491628,
			"y": -4918.945569625703,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 291.3931378178212,
			"height": 265.4211407514502,
			"seed": 1238425207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aa4c9b9655715080fb0dfe63983acdd6656f6d6b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 525074461,
			"isDeleted": false,
			"id": "ynaUvDk3",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1361.3491612763203,
			"y": -4640.893906924048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 517.9461669921875,
			"height": 35,
			"seed": 910131993,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Learning Theory..... for Decision trees",
			"rawText": "Learning Theory..... for Decision trees",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Learning Theory..... for Decision trees",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 1267293235,
			"isDeleted": false,
			"id": "GJbPtUan",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1443.6506923898357,
			"y": -4593.263385422109,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 316.0596008300781,
			"height": 25,
			"seed": 1970064183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "phgFK7UmF9sUsZb7JT1s3",
					"type": "arrow"
				}
			],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Consider the hypothesis space H",
			"rawText": "Consider the hypothesis space H",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider the hypothesis space H",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 292549757,
			"isDeleted": false,
			"id": "phgFK7UmF9sUsZb7JT1s3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1769.3636598596504,
			"y": -4580.027157540427,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 182.8505449583281,
			"height": 46.55604281226806,
			"seed": 2102414519,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GJbPtUan",
				"focus": -0.22632714067652507,
				"gap": 9.653366639736532
			},
			"endBinding": {
				"elementId": "qXaHp7Q5",
				"focus": 0.19906708678422394,
				"gap": 6.063885515467405
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
					99.85933820602418,
					2.6989010325951313
				],
				[
					123.47472224123248,
					46.55604281226806
				],
				[
					182.8505449583281,
					45.88131755411905
				]
			]
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 1964334547,
			"isDeleted": false,
			"id": "qXaHp7Q5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1958.2780903334458,
			"y": -4550.7370482470715,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 110.67222595214844,
			"height": 40,
			"seed": 1207551961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "phgFK7UmF9sUsZb7JT1s3",
					"type": "arrow"
				}
			],
			"updated": 1708956061090,
			"link": "[[Hypothesis space]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "hold on a sec,\nwhat is that?",
			"rawText": "hold on a sec,\nwhat is that?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "hold on a sec,\nwhat is that?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 399924445,
			"isDeleted": false,
			"id": "L4QfFkcQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1367.5620867986818,
			"y": -4564.399610565102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 492.27301025390625,
			"height": 40,
			"seed": 1877641689,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The generalization of correct classifications (of hypothesis h)\ncan be bounded as",
			"rawText": "The generalization of correct classifications (of hypothesis h)\ncan be bounded as",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The generalization of correct classifications (of hypothesis h)\ncan be bounded as",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 1022372723,
			"isDeleted": false,
			"id": "WRsCjmR3yoBGeigoHyJtk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1490.9058273564597,
			"y": -4519.753425513474,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 299.74092949394003,
			"height": 42.63273614246412,
			"seed": 679288375,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "401bcac604059b9d966dc67190cb88fc2c0a6038",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 292,
			"versionNonce": 1779480893,
			"isDeleted": false,
			"id": "A7N1dN4mt83FjVRoY-2mm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1719.3174975738875,
			"y": -4480.818178076661,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 78.65387961691408,
			"height": 44.65940622316339,
			"seed": 1332358105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061090,
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
					-6.332303867463452,
					20.330028206066345
				],
				[
					-71.65501744761264,
					24.329378017096133
				],
				[
					-78.65387961691408,
					44.65940622316339
				]
			]
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 123749651,
			"isDeleted": false,
			"id": "ewgIk630",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1582.0175548280213,
			"y": -4434.492376098902,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 124.624267578125,
			"height": 20,
			"seed": 43954041,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061090,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Size of H space",
			"rawText": "Size of H space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Size of H space",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 171,
			"versionNonce": 1367378333,
			"isDeleted": false,
			"id": "GL5VscRbm1l6K0tRA7P5d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1770.0720647771195,
			"y": -4491.312228451155,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 51.1417081605764,
			"height": 55.10779981384621,
			"seed": 1774009401,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061090,
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
					-0.4174833319229947,
					30.893766562307974
				],
				[
					44.044491517884126,
					29.223833234615086
				],
				[
					50.724224828653405,
					55.10779981384621
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 1809590963,
			"isDeleted": false,
			"id": "L88m7FpM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1755.7801534363393,
			"y": -4436.413170303271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 130.0322723388672,
			"height": 40,
			"seed": 1611891225,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "number of i.i.d\nsamples in space",
			"rawText": "number of i.i.d\nsamples in space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of i.i.d\nsamples in space",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 202,
			"versionNonce": 1867992573,
			"isDeleted": false,
			"id": "m60rBZDV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1439.066528538433,
			"y": -4384.088458526585,
			"strokeColor": "#e03131",
			"backgroundColor": "#deb072",
			"width": 385.0247802734375,
			"height": 60,
			"seed": 214232697,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We observe that the generalization of the error\ngrows with the number of hypotheses\nand shrinks with the number of data",
			"rawText": "We observe that the generalization of the error\ngrows with the number of hypotheses\nand shrinks with the number of data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We observe that the generalization of the error\ngrows with the number of hypotheses\nand shrinks with the number of data",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 1326079059,
			"isDeleted": false,
			"id": "WCGJkTj7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1446.3637687057926,
			"y": -4511.432501928049,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 47.70509399845754,
			"height": 24.806648879197922,
			"seed": 24850,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bf39b2bd84e0e6c18233672213dbf712e0352db2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 20,
			"versionNonce": 1117161053,
			"isDeleted": false,
			"id": "yW6nB4Wl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1545.8298650150696,
			"y": -4296.157008280733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 146.56031799316406,
			"height": 20,
			"seed": 2039477815,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "IN OTHER WORDS",
			"rawText": "IN OTHER WORDS",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "IN OTHER WORDS",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 73,
			"versionNonce": 1019304435,
			"isDeleted": false,
			"id": "_X53C5tAiR6k-bvzkc8ES",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1428.4169528730038,
			"y": -4272.449015009094,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 388.8966749921638,
			"height": 92.06533530426734,
			"seed": 1792199001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "54507bd990d2170d48703a915afa61f027f0c4ac",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 1846522557,
			"isDeleted": false,
			"id": "pJmrqojI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1479.2160643703457,
			"y": -4179.694187248806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 318.5196533203125,
			"height": 50,
			"seed": 1072225559,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Grows with model complexity |H|\nShrinks with training data set m",
			"rawText": "Grows with model complexity |H|\nShrinks with training data set m",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Grows with model complexity |H|\nShrinks with training data set m",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 40,
			"versionNonce": 34055059,
			"isDeleted": false,
			"id": "Dfd6vOuniJwUGPUtnh-Ou",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1813.3085609817722,
			"y": -4225.1530911368545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 221.27643994008395,
			"height": 0.8746104345464119,
			"seed": 79220855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061091,
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
					221.27643994008395,
					0.8746104345464119
				]
			]
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 1046762269,
			"isDeleted": false,
			"id": "SUWin59l",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1875.1683373191365,
			"y": -4255.013677215048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 87.93617248535156,
			"height": 20,
			"seed": 1619412631,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "BUT WAIT",
			"rawText": "BUT WAIT",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BUT WAIT",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 123,
			"versionNonce": 118733107,
			"isDeleted": false,
			"id": "VFzPASyV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2057.4557843497882,
			"y": -4265.888287649594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 288.359619140625,
			"height": 75,
			"seed": 868913975,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This only applies to the set \nof hypotheses that perfectly\nfit the data!",
			"rawText": "This only applies to the set \nof hypotheses that perfectly\nfit the data!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This only applies to the set \nof hypotheses that perfectly\nfit the data!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 396,
			"versionNonce": 1879435133,
			"isDeleted": false,
			"id": "CuXldu-7MQ89Ob7LmgUho",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2188.516437401914,
			"y": -4168.303412891379,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 253.56285674625974,
			"height": 197.1354364310646,
			"seed": 421578585,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "RlWyaShK8qZClprjY1_qW",
				"focus": 0.1759442366908938,
				"gap": 16.88367628259789
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
					-18.02316719404689,
					181.7568197985729
				],
				[
					-253.56285674625974,
					197.1354364310646
				]
			]
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 1766595283,
			"isDeleted": false,
			"id": "4E6Wbi2l",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1978.908602748351,
			"y": -3955.679023048365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 250.33651733398438,
			"height": 40,
			"seed": 791221113,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets make a much simpler model\n",
			"rawText": "Lets make a much simpler model\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets make a much simpler model\n",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 239,
			"versionNonce": 892727261,
			"isDeleted": false,
			"id": "RlWyaShK8qZClprjY1_qW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1440.7668503730492,
			"y": -4059.759366629472,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 477.30305400000714,
			"height": 174.3858319563345,
			"seed": 1821087351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CuXldu-7MQ89Ob7LmgUho",
					"type": "arrow"
				},
				{
					"id": "OrrSZiSdCFNOp7SdgCHBn",
					"type": "arrow"
				}
			],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6b5617ad35ef5d5325954528dbc2ecca19dd3ae2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 69,
			"versionNonce": 1430734963,
			"isDeleted": false,
			"id": "Wt7hhPk8UPWiVUMljgw_w",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1647.8604791052257,
			"y": -4055.8476956493905,
			"strokeColor": "#ffffff",
			"backgroundColor": "#deb072",
			"width": 209.31555843956562,
			"height": 6.732371762676394,
			"seed": 1355575639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6120337966067382,
					0
				],
				[
					0,
					0
				],
				[
					-1.224067593213931,
					0
				],
				[
					-2.448135186427862,
					-0.6120337966071929
				],
				[
					-5.508304169462463,
					-1.224067593213931
				],
				[
					-11.01660833892447,
					-1.224067593213931
				],
				[
					-15.912878711779967,
					-1.224067593213931
				],
				[
					-20.19711528802827,
					-1.224067593213931
				],
				[
					-23.257284271062872,
					-1.224067593213931
				],
				[
					-27.541520847311403,
					-1.224067593213931
				],
				[
					-31.825757423559708,
					-1.224067593213931
				],
				[
					-36.722027796415205,
					-1.224067593213931
				],
				[
					-40.39423057605654,
					-1.224067593213931
				],
				[
					-44.06643335569811,
					-1.224067593213931
				],
				[
					-46.514568542125744,
					-1.836101389821124
				],
				[
					-48.962703728553606,
					-1.836101389821124
				],
				[
					-52.634906508194945,
					-2.448135186427862
				],
				[
					-55.08304169462258,
					-2.448135186427862
				],
				[
					-57.531176881050214,
					-2.448135186427862
				],
				[
					-60.591345864084815,
					-2.448135186427862
				],
				[
					-64.26354864372638,
					-2.448135186427862
				],
				[
					-67.32371762676098,
					-2.448135186427862
				],
				[
					-71.60795420300929,
					-2.448135186427862
				],
				[
					-73.44405559283018,
					-2.448135186427862
				],
				[
					-77.72829216907849,
					-2.448135186427862
				],
				[
					-80.78846115211309,
					-3.0601689830346004
				],
				[
					-84.46066393175465,
					-3.0601689830346004
				],
				[
					-89.96896810121689,
					-4.89627037285527
				],
				[
					-96.70133986389305,
					-5.508304169462463
				],
				[
					-100.37354264353462,
					-6.120337966069201
				],
				[
					-105.26981301638989,
					-6.732371762676394
				],
				[
					-110.16608338924516,
					-6.732371762676394
				],
				[
					-114.45031996549369,
					-6.732371762676394
				],
				[
					-120.57065793156289,
					-6.732371762676394
				],
				[
					-124.8548945078112,
					-6.732371762676394
				],
				[
					-129.1391310840595,
					-6.732371762676394
				],
				[
					-134.035401456915,
					-6.732371762676394
				],
				[
					-137.0955704399496,
					-6.732371762676394
				],
				[
					-140.76777321959116,
					-6.732371762676394
				],
				[
					-143.82794220262576,
					-6.732371762676394
				],
				[
					-146.88811118566036,
					-6.732371762676394
				],
				[
					-149.94828016869474,
					-6.732371762676394
				],
				[
					-154.84455054155023,
					-6.732371762676394
				],
				[
					-157.90471952458483,
					-6.732371762676394
				],
				[
					-160.96488850761943,
					-6.732371762676394
				],
				[
					-165.24912508386774,
					-6.120337966069201
				],
				[
					-168.9213278635093,
					-6.120337966069201
				],
				[
					-171.36946304993694,
					-5.508304169462463
				],
				[
					-176.87776721939917,
					-4.89627037285527
				],
				[
					-181.1620037956477,
					-4.2842365762485315
				],
				[
					-183.61013898207534,
					-4.2842365762485315
				],
				[
					-186.6703079651097,
					-4.2842365762485315
				],
				[
					-190.34251074475128,
					-3.6722027796417933
				],
				[
					-192.17861213457218,
					-3.6722027796417933
				],
				[
					-197.07488250742745,
					-3.6722027796417933
				],
				[
					-197.6869163040344,
					-3.6722027796417933
				],
				[
					-199.52301769385508,
					-3.6722027796417933
				],
				[
					-201.35911908367598,
					-3.6722027796417933
				],
				[
					-202.58318667688968,
					-3.6722027796417933
				],
				[
					-204.41928806671035,
					-3.6722027796417933
				],
				[
					-205.03132186331732,
					-3.6722027796417933
				],
				[
					-206.25538945653125,
					-3.6722027796417933
				],
				[
					-207.47945704974495,
					-3.6722027796417933
				],
				[
					-208.09149084635192,
					-3.6722027796417933
				],
				[
					-208.70352464295888,
					-3.6722027796417933
				],
				[
					-208.70352464295888,
					-3.6722027796417933
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 213,
			"versionNonce": 2080762941,
			"isDeleted": false,
			"id": "OrrSZiSdCFNOp7SdgCHBn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1824.3414836462346,
			"y": -3872.320549639022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 87.4608277574664,
			"height": 53.42342455875678,
			"seed": 122246615,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RlWyaShK8qZClprjY1_qW",
				"focus": -0.6572374902408502,
				"gap": 13.052985034115636
			},
			"endBinding": {
				"elementId": "LSN5Ah8Q",
				"focus": 0.5298013431504324,
				"gap": 8.143737600756367
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
					-12.549827638689749,
					45.17937949928455
				],
				[
					-87.4608277574664,
					53.42342455875678
				]
			]
		},
		{
			"type": "text",
			"version": 79,
			"versionNonce": 550224403,
			"isDeleted": false,
			"id": "LSN5Ah8Q",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1462.128336745043,
			"y": -3841.6989702006153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 266.60858154296875,
			"height": 40,
			"seed": 1049110455,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "OrrSZiSdCFNOp7SdgCHBn",
					"type": "arrow"
				}
			],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How large is the hypothesis space\nspace of the decision tree?",
			"rawText": "How large is the hypothesis space\nspace of the decision tree?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How large is the hypothesis space\nspace of the decision tree?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 90,
			"versionNonce": 1951882397,
			"isDeleted": false,
			"id": "qURXFD3fcMc50cSnYYdHw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1438.8362804923413,
			"y": -3816.96628921716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 251.8519613597573,
			"height": 5.358552369356403,
			"seed": 398337847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XLdmflhq",
				"focus": -1.1807703253985697,
				"gap": 13.114847300269503
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
					-251.8519613597573,
					-5.358552369356403
				]
			]
		},
		{
			"type": "text",
			"version": 54,
			"versionNonce": 617613235,
			"isDeleted": false,
			"id": "XLdmflhq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1222.8730140026187,
			"y": -3843.7590510639425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 202.84841918945312,
			"height": 20,
			"seed": 67446553,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "qURXFD3fcMc50cSnYYdHw",
					"type": "arrow"
				}
			],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How do we find that out?",
			"rawText": "How do we find that out?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we find that out?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 1440465149,
			"isDeleted": false,
			"id": "WhMg1TRM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 688.5709827103194,
			"y": -4052.249660862252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 369.54559326171875,
			"height": 35,
			"seed": 1470842583,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Complexity of decision tree",
			"rawText": "Complexity of decision tree",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Complexity of decision tree",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1467652435,
			"isDeleted": false,
			"id": "vqOqwAyN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 611.0189006145199,
			"y": -3963.120361505585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 495.83941650390625,
			"height": 75,
			"seed": 129647031,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "General decision Tree with n binary features\nthat is expanded untill it perfectly fits the data\nhas a complexity of",
			"rawText": "General decision Tree with n binary features\nthat is expanded untill it perfectly fits the data\nhas a complexity of",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "General decision Tree with n binary features\nthat is expanded untill it perfectly fits the data\nhas a complexity of",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 48,
			"versionNonce": 1712626013,
			"isDeleted": false,
			"id": "dreCXKm9hA2TrWfxCXtBH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 779.2104962023125,
			"y": -3874.7107211485413,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 150.00000000000003,
			"height": 73,
			"seed": 823906743,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fca36c55729033c69768d213f791319f284bcd26",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 68,
			"versionNonce": 639760115,
			"isDeleted": false,
			"id": "4OR6Kkhy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 662.9525995800841,
			"y": -3812.1830450395864,
			"strokeColor": "#e03131",
			"backgroundColor": "#deb072",
			"width": 367.9207763671875,
			"height": 20,
			"seed": 334911703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "all possible lookup tables of n binary features",
			"rawText": "all possible lookup tables of n binary features",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all possible lookup tables of n binary features",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 63,
			"versionNonce": 1045652925,
			"isDeleted": false,
			"id": "i_M1wUEgn9h2LIEK0zv9y",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 849.3091189195092,
			"y": -3770.771607773072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 0.6390955399294853,
			"height": 85.63880235055149,
			"seed": 922655191,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061091,
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
					-0.6390955399294853,
					85.63880235055149
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 256680083,
			"isDeleted": false,
			"id": "eVAUaVpz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 746.3072442684207,
			"y": -3665.959939224636,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 197.05641174316406,
			"height": 40,
			"seed": 25558327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Decision tree of depth 0\n",
			"rawText": "Decision tree of depth 0\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Decision tree of depth 0\n",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 41,
			"versionNonce": 1371121181,
			"isDeleted": false,
			"id": "ZoCc1F7gkrqGeroh4V3Xq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 775.2527367597912,
			"y": -3637.524054011194,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 143,
			"height": 62,
			"seed": 1904454681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pNIsINCpEWJ4ycm2c4epQ",
					"type": "arrow"
				}
			],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e7b675c921beb23d63d3566b14c2069bf5afea71",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 190,
			"versionNonce": 2091980339,
			"isDeleted": false,
			"id": "pNIsINCpEWJ4ycm2c4epQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 765.6261618439763,
			"y": -3604.1024652835213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 77.29962015003821,
			"height": 1.1515335275425969,
			"seed": 1291074295,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZoCc1F7gkrqGeroh4V3Xq",
				"focus": -0.037830651400267645,
				"gap": 9.6265749158149
			},
			"endBinding": {
				"elementId": "P_gFmCsMFnrvtgLMR9e4Q",
				"focus": 0.015567733589168575,
				"gap": 5.526389021184428
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
					-77.29962015003821,
					1.1515335275425969
				]
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 859363965,
			"isDeleted": false,
			"id": "PoXpSdET",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 437.8284436156965,
			"y": -3664.0441359544498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 193.8404083251953,
			"height": 20,
			"seed": 91473879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061091,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Decision tree of depth k",
			"rawText": "Decision tree of depth k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Decision tree of depth k",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 165,
			"versionNonce": 1563809747,
			"isDeleted": false,
			"id": "P_gFmCsMFnrvtgLMR9e4Q",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 373.0636412622587,
			"y": -3625.682483914689,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 309.73651141049504,
			"height": 49.40101321230681,
			"seed": 1541901431,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pNIsINCpEWJ4ycm2c4epQ",
					"type": "arrow"
				}
			],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7fa667adf004bf162d1e216e80eb8e7faede81f7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 305,
			"versionNonce": 462586589,
			"isDeleted": false,
			"id": "svG64v-enIClhWr6Oi5-S",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1817.0251989567882,
			"y": -4014.9180903416436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deb072",
			"width": 121.77317218964663,
			"height": 276.04662600536403,
			"seed": 367333977,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "UdcnYDMFs-YcpclQVMnah",
				"focus": -0.07260183136915425,
				"gap": 17.005739663113673
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
					106.77226557716085,
					85.72955630283013
				],
				[
					121.77317218964663,
					276.04662600536403
				]
			]
		},
		{
			"type": "image",
			"version": 228,
			"versionNonce": 2129749363,
			"isDeleted": false,
			"id": "UdcnYDMFs-YcpclQVMnah",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1682.6610883740414,
			"y": -3721.865724673166,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 570.0586084678949,
			"height": 162.23600084334348,
			"seed": 2043142585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "svG64v-enIClhWr6Oi5-S",
					"type": "arrow"
				}
			],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6555ad0647ea5fdd123df01f8f37325c9c1d0b54",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 287,
			"versionNonce": 794304317,
			"isDeleted": false,
			"id": "8qoUpwau2ohDXzNJZ9nh2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1740.104322613993,
			"y": -3540.407503443294,
			"strokeColor": "transparent",
			"backgroundColor": "#deb072",
			"width": 397.0729250107506,
			"height": 257.3797995852817,
			"seed": 1397259831,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "78e31c435840e945b43dc759482fe97fffd742c1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 96,
			"versionNonce": 690634515,
			"isDeleted": false,
			"id": "Z27Mmz1aBURVZ8xmxACFK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1612.9526420674638,
			"y": -3734.784001453855,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 658.6723628715454,
			"height": 469.47923736588837,
			"seed": 737141335,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "dfNko81SOmn8XuTzXAeVH",
					"type": "arrow"
				}
			],
			"updated": 1708956061092,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 57,
			"versionNonce": 82522013,
			"isDeleted": false,
			"id": "dfNko81SOmn8XuTzXAeVH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2273.698420726454,
			"y": -3509.4647887270257,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 365.24545027852264,
			"height": 1.2014652969687631,
			"seed": 951900855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Z27Mmz1aBURVZ8xmxACFK",
				"focus": -0.035324137897467994,
				"gap": 2.073415787444901
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
					365.24545027852264,
					-1.2014652969687631
				]
			]
		},
		{
			"type": "text",
			"version": 19,
			"versionNonce": 1985406131,
			"isDeleted": false,
			"id": "aeRJlZ3L",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2428.5348668558368,
			"y": -3561.4190047148722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 65.18428039550781,
			"height": 35,
			"seed": 1942212921,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Idea",
			"rawText": "Idea",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 1786590205,
			"isDeleted": false,
			"id": "xHQbQ5AH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2665.461405102934,
			"y": -3564.7321923875916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 554.9063720703125,
			"height": 105,
			"seed": 471389401,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Combine the predictions of\nseveral randomized trees into one model\nForest!",
			"rawText": "Combine the predictions of\nseveral randomized trees into one model\nForest!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Combine the predictions of\nseveral randomized trees into one model\nForest!",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "line",
			"version": 3957,
			"versionNonce": 1847449171,
			"isDeleted": false,
			"id": "0K_nT87kvBOSpS17lMY_y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2699.627891067842,
			"y": -3618.720549749199,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 1622424025,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 296,
			"versionNonce": 1812966493,
			"isDeleted": false,
			"id": "7k3Zy9-wzdPm-PimE97p7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2688.917345820076,
			"y": -3638.0404047170605,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 1235326649,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 1599443955,
			"isDeleted": false,
			"id": "Mtie-ORUCPNYVBWK0-ndl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2694.3215668071675,
			"y": -3637.592408076754,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 1787844505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 382,
			"versionNonce": 427038909,
			"isDeleted": false,
			"id": "KObnmM7fD1JYnsoi3pQpJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2688.8347694607965,
			"y": -3637.4509520641163,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 95681657,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 434,
			"versionNonce": 2047122835,
			"isDeleted": false,
			"id": "IVjgfJbT3I-u4JW_GG1Mp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2700.521832520641,
			"y": -3633.2158642095724,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 1255146841,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 383,
			"versionNonce": 206305565,
			"isDeleted": false,
			"id": "RrVHHBsoq6gyNWS_zy_qJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2694.971788964835,
			"y": -3630.276117945527,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 624423481,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 361,
			"versionNonce": 694252339,
			"isDeleted": false,
			"id": "nzkfFb4irCOe888C9gVRg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2710.1340026283274,
			"y": -3629.102552792191,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 1238319897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 412,
			"versionNonce": 772328829,
			"isDeleted": false,
			"id": "0DHK_uTTTP_nktpKBBFl0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2714.6821758675737,
			"y": -3635.726758855152,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 84506617,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 341,
			"versionNonce": 768775379,
			"isDeleted": false,
			"id": "1aifE-c-V85lrwBEUZMD_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2692.259173220653,
			"y": -3626.8234214210815,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 1223299289,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 370,
			"versionNonce": 1038882269,
			"isDeleted": false,
			"id": "QaHLJnaDoA5aaLV8kMPno",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2683.9255938741826,
			"y": -3636.037933201915,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 2063895993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 497,
			"versionNonce": 1995342451,
			"isDeleted": false,
			"id": "7KyuogkR0SrzKVU01oELI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2694.77987091644,
			"y": -3647.4361469136315,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 41709209,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 386355773,
			"isDeleted": false,
			"id": "Ava46IUUsRii0cB1I32Tc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2716.093954787291,
			"y": -3651.050183095781,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 369439609,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 828,
			"versionNonce": 1031519251,
			"isDeleted": false,
			"id": "It1U16sZ5fFc9qF5V78A8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2716.3434816696936,
			"y": -3658.0142675756297,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 1239571545,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 362,
			"versionNonce": 909902493,
			"isDeleted": false,
			"id": "Z8tYoTf_49Ez_IOzitBWf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2710.7359565922197,
			"y": -3658.6666752431797,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 1575446841,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 358,
			"versionNonce": 1567670707,
			"isDeleted": false,
			"id": "ObaRvzhUxj2bygh-Cj2cr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2699.680018571077,
			"y": -3655.52594523117,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 1266145817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 347,
			"versionNonce": 3909373,
			"isDeleted": false,
			"id": "U8DqEZd3WYwX_VhSCOMly",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2691.593803565451,
			"y": -3661.351321173478,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 327626489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 304,
			"versionNonce": 1878266707,
			"isDeleted": false,
			"id": "eH2F47F3rNcgdjj8IA3P9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2691.4831514594184,
			"y": -3656.163746460006,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 1285089241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 340,
			"versionNonce": 1200078685,
			"isDeleted": false,
			"id": "YMNf_ZkVETm37dXE3Zfnh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2687.510787180392,
			"y": -3658.490835682435,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 1891665081,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 331,
			"versionNonce": 626798835,
			"isDeleted": false,
			"id": "vVPZ9io9HpszeA-_qOxms",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2681.3860981576977,
			"y": -3659.6277525640194,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 1805747609,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 480,
			"versionNonce": 309447613,
			"isDeleted": false,
			"id": "KzK4NgYTiRKDZBWE3sQhW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2694.6339090864567,
			"y": -3664.3652693132226,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 1752132217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 310,
			"versionNonce": 1596955283,
			"isDeleted": false,
			"id": "T6M_78ZotNfBsC8M3q_K9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2716.3577710309546,
			"y": -3640.7513429582714,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 1609413465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 369,
			"versionNonce": 555437085,
			"isDeleted": false,
			"id": "Gd4XkC7hS-TEur058DRDn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2683.6422414695676,
			"y": -3652.271774680487,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 1718607929,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061092,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 471,
			"versionNonce": 170184755,
			"isDeleted": false,
			"id": "M2-HbJjet4ZSp5BqOodcv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2677.923873725603,
			"y": -3647.31847619802,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 970551577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061092,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 636,
			"versionNonce": 863355005,
			"isDeleted": false,
			"id": "tTebh33hz9vnb_ncBjY0N",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2697.5997644248055,
			"y": -3645.8470472133063,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 262006265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061093,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 425,
			"versionNonce": 941773267,
			"isDeleted": false,
			"id": "tQthQAqR6vVPIo-QTKG3z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2700.906015509197,
			"y": -3636.0636992201944,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 583057113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 400,
			"versionNonce": 256026845,
			"isDeleted": false,
			"id": "d8OYY7TcgVR6jc7TIH0RG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2682.101270652263,
			"y": -3637.5225381399923,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 30768057,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 773,
			"versionNonce": 2050924403,
			"isDeleted": false,
			"id": "kxTNXRo14U9fxpdLAkWaM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2677.9956919633664,
			"y": -3640.446738968804,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 486513817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 444,
			"versionNonce": 1175684413,
			"isDeleted": false,
			"id": "4oM9QspXyJr9eOdA7RmPq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2692.359693546981,
			"y": -3619.523644787087,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 334668153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 599,
			"versionNonce": 2059417875,
			"isDeleted": false,
			"id": "zOf0FU1oh79mGW3FOXXNB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2689.191737326585,
			"y": -3620.0734459172418,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 1139935833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 760,
			"versionNonce": 994694557,
			"isDeleted": false,
			"id": "lpF13fWKTcCyYnpmUa-LK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2689.033768081412,
			"y": -3620.155829753084,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 366040889,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 1461558963,
			"isDeleted": false,
			"id": "b9DIEHBiGgaJm8X8A2dsV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2687.8425741134442,
			"y": -3617.0430915557827,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 200542233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 673,
			"versionNonce": 1779898877,
			"isDeleted": false,
			"id": "9vLDcuTrHs64GrnZIscOE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2687.0930206693783,
			"y": -3615.4346118058074,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 273521913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 507,
			"versionNonce": 972902483,
			"isDeleted": false,
			"id": "B14BkKwZN7uOYh2AlfCeA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2689.9594907245314,
			"y": -3609.3714996544127,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 39949785,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 430,
			"versionNonce": 1803342429,
			"isDeleted": false,
			"id": "lXc2me-qhGCaCcZ6O_HEB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2687.9399158811143,
			"y": -3610.4433900619465,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 88306361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 663,
			"versionNonce": 892718579,
			"isDeleted": false,
			"id": "lstVVukLplMzjV9DNSmz5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2686.1650648369123,
			"y": -3613.9375450316015,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 227980185,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 1011646141,
			"isDeleted": false,
			"id": "68HBK9HJ4of7RZiX0d6ZC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2685.308522147669,
			"y": -3609.171795830725,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.8835727562580378,
			"height": 5.0743499232385645,
			"seed": 797890681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 506,
			"versionNonce": 1540200339,
			"isDeleted": false,
			"id": "cxzjuOlsm53cYLfi9oFEe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2695.3395400698346,
			"y": -3619.1711693513907,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 753885529,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 689,
			"versionNonce": 1126670109,
			"isDeleted": false,
			"id": "npMtpWcDA7e7u7DWXJ-lq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2699.58215213076,
			"y": -3614.0060539765423,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 1124847161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 404,
			"versionNonce": 469445939,
			"isDeleted": false,
			"id": "4cfjgOynLVmnCNI6OQnxw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2698.0504534875254,
			"y": -3613.1311090306644,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 952606489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 350,
			"versionNonce": 377467773,
			"isDeleted": false,
			"id": "AFEsCUjBl3Vczu8jGkEF9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2700.760825079674,
			"y": -3613.9854877969037,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 748049401,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1385,
			"versionNonce": 1495600851,
			"isDeleted": false,
			"id": "_AoCUCmsQ5myHJ4HpgwYU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2699.628283199613,
			"y": -3614.043844726929,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 578514137,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 400,
			"versionNonce": 43400157,
			"isDeleted": false,
			"id": "tI-BT5YxVImDVvDldet6a",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2697.4996319544034,
			"y": -3617.9068310434564,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 1376414137,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 606,
			"versionNonce": 1172421747,
			"isDeleted": false,
			"id": "dER31Kxinxdp6gr42-7_4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2698.692263762916,
			"y": -3618.7839475080455,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 879151769,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 1333573693,
			"isDeleted": false,
			"id": "v_HbLKCBqJLvcK_PADpQ0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2702.3115592980957,
			"y": -3617.9786714180614,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 1380192121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 394,
			"versionNonce": 2113386003,
			"isDeleted": false,
			"id": "iDNopkFZ_65CYLgAYewlC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2705.7931910883394,
			"y": -3617.6065553335175,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 1374009433,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 502,
			"versionNonce": 1192536221,
			"isDeleted": false,
			"id": "eYisjAlhH1JiDEppyM3xS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2713.262026390202,
			"y": -3617.482484663232,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 1159677241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1275,
			"versionNonce": 1616739251,
			"isDeleted": false,
			"id": "xiFe4ei9AHu3WJHexe4IS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2688.6202614102463,
			"y": -3620.338934376905,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 928265753,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 427,
			"versionNonce": 2064616701,
			"isDeleted": false,
			"id": "9JWeXzlkUmHJViNSwZ-LH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2679.6653096395526,
			"y": -3618.5957920671917,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 2071464697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 426,
			"versionNonce": 691637587,
			"isDeleted": false,
			"id": "ahDKO2zMlDcdSVQAbajdD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2681.3884364003,
			"y": -3617.697194144156,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 974013401,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 428,
			"versionNonce": 1257170269,
			"isDeleted": false,
			"id": "YFBwSQZGimBxORcko3CIt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2678.557319355987,
			"y": -3620.0334241185583,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 1059741881,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 416,
			"versionNonce": 1273129715,
			"isDeleted": false,
			"id": "zqBQaB3FPc8dg_fHmLl9j",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2680.0801251071657,
			"y": -3621.803231526592,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 141549977,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 384,
			"versionNonce": 704917949,
			"isDeleted": false,
			"id": "SmDQeRhZlW1irVgmpVSN0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2676.1795892925493,
			"y": -3623.4730254074775,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 319964793,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 330,
			"versionNonce": 215913619,
			"isDeleted": false,
			"id": "sGTFAbYrt_ZJMCBj8x6AJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2674.4771181269166,
			"y": -3623.4828222515544,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 1775570777,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 628159005,
			"isDeleted": false,
			"id": "fujwtrXzfJrfJMC47JTEI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2696.461220549175,
			"y": -3620.869823620082,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 1930148921,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 860,
			"versionNonce": 1541704243,
			"isDeleted": false,
			"id": "9_2TNaAj_Za5PO-hKxSM1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2684.7504067638124,
			"y": -3607.4308423884636,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 2124008729,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 785,
			"versionNonce": 707176061,
			"isDeleted": false,
			"id": "SuPO6asO-eew8CF7bjZib",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2677.5108956624986,
			"y": -3604.9279616549356,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 334676473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 656,
			"versionNonce": 1843055571,
			"isDeleted": false,
			"id": "XRTJ3QtuY2ptWoME2LstD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2679.749524321132,
			"y": -3645.497636148918,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1710809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061093,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 725,
			"versionNonce": 182898397,
			"isDeleted": false,
			"id": "eOI4-pqykfRnuVOveXZVj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2684.5831357188135,
			"y": -3642.931440314172,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 597907385,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 723,
			"versionNonce": 383244659,
			"isDeleted": false,
			"id": "e0tBFlEb1xw5wCAzyE_BV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2700.304027302909,
			"y": -3644.1262150880716,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 11663513,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061093,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 761,
			"versionNonce": 1178790717,
			"isDeleted": false,
			"id": "Dvm8hhC_Vwymzo9JmILKp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2705.183964164251,
			"y": -3641.0773062836774,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 150568313,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3959,
			"versionNonce": 1679962899,
			"isDeleted": false,
			"id": "CsVKqVZPTgGhcDvJkaQqp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2774.0750396905314,
			"y": -3669.69269902941,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 1781634871,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 298,
			"versionNonce": 211581853,
			"isDeleted": false,
			"id": "kNj4Bb9J1cms2Azu5Fhvc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2763.364494442765,
			"y": -3689.012553997272,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 1418172503,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061093,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 307,
			"versionNonce": 1982879923,
			"isDeleted": false,
			"id": "TDY8QSMsUPhHTgJvzTyNz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2768.7687154298565,
			"y": -3688.564557356965,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 1119909239,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 384,
			"versionNonce": 103088125,
			"isDeleted": false,
			"id": "HuZTSM7LA3i4PB11DHrSE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2763.281918083485,
			"y": -3688.4231013443273,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 1814081175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 436,
			"versionNonce": 447269459,
			"isDeleted": false,
			"id": "A5Mn_wSrRxcPKPtvQ_snP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2774.96898114333,
			"y": -3684.1880134897833,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 727499703,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 385,
			"versionNonce": 1490942045,
			"isDeleted": false,
			"id": "EAdgc1dHtU-QETeaSA-dH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2769.418937587524,
			"y": -3681.248267225739,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 278475991,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 363,
			"versionNonce": 643958771,
			"isDeleted": false,
			"id": "63QWi9g_pXglhWb2ey8nQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2784.5811512510163,
			"y": -3680.0747020724025,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 862618103,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 414,
			"versionNonce": 1855513789,
			"isDeleted": false,
			"id": "2k_sKiTPkQOn88cVVZAZn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2789.1293244902627,
			"y": -3686.6989081353636,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 1154820887,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 343,
			"versionNonce": 258118035,
			"isDeleted": false,
			"id": "bkQUKHgygFsDMPy5tGwhN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2766.7063218433414,
			"y": -3677.795570701293,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 1632481335,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 372,
			"versionNonce": 2063025437,
			"isDeleted": false,
			"id": "WJhCI0zZugvhOk4A8ubV2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2758.372742496871,
			"y": -3687.010082482127,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 582521175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 499,
			"versionNonce": 1189144371,
			"isDeleted": false,
			"id": "b7g1dlqJNqMaX5HX3xtNk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2769.2270195391284,
			"y": -3698.4082961938434,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 1919569527,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 1097505149,
			"isDeleted": false,
			"id": "Exz1ZTDZ6RysnF0CGN0nP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2790.5411034099798,
			"y": -3702.0223323759924,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 455567255,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 830,
			"versionNonce": 1396934867,
			"isDeleted": false,
			"id": "xkeW_05rngDeU0zQOMFHg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2790.790630292382,
			"y": -3708.986416855841,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 455367863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 364,
			"versionNonce": 456417757,
			"isDeleted": false,
			"id": "2TET6jtUb66_xpJo5-jta",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2785.183105214908,
			"y": -3709.6388245233916,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 906341847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 360,
			"versionNonce": 706803315,
			"isDeleted": false,
			"id": "CjMhTnSMiDhyECIaxGPTr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2774.1271671937666,
			"y": -3706.4980945113816,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 1189075703,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 349,
			"versionNonce": 1030102589,
			"isDeleted": false,
			"id": "RMoeuzKLpQKDqV-lJsBRN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2766.0409521881393,
			"y": -3712.3234704536894,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 1379361815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 306,
			"versionNonce": 1245687827,
			"isDeleted": false,
			"id": "OTXkme6ja4jt3uUV7pfOA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2765.9303000821074,
			"y": -3707.1358957402176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 1476446519,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 342,
			"versionNonce": 1054953117,
			"isDeleted": false,
			"id": "_ofYuLsPEnuK4xwi3rD4R",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2761.9579358030805,
			"y": -3709.4629849626467,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 1705019991,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 333,
			"versionNonce": 362165683,
			"isDeleted": false,
			"id": "wUectx8rLeQiSy1PcZARS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2755.8332467803866,
			"y": -3710.5999018442303,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 1743464311,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 482,
			"versionNonce": 1582789373,
			"isDeleted": false,
			"id": "u4FhJ8gIfT4AXLK58XCUO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2769.081057709145,
			"y": -3715.337418593434,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 1025843351,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 312,
			"versionNonce": 1800079187,
			"isDeleted": false,
			"id": "t_SZM2SJwmOXOSN4V5F-_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2790.804919653643,
			"y": -3691.723492238483,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 117634487,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 371,
			"versionNonce": 139070301,
			"isDeleted": false,
			"id": "HNmAcTvOeeT-h_k5YLVKc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2758.0893900922565,
			"y": -3703.243923960699,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 1017718487,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 473,
			"versionNonce": 28615923,
			"isDeleted": false,
			"id": "Fb1oUW_NPBaU2t8qk0T75",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2752.371022348292,
			"y": -3698.2906254782315,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 2091660279,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061094,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 638,
			"versionNonce": 487233469,
			"isDeleted": false,
			"id": "R5HUii94tPTR9v20sX4Qz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2772.046913047494,
			"y": -3696.819196493517,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 521182487,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061094,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 427,
			"versionNonce": 5869203,
			"isDeleted": false,
			"id": "ca_MtnIqBDe4KlXo775FI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2775.353164131886,
			"y": -3687.035848500406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 122348087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 402,
			"versionNonce": 1991940125,
			"isDeleted": false,
			"id": "g5Us0L6rQUYvy0sk9OUR4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2756.548419274952,
			"y": -3688.4946874202037,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 910132055,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 775,
			"versionNonce": 1508918323,
			"isDeleted": false,
			"id": "E93uuZsu_itT0MAJ2bHDZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2752.4428405860554,
			"y": -3691.4188882490157,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 474153079,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 446,
			"versionNonce": 793480317,
			"isDeleted": false,
			"id": "XybIIpZEuG4ugsFYUlyQv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2766.80684216967,
			"y": -3670.495794067299,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 723114391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 601,
			"versionNonce": 1717519827,
			"isDeleted": false,
			"id": "EgUMhViHkHPQe9x2Oz8mT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2763.6388859492745,
			"y": -3671.045595197453,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 670600887,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 762,
			"versionNonce": 645854429,
			"isDeleted": false,
			"id": "nshAXtXQfpMf4KUguxJ4w",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2763.4809167041003,
			"y": -3671.127979033295,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 1032036311,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 1019024243,
			"isDeleted": false,
			"id": "0eGBDswhOoEy2cElWUi2j",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2762.2897227361336,
			"y": -3668.015240835994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 1305447671,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 675,
			"versionNonce": 1206276413,
			"isDeleted": false,
			"id": "5ovUN6yb0gn_Dcj0bCzls",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2761.5401692920677,
			"y": -3666.406761086019,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 73455127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 509,
			"versionNonce": 1297100051,
			"isDeleted": false,
			"id": "3JAPsbbl_4fz_vSmYqCQF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2764.4066393472203,
			"y": -3660.3436489346236,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 673970999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 432,
			"versionNonce": 283320733,
			"isDeleted": false,
			"id": "Nk2w4WcaKat_N-F5pDVzT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2762.3870645038032,
			"y": -3661.4155393421584,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 764771415,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 665,
			"versionNonce": 999232179,
			"isDeleted": false,
			"id": "9ab1_yvQ7MhoeM7JzrkyM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2760.6122134596008,
			"y": -3664.9096943118125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 141678967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 452,
			"versionNonce": 1453778429,
			"isDeleted": false,
			"id": "xzTI5NPQiyGUMl1ILGm0t",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2759.755670770358,
			"y": -3660.143945110936,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.883572756258038,
			"height": 5.0743499232385645,
			"seed": 1040552599,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 508,
			"versionNonce": 2015380563,
			"isDeleted": false,
			"id": "hcSETc57i13jaYL6BfLaJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2769.786688692524,
			"y": -3670.143318631602,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 923084727,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 691,
			"versionNonce": 1278418525,
			"isDeleted": false,
			"id": "bKZkp9R1dzDhod62uKKGD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2774.029300753449,
			"y": -3664.978203256754,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 1368725719,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 406,
			"versionNonce": 450511347,
			"isDeleted": false,
			"id": "M-luOXy8YFmNh83gSu6So",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2772.497602110214,
			"y": -3664.103258310876,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 860481015,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 352,
			"versionNonce": 1213811389,
			"isDeleted": false,
			"id": "7OMo46aqb25k5Q08IF5rB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2775.2079737023632,
			"y": -3664.957637077115,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 1529351959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1387,
			"versionNonce": 2093190035,
			"isDeleted": false,
			"id": "vZVHtmhEtJVaKbd0HeMnc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2774.0754318223026,
			"y": -3665.0159940071403,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 1940132919,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 402,
			"versionNonce": 1270541085,
			"isDeleted": false,
			"id": "Va6iF0bppt4BgSeHa7mRc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2771.946780577093,
			"y": -3668.878980323668,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 1688368471,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 608,
			"versionNonce": 303210803,
			"isDeleted": false,
			"id": "O9FkYeXBVxsQN1EdH1x4O",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2773.1394123856044,
			"y": -3669.756096788257,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 628601463,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 479,
			"versionNonce": 1187610493,
			"isDeleted": false,
			"id": "d3-A6eusqR_KmTBQdFgDv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2776.758707920784,
			"y": -3668.950820698273,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 1323846551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 396,
			"versionNonce": 70124243,
			"isDeleted": false,
			"id": "Pl3KLW2IHeItiPvZ_92_Q",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2780.2403397110284,
			"y": -3668.578704613729,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 1831387319,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 504,
			"versionNonce": 533104605,
			"isDeleted": false,
			"id": "hh7KsomTGe73dsprp3-YP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2787.709175012891,
			"y": -3668.4546339434432,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 299733463,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1277,
			"versionNonce": 195833971,
			"isDeleted": false,
			"id": "T-7cfTl8dOjJ9q_JWmnrW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2763.067410032935,
			"y": -3671.3110836571163,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 639319799,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 429,
			"versionNonce": 2026079293,
			"isDeleted": false,
			"id": "qZYD4Jf5HyN5ZmH1jrJtu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2754.1124582622415,
			"y": -3669.567941347403,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 2087077911,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 428,
			"versionNonce": 173255187,
			"isDeleted": false,
			"id": "hU9fSDX31xXY33s-nLaiW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2755.835585022989,
			"y": -3668.6693434243675,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 582167863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 430,
			"versionNonce": 899806365,
			"isDeleted": false,
			"id": "WSU92AV2rB4ZOUuDJZ10E",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2753.004467978676,
			"y": -3671.0055733987697,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 1952869975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061094,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 418,
			"versionNonce": 1696264115,
			"isDeleted": false,
			"id": "VtlFRtSDi9_WLcVmPHkft",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2754.5272737298546,
			"y": -3672.7753808068032,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 1817480055,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 386,
			"versionNonce": 1108564221,
			"isDeleted": false,
			"id": "hpAxC91Dgy1nQ9spD8UjO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2750.6267379152378,
			"y": -3674.445174687689,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 918684823,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 332,
			"versionNonce": 505971027,
			"isDeleted": false,
			"id": "AIFzOjJP-gyjDRFFwFA9m",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2748.9242667496055,
			"y": -3674.4549715317658,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 56842679,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 356,
			"versionNonce": 395915613,
			"isDeleted": false,
			"id": "PZmTL6Xc2CqT2c5lCd-Os",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2770.9083691718643,
			"y": -3671.841972900294,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 391973591,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 862,
			"versionNonce": 785571571,
			"isDeleted": false,
			"id": "gKE1Bvjk63byHXWN07N30",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2759.1975553865013,
			"y": -3658.4029916686754,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 524523511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 787,
			"versionNonce": 59047357,
			"isDeleted": false,
			"id": "tndd2n_wT1A8lnyZGn3VT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2751.9580442851875,
			"y": -3655.900110935147,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 1092321559,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 658,
			"versionNonce": 564168851,
			"isDeleted": false,
			"id": "KfpjLXI2xpGqaeAF9hMZ-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2754.196672943821,
			"y": -3696.4697854291294,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1851344439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 727,
			"versionNonce": 754466333,
			"isDeleted": false,
			"id": "1sivotiGloX8OTTpopqtl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2759.030284341503,
			"y": -3693.903589594383,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 1977706327,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 725,
			"versionNonce": 1816657459,
			"isDeleted": false,
			"id": "aFoYulf8MGEdidfpa7Yzf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2774.7511759255976,
			"y": -3695.0983643682825,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1443390583,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 763,
			"versionNonce": 1524920957,
			"isDeleted": false,
			"id": "KxY4ublfsQao8w44zk0Hc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2779.6311127869394,
			"y": -3692.0494555638884,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 1318239639,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3964,
			"versionNonce": 162512851,
			"isDeleted": false,
			"id": "qkD-xq0IHDW4iUFV91ieY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2849.000914202291,
			"y": -3634.9772364127098,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 1574756567,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 303,
			"versionNonce": 2047548125,
			"isDeleted": false,
			"id": "cfQLSaqgrxYKkpb4a-zhQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2838.2903689545255,
			"y": -3654.2970913805707,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 1935191543,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 312,
			"versionNonce": 1408126323,
			"isDeleted": false,
			"id": "p3oNt0WjH9HdRv1q14-aE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2843.694589941617,
			"y": -3653.8490947402647,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 1042142999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 389,
			"versionNonce": 1660794685,
			"isDeleted": false,
			"id": "hsnm1HfBaFDE8nQykSOJg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2838.2077925952462,
			"y": -3653.707638727627,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 77650999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 441,
			"versionNonce": 508176147,
			"isDeleted": false,
			"id": "IPhpIA9Bs6aNHsJPvBQia",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2849.8948556550904,
			"y": -3649.472550873083,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 1254505815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 390,
			"versionNonce": 1612564381,
			"isDeleted": false,
			"id": "PwlCg1sQXHWhvOyrDPYRC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2844.3448120992844,
			"y": -3646.5328046090367,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 602045047,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 368,
			"versionNonce": 255446195,
			"isDeleted": false,
			"id": "T1CROem6OulCOgChJcg_p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2859.5070257627767,
			"y": -3645.3592394557013,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 1153045399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 419,
			"versionNonce": 1939655677,
			"isDeleted": false,
			"id": "SNwAQFQ6TNitv9ltz4Sg2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2864.055199002023,
			"y": -3651.9834455186624,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 1434552503,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 348,
			"versionNonce": 979615315,
			"isDeleted": false,
			"id": "sALGJjMTvJgr_GQHy6TAh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2841.6321963551027,
			"y": -3643.0801080845918,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 64838103,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 377,
			"versionNonce": 1568425053,
			"isDeleted": false,
			"id": "x3f0x5PCUwczwVi08Rm8_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2833.2986170086324,
			"y": -3652.294619865425,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 1424099063,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 504,
			"versionNonce": 2057206771,
			"isDeleted": false,
			"id": "11VAgH5v2xM--2FfIznTO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2844.1528940508897,
			"y": -3663.6928335771413,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 924061719,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 458,
			"versionNonce": 1636675773,
			"isDeleted": false,
			"id": "0RAxT5jT4Z5dfBBI_l8B2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2865.46697792174,
			"y": -3667.306869759291,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 1416099127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 835,
			"versionNonce": 200312211,
			"isDeleted": false,
			"id": "M0vqWUC8aBTkX2x35QXx6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2865.7165048041434,
			"y": -3674.27095423914,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 608319063,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 369,
			"versionNonce": 1299353885,
			"isDeleted": false,
			"id": "85v-Pf-ZktrBedA3xODUo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2860.1089797266695,
			"y": -3674.9233619066895,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 1031230327,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 365,
			"versionNonce": 1703959347,
			"isDeleted": false,
			"id": "jJkCWoj41z-dZ4wQoBRKq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2849.053041705526,
			"y": -3671.7826318946804,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 1749798039,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 1050436989,
			"isDeleted": false,
			"id": "TpYtzjOZbA6Sm935nBQ-L",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2840.9668266999006,
			"y": -3677.6080078369882,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 1886658999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 311,
			"versionNonce": 1407483091,
			"isDeleted": false,
			"id": "YqaettQRIZx5n5EP75T57",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2840.8561745938678,
			"y": -3672.4204331235164,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 924111575,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 347,
			"versionNonce": 676113885,
			"isDeleted": false,
			"id": "_-gBKLU4bznq8Yf1ETGxr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2836.883810314842,
			"y": -3674.7475223459446,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 79847415,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 338,
			"versionNonce": 1384344179,
			"isDeleted": false,
			"id": "jTEqBuXtvcj-dFujMjVww",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2830.759121292147,
			"y": -3675.88443922753,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 461457687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 487,
			"versionNonce": 429189693,
			"isDeleted": false,
			"id": "Ghh1UMcu4am0fPRdPU8bS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2844.0069322209065,
			"y": -3680.621955976733,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 147197495,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 317,
			"versionNonce": 640918547,
			"isDeleted": false,
			"id": "weLHLdQFTubmwIaPTmN6H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2865.7307941654044,
			"y": -3657.0080296217816,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 930426711,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 376,
			"versionNonce": 1129749149,
			"isDeleted": false,
			"id": "sKAZtcgryjXajeLd6KPDR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2833.015264604017,
			"y": -3668.5284613439967,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 1105407095,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 478,
			"versionNonce": 921414067,
			"isDeleted": false,
			"id": "OOuuPg5yuRz_wG7PBPotC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2827.2968968600517,
			"y": -3663.5751628615303,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 64259479,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 643,
			"versionNonce": 1044594429,
			"isDeleted": false,
			"id": "tIwVW8NynRjcj7kQi-MkA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2846.9727875592553,
			"y": -3662.103733876817,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 1820179127,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061095,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 432,
			"versionNonce": 701627219,
			"isDeleted": false,
			"id": "qg89LTAB6V9ubB5AlZ0l7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2850.2790386436463,
			"y": -3652.3203858837046,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 277040087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 407,
			"versionNonce": 282875741,
			"isDeleted": false,
			"id": "E1HVkiVjrFxE1KIpW7dVM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2831.474293786712,
			"y": -3653.7792248035025,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 2079963383,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 780,
			"versionNonce": 993859827,
			"isDeleted": false,
			"id": "WpSBkQ0QgLnzWYe61if2U",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2827.3687150978158,
			"y": -3656.7034256323136,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 1147503127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 1970496445,
			"isDeleted": false,
			"id": "2lh3f3d_qK0_wnVkzntGV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2841.7327166814302,
			"y": -3635.780331450597,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 1522214711,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 606,
			"versionNonce": 1488159379,
			"isDeleted": false,
			"id": "OfZgIM-4hpZgbTgnK2tx6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2838.564760461034,
			"y": -3636.330132580752,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 492775511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 767,
			"versionNonce": 1613358109,
			"isDeleted": false,
			"id": "7Um8mZ_N7kdqmlOFWlHC4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2838.4067912158616,
			"y": -3636.412516416595,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 707134839,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 460,
			"versionNonce": 2062268467,
			"isDeleted": false,
			"id": "HlQMJD65mT2lCF7pOy1If",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2837.215597247893,
			"y": -3633.299778219293,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 1884569239,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 680,
			"versionNonce": 1156667517,
			"isDeleted": false,
			"id": "ZlVIdmitIUBYOVuiXvtYR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2836.4660438038272,
			"y": -3631.6912984693176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 43930551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 514,
			"versionNonce": 1070348755,
			"isDeleted": false,
			"id": "AtUKVMCbicYN2XZl_115Z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2839.3325138589807,
			"y": -3625.6281863179233,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 690537687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 437,
			"versionNonce": 495665373,
			"isDeleted": false,
			"id": "f7yMgCGUt7dqhBujtVLBz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2837.3129390155636,
			"y": -3626.7000767254563,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 864555511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 670,
			"versionNonce": 1147897715,
			"isDeleted": false,
			"id": "jvyALuQ6lMDzyaiS1UIha",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2835.538087971362,
			"y": -3630.194231695112,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 180402967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 457,
			"versionNonce": 797515069,
			"isDeleted": false,
			"id": "F9NUJMnCNLTX414iNHhFt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2834.6815452821183,
			"y": -3625.4284824942356,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.883572756258038,
			"height": 5.0743499232385645,
			"seed": 55001143,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 513,
			"versionNonce": 1058021651,
			"isDeleted": false,
			"id": "pIsRsEWoXQO-0tDB1qcgH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2844.7125632042835,
			"y": -3635.427856014901,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 1862279511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 696,
			"versionNonce": 306998685,
			"isDeleted": false,
			"id": "3z3MqjFsQ-Kyy9vtaCZoh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2848.9551752652087,
			"y": -3630.262740640052,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 1866456695,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 411,
			"versionNonce": 1496352435,
			"isDeleted": false,
			"id": "gdfCtTFYoYVFT9nfRPg3a",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2847.423476621975,
			"y": -3629.3877956941747,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 113964951,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 357,
			"versionNonce": 1963373053,
			"isDeleted": false,
			"id": "5Yeh5lkkM8isj1M-E4pWK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2850.1338482141227,
			"y": -3630.242174460414,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 1809181879,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1392,
			"versionNonce": 1232287827,
			"isDeleted": false,
			"id": "QaUtWOE6gkWypwo3dw3oK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2849.001306334062,
			"y": -3630.300531390439,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 436551127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 407,
			"versionNonce": 616131165,
			"isDeleted": false,
			"id": "8WkLcss5kNdLUWEvhdQqj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2846.8726550888523,
			"y": -3634.163517706966,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 611150583,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 613,
			"versionNonce": 766424563,
			"isDeleted": false,
			"id": "C7r_jJTWTAsO3emBtyJim",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2848.0652868973657,
			"y": -3635.0406341715557,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 1200813079,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 484,
			"versionNonce": 1379276477,
			"isDeleted": false,
			"id": "tY0d-XHx7LoPUh3Qer1Ae",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2851.6845824325455,
			"y": -3634.235358081571,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 996825399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 401,
			"versionNonce": 619282323,
			"isDeleted": false,
			"id": "iMBNeJ6ur79e1tXNPN32R",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2855.1662142227888,
			"y": -3633.8632419970277,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 1163401815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061095,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 509,
			"versionNonce": 404633373,
			"isDeleted": false,
			"id": "u4RvbYTbN2gtYxAjE_myZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2862.6350495246515,
			"y": -3633.739171326742,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 170964855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1282,
			"versionNonce": 693769523,
			"isDeleted": false,
			"id": "No2IyyjPHiT3ziCr---bu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2837.9932845446956,
			"y": -3636.595621040415,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 540586135,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 434,
			"versionNonce": 1088637821,
			"isDeleted": false,
			"id": "3T2zDODeNHg_nN55a3Ll7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2829.038332774002,
			"y": -3634.852478730702,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 1629783479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 433,
			"versionNonce": 711390931,
			"isDeleted": false,
			"id": "3782LcXlSoshthzCzezWQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2830.7614595347495,
			"y": -3633.9538808076663,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 2081994455,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 435,
			"versionNonce": 1288098781,
			"isDeleted": false,
			"id": "wwXlPxLYTcfyYb_RSIM_-",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2827.9303424904365,
			"y": -3636.2901107820685,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 1202308087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 423,
			"versionNonce": 1722197107,
			"isDeleted": false,
			"id": "KMe1xNAcpPNnc2DNsX9EE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2829.453148241615,
			"y": -3638.059918190102,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 1406938391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 391,
			"versionNonce": 937054269,
			"isDeleted": false,
			"id": "dSo336iY8HHoc47VkvqiZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2825.552612426999,
			"y": -3639.7297120709877,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 1009021495,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 337,
			"versionNonce": 98541075,
			"isDeleted": false,
			"id": "clHes5Hzhd34n0s_oX0VL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2823.850141261366,
			"y": -3639.7395089150646,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 963056471,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 361,
			"versionNonce": 2147434653,
			"isDeleted": false,
			"id": "TQ18SZAlDLao4753j1SYe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2845.8342436836238,
			"y": -3637.126510283592,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 1945669751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 867,
			"versionNonce": 1929929651,
			"isDeleted": false,
			"id": "Z7hou204GAhS4wUnv2zL2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2834.1234298982617,
			"y": -3623.6875290519733,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 362637719,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 792,
			"versionNonce": 1793533181,
			"isDeleted": false,
			"id": "NSUHgV95mgtmnXvaxFaI6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2826.883918796948,
			"y": -3621.184648318446,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 462036663,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 663,
			"versionNonce": 1984394579,
			"isDeleted": false,
			"id": "sLUZgqHcjO0w7REV2xN1g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2829.1225474555813,
			"y": -3661.754322812428,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1751330775,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 732,
			"versionNonce": 202603869,
			"isDeleted": false,
			"id": "QYvCkLuXJCEPzl3-DQ_5a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2833.9561588532624,
			"y": -3659.1881269776827,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 373103863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 730,
			"versionNonce": 250827507,
			"isDeleted": false,
			"id": "mVrCMP2_2sjdXUh1jyAX9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2849.677050437359,
			"y": -3660.3829017515823,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 144467479,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 768,
			"versionNonce": 181782973,
			"isDeleted": false,
			"id": "rMwujYGoCPq50Q2x-HvQk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2854.5569872987007,
			"y": -3657.333992947188,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 1047890743,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3971,
			"versionNonce": 227703955,
			"isDeleted": false,
			"id": "YZ2p1Q1sVZFlk08jIH31w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.086603288906,
			"y": -3677.247098162692,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 1581950583,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 310,
			"versionNonce": 676301341,
			"isDeleted": false,
			"id": "JoMV-mx6viJWjHFx23u9g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2929.37605804114,
			"y": -3696.566953130554,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 1497153431,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 319,
			"versionNonce": 1843098163,
			"isDeleted": false,
			"id": "NznVYId5Ul6EHar9ZcRpt",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2934.7802790282312,
			"y": -3696.118956490247,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 483308727,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 396,
			"versionNonce": 91373181,
			"isDeleted": false,
			"id": "c-C95OuQWgqmrvHit00Iv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2929.2934816818597,
			"y": -3695.9775004776093,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 1084556759,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 448,
			"versionNonce": 1890890707,
			"isDeleted": false,
			"id": "S3rup_6xfkL8FzRAfyMOs",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.9805447417048,
			"y": -3691.7424126230653,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 1943286519,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 397,
			"versionNonce": 687826653,
			"isDeleted": false,
			"id": "SKelhfRrYdsnL66hEfGgT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2935.4305011858987,
			"y": -3688.802666359021,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 249609239,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 375,
			"versionNonce": 1983168883,
			"isDeleted": false,
			"id": "Bgg1Y0oSO8t97asrZRiFf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2950.592714849391,
			"y": -3687.6291012056845,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 1707024695,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 426,
			"versionNonce": 1166574397,
			"isDeleted": false,
			"id": "NkLr2Lri1tSfVKsUcLyHU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2955.1408880886374,
			"y": -3694.2533072686456,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 1507058263,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 355,
			"versionNonce": 396499731,
			"isDeleted": false,
			"id": "TOqJ7i-NNV1ay9zB4IXtV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2932.717885441716,
			"y": -3685.349969834575,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 737378167,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 384,
			"versionNonce": 1064244125,
			"isDeleted": false,
			"id": "V_4kaxsl_cxCuThu9siRP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2924.384306095246,
			"y": -3694.564481615409,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 241334423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 511,
			"versionNonce": 24330419,
			"isDeleted": false,
			"id": "OC4inzD9uInhIgnLwbRW5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2935.238583137503,
			"y": -3705.9626953271254,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 1993690551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 465,
			"versionNonce": 1927583741,
			"isDeleted": false,
			"id": "PQ5zgC_-d_ksSiYRtMZuP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2956.5526670083545,
			"y": -3709.5767315092744,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 812678871,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 842,
			"versionNonce": 223261267,
			"isDeleted": false,
			"id": "dT1iyjlcA6PzRjsq9XlJy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2956.802193890757,
			"y": -3716.540815989123,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 768117751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 376,
			"versionNonce": 971673693,
			"isDeleted": false,
			"id": "jOYsCFkx4qOH6et6pJOWr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2951.194668813283,
			"y": -3717.1932236566736,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 451015959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 372,
			"versionNonce": 470478835,
			"isDeleted": false,
			"id": "7XYhk8uO3IVKpCj7Eqp1d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.1387307921414,
			"y": -3714.0524936446636,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 791755319,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 361,
			"versionNonce": 844266685,
			"isDeleted": false,
			"id": "k-TYyFcvvsfkYwwzQ8ULG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2932.052515786514,
			"y": -3719.8778695869714,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 1067113303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 318,
			"versionNonce": 799963539,
			"isDeleted": false,
			"id": "iEVhXC2BQPk2vqAObcOy-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2931.941863680482,
			"y": -3714.6902948734996,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 275994743,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 1136516381,
			"isDeleted": false,
			"id": "hxk_cJ6yWwHV1hTJTL6Zt",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2927.9694994014553,
			"y": -3717.0173840959287,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 1736389015,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 345,
			"versionNonce": 1164955443,
			"isDeleted": false,
			"id": "asAjX9-yX8OvYPsByFz7i",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2921.8448103787614,
			"y": -3718.1543009775123,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 1576199863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 494,
			"versionNonce": 1704866173,
			"isDeleted": false,
			"id": "d_fTVzRaBikt2Sm_sA417",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2935.09262130752,
			"y": -3722.891817726716,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 1920137175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 324,
			"versionNonce": 1874161875,
			"isDeleted": false,
			"id": "Wkg_pmGCsJ15VfVWUnRYv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2956.816483252018,
			"y": -3699.277891371765,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 1528030455,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 383,
			"versionNonce": 624228829,
			"isDeleted": false,
			"id": "hF4UwRzRc6Y5DzbUA17gK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2924.1009536906313,
			"y": -3710.798323093981,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 391786007,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 485,
			"versionNonce": 806739571,
			"isDeleted": false,
			"id": "k0QAQptr8AOF2bSXKGLn_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2918.382585946667,
			"y": -3705.8450246115135,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 1111118647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 650,
			"versionNonce": 1804842557,
			"isDeleted": false,
			"id": "Bh4S8pgxGRuEeg2lQ85IT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2938.0584766458687,
			"y": -3704.373595626799,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 605606999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061096,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 439,
			"versionNonce": 290953235,
			"isDeleted": false,
			"id": "TUhZBlXGgtZoseZwUf4YY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2941.3647277302607,
			"y": -3694.590247633688,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 80359799,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 414,
			"versionNonce": 60548765,
			"isDeleted": false,
			"id": "aDoXzd0j77U5vYLHHd6op",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2922.5599828733266,
			"y": -3696.0490865534857,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 1033038487,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 787,
			"versionNonce": 24190387,
			"isDeleted": false,
			"id": "oFPcJXpdjRgUeG8RXlKM1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2918.45440418443,
			"y": -3698.9732873822977,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 187137975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 458,
			"versionNonce": 1610550013,
			"isDeleted": false,
			"id": "UywHsZhVHtS6ZxrxlfHuW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2932.8184057680446,
			"y": -3678.050193200581,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 531394775,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 613,
			"versionNonce": 1804136275,
			"isDeleted": false,
			"id": "cXlMO681-PCZ9FCzkYlkN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2929.6504495476493,
			"y": -3678.599994330735,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 1958100471,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 774,
			"versionNonce": 557753181,
			"isDeleted": false,
			"id": "iN02BPryOEYpPPForgoZ_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2929.492480302475,
			"y": -3678.682378166577,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 1565091607,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 467,
			"versionNonce": 301305075,
			"isDeleted": false,
			"id": "qh5pRgfnvztJrvDjcmDYK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2928.3012863345084,
			"y": -3675.569639969276,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 1473932343,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 687,
			"versionNonce": 1538011069,
			"isDeleted": false,
			"id": "o9b2hH5nn0q13pJaIiLtd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2927.5517328904425,
			"y": -3673.961160219301,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 541969751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 675116691,
			"isDeleted": false,
			"id": "pBi_xz8ZN_HT7RuEj4gkz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2930.418202945595,
			"y": -3667.8980480679056,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 33032823,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 444,
			"versionNonce": 493432861,
			"isDeleted": false,
			"id": "2xweZ0MO8dj_3MHXv8-xc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2928.398628102178,
			"y": -3668.9699384754404,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 1771938711,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 677,
			"versionNonce": 756493363,
			"isDeleted": false,
			"id": "IJfKOagxKMv916IFV0_4q",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2926.6237770579755,
			"y": -3672.4640934450945,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 930289847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 464,
			"versionNonce": 879174781,
			"isDeleted": false,
			"id": "lbKh5EFSQf5EBhLpOBXOf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 2925.7672343687327,
			"y": -3667.698344244218,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.883572756258038,
			"height": 5.0743499232385645,
			"seed": 1360849367,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 520,
			"versionNonce": 74001875,
			"isDeleted": false,
			"id": "bRxpfdUgENz8eNAD5B5c6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2935.7982522908987,
			"y": -3677.697717764884,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 1940887287,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 703,
			"versionNonce": 879201501,
			"isDeleted": false,
			"id": "CwMIzZkNy5wMd3865PJXy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.040864351824,
			"y": -3672.532602390036,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 1169137687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 418,
			"versionNonce": 1363802995,
			"isDeleted": false,
			"id": "k1HnkIy9B9d4KcFtI_Tkf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2938.5091657085886,
			"y": -3671.657657444158,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 689014071,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 364,
			"versionNonce": 1023142205,
			"isDeleted": false,
			"id": "Gh0JUvgVYQkX9nhthHY4b",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2941.219537300738,
			"y": -3672.512036210397,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 1295631959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1399,
			"versionNonce": 268440851,
			"isDeleted": false,
			"id": "q47mUpygsPj-2E_F1krUC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.0869954206773,
			"y": -3672.5703931404223,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 16573303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 414,
			"versionNonce": 2139470237,
			"isDeleted": false,
			"id": "n5VL93S2w1IpgWy0-E4ct",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2937.9583441754676,
			"y": -3676.43337945695,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 1151294615,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 620,
			"versionNonce": 1879177907,
			"isDeleted": false,
			"id": "q-gWJUcC_J5r4VIpEOZw9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2939.150975983979,
			"y": -3677.310495921539,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 466989495,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 491,
			"versionNonce": 87457277,
			"isDeleted": false,
			"id": "bekIT89qY209VGsMXAkBy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2942.770271519159,
			"y": -3676.505219831555,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 532964055,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 408,
			"versionNonce": 1844849747,
			"isDeleted": false,
			"id": "pzKf_6c3HhEgGsSIzzizI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2946.251903309403,
			"y": -3676.133103747011,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 1358950391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 516,
			"versionNonce": 890222173,
			"isDeleted": false,
			"id": "MLEzmgKj9DOKXywLKMgrG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2953.720738611266,
			"y": -3676.0090330767252,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 697096471,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1289,
			"versionNonce": 766716403,
			"isDeleted": false,
			"id": "boe3yEsAf8-LizUI-q1Kk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2929.07897363131,
			"y": -3678.8654827903983,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 1860148791,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 441,
			"versionNonce": 434299581,
			"isDeleted": false,
			"id": "p56EVuUhahsUw6eSeibPt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2920.1240218606163,
			"y": -3677.122340480685,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 1138540375,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 440,
			"versionNonce": 339702675,
			"isDeleted": false,
			"id": "snu_5d3EcyihxWY8gpuX5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2921.847148621364,
			"y": -3676.2237425576495,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 2061024375,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 442,
			"versionNonce": 1750172445,
			"isDeleted": false,
			"id": "DOsBdwQwFLL0CCzJVWAGX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2919.016031577051,
			"y": -3678.5599725320517,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 664278423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 430,
			"versionNonce": 567380275,
			"isDeleted": false,
			"id": "b71jehaNoKht3tzZiIOHh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2920.5388373282294,
			"y": -3680.3297799400852,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 1901021879,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061096,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 398,
			"versionNonce": 1154291581,
			"isDeleted": false,
			"id": "TH1xhOY4WWlIAvEep2t4X",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2916.6383015136125,
			"y": -3681.999573820971,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 614652887,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 344,
			"versionNonce": 198175443,
			"isDeleted": false,
			"id": "UYITKi2csgLU27KEMZujC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2914.9358303479803,
			"y": -3682.0093706650478,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 94849271,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 368,
			"versionNonce": 1234640861,
			"isDeleted": false,
			"id": "75Rd2If6X9n2UByFhr7Z_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2936.919932770239,
			"y": -3679.396372033576,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 1642140183,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 874,
			"versionNonce": 382802035,
			"isDeleted": false,
			"id": "vbWyFkg0W_lfRbD55CYDY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2925.209118984876,
			"y": -3665.9573908019574,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 1648670519,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 799,
			"versionNonce": 1287724093,
			"isDeleted": false,
			"id": "kksPdVTdTaiX6nXQuQDjL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 2917.9696078835623,
			"y": -3663.454510068429,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 490125399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 670,
			"versionNonce": 815501843,
			"isDeleted": false,
			"id": "H59OMqOvQ6NwrL8DCpmo8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2920.2082365421957,
			"y": -3704.0241845624114,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1753978231,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 739,
			"versionNonce": 1714195613,
			"isDeleted": false,
			"id": "-1Q2uHJdlxWvFp6g_qDfT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2925.0418479398777,
			"y": -3701.457988727665,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 1804062359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 737,
			"versionNonce": 1243994035,
			"isDeleted": false,
			"id": "Xe_yGEVbH_U-TQds3r_Xi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.7627395239724,
			"y": -3702.6527635015646,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1893721015,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 775,
			"versionNonce": 898298109,
			"isDeleted": false,
			"id": "J-dL3EZ8cSpM61Rh6Gbc2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2945.642676385314,
			"y": -3699.6038546971704,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 2025346263,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3971,
			"versionNonce": 1905682771,
			"isDeleted": false,
			"id": "4X6E7qyPeL2SojMX3ILV_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3037.5628384590004,
			"y": -3631.1776821590133,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 429746199,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 310,
			"versionNonce": 1750976861,
			"isDeleted": false,
			"id": "2C_8-pf62kvKnwRl75Pz4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3026.852293211235,
			"y": -3650.4975371268742,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 1275481399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 319,
			"versionNonce": 742639347,
			"isDeleted": false,
			"id": "y0TSanwpiDdpIIvtstIbO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3032.2565141983264,
			"y": -3650.0495404865683,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 1180012119,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 396,
			"versionNonce": 2146866621,
			"isDeleted": false,
			"id": "uNUFRvAbDpLLH1bb8w4IR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3026.7697168519558,
			"y": -3649.9080844739306,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 1935649655,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 448,
			"versionNonce": 280260755,
			"isDeleted": false,
			"id": "1Vp9dbNk9ZoefYwMD9aur",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3038.4567799118,
			"y": -3645.6729966193866,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 1869161623,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 397,
			"versionNonce": 1467405853,
			"isDeleted": false,
			"id": "2COjMjqTkwJtxbv2rzqzj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3032.906736355994,
			"y": -3642.7332503553403,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 1512470967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 375,
			"versionNonce": 547284531,
			"isDeleted": false,
			"id": "d9TS4ETEVIUrAiEuo7rii",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3048.0689500194862,
			"y": -3641.559685202005,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 1757162199,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 426,
			"versionNonce": 1775241853,
			"isDeleted": false,
			"id": "-oSre7ujVL7kRevYDLztd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3052.6171232587326,
			"y": -3648.183891264966,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 935245815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 355,
			"versionNonce": 1659480019,
			"isDeleted": false,
			"id": "XLJaKlaBIcq2HlFZYkJsl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3030.194120611812,
			"y": -3639.2805538308953,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 1563599127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 384,
			"versionNonce": 1472443101,
			"isDeleted": false,
			"id": "ZydJlRa7lCWAuLyAQQ6o8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3021.860541265342,
			"y": -3648.4950656117285,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 982279735,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 511,
			"versionNonce": 1034630515,
			"isDeleted": false,
			"id": "022w_2Rqxa4POnRjyFibk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3032.714818307599,
			"y": -3659.893279323445,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 246450007,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 465,
			"versionNonce": 769871677,
			"isDeleted": false,
			"id": "E77o0_-TSomw0E1jmBxqi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3054.0289021784497,
			"y": -3663.5073155055948,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 1207141495,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 842,
			"versionNonce": 271191827,
			"isDeleted": false,
			"id": "efZ7oXc0KKTZnYVxvx_9e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3054.278429060853,
			"y": -3670.4713999854434,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 370793879,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 376,
			"versionNonce": 1787846557,
			"isDeleted": false,
			"id": "_Udl9IsEWGHP56f0lkA_p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3048.670903983379,
			"y": -3671.123807652993,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 1012404919,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 372,
			"versionNonce": 215790771,
			"isDeleted": false,
			"id": "NAoo42fj47KblKt8M74a0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3037.6149659622356,
			"y": -3667.983077640984,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 592618455,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 361,
			"versionNonce": 1140614141,
			"isDeleted": false,
			"id": "IuP6aBMroiC0GggH3e4W4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3029.52875095661,
			"y": -3673.808453583292,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 723390711,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 318,
			"versionNonce": 1399432787,
			"isDeleted": false,
			"id": "QLrmrkLsvgr0A0V80PUJq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3029.4180988505773,
			"y": -3668.62087886982,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 1027529239,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 774429789,
			"isDeleted": false,
			"id": "_9GerPmZY_3VDQerRH4Vf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3025.4457345715514,
			"y": -3670.947968092248,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 514424631,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 345,
			"versionNonce": 1252484083,
			"isDeleted": false,
			"id": "c6i_JPk88S4rcLxyRofc7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3019.3210455488565,
			"y": -3672.0848849738336,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 29524055,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 494,
			"versionNonce": 552028349,
			"isDeleted": false,
			"id": "f9iFnk9UGLRHcvGoYTksn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3032.568856477616,
			"y": -3676.8224017230364,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 1482579319,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 324,
			"versionNonce": 983330195,
			"isDeleted": false,
			"id": "Jriduau_xtFbRNRun_zkv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3054.292718422114,
			"y": -3653.208475368085,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 1707185815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 383,
			"versionNonce": 500771101,
			"isDeleted": false,
			"id": "LiWeZ39hUSXUPKag1kDv9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3021.5771888607264,
			"y": -3664.7289070903003,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 278965175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 485,
			"versionNonce": 645874483,
			"isDeleted": false,
			"id": "l6A49ezY4i23dpotM9A5T",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3015.858821116761,
			"y": -3659.775608607834,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 1965038807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 650,
			"versionNonce": 1987050877,
			"isDeleted": false,
			"id": "uqcZ3Qa4_qDwmSFCBogez",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3035.534711815965,
			"y": -3658.3041796231205,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 919890423,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 439,
			"versionNonce": 1723229395,
			"isDeleted": false,
			"id": "bGjbQZojzob89CJdcInE-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3038.840962900356,
			"y": -3648.520831630008,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 314708759,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 414,
			"versionNonce": 1374504413,
			"isDeleted": false,
			"id": "shnYcAS6NZ1D-xIc6y-K_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3020.0362180434217,
			"y": -3649.979670549806,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 828217399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 787,
			"versionNonce": 47731315,
			"isDeleted": false,
			"id": "whGXApwv8ZNWMQcW7KyFl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3015.9306393545253,
			"y": -3652.903871378617,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 948664663,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 458,
			"versionNonce": 1935835709,
			"isDeleted": false,
			"id": "_T1iLYP-gLQux6liXcbn8",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3030.2946409381398,
			"y": -3631.9807771969004,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 497038967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 613,
			"versionNonce": 1269533715,
			"isDeleted": false,
			"id": "itt9A6dTKGDMZNxzrz8ga",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3027.1266847177435,
			"y": -3632.5305783270555,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 929058711,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 774,
			"versionNonce": 1068577437,
			"isDeleted": false,
			"id": "i5_9hSyxEZ1Xn-BBl-HAY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3026.968715472571,
			"y": -3632.6129621628984,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 268453047,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 467,
			"versionNonce": 891720115,
			"isDeleted": false,
			"id": "l8698RefBFoHi7bzeu2Mp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3025.7775215046026,
			"y": -3629.5002239655964,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 1998886359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 687,
			"versionNonce": 59430653,
			"isDeleted": false,
			"id": "mLNqsRTuydp-HZnW3IyGB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3025.0279680605368,
			"y": -3627.891744215621,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 1407304439,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 1886380883,
			"isDeleted": false,
			"id": "htB-SSNViE0-gKmKU_bWg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3027.8944381156903,
			"y": -3621.828632064227,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 918309911,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 444,
			"versionNonce": 2037444445,
			"isDeleted": false,
			"id": "eAn1d85PoMRpvs5ie5fMR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3025.874863272273,
			"y": -3622.90052247176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 732475703,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 677,
			"versionNonce": 1172177139,
			"isDeleted": false,
			"id": "kFM1DRIlM7FA3oZ9BILl1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3024.1000122280716,
			"y": -3626.3946774414158,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 1275818583,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 464,
			"versionNonce": 263519165,
			"isDeleted": false,
			"id": "YpkJ3rW2eVq-Pclf7STqz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3023.243469538828,
			"y": -3621.628928240539,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.883572756258038,
			"height": 5.0743499232385645,
			"seed": 280563575,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 520,
			"versionNonce": 787966611,
			"isDeleted": false,
			"id": "VRZqUhHctkdxI-Xxw3sKf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3033.274487460993,
			"y": -3631.6283017612045,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 1677068439,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 703,
			"versionNonce": 1853389853,
			"isDeleted": false,
			"id": "hHnIWZ3760OzHEKWh-Q6F",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3037.517099521918,
			"y": -3626.4631863863556,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 1937169847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 418,
			"versionNonce": 812818483,
			"isDeleted": false,
			"id": "5Nw-pSyvbnvwLuZWNFuM9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3035.9854008786847,
			"y": -3625.588241440478,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 1113591511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 364,
			"versionNonce": 1034743933,
			"isDeleted": false,
			"id": "Sdp9y34Eto-ou_oRPJIAf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3038.6957724708323,
			"y": -3626.4426202067175,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 2068192247,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1399,
			"versionNonce": 1949704659,
			"isDeleted": false,
			"id": "qjBoGabzWo9U8Nr_2875K",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3037.5632305907716,
			"y": -3626.5009771367427,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 36537623,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 414,
			"versionNonce": 722720989,
			"isDeleted": false,
			"id": "H8qJhaRKBwtuL80nXQFT4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3035.434579345562,
			"y": -3630.3639634532697,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 1183500855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 620,
			"versionNonce": 592998259,
			"isDeleted": false,
			"id": "WuCXCPFZLWXqDXf8IU1sh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3036.627211154075,
			"y": -3631.241079917859,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 1430416215,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 491,
			"versionNonce": 809415997,
			"isDeleted": false,
			"id": "D89vIcjllQ79mQxwifFF2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3040.246506689255,
			"y": -3630.4358038278747,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 715712631,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 408,
			"versionNonce": 2099475,
			"isDeleted": false,
			"id": "uQaNcWF6AxIHtgjZ9gjON",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3043.7281384794983,
			"y": -3630.0636877433312,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 1149419927,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 516,
			"versionNonce": 412026269,
			"isDeleted": false,
			"id": "BAd79vKB2N3IgEQBGNhpM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3051.196973781361,
			"y": -3629.9396170730456,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 1946449591,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1289,
			"versionNonce": 1073966771,
			"isDeleted": false,
			"id": "LJa1dm_pydkjS9--cpH4A",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3026.555208801405,
			"y": -3632.7960667867187,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 1876068311,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 441,
			"versionNonce": 1194740221,
			"isDeleted": false,
			"id": "g3liw0OnybqtABnLn7oAU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3017.6002570307114,
			"y": -3631.0529244770055,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 637629687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 440,
			"versionNonce": 631840851,
			"isDeleted": false,
			"id": "S_2b5qtp--Tmqb82dEwKj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3019.323383791459,
			"y": -3630.15432655397,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 1310047767,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 442,
			"versionNonce": 1026949725,
			"isDeleted": false,
			"id": "b82NtU3VhSz-EBHAOabcX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3016.492266747146,
			"y": -3632.490556528372,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 990110519,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 430,
			"versionNonce": 1525128691,
			"isDeleted": false,
			"id": "RvFLSIviJfdnsZqGINU1f",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3018.0150724983246,
			"y": -3634.2603639364056,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 1831887959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 398,
			"versionNonce": 1600106173,
			"isDeleted": false,
			"id": "aNy98qiNM9MJagpJTy7Eh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3014.1145366837086,
			"y": -3635.9301578172913,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 1685045623,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 344,
			"versionNonce": 180709267,
			"isDeleted": false,
			"id": "8GnPIihRtpxf_blUg07dP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3012.4120655180755,
			"y": -3635.939954661368,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 839285399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 368,
			"versionNonce": 2085932829,
			"isDeleted": false,
			"id": "sOU1qU_k3WmLbmXFLWk9X",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3034.3961679403333,
			"y": -3633.3269560298954,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 1252593591,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 874,
			"versionNonce": 997784883,
			"isDeleted": false,
			"id": "ISiPSBLNomhcUXWBkRO8V",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 3022.6853541549713,
			"y": -3619.887974798277,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 410779863,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 799,
			"versionNonce": 310829949,
			"isDeleted": false,
			"id": "ct3g1L8VJ3hLD-OVbs3NB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 3015.4458430536574,
			"y": -3617.3850940647494,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 1293143543,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 670,
			"versionNonce": 1751703251,
			"isDeleted": false,
			"id": "1N6zYjCRAyXqk-U9BQ9rj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3017.684471712291,
			"y": -3657.9547685587318,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1937045271,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 739,
			"versionNonce": 1446472669,
			"isDeleted": false,
			"id": "NRL1wVOAb1nXfOc7zy7gd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3022.518083109972,
			"y": -3655.3885727239863,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 1108606007,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 737,
			"versionNonce": 1546357875,
			"isDeleted": false,
			"id": "XMjKRrpP0AoKK7xfIyQms",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3038.2389746940685,
			"y": -3656.583347497886,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 752180567,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 775,
			"versionNonce": 2004346941,
			"isDeleted": false,
			"id": "gSsiSBW1N_wfsTi16k-iI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3043.1189115554103,
			"y": -3653.5344386934917,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 923638391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3954,
			"versionNonce": 1250395667,
			"isDeleted": false,
			"id": "YbV2nymW5Ep943Z69fTSs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3135.1808551970826,
			"y": -3672.2318843581415,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 884819511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 673831069,
			"isDeleted": false,
			"id": "9s_0l3RzRJ7xeClDpmQlX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3124.4703099493163,
			"y": -3691.5517393260025,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 1338337111,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 712199091,
			"isDeleted": false,
			"id": "QxA1v19QxmcVXkPSoaCrh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3129.8745309364076,
			"y": -3691.1037426856965,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 1399612535,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 379,
			"versionNonce": 1644084477,
			"isDeleted": false,
			"id": "oyXLqGGLin0u_iEv6w8Qy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3124.387733590036,
			"y": -3690.9622866730588,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 2138488215,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 431,
			"versionNonce": 1343577427,
			"isDeleted": false,
			"id": "wiP2LhcVNDKspUlPuk7Yy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3136.074796649881,
			"y": -3686.727198818515,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 655946423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 380,
			"versionNonce": 1819809117,
			"isDeleted": false,
			"id": "iK09H6Fuz0Xeoo1hB38EV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3130.524753094075,
			"y": -3683.7874525544685,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 1123517399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 358,
			"versionNonce": 1187265267,
			"isDeleted": false,
			"id": "RNh3FEfxWgxgsLLNCeYSq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3145.6869667575675,
			"y": -3682.613887401133,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 1126625527,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 409,
			"versionNonce": 585589181,
			"isDeleted": false,
			"id": "cNMaCSv68PC3jLWdTe0U3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3150.235139996814,
			"y": -3689.238093464094,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 556513815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 338,
			"versionNonce": 1795581075,
			"isDeleted": false,
			"id": "MwbpYYOxwcuVpoGmMHAtG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3127.8121373498925,
			"y": -3680.3347560300235,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 838491959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 367,
			"versionNonce": 2054038045,
			"isDeleted": false,
			"id": "xRviynxOCDQo8nwDwVsRk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3119.478558003422,
			"y": -3689.5492678108567,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 938958935,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 494,
			"versionNonce": 1150442035,
			"isDeleted": false,
			"id": "3gsQe025zjW-_lCr1aSUw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3130.3328350456795,
			"y": -3700.947481522573,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 888618359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 448,
			"versionNonce": 1207817853,
			"isDeleted": false,
			"id": "Xh1oamRq9tarso_sgPGkG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3151.646918916531,
			"y": -3704.561517704723,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 2084468375,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 825,
			"versionNonce": 542022611,
			"isDeleted": false,
			"id": "MLIUxiihq_E5kR_SjHnpe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3151.896445798933,
			"y": -3711.5256021845717,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 75598775,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 359,
			"versionNonce": 1180171997,
			"isDeleted": false,
			"id": "GomJZqZQlQZHKJENqJMo7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3146.2889207214594,
			"y": -3712.1780098521212,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 2045050071,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 355,
			"versionNonce": 1783736691,
			"isDeleted": false,
			"id": "zBtwoezw4Q65bzMXeQXnl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3135.2329827003177,
			"y": -3709.037279840112,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 268257783,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061097,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 344,
			"versionNonce": 1544428349,
			"isDeleted": false,
			"id": "KuSef9plev_DRIo4aDw_q",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3127.1467676946904,
			"y": -3714.86265578242,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 332329751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 301,
			"versionNonce": 1205994259,
			"isDeleted": false,
			"id": "tMKF0l7MuytWeJuedsfOf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3127.0361155886585,
			"y": -3709.675081068948,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 1036941367,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 337,
			"versionNonce": 562146205,
			"isDeleted": false,
			"id": "gZlYChQTRF2kx7Ui1HfB5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3123.0637513096317,
			"y": -3712.0021702913764,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 1138776407,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 328,
			"versionNonce": 1903569075,
			"isDeleted": false,
			"id": "RPCR5AxJr4RhLZmTJWd4I",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3116.9390622869378,
			"y": -3713.139087172962,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 727258743,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 652488701,
			"isDeleted": false,
			"id": "IebCWtwIpqtp_dAtFGF9e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3130.1868732156963,
			"y": -3717.8766039221646,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 1526542231,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 307,
			"versionNonce": 1286904403,
			"isDeleted": false,
			"id": "LTHNAYgQl6mMpRrqpCeN1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3151.9107351601942,
			"y": -3694.2626775672134,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 1828791479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 366,
			"versionNonce": 2050435165,
			"isDeleted": false,
			"id": "5GXS1A1obVv7PkCsSzKqK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3119.1952055988077,
			"y": -3705.7831092894285,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 1091139031,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 468,
			"versionNonce": 1181997043,
			"isDeleted": false,
			"id": "HGNHnVZz_uII2491I8qNR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3113.4768378548433,
			"y": -3700.829810806962,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 1311417079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 633,
			"versionNonce": 1833702589,
			"isDeleted": false,
			"id": "XHHfTNfqB9Fq_isulZWDA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3133.152728554045,
			"y": -3699.3583818222487,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 887696407,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 422,
			"versionNonce": 1824154003,
			"isDeleted": false,
			"id": "x4gtfsybJKZN9ApA4Lf4P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3136.458979638437,
			"y": -3689.5750338291364,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 288985399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 397,
			"versionNonce": 465859869,
			"isDeleted": false,
			"id": "l8R977IqDyVVv-0KFeUxx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3117.654234781503,
			"y": -3691.0338727489343,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 209736279,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 770,
			"versionNonce": 1220458291,
			"isDeleted": false,
			"id": "4XGRAO1wvcdgUmLjwgwGi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3113.5486560926065,
			"y": -3693.9580735777454,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 798093175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 441,
			"versionNonce": 823249277,
			"isDeleted": false,
			"id": "E6yqs1_8PkXPf27uEXC2b",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3127.912657676221,
			"y": -3673.0349793960286,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 1957882007,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 596,
			"versionNonce": 2028427475,
			"isDeleted": false,
			"id": "jr07UDvYEUVFKheA-6l-f",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3124.7447014558256,
			"y": -3673.5847805261837,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 429374903,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 757,
			"versionNonce": 1853198813,
			"isDeleted": false,
			"id": "Vg7XlO4lrhyRzMqPCubdj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3124.5867322106515,
			"y": -3673.6671643620266,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 828698327,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 450,
			"versionNonce": 181061235,
			"isDeleted": false,
			"id": "UtrVhjWyUBXzbyeDODbQ4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3123.395538242685,
			"y": -3670.5544261647246,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 1991179255,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 670,
			"versionNonce": 1895910973,
			"isDeleted": false,
			"id": "XvoqQCHGq2OlZfH9BjO7s",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3122.645984798619,
			"y": -3668.9459464147494,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 1568302359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 504,
			"versionNonce": 355434515,
			"isDeleted": false,
			"id": "y-vSDC1CQw1d5-IAevIyE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3125.5124548537715,
			"y": -3662.882834263355,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 1698409015,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 427,
			"versionNonce": 932609693,
			"isDeleted": false,
			"id": "GTPvHn4JlluF1bJ6s2o3J",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3123.4928800103544,
			"y": -3663.954724670888,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 718752599,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 660,
			"versionNonce": 302777779,
			"isDeleted": false,
			"id": "eN9JXrISLY9272ef9gaXT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3121.718028966152,
			"y": -3667.448879640544,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 983681143,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 447,
			"versionNonce": 1759945469,
			"isDeleted": false,
			"id": "NhKgoScrAfwi11IPNc4K8",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3120.861486276909,
			"y": -3662.6831304396674,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.883572756258038,
			"height": 5.0743499232385645,
			"seed": 576692631,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 503,
			"versionNonce": 2022102867,
			"isDeleted": false,
			"id": "In1S68uTAUbzi780Tcstn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3130.892504199075,
			"y": -3672.6825039603327,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 1128617655,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 686,
			"versionNonce": 1500724061,
			"isDeleted": false,
			"id": "mTRMSigBl4AB6NT7wXxfM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3135.1351162600004,
			"y": -3667.517388585484,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 1677158359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 401,
			"versionNonce": 385250547,
			"isDeleted": false,
			"id": "oHxptBklqFWPiD3eDdjhd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3133.603417616765,
			"y": -3666.6424436396064,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 42620151,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 347,
			"versionNonce": 1368246205,
			"isDeleted": false,
			"id": "82MEd5XfME279JuaIY0R9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3136.3137892089144,
			"y": -3667.4968224058457,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 1719836183,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1382,
			"versionNonce": 752967315,
			"isDeleted": false,
			"id": "Y4Si_1Ih4cfWZZHzOCZ7k",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3135.1812473288537,
			"y": -3667.555179335871,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 1926546231,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 397,
			"versionNonce": 324519965,
			"isDeleted": false,
			"id": "lLvChXwIDfK-RLhafE4fj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3133.052596083644,
			"y": -3671.418165652398,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 937772119,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 603,
			"versionNonce": 1157502003,
			"isDeleted": false,
			"id": "H8r0tuIc24cLhG1xCE1LP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3134.2452278921555,
			"y": -3672.2952821169874,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 1166582135,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 474,
			"versionNonce": 549633149,
			"isDeleted": false,
			"id": "N1cc8kPbDx6XsZjvWYyzA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3137.8645234273354,
			"y": -3671.490006027003,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 1023629975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 391,
			"versionNonce": 1328747987,
			"isDeleted": false,
			"id": "SIPEd3HeRZZPz0H0afX-d",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3141.3461552175795,
			"y": -3671.1178899424594,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 587853751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 499,
			"versionNonce": 1099965661,
			"isDeleted": false,
			"id": "LRoRe2pyGCN3ZifV7QqLR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3148.8149905194423,
			"y": -3670.993819272174,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 1908465879,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1272,
			"versionNonce": 2056708979,
			"isDeleted": false,
			"id": "o4tGULHljP-zd1sTFJW-i",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3124.1732255394863,
			"y": -3673.850268985847,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 1790750199,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 424,
			"versionNonce": 1230078269,
			"isDeleted": false,
			"id": "6k3uBWUMMWuCnrg3RKkHQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3115.2182737687926,
			"y": -3672.1071266761337,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 687986455,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 423,
			"versionNonce": 1332739347,
			"isDeleted": false,
			"id": "naEqw6ygzhsQHQGUTqst9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3116.9414005295403,
			"y": -3671.208528753098,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 1929698359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 425,
			"versionNonce": 493375901,
			"isDeleted": false,
			"id": "KGGJIz-qDHXD0BQtePiNS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3114.1102834852272,
			"y": -3673.5447587275003,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 1286225239,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 413,
			"versionNonce": 154460851,
			"isDeleted": false,
			"id": "AxerTMz9fLVWOu0feL2bf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3115.633089236406,
			"y": -3675.314566135534,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 1229355639,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 381,
			"versionNonce": 2063996413,
			"isDeleted": false,
			"id": "EDDyJ_xizXZThF5jmUq2S",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3111.732553421789,
			"y": -3676.9843600164195,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 496898967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 327,
			"versionNonce": 814486611,
			"isDeleted": false,
			"id": "9HiUGd0ObXg2dLWWQDVLl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3110.0300822561567,
			"y": -3676.9941568604963,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 1910868151,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 351,
			"versionNonce": 2100055645,
			"isDeleted": false,
			"id": "H4AFQLBkA_YvA-f2vtWfg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3132.0141846784154,
			"y": -3674.3811582290236,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 1942051287,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 857,
			"versionNonce": 1967919603,
			"isDeleted": false,
			"id": "DXFa3It2SSvqmfwaGQjUk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 3120.3033708930525,
			"y": -3660.942176997405,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 675677943,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 782,
			"versionNonce": 1655470781,
			"isDeleted": false,
			"id": "5d4GWztPSQw_gHEXSpbfN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 3113.0638597917387,
			"y": -3658.4392962638776,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 2113409047,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 653,
			"versionNonce": 1216043923,
			"isDeleted": false,
			"id": "3xQqeHyuoCN9WxfCGsh3A",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3115.302488450372,
			"y": -3699.00897075786,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 516683063,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 722,
			"versionNonce": 338172701,
			"isDeleted": false,
			"id": "erT8moSj5UlRovM2Zllso",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3120.136099848054,
			"y": -3696.4427749231145,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 36058711,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 720,
			"versionNonce": 911241523,
			"isDeleted": false,
			"id": "ErEFeQZLZx_-hhV--FJto",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3135.856991432149,
			"y": -3697.637549697014,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1054561143,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 758,
			"versionNonce": 1779478397,
			"isDeleted": false,
			"id": "UIYPWvw8kUHOqWbByCE-7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3140.7369282934906,
			"y": -3694.58864089262,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 489671831,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3957,
			"versionNonce": 3265235,
			"isDeleted": false,
			"id": "UGW9P93gOyYJNNuMuaMr8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3215.582514218825,
			"y": -3632.515402190773,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 44.86694699501087,
			"height": 54.611724177617,
			"seed": 1275288953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					5.33983179977447,
					-1.3891591711727969
				],
				[
					9.382230538285489,
					-3.9509307160601694
				],
				[
					12.901029206508982,
					-6.996789826530689
				],
				[
					14.982036347336006,
					-9.89117215451561
				],
				[
					17.61268298423865,
					-16.299677884993987
				],
				[
					19.75999576229526,
					-25.605660708999164
				],
				[
					21.17822974184298,
					-38.42571668838198
				],
				[
					19.54198951451874,
					-37.22910218102938
				],
				[
					19.566875540603043,
					-39.13832242676485
				],
				[
					20.270803373689724,
					-40.48968320507035
				],
				[
					18.500129271978363,
					-41.74039786843055
				],
				[
					16.82581086671021,
					-39.356907658353066
				],
				[
					15.38481037578139,
					-40.25509312511707
				],
				[
					15.391143796333138,
					-41.17567738573284
				],
				[
					14.785583828281762,
					-44.81758148768835
				],
				[
					13.914020197057281,
					-45.42406189154294
				],
				[
					13.874233617175792,
					-46.54600918480339
				],
				[
					12.631590467782361,
					-46.64907058724723
				],
				[
					11.526946454038685,
					-46.377245110519695
				],
				[
					9.630969749258597,
					-43.337840470470816
				],
				[
					8.483101796120144,
					-42.860894847211966
				],
				[
					7.246794351238255,
					-43.51443395898148
				],
				[
					7.111942512205997,
					-46.18060530676105
				],
				[
					8.119296689944461,
					-47.65680618627387
				],
				[
					6.413023402981549,
					-47.83052188542457
				],
				[
					5.4291757396024645,
					-45.493840289662856
				],
				[
					4.702796581588414,
					-50.60917140194254
				],
				[
					2.67744268943944,
					-51.16645987942013
				],
				[
					2.3242146011415414,
					-49.02714552861639
				],
				[
					1.9016386411478214,
					-51.40977011792608
				],
				[
					0.5010322634098112,
					-51.54375862015034
				],
				[
					-0.28185434425105677,
					-47.98784332106266
				],
				[
					-0.47129967460978545,
					-50.9420996554536
				],
				[
					0.23638755632334393,
					-54.09231745753975
				],
				[
					-1.5030808025108215,
					-54.21267071970131
				],
				[
					-1.670750860045765,
					-53.28238876573441
				],
				[
					-1.8309203935663203,
					-54.551850171210994
				],
				[
					-2.8904950283891577,
					-54.611724177617
				],
				[
					-2.876702195099593,
					-53.82438727426731
				],
				[
					-3.6501332091491543,
					-50.95287309387502
				],
				[
					-4.366211708422357,
					-48.46083540989127
				],
				[
					-5.049638718258973,
					-45.5164549177166
				],
				[
					-4.39027550897524,
					-48.949497746972845
				],
				[
					-5.167315179523803,
					-49.12692259685417
				],
				[
					-6.686504750571002,
					-46.683622331245324
				],
				[
					-6.7766023971361316,
					-44.276728384999906
				],
				[
					-7.407669628339985,
					-49.97342547906892
				],
				[
					-7.899490681838101,
					-50.65858487242105
				],
				[
					-7.787140414849029,
					-51.758181334985736
				],
				[
					-9.083735262862449,
					-51.9126546727414
				],
				[
					-8.971147464053175,
					-50.392736518514965
				],
				[
					-10.121393019353318,
					-50.665908389550204
				],
				[
					-11.163020297993127,
					-48.10216236140753
				],
				[
					-11.96958700095888,
					-51.063545792384
				],
				[
					-16.253400291333925,
					-49.59497676457463
				],
				[
					-15.197003786586011,
					-49.072989169912645
				],
				[
					-16.242122097794617,
					-48.26056411003553
				],
				[
					-16.21838832943422,
					-47.17249707658918
				],
				[
					-16.792367985199633,
					-41.33411110979817
				],
				[
					-17.268778019883158,
					-44.27476189560392
				],
				[
					-19.76240990781393,
					-43.69492845084675
				],
				[
					-19.838038668985867,
					-42.693953372856235
				],
				[
					-20.50220276178916,
					-37.579938963406725
				],
				[
					-21.67381247714738,
					-32.596909649032
				],
				[
					-22.85944342177608,
					-28.36837275396644
				],
				[
					-23.54560204754487,
					-25.563908781701613
				],
				[
					-23.688717253167894,
					-21.37645118776971
				],
				[
					-23.152432070098442,
					-16.810290217824765
				],
				[
					-22.477311822088986,
					-14.128983068387628
				],
				[
					-20.72414198835764,
					-9.557372570337217
				],
				[
					-18.731017053080524,
					-6.2949940699261795
				],
				[
					-15.436386756199546,
					-3.509357920350941
				],
				[
					-9.871023061076249,
					-1.1975863322515405
				],
				[
					-8.498191301295094,
					-0.8613546703835713
				],
				[
					-6.879464724704685,
					-0.7589178383546763
				],
				[
					-3.810758732159266,
					-0.3372048447970718
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 296,
			"versionNonce": 849852381,
			"isDeleted": false,
			"id": "A0cVhqcneJA91cUk6EjPO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3204.871968971059,
			"y": -3651.8352571586347,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7298339586749846,
			"height": 1.2847481561142535,
			"seed": 847988313,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.04426397163893734
				],
				[
					-0.007928247396899495,
					0.06805037489131392
				],
				[
					-0.068905821656326,
					0.17705754761740702
				],
				[
					-0.19005203313720448,
					0.37391993364111586
				],
				[
					-0.3450025108603448,
					0.5757090286066304
				],
				[
					-0.7298339586749846,
					1.2609617528618768
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				],
				[
					-0.7298339586749846,
					1.2847481561142535
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 1991639155,
			"isDeleted": false,
			"id": "DQcjnGseYuj_qRVduv2Xs",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3210.27618995815,
			"y": -3651.387260518328,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1193496004262047,
			"height": 1.5353608370293064,
			"seed": 1440944953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.006219014928543188,
					0.006220675990241698
				],
				[
					-0.006219014928543188,
					0.02488270396094637
				],
				[
					-0.006219014928543188,
					0.061110459193806345
				],
				[
					-0.006219014928543188,
					0.0973382144266561
				],
				[
					0.0017075714066680083,
					0.30479651290476617
				],
				[
					0.014657208261116224,
					0.369539713991922
				],
				[
					0.027603522992187844,
					0.4990244551045656
				],
				[
					0.035533431450775636,
					0.5670748299958898
				],
				[
					0.23093408319640837,
					0.9730200328203803
				],
				[
					0.3483279563429823,
					1.1349037819943262
				],
				[
					0.6236887952229236,
					1.3751846592620287
				],
				[
					0.6884303352483911,
					1.4010806108475486
				],
				[
					0.8179134152993669,
					1.4658221508730367
				],
				[
					0.9269288933338605,
					1.5100894446353197
				],
				[
					1.1006892335171983,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				],
				[
					1.1131305854976614,
					1.5353608370293064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 382,
			"versionNonce": 2013180989,
			"isDeleted": false,
			"id": "CXk7tytTseKMvfl_cYYUQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3204.7893926117786,
			"y": -3651.24580450569,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.45883171193256,
			"height": 1.2144669753871937,
			"seed": 1517175833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.006220675990241698
				],
				[
					0.006220675990231487,
					0.012441351980473185
				],
				[
					0.02488270396092595,
					0.03110337995117786
				],
				[
					0.06111045919379614,
					0.059402887787138335
				],
				[
					0.0735518111742591,
					0.07806491575784301
				],
				[
					0.09843617619687337,
					0.10294928078046747
				],
				[
					0.2516608108348765,
					0.210308680320365
				],
				[
					0.2754455530255954,
					0.21823858877894256
				],
				[
					0.483329083293674,
					0.3686111805130127
				],
				[
					0.547563999506865,
					0.4136774449432021
				],
				[
					0.6423740780571113,
					0.47842562921540227
				],
				[
					0.8029588769975767,
					0.58977988209483
				],
				[
					0.8671937932107677,
					0.6348461465250194
				],
				[
					0.9873300791904289,
					0.7186998622363926
				],
				[
					1.055380454081753,
					0.7487600954527607
				],
				[
					1.1439083973596074,
					0.7819580741819586
				],
				[
					1.2529155700857004,
					0.8299876726486252
				],
				[
					1.3414451744252633,
					0.8742516442875625
				],
				[
					1.538980290429211,
					0.9462935503950402
				],
				[
					1.6319133692814813,
					0.9794383751504985
				],
				[
					1.6681411245143312,
					0.9873666225473979
				],
				[
					1.7124050961532682,
					1.0094986083668667
				],
				[
					1.780455471044572,
					1.0205646012765959
				],
				[
					1.8689850753841353,
					1.0414408244662554
				],
				[
					1.9256903990035352,
					1.0760158233278752
				],
				[
					1.9732632055082882,
					1.0918723181216743
				],
				[
					2.0094909607411586,
					1.1060229025704935
				],
				[
					2.0980189040190127,
					1.1281548883899621
				],
				[
					2.1609465646903327,
					1.1405962403704353
				],
				[
					2.197174319923203,
					1.1468169163606667
				],
				[
					2.2520641031267474,
					1.1547451637575663
				],
				[
					2.264505455107231,
					1.1547451637575663
				],
				[
					2.2945125343498494,
					1.1626734111544759
				],
				[
					2.3307402895826987,
					1.1626734111544759
				],
				[
					2.4017025055984185,
					1.1885710238016738
				],
				[
					2.4902321099379607,
					1.2015189995944338
				],
				[
					2.546937433557382,
					1.2015189995944338
				],
				[
					2.683038183340009,
					1.2144669753871937
				],
				[
					2.73974350695941,
					1.2144669753871937
				],
				[
					2.8121990174251295,
					1.2144669753871937
				],
				[
					2.8484267726579793,
					1.2144669753871937
				],
				[
					2.8959995791627526,
					1.2144669753871937
				],
				[
					2.9878363573064433,
					1.2144669753871937
				],
				[
					3.0558867321977674,
					1.2144669753871937
				],
				[
					3.123937107089071,
					1.2144669753871937
				],
				[
					3.1715082525321563,
					1.2144669753871937
				],
				[
					3.239558627423481,
					1.2144669753871937
				],
				[
					3.2962656121045693,
					1.2144669753871937
				],
				[
					3.3734485041105198,
					1.2144669753871937
				],
				[
					3.441498879001844,
					1.2144669753871937
				],
				[
					3.4890716855065973,
					1.1986104805933946
				],
				[
					3.5457770091260183,
					1.1986104805933946
				],
				[
					3.8000191098110547,
					1.163528857919488
				],
				[
					3.9328110247278456,
					1.137632906333968
				],
				[
					3.9895163483472666,
					1.1265669134242289
				],
				[
					4.0257474257034715,
					1.1203462374339974
				],
				[
					4.061971858812965,
					1.1203462374339974
				],
				[
					4.130022233704291,
					1.0902860042176292
				],
				[
					4.177595040209043,
					1.0823560957590412
				],
				[
					4.225167846713816,
					1.0664996009652423
				],
				[
					4.359059384462545,
					1.0411086121303312
				],
				[
					4.415764708081945,
					1.0238236042920381
				],
				[
					4.494439233476208,
					0.9972316678627561
				],
				[
					4.551147879218965,
					0.9910109918725145
				],
				[
					4.587375634451835,
					0.9751544970787154
				],
				[
					4.637858621019316,
					0.9578661671170663
				],
				[
					4.662744647103618,
					0.9516471521885129
				],
				[
					4.687627351064564,
					0.9392058002080398
				],
				[
					4.700068703045027,
					0.9329834631561199
				],
				[
					4.790088279711214,
					0.8950481365166023
				],
				[
					4.808751968743597,
					0.8888291215880488
				],
				[
					4.844979723976447,
					0.8667502897423299
				],
				[
					4.868762805105477,
					0.8588220423454306
				],
				[
					4.904993882461704,
					0.8446714578966112
				],
				[
					4.963004800561286,
					0.7996068545280898
				],
				[
					4.987890826645589,
					0.7933861785378584
				],
				[
					5.011677229897976,
					0.777528022682371
				],
				[
					5.041682648078925,
					0.7633790992952401
				],
				[
					5.092168956769763,
					0.7412471134757714
				],
				[
					5.11082932367879,
					0.7288057614952982
				],
				[
					5.129493012711193,
					0.7225850855050667
				],
				[
					5.165720767944042,
					0.702215486127694
				],
				[
					5.190603471904989,
					0.6897741341472209
				],
				[
					5.250617630390225,
					0.6614746263112604
				],
				[
					5.286845385623075,
					0.6473240418624513
				],
				[
					5.305509074655458,
					0.6286620138917365
				],
				[
					5.341736829888328,
					0.6224413379015049
				],
				[
					5.354178181868791,
					0.6162206619112632
				],
				[
					5.372838548777818,
					0.6037793099308002
				],
				[
					5.409066304010667,
					0.5896303865436591
				],
				[
					5.42772999304307,
					0.5834097105534275
				],
				[
					5.440171345023534,
					0.5771890345631859
				],
				[
					5.4463903599520975,
					0.5709683585729544
				],
				[
					5.45883171193256,
					0.5647476825827127
				],
				[
					5.45883171193256,
					0.5647476825827127
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 434,
			"versionNonce": 329480723,
			"isDeleted": false,
			"id": "AGGetU3O_v3eRfl-ECPho",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3216.4764556716236,
			"y": -3647.010716651146,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.2919929863861097,
			"height": 10.05614713947535,
			"seed": 203446521,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.9525787545687106,
					5.109076046284637
				],
				[
					-3.2365237069869104,
					8.330564519521722
				],
				[
					-3.2919929863861097,
					10.05614713947535
				]
			]
		},
		{
			"type": "line",
			"version": 383,
			"versionNonce": 100082845,
			"isDeleted": false,
			"id": "v95WMrn0h7SnmW_-iUQyx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3210.9264121158176,
			"y": -3644.0709703871016,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.308295205736887,
			"height": 4.2386521846812055,
			"seed": 1820119513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.8735748420270605,
					1.8592800278163741
				],
				[
					-1.308295205736887,
					3.0300124815793525
				],
				[
					-1.2896952264573052,
					4.2386521846812055
				]
			]
		},
		{
			"type": "line",
			"version": 361,
			"versionNonce": 1408286643,
			"isDeleted": false,
			"id": "AUv1ZkZqI5cRRCkb_FbR9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3226.08862577931,
			"y": -3642.8974052337653,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.979200244411936,
			"height": 6.349292746246911,
			"seed": 9907897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.2184286074931212,
					2.4525343151186445
				],
				[
					-2.983550550259829,
					5.302566048437612
				],
				[
					-3.979200244411936,
					6.349292746246911
				]
			]
		},
		{
			"type": "line",
			"version": 412,
			"versionNonce": 809666813,
			"isDeleted": false,
			"id": "tVg5GhzEhAzLYX13Z9z1P",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3230.6367990185563,
			"y": -3649.5216112967264,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.75069794600514,
			"height": 13.781284999359455,
			"seed": 1595076505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-2.155387312744402,
					5.980101105050817
				],
				[
					-4.213960663561328,
					10.551560124992571
				],
				[
					-6.75069794600514,
					13.781284999359455
				]
			]
		},
		{
			"type": "line",
			"version": 341,
			"versionNonce": 1371820371,
			"isDeleted": false,
			"id": "2GGCglsgVcEY732co7ZVA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3208.213796371635,
			"y": -3640.6182738626558,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.440513075195675,
			"height": 1.5310652779431317,
			"seed": 2116260985,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.440513075195675,
					0.637603187417411
				],
				[
					-0.4287331472595126,
					1.5310652779431317
				]
			]
		},
		{
			"type": "line",
			"version": 370,
			"versionNonce": 1482842461,
			"isDeleted": false,
			"id": "dK4D1zsrj98dkRiLQQ2vN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3199.8802170251647,
			"y": -3649.83278564349,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1437404693820732,
			"height": 9.651962286952822,
			"seed": 1099734361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.05977844847463787,
					3.9162089275704397
				],
				[
					0.1579451040183376,
					7.765499306245013
				],
				[
					1.0839620209074352,
					9.651962286952822
				]
			]
		},
		{
			"type": "line",
			"version": 497,
			"versionNonce": 510963443,
			"isDeleted": false,
			"id": "2kSW98Fl9VZJk3xvBz1Ag",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3210.734494067422,
			"y": -3661.230999355206,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.082130137787962,
			"height": 3.626863342496488,
			"seed": 1218546233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.8664559603292138,
					1.6444192347542872
				],
				[
					-1.082130137787962,
					3.626863342496488
				]
			]
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 866659773,
			"isDeleted": false,
			"id": "eOcaPGpQOaLK6PtmO3YMU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3232.0485779382734,
			"y": -3664.845035537355,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.017333359247665,
			"height": 13.674580902047827,
			"seed": 2084952857,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.640921681848572,
					4.584175666104311
				],
				[
					-4.032918979131356,
					10.467450431638978
				],
				[
					-4.862355340050248,
					12.267592109136352
				],
				[
					-5.017333359247665,
					13.674580902047827
				]
			]
		},
		{
			"type": "line",
			"version": 828,
			"versionNonce": 1552439443,
			"isDeleted": false,
			"id": "_d_ZBe-kSQKCHe8908U92",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3232.2981048206757,
			"y": -3671.809120017204,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.1441010856961675,
			"height": 8.116227121636626,
			"seed": 1559039993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.144693543707741,
					1.600112772085941
				],
				[
					-2.5205049590493385,
					2.8338763277967733
				],
				[
					-3.1531376605122903,
					3.234583962023528
				],
				[
					-3.5804014111769535,
					4.178682767696058
				],
				[
					-5.1441010856961675,
					8.116227121636626
				]
			]
		},
		{
			"type": "line",
			"version": 362,
			"versionNonce": 1362456093,
			"isDeleted": false,
			"id": "gYFomRL9_Gl9nv-IwKON3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3226.690579743202,
			"y": -3672.4615276847544,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.710957147303426,
			"height": 7.682622509131813,
			"seed": 278571225,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.7794768766936546,
					2.498448096083899
				],
				[
					-2.710957147303426,
					7.682622509131813
				]
			]
		},
		{
			"type": "line",
			"version": 358,
			"versionNonce": 431345203,
			"isDeleted": false,
			"id": "3JVdnltwlu174hPU4KnYN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3215.63464172206,
			"y": -3669.3207976727444,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.184982127194678,
			"height": 5.461842627348771,
			"seed": 820127161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.062463917657961,
					1.9391402297540872
				],
				[
					-2.184982127194678,
					5.461842627348771
				]
			]
		},
		{
			"type": "line",
			"version": 347,
			"versionNonce": 1610326653,
			"isDeleted": false,
			"id": "vAYjGdgYCptzpyqwE4FvE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3207.548426716433,
			"y": -3675.1461736150522,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.01018498722789785,
			"height": 3.0643284619842257,
			"seed": 1491535513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.01018498722789785,
					3.0643284619842257
				]
			]
		},
		{
			"type": "line",
			"version": 304,
			"versionNonce": 1759743955,
			"isDeleted": false,
			"id": "r1xmjryLyWoY-SqkTSyjr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3207.437774610401,
			"y": -3669.9585989015804,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.05634808819300474,
			"height": 2.46004220674533,
			"seed": 1935461241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.05634808819300474,
					2.46004220674533
				]
			]
		},
		{
			"type": "line",
			"version": 340,
			"versionNonce": 884755165,
			"isDeleted": false,
			"id": "ik2jMLnAH_1b4a2_n65-q",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3203.465410331374,
			"y": -3672.2856881240095,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5634561267528417,
			"height": 6.391141373455735,
			"seed": 1216803929,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.49812367743048114,
					2.5417572787528453
				],
				[
					-0.5634561267528417,
					6.391141373455735
				]
			]
		},
		{
			"type": "line",
			"version": 331,
			"versionNonce": 1009261939,
			"isDeleted": false,
			"id": "O640ph9IajdweMY91otSq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3197.3407213086803,
			"y": -3673.422605005593,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0573015790795341,
			"height": 4.650691501312481,
			"seed": 1278804281,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.226905070927162,
					2.409043005073917
				],
				[
					-1.0573015790795341,
					4.650691501312481
				]
			]
		},
		{
			"type": "line",
			"version": 480,
			"versionNonce": 269018941,
			"isDeleted": false,
			"id": "OmFQls2-HORzolL1nnkBV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3210.588532237439,
			"y": -3678.160121754797,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.287879257380371,
			"height": 6.410909266635323,
			"seed": 735474201,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.287879257380371,
					6.410909266635323
				]
			]
		},
		{
			"type": "line",
			"version": 310,
			"versionNonce": 2127165203,
			"isDeleted": false,
			"id": "go-j6tnWWQkDMVFGESArD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3232.3123941819367,
			"y": -3654.5461953998456,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.38617192459011335,
			"height": 1.3607115732994128,
			"seed": 475186937,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.38617192459011335,
					1.3607115732994128
				]
			]
		},
		{
			"type": "line",
			"version": 369,
			"versionNonce": 608368541,
			"isDeleted": false,
			"id": "ItJwNpeyH2XtnDgTLoU8L",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3199.59686462055,
			"y": -3666.0666271220616,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.20447905658169496,
			"height": 2.1655227896177456,
			"seed": 1748074457,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.20447905658169496,
					0.9660812670886381
				],
				[
					-0.14131526960392057,
					2.1655227896177456
				]
			]
		},
		{
			"type": "ellipse",
			"version": 471,
			"versionNonce": 1866439859,
			"isDeleted": false,
			"id": "2_KpsINAQSX0KJ7eb_R9w",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3193.878496876586,
			"y": -3661.1133286395943,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 8.880415228039423,
			"height": 8.97084633273674,
			"seed": 1032199353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 636,
			"versionNonce": 1536949245,
			"isDeleted": false,
			"id": "Aj-y3i4itfjeetv3IkOVj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3213.5543875757876,
			"y": -3659.64189965488,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 9.842688958436396,
			"height": 9.566318928755615,
			"seed": 1005854105,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061098,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 425,
			"versionNonce": 959417939,
			"isDeleted": false,
			"id": "lKfQoOhnN8e4qqKj5_adJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3216.8606386601796,
			"y": -3649.8585516617686,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.197157746932062,
			"height": 0.7301953034773013,
			"seed": 1118765689,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.9130034466296221,
					0.4661997680443727
				],
				[
					2.187714445883716,
					0.7301953034773013
				],
				[
					3.424594637610123,
					0.6285619029820471
				],
				[
					4.197157746932062,
					0.29370739290548364
				]
			]
		},
		{
			"type": "line",
			"version": 400,
			"versionNonce": 1578464349,
			"isDeleted": false,
			"id": "sIxsiosV0nHSIG9qy84Ae",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3198.0558938032455,
			"y": -3651.3173905815665,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.83435389359901,
			"height": 1.7285457602682668,
			"seed": 2121943897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.9080785265234651,
					-0.036169490300095086
				],
				[
					-2.1233679191030395,
					-0.3252028473000484
				],
				[
					-3.83435389359901,
					-1.7285457602682668
				]
			]
		},
		{
			"type": "line",
			"version": 773,
			"versionNonce": 1332759539,
			"isDeleted": false,
			"id": "Dd4x6LowajbWNj1Zpb3bb",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3193.950315114349,
			"y": -3654.2415914103785,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.753725907146815,
			"height": 18.87580200901345,
			"seed": 933853241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.01906298270535446,
					1.9212986158095648
				],
				[
					0.07822527209690677,
					4.328768646994639
				],
				[
					0.5011190538825857,
					7.215298896843709
				],
				[
					1.1606219360931367,
					10.066401767641562
				],
				[
					1.4898937456384174,
					11.347593590699718
				],
				[
					2.121421985345346,
					12.731297963090578
				],
				[
					2.9477291286338283,
					14.068620382426987
				],
				[
					4.610975423813189,
					16.292877482505812
				],
				[
					5.708848902235462,
					17.467142037608724
				],
				[
					6.940334029513393,
					18.332310932745045
				],
				[
					7.753725907146815,
					18.87580200901345
				]
			]
		},
		{
			"type": "line",
			"version": 444,
			"versionNonce": 1468063933,
			"isDeleted": false,
			"id": "iv1oQTC8xAmieb9YUtvYX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3208.3143166979635,
			"y": -3633.3184972286617,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.303639294187098,
			"height": 9.142728363538836,
			"seed": 1612712217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.05989807582862913,
					1.4144619320777267
				],
				[
					0.4006135781547956,
					2.7370369986134184
				],
				[
					1.4673563329951367,
					4.30706189296516
				],
				[
					2.7789430931981083,
					5.995487263841337
				],
				[
					4.059146137347972,
					7.502367345650637
				],
				[
					5.303639294187098,
					9.142728363538836
				]
			]
		},
		{
			"type": "line",
			"version": 599,
			"versionNonce": 101209491,
			"isDeleted": false,
			"id": "R3lBhqzZ_RheImq6PsLIz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3205.146360477568,
			"y": -3633.868298358816,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.721124213726757,
			"height": 15.491699188467647,
			"seed": 1632730617,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.08917544319999793,
					2.167930426183388
				],
				[
					0.9820237291626759,
					4.733587053260998
				],
				[
					2.5103000018381647,
					6.525369687969913
				],
				[
					5.3306896873786345,
					9.275543562063996
				],
				[
					7.4506882634780265,
					11.083785987113858
				],
				[
					8.745998933494395,
					12.140454712812748
				],
				[
					9.528239404488497,
					14.123945990497553
				],
				[
					9.721124213726757,
					15.491699188467647
				]
			]
		},
		{
			"type": "line",
			"version": 760,
			"versionNonce": 2105524509,
			"isDeleted": false,
			"id": "Qm1aTDEtSIcjKJEXlOoEz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3204.988391232394,
			"y": -3633.950682194658,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.195970567096213,
			"height": 15.75447242302005,
			"seed": 708925145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.7986129007737702,
					0.8222529389374017
				],
				[
					-1.1832099472306445,
					2.087705467880643
				],
				[
					-1.02950437134939,
					3.6614282688531827
				],
				[
					-0.5850471979345925,
					5.209807549022644
				],
				[
					0.20563228059629318,
					6.621537162411354
				],
				[
					2.809420252896085,
					8.863600715921889
				],
				[
					4.167485946600783,
					10.13936795874329
				],
				[
					5.1058729711747395,
					11.127980313663405
				],
				[
					6.744207941022714,
					12.321887625884887
				],
				[
					7.639470290608984,
					14.060839809802099
				],
				[
					8.012760619865569,
					15.75447242302005
				]
			]
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 1814965043,
			"isDeleted": false,
			"id": "G0KzV2I4UPRF4RL-bgsOK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3203.7971972644273,
			"y": -3630.837943997357,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9368606366643345,
			"height": 1.9266683810109164,
			"seed": 2105742265,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.49084123473983954,
					0.2189944996171378
				],
				[
					-0.9368606366643345,
					0.8485599394016308
				],
				[
					-0.7099896381103101,
					1.9266683810109164
				]
			]
		},
		{
			"type": "line",
			"version": 673,
			"versionNonce": 1434686845,
			"isDeleted": false,
			"id": "6B9Ijb5-t_aeBClpZM06H",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3203.0476438203614,
			"y": -3629.2294642473817,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.320358725623308,
			"height": 11.279747706781784,
			"seed": 2134520985,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.581943823621141,
					0.24456782191488036
				],
				[
					-0.8283247582463455,
					1.0039120746163148
				],
				[
					-0.754676541607675,
					2.0130610933865922
				],
				[
					-0.1829030153290144,
					2.99480259444288
				],
				[
					0.050151540875420474,
					4.065989583694089
				],
				[
					1.1791915834796598,
					5.153066608407618
				],
				[
					3.213898291048533,
					6.221717348134968
				],
				[
					5.4073261502403005,
					7.7170715146102395
				],
				[
					6.733251568788664,
					9.279570968082858
				],
				[
					7.492033967376962,
					11.279747706781784
				]
			]
		},
		{
			"type": "line",
			"version": 507,
			"versionNonce": 1716014291,
			"isDeleted": false,
			"id": "pcCcDHUPw3vj0N0f6hZZn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3205.914113875514,
			"y": -3623.1663520959864,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.0995022959859457,
			"height": 4.552186298316722,
			"seed": 52050297,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.08979967765459178,
					0.7510102590457917
				],
				[
					0.4708864535734649,
					1.6709456993864424
				],
				[
					1.225316327521714,
					2.5370359087720757
				],
				[
					1.7680863752471827,
					3.0319756215454516
				],
				[
					2.0995022959859457,
					4.552186298316722
				]
			]
		},
		{
			"type": "line",
			"version": 430,
			"versionNonce": 986570205,
			"isDeleted": false,
			"id": "PSDckLlAtGiKqtWK6SBzj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3203.894539032097,
			"y": -3624.238242503521,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5128511926998245,
			"height": 6.400291649880057,
			"seed": 442933849,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.0907947813746564,
					0.7768913888501383
				],
				[
					0.06678790412781217,
					1.978567678208241
				],
				[
					0.5482431181859057,
					3.241480795221758
				],
				[
					1.2953594014457002,
					4.749202076997831
				],
				[
					2.422056411325168,
					6.400291649880057
				]
			]
		},
		{
			"type": "line",
			"version": 663,
			"versionNonce": 132987507,
			"isDeleted": false,
			"id": "h2cT1SZJAncwn4UGFvwjd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3202.1196879878944,
			"y": -3627.7323974731753,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.9944124328736397,
			"height": 9.872937670893526,
			"seed": 1643310905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.5749647311450454,
					1.0168415921806142
				],
				[
					-0.9471187645597482,
					3.185767130536075
				],
				[
					-0.32977465936530925,
					5.991394263590864
				],
				[
					3.0472936683138916,
					9.872937670893526
				]
			]
		},
		{
			"type": "line",
			"version": 450,
			"versionNonce": 611326525,
			"isDeleted": false,
			"id": "1CuuHhCzn5oQunzROPjZt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": 3201.2631452986516,
			"y": -3622.9666482722987,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.883572756258038,
			"height": 5.0743499232385645,
			"seed": 270704665,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.2808840692751711,
					1.189964770402931
				],
				[
					-0.2934110833929669,
					2.158607745268517
				],
				[
					-0.1177341754937465,
					3.1581854495630144
				],
				[
					1.590161672865071,
					5.0743499232385645
				]
			]
		},
		{
			"type": "line",
			"version": 506,
			"versionNonce": 769881107,
			"isDeleted": false,
			"id": "uLRC386iGe1TIblNS_MJr",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3211.2941632208176,
			"y": -3632.966021792965,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.175731392891473,
			"height": 6.4907495420154895,
			"seed": 1122579705,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.08825776670547884,
					1.3816326484622412
				],
				[
					0.616349269370473,
					3.031098023048004
				],
				[
					1.2923815002130266,
					4.496683857121642
				],
				[
					2.752502204344333,
					5.97642532600609
				],
				[
					4.175731392891473,
					6.4907495420154895
				]
			]
		},
		{
			"type": "line",
			"version": 689,
			"versionNonce": 726387357,
			"isDeleted": false,
			"id": "WMxuaDsF3M5SP6rHaQHlP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3215.536775281743,
			"y": -3627.800906418117,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5972700752300375,
			"height": 9.121681498205103,
			"seed": 231353817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.022887385561771553,
					2.7863810718515714
				],
				[
					1.4678559931257797,
					6.296875086518519
				],
				[
					1.5972700752300375,
					9.121681498205103
				]
			]
		},
		{
			"type": "line",
			"version": 404,
			"versionNonce": 1478588851,
			"isDeleted": false,
			"id": "7n_cp_4x8XCYPs3MFeHC7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3214.0050766385075,
			"y": -3626.9259614722387,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.5684240001593586,
			"height": 2.0517960749236597,
			"seed": 1205406393,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.4476723098978512,
					0.862328939458717
				],
				[
					1.0383771888887485,
					1.514908173870235
				],
				[
					1.5684240001593586,
					2.0517960749236597
				]
			]
		},
		{
			"type": "line",
			"version": 350,
			"versionNonce": 1343385341,
			"isDeleted": false,
			"id": "80p3-CTMRv9ZGvbnu4ge2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3216.715448230657,
			"y": -3627.780340238478,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1622991918464143,
			"height": 1.6011543529712913,
			"seed": 431573913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.32628436687414364,
					0.8434977752471803
				],
				[
					-1.1622991918464143,
					1.6011543529712913
				]
			]
		},
		{
			"type": "line",
			"version": 1385,
			"versionNonce": 1137560403,
			"isDeleted": false,
			"id": "KUQEHYOBbq8Yc2FTXNCqH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3215.582906350596,
			"y": -3627.838697168503,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17.17005930348325,
			"height": 5.173443043692675,
			"seed": 1268674681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					12.722308297280412,
					0.09325091661594379
				],
				[
					16.561001011760595,
					-0.2631817429838802
				],
				[
					14.99152426776313,
					-0.6827549985849858
				],
				[
					17.077679102622366,
					-1.1821579202045616
				],
				[
					16.629165616585876,
					-1.8119953268956044
				],
				[
					14.940082465284563,
					-1.7752186546646107
				],
				[
					16.003582699952297,
					-2.293109001117568
				],
				[
					17.17005930348325,
					-3.096653146809266
				],
				[
					16.509614024317454,
					-3.614495003038586
				],
				[
					13.72720704253443,
					-3.30758140313613
				],
				[
					13.967271598461856,
					-4.672623364234352
				],
				[
					13.254043656720116,
					-5.080192127076732
				],
				[
					11.756108967038527,
					-3.6465048754579357
				],
				[
					6.626576983264863,
					-3.518906014334551
				],
				[
					2.160930976265378,
					-4.034247461640108
				],
				[
					0.6336997584181455,
					-4.843800178522961
				]
			]
		},
		{
			"type": "line",
			"version": 400,
			"versionNonce": 21333853,
			"isDeleted": false,
			"id": "HtIWigDGXJ1u0Vals_19U",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3213.4542551053864,
			"y": -3631.701683485031,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6489850772807304,
			"height": 3.85757227764396,
			"seed": 1397487961,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.24650953913139304,
					0.8226724847854928
				],
				[
					1.2205727186865831,
					2.4023406088313584
				],
				[
					2.6489850772807304,
					3.85757227764396
				]
			]
		},
		{
			"type": "line",
			"version": 606,
			"versionNonce": 1161750771,
			"isDeleted": false,
			"id": "15eygX_YLdg7mQ0BmT_ep",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3214.646886913898,
			"y": -3632.5787999496197,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.867183364734756,
			"height": 4.862557577813378,
			"seed": 571827769,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.31564894280496936,
					0.6124573879029316
				],
				[
					1.417584325061547,
					1.5552885011625726
				],
				[
					2.804025388345296,
					2.627109891884193
				],
				[
					4.036169688195762,
					3.6022898051072754
				],
				[
					6.047384228467578,
					4.827452033485884
				],
				[
					6.867183364734756,
					4.862557577813378
				]
			]
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 1630966717,
			"isDeleted": false,
			"id": "3kR6r0SryFN2kNUORnxzV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3218.266182449078,
			"y": -3631.773523859636,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.635916621993541,
			"height": 4.090735409783935,
			"seed": 853423897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.5520422217951784,
					0.7685078508355633
				],
				[
					1.2501538633823799,
					1.4368570364559416
				],
				[
					2.9989601040530456,
					2.5702843901650096
				],
				[
					4.86412179877261,
					3.7153662637143143
				],
				[
					5.874409283663312,
					4.090735409783935
				],
				[
					6.635916621993541,
					4.047667658102286
				]
			]
		},
		{
			"type": "line",
			"version": 394,
			"versionNonce": 1643860627,
			"isDeleted": false,
			"id": "Bsm3mwWtocEel7-RxBsqP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3221.747814239322,
			"y": -3631.4014077750917,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.941551020190194,
			"height": 2.570554248800969,
			"seed": 1478093817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					1.9057416871009902,
					1.4285167179885279
				],
				[
					3.941551020190194,
					2.570554248800969
				]
			]
		},
		{
			"type": "line",
			"version": 502,
			"versionNonce": 1275532317,
			"isDeleted": false,
			"id": "TOP8pXQqhWdC6AYGTnCfo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3229.216649541185,
			"y": -3631.277337104806,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.143053717238449,
			"height": 1.7943280193230322,
			"seed": 1238107353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.11378758046610339,
					0.6955943664986743
				],
				[
					-0.4764143390693094,
					1.3881233075545827
				],
				[
					-1.143053717238449,
					1.7943280193230322
				]
			]
		},
		{
			"type": "line",
			"version": 1275,
			"versionNonce": 716802099,
			"isDeleted": false,
			"id": "m2FvjoaT-ZpSaMgW-MZ5k",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3204.574884561229,
			"y": -3634.133786818479,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.913177377390012,
			"height": 9.311987891746655,
			"seed": 1938293177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-1.5813062916355702,
					0.3468625579582445
				],
				[
					-3.37779276665983,
					0.4582606824079138
				],
				[
					-4.889885940228352,
					0.36840594168606405
				],
				[
					-5.510837110384202,
					-0.11306138459328444
				],
				[
					-6.543802807322912,
					-0.337934156011185
				],
				[
					-7.342496566474756,
					-0.3990104657310389
				],
				[
					-8.22653088696026,
					-0.8492079639079521
				],
				[
					-8.638904398484947,
					-1.5604658301267835
				],
				[
					-9.3520705802999,
					-1.689743866769822
				],
				[
					-11.182668129429604,
					-3.2198733366033765
				],
				[
					-11.869907874291737,
					-4.120854101473054
				],
				[
					-12.728189876172266,
					-4.067587859497074
				],
				[
					-12.521439385388696,
					-3.1576174288171974
				],
				[
					-14.162241486555956,
					-4.319243687146926
				],
				[
					-14.205285261826932,
					-3.163598716506548
				],
				[
					-14.858096865221821,
					-3.552178203437029
				],
				[
					-14.913177377390012,
					-1.9451932173126767
				],
				[
					-12.951971720904675,
					-0.6756356168229493
				],
				[
					-12.018710274190985,
					-0.453212325125452
				],
				[
					-11.801175193888138,
					0.2575430699352828
				],
				[
					-10.13206918795694,
					0.3112177376654394
				],
				[
					-10.219948437794166,
					1.0388980810180177
				],
				[
					-9.710420112594157,
					1.644584876014095
				],
				[
					-8.740734612240889,
					1.8267481363966722
				],
				[
					-8.630885281243218,
					2.58011738488189
				],
				[
					-7.163733987897939,
					2.711449910548854
				],
				[
					-6.128814296166925,
					3.7748487001962587
				],
				[
					-4.917474025117868,
					3.9461768552425642
				],
				[
					-4.052552955122872,
					4.7357637948810485
				],
				[
					-1.9091174003687412,
					4.992744204599728
				]
			]
		},
		{
			"type": "line",
			"version": 427,
			"versionNonce": 497584253,
			"isDeleted": false,
			"id": "q2YP5t7YDzFz1GIQTVaUc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3195.619932790535,
			"y": -3632.390644508766,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.429724120160359,
			"height": 1.327943674255136,
			"seed": 40985241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					2.28451440868112,
					-0.274384720869371
				],
				[
					4.633001188120533,
					-0.762513686160139
				],
				[
					5.67208574773946,
					-1.304278626214878
				],
				[
					6.429724120160359,
					-1.327943674255136
				]
			]
		},
		{
			"type": "line",
			"version": 426,
			"versionNonce": 1432357331,
			"isDeleted": false,
			"id": "LFGD-IKWg_VKiePlJ_rnH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3197.3430595512827,
			"y": -3631.4920465857303,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.462449771115478,
			"height": 0.9491964999539805,
			"seed": 859547513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					2.767290846983029,
					-0.18944291204832295
				],
				[
					4.41839924961538,
					-0.6519700313803845
				],
				[
					5.687285634622253,
					-0.9486719953012575
				],
				[
					6.462449771115478,
					-0.9491964999539805
				]
			]
		},
		{
			"type": "line",
			"version": 428,
			"versionNonce": 937193693,
			"isDeleted": false,
			"id": "FODJ-sDFi1v4p_EMqgV0b",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3194.5119425069697,
			"y": -3633.8282765601325,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.024094278494231,
			"height": 0.5436842742930232,
			"seed": 1613385817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					1.2260885315775738,
					-0.006253495455966463
				],
				[
					2.763290888089239,
					-0.14981950807088396
				],
				[
					4.024094278494231,
					-0.5436842742930232
				]
			]
		},
		{
			"type": "line",
			"version": 416,
			"versionNonce": 386226035,
			"isDeleted": false,
			"id": "Gw-7RJWu2PaFqPLN9uf4z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3196.0347482581483,
			"y": -3635.598083968166,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5830059222880033,
			"height": 0.3805560704702893,
			"seed": 1326505273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					-0.531120075135546,
					0.25223407253339
				],
				[
					-2.5830059222880033,
					0.3805560704702893
				]
			]
		},
		{
			"type": "line",
			"version": 384,
			"versionNonce": 1211387197,
			"isDeleted": false,
			"id": "ztZCeYK61rQGvC1f45gTK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3192.1342124435314,
			"y": -3637.2678778490517,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.3172027871709474,
			"height": 1.9295059065364162,
			"seed": 1062391321,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.1692000419061563,
					0.4291055323879196
				],
				[
					0.3172027871709474,
					1.1884007161247436
				],
				[
					0.10633901912105276,
					1.9295059065364162
				]
			]
		},
		{
			"type": "line",
			"version": 330,
			"versionNonce": 1039134995,
			"isDeleted": false,
			"id": "CRvzwWceRcfXI05aoBPOk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3190.431741277899,
			"y": -3637.2776746931286,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.444293059017627,
			"height": 0.4443306771791992,
			"seed": 937665273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.444293059017627,
					0.4443306771791992
				]
			]
		},
		{
			"type": "line",
			"version": 354,
			"versionNonce": 1309777309,
			"isDeleted": false,
			"id": "kbp-bl7e5Jo8Mb4fJR5SZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3212.415843700158,
			"y": -3634.664676061657,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.781240683075567,
			"height": 1.7023799459250535,
			"seed": 356965337,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061098,
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
					0.008852628221618638,
					0.5152631012499621
				],
				[
					-0.1479696516839345,
					1.2265491897577319
				],
				[
					-0.7723880548539483,
					1.7023799459250535
				]
			]
		},
		{
			"type": "line",
			"version": 860,
			"versionNonce": 194401971,
			"isDeleted": false,
			"id": "2ulQpFJROrpyEyVgJdYDz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 3200.705029914795,
			"y": -3621.2256948300383,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 33.6525053279589,
			"height": 3.4145048212059415,
			"seed": 1469053113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
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
					-2.3537957534759806,
					0.4021779149350832
				],
				[
					-6.29778879266089,
					1.5112600597990193
				],
				[
					-7.100493021680998,
					2.36772473063071
				],
				[
					-4.890049310530023,
					3.1203768741490383
				],
				[
					5.087933971687442,
					3.4145048212059415
				],
				[
					14.287705812671472,
					3.1621816800813094
				],
				[
					23.920204226160845,
					2.0641626393241816
				],
				[
					26.552012306277902,
					1.1511264686684028
				],
				[
					25.580594547997695,
					0.46208717376424424
				],
				[
					23.1622314493124,
					0.41390118272944054
				],
				[
					16.54529402918411,
					0.0920094202282663
				]
			]
		},
		{
			"type": "line",
			"version": 785,
			"versionNonce": 1621484029,
			"isDeleted": false,
			"id": "eQ61b4uJck4uY4Uq5IPNB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 3193.465518813481,
			"y": -3618.72281409651,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 34.01146039582781,
			"height": 24.90364316003663,
			"seed": 811760025,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
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
					1.1501969963285408,
					7.630832064340315
				],
				[
					2.43731599300016,
					13.57813232884351
				],
				[
					4.85999994643465,
					19.665606555248107
				],
				[
					9.830277019469554,
					22.98416599835581
				],
				[
					18.187370171032022,
					23.66333858688293
				],
				[
					24.7581723974292,
					23.194641434824785
				],
				[
					30.56743171988788,
					21.42586748837234
				],
				[
					30.94703299001388,
					20.007356851779857
				],
				[
					31.967626984860182,
					13.195268372478363
				],
				[
					33.092016824182984,
					8.277547002106845
				],
				[
					34.01146039582781,
					1.147667163280427
				],
				[
					33.91090102170398,
					-1.2403045731537017
				]
			]
		},
		{
			"type": "ellipse",
			"version": 656,
			"versionNonce": 1319045203,
			"isDeleted": false,
			"id": "tRBOE-GHvGs33ujySEssK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3195.7041474721145,
			"y": -3659.292488590492,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1358028409,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 725,
			"versionNonce": 888314461,
			"isDeleted": false,
			"id": "m6BehXdk0nmjE6jWz6zD5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3200.5377588697966,
			"y": -3656.726292755746,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 2013374297,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 723,
			"versionNonce": 1021347315,
			"isDeleted": false,
			"id": "529nJNeykDCH6SNyk_8Ac",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3216.2586504538913,
			"y": -3657.9210675296454,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.1122362503699796,
			"height": 2.0401017720173447,
			"seed": 1071993913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 761,
			"versionNonce": 1674135229,
			"isDeleted": false,
			"id": "QHHIkbEhSEUIMVO3Iwm5a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3221.138587315233,
			"y": -3654.872158725251,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 5.82241913004278,
			"height": 3.563596364687012,
			"seed": 746611993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
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
					-0.5043548811327101,
					0.7308323358426202
				],
				[
					-1.0454819502382873,
					1.270480269071589
				],
				[
					-2.2946818044448474,
					1.5034746224379525
				],
				[
					-3.8884367902326717,
					1.511569846082751
				],
				[
					-4.453528470779436,
					2.064707498506562
				],
				[
					-4.444115076044587,
					2.8641221444688605
				],
				[
					-3.7154814321785716,
					3.2880416166305193
				],
				[
					-1.2272259856393537,
					3.2341479958456856
				],
				[
					0.34595596026444586,
					2.2076816424213477
				],
				[
					1.159470251450728,
					1.2307045651891986
				],
				[
					1.368890659263344,
					0.12545160425631172
				],
				[
					0.7415612914277312,
					-0.27555474805649316
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 245,
			"versionNonce": 224481171,
			"isDeleted": false,
			"id": "yOJMynJS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2550.2903421390142,
			"y": -3449.445121123268,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 800.8592529296875,
			"height": 75,
			"seed": 1947607703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KwYNb-Zb0Rtn0FKWZOqyn",
					"type": "arrow"
				}
			],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Train each Bootstrap tree model on a dataset of length N (duplicates allowed)\nWe use majority vote for classification and averaging for regression\nSmoother decision boundary via lower variance",
			"rawText": "Train each Bootstrap tree model on a dataset of length N (duplicates allowed)\nWe use majority vote for classification and averaging for regression\nSmoother decision boundary via lower variance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Train each Bootstrap tree model on a dataset of length N (duplicates allowed)\nWe use majority vote for classification and averaging for regression\nSmoother decision boundary via lower variance",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 58,
			"versionNonce": 1875601181,
			"isDeleted": false,
			"id": "d-mGVpIAToDd9Hg-sXarK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3374.986034817141,
			"y": -3430.7667070940743,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 109.62761793096251,
			"height": 94.08984531082615,
			"seed": 1846083257,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
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
					100.1323124408791,
					0
				],
				[
					109.62761793096251,
					-94.08984531082615
				]
			]
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 1381492019,
			"isDeleted": false,
			"id": "lPkcYeWG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3306.150859666721,
			"y": -3580.101966165386,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 353.4727478027344,
			"height": 40,
			"seed": 1101504439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "if datasets are highly overlapping\npredictions of trees become highly corrolated",
			"rawText": "if datasets are highly overlapping\npredictions of trees become highly corrolated",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if datasets are highly overlapping\npredictions of trees become highly corrolated",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 191527805,
			"isDeleted": false,
			"id": "KwYNb-Zb0Rtn0FKWZOqyn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2969.1735487959368,
			"y": -3364.519386945524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.1030447573007223,
			"height": 114.71665475923646,
			"seed": 2128056919,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yOJMynJS",
				"focus": -0.04490519819386148,
				"gap": 9.925734177744289
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
					1.1030447573007223,
					114.71665475923646
				]
			]
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 321570515,
			"isDeleted": false,
			"id": "XP3bSZJQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3001.227392563687,
			"y": -3327.015865197312,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 235.9204864501953,
			"height": 20,
			"seed": 652631609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets lower the variance more!",
			"rawText": "Lets lower the variance more!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets lower the variance more!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 518521821,
			"isDeleted": false,
			"id": "dWY33LM0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2864.1782244496744,
			"y": -3228.8448817975805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 216.60891723632812,
			"height": 35,
			"seed": 627670519,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Random forests",
			"rawText": "Random forests",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Random forests",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 42,
			"versionNonce": 644904051,
			"isDeleted": false,
			"id": "dnqWRCjw8nf694O7ySq4p",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2572.928831418255,
			"y": -3187.639929076634,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 905,
			"height": 211,
			"seed": 112689303,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zfV-LJ9IG1QwQ2e3MZhtC",
					"type": "arrow"
				}
			],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c74e69a95f5da8e772d048911721c02c8054aaa8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 764,
			"versionNonce": 240484413,
			"isDeleted": false,
			"id": "VPpOySqE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2628.245478757092,
			"y": -2780.0937926626266,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 838.6736450195312,
			"height": 100,
			"seed": 1544638711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Control the error via out of bag Samples:\nSince we only grow our bootstrapped trees according to our samples, We use the out of bag samples\nas a measure of error rate and run them through our tree to see the results and build further upon it.\nOnce we know our error we can tweak parameters to get lowest error\n",
			"rawText": "Control the error via out of bag Samples:\nSince we only grow our bootstrapped trees according to our samples, We use the out of bag samples\nas a measure of error rate and run them through our tree to see the results and build further upon it.\nOnce we know our error we can tweak parameters to get lowest error\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Control the error via out of bag Samples:\nSince we only grow our bootstrapped trees according to our samples, We use the out of bag samples\nas a measure of error rate and run them through our tree to see the results and build further upon it.\nOnce we know our error we can tweak parameters to get lowest error\n",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 48,
			"versionNonce": 1273982483,
			"isDeleted": false,
			"id": "zfV-LJ9IG1QwQ2e3MZhtC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3487.3250524235245,
			"y": -3156.9551766462087,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 96.66666666666606,
			"height": 2.2222222222221717,
			"seed": 585535945,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dnqWRCjw8nf694O7ySq4p",
				"focus": -0.5538884411704744,
				"gap": 9.396221005269581
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
					96.66666666666606,
					-2.2222222222221717
				]
			]
		},
		{
			"type": "text",
			"version": 169,
			"versionNonce": 1066692765,
			"isDeleted": false,
			"id": "NbnepCkc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3605.102830201302,
			"y": -3179.177398868431,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 287.4085693359375,
			"height": 80,
			"seed": 1453185927,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Picking random tuples from the\ndataset with duplicates allowed\nNote that we only will use a subset\nof their features though!",
			"rawText": "Picking random tuples from the\ndataset with duplicates allowed\nNote that we only will use a subset\nof their features though!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Picking random tuples from the\ndataset with duplicates allowed\nNote that we only will use a subset\nof their features though!",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"id": "WCIfuDMkvzLd_9HyGVUG9",
			"type": "freedraw",
			"x": 460.68988643146326,
			"y": -3345.057411718818,
			"width": 33.110675329203445,
			"height": 52.58754316991144,
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
			"seed": 1954589907,
			"version": 38,
			"versionNonce": 111031219,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956061099,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.9476867840707541,
					0
				],
				[
					7.79074713628313,
					0
				],
				[
					12.335349632448356,
					0.6492289280236037
				],
				[
					14.932265344542714,
					1.947686784070811
				],
				[
					18.178409984660675,
					3.895373568141622
				],
				[
					20.126096768731486,
					7.1415182082591855
				],
				[
					22.7230124808259,
					11.036891776400807
				],
				[
					22.7230124808259,
					14.93226534454243
				],
				[
					22.7230124808259,
					20.12609676873126
				],
				[
					22.7230124808259,
					25.319928192920088
				],
				[
					22.7230124808259,
					29.864530689085313
				],
				[
					21.424554624778693,
					34.40913318525054
				],
				[
					18.82763891268428,
					38.30450675339216
				],
				[
					17.529181056637128,
					41.55065139351018
				],
				[
					15.581494272566317,
					43.49833817758099
				],
				[
					13.633807488495506,
					45.4460249616518
				],
				[
					12.335349632448356,
					47.39371174572261
				],
				[
					9.738433920353941,
					49.34139852979342
				],
				[
					7.79074713628313,
					51.289085313864234
				],
				[
					5.193831424188772,
					52.58754316991144
				],
				[
					3.2461446401179614,
					52.58754316991144
				],
				[
					1.9476867840707541,
					52.58754316991144
				],
				[
					0,
					52.58754316991144
				],
				[
					-2.5969157120944146,
					51.93831424188738
				],
				[
					-3.2461446401180183,
					51.93831424188738
				],
				[
					-5.193831424188772,
					50.63985638584063
				],
				[
					-6.49228928023598,
					49.34139852979342
				],
				[
					-8.43997606430679,
					48.042940673746216
				],
				[
					-9.089204992330394,
					46.74448281769901
				],
				[
					-9.089204992330394,
					46.095253889675405
				],
				[
					-9.738433920353941,
					43.49833817758099
				],
				[
					-10.387662848377545,
					42.84910924955739
				],
				[
					-10.387662848377545,
					41.55065139351018
				],
				[
					-10.387662848377545,
					40.901422465486576
				],
				[
					-10.387662848377545,
					40.901422465486576
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-10.387662848377545,
				40.901422465486576
			]
		},
		{
			"id": "V1uPHV8OsT08fxH2q-x6W",
			"type": "freedraw",
			"x": 369.14860758013606,
			"y": -3371.026568839762,
			"width": 29.864530689085484,
			"height": 57.13214566607667,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1813818717,
			"version": 47,
			"versionNonce": 188714739,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6492289280236037,
					0
				],
				[
					1.2984578560472073,
					0
				],
				[
					3.2461446401180183,
					0
				],
				[
					5.193831424188772,
					0
				],
				[
					7.141518208259583,
					0
				],
				[
					9.089204992330394,
					0.6492289280236037
				],
				[
					11.036891776401148,
					3.2461446401180183
				],
				[
					12.98457856047196,
					5.193831424188829
				],
				[
					13.633807488495563,
					9.089204992330451
				],
				[
					13.633807488495563,
					13.633807488495677
				],
				[
					13.633807488495563,
					16.879952128613695
				],
				[
					12.335349632448356,
					22.073783552802524
				],
				[
					9.738433920353998,
					30.513759617109372
				],
				[
					6.49228928023598,
					36.356819969321805
				],
				[
					4.544602496165169,
					41.55065139351018
				],
				[
					-3.2461446401179614,
					51.93831424188784
				],
				[
					-8.439976064306734,
					55.184458882005856
				],
				[
					-12.335349632448356,
					57.13214566607667
				],
				[
					-12.984578560471903,
					57.13214566607667
				],
				[
					-13.633807488495506,
					57.13214566607667
				],
				[
					-14.932265344542714,
					56.48291673805306
				],
				[
					-16.23072320058992,
					55.184458882005856
				],
				[
					-16.23072320058992,
					52.58754316991144
				],
				[
					-16.23072320058992,
					49.99062745781703
				],
				[
					-15.581494272566317,
					48.042940673746216
				],
				[
					-13.633807488495506,
					45.4460249616518
				],
				[
					-12.984578560471903,
					44.147567105604594
				],
				[
					-9.089204992330338,
					42.84910924955739
				],
				[
					-7.1415182082595265,
					42.84910924955739
				],
				[
					-3.895373568141565,
					42.84910924955739
				],
				[
					-1.9476867840707541,
					42.84910924955739
				],
				[
					-0.6492289280236037,
					42.84910924955739
				],
				[
					1.947686784070811,
					42.84910924955739
				],
				[
					3.2461446401180183,
					43.49833817758099
				],
				[
					3.895373568141622,
					44.147567105604594
				],
				[
					5.193831424188772,
					45.4460249616518
				],
				[
					5.843060352212376,
					46.095253889675405
				],
				[
					6.49228928023598,
					48.042940673746216
				],
				[
					7.141518208259583,
					50.63985638584063
				],
				[
					7.790747136283187,
					52.58754316991144
				],
				[
					9.089204992330394,
					54.53522995398225
				],
				[
					9.738433920353998,
					55.184458882005856
				],
				[
					10.387662848377545,
					55.184458882005856
				],
				[
					10.387662848377545,
					55.184458882005856
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				10.387662848377545,
				55.184458882005856
			]
		},
		{
			"id": "8kPMf2Q_toPmLjOrWqgCY",
			"type": "freedraw",
			"x": 391.87162006096196,
			"y": -3415.1741359453667,
			"width": 16.879952128613525,
			"height": 44.147567105604594,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 103178909,
			"version": 53,
			"versionNonce": 1971015101,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.6492289280236037
				],
				[
					0.6492289280236037,
					-0.6492289280236037
				],
				[
					1.2984578560472073,
					0
				],
				[
					1.2984578560472073,
					0.6492289280236037
				],
				[
					1.2984578560472073,
					1.947686784070811
				],
				[
					1.2984578560472073,
					3.2461446401180183
				],
				[
					1.2984578560472073,
					5.193831424188829
				],
				[
					1.2984578560472073,
					5.843060352212433
				],
				[
					1.2984578560472073,
					6.492289280236037
				],
				[
					1.947686784070811,
					11.686120704424866
				],
				[
					3.895373568141565,
					19.47686784070811
				],
				[
					4.544602496165169,
					24.021470336873335
				],
				[
					5.193831424188772,
					29.86453068908577
				],
				[
					5.193831424188772,
					34.409133185250994
				],
				[
					5.193831424188772,
					37.00604889734541
				],
				[
					5.193831424188772,
					38.953735681415765
				],
				[
					5.193831424188772,
					39.60296460943937
				],
				[
					5.193831424188772,
					40.25219353746297
				],
				[
					3.895373568141565,
					41.55065139351018
				],
				[
					2.5969157120944146,
					42.19988032153378
				],
				[
					0,
					42.84910924955739
				],
				[
					-1.9476867840707541,
					43.49833817758099
				],
				[
					-3.895373568141565,
					43.49833817758099
				],
				[
					-4.544602496165169,
					43.49833817758099
				],
				[
					-5.193831424188772,
					43.49833817758099
				],
				[
					-6.49228928023598,
					42.19988032153378
				],
				[
					-7.141518208259583,
					41.55065139351018
				],
				[
					-9.089204992330338,
					40.25219353746297
				],
				[
					-9.089204992330338,
					39.60296460943937
				],
				[
					-9.089204992330338,
					38.30450675339216
				],
				[
					-9.089204992330338,
					37.00604889734541
				],
				[
					-9.089204992330338,
					35.7075910412982
				],
				[
					-8.439976064306734,
					35.05836211327414
				],
				[
					-7.141518208259583,
					34.409133185250994
				],
				[
					-6.49228928023598,
					34.409133185250994
				],
				[
					-5.843060352212376,
					34.409133185250994
				],
				[
					-4.544602496165169,
					34.409133185250994
				],
				[
					-2.596915712094358,
					34.409133185250994
				],
				[
					-1.2984578560472073,
					34.409133185250994
				],
				[
					0,
					34.409133185250994
				],
				[
					1.2984578560472073,
					35.05836211327414
				],
				[
					2.5969157120944146,
					35.7075910412982
				],
				[
					3.895373568141565,
					35.7075910412982
				],
				[
					4.544602496165169,
					35.7075910412982
				],
				[
					5.193831424188772,
					36.35681996932135
				],
				[
					5.843060352212376,
					37.00604889734541
				],
				[
					6.49228928023598,
					37.65527782536856
				],
				[
					7.141518208259583,
					37.65527782536856
				],
				[
					7.790747136283187,
					38.30450675339216
				],
				[
					7.790747136283187,
					38.30450675339216
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				7.790747136283187,
				38.30450675339216
			]
		},
		{
			"id": "1qogbjvT6XxlNWxH2Gd7V",
			"type": "freedraw",
			"x": 402.9085118373631,
			"y": -3426.860256649791,
			"width": 7.141518208259583,
			"height": 16.230723200589637,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 846372381,
			"version": 29,
			"versionNonce": 754399379,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.6492289280236037
				],
				[
					0,
					3.2461446401175635
				],
				[
					0,
					5.843060352211978
				],
				[
					0,
					8.439976064306393
				],
				[
					0,
					11.036891776400807
				],
				[
					0,
					12.984578560471618
				],
				[
					0,
					14.283036416518826
				],
				[
					0,
					14.93226534454243
				],
				[
					0.6492289280236037,
					13.633807488495222
				],
				[
					0.6492289280236037,
					12.335349632448015
				],
				[
					1.2984578560472073,
					10.387662848377204
				],
				[
					1.947686784070811,
					9.089204992329996
				],
				[
					2.5969157120944146,
					7.790747136282789
				],
				[
					3.895373568141565,
					6.492289280235582
				],
				[
					4.544602496165169,
					6.492289280235582
				],
				[
					5.843060352212376,
					7.1415182082591855
				],
				[
					6.49228928023598,
					7.1415182082591855
				],
				[
					7.141518208259583,
					7.790747136282789
				],
				[
					7.141518208259583,
					8.439976064306393
				],
				[
					7.141518208259583,
					9.7384339203536
				],
				[
					7.141518208259583,
					11.036891776400807
				],
				[
					7.141518208259583,
					12.984578560471618
				],
				[
					7.141518208259583,
					14.283036416518826
				],
				[
					7.141518208259583,
					15.581494272566033
				],
				[
					7.141518208259583,
					16.230723200589637
				],
				[
					7.141518208259583,
					16.230723200589637
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				7.141518208259583,
				16.230723200589637
			]
		},
		{
			"id": "hRL3Nq5yxSJcgo4PUp5oK",
			"type": "freedraw",
			"x": 425.631524318189,
			"y": -3413.8756780893195,
			"width": 5.193831424188772,
			"height": 1.2984578560472073,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1009361053,
			"version": 10,
			"versionNonce": 732204573,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6492289280236037,
					0
				],
				[
					1.2984578560472073,
					-0.6492289280236037
				],
				[
					-0.6492289280236037,
					-1.2984578560472073
				],
				[
					-1.947686784070811,
					-1.2984578560472073
				],
				[
					-3.895373568141565,
					-1.2984578560472073
				],
				[
					-3.2461446401179614,
					-1.2984578560472073
				],
				[
					-3.2461446401179614,
					-1.2984578560472073
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-3.2461446401179614,
				-1.2984578560472073
			]
		},
		{
			"id": "DVV-lMidQx15KkpfmjMNm",
			"type": "freedraw",
			"x": 447.0560789429677,
			"y": -3432.7033170020036,
			"width": 2.596915712094358,
			"height": 21.424554624778466,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1851979773,
			"version": 14,
			"versionNonce": 961064499,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6492289280236037,
					1.2984578560472073
				],
				[
					-1.2984578560472073,
					3.2461446401180183
				],
				[
					-1.9476867840707541,
					6.492289280236037
				],
				[
					-2.596915712094358,
					10.387662848377204
				],
				[
					-2.596915712094358,
					13.633807488495222
				],
				[
					-2.596915712094358,
					16.87995212861324
				],
				[
					-2.596915712094358,
					18.178409984660448
				],
				[
					-2.596915712094358,
					19.476867840707655
				],
				[
					-1.9476867840707541,
					20.775325696754862
				],
				[
					-1.2984578560472073,
					21.424554624778466
				],
				[
					-1.2984578560472073,
					21.424554624778466
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-1.2984578560472073,
				21.424554624778466
			]
		},
		{
			"id": "KcvCkZbqzYKyFB1E3sDpn",
			"type": "freedraw",
			"x": 500.2928510409027,
			"y": -3347.6543274309124,
			"width": 26.618386048967523,
			"height": 30.513759617108917,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1686760669,
			"version": 12,
			"versionNonce": 1602667133,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6492289280236037,
					0
				],
				[
					-9.089204992330394,
					7.14151820825964
				],
				[
					-14.93226534454277,
					12.984578560472073
				],
				[
					-19.47686784070794,
					18.82763891268405
				],
				[
					-24.67069926489671,
					24.670699264896484
				],
				[
					-25.96915712094392,
					28.566072833038106
				],
				[
					-26.618386048967523,
					29.864530689085313
				],
				[
					-26.618386048967523,
					30.513759617108917
				],
				[
					-26.618386048967523,
					30.513759617108917
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-26.618386048967523,
				30.513759617108917
			]
		},
		{
			"id": "NUXOA89XSOmIhF4uyYfuu",
			"type": "freedraw",
			"x": 480.16675427217115,
			"y": -3345.7066406468416,
			"width": 21.424554624778693,
			"height": 33.11067532920333,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1273581821,
			"version": 15,
			"versionNonce": 1394241491,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.6492289280236037
				],
				[
					0.6492289280236037,
					3.2461446401180183
				],
				[
					3.895373568141622,
					9.089204992329996
				],
				[
					5.843060352212376,
					13.633807488495222
				],
				[
					9.738433920353941,
					20.775325696754862
				],
				[
					13.633807488495563,
					25.319928192920088
				],
				[
					16.879952128613525,
					29.21530176106171
				],
				[
					18.178409984660732,
					31.812217473156124
				],
				[
					18.827638912684336,
					32.46144640117973
				],
				[
					20.775325696755147,
					33.11067532920333
				],
				[
					21.424554624778693,
					33.11067532920333
				],
				[
					21.424554624778693,
					33.11067532920333
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				21.424554624778693,
				33.11067532920333
			]
		},
		{
			"id": "aopqXvSKNzOSiEH-2nt_j",
			"type": "freedraw",
			"x": 541.8435024344128,
			"y": -3352.8481588551012,
			"width": 23.372241408849504,
			"height": 43.49833817758099,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1125704253,
			"version": 40,
			"versionNonce": 1440967389,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.947686784070811
				],
				[
					0,
					-3.2461446401180183
				],
				[
					1.2984578560472073,
					-3.895373568141622
				],
				[
					3.895373568141622,
					-3.895373568141622
				],
				[
					5.843060352212433,
					-3.895373568141622
				],
				[
					7.790747136283244,
					-2.5969157120944146
				],
				[
					11.036891776401262,
					0.6492289280236037
				],
				[
					15.581494272566374,
					4.544602496165226
				],
				[
					20.1260967687316,
					9.089204992330451
				],
				[
					22.073783552802297,
					12.33534963244847
				],
				[
					22.7230124808259,
					17.529181056636844
				],
				[
					21.424554624778693,
					20.12609676873126
				],
				[
					17.529181056637185,
					25.96915712094369
				],
				[
					14.28303641651928,
					29.864530689085313
				],
				[
					8.439976064306848,
					34.40913318525054
				],
				[
					5.193831424188829,
					37.65527782536856
				],
				[
					2.5969157120944146,
					38.953735681415765
				],
				[
					0,
					39.60296460943937
				],
				[
					0,
					38.953735681415765
				],
				[
					-0.6492289280236037,
					35.707591041297746
				],
				[
					-0.6492289280236037,
					33.759904257226935
				],
				[
					-0.6492289280236037,
					30.513759617108917
				],
				[
					0,
					28.566072833038106
				],
				[
					1.947686784070811,
					25.319928192920088
				],
				[
					5.843060352212433,
					23.372241408849277
				],
				[
					7.790747136283244,
					22.07378355280207
				],
				[
					10.387662848377659,
					22.07378355280207
				],
				[
					12.984578560472073,
					22.07378355280207
				],
				[
					13.633807488495677,
					24.670699264896484
				],
				[
					13.633807488495677,
					27.2676149769909
				],
				[
					13.633807488495677,
					30.513759617108917
				],
				[
					13.633807488495677,
					33.11067532920333
				],
				[
					13.633807488495677,
					35.707591041297746
				],
				[
					13.633807488495677,
					36.35681996932135
				],
				[
					13.633807488495677,
					37.65527782536856
				],
				[
					13.633807488495677,
					38.30450675339216
				],
				[
					13.633807488495677,
					38.30450675339216
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				13.633807488495677,
				38.30450675339216
			]
		},
		{
			"id": "Sy8o2WkGXHxXaU9nFBO2d",
			"type": "freedraw",
			"x": 572.357262051522,
			"y": -3381.41423168814,
			"width": 20.77532569675509,
			"height": 42.19988032153378,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1857193181,
			"version": 43,
			"versionNonce": 2088959347,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6492289280236037,
					0
				],
				[
					-0.6492289280236037,
					-0.6492289280231489
				],
				[
					0,
					-0.6492289280231489
				],
				[
					3.2461446401180183,
					-1.9476867840703562
				],
				[
					4.544602496165226,
					-3.2461446401175635
				],
				[
					7.1415182082595265,
					-3.2461446401175635
				],
				[
					8.439976064306734,
					-3.2461446401175635
				],
				[
					8.439976064306734,
					-1.9476867840703562
				],
				[
					8.439976064306734,
					3.246144640118473
				],
				[
					8.439976064306734,
					8.439976064306848
				],
				[
					7.79074713628313,
					14.28303641651928
				],
				[
					5.843060352212433,
					20.775325696755317
				],
				[
					3.2461446401180183,
					25.969157120944146
				],
				[
					-0.6492289280236037,
					31.162988545132976
				],
				[
					-3.2461446401180183,
					35.7075910412982
				],
				[
					-5.193831424188829,
					37.65527782536901
				],
				[
					-7.14151820825964,
					38.304506753392616
				],
				[
					-7.790747136283244,
					37.65527782536901
				],
				[
					-9.738433920354055,
					35.7075910412982
				],
				[
					-10.387662848377545,
					34.409133185250994
				],
				[
					-11.036891776401148,
					33.11067532920379
				],
				[
					-11.036891776401148,
					31.81221747315658
				],
				[
					-11.036891776401148,
					30.513759617109372
				],
				[
					-10.387662848377545,
					27.916843905014957
				],
				[
					-9.738433920354055,
					25.969157120944146
				],
				[
					-6.492289280236037,
					24.021470336873335
				],
				[
					-5.193831424188829,
					24.021470336873335
				],
				[
					-4.544602496165226,
					24.021470336873335
				],
				[
					-2.5969157120944146,
					26.61838604896775
				],
				[
					-1.2984578560472073,
					29.215301761062165
				],
				[
					1.2984578560472073,
					32.46144640118018
				],
				[
					1.2984578560472073,
					34.409133185250994
				],
				[
					2.5969157120944146,
					36.356819969321805
				],
				[
					3.2461446401180183,
					37.00604889734541
				],
				[
					5.193831424188829,
					38.304506753392616
				],
				[
					5.843060352212433,
					38.95373568141622
				],
				[
					7.79074713628313,
					38.95373568141622
				],
				[
					9.089204992330338,
					38.95373568141622
				],
				[
					9.738433920353941,
					38.304506753392616
				],
				[
					9.738433920353941,
					38.304506753392616
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				9.738433920353941,
				38.304506753392616
			]
		},
		{
			"id": "2SFW_fWglKEr-5PL2y8xd",
			"type": "freedraw",
			"x": 580.7972381158287,
			"y": -3420.3679673695556,
			"width": 12.98457856047196,
			"height": 33.75990425722739,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1975439517,
			"version": 31,
			"versionNonce": 1061947197,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					3.2461446401180183
				],
				[
					0,
					11.036891776401262
				],
				[
					0,
					20.775325696755317
				],
				[
					0,
					27.916843905014957
				],
				[
					0,
					30.513759617109372
				],
				[
					0,
					33.11067532920379
				],
				[
					0,
					33.75990425722739
				],
				[
					0,
					32.46144640118018
				],
				[
					0,
					29.215301761062165
				],
				[
					0.6492289280236037,
					26.61838604896775
				],
				[
					1.2984578560472073,
					22.723012480826128
				],
				[
					1.947686784070811,
					18.827638912684506
				],
				[
					2.5969157120944146,
					16.879952128613695
				],
				[
					2.5969157120944146,
					15.581494272566488
				],
				[
					3.8953735681415083,
					13.633807488495677
				],
				[
					4.544602496165112,
					13.633807488495677
				],
				[
					5.193831424188716,
					14.932265344542884
				],
				[
					5.843060352212319,
					16.879952128613695
				],
				[
					7.1415182082595265,
					20.775325696755317
				],
				[
					7.79074713628313,
					23.37224140884973
				],
				[
					8.439976064306734,
					25.969157120944146
				],
				[
					9.089204992330338,
					27.916843905014957
				],
				[
					9.089204992330338,
					28.56607283303856
				],
				[
					9.089204992330338,
					29.215301761062165
				],
				[
					9.738433920353941,
					29.86453068908577
				],
				[
					11.036891776401148,
					31.162988545132976
				],
				[
					12.98457856047196,
					32.46144640118018
				],
				[
					12.98457856047196,
					32.46144640118018
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				12.98457856047196,
				32.46144640118018
			]
		},
		{
			"id": "DdT3vtIpGpm30xo38Mlo0",
			"type": "freedraw",
			"x": 613.9079134450321,
			"y": -3398.294183816753,
			"width": 10.387662848377431,
			"height": 3.2461446401180183,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1958391773,
			"version": 10,
			"versionNonce": 818468627,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2984578560472073,
					-0.6492289280236037
				],
				[
					-3.895373568141622,
					-1.947686784070811
				],
				[
					-6.492289280236037,
					-2.5969157120944146
				],
				[
					-9.089204992330451,
					-3.2461446401180183
				],
				[
					-9.738433920354055,
					-3.2461446401180183
				],
				[
					-10.387662848377431,
					-3.2461446401180183
				],
				[
					-10.387662848377431,
					-3.2461446401180183
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-10.387662848377431,
				-3.2461446401180183
			]
		},
		{
			"id": "N3WXtI_a8l20aUoNmdBYp",
			"type": "freedraw",
			"x": 639.2278416379525,
			"y": -3418.4202805854848,
			"width": 0,
			"height": 29.215301761062165,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1468325693,
			"version": 12,
			"versionNonce": 1042421661,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.947686784070811
				],
				[
					0,
					4.544602496165226
				],
				[
					0,
					7.790747136283244
				],
				[
					0,
					12.984578560472073
				],
				[
					0,
					18.827638912684506
				],
				[
					0,
					24.021470336873335
				],
				[
					0,
					27.267614976991354
				],
				[
					0,
					29.215301761062165
				],
				[
					0,
					29.215301761062165
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				29.215301761062165
			]
		},
		{
			"id": "je-2ZLBinpiZUROXtDkqB",
			"type": "freedraw",
			"x": 377.58858364444285,
			"y": -3166.519456512329,
			"width": 41.55065139351018,
			"height": 27.2676149769909,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2100068189,
			"version": 48,
			"versionNonce": 1046641843,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.9476867840707541,
					-2.5969157120944146
				],
				[
					7.79074713628313,
					-4.544602496165226
				],
				[
					11.686120704424752,
					-6.492289280236037
				],
				[
					17.529181056637128,
					-7.790747136283244
				],
				[
					23.372241408849504,
					-7.790747136283244
				],
				[
					25.969157120943862,
					-7.790747136283244
				],
				[
					28.566072833038277,
					-7.790747136283244
				],
				[
					31.162988545132634,
					-6.492289280236037
				],
				[
					34.40913318525065,
					-3.2461446401180183
				],
				[
					38.30450675339222,
					0.6492289280236037
				],
				[
					39.602964609439425,
					4.544602496165226
				],
				[
					40.901422465486576,
					7.790747136282789
				],
				[
					41.55065139351018,
					10.387662848377204
				],
				[
					41.55065139351018,
					12.335349632448015
				],
				[
					40.901422465486576,
					12.984578560471618
				],
				[
					37.655277825368614,
					14.93226534454243
				],
				[
					30.51375961710903,
					16.230723200589637
				],
				[
					24.670699264896655,
					18.178409984660448
				],
				[
					20.126096768731486,
					18.82763891268405
				],
				[
					12.984578560471903,
					19.476867840707655
				],
				[
					9.089204992330338,
					19.476867840707655
				],
				[
					4.544602496165169,
					19.476867840707655
				],
				[
					1.9476867840707541,
					18.178409984660448
				],
				[
					1.2984578560472073,
					15.581494272566033
				],
				[
					1.2984578560472073,
					11.686120704424411
				],
				[
					2.596915712094358,
					7.790747136282789
				],
				[
					6.49228928023598,
					4.544602496165226
				],
				[
					9.089204992330338,
					4.544602496165226
				],
				[
					13.633807488495506,
					4.544602496165226
				],
				[
					15.581494272566317,
					4.544602496165226
				],
				[
					18.82763891268428,
					5.193831424188829
				],
				[
					23.372241408849504,
					7.14151820825964
				],
				[
					25.969157120943862,
					9.089204992329996
				],
				[
					27.916843905014673,
					11.036891776401262
				],
				[
					29.215301761061824,
					13.633807488495222
				],
				[
					30.51375961710903,
					13.633807488495222
				],
				[
					30.51375961710903,
					14.283036416518826
				],
				[
					31.162988545132634,
					14.93226534454243
				],
				[
					32.46144640117984,
					15.581494272566033
				],
				[
					33.110675329203445,
					15.581494272566033
				],
				[
					35.0583621132742,
					16.230723200589637
				],
				[
					37.00604889734501,
					16.87995212861324
				],
				[
					38.30450675339222,
					16.87995212861324
				],
				[
					40.25219353746297,
					18.178409984660448
				],
				[
					40.25219353746297,
					18.178409984660448
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				40.25219353746297,
				18.178409984660448
			]
		},
		{
			"id": "nQSF_htb_n5YFgmpdot1Z",
			"type": "freedraw",
			"x": 420.43769289400024,
			"y": -3206.122421121768,
			"width": 39.602964609439425,
			"height": 24.02147033687288,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 684726525,
			"version": 65,
			"versionNonce": 748100605,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.2461446401179614,
					-0.6492289280236037
				],
				[
					6.49228928023598,
					-1.2984578560472073
				],
				[
					9.738433920353941,
					-1.947686784070811
				],
				[
					11.036891776401148,
					-1.947686784070811
				],
				[
					12.98457856047196,
					-1.2984578560472073
				],
				[
					14.932265344542714,
					0.6492289280236037
				],
				[
					14.932265344542714,
					3.2461446401180183
				],
				[
					14.932265344542714,
					5.843060352212433
				],
				[
					14.932265344542714,
					9.089204992329996
				],
				[
					14.28303641651911,
					11.686120704424411
				],
				[
					12.335349632448356,
					13.633807488495222
				],
				[
					10.387662848377545,
					15.581494272566033
				],
				[
					8.439976064306734,
					16.87995212861324
				],
				[
					5.193831424188772,
					18.178409984660448
				],
				[
					3.2461446401179614,
					18.82763891268405
				],
				[
					0.6492289280236037,
					19.476867840707655
				],
				[
					-1.2984578560472073,
					20.12609676873126
				],
				[
					-2.5969157120944146,
					20.12609676873126
				],
				[
					-3.2461446401179614,
					20.12609676873126
				],
				[
					-3.895373568141565,
					20.12609676873126
				],
				[
					-5.843060352212376,
					20.12609676873126
				],
				[
					-6.49228928023598,
					19.476867840707655
				],
				[
					-7.790747136283187,
					18.82763891268405
				],
				[
					-8.439976064306734,
					17.529181056636844
				],
				[
					-9.738433920353941,
					16.230723200589637
				],
				[
					-10.387662848377545,
					16.230723200589637
				],
				[
					-11.036891776401148,
					15.581494272566033
				],
				[
					-11.036891776401148,
					13.633807488495222
				],
				[
					-10.387662848377545,
					12.984578560471618
				],
				[
					-9.738433920353941,
					11.686120704424411
				],
				[
					-8.439976064306734,
					11.036891776400807
				],
				[
					-6.49228928023598,
					9.7384339203536
				],
				[
					-4.544602496165169,
					7.790747136282789
				],
				[
					-2.5969157120944146,
					7.1415182082591855
				],
				[
					-1.2984578560472073,
					7.1415182082591855
				],
				[
					0.6492289280236037,
					7.1415182082591855
				],
				[
					2.5969157120944146,
					7.1415182082591855
				],
				[
					4.544602496165169,
					7.1415182082591855
				],
				[
					7.141518208259583,
					7.1415182082591855
				],
				[
					10.387662848377545,
					7.790747136282789
				],
				[
					12.335349632448356,
					7.790747136282789
				],
				[
					12.98457856047196,
					8.439976064306393
				],
				[
					13.633807488495563,
					9.7384339203536
				],
				[
					14.28303641651911,
					11.036891776400807
				],
				[
					14.932265344542714,
					12.335349632448015
				],
				[
					15.581494272566317,
					13.633807488495222
				],
				[
					15.581494272566317,
					14.93226534454243
				],
				[
					16.23072320058992,
					16.230723200589637
				],
				[
					16.879952128613525,
					16.87995212861324
				],
				[
					17.529181056637128,
					17.529181056636844
				],
				[
					18.827638912684336,
					18.82763891268405
				],
				[
					19.47686784070794,
					19.476867840707655
				],
				[
					20.126096768731486,
					20.12609676873126
				],
				[
					22.073783552802297,
					20.12609676873126
				],
				[
					22.7230124808259,
					20.775325696754862
				],
				[
					24.67069926489671,
					22.07378355280207
				],
				[
					25.31992819292026,
					22.07378355280207
				],
				[
					26.618386048967466,
					22.07378355280207
				],
				[
					27.26761497699107,
					22.07378355280207
				],
				[
					27.916843905014673,
					22.07378355280207
				],
				[
					28.566072833038277,
					22.07378355280207
				],
				[
					28.566072833038277,
					22.07378355280207
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				28.566072833038277,
				22.07378355280207
			]
		},
		{
			"id": "uH9uue0ZO0MPKC7uRNNyw",
			"type": "freedraw",
			"x": 467.8314046397228,
			"y": -3225.5992889624763,
			"width": 14.28303641651911,
			"height": 52.58754316991144,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1447538941,
			"version": 24,
			"versionNonce": 1626762835,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6492289280235468,
					0
				],
				[
					-1.9476867840707541,
					2.5969157120944146
				],
				[
					-5.193831424188772,
					9.738433920354055
				],
				[
					-7.1415182082595265,
					14.28303641651928
				],
				[
					-10.387662848377545,
					20.775325696754862
				],
				[
					-13.633807488495506,
					27.2676149769909
				],
				[
					-13.633807488495506,
					31.16298854513252
				],
				[
					-14.28303641651911,
					33.11067532920333
				],
				[
					-14.28303641651911,
					37.006048897344954
				],
				[
					-14.28303641651911,
					40.25219353746297
				],
				[
					-14.28303641651911,
					42.84910924955739
				],
				[
					-13.633807488495506,
					44.7967960336282
				],
				[
					-12.984578560471903,
					46.095253889675405
				],
				[
					-12.335349632448299,
					48.042940673746216
				],
				[
					-11.686120704424695,
					48.69216960176982
				],
				[
					-10.387662848377545,
					49.99062745781703
				],
				[
					-9.738433920353941,
					51.289085313864234
				],
				[
					-8.439976064306734,
					51.93831424188784
				],
				[
					-7.79074713628313,
					51.93831424188784
				],
				[
					-7.79074713628313,
					52.58754316991144
				],
				[
					-7.79074713628313,
					52.58754316991144
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-7.79074713628313,
				52.58754316991144
			]
		},
		{
			"id": "qHMoK9Fmum2kSQAJ69FxL",
			"type": "freedraw",
			"x": 487.30827248043073,
			"y": -3208.7193368338626,
			"width": 19.47686784070794,
			"height": 22.723012480825673,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1873003933,
			"version": 49,
			"versionNonce": 581735517,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.544602496165169,
					0
				],
				[
					6.49228928023598,
					0
				],
				[
					7.141518208259583,
					0
				],
				[
					9.738433920353941,
					1.2984578560472073
				],
				[
					10.387662848377545,
					3.2461446401180183
				],
				[
					11.686120704424752,
					5.1938314241883745
				],
				[
					11.686120704424752,
					8.439976064306848
				],
				[
					11.686120704424752,
					10.387662848377204
				],
				[
					11.036891776401148,
					12.984578560471618
				],
				[
					10.387662848377545,
					15.581494272566033
				],
				[
					8.439976064306734,
					18.178409984660448
				],
				[
					7.141518208259583,
					20.12609676873126
				],
				[
					5.843060352212376,
					20.775325696754862
				],
				[
					4.544602496165169,
					21.424554624778466
				],
				[
					3.2461446401179614,
					22.07378355280207
				],
				[
					1.2984578560472073,
					22.07378355280207
				],
				[
					0,
					22.07378355280207
				],
				[
					-1.2984578560472073,
					22.07378355280207
				],
				[
					-2.5969157120944146,
					22.07378355280207
				],
				[
					-3.895373568141565,
					22.07378355280207
				],
				[
					-4.544602496165169,
					22.07378355280207
				],
				[
					-5.193831424188772,
					21.424554624778466
				],
				[
					-7.141518208259583,
					20.12609676873126
				],
				[
					-7.141518208259583,
					18.82763891268405
				],
				[
					-7.141518208259583,
					18.178409984660448
				],
				[
					-7.141518208259583,
					16.230723200589637
				],
				[
					-7.141518208259583,
					14.93226534454243
				],
				[
					-6.49228928023598,
					14.283036416518826
				],
				[
					-5.193831424188772,
					12.984578560471618
				],
				[
					-2.5969157120944146,
					12.984578560471618
				],
				[
					-0.6492289280236037,
					12.984578560471618
				],
				[
					1.2984578560472073,
					12.984578560471618
				],
				[
					3.2461446401179614,
					12.984578560471618
				],
				[
					3.895373568141565,
					13.633807488495222
				],
				[
					5.843060352212376,
					14.93226534454243
				],
				[
					6.49228928023598,
					17.529181056636844
				],
				[
					7.141518208259583,
					19.476867840707655
				],
				[
					7.141518208259583,
					20.775325696754862
				],
				[
					7.141518208259583,
					22.07378355280207
				],
				[
					7.790747136283187,
					22.07378355280207
				],
				[
					7.790747136283187,
					22.723012480825673
				],
				[
					8.439976064306734,
					22.723012480825673
				],
				[
					10.387662848377545,
					22.723012480825673
				],
				[
					11.686120704424752,
					22.723012480825673
				],
				[
					12.335349632448356,
					22.723012480825673
				],
				[
					12.335349632448356,
					22.723012480825673
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				12.335349632448356,
				22.723012480825673
			]
		},
		{
			"id": "LUsaqAm4petHowjFOUAfF",
			"type": "freedraw",
			"x": 506.13591139311507,
			"y": -3230.793120386665,
			"width": 11.036891776401148,
			"height": 16.879952128613695,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 383235997,
			"version": 28,
			"versionNonce": 458959859,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.5969157120944146
				],
				[
					-0.6492289280236037,
					6.492289280236037
				],
				[
					-1.2984578560472073,
					9.738433920354055
				],
				[
					-1.947686784070811,
					12.984578560472073
				],
				[
					-2.5969157120944146,
					15.581494272566488
				],
				[
					-2.5969157120944146,
					16.23072320059009
				],
				[
					-2.5969157120944146,
					16.879952128613695
				],
				[
					-1.947686784070811,
					15.581494272566488
				],
				[
					-0.6492289280236037,
					13.633807488495677
				],
				[
					1.2984578560471505,
					11.686120704424866
				],
				[
					3.2461446401179614,
					7.790747136283244
				],
				[
					4.544602496165169,
					5.193831424188829
				],
				[
					5.843060352212376,
					3.2461446401180183
				],
				[
					6.492289280235923,
					1.947686784070811
				],
				[
					7.1415182082595265,
					1.2984578560472073
				],
				[
					7.79074713628313,
					1.2984578560472073
				],
				[
					8.439976064306734,
					1.947686784070811
				],
				[
					8.439976064306734,
					3.2461446401180183
				],
				[
					8.439976064306734,
					6.492289280236037
				],
				[
					8.439976064306734,
					8.439976064306848
				],
				[
					8.439976064306734,
					10.387662848377659
				],
				[
					8.439976064306734,
					11.686120704424866
				],
				[
					8.439976064306734,
					12.33534963244847
				],
				[
					8.439976064306734,
					12.984578560472073
				],
				[
					8.439976064306734,
					12.984578560472073
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				8.439976064306734,
				12.984578560472073
			]
		},
		{
			"id": "QfshUtDNxQwpbY4UNwwGh",
			"type": "freedraw",
			"x": 526.2620081618466,
			"y": -3222.3531443223583,
			"width": 3.895373568141622,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 835041725,
			"version": 10,
			"versionNonce": 1010041021,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6492289280236037,
					0
				],
				[
					-1.2984578560472073,
					0
				],
				[
					-1.947686784070811,
					0
				],
				[
					-2.5969157120944146,
					0
				],
				[
					-3.2461446401180183,
					0
				],
				[
					-3.895373568141622,
					0
				],
				[
					-3.895373568141622,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-3.895373568141622,
				0
			]
		},
		{
			"id": "gxBdzY-lu6Bf_cFQKWIUV",
			"type": "freedraw",
			"x": 536.0004420822005,
			"y": -3230.793120386665,
			"width": 0.6492289280236037,
			"height": 18.178409984660902,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1648348445,
			"version": 16,
			"versionNonce": 1368864147,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.6492289280236037
				],
				[
					0,
					0
				],
				[
					0,
					0.6492289280236037
				],
				[
					0,
					3.2461446401180183
				],
				[
					0,
					6.492289280236037
				],
				[
					-0.6492289280236037,
					7.790747136283244
				],
				[
					-0.6492289280236037,
					9.089204992330451
				],
				[
					-0.6492289280236037,
					12.33534963244847
				],
				[
					-0.6492289280236037,
					14.28303641651928
				],
				[
					-0.6492289280236037,
					15.581494272566488
				],
				[
					-0.6492289280236037,
					16.879952128613695
				],
				[
					-0.6492289280236037,
					17.5291810566373
				],
				[
					-0.6492289280236037,
					17.5291810566373
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-0.6492289280236037,
				17.5291810566373
			]
		},
		{
			"id": "ODMrvuQk7GyjNsK1IBCnn",
			"type": "freedraw",
			"x": 546.388104930578,
			"y": -3211.9654814739806,
			"width": 9.089204992330338,
			"height": 35.707591041297746,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1745015485,
			"version": 30,
			"versionNonce": 516874525,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6492289280236037,
					1.947686784070811
				],
				[
					1.947686784070811,
					4.544602496165226
				],
				[
					1.947686784070811,
					7.1415182082591855
				],
				[
					1.947686784070811,
					9.7384339203536
				],
				[
					1.947686784070811,
					11.036891776400807
				],
				[
					1.947686784070811,
					12.984578560471618
				],
				[
					1.947686784070811,
					14.93226534454243
				],
				[
					1.947686784070811,
					16.87995212861324
				],
				[
					1.947686784070811,
					18.82763891268405
				],
				[
					1.947686784070811,
					20.12609676873126
				],
				[
					1.2984578560472073,
					22.07378355280207
				],
				[
					1.2984578560472073,
					23.372241408849277
				],
				[
					0.6492289280236037,
					24.02147033687288
				],
				[
					0,
					25.319928192920088
				],
				[
					-0.6492289280236037,
					25.96915712094369
				],
				[
					-0.6492289280236037,
					26.618386048967295
				],
				[
					-1.947686784070811,
					27.916843905014503
				],
				[
					-2.5969157120944146,
					28.566072833038106
				],
				[
					-3.895373568141622,
					29.864530689085313
				],
				[
					-4.544602496165226,
					30.513759617108917
				],
				[
					-5.193831424188829,
					31.16298854513252
				],
				[
					-5.843060352212433,
					32.46144640117973
				],
				[
					-6.492289280236037,
					33.759904257226935
				],
				[
					-7.1415182082595265,
					34.40913318525054
				],
				[
					-7.1415182082595265,
					35.05836211327414
				],
				[
					-7.1415182082595265,
					35.707591041297746
				],
				[
					-7.1415182082595265,
					35.707591041297746
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-7.1415182082595265,
				35.707591041297746
			]
		},
		{
			"id": "LaZzoSGckS9oGlqrqQDoq",
			"type": "freedraw",
			"x": 312.6656908420831,
			"y": -3183.3994086409425,
			"width": 18.827638912684336,
			"height": 23.37224140884973,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2112419229,
			"version": 27,
			"versionNonce": 585173811,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.6492289280236037
				],
				[
					0,
					3.895373568141622
				],
				[
					0,
					7.14151820825964
				],
				[
					0,
					9.738433920354055
				],
				[
					0,
					12.984578560472073
				],
				[
					0,
					14.932265344542884
				],
				[
					0,
					18.178409984660902
				],
				[
					1.2984578560472073,
					15.581494272566488
				],
				[
					4.544602496165226,
					10.387662848377659
				],
				[
					7.141518208259583,
					5.843060352212433
				],
				[
					9.738433920353941,
					0.6492289280236037
				],
				[
					11.686120704424752,
					-1.947686784070811
				],
				[
					11.686120704424752,
					-3.2461446401180183
				],
				[
					14.283036416519167,
					-5.193831424188829
				],
				[
					16.230723200589978,
					-4.544602496165226
				],
				[
					16.87995212861358,
					-0.6492289280236037
				],
				[
					18.178409984660732,
					2.5969157120944146
				],
				[
					18.827638912684336,
					6.492289280236037
				],
				[
					18.827638912684336,
					9.738433920354055
				],
				[
					18.827638912684336,
					12.984578560472073
				],
				[
					18.827638912684336,
					14.932265344542884
				],
				[
					18.827638912684336,
					16.879952128613695
				],
				[
					18.827638912684336,
					18.178409984660902
				],
				[
					18.827638912684336,
					18.178409984660902
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				18.827638912684336,
				18.178409984660902
			]
		},
		{
			"id": "sIN7NvIW_uzJT8lm-ap6Q",
			"type": "freedraw",
			"x": 666.4954566149436,
			"y": -3184.6978664969897,
			"width": 24.021470336873108,
			"height": 51.93831424188784,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1111567197,
			"version": 35,
			"versionNonce": 1072608637,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.947686784070811,
					0
				],
				[
					2.5969157120944146,
					0.6492289280236037
				],
				[
					5.193831424188602,
					1.947686784070811
				],
				[
					7.7907471362830165,
					3.895373568141622
				],
				[
					10.387662848377431,
					6.492289280236037
				],
				[
					18.178409984660675,
					16.879952128613695
				],
				[
					18.82763891268428,
					22.723012480826128
				],
				[
					18.82763891268428,
					29.864530689085313
				],
				[
					18.82763891268428,
					37.006048897344954
				],
				[
					14.932265344542657,
					42.84910924955739
				],
				[
					11.686120704424638,
					46.74448281769901
				],
				[
					8.43997606430662,
					49.34139852979342
				],
				[
					5.8430603522122055,
					49.99062745781703
				],
				[
					2.5969157120944146,
					49.99062745781703
				],
				[
					-0.6492289280236037,
					49.99062745781703
				],
				[
					-2.5969157120944146,
					49.34139852979342
				],
				[
					-3.895373568141622,
					48.69216960176982
				],
				[
					-5.193831424188829,
					48.69216960176982
				],
				[
					-5.193831424188829,
					46.095253889675405
				],
				[
					-3.2461446401180183,
					41.55065139351018
				],
				[
					-0.6492289280236037,
					38.30450675339216
				],
				[
					1.2984578560472073,
					37.006048897344954
				],
				[
					2.5969157120944146,
					36.35681996932135
				],
				[
					4.544602496164998,
					37.65527782536856
				],
				[
					7.141518208259413,
					40.25219353746297
				],
				[
					8.43997606430662,
					43.49833817758099
				],
				[
					9.738433920353827,
					46.095253889675405
				],
				[
					10.387662848377431,
					48.042940673746216
				],
				[
					10.387662848377431,
					49.34139852979342
				],
				[
					11.036891776401035,
					51.289085313864234
				],
				[
					11.036891776401035,
					51.93831424188784
				],
				[
					11.036891776401035,
					51.93831424188784
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				11.036891776401035,
				51.93831424188784
			]
		},
		{
			"id": "bwaNRMUW9SXn87WS1wvQD",
			"type": "freedraw",
			"x": 711.2922526485718,
			"y": -3224.9500600344527,
			"width": 23.372241408849504,
			"height": 48.042940673746216,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2052654109,
			"version": 35,
			"versionNonce": 60763347,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.544602496164998,
					-0.6492289280236037
				],
				[
					5.193831424188602,
					-0.6492289280236037
				],
				[
					7.141518208259413,
					-0.6492289280236037
				],
				[
					10.387662848377431,
					0.6492289280236037
				],
				[
					14.932265344542657,
					5.843060352212433
				],
				[
					18.178409984660675,
					11.036891776401262
				],
				[
					22.073783552802297,
					16.879952128613695
				],
				[
					23.372241408849504,
					24.02147033687288
				],
				[
					23.372241408849504,
					29.21530176106171
				],
				[
					22.7230124808259,
					33.11067532920333
				],
				[
					21.424554624778693,
					37.65527782536856
				],
				[
					14.932265344542657,
					42.19988032153378
				],
				[
					10.387662848377431,
					43.49833817758099
				],
				[
					6.492289280235809,
					43.49833817758099
				],
				[
					3.2461446401180183,
					43.49833817758099
				],
				[
					0.6492289280236037,
					42.84910924955739
				],
				[
					0,
					42.84910924955739
				],
				[
					0,
					41.55065139351018
				],
				[
					1.947686784070811,
					36.35681996932135
				],
				[
					4.544602496164998,
					31.16298854513252
				],
				[
					6.492289280235809,
					26.618386048967295
				],
				[
					7.7907471362830165,
					24.67069926489694
				],
				[
					9.738433920353827,
					24.67069926489694
				],
				[
					11.036891776401035,
					24.67069926489694
				],
				[
					12.335349632448242,
					29.21530176106171
				],
				[
					13.63380748849545,
					32.46144640117973
				],
				[
					14.283036416519053,
					37.65527782536856
				],
				[
					14.932265344542657,
					41.55065139351018
				],
				[
					14.932265344542657,
					44.7967960336282
				],
				[
					14.932265344542657,
					46.74448281769901
				],
				[
					14.932265344542657,
					47.39371174572261
				],
				[
					14.932265344542657,
					47.39371174572261
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				14.932265344542657,
				47.39371174572261
			]
		},
		{
			"id": "uf-Mm67bz61d2D3Amb64v",
			"type": "freedraw",
			"x": 751.5444461860347,
			"y": -3272.993000708199,
			"width": 16.230723200589864,
			"height": 44.7967960336282,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 550415581,
			"version": 33,
			"versionNonce": 1792343517,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					3.2461446401180183
				],
				[
					0,
					11.036891776401262
				],
				[
					0,
					18.178409984660902
				],
				[
					0,
					27.2676149769909
				],
				[
					-0.6492289280236037,
					33.11067532920333
				],
				[
					-1.2984578560472073,
					37.65527782536856
				],
				[
					-2.5969157120944146,
					40.25219353746297
				],
				[
					-2.5969157120944146,
					40.901422465486576
				],
				[
					-2.5969157120944146,
					36.35681996932135
				],
				[
					-2.5969157120944146,
					34.40913318525054
				],
				[
					-2.5969157120944146,
					29.864530689085313
				],
				[
					-2.5969157120944146,
					25.319928192920543
				],
				[
					-1.947686784070811,
					22.723012480826128
				],
				[
					-1.2984578560472073,
					20.126096768731713
				],
				[
					-0.6492289280236037,
					18.827638912684506
				],
				[
					0,
					19.47686784070811
				],
				[
					1.2984578560472073,
					21.42455462477892
				],
				[
					2.5969157120944146,
					25.96915712094369
				],
				[
					4.544602496165226,
					29.21530176106171
				],
				[
					6.492289280236037,
					32.46144640117973
				],
				[
					7.7907471362830165,
					34.40913318525054
				],
				[
					8.43997606430662,
					37.006048897344954
				],
				[
					9.738433920353827,
					38.30450675339216
				],
				[
					10.387662848377431,
					39.60296460943937
				],
				[
					11.036891776401035,
					40.901422465486576
				],
				[
					11.686120704424638,
					42.84910924955739
				],
				[
					12.335349632448242,
					43.49833817758099
				],
				[
					12.984578560471846,
					44.147567105604594
				],
				[
					13.63380748849545,
					44.7967960336282
				],
				[
					13.63380748849545,
					44.7967960336282
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				13.63380748849545,
				44.7967960336282
			]
		},
		{
			"id": "p-oY6ZXSbmDGR2JNVNZ5z",
			"type": "freedraw",
			"x": 610.0125398768905,
			"y": -3178.2055772167537,
			"width": 12.33534963244847,
			"height": 21.42455462477892,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 318437597,
			"version": 29,
			"versionNonce": 392698483,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708956257484,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.2984578560472073
				],
				[
					0,
					3.2461446401180183
				],
				[
					0,
					8.439976064306848
				],
				[
					0,
					11.686120704424866
				],
				[
					0,
					15.581494272566488
				],
				[
					0,
					18.178409984660448
				],
				[
					0,
					20.126096768731713
				],
				[
					0,
					21.42455462477892
				],
				[
					0.6492289280236037,
					21.42455462477892
				],
				[
					1.947686784070811,
					20.126096768731713
				],
				[
					2.5969157120944146,
					16.879952128613695
				],
				[
					3.895373568141622,
					14.28303641651928
				],
				[
					5.193831424188829,
					11.036891776401262
				],
				[
					5.843060352212433,
					7.790747136283244
				],
				[
					6.492289280236037,
					5.843060352212433
				],
				[
					7.14151820825964,
					4.544602496165226
				],
				[
					7.790747136283244,
					3.895373568141622
				],
				[
					8.439976064306848,
					3.2461446401180183
				],
				[
					10.387662848377659,
					6.492289280236037
				],
				[
					11.036891776401262,
					9.738433920354055
				],
				[
					11.686120704424866,
					12.33534963244847
				],
				[
					11.686120704424866,
					14.28303641651928
				],
				[
					11.686120704424866,
					14.932265344542884
				],
				[
					11.686120704424866,
					16.23072320059009
				],
				[
					12.33534963244847,
					17.5291810566373
				],
				[
					12.33534963244847,
					17.5291810566373
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				12.33534963244847,
				17.5291810566373
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 0.5,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -413.62078914975257,
		"scrollY": 4043.292979606196,
		"zoom": {
			"value": 1.5402887284216236
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