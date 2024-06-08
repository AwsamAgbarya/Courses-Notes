---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Kernel Methods ^3QRO1NIq

ಠ_ಠ ^ZHgWoVSf

Yay, well if it isnt
my favorite
subject ever!!! ^CCrmPibG

Kernelize ^zGi3Q6BV

Models ^64ZDd2LS

If you get this reference i love you ^1gGBGVFN

What's a kernel? ^T3d3qqYT

Corn???? ^LqGeU9LN

a function ^o220c8NR

core
computer
program ^Dl2VnI3c

A way
to measure
similarities
through dot
products ^A1NK2yD6

unmarked
linguistic
string??? ^AGy2ffPD

Recap: ^g075AjVH

Linear models are quite common in Machine learning
Linear models are good in theory but are too simply to
apply to complex models.
a fix to the linearity limitation is to apply this method
into higher dimensions, higher dimensions usually include a solution in
the manifold that would otherwise be non-linear in the dimension of
the manifold.








Computing things in higher dimensions is quite expensive, linear methods usually
need to compute dot products (similarity measures) in "infinite" dimensions



Some dot products are expressed more compactly using general nonlinear functions.
The kernel trick revolves around computing the result of the infinite dimension
dot product without doing the mapping to higher dimensions.

This is done by a Mercer kernel which is a PSD symmetric kernel according to mercers
theorem ^Vb7R3Pfx

examples ^N8QwNYEv

Types of Non-Numeric
Kernels ^J4OHqto5

String Kernels ^NPtkpBLj

Notation ^RuiSDikI

- an Alphabet is a finite set of discrete symbols

- a Natural language involves letters and numbers

- a string is a concatenation of symbols from an alphabet

- A^L = all strings of length L from alphabet A

- A^* = all strings of any length from alphabet A  ^huuhS9Jf

Approach 1:
Count the number of matching symbols
Problem 1:
Doesnt take into account a slight shift in the position ^rdec9J5h

We are gonna start with simple
ideas on how to compare
two strings and build upon them
according to the situation ^yZdX2QYJ

Approach 2:
Count the number of matching symbols with some shift tolerance.
Problem 2:
Order matters, not occurances ^xqd16O5J

Approach 3:
Count the number of matching symbols between sequences.
with full shift invariance.
Problem 3:
only individual letters are counted, not sequences ^Sfm78HF9

different
weights ^WH8HD2FS

Approach 4:
Count the number of matching subsequences of symbols.
Can be generalized to triplets of consecutive of symbols,
or more generally, ‘n-grams’ ^2jMOmATY

build sorted lists before performing the kernel evaluations to reduce computation ^OZcKqdB6

Tree Kernels ^eAqAtVXi

Notation ^DZF3LEEf

- A tree is an acyclic graph rooted at node V

- a parse tree is a tree derived from a grammar with
  some production rules.

- Vi is the ith child of node V
- |v| is the number of children of node v
- T is the set of all possible trees
 ^goSW2zUl

Lets give an example of a
sentence tree derived from
a grammar ^Ii80uBC2

a Tree kernel is given by ^beE1N8Z3

number of
occurances of 
subtree t in
z ^35SvLz5z

By definition k is an inner product in the space of all trees T
and thus symmetric and PSD
parse trees count the number of of shared subtrees ^BHJwkCLr

We can define this counting function recursively ^m2oW2eP2

We can use dynamic programming to implement an efficient
way of recursively doing this ^kxCZSFRV

Model Induced
Kernels ^HnhYxi8a

Certain machine learning models already
exist for structured data for example markov models and GNN ^W0qtWmSa

Idea:
Do not build a new kernel directly on the input data, extract a
kernel from local response of the existing model ^38WHDc2l

Suppose x ∈ X and we have some generative model for the data
The Fisher Kernel is built as follows. It computes the gradient
of the locally evaluated function w.r.t. the model parameters. ^eTMk9a8c

Normalization term to not
allow the matrix to blow up.
the middle term is basically an
expectation over the covariance
matrix of the Gradients ^Akh5mwMr

For example:
Fisher Kernel ^kapWlQmJ

Diffusion Kernels ^muQyW96m

Diffusion kernels assume that the input domain is discrete
and that the local geometry is given by a graph
the diffusion kernel defines the generator matrix which is
basically the graph laplacian in a way. ^DhQa3WFn

then diffuses the graph signal by matrix exponentiation. Kernel ^p1g48QWI

scores are then given by: ^g1xA1k8K

hyperparameter ^y2JZ7f0l

the diffusion kernel is particularly useful for semi-supervised ^8rxyNbQC

learning, or for unsupervised analyses such as clustering ^H8UAm5cw

# Embedded files
f7fe35e37ab3555dce1ad9beb576fd97260254b2: [[Pasted Image 20240504112755_405.png]]
4554cac0978000ab78fc40d8dc4db584d7a895e6: [[Pasted Image 20240531130329_523.png]]
b54deb6ffdb6b4aae6267f7f2671c3619adb55d7: [[Pasted Image 20240531202059_088.png]]
3e4a40b4175452c6cda2f57ad2ffa7aae6854bdd: [[Pasted Image 20240531202145_113.png]]
579a6291ddb3e4cea778b75aa77faa24a59d91f7: [[Pasted Image 20240531202201_116.png]]
8ba6805c0a283966ac85433a77e38c99df6fad6a: [[Pasted Image 20240531202246_121.png]]
6e627461cfb1d40495af35c318eb94ac14ac6f53: [[Pasted Image 20240531202340_137.png]]
8daa979fc9d2dd99a1047c56c17da18ad49bbaf0: [[Pasted Image 20240531203521_962.png]]
bc12ccfbb35a2fb7e055fc527a30e46e66291a14: [[Pasted Image 20240531203717_297.png]]
e758f3f801be46b6a280cb533c5fa05313eab168: [[Pasted Image 20240531204023_339.png]]
12f14a85ee122ca320154f1539367d881d627325: [[Pasted Image 20240531204038_349.png]]
99e975181af75b683274be932478bd59b43b9dfd: [[Pasted Image 20240531204413_271.png]]
92f8c69ff949d7e89ec45531a03892db40c3e720: [[Pasted Image 20240531204424_407.png]]
49ce4ade3aee7bb1c9b6af51e34e8772337aeff9: [[Pasted Image 20240531205357_420.png]]
255c620ae734545bed7478fe514b6edc6dbf57b4: [[Pasted Image 20240531205412_431.png]]
64be02c1293114e088cc44da245f4864e6b72947: [[Pasted Image 20240531205544_437.png]]
34ca0d55460886c6e4fe7a6aa7490f1ce5eabc73: [[Pasted Image 20240531210157_478.png]]
dd5c3e16ab4f6724f9cdb69ee3e531d838c58c00: [[Pasted Image 20240531210258_490.png]]
1b7549281e8a5b1a120a61be3c4cad75f7129c89: [[Pasted Image 20240531210413_497.png]]
9dbda5becac35c03e9c6e3660a87b5fc725391db: [[Pasted Image 20240531210629_535.png]]
945d242e9b77af91560b93fe3193246d53f370e9: [[Pasted Image 20240531210644_547.png]]
a89aed78227e8aecf1712c0bf412d74db309d7b1: [[Pasted Image 20240531210857_567.png]]
9452fd1182789a4c99782f0110fc8779d5cde828: [[Pasted Image 20240531210903_266.png]]
0b9c99f928e2b988332c1f85caf6524e41bd489e: [[Pasted Image 20240531211240_680.png]]
85f30984f13860b79c696322259edde743461d69: [[Pasted Image 20240531211305_853.png]]
628de99bb72de7ba8f5deaf0073e41ac44314b26: [[Pasted Image 20240531211417_706.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "freedraw",
			"version": 386,
			"versionNonce": 962639728,
			"isDeleted": false,
			"id": "X1gdZh-kJ4Y8b_A9at7-a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 50,
			"angle": 0,
			"x": -72.21123090588202,
			"y": -614.2237575445922,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 137.96033016884422,
			"height": 167.52325806216803,
			"seed": 415955312,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
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
					-77.31842679792369,
					24.256761348368247
				],
				[
					-137.96033016884422,
					109.91344985979352
				],
				[
					-131.89613983175218,
					167.52325806216803
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
			"version": 373,
			"versionNonce": 331134864,
			"isDeleted": false,
			"id": "9hIvF8h_nZYQoikGI6GYr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 50,
			"angle": 0,
			"x": 60.44293271800677,
			"y": -602.095376870408,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.18499634866635,
			"height": 175.86151977566962,
			"seed": 1320719760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
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
					62.91597474733005,
					9.096285505638091
				],
				[
					95.5109978091998,
					77.31842679792369
				],
				[
					159.18499634866635,
					90.20483126424433
				],
				[
					131.13811603961557,
					162.21709151721248
				],
				[
					154.6368535958473,
					175.86151977566962
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 399,
			"versionNonce": 490228080,
			"isDeleted": false,
			"id": "NI85uj6dQIk2N4J5OK_9U",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 50,
			"angle": 0,
			"x": 25.573838279727397,
			"y": -605.1274720389541,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.54309297774591,
			"height": 180.40831508307363,
			"seed": 1561392016,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
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
					31.07897547759681,
					20.346802452978245
				],
				[
					17.434547219139674,
					48.154099138715104
				],
				[
					98.54309297774591,
					47.475872390282504
				],
				[
					53.81968924169196,
					119.3679077241389
				],
				[
					51.54561786528244,
					180.40831508307363
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 372,
			"versionNonce": 677332368,
			"isDeleted": false,
			"id": "fnujjo6L_SbxowGAT7UU6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 50,
			"angle": 0,
			"x": -17.63351787205346,
			"y": -604.3694482468177,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.57771303382847,
			"height": 175.1034959835331,
			"seed": 2008360336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
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
					17.434547219139596,
					38.65921339896188
				],
				[
					-2.274071376409523,
					102.33321193842843
				],
				[
					-37.14316581468888,
					122.79985432611414
				],
				[
					9.096285505638011,
					175.1034959835331
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
			"version": 373,
			"versionNonce": 72194928,
			"isDeleted": false,
			"id": "kjMkAN-DB42kjS_rU8tm_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 50,
			"angle": 0,
			"x": -38.858184051875696,
			"y": -609.6756147917731,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 109.91344985979352,
			"height": 162.21709151721248,
			"seed": 555174288,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
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
					-61.399927163057036,
					22.74071376409523
				],
				[
					-31.07897547759681,
					62.915974747330054
				],
				[
					-109.91344985979352,
					107.639378483384
				],
				[
					-95.51099780919988,
					162.21709151721248
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
			"type": "image",
			"version": 341,
			"versionNonce": 1702892432,
			"isDeleted": false,
			"id": "BfOBAb3UGBzouZ3eHwJ-a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -274.8185101441274,
			"y": -870.3975546722857,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 585.7200069183716,
			"height": 251.95372361878037,
			"seed": 824660848,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772846,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4554cac0978000ab78fc40d8dc4db584d7a895e6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 3304,
			"versionNonce": 1088990576,
			"isDeleted": false,
			"id": "56XEnQw3-cF7q0SLviq7T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -379.6600670525595,
			"y": -580.5460828389743,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 40.69307340252653,
			"height": 37.454089191256976,
			"seed": 1486814576,
			"groupIds": [
				"_ilhBxmkSgDPuX7ktRZvY",
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772846,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3368,
			"versionNonce": 559358352,
			"isDeleted": false,
			"id": "mt4SP6uWPFv9vUe5kcBxC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -361.6984831506916,
			"y": -543.299577865687,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 1.9967385020061825,
			"height": 45.40674807233881,
			"seed": 146657136,
			"groupIds": [
				"_ilhBxmkSgDPuX7ktRZvY",
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.9967385020061825,
					45.40674807233881
				]
			]
		},
		{
			"type": "line",
			"version": 3321,
			"versionNonce": 475103088,
			"isDeleted": false,
			"id": "NHZ2IcnUWfq_uUcoL85Pt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -363.0076406137755,
			"y": -496.7299220703095,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 17.974457087715848,
			"height": 27.69140972152448,
			"seed": 825385328,
			"groupIds": [
				"_ilhBxmkSgDPuX7ktRZvY",
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772846,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.974457087715848,
					27.69140972152448
				]
			]
		},
		{
			"type": "line",
			"version": 3298,
			"versionNonce": 723283856,
			"isDeleted": false,
			"id": "tJl7qvXZ2wIXs8k-RDosd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -365.3919423751779,
			"y": -498.5227064290814,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 15.379459149039883,
			"height": 25.725155776800865,
			"seed": 1095021424,
			"groupIds": [
				"_ilhBxmkSgDPuX7ktRZvY",
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.379459149039883,
					25.725155776800865
				]
			]
		},
		{
			"type": "line",
			"version": 3359,
			"versionNonce": 1993347440,
			"isDeleted": false,
			"id": "OGeXGneyaQc7DbAGdUtMI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -386.0603420365883,
			"y": -517.4975506956316,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 23.764502950150945,
			"height": 15.221041150303197,
			"seed": 2134689136,
			"groupIds": [
				"_ilhBxmkSgDPuX7ktRZvY",
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.764502950150945,
					-15.221041150303197
				]
			]
		},
		{
			"type": "line",
			"version": 3402,
			"versionNonce": 721943952,
			"isDeleted": false,
			"id": "iHqicjC0OdlBxwdnFUVDz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -364.03644262747804,
			"y": -533.5914122265253,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 17.0005270816818,
			"height": 20.256957849888803,
			"seed": 677549936,
			"groupIds": [
				"_ilhBxmkSgDPuX7ktRZvY",
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.0005270816818,
					20.256957849888803
				]
			]
		},
		{
			"type": "text",
			"version": 1102,
			"versionNonce": 1739350896,
			"isDeleted": false,
			"id": "ZHgWoVSf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.02568439773626,
			"y": -562.9839809553441,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 28.03607177734375,
			"height": 19.079220341604938,
			"seed": 285092208,
			"groupIds": [
				"5PNoSMaylTtnWSu-ofrVP",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 13.467684947015261,
			"fontFamily": 1,
			"text": "ಠ_ಠ",
			"rawText": "ಠ_ಠ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ಠ_ಠ",
			"lineHeight": 1.4166666666666656
		},
		{
			"type": "text",
			"version": 485,
			"versionNonce": 38914960,
			"isDeleted": false,
			"id": "CCrmPibG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -320.54707982097716,
			"y": -610.8698370170824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.81564331054688,
			"height": 32.4827038041209,
			"seed": 775459216,
			"groupIds": [
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 8.662054347765574,
			"fontFamily": 1,
			"text": "Yay, well if it isnt\nmy favorite\nsubject ever!!!",
			"rawText": "Yay, well if it isnt\nmy favorite\nsubject ever!!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Yay, well if it isnt\nmy favorite\nsubject ever!!!",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1924,
			"versionNonce": 1563325808,
			"isDeleted": false,
			"id": "_Ci9-lkcZx7CqIOkd_MGI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -314.479609301819,
			"y": -573.2420856888174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.52225015771747,
			"height": 72.65072691374422,
			"seed": 439979408,
			"groupIds": [
				"ovG-_99bIzWnSD-sBwZUI",
				"7sXgsGE07s3tgKhc9nJDS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.914888284057469,
					7.892683683037656
				],
				[
					-18.04721286772608,
					14.549163897647745
				],
				[
					-12.937459826863876,
					2.187129213371877
				],
				[
					-9.132324583668627,
					-5.705554469665783
				],
				[
					-19.569266965004186,
					-9.604350023937378
				],
				[
					-23.70055665761617,
					-19.77925549484134
				],
				[
					-19.895421414420927,
					-31.1903644341729
				],
				[
					-7.610270486390527,
					-37.18119662732198
				],
				[
					-4.131289692612,
					-47.73647239620367
				],
				[
					5.7620619396956725,
					-54.678230334297055
				],
				[
					21.09132106228227,
					-53.82239716384715
				],
				[
					32.94159939109042,
					-58.10156301609648
				],
				[
					45.552904768537594,
					-57.721192718118765
				],
				[
					57.077028647928906,
					-52.681286269914004
				],
				[
					66.7529439806254,
					-40.319251585638135
				],
				[
					78.1683497102112,
					-36.80082632934426
				],
				[
					83.82169350010129,
					-27.291568879901305
				],
				[
					81.75604865379532,
					-14.834441621131004
				],
				[
					70.77551552343182,
					-7.892683683037617
				],
				[
					65.33960803315289,
					2.0920366388774427
				],
				[
					50.4452215097886,
					7.987776257532087
				],
				[
					35.00724423739645,
					3.328240107305043
				],
				[
					25.113892605088775,
					9.22397972595969
				],
				[
					10.002069782113336,
					8.748516853487537
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 806,
			"versionNonce": 724687248,
			"isDeleted": false,
			"id": "v6UeOO4itnW0ZaK2MKyUW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 287.18355783286995,
			"y": -577.5604088443174,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 157.1456151593566,
			"height": 123.644242257252,
			"seed": 2120362384,
			"groupIds": [
				"A-7MihLH8e_3qB0F_Z3Pr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f7fe35e37ab3555dce1ad9beb576fd97260254b2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 332,
			"versionNonce": 1017005936,
			"isDeleted": false,
			"id": "Oi_ljy42PgWxT1FI2ije4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 310.5264563855226,
			"y": -566.9037366492834,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 77.43345995656509,
			"height": 1.4973320986075667,
			"seed": 230732176,
			"groupIds": [
				"A-7MihLH8e_3qB0F_Z3Pr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					77.43345995656509,
					1.4973320986075667
				]
			]
		},
		{
			"type": "text",
			"version": 421,
			"versionNonce": 417343376,
			"isDeleted": false,
			"id": "zGi3Q6BV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 315.45211292238037,
			"y": -589.6483557248927,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 55.584381103515625,
			"height": 16.52894697014373,
			"seed": 210466160,
			"groupIds": [
				"A-7MihLH8e_3qB0F_Z3Pr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 13.223157576114984,
			"fontFamily": 1,
			"text": "Kernelize",
			"rawText": "Kernelize",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernelize",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 356,
			"versionNonce": 38001008,
			"isDeleted": false,
			"id": "IdYUo_gYfZ5LonDhPMcg5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 335.6677024613073,
			"y": -549.7148974898502,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 77.43345995656509,
			"height": 1.4973320986075667,
			"seed": 90417520,
			"groupIds": [
				"A-7MihLH8e_3qB0F_Z3Pr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					77.43345995656509,
					1.4973320986075667
				]
			]
		},
		{
			"type": "text",
			"version": 583,
			"versionNonce": 395621776,
			"isDeleted": false,
			"id": "64ZDd2LS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 354.1645046161194,
			"y": -546.2634539736797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.05580139160156,
			"height": 15.06934397994376,
			"seed": 505593200,
			"groupIds": [
				"A-7MihLH8e_3qB0F_Z3Pr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 12.055475183955007,
			"fontFamily": 1,
			"text": "Models",
			"rawText": "Models",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Models",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 469,
			"versionNonce": 1634151280,
			"isDeleted": false,
			"id": "1gGBGVFN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 305.2601127556127,
			"y": -454.8704185233645,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 134.00277709960938,
			"height": 9.441430883185124,
			"seed": 602661264,
			"groupIds": [
				"A-7MihLH8e_3qB0F_Z3Pr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 7.553144706548099,
			"fontFamily": 1,
			"text": "If you get this reference i love you",
			"rawText": "If you get this reference i love you",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If you get this reference i love you",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 747078544,
			"isDeleted": false,
			"id": "T3d3qqYT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -54.8425731049727,
			"y": -637.537116399888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.76762390136719,
			"height": 17.308944336071924,
			"seed": 1795485584,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 13.847155468857538,
			"fontFamily": 1,
			"text": "What's a kernel?",
			"rawText": "What's a kernel?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What's a kernel?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 1682980208,
			"isDeleted": false,
			"id": "LqGeU9LN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 194.1253200631271,
			"y": -425.6260088058888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.88873291015625,
			"height": 12.914046267847898,
			"seed": 360830832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 10.331237014278319,
			"fontFamily": 1,
			"text": "Corn????",
			"rawText": "Corn????",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Corn????",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 1978700176,
			"isDeleted": false,
			"id": "o220c8NR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 51.6700944918685,
			"y": -421.3640132775836,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 57.75514221191406,
			"height": 14.4718530041619,
			"seed": 864056176,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 11.57748240332952,
			"fontFamily": 1,
			"text": "a function",
			"rawText": "a function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a function",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 205983600,
			"isDeleted": false,
			"id": "Dl2VnI3c",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -247.29111225847385,
			"y": -458.6753563506058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 51.90650939941406,
			"height": 45.401683559166514,
			"seed": 1847897968,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 12.107115615777738,
			"fontFamily": 1,
			"text": "core\ncomputer\nprogram",
			"rawText": "core\ncomputer\nprogram",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "core\ncomputer\nprogram",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 185065360,
			"isDeleted": false,
			"id": "A1NK2yD6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.1421796212601,
			"y": -447.7943566001908,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 57.39704895019531,
			"height": 61.93868719927749,
			"seed": 766141808,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 9.910189951884398,
			"fontFamily": 1,
			"text": "A way\nto measure\nsimilarities\nthrough dot\nproducts",
			"rawText": "A way\nto measure\nsimilarities\nthrough dot\nproducts",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A way\nto measure\nsimilarities\nthrough dot\nproducts",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 1905500528,
			"isDeleted": false,
			"id": "AGy2ffPD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -39.23866731121166,
			"y": -427.24177742435313,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 47.02392578125,
			"height": 40.3908706117935,
			"seed": 1637830032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 10.770898829811602,
			"fontFamily": 1,
			"text": "unmarked\nlinguistic\nstring???",
			"rawText": "unmarked\nlinguistic\nstring???",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "unmarked\nlinguistic\nstring???",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 221,
			"versionNonce": 1543859600,
			"isDeleted": false,
			"id": "ddCUemZRMLUSaCSjRtkSW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.87689947882862,
			"y": -574.5197380124961,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 130.60903002672393,
			"height": 51.3505588139256,
			"seed": 1467480432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 239,
			"versionNonce": 1669198704,
			"isDeleted": false,
			"id": "9Vt-O58Ah0Cz2Z_iPuTic",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -30.011812228397844,
			"y": -575.0778962604736,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 175.26168986492013,
			"height": 51.35055881392568,
			"seed": 1496160144,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 253,
			"versionNonce": 304167824,
			"isDeleted": false,
			"id": "3QRO1NIq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -159.3408099488257,
			"y": -572.346221237787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 300.0184631347656,
			"height": 50.650908306829734,
			"seed": 1795976560,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 40.52072664546379,
			"fontFamily": 1,
			"text": "Kernel Methods",
			"rawText": "Kernel Methods",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernel Methods",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1253,
			"versionNonce": 139330928,
			"isDeleted": false,
			"id": "Vb7R3Pfx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 446.42539480922983,
			"y": -246.40722698915513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 846.119140625,
			"height": 650,
			"seed": 672671088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Linear models are quite common in Machine learning\nLinear models are good in theory but are too simply to\napply to complex models.\na fix to the linearity limitation is to apply this method\ninto higher dimensions, higher dimensions usually include a solution in\nthe manifold that would otherwise be non-linear in the dimension of\nthe manifold.\n\n\n\n\n\n\n\n\nComputing things in higher dimensions is quite expensive, linear methods usually\nneed to compute dot products (similarity measures) in \"infinite\" dimensions\n\n\n\nSome dot products are expressed more compactly using general nonlinear functions.\nThe kernel trick revolves around computing the result of the infinite dimension\ndot product without doing the mapping to higher dimensions.\n\nThis is done by a Mercer kernel which is a PSD symmetric kernel according to mercers\ntheorem",
			"rawText": "Linear models are quite common in Machine learning\nLinear models are good in theory but are too simply to\napply to complex models.\na fix to the linearity limitation is to apply this method\ninto higher dimensions, higher dimensions usually include a solution in\nthe manifold that would otherwise be non-linear in the dimension of\nthe manifold.\n\n\n\n\n\n\n\n\nComputing things in higher dimensions is quite expensive, linear methods usually\nneed to compute dot products (similarity measures) in \"infinite\" dimensions\n\n\n\nSome dot products are expressed more compactly using general nonlinear functions.\nThe kernel trick revolves around computing the result of the infinite dimension\ndot product without doing the mapping to higher dimensions.\n\nThis is done by a Mercer kernel which is a PSD symmetric kernel according to mercers\ntheorem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear models are quite common in Machine learning\nLinear models are good in theory but are too simply to\napply to complex models.\na fix to the linearity limitation is to apply this method\ninto higher dimensions, higher dimensions usually include a solution in\nthe manifold that would otherwise be non-linear in the dimension of\nthe manifold.\n\n\n\n\n\n\n\n\nComputing things in higher dimensions is quite expensive, linear methods usually\nneed to compute dot products (similarity measures) in \"infinite\" dimensions\n\n\n\nSome dot products are expressed more compactly using general nonlinear functions.\nThe kernel trick revolves around computing the result of the infinite dimension\ndot product without doing the mapping to higher dimensions.\n\nThis is done by a Mercer kernel which is a PSD symmetric kernel according to mercers\ntheorem",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 353,
			"versionNonce": 1871923600,
			"isDeleted": false,
			"id": "zTIGkK1O4Vry2zbRrJSgk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 659.5176539520604,
			"y": -18.43584993289818,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 426.84291704839916,
			"height": 135.8439236784297,
			"seed": 1350095728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b54deb6ffdb6b4aae6267f7f2671c3619adb55d7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 292,
			"versionNonce": 2102122352,
			"isDeleted": false,
			"id": "n_Km-lSKv5xGC8Yb3tn4G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 802.9112486930829,
			"y": -63.90472587241983,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 133.14743464666256,
			"height": 36.04865042835405,
			"seed": 1312512912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e4a40b4175452c6cda2f57ad2ffa7aae6854bdd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 341,
			"versionNonce": 798201744,
			"isDeleted": false,
			"id": "WqGMQf7Wkdp5Jy1OgAu6m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 767.0466149723569,
			"y": 197.58457585160693,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 211.78499514900446,
			"height": 31.301555886802547,
			"seed": 455381904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "579a6291ddb3e4cea778b75aa77faa24a59d91f7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 290,
			"versionNonce": 1992255856,
			"isDeleted": false,
			"id": "gWkjsum6xlTUGBiIhR2B-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 761.5042187024505,
			"y": 403.5927729271298,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 215.96149425041165,
			"height": 72.23036463104984,
			"seed": 1984686480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8ba6805c0a283966ac85433a77e38c99df6fad6a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 314,
			"versionNonce": 1717183888,
			"isDeleted": false,
			"id": "nvkf4v6banrd7S4YITWQa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 641.7692998171074,
			"y": 485.38067549275365,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 462.3396256669588,
			"height": 122.71977718320511,
			"seed": 882877328,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6e627461cfb1d40495af35c318eb94ac14ac6f53",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 206,
			"versionNonce": 1609612144,
			"isDeleted": false,
			"id": "Bho1YuWfNdBdXDmoA4_rx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 428.14597316857953,
			"y": -263.1683533439566,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 874.9051434712972,
			"height": 893.8905434949543,
			"seed": 1144693136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 396,
			"versionNonce": 1629418384,
			"isDeleted": false,
			"id": "-dLFjfJlkLsVX0Bj-mrJ2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -33.03609060201066,
			"y": -206.97164889228233,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 109.80885562833836,
			"height": 43.92354225133537,
			"seed": 1776757136,
			"groupIds": [
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-86.33247959745219,
					-14.388746599575368
				],
				[
					-107.5369482705107,
					10.602234336529209
				],
				[
					-83.30326978701531,
					29.534795651760003
				],
				[
					2.2719073578276676,
					21.961771125667685
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 352,
			"versionNonce": 2066206064,
			"isDeleted": false,
			"id": "TELfGTxu1ZGAnv7jRLCM5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.141952716974436,
			"x": -28.338416084380555,
			"y": -113.94631574693318,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 179.48068126838757,
			"height": 62.09880111395689,
			"seed": 368200560,
			"groupIds": [
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-146.15937335358143,
					-3.029209810436936
				],
				[
					-179.48068126838757,
					32.56400546219689
				],
				[
					-137.82904637487988,
					59.06959130351996
				],
				[
					-0.7573024526092225,
					34.07861036741534
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 368,
			"versionNonce": 102367632,
			"isDeleted": false,
			"id": "IJ68bPtpoQAhLY0S-j2y5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -20.55856395291258,
			"y": -176.69105632446076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 146.91667580619054,
			"height": 64.37070847178451,
			"seed": 2028835184,
			"groupIds": [
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					116.62457770182135,
					16.660653957403035
				],
				[
					144.64476844836287,
					40.13702998828921
				],
				[
					109.80885562833835,
					64.37070847178451
				],
				[
					-2.271907357827667,
					35.59321527263378
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 647,
			"versionNonce": 28090224,
			"isDeleted": false,
			"id": "bMnAtimfBx4v0U0LAxa4t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 16.85353752072575,
			"y": 167.93839563056116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 78.24006394961907,
			"height": 57.17543134779862,
			"seed": 814121872,
			"groupIds": [
				"NhivmUTeJBTgeao_snSVM",
				"3oVuhyrq80XOQS8kvCdnY",
				"DCY2LQ9QnSv57sS2UFw-0",
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.516927586191073,
					34.60618213156229
				],
				[
					-51.15696489013565,
					40.62464858922531
				],
				[
					-78.24006394961907,
					28.086176802427364
				],
				[
					-76.23390846373137,
					-1.5046166144157096
				],
				[
					-53.16312037602326,
					-16.550782758573312
				],
				[
					-16.049243887101362,
					-13.040010658269898
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 487,
			"versionNonce": 881020816,
			"isDeleted": false,
			"id": "_YSYCQ5XlF67aZWqRsesN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -62.389604171837334,
			"y": 147.8768407716845,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 79.74468056403497,
			"height": 47.14465391836024,
			"seed": 1327954320,
			"groupIds": [
				"NhivmUTeJBTgeao_snSVM",
				"3oVuhyrq80XOQS8kvCdnY",
				"DCY2LQ9QnSv57sS2UFw-0",
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 801,
			"versionNonce": 1137127792,
			"isDeleted": false,
			"id": "rzrPBm8kuxWfeG9CiWR4_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -15.918246695520821,
			"y": 122.53846492466221,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 23.063354595940528,
			"height": 433.2292882923734,
			"seed": 1826489232,
			"groupIds": [
				"3oVuhyrq80XOQS8kvCdnY",
				"DCY2LQ9QnSv57sS2UFw-0",
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.7133358348165135,
					43.865595996200646
				],
				[
					-20.350018761124012,
					5.8788943087691825
				],
				[
					-15.37556973062705,
					-298.4669418298188
				],
				[
					-10.853343339266146,
					-389.3636922961727
				],
				[
					2.7133358348165135,
					-369.0136735350487
				],
				[
					-6.331116947905245,
					-221.1368705375476
				],
				[
					0.9044452782721712,
					-77.33007129227126
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 213,
			"versionNonce": 613604752,
			"isDeleted": false,
			"id": "efS59Xgll1y-2jBty1El-",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -38.29203009003581,
			"y": -275.51458120908813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 34.30595137413693,
			"height": 19.297097647952008,
			"seed": 1580465008,
			"groupIds": [
				"DCY2LQ9QnSv57sS2UFw-0",
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 330,
			"versionNonce": 1220510576,
			"isDeleted": false,
			"id": "zAFYhRqyrcAZDXA2bOd1Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -34.921192498120774,
			"y": 141.3551835015815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 19.444515655868432,
			"height": 8.750032045140877,
			"seed": 1157933456,
			"groupIds": [
				"DCY2LQ9QnSv57sS2UFw-0",
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.370408349796488,
					8.750032045140877
				],
				[
					19.444515655868432,
					1.9444515655868617
				]
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 1199614864,
			"isDeleted": false,
			"id": "g075AjVH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.14461585021026746,
			"x": -8.16332354334358,
			"y": -169.82307572251335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 95.23886108398438,
			"height": 38.069131714118654,
			"seed": 1061957008,
			"groupIds": [
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772847,
			"link": null,
			"locked": false,
			"fontSize": 30.455305371294923,
			"fontFamily": 1,
			"text": "Recap:",
			"rawText": "Recap:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recap:",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 1860015472,
			"isDeleted": false,
			"id": "N8QwNYEv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -125.32999627387034,
			"y": -211.53176170217796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 85.1668701171875,
			"height": 25.04118142503316,
			"seed": 1040745840,
			"groupIds": [
				"Z7HwDibLgCADTNaG-vNzf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 20.032945140026527,
			"fontFamily": 1,
			"text": "examples",
			"rawText": "examples",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "examples",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 663009680,
			"isDeleted": false,
			"id": "J4OHqto5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1473.699508664241,
			"y": -422.5058859476993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 294.4212646484375,
			"height": 70,
			"seed": 1797606256,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "GSRA8_xmlfsuovlV-X4Ck",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Types of Non-Numeric\nKernels",
			"rawText": "Types of Non-Numeric\nKernels",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Types of Non-Numeric\nKernels",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 210,
			"versionNonce": 191457136,
			"isDeleted": false,
			"id": "QorUgNUpNz4LgKiet4ZAv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1492.0283201359684,
			"y": -459.44897808271014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 329.77115429861556,
			"height": 125.04199370251867,
			"seed": 476129168,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tK33vc9SLvQnWWcaO1WRv",
					"type": "arrow"
				},
				{
					"id": "GSRA8_xmlfsuovlV-X4Ck",
					"type": "arrow"
				},
				{
					"id": "9dPfFmEGGOElPdd_ihMmo",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 583,
			"versionNonce": 1205274512,
			"isDeleted": false,
			"id": "tK33vc9SLvQnWWcaO1WRv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1332.6775625862292,
			"y": -331.8474859866245,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.7868769900424013,
			"height": 151.59845659364473,
			"seed": 810130832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "QorUgNUpNz4LgKiet4ZAv",
				"gap": 2.59506598563776,
				"focus": 0.040503080783667406
			},
			"endBinding": {
				"elementId": "NPtkpBLj",
				"gap": 10.379989181992528,
				"focus": 0.018836049746408914
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					2.7868769900424013,
					151.59845659364473
				]
			]
		},
		{
			"type": "rectangle",
			"version": 339,
			"versionNonce": 178977136,
			"isDeleted": false,
			"id": "_HhynyMwrwutpXnDqxUH_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1643.7270380127377,
			"y": -180.95502706102354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 640.9548505745548,
			"height": 937.5279839708445,
			"seed": 1981421936,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 78615952,
			"isDeleted": false,
			"id": "NPtkpBLj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1424.9514484011318,
			"y": -169.86904021098727,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.60079956054688,
			"height": 35,
			"seed": 1773279632,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tK33vc9SLvQnWWcaO1WRv",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "String Kernels",
			"rawText": "String Kernels",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "String Kernels",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 400,
			"versionNonce": 267012976,
			"isDeleted": false,
			"id": "cFbeAgL1pQr5z2QjYe8Ry",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1715.782751214962,
			"y": -176.70379295854272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 260.225029217916,
			"height": 147.64115095693526,
			"seed": 1923974032,
			"groupIds": [
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1407,
			"versionNonce": 1933992848,
			"isDeleted": false,
			"id": "BGIL5OhZw1FXBZhevTBHP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1590.299283566297,
			"y": -173.483024808271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bfc2c9",
			"width": 4.317792954202469,
			"height": 8.460877522974805,
			"seed": 1526341008,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.3444176639487395,
					3.2945009823972704
				],
				[
					2.6705424630038426,
					6.5640436240187965
				],
				[
					1.647250491198626,
					8.460877522974805
				],
				[
					1.1980003572353677,
					6.788668691000435
				],
				[
					1.4475837649927314,
					3.41929268627597
				],
				[
					-0.9733752902537295,
					1.2229586980111113
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1614,
			"versionNonce": 359619952,
			"isDeleted": false,
			"id": "zkWedNPEfAdcVuSzWCEZy",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1594.052956046928,
			"y": -171.5286095503372,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 3.957842265969557,
			"height": 4.783826738867567,
			"seed": 788523920,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.75521700490823,
					0.41299223644899535
				],
				[
					3.4760179901123776,
					-1.204560689642939
				],
				[
					3.957842265969557,
					-3.4416019704083305
				],
				[
					2.7532815763266356,
					-4.370834502418571
				],
				[
					2.4091213792858066,
					-3.5792660492246617
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1526,
			"versionNonce": 1104376208,
			"isDeleted": false,
			"id": "RGAVu4f6dklhQNr0YDqLq",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.308504975540734,
			"x": -1595.6923690294395,
			"y": -175.30565020724427,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d8de",
			"width": 5.308036869102894,
			"height": 2.7996475039756348,
			"seed": 1562114448,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 985,
			"versionNonce": 209858416,
			"isDeleted": false,
			"id": "ueWi_V1LR5NDdvDzEvz97",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1592.404175757444,
			"y": -172.07521415355058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5305159404541453,
			"height": 0.38315040143909795,
			"seed": 1216759696,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5305159404541453,
					0.38315040143909795
				]
			]
		},
		{
			"type": "line",
			"version": 992,
			"versionNonce": 395231120,
			"isDeleted": false,
			"id": "oAKL3NyIsvW-78lEye7bb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1591.8736598169896,
			"y": -172.50257421669397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5305159404541453,
			"height": 0.38315040143909795,
			"seed": 762762640,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5305159404541453,
					0.38315040143909795
				]
			]
		},
		{
			"type": "ellipse",
			"version": 998,
			"versionNonce": 2104148336,
			"isDeleted": false,
			"id": "I0Oj3SnDAW9qqLF1uaXSp",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.5577432708235079,
			"x": -1593.391803616256,
			"y": -175.72584243400678,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f9fb",
			"width": 1.3262898511353183,
			"height": 1.8610964013755256,
			"seed": 19243920,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1878,
			"versionNonce": 1957711248,
			"isDeleted": false,
			"id": "8ynq87U3pLbC18xxZ4ohQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1590.1569898577047,
			"y": -173.15849957437487,
			"strokeColor": "transparent",
			"backgroundColor": "#9ca2ad",
			"width": 2.5448776442833294,
			"height": 7.477337628581419,
			"seed": 1372238224,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5981858442582091,
					1.1765155900778232
				],
				[
					1.4126102652251238,
					3.0142343322657417
				],
				[
					1.182865991902195,
					6.134620308955402
				],
				[
					1.2651194973428856,
					7.477337628581419
				],
				[
					1.9466918000251205,
					3.386397766935823
				],
				[
					0.0693417594103955,
					1.2200567470495336
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 901,
			"versionNonce": 661721968,
			"isDeleted": false,
			"id": "8QB_2swaKY3UJ6ERcaTt7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1589.7804155955007,
			"y": -165.86004656085197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9ca2ad",
			"width": 2.676090962842156,
			"height": 0.44192843916869334,
			"seed": 647888784,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.05158270206397,
					-0.34230024427924294
				],
				[
					1.9024824289611193,
					-0.07822791524229722
				],
				[
					2.676090962842156,
					-0.44192843916869334
				]
			]
		},
		{
			"type": "ellipse",
			"version": 809,
			"versionNonce": 309336976,
			"isDeleted": false,
			"id": "wS93_tZxagZ7B_FbbxcwY",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1589.817779142845,
			"y": -165.7898388146196,
			"strokeColor": "#8b5a2b",
			"backgroundColor": "#8b5a2b",
			"width": 2.328896200422019,
			"height": 2.203009919318116,
			"seed": 1607962000,
			"groupIds": [
				"H03x5FgHT9h6o6PafKaKJ",
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 394,
			"versionNonce": 551363952,
			"isDeleted": false,
			"id": "RuiSDikI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1621.296351846518,
			"y": -160.65062511350396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 67.76014709472656,
			"height": 20,
			"seed": 287176048,
			"groupIds": [
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Notation",
			"rawText": "Notation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notation",
			"lineHeight": 1.25
		},
		{
			"id": "huuhS9Jf",
			"type": "text",
			"x": -1709.6013349970394,
			"y": -136.29462176628573,
			"width": 249.85865783691406,
			"height": 97.36564090602582,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": null,
			"seed": 664204656,
			"version": 761,
			"versionNonce": 1124477328,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"text": "- an Alphabet is a finite set of discrete symbols\n\n- a Natural language involves letters and numbers\n\n- a string is a concatenation of symbols from an alphabet\n\n- A^L = all strings of length L from alphabet A\n\n- A^* = all strings of any length from alphabet A ",
			"rawText": "- an Alphabet is a finite set of discrete symbols\n\n- a Natural language involves letters and numbers\n\n- a string is a concatenation of symbols from an alphabet\n\n- A^L = all strings of length L from alphabet A\n\n- A^* = all strings of any length from alphabet A ",
			"fontSize": 8.654723636091184,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- an Alphabet is a finite set of discrete symbols\n\n- a Natural language involves letters and numbers\n\n- a string is a concatenation of symbols from an alphabet\n\n- A^L = all strings of length L from alphabet A\n\n- A^* = all strings of any length from alphabet A ",
			"lineHeight": 1.25
		},
		{
			"id": "rdec9J5h",
			"type": "text",
			"x": -1546.5152243194782,
			"y": -29.06264197910161,
			"width": 437.0729064941406,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1765668720,
			"version": 255,
			"versionNonce": 1995896688,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"text": "Approach 1:\nCount the number of matching symbols\nProblem 1:\nDoesnt take into account a slight shift in the position",
			"rawText": "Approach 1:\nCount the number of matching symbols\nProblem 1:\nDoesnt take into account a slight shift in the position",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 1:\nCount the number of matching symbols\nProblem 1:\nDoesnt take into account a slight shift in the position",
			"lineHeight": 1.25
		},
		{
			"id": "yZdX2QYJ",
			"type": "text",
			"x": -1438.4540567002928,
			"y": -122.66656545480761,
			"width": 250.3525390625,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1635467120,
			"version": 200,
			"versionNonce": 1370126224,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"text": "We are gonna start with simple\nideas on how to compare\ntwo strings and build upon them\naccording to the situation",
			"rawText": "We are gonna start with simple\nideas on how to compare\ntwo strings and build upon them\naccording to the situation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We are gonna start with simple\nideas on how to compare\ntwo strings and build upon them\naccording to the situation",
			"lineHeight": 1.25
		},
		{
			"id": "ol9b5BrpvUv03MRNrEIDU",
			"type": "arrow",
			"x": -1330.4922415905748,
			"y": 105.01278830981937,
			"width": 1.9913533293558885,
			"height": 41.733409213445725,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 716835728,
			"version": 698,
			"versionNonce": 1309051248,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.9913533293558885,
					41.733409213445725
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "49SklR98XtpxyjdJM8GOg",
				"focus": 0.002110940105037915,
				"gap": 6.462176702805603
			},
			"endBinding": {
				"elementId": "xqd16O5J",
				"focus": -0.0031099038576203977,
				"gap": 4.6131144144776215
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "text",
			"version": 480,
			"versionNonce": 1653933456,
			"isDeleted": false,
			"id": "xqd16O5J",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1581.131938811148,
			"y": 151.35931193774272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 511.12103271484375,
			"height": 80,
			"seed": 1096653200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ol9b5BrpvUv03MRNrEIDU",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Approach 2:\nCount the number of matching symbols with some shift tolerance.\nProblem 2:\nOrder matters, not occurances",
			"rawText": "Approach 2:\nCount the number of matching symbols with some shift tolerance.\nProblem 2:\nOrder matters, not occurances",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 2:\nCount the number of matching symbols with some shift tolerance.\nProblem 2:\nOrder matters, not occurances",
			"lineHeight": 1.25
		},
		{
			"id": "49SklR98XtpxyjdJM8GOg",
			"type": "image",
			"x": -1408.2352728932422,
			"y": 50.93735781924934,
			"width": 152.92256804776093,
			"height": 47.6132537877644,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 744774032,
			"version": 71,
			"versionNonce": 22272880,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ol9b5BrpvUv03MRNrEIDU",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8daa979fc9d2dd99a1047c56c17da18ad49bbaf0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xZ2hYHJ33SQlHAljGwLfM",
			"type": "image",
			"x": -1493.2295856364995,
			"y": 230.943394746621,
			"width": 334.48449320273846,
			"height": 42.23046686060399,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1223429488,
			"version": 199,
			"versionNonce": 1392366480,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-IynFedYmYVFL-vGUC-HF",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bc12ccfbb35a2fb7e055fc527a30e46e66291a14",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1103,
			"versionNonce": 1126624624,
			"isDeleted": false,
			"id": "-IynFedYmYVFL-vGUC-HF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1326.465310417126,
			"y": 277.81237619407517,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 0.8257041938666134,
			"height": 32.17337391402788,
			"seed": 889228176,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xZ2hYHJ33SQlHAljGwLfM",
				"gap": 4.63851458685015,
				"focus": -0.0010905570536394573
			},
			"endBinding": {
				"elementId": "Sfm78HF9",
				"gap": 4.61311441447765,
				"focus": -0.003109903857619579
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-0.8257041938666134,
					32.17337391402788
				]
			]
		},
		{
			"type": "text",
			"version": 593,
			"versionNonce": 421323152,
			"isDeleted": false,
			"id": "Sfm78HF9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1556.2352251743778,
			"y": 314.5988645225807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 456.5129089355469,
			"height": 100,
			"seed": 436771216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-IynFedYmYVFL-vGUC-HF",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Approach 3:\nCount the number of matching symbols between sequences.\nwith full shift invariance.\nProblem 3:\nonly individual letters are counted, not sequences",
			"rawText": "Approach 3:\nCount the number of matching symbols between sequences.\nwith full shift invariance.\nProblem 3:\nonly individual letters are counted, not sequences",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 3:\nCount the number of matching symbols between sequences.\nwith full shift invariance.\nProblem 3:\nonly individual letters are counted, not sequences",
			"lineHeight": 1.25
		},
		{
			"id": "tSXiAudHo1RQAhnPWfvi8",
			"type": "arrow",
			"x": -1236.8516100910574,
			"y": 262.723443394005,
			"width": 106.61286698242293,
			"height": 20.37993031075905,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1827078544,
			"version": 157,
			"versionNonce": 1019723632,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					7.4865050121156855,
					20.37993031075905
				],
				[
					106.61286698242293,
					12.893425298643479
				]
			],
			"lastCommittedPoint": [
				106.47473795008818,
				20.37993031075905
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "WH8HD2FS",
				"focus": 0.15572663467430525,
				"gap": 9.005074033131109
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "WH8HD2FS",
			"type": "text",
			"x": -1121.2336690755033,
			"y": 262.86217844378984,
			"width": 43.68521869158053,
			"height": 25.30417187110154,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1949545328,
			"version": 81,
			"versionNonce": 606744464,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "tSXiAudHo1RQAhnPWfvi8",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"text": "different\nweights",
			"rawText": "different\nweights",
			"fontSize": 10.121668748440616,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "different\nweights",
			"lineHeight": 1.25
		},
		{
			"id": "GiB9snmqx_qAGEpgdVnNJ",
			"type": "image",
			"x": -1535.285501986671,
			"y": 414.5988652472552,
			"width": 191.8111748525249,
			"height": 102.02722066623666,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1143248240,
			"version": 144,
			"versionNonce": 780030320,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e758f3f801be46b6a280cb533c5fa05313eab168",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YqMtXD1AkLM382q2h2Xr1",
			"type": "image",
			"x": -1317.5508496943862,
			"y": 420.3370687884113,
			"width": 217.82853363445477,
			"height": 90.55081485385764,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 370048368,
			"version": 107,
			"versionNonce": 1012776336,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZjnlINP46YTJsAj39cDS2",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "12f14a85ee122ca320154f1539367d881d627325",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1243,
			"versionNonce": 261268336,
			"isDeleted": false,
			"id": "ZjnlINP46YTJsAj39cDS2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1326.1812167740025,
			"y": 502.9376311607735,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 1.1581039542959388,
			"height": 48.6398783000472,
			"seed": 2006912368,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "YqMtXD1AkLM382q2h2Xr1",
				"focus": 1.0553061226917486,
				"gap": 8.630367079616235
			},
			"endBinding": {
				"elementId": "2jMOmATY",
				"focus": -0.0031099038576179587,
				"gap": 4.61311441447765
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-1.1581039542959388,
					48.6398783000472
				]
			]
		},
		{
			"type": "text",
			"version": 662,
			"versionNonce": 1659866000,
			"isDeleted": false,
			"id": "2jMOmATY",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1554.039128967778,
			"y": 556.1906238752983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 452.68890380859375,
			"height": 80,
			"seed": 1832640368,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZjnlINP46YTJsAj39cDS2",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Approach 4:\nCount the number of matching subsequences of symbols.\nCan be generalized to triplets of consecutive of symbols,\nor more generally, ‘n-grams’",
			"rawText": "Approach 4:\nCount the number of matching subsequences of symbols.\nCan be generalized to triplets of consecutive of symbols,\nor more generally, ‘n-grams’",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 4:\nCount the number of matching subsequences of symbols.\nCan be generalized to triplets of consecutive of symbols,\nor more generally, ‘n-grams’",
			"lineHeight": 1.25
		},
		{
			"id": "ZclUv0z8dJCN3xHvahXig",
			"type": "image",
			"x": -1568.2164240326151,
			"y": 640.7022682655378,
			"width": 224.742097301453,
			"height": 44.35043605283662,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1695809392,
			"version": 153,
			"versionNonce": 776779120,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "99e975181af75b683274be932478bd59b43b9dfd",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Bslp6pS-NG6h5tTaweFS0",
			"type": "image",
			"x": -1343.4743272923133,
			"y": 636.1906235831768,
			"width": 272.1226848154926,
			"height": 62.596911523052626,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1592920432,
			"version": 145,
			"versionNonce": 840407440,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "92f8c69ff949d7e89ec45531a03892db40c3e720",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "OZcKqdB6",
			"type": "text",
			"x": -1617.001896552789,
			"y": 721.1556705690323,
			"width": 594.4871079113275,
			"height": 18.439847431380155,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1925679472,
			"version": 86,
			"versionNonce": 1341425520,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"text": "build sorted lists before performing the kernel evaluations to reduce computation",
			"rawText": "build sorted lists before performing the kernel evaluations to reduce computation",
			"fontSize": 14.751877945104122,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "build sorted lists before performing the kernel evaluations to reduce computation",
			"lineHeight": 1.25
		},
		{
			"id": "GSRA8_xmlfsuovlV-X4Ck",
			"type": "arrow",
			"x": -1349.9265965756956,
			"y": -332.03444438784675,
			"width": 688.1750682897498,
			"height": 168.2807017972484,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
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
			"seed": 1029690768,
			"version": 512,
			"versionNonce": 1024321424,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-64.28794131320774,
					86.15872318574861
				],
				[
					-614.5051980102562,
					77.94652532459872
				],
				[
					-688.1750682897498,
					168.2807017972484
				]
			],
			"lastCommittedPoint": [
				-658.3445285355226,
				218.99194296399924
			],
			"startBinding": {
				"elementId": "QorUgNUpNz4LgKiet4ZAv",
				"gap": 2.978663522102366,
				"focus": -0.14961038941600016
			},
			"endBinding": {
				"elementId": "9gBsPG65yB2wxrR7ZklPM",
				"gap": 2.737399287049925,
				"focus": -0.5065343659244929
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "9gBsPG65yB2wxrR7ZklPM",
			"type": "rectangle",
			"x": -2293.6331498150234,
			"y": -161.0163433035484,
			"width": 518.7371648959731,
			"height": 622.7583378038728,
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
				"type": 3
			},
			"seed": 544268688,
			"version": 250,
			"versionNonce": 1355946352,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "GSRA8_xmlfsuovlV-X4Ck",
					"type": "arrow"
				}
			],
			"updated": 1717182772849,
			"link": null,
			"locked": false
		},
		{
			"id": "eAqAtVXi",
			"type": "text",
			"x": -2126.999175830925,
			"y": -152.36904045599732,
			"width": 174.66476440429688,
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
			"seed": 884205424,
			"version": 35,
			"versionNonce": 1879733648,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "Tree Kernels",
			"rawText": "Tree Kernels",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tree Kernels",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 478,
			"versionNonce": 1143827312,
			"isDeleted": false,
			"id": "dlKSyT1MqsXlftu8SxX1s",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2412.5324722959313,
			"y": -157.0279199159098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 260.225029217916,
			"height": 147.64115095693526,
			"seed": 1452634000,
			"groupIds": [
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1484,
			"versionNonce": 1883587472,
			"isDeleted": false,
			"id": "xArKCKOzkT3II-0i0Jwd2",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2287.374149413718,
			"y": -153.80715176563805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bfc2c9",
			"width": 4.317792954202469,
			"height": 8.460877522974805,
			"seed": 2137062800,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.3444176639487395,
					3.2945009823972704
				],
				[
					2.6705424630038426,
					6.5640436240187965
				],
				[
					1.647250491198626,
					8.460877522974805
				],
				[
					1.1980003572353677,
					6.788668691000435
				],
				[
					1.4475837649927314,
					3.41929268627597
				],
				[
					-0.9733752902537295,
					1.2229586980111113
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1691,
			"versionNonce": 340688240,
			"isDeleted": false,
			"id": "dSxo1uP1I_zqsyHe-8w7l",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2291.1278218943494,
			"y": -151.85273650770424,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 3.957842265969557,
			"height": 4.783826738867567,
			"seed": 1670040464,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.75521700490823,
					0.41299223644899535
				],
				[
					3.4760179901123776,
					-1.204560689642939
				],
				[
					3.957842265969557,
					-3.4416019704083305
				],
				[
					2.7532815763266356,
					-4.370834502418571
				],
				[
					2.4091213792858066,
					-3.5792660492246617
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1603,
			"versionNonce": 2079740304,
			"isDeleted": false,
			"id": "VK_omWSQimvh3yHtCwFUW",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.308504975540734,
			"x": -2292.7672348768606,
			"y": -155.62977716461134,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d8de",
			"width": 5.308036869102894,
			"height": 2.7996475039756348,
			"seed": 2102057360,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1062,
			"versionNonce": 578637680,
			"isDeleted": false,
			"id": "MzYhfVwHBmkRc-Yx-7r4u",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2289.479041604865,
			"y": -152.39934111091762,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5305159404541453,
			"height": 0.38315040143909795,
			"seed": 1071196048,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5305159404541453,
					0.38315040143909795
				]
			]
		},
		{
			"type": "line",
			"version": 1069,
			"versionNonce": 1247125392,
			"isDeleted": false,
			"id": "bu9v9Xb5sKg9hSSeYpt-6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2288.9485256644107,
			"y": -152.82670117406101,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5305159404541453,
			"height": 0.38315040143909795,
			"seed": 2003678608,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5305159404541453,
					0.38315040143909795
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1075,
			"versionNonce": 1728176496,
			"isDeleted": false,
			"id": "O-8LwXc73jp3uh2RRH5xZ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.5577432708235079,
			"x": -2290.4666694636776,
			"y": -156.04996939137382,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f9fb",
			"width": 1.3262898511353183,
			"height": 1.8610964013755256,
			"seed": 692093840,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1955,
			"versionNonce": 1805331856,
			"isDeleted": false,
			"id": "zBuBv9m3htr02oN2VdJrg",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2287.2318557051262,
			"y": -153.48262653174194,
			"strokeColor": "transparent",
			"backgroundColor": "#9ca2ad",
			"width": 2.5448776442833294,
			"height": 7.477337628581419,
			"seed": 1938395536,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5981858442582091,
					1.1765155900778232
				],
				[
					1.4126102652251238,
					3.0142343322657417
				],
				[
					1.182865991902195,
					6.134620308955402
				],
				[
					1.2651194973428856,
					7.477337628581419
				],
				[
					1.9466918000251205,
					3.386397766935823
				],
				[
					0.0693417594103955,
					1.2200567470495336
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 978,
			"versionNonce": 287585136,
			"isDeleted": false,
			"id": "ByTgY_RUrw1MTmemicy4O",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2286.8552814429218,
			"y": -146.184173518219,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9ca2ad",
			"width": 2.676090962842156,
			"height": 0.44192843916869334,
			"seed": 1837162384,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.05158270206397,
					-0.34230024427924294
				],
				[
					1.9024824289611193,
					-0.07822791524229722
				],
				[
					2.676090962842156,
					-0.44192843916869334
				]
			]
		},
		{
			"type": "ellipse",
			"version": 886,
			"versionNonce": 687799184,
			"isDeleted": false,
			"id": "WsFv1aAhNu3BTJjqNK4_j",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2286.892644990266,
			"y": -146.11396577198664,
			"strokeColor": "#8b5a2b",
			"backgroundColor": "#8b5a2b",
			"width": 2.328896200422019,
			"height": 2.203009919318116,
			"seed": 123628944,
			"groupIds": [
				"XgxXdyg7Ro84J-AvDWSkP",
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 471,
			"versionNonce": 657212784,
			"isDeleted": false,
			"id": "DZF3LEEf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2318.3712176939393,
			"y": -140.974752070871,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 67.76014709472656,
			"height": 20,
			"seed": 1784298384,
			"groupIds": [
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Notation",
			"rawText": "Notation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1091,
			"versionNonce": 1689848208,
			"isDeleted": false,
			"id": "goSW2zUl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2406.351056078009,
			"y": -116.61874872365277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 231.90130615234375,
			"height": 97.36564090602582,
			"seed": 1487686032,
			"groupIds": [
				"IRzYwoYMlp33UuvF5TEa1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 8.654723636091184,
			"fontFamily": 1,
			"text": "- A tree is an acyclic graph rooted at node V\n\n- a parse tree is a tree derived from a grammar with\n  some production rules.\n\n- Vi is the ith child of node V\n- |v| is the number of children of node v\n- T is the set of all possible trees\n",
			"rawText": "- A tree is an acyclic graph rooted at node V\n\n- a parse tree is a tree derived from a grammar with\n  some production rules.\n\n- Vi is the ith child of node V\n- |v| is the number of children of node v\n- T is the set of all possible trees\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- A tree is an acyclic graph rooted at node V\n\n- a parse tree is a tree derived from a grammar with\n  some production rules.\n\n- Vi is the ith child of node V\n- |v| is the number of children of node v\n- T is the set of all possible trees\n",
			"lineHeight": 1.25
		},
		{
			"id": "Ii80uBC2",
			"type": "text",
			"x": -2151.5917917997494,
			"y": -111.32447545079162,
			"width": 212.49642944335938,
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
			"seed": 1059117936,
			"version": 98,
			"versionNonce": 643962736,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "Lets give an example of a\nsentence tree derived from\na grammar",
			"rawText": "Lets give an example of a\nsentence tree derived from\na grammar",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets give an example of a\nsentence tree derived from\na grammar",
			"lineHeight": 1.25
		},
		{
			"id": "E7yoz-5bGrvXRTvVKWZLG",
			"type": "image",
			"x": -1915.3513187573894,
			"y": -136.82166491981428,
			"width": 113.08074992698471,
			"height": 134.56609241311182,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1146934160,
			"version": 62,
			"versionNonce": 2046908304,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "49ce4ade3aee7bb1c9b6af51e34e8772337aeff9",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "0GGM9bFTcM1kYmvSrLdor",
			"type": "image",
			"x": -2133.820281062768,
			"y": -45.279909770953836,
			"width": 188.30697484093338,
			"height": 67.25249101461907,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 994018704,
			"version": 96,
			"versionNonce": 588097904,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "255c620ae734545bed7478fe514b6edc6dbf57b4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "beE1N8Z3",
			"type": "text",
			"x": -2141.2257231527356,
			"y": 29.43792975209079,
			"width": 195.71241760253906,
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
			"seed": 142123408,
			"version": 78,
			"versionNonce": 487581072,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "a Tree kernel is given by",
			"rawText": "a Tree kernel is given by",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a Tree kernel is given by",
			"lineHeight": 1.25
		},
		{
			"id": "oa3pSFBLOlR98GVUVuumo",
			"type": "image",
			"x": -2147.623358952229,
			"y": 56.90327884636636,
			"width": 215.91313056674454,
			"height": 36.63126521850152,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1015265136,
			"version": 102,
			"versionNonce": 1752628080,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64be02c1293114e088cc44da245f4864e6b72947",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZHPkO_JQKUgQZxOgDG8AB",
			"type": "arrow",
			"x": -1957.1958237051294,
			"y": 80.32354126658339,
			"width": 41.81273448110551,
			"height": 15.29806786687854,
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
			"roundness": {
				"type": 2
			},
			"seed": 1532386192,
			"version": 186,
			"versionNonce": 991736720,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					17.728085153862366,
					15.29806786687854
				],
				[
					41.81273448110551,
					0.8032022504730634
				]
			],
			"lastCommittedPoint": [
				45.21286137111315,
				26.210354418036673
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "35SvLz5z",
				"focus": 0.6335959274600791,
				"gap": 3.1059587086074316
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "35SvLz5z",
			"type": "text",
			"x": -1912.2771305154165,
			"y": 61.84745430989699,
			"width": 73.97189158630464,
			"height": 50.513351279708786,
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
			"seed": 1520550768,
			"version": 171,
			"versionNonce": 417729904,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZHPkO_JQKUgQZxOgDG8AB",
					"type": "arrow"
				}
			],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "number of\noccurances of \nsubtree t in\nz",
			"rawText": "number of\noccurances of \nsubtree t in\nz",
			"fontSize": 10.102670255941762,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of\noccurances of \nsubtree t in\nz",
			"lineHeight": 1.25
		},
		{
			"id": "BHJwkCLr",
			"type": "text",
			"x": -2199.9507853578425,
			"y": 112.3608062375035,
			"width": 331.3724365234375,
			"height": 40.228124237825526,
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
			"seed": 514344336,
			"version": 166,
			"versionNonce": 1516224912,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "By definition k is an inner product in the space of all trees T\nand thus symmetric and PSD\nparse trees count the number of of shared subtrees",
			"rawText": "By definition k is an inner product in the space of all trees T\nand thus symmetric and PSD\nparse trees count the number of of shared subtrees",
			"fontSize": 10.727499796753474,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "By definition k is an inner product in the space of all trees T\nand thus symmetric and PSD\nparse trees count the number of of shared subtrees",
			"lineHeight": 1.25
		},
		{
			"id": "q2S7YL9O0VpoxobnmGTdC",
			"type": "image",
			"x": -2172.284747592417,
			"y": 157.1353242448702,
			"width": 265.2359065157716,
			"height": 34.22398793751891,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1864052080,
			"version": 92,
			"versionNonce": 1302519664,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "34ca0d55460886c6e4fe7a6aa7490f1ce5eabc73",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "m2oW2eP2",
			"type": "text",
			"x": -2172.284748433408,
			"y": 201.76229792606688,
			"width": 260.8614587083116,
			"height": 13.996486397127633,
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
			"seed": 930449776,
			"version": 133,
			"versionNonce": 2047938448,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "We can define this counting function recursively",
			"rawText": "We can define this counting function recursively",
			"fontSize": 11.197189117702111,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can define this counting function recursively",
			"lineHeight": 1.25
		},
		{
			"id": "fsqeB6wJZD5F680ozMDlR",
			"type": "image",
			"x": -2205.8876378601744,
			"y": 215.75878419259536,
			"width": 328.06723818033305,
			"height": 128.22169919719886,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2078664592,
			"version": 203,
			"versionNonce": 922055024,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dd5c3e16ab4f6724f9cdb69ee3e531d838c58c00",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "kxCZSFRV",
			"type": "text",
			"x": -2260.6570225802925,
			"y": 362.0548383421319,
			"width": 452.784912109375,
			"height": 40,
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
			"seed": 99428208,
			"version": 137,
			"versionNonce": 1919458704,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "We can use dynamic programming to implement an efficient\nway of recursively doing this",
			"rawText": "We can use dynamic programming to implement an efficient\nway of recursively doing this",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can use dynamic programming to implement an efficient\nway of recursively doing this",
			"lineHeight": 1.25
		},
		{
			"id": "RtVejH2qIqFVeiLqgb8Gm",
			"type": "image",
			"x": -2104.7260668215786,
			"y": 414.27610856594185,
			"width": 140.92300061109609,
			"height": 28.18460012221922,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1558510992,
			"version": 50,
			"versionNonce": 1009107824,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1b7549281e8a5b1a120a61be3c4cad75f7129c89",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 632,
			"versionNonce": 1419668368,
			"isDeleted": false,
			"id": "9dPfFmEGGOElPdd_ihMmo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1312.1410186434873,
			"y": -334.17510946453234,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 692.5469129485775,
			"height": 167.64501470211337,
			"seed": 19106672,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "QorUgNUpNz4LgKiet4ZAv",
				"focus": 0.18570360573630815,
				"gap": 1
			},
			"endBinding": {
				"elementId": "JNQqAGXKpJ5Xb10wf6Gze",
				"gap": 10.520489768582365,
				"focus": 0.5275056672181668
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					64.28794131320775,
					86.15872318574863
				],
				[
					614.5051980102563,
					77.94652532459874
				],
				[
					692.5469129485775,
					167.64501470211337
				]
			]
		},
		{
			"type": "rectangle",
			"version": 339,
			"versionNonce": 461100400,
			"isDeleted": false,
			"id": "JNQqAGXKpJ5Xb10wf6Gze",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -891.5890206147997,
			"y": -156.0096049938366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 518.7371648959731,
			"height": 559.67502984707,
			"seed": 1002916240,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "9dPfFmEGGOElPdd_ihMmo",
					"type": "arrow"
				},
				{
					"id": "acVmYjI_KnPnfolcAroLD",
					"type": "arrow"
				}
			],
			"updated": 1717182772849,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 1256880528,
			"isDeleted": false,
			"id": "HnhYxi8a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -735.1470861204475,
			"y": -146.72661505115042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 195.04884338378906,
			"height": 70,
			"seed": 1430755216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Model Induced\nKernels",
			"rawText": "Model Induced\nKernels",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Model Induced\nKernels",
			"lineHeight": 1.25
		},
		{
			"id": "W0qtWmSa",
			"type": "text",
			"x": -890.4533167228548,
			"y": -66.3692844872242,
			"width": 504.41693115234375,
			"height": 40,
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
			"seed": 371701104,
			"version": 62,
			"versionNonce": 171943792,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "Certain machine learning models already\nexist for structured data for example markov models and GNN",
			"rawText": "Certain machine learning models already\nexist for structured data for example markov models and GNN",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Certain machine learning models already\nexist for structured data for example markov models and GNN",
			"lineHeight": 1.25
		},
		{
			"id": "38WHDc2l",
			"type": "text",
			"x": -884.1661993754758,
			"y": -19.062641761225105,
			"width": 508.9770202636719,
			"height": 60,
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
			"seed": 1633398160,
			"version": 28,
			"versionNonce": 2021967760,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "Idea:\nDo not build a new kernel directly on the input data, extract a\nkernel from local response of the existing model",
			"rawText": "Idea:\nDo not build a new kernel directly on the input data, extract a\nkernel from local response of the existing model",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea:\nDo not build a new kernel directly on the input data, extract a\nkernel from local response of the existing model",
			"lineHeight": 1.25
		},
		{
			"id": "1xYCETdz0Ibzgmvi_weJX",
			"type": "image",
			"x": -739.4719746785199,
			"y": 48.879687037190905,
			"width": 236.11643394646003,
			"height": 36.974276744363245,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1019071376,
			"version": 96,
			"versionNonce": 1421425008,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9dbda5becac35c03e9c6e3660a87b5fc725391db",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "k5vYiCxcnQzjVxzqzXNyL",
			"type": "image",
			"x": -698.8553643549793,
			"y": 92.52491865049832,
			"width": 140.26463871574265,
			"height": 32.27327970450716,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 695080304,
			"version": 63,
			"versionNonce": 1504007568,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "945d242e9b77af91560b93fe3193246d53f370e9",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "J1F4AqxU3I4Xzzimi8RdV",
			"type": "line",
			"x": -794.0399707053606,
			"y": 132.9218913079311,
			"width": 312.75805080648513,
			"height": 1.2713741902702793,
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
			"roundness": {
				"type": 2
			},
			"seed": 1453145456,
			"version": 61,
			"versionNonce": 2117110640,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					312.75805080648513,
					-1.2713741902702793
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "eTMk9a8c",
			"type": "text",
			"x": -889.0513609076858,
			"y": 181.7406612087028,
			"width": 517.2344970703125,
			"height": 60,
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
			"seed": 1192035696,
			"version": 54,
			"versionNonce": 595862416,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"text": "Suppose x ∈ X and we have some generative model for the data\nThe Fisher Kernel is built as follows. It computes the gradient\nof the locally evaluated function w.r.t. the model parameters.",
			"rawText": "Suppose x ∈ X and we have some generative model for the data\nThe Fisher Kernel is built as follows. It computes the gradient\nof the locally evaluated function w.r.t. the model parameters.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Suppose x ∈ X and we have some generative model for the data\nThe Fisher Kernel is built as follows. It computes the gradient\nof the locally evaluated function w.r.t. the model parameters.",
			"lineHeight": 1.25
		},
		{
			"id": "1b3lLcXQQfC8LFRRFpcoO",
			"type": "image",
			"x": -687.6043858262407,
			"y": 248.7252705852955,
			"width": 117.76268255879424,
			"height": 35.55099850831524,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1309839216,
			"version": 75,
			"versionNonce": 1626185072,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a89aed78227e8aecf1712c0bf412d74db309d7b1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "GHhuBESWkoaf9nLy5NoJR",
			"type": "image",
			"x": -766.4342100839555,
			"y": 299.4570683771535,
			"width": 258.45480148789903,
			"height": 30.28359290161241,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1979159952,
			"version": 82,
			"versionNonce": 609825168,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rGbTDn9sXkBtlrBDETlE4",
					"type": "arrow"
				}
			],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9452fd1182789a4c99782f0110fc8779d5cde828",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "rGbTDn9sXkBtlrBDETlE4",
			"type": "arrow",
			"x": -610.2960314816178,
			"y": 335.3458504150009,
			"width": 81.48915142271812,
			"height": 28.011895801559433,
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
			"roundness": {
				"type": 2
			},
			"seed": 1494638960,
			"version": 91,
			"versionNonce": 1312321392,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.456437968429782,
					28.011895801559433
				],
				[
					81.48915142271812,
					27.05694480832443
				]
			],
			"lastCommittedPoint": [
				81.48915142271812,
				27.05694480832443
			],
			"startBinding": {
				"elementId": "GHhuBESWkoaf9nLy5NoJR",
				"focus": -0.17935870996036576,
				"gap": 5.605189136234998
			},
			"endBinding": {
				"elementId": "Akh5mwMr",
				"focus": 0.20404069955669843,
				"gap": 7.2040664155101695
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Akh5mwMr",
			"type": "text",
			"x": -521.6028136433895,
			"y": 340.11953562848737,
			"width": 137.751000232224,
			"height": 54.05889529232837,
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
			"seed": 1234924400,
			"version": 272,
			"versionNonce": 593264528,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rGbTDn9sXkBtlrBDETlE4",
					"type": "arrow"
				}
			],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "Normalization term to not\nallow the matrix to blow up.\nthe middle term is basically an\nexpectation over the covariance\nmatrix of the Gradients",
			"rawText": "Normalization term to not\nallow the matrix to blow up.\nthe middle term is basically an\nexpectation over the covariance\nmatrix of the Gradients",
			"fontSize": 8.649423246772535,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normalization term to not\nallow the matrix to blow up.\nthe middle term is basically an\nexpectation over the covariance\nmatrix of the Gradients",
			"lineHeight": 1.25
		},
		{
			"id": "kapWlQmJ",
			"type": "text",
			"x": -682.9411977974434,
			"y": 142.68185031146422,
			"width": 98.78421020507812,
			"height": 40,
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
			"seed": 321609584,
			"version": 52,
			"versionNonce": 777585008,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "For example:\nFisher Kernel",
			"rawText": "For example:\nFisher Kernel",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For example:\nFisher Kernel",
			"lineHeight": 1.25
		},
		{
			"id": "acVmYjI_KnPnfolcAroLD",
			"type": "arrow",
			"x": -639.3518898386766,
			"y": 405.4211649133151,
			"width": 0.13012660108176988,
			"height": 112.00554872383736,
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
			"roundness": {
				"type": 2
			},
			"seed": 40074608,
			"version": 65,
			"versionNonce": 347303312,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182796369,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13012660108176988,
					112.00554872383736
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "JNQqAGXKpJ5Xb10wf6Gze",
				"focus": 0.027495433735863602,
				"gap": 1.7557400600816777
			},
			"endBinding": {
				"elementId": "CNs32ZZ4OkHPWalnu9BZq",
				"focus": 0.0062890963538377595,
				"gap": 5.608303752365259
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "rectangle",
			"version": 373,
			"versionNonce": 1646170512,
			"isDeleted": false,
			"id": "CNs32ZZ4OkHPWalnu9BZq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -900.8154648206566,
			"y": 523.0350173895177,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 518.7371648959731,
			"height": 559.67502984707,
			"seed": 1936649072,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "acVmYjI_KnPnfolcAroLD",
					"type": "arrow"
				}
			],
			"updated": 1717182796368,
			"link": null,
			"locked": false
		},
		{
			"id": "muQyW96m",
			"type": "text",
			"x": -754.9651542338015,
			"y": 532.6378859658678,
			"width": 230.49696350097656,
			"height": 35,
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
			"seed": 843838320,
			"version": 51,
			"versionNonce": 1439554448,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "Diffusion Kernels",
			"rawText": "Diffusion Kernels",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Diffusion Kernels",
			"lineHeight": 1.25
		},
		{
			"id": "DhQa3WFn",
			"type": "text",
			"x": -873.8555512238726,
			"y": 577.3531781679294,
			"width": 465.74493408203125,
			"height": 80,
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
			"seed": 913517936,
			"version": 94,
			"versionNonce": 456877424,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "Diffusion kernels assume that the input domain is discrete\nand that the local geometry is given by a graph\nthe diffusion kernel defines the generator matrix which is\nbasically the graph laplacian in a way.",
			"rawText": "Diffusion kernels assume that the input domain is discrete\nand that the local geometry is given by a graph\nthe diffusion kernel defines the generator matrix which is\nbasically the graph laplacian in a way.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Diffusion kernels assume that the input domain is discrete\nand that the local geometry is given by a graph\nthe diffusion kernel defines the generator matrix which is\nbasically the graph laplacian in a way.",
			"lineHeight": 1.25
		},
		{
			"id": "8Ei9ebQceV8e4CrA42cEQ",
			"type": "image",
			"x": -739.3250361348823,
			"y": 659.5304966254834,
			"width": 199.28140664862056,
			"height": 61.62517394354933,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 211519344,
			"version": 70,
			"versionNonce": 1420552592,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0b9c99f928e2b988332c1f85caf6524e41bd489e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "p1g48QWI",
			"type": "text",
			"x": -888.4717084321903,
			"y": 734.2011147279383,
			"width": 495.55303955078125,
			"height": 20,
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
			"seed": 1097935216,
			"version": 13,
			"versionNonce": 431510896,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182775240,
			"link": null,
			"locked": false,
			"text": "then diffuses the graph signal by matrix exponentiation. Kernel",
			"rawText": "then diffuses the graph signal by matrix exponentiation. Kernel",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "then diffuses the graph signal by matrix exponentiation. Kernel",
			"lineHeight": 1.25
		},
		{
			"id": "g1xA1k8K",
			"type": "text",
			"x": -739.1913968477177,
			"y": 764.2011147279383,
			"width": 196.99241638183594,
			"height": 20,
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
			"seed": 681862544,
			"version": 25,
			"versionNonce": 216803184,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182775240,
			"link": null,
			"locked": false,
			"text": "scores are then given by:",
			"rawText": "scores are then given by:",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scores are then given by:",
			"lineHeight": 1.25
		},
		{
			"id": "O7Ps5e8MHQoAXwxtFEZQT",
			"type": "image",
			"x": -744.635007386615,
			"y": 811.0171259944254,
			"width": 197.7334738255108,
			"height": 42.47092219491605,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 532482928,
			"version": 67,
			"versionNonce": 723324304,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182785155,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "85f30984f13860b79c696322259edde743461d69",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "tqG_KX1hW2sJ5iPaCFqGm",
			"type": "arrow",
			"x": -594.286633885858,
			"y": 814.1758761607646,
			"width": 91.74378576551908,
			"height": 19.960871663247985,
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
			"roundness": {
				"type": 2
			},
			"seed": 1430448528,
			"version": 89,
			"versionNonce": 174831472,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717182802172,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					29.219307252649628,
					-16.69674700151404
				],
				[
					91.74378576551908,
					-19.960871663247985
				]
			],
			"lastCommittedPoint": [
				99.2528849534446,
				-13.450157306775168
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "y2JZ7f0l",
				"focus": 1.2315449679956545,
				"gap": 4.776762495389619
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "y2JZ7f0l",
			"type": "text",
			"x": -498.21026201494385,
			"y": 796.2265107929824,
			"width": 87.517768533532,
			"height": 14.759438976790474,
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
			"seed": 755691888,
			"version": 90,
			"versionNonce": 1293276016,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "tqG_KX1hW2sJ5iPaCFqGm",
					"type": "arrow"
				}
			],
			"updated": 1717182802124,
			"link": null,
			"locked": false,
			"text": "hyperparameter",
			"rawText": "hyperparameter",
			"fontSize": 11.807551181432379,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "hyperparameter",
			"lineHeight": 1.25
		},
		{
			"id": "8rxyNbQC",
			"type": "text",
			"x": -880.9837025633826,
			"y": 862.7466710279487,
			"width": 480.5770263671875,
			"height": 20,
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
			"seed": 164867440,
			"version": 12,
			"versionNonce": 1784855952,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182829045,
			"link": null,
			"locked": false,
			"text": "the diffusion kernel is particularly useful for semi-supervised",
			"rawText": "the diffusion kernel is particularly useful for semi-supervised",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the diffusion kernel is particularly useful for semi-supervised",
			"lineHeight": 1.25
		},
		{
			"id": "H8UAm5cw",
			"type": "text",
			"x": -863.7116688719764,
			"y": 892.7466710279487,
			"width": 446.032958984375,
			"height": 20,
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
			"seed": 1889280400,
			"version": 12,
			"versionNonce": 992625552,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182835656,
			"link": null,
			"locked": false,
			"text": "learning, or for unsupervised analyses such as clustering",
			"rawText": "learning, or for unsupervised analyses such as clustering",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "learning, or for unsupervised analyses such as clustering",
			"lineHeight": 1.25
		},
		{
			"id": "sAiiC01CeLW0AlRBjVHzR",
			"type": "image",
			"x": -820.7429376663084,
			"y": 922.7466714311741,
			"width": 359.519707657755,
			"height": 149.4898502208163,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1610260368,
			"version": 108,
			"versionNonce": 1938749808,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717182856498,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "628de99bb72de7ba8f5deaf0073e41ac44314b26",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "qBb6bhbW",
			"type": "text",
			"x": -636.2204457962076,
			"y": 113.82790992969842,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 255325552,
			"version": 87,
			"versionNonce": 193804144,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "JNQqAGXKpJ5Xb10wf6Gze",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 510,
			"versionNonce": 681064336,
			"isDeleted": true,
			"id": "ZPS8Ai4U8eoyurEnw_ilN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1010.4883430957075,
			"y": -151.38549451106292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 260.225029217916,
			"height": 147.64115095693526,
			"seed": 898508176,
			"groupIds": [
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1516,
			"versionNonce": 1976879472,
			"isDeleted": true,
			"id": "i7MTuUwoOVhwrGYCAMgcR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -885.3300202134942,
			"y": -148.16472636079118,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bfc2c9",
			"width": 4.317792954202469,
			"height": 8.460877522974805,
			"seed": 701690768,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.3444176639487395,
					3.2945009823972704
				],
				[
					2.6705424630038426,
					6.5640436240187965
				],
				[
					1.647250491198626,
					8.460877522974805
				],
				[
					1.1980003572353677,
					6.788668691000435
				],
				[
					1.4475837649927314,
					3.41929268627597
				],
				[
					-0.9733752902537295,
					1.2229586980111113
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1723,
			"versionNonce": 365610384,
			"isDeleted": true,
			"id": "5GJZxXVJIY84y4ECQoB22",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -889.0836926941256,
			"y": -146.2103111028573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 3.957842265969557,
			"height": 4.783826738867567,
			"seed": 407765392,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.75521700490823,
					0.41299223644899535
				],
				[
					3.4760179901123776,
					-1.204560689642939
				],
				[
					3.957842265969557,
					-3.4416019704083305
				],
				[
					2.7532815763266356,
					-4.370834502418571
				],
				[
					2.4091213792858066,
					-3.5792660492246617
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1635,
			"versionNonce": 358226800,
			"isDeleted": true,
			"id": "Vog28AnXdTn3V7cEBuu7l",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.308504975540734,
			"x": -890.7231056766368,
			"y": -149.98735175976446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d8de",
			"width": 5.308036869102894,
			"height": 2.7996475039756348,
			"seed": 1614237584,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1094,
			"versionNonce": 427529104,
			"isDeleted": true,
			"id": "K7zjH8M3NwKT9B7RxS3xE",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -887.4349124046412,
			"y": -146.75691570607069,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5305159404541453,
			"height": 0.38315040143909795,
			"seed": 969334160,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5305159404541453,
					0.38315040143909795
				]
			]
		},
		{
			"type": "line",
			"version": 1101,
			"versionNonce": 2087005552,
			"isDeleted": true,
			"id": "4Bcw-jqtajv6uKhLmxpTR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -886.9043964641869,
			"y": -147.18427576921408,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5305159404541453,
			"height": 0.38315040143909795,
			"seed": 372550544,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5305159404541453,
					0.38315040143909795
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1107,
			"versionNonce": 1239589264,
			"isDeleted": true,
			"id": "M-Ybuz8296Q_t1yVlBHQv",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.5577432708235079,
			"x": -888.4225402634538,
			"y": -150.4075439865269,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f9fb",
			"width": 1.3262898511353183,
			"height": 1.8610964013755256,
			"seed": 2142812560,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1987,
			"versionNonce": 876478320,
			"isDeleted": true,
			"id": "dpze1LwsfvEA8iASK1HXr",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -885.1877265049025,
			"y": -147.84020112689507,
			"strokeColor": "transparent",
			"backgroundColor": "#9ca2ad",
			"width": 2.5448776442833294,
			"height": 7.477337628581419,
			"seed": 2039154576,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5981858442582091,
					1.1765155900778232
				],
				[
					1.4126102652251238,
					3.0142343322657417
				],
				[
					1.182865991902195,
					6.134620308955402
				],
				[
					1.2651194973428856,
					7.477337628581419
				],
				[
					1.9466918000251205,
					3.386397766935823
				],
				[
					0.0693417594103955,
					1.2200567470495336
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1010,
			"versionNonce": 909635472,
			"isDeleted": true,
			"id": "d73VYAnaw7WwuQgcn-tE7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -884.811152242698,
			"y": -140.54174811337214,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9ca2ad",
			"width": 2.676090962842156,
			"height": 0.44192843916869334,
			"seed": 1608750480,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.05158270206397,
					-0.34230024427924294
				],
				[
					1.9024824289611193,
					-0.07822791524229722
				],
				[
					2.676090962842156,
					-0.44192843916869334
				]
			]
		},
		{
			"type": "ellipse",
			"version": 918,
			"versionNonce": 1563201904,
			"isDeleted": true,
			"id": "vO3P4FyUr6wrm478iYNLw",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -884.8485157900423,
			"y": -140.4715403671397,
			"strokeColor": "#8b5a2b",
			"backgroundColor": "#8b5a2b",
			"width": 2.328896200422019,
			"height": 2.203009919318116,
			"seed": 1207591824,
			"groupIds": [
				"vwXpIK58G9TiXxc2xCLGv",
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 503,
			"versionNonce": 1186168208,
			"isDeleted": true,
			"id": "BQlmjpB7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -916.3270884937156,
			"y": -135.33232666602407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 67.76014709472656,
			"height": 20,
			"seed": 1611100560,
			"groupIds": [
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Notation",
			"rawText": "Notation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1123,
			"versionNonce": 1316545392,
			"isDeleted": true,
			"id": "Qzk7Auc3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1004.3069268777854,
			"y": -110.97632331880584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 231.90130615234375,
			"height": 97.36564090602582,
			"seed": 1329774480,
			"groupIds": [
				"ZyuCvhaACecllXdJn38aR"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 8.654723636091184,
			"fontFamily": 1,
			"text": "- A tree is an acyclic graph rooted at node V\n\n- a parse tree is a tree derived from a grammar with\n  some production rules.\n\n- Vi is the ith child of node V\n- |v| is the number of children of node v\n- T is the set of all possible trees\n",
			"rawText": "- A tree is an acyclic graph rooted at node V\n\n- a parse tree is a tree derived from a grammar with\n  some production rules.\n\n- Vi is the ith child of node V\n- |v| is the number of children of node v\n- T is the set of all possible trees\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- A tree is an acyclic graph rooted at node V\n\n- a parse tree is a tree derived from a grammar with\n  some production rules.\n\n- Vi is the ith child of node V\n- |v| is the number of children of node v\n- T is the set of all possible trees\n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 479021968,
			"isDeleted": true,
			"id": "UmDa8Kc3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -749.5476625995257,
			"y": -105.68205004594472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.49642944335938,
			"height": 60,
			"seed": 367283600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets give an example of a\nsentence tree derived from\na grammar",
			"rawText": "Lets give an example of a\nsentence tree derived from\na grammar",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets give an example of a\nsentence tree derived from\na grammar",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 94,
			"versionNonce": 912979312,
			"isDeleted": true,
			"id": "Ps-wpYwN8ptZzKowyi6DN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -513.3071895571657,
			"y": -131.17923951496738,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 113.08074992698471,
			"height": 134.56609241311182,
			"seed": 1831082896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "49ce4ade3aee7bb1c9b6af51e34e8772337aeff9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 128,
			"versionNonce": 1912428944,
			"isDeleted": true,
			"id": "UjFFDcb-jG-xXuS39XwG7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -731.7761518625443,
			"y": -39.637484366106946,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188.30697484093338,
			"height": 67.25249101461907,
			"seed": 658123152,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "255c620ae734545bed7478fe514b6edc6dbf57b4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 977979248,
			"isDeleted": true,
			"id": "yu90i8DB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -739.1815939525118,
			"y": 35.080355156937685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 195.71241760253906,
			"height": 20,
			"seed": 257849232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a Tree kernel is given by",
			"rawText": "a Tree kernel is given by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a Tree kernel is given by",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 134,
			"versionNonce": 2050729872,
			"isDeleted": true,
			"id": "8eWJkN3sQaO7dXI452sun",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -745.5792297520052,
			"y": 62.545704251213266,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 215.91313056674454,
			"height": 36.63126521850152,
			"seed": 1237910928,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64be02c1293114e088cc44da245f4864e6b72947",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 250,
			"versionNonce": 375413104,
			"isDeleted": true,
			"id": "jnHKEWLF5pUZ5YN_FbltA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -555.1516945049057,
			"y": 85.9659666714303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 41.81273448110551,
			"height": 15.29806786687854,
			"seed": 867292048,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "7UguO1O7",
				"focus": 0.6335959274600791,
				"gap": 3.1059587086074316
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					17.728085153862366,
					15.29806786687854
				],
				[
					41.81273448110551,
					0.8032022504730634
				]
			]
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 1098921360,
			"isDeleted": true,
			"id": "7UguO1O7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -510.2330013151927,
			"y": 67.48987971474389,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.97189158630464,
			"height": 50.513351279708786,
			"seed": 1129374096,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 10.102670255941762,
			"fontFamily": 1,
			"text": "number of\noccurances of \nsubtree t in\nz",
			"rawText": "number of\noccurances of \nsubtree t in\nz",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of\noccurances of \nsubtree t in\nz",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 198,
			"versionNonce": 1039379312,
			"isDeleted": true,
			"id": "vic7vJtQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -797.9066561576187,
			"y": 118.0032316423504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 331.3724365234375,
			"height": 40.228124237825526,
			"seed": 1742614416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 10.727499796753474,
			"fontFamily": 1,
			"text": "By definition k is an inner product in the space of all trees T\nand thus symmetric and PSD\nparse trees count the number of of shared subtrees",
			"rawText": "By definition k is an inner product in the space of all trees T\nand thus symmetric and PSD\nparse trees count the number of of shared subtrees",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "By definition k is an inner product in the space of all trees T\nand thus symmetric and PSD\nparse trees count the number of of shared subtrees",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 124,
			"versionNonce": 218301328,
			"isDeleted": true,
			"id": "kLMLAVGOyNI-1E7PB6FGj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -770.240618392193,
			"y": 162.7777496497171,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 265.2359065157716,
			"height": 34.22398793751891,
			"seed": 1771158928,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "34ca0d55460886c6e4fe7a6aa7490f1ce5eabc73",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 2068626800,
			"isDeleted": true,
			"id": "1fxVqX6i",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -770.2406192331841,
			"y": 207.40472333091378,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 260.8614587083116,
			"height": 13.996486397127633,
			"seed": 1235454864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 11.197189117702111,
			"fontFamily": 1,
			"text": "We can define this counting function recursively",
			"rawText": "We can define this counting function recursively",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can define this counting function recursively",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 235,
			"versionNonce": 989598096,
			"isDeleted": true,
			"id": "0rvX7rV-IHqY3YJ2KrFme",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -803.8435086599507,
			"y": 221.40120959744226,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 328.06723818033305,
			"height": 128.22169919719886,
			"seed": 575379856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dd5c3e16ab4f6724f9cdb69ee3e531d838c58c00",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 169,
			"versionNonce": 263425904,
			"isDeleted": true,
			"id": "WKjgyxbW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -858.6128933800687,
			"y": 367.6972637469788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 452.784912109375,
			"height": 40,
			"seed": 113371024,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can use dynamic programming to implement an efficient\nway of recursively doing this",
			"rawText": "We can use dynamic programming to implement an efficient\nway of recursively doing this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can use dynamic programming to implement an efficient\nway of recursively doing this",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 82,
			"versionNonce": 581132176,
			"isDeleted": true,
			"id": "AuJLsXzPVrNslTQZpd_pS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -702.6819376213548,
			"y": 419.91853397078876,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 140.92300061109609,
			"height": 28.18460012221922,
			"seed": 1665037712,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1b7549281e8a5b1a120a61be3c4cad75f7129c89",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "0DaVXcIb",
			"type": "text",
			"x": -2038.2645749964313,
			"y": 140.36282559838799,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1159977360,
			"version": 101,
			"versionNonce": 1399857520,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "9gBsPG65yB2wxrR7ZklPM",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 118,
			"versionNonce": 1949363600,
			"isDeleted": true,
			"id": "scYmLeB-MPjJ8Mj4Vn9_g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1470.2660002372077,
			"y": 394.5988642765765,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 284.5744597886346,
			"height": 35.92905661606864,
			"seed": 2128537488,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bc12ccfbb35a2fb7e055fc527a30e46e66291a14",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "4OELRE6q",
			"type": "text",
			"x": -1233.3651127083363,
			"y": 273.10337370476407,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1964402576,
			"version": 4,
			"versionNonce": 1439331184,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tSXiAudHo1RQAhnPWfvi8",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "XYu3Per7",
			"type": "text",
			"x": -1662.791498486702,
			"y": -245.18930164593715,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 972895632,
			"version": 4,
			"versionNonce": 417119120,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "GSRA8_xmlfsuovlV-X4Ck",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "keW1pevT",
			"type": "text",
			"x": -1946.656303816851,
			"y": 101.03297104171145,
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
			"seed": 340088720,
			"version": 4,
			"versionNonce": 2097841520,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772851,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ZHPkO_JQKUgQZxOgDG8AB",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "HiQETG21",
			"type": "text",
			"x": -609.8396011425825,
			"y": 353.3577462165603,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 2015203696,
			"version": 3,
			"versionNonce": 316590480,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772851,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rGbTDn9sXkBtlrBDETlE4",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "Zhh0bDe4",
			"type": "text",
			"x": -268.6488864029959,
			"y": 348.38828930103836,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1275552144,
			"version": 3,
			"versionNonce": 645420912,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772851,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "TtTV3l3I",
			"type": "text",
			"x": -636.8634121943337,
			"y": 137.8820334017075,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 173402992,
			"version": 3,
			"versionNonce": 1567561616,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182772851,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "eli6uqxz",
			"type": "text",
			"x": -569.0673342626029,
			"y": 787.4791291592505,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1352370576,
			"version": 2,
			"versionNonce": 1314622832,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717182790354,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tqG_KX1hW2sJ5iPaCFqGm",
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
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 1592.1180662574864,
		"scrollY": -181.37672962391787,
		"zoom": {
			"value": 0.9120582637281842
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