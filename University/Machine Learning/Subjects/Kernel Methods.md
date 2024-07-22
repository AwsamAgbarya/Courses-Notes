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

Structured Output ^JCLJfUpx

Structured Output  ^rmKf0avm

What is Structured output?
Unlike classical machine learning concepts like classification and regression
Structured output is the prediction and learning of complex structures that abide
by certain rules like trees orderings and alignments
to learn a structured prediction model, we train a function that scores the
compatibility between input 𝑥 and output 𝑦 ^hxMu7x3V

SVMs for Binary classification ^UUx3La8k

We have a Dataset {xn, yn} with yn being either +1 or -1 according to the class
we want to find the model that correctly separates both classes while having the
maximum margin ^uhFquhvV

Objective ^ljUz4gIV

Primal ^TA5Y3xDk

Dual ^29Wk5MNG

But there is never a clear separation between classes, Training points are allowed to
be misclassified but with a penalty that increases linearly with the distance to
the decision boundary. ^LCSdICp4

Prediction ^OmaYbNsl

Idea:
Instead of mapping x to a higher dimension, lets build a feature extractor that
maps x and y to higher dimensions that represents their features.
This leaves a design that is flexible and problem specific to combine properties
of x and y. ^8es9qafc

Problem:
prediction requires brute-force exhaustive search over 𝒴 which is not feasible ^ZcT9ll8b

Solution:
Decompose Y into non-overlapping parts/features such that their maps do not
intersect or combine different parts.
Our final solution combines the compatibilities that were computed on
each part separately ^IupYcLtg

Viterbi Algorithm ^uJbkonFP

The abstract idea is that we assume that Y decomposes into different independent
parts with connections, thus we can perform the map on each of them seperately ^t7fMdZyy

While this is given as a sum
it can also be given as a concatenation ^2JyXMM8R

Linear instead of exponential complexity ^A1dEPdJq

Soft-Margin SVM ^3DDqRtyz

This enables us to quantify the mismatch between
𝑦 and 𝑦𝑛 (incorrect predictions can vary in quality)
We want to give a bigger penalty for heavier violations ^O7kGTcvn

Slack Rescaling ^2CuenBTL

Margin Rescaling ^YQLM1vif

Normally Our magrin would look like this ^OfOHdnwD

But we want to reformulate our slack to scale
with the error of the prediction ^LCqskSmc

Normally our margin is fixed at 1 ^Yl2xAmQ2

But we want to have a bigger margin for higher loss so we focus
on separating them correctly and not such high margin on things we already
predict correctly ^6Hctkm1J

Kernels ^oyWrArz7

We can use the Kernel trick in this situation as well
to help simplify the computation of the mapping we do
We define the kernel as follows ^OoO72mKi

Which turns our dual formulation into ^vhOM32hl

But how do we construct a valid kernel for a feature map that involves
2 parameters?
Kernels and combineable! Given 2 kernels we can use the following rules ^Iw6Kx7Th

Anomaly Detection ^lPVxnLX3

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
a6169de55e8e82aad150967864c656048502b2d6: [[Pasted Image 20240628164435_031.png]]
89d6dbae18990de98c7938f197565e12eab63015: [[Pasted Image 20240628164640_064.png]]
ec7e85833abce9b32c0b6184f0dc99f73a083f6e: [[Pasted Image 20240628165101_101.png]]
d64f54449b3de54304c661a4869b2e76934e4e94: [[Pasted Image 20240628165116_114.png]]
b91ca87702b1be4a00819345eb420f7a51f17874: [[Pasted Image 20240628165132_116.png]]
6b2a9597ce543195856953dae5637ad10566b002: [[Pasted Image 20240628165149_119.png]]
ed329516302155e72701839a4807b8743e22c14a: [[Pasted Image 20240628165334_127.png]]
5461d55eb29b67a77717a9fac4187fb302f86f82: [[Pasted Image 20240628165350_129.png]]
582779975618060c59ca423bf235266e315ed4f4: [[Pasted Image 20240628165537_143.png]]
7013525b3adfe23d3b68d2afbc428b4f668602a8: [[Pasted Image 20240628165622_148.png]]
39868d05aa368db198e299d6c51d2df2717c5602: [[Pasted Image 20240628170329_234.png]]
dc3b52b940d1f47041b24da2e8c05298aa0e0318: [[Pasted Image 20240628170329_249.png]]
3e15ae2d507e7c8d161838abd5bd0d1b41d88d39: [[Pasted Image 20240628170400_252.png]]
70be5d28c802bb42b8943299b2e6258ad889eda2: [[Pasted Image 20240628170556_276.png]]
54268537edffdbf7d0d8cae83584e74138cc5ee2: [[Pasted Image 20240628170938_327.png]]
3d4e85bad13a376b03ed2d74920abbbe6dfa1e8f: [[Pasted Image 20240628171108_348.png]]
b096a6f7298dbd48d51124486e2c56a79ffcc2d0: [[Pasted Image 20240628171123_381.png]]
03c7edd2c76705d65be3d2a64b4094198dabcc2f: [[Pasted Image 20240628171258_391.png]]
20028bb1bbfa6a9b6b0ec015d9d89c6a3e7d9ddd: [[Pasted Image 20240628171343_418.png]]
0fa5ec4d6a8f2600579dd429d2b71167a995c239: [[Pasted Image 20240628171358_419.png]]
f24a8b983915901d1baf1721a2aeb8c89fa467d8: [[Pasted Image 20240628171550_445.png]]
4dc14161889ed7cb7093609d276c15072fbfef09: [[Pasted Image 20240628171605_447.png]]
86b2c9539d79d6db418cee0eff4c4cb15e54caf7: [[Pasted Image 20240628171650_451.png]]
9ae2cb58b3d91eb3cf7f74e67ba7d550f83c5f4c: [[Pasted Image 20240628171750_457.png]]

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
			"version": 454,
			"versionNonce": 2043048207,
			"isDeleted": false,
			"id": "TELfGTxu1ZGAnv7jRLCM5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5460085333419151,
			"x": -48.49838915261398,
			"y": -49.6726518725971,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 179.48068126838757,
			"height": 62.098801113956895,
			"seed": 368200560,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1719577402673,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					146.15937335358143,
					-3.029209810436936
				],
				[
					179.48068126838757,
					32.56400546219689
				],
				[
					137.82904637487988,
					59.06959130351996
				],
				[
					0.7573024526092225,
					34.07861036741534
				],
				[
					0,
					0
				]
			]
		},
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
			"version": 397,
			"versionNonce": 1352534735,
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
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 369,
			"versionNonce": 827447535,
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
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 648,
			"versionNonce": 671592833,
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
				"DCY2LQ9QnSv57sS2UFw-0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 488,
			"versionNonce": 44491535,
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
				"DCY2LQ9QnSv57sS2UFw-0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 802,
			"versionNonce": 167237985,
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
				"DCY2LQ9QnSv57sS2UFw-0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 214,
			"versionNonce": 353741103,
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
				"DCY2LQ9QnSv57sS2UFw-0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 331,
			"versionNonce": 794297665,
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
				"DCY2LQ9QnSv57sS2UFw-0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1719577375439,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 248,
			"versionNonce": 369535823,
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
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1719577375439,
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
			"version": 117,
			"versionNonce": 864531745,
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
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1719577375439,
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
			"type": "text",
			"version": 761,
			"versionNonce": 1124477328,
			"isDeleted": false,
			"id": "huuhS9Jf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1709.6013349970394,
			"y": -136.29462176628573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 250.30738830566406,
			"height": 97.36564090602582,
			"seed": 664204656,
			"groupIds": [
				"SdyNK2vaVK4cT-Ja2xMnm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 8.654723636091184,
			"fontFamily": 1,
			"text": "- an Alphabet is a finite set of discrete symbols\n\n- a Natural language involves letters and numbers\n\n- a string is a concatenation of symbols from an alphabet\n\n- A^L = all strings of length L from alphabet A\n\n- A^* = all strings of any length from alphabet A ",
			"rawText": "- an Alphabet is a finite set of discrete symbols\n\n- a Natural language involves letters and numbers\n\n- a string is a concatenation of symbols from an alphabet\n\n- A^L = all strings of length L from alphabet A\n\n- A^* = all strings of any length from alphabet A ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- an Alphabet is a finite set of discrete symbols\n\n- a Natural language involves letters and numbers\n\n- a string is a concatenation of symbols from an alphabet\n\n- A^L = all strings of length L from alphabet A\n\n- A^* = all strings of any length from alphabet A ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 255,
			"versionNonce": 1995896688,
			"isDeleted": false,
			"id": "rdec9J5h",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1546.5152243194782,
			"y": -29.06264197910161,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 437.0729064941406,
			"height": 80,
			"seed": 1765668720,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Approach 1:\nCount the number of matching symbols\nProblem 1:\nDoesnt take into account a slight shift in the position",
			"rawText": "Approach 1:\nCount the number of matching symbols\nProblem 1:\nDoesnt take into account a slight shift in the position",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 1:\nCount the number of matching symbols\nProblem 1:\nDoesnt take into account a slight shift in the position",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 1370126224,
			"isDeleted": false,
			"id": "yZdX2QYJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1438.4540567002928,
			"y": -122.66656545480761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 250.3525390625,
			"height": 80,
			"seed": 1635467120,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We are gonna start with simple\nideas on how to compare\ntwo strings and build upon them\naccording to the situation",
			"rawText": "We are gonna start with simple\nideas on how to compare\ntwo strings and build upon them\naccording to the situation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We are gonna start with simple\nideas on how to compare\ntwo strings and build upon them\naccording to the situation",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 698,
			"versionNonce": 1309051248,
			"isDeleted": false,
			"id": "ol9b5BrpvUv03MRNrEIDU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1330.4922415905748,
			"y": 105.01278830981937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 1.9913533293558885,
			"height": 41.733409213445725,
			"seed": 716835728,
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
				"elementId": "49SklR98XtpxyjdJM8GOg",
				"focus": 0.002110940105037915,
				"gap": 6.462176702805603
			},
			"endBinding": {
				"elementId": "xqd16O5J",
				"focus": -0.0031099038576203977,
				"gap": 4.6131144144776215
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
					1.9913533293558885,
					41.733409213445725
				]
			]
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
			"type": "image",
			"version": 71,
			"versionNonce": 22272880,
			"isDeleted": false,
			"id": "49SklR98XtpxyjdJM8GOg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1408.2352728932422,
			"y": 50.93735781924934,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 152.92256804776093,
			"height": 47.6132537877644,
			"seed": 744774032,
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
			"status": "pending",
			"fileId": "8daa979fc9d2dd99a1047c56c17da18ad49bbaf0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 199,
			"versionNonce": 1392366480,
			"isDeleted": false,
			"id": "xZ2hYHJ33SQlHAljGwLfM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1493.2295856364995,
			"y": 230.943394746621,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 334.48449320273846,
			"height": 42.23046686060399,
			"seed": 1223429488,
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
			"type": "arrow",
			"version": 157,
			"versionNonce": 1019723632,
			"isDeleted": false,
			"id": "tSXiAudHo1RQAhnPWfvi8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1236.8516100910574,
			"y": 262.723443394005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 106.61286698242293,
			"height": 20.37993031075905,
			"seed": 1827078544,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "WH8HD2FS",
				"focus": 0.15572663467430525,
				"gap": 9.005074033131109
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
					7.4865050121156855,
					20.37993031075905
				],
				[
					106.61286698242293,
					12.893425298643479
				]
			]
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 606744464,
			"isDeleted": false,
			"id": "WH8HD2FS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1121.2336690755033,
			"y": 262.86217844378984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 43.63226318359375,
			"height": 25.304171871101538,
			"seed": 1949545328,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tSXiAudHo1RQAhnPWfvi8",
					"type": "arrow"
				}
			],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 10.121668748440616,
			"fontFamily": 1,
			"text": "different\nweights",
			"rawText": "different\nweights",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "different\nweights",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 780030320,
			"isDeleted": false,
			"id": "GiB9snmqx_qAGEpgdVnNJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1535.285501986671,
			"y": 414.5988652472552,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 191.8111748525249,
			"height": 102.02722066623666,
			"seed": 1143248240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "image",
			"version": 107,
			"versionNonce": 1012776336,
			"isDeleted": false,
			"id": "YqMtXD1AkLM382q2h2Xr1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1317.5508496943862,
			"y": 420.3370687884113,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 217.82853363445477,
			"height": 90.55081485385764,
			"seed": 370048368,
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
			"type": "image",
			"version": 153,
			"versionNonce": 776779120,
			"isDeleted": false,
			"id": "ZclUv0z8dJCN3xHvahXig",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1568.2164240326151,
			"y": 640.7022682655378,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 224.742097301453,
			"height": 44.35043605283662,
			"seed": 1695809392,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "image",
			"version": 145,
			"versionNonce": 840407440,
			"isDeleted": false,
			"id": "Bslp6pS-NG6h5tTaweFS0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1343.4743272923133,
			"y": 636.1906235831768,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 272.1226848154926,
			"height": 62.596911523052626,
			"seed": 1592920432,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "text",
			"version": 86,
			"versionNonce": 1341425520,
			"isDeleted": false,
			"id": "OZcKqdB6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1617.001896552789,
			"y": 721.1556705690323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 594.410400390625,
			"height": 18.43984743138015,
			"seed": 1925679472,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772848,
			"link": null,
			"locked": false,
			"fontSize": 14.751877945104122,
			"fontFamily": 1,
			"text": "build sorted lists before performing the kernel evaluations to reduce computation",
			"rawText": "build sorted lists before performing the kernel evaluations to reduce computation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "build sorted lists before performing the kernel evaluations to reduce computation",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 512,
			"versionNonce": 1024321424,
			"isDeleted": false,
			"id": "GSRA8_xmlfsuovlV-X4Ck",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1349.9265965756956,
			"y": -332.03444438784675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 688.1750682897498,
			"height": 168.2807017972484,
			"seed": 1029690768,
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
				"gap": 2.978663522102366,
				"focus": -0.14961038941600016
			},
			"endBinding": {
				"elementId": "9gBsPG65yB2wxrR7ZklPM",
				"gap": 2.737399287049925,
				"focus": -0.5065343659244929
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
			]
		},
		{
			"type": "rectangle",
			"version": 250,
			"versionNonce": 1355946352,
			"isDeleted": false,
			"id": "9gBsPG65yB2wxrR7ZklPM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2293.6331498150234,
			"y": -161.0163433035484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 518.7371648959731,
			"height": 622.7583378038728,
			"seed": 544268688,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
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
			"type": "text",
			"version": 35,
			"versionNonce": 1879733648,
			"isDeleted": false,
			"id": "eAqAtVXi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2126.999175830925,
			"y": -152.36904045599732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174.66476440429688,
			"height": 35,
			"seed": 884205424,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Tree Kernels",
			"rawText": "Tree Kernels",
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
			"width": 232.3177947998047,
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
			"type": "text",
			"version": 98,
			"versionNonce": 643962736,
			"isDeleted": false,
			"id": "Ii80uBC2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2151.5917917997494,
			"y": -111.32447545079162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.49642944335938,
			"height": 60,
			"seed": 1059117936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
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
			"version": 62,
			"versionNonce": 2046908304,
			"isDeleted": false,
			"id": "E7yoz-5bGrvXRTvVKWZLG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1915.3513187573894,
			"y": -136.82166491981428,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 113.08074992698471,
			"height": 134.56609241311182,
			"seed": 1146934160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "image",
			"version": 96,
			"versionNonce": 588097904,
			"isDeleted": false,
			"id": "0GGM9bFTcM1kYmvSrLdor",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2133.820281062768,
			"y": -45.279909770953836,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188.30697484093338,
			"height": 67.25249101461907,
			"seed": 994018704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "text",
			"version": 78,
			"versionNonce": 487581072,
			"isDeleted": false,
			"id": "beE1N8Z3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2141.2257231527356,
			"y": 29.43792975209079,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 195.71241760253906,
			"height": 20,
			"seed": 142123408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
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
			"version": 102,
			"versionNonce": 1752628080,
			"isDeleted": false,
			"id": "oa3pSFBLOlR98GVUVuumo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2147.623358952229,
			"y": 56.90327884636636,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 215.91313056674454,
			"height": 36.63126521850152,
			"seed": 1015265136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "arrow",
			"version": 186,
			"versionNonce": 991736720,
			"isDeleted": false,
			"id": "ZHPkO_JQKUgQZxOgDG8AB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1957.1958237051294,
			"y": 80.32354126658339,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 41.81273448110551,
			"height": 15.29806786687854,
			"seed": 1532386192,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "35SvLz5z",
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
			"version": 171,
			"versionNonce": 417729904,
			"isDeleted": false,
			"id": "35SvLz5z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1912.2771305154165,
			"y": 61.84745430989699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.90602111816406,
			"height": 50.51335127970881,
			"seed": 1520550768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZHPkO_JQKUgQZxOgDG8AB",
					"type": "arrow"
				}
			],
			"updated": 1717182772849,
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
			"version": 166,
			"versionNonce": 1516224912,
			"isDeleted": false,
			"id": "BHJwkCLr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2199.9507853578425,
			"y": 112.3608062375035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 331.3724365234375,
			"height": 40.228124237825526,
			"seed": 514344336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
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
			"version": 92,
			"versionNonce": 1302519664,
			"isDeleted": false,
			"id": "q2S7YL9O0VpoxobnmGTdC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2172.284747592417,
			"y": 157.1353242448702,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 265.2359065157716,
			"height": 34.22398793751891,
			"seed": 1864052080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "text",
			"version": 133,
			"versionNonce": 2047938448,
			"isDeleted": false,
			"id": "m2oW2eP2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2172.284748433408,
			"y": 201.76229792606688,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 260.6365661621094,
			"height": 13.996486397127638,
			"seed": 930449776,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
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
			"version": 203,
			"versionNonce": 922055024,
			"isDeleted": false,
			"id": "fsqeB6wJZD5F680ozMDlR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2205.8876378601744,
			"y": 215.75878419259536,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 328.06723818033305,
			"height": 128.22169919719886,
			"seed": 2078664592,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "text",
			"version": 137,
			"versionNonce": 1919458704,
			"isDeleted": false,
			"id": "kxCZSFRV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2260.6570225802925,
			"y": 362.0548383421319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 452.784912109375,
			"height": 40,
			"seed": 99428208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
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
			"version": 50,
			"versionNonce": 1009107824,
			"isDeleted": false,
			"id": "RtVejH2qIqFVeiLqgb8Gm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2104.7260668215786,
			"y": 414.27610856594185,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 140.92300061109609,
			"height": 28.18460012221922,
			"seed": 1558510992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "text",
			"version": 62,
			"versionNonce": 171943792,
			"isDeleted": false,
			"id": "W0qtWmSa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -890.4533167228548,
			"y": -66.3692844872242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 504.41693115234375,
			"height": 40,
			"seed": 371701104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Certain machine learning models already\nexist for structured data for example markov models and GNN",
			"rawText": "Certain machine learning models already\nexist for structured data for example markov models and GNN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Certain machine learning models already\nexist for structured data for example markov models and GNN",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 28,
			"versionNonce": 2021967760,
			"isDeleted": false,
			"id": "38WHDc2l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -884.1661993754758,
			"y": -19.062641761225105,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 508.9770202636719,
			"height": 60,
			"seed": 1633398160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Idea:\nDo not build a new kernel directly on the input data, extract a\nkernel from local response of the existing model",
			"rawText": "Idea:\nDo not build a new kernel directly on the input data, extract a\nkernel from local response of the existing model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea:\nDo not build a new kernel directly on the input data, extract a\nkernel from local response of the existing model",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 96,
			"versionNonce": 1421425008,
			"isDeleted": false,
			"id": "1xYCETdz0Ibzgmvi_weJX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -739.4719746785199,
			"y": 48.879687037190905,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 236.11643394646003,
			"height": 36.974276744363245,
			"seed": 1019071376,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "image",
			"version": 63,
			"versionNonce": 1504007568,
			"isDeleted": false,
			"id": "k5vYiCxcnQzjVxzqzXNyL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -698.8553643549793,
			"y": 92.52491865049832,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 140.26463871574265,
			"height": 32.27327970450716,
			"seed": 695080304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "line",
			"version": 61,
			"versionNonce": 2117110640,
			"isDeleted": false,
			"id": "J1F4AqxU3I4Xzzimi8RdV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -794.0399707053606,
			"y": 132.9218913079311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 312.75805080648513,
			"height": 1.2713741902702793,
			"seed": 1453145456,
			"groupIds": [],
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
					312.75805080648513,
					-1.2713741902702793
				]
			]
		},
		{
			"type": "text",
			"version": 54,
			"versionNonce": 595862416,
			"isDeleted": false,
			"id": "eTMk9a8c",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -889.0513609076858,
			"y": 181.7406612087028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 517.2344970703125,
			"height": 60,
			"seed": 1192035696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772849,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Suppose x ∈ X and we have some generative model for the data\nThe Fisher Kernel is built as follows. It computes the gradient\nof the locally evaluated function w.r.t. the model parameters.",
			"rawText": "Suppose x ∈ X and we have some generative model for the data\nThe Fisher Kernel is built as follows. It computes the gradient\nof the locally evaluated function w.r.t. the model parameters.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Suppose x ∈ X and we have some generative model for the data\nThe Fisher Kernel is built as follows. It computes the gradient\nof the locally evaluated function w.r.t. the model parameters.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 75,
			"versionNonce": 1626185072,
			"isDeleted": false,
			"id": "1b3lLcXQQfC8LFRRFpcoO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -687.6043858262407,
			"y": 248.7252705852955,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 117.76268255879424,
			"height": 35.55099850831524,
			"seed": 1309839216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "image",
			"version": 82,
			"versionNonce": 609825168,
			"isDeleted": false,
			"id": "GHhuBESWkoaf9nLy5NoJR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -766.4342100839555,
			"y": 299.4570683771535,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 258.45480148789903,
			"height": 30.28359290161241,
			"seed": 1979159952,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
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
			"type": "arrow",
			"version": 91,
			"versionNonce": 1312321392,
			"isDeleted": false,
			"id": "rGbTDn9sXkBtlrBDETlE4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -610.2960314816178,
			"y": 335.3458504150009,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 81.48915142271812,
			"height": 28.011895801559433,
			"seed": 1494638960,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
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
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
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
			]
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 593264528,
			"isDeleted": false,
			"id": "Akh5mwMr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -521.6028136433895,
			"y": 340.11953562848737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 137.60897827148438,
			"height": 54.058895292328344,
			"seed": 1234924400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rGbTDn9sXkBtlrBDETlE4",
					"type": "arrow"
				}
			],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 8.649423246772535,
			"fontFamily": 1,
			"text": "Normalization term to not\nallow the matrix to blow up.\nthe middle term is basically an\nexpectation over the covariance\nmatrix of the Gradients",
			"rawText": "Normalization term to not\nallow the matrix to blow up.\nthe middle term is basically an\nexpectation over the covariance\nmatrix of the Gradients",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normalization term to not\nallow the matrix to blow up.\nthe middle term is basically an\nexpectation over the covariance\nmatrix of the Gradients",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 52,
			"versionNonce": 777585008,
			"isDeleted": false,
			"id": "kapWlQmJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -682.9411977974434,
			"y": 142.68185031146422,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.78421020507812,
			"height": 40,
			"seed": 321609584,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "For example:\nFisher Kernel",
			"rawText": "For example:\nFisher Kernel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For example:\nFisher Kernel",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 65,
			"versionNonce": 347303312,
			"isDeleted": false,
			"id": "acVmYjI_KnPnfolcAroLD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -639.3518898386766,
			"y": 405.4211649133151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.13012660108176988,
			"height": 112.00554872383736,
			"seed": 40074608,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182796369,
			"link": null,
			"locked": false,
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
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-0.13012660108176988,
					112.00554872383736
				]
			]
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
			"type": "text",
			"version": 51,
			"versionNonce": 1439554448,
			"isDeleted": false,
			"id": "muQyW96m",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -754.9651542338015,
			"y": 532.6378859658678,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 230.49696350097656,
			"height": 35,
			"seed": 843838320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Diffusion Kernels",
			"rawText": "Diffusion Kernels",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Diffusion Kernels",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 456877424,
			"isDeleted": false,
			"id": "DhQa3WFn",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -873.8555512238726,
			"y": 577.3531781679294,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 465.74493408203125,
			"height": 80,
			"seed": 913517936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182772850,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Diffusion kernels assume that the input domain is discrete\nand that the local geometry is given by a graph\nthe diffusion kernel defines the generator matrix which is\nbasically the graph laplacian in a way.",
			"rawText": "Diffusion kernels assume that the input domain is discrete\nand that the local geometry is given by a graph\nthe diffusion kernel defines the generator matrix which is\nbasically the graph laplacian in a way.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Diffusion kernels assume that the input domain is discrete\nand that the local geometry is given by a graph\nthe diffusion kernel defines the generator matrix which is\nbasically the graph laplacian in a way.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 70,
			"versionNonce": 1420552592,
			"isDeleted": false,
			"id": "8Ei9ebQceV8e4CrA42cEQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -739.3250361348823,
			"y": 659.5304966254834,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 199.28140664862056,
			"height": 61.62517394354933,
			"seed": 211519344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "text",
			"version": 13,
			"versionNonce": 431510896,
			"isDeleted": false,
			"id": "p1g48QWI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -888.4717084321903,
			"y": 734.2011147279383,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 495.55303955078125,
			"height": 20,
			"seed": 1097935216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182775240,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "then diffuses the graph signal by matrix exponentiation. Kernel",
			"rawText": "then diffuses the graph signal by matrix exponentiation. Kernel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "then diffuses the graph signal by matrix exponentiation. Kernel",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 25,
			"versionNonce": 216803184,
			"isDeleted": false,
			"id": "g1xA1k8K",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -739.1913968477177,
			"y": 764.2011147279383,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 196.99241638183594,
			"height": 20,
			"seed": 681862544,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182775240,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "scores are then given by:",
			"rawText": "scores are then given by:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scores are then given by:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 67,
			"versionNonce": 723324304,
			"isDeleted": false,
			"id": "O7Ps5e8MHQoAXwxtFEZQT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -744.635007386615,
			"y": 811.0171259944254,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 197.7334738255108,
			"height": 42.47092219491605,
			"seed": 532482928,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"type": "arrow",
			"version": 89,
			"versionNonce": 174831472,
			"isDeleted": false,
			"id": "tqG_KX1hW2sJ5iPaCFqGm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -594.286633885858,
			"y": 814.1758761607646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 91.74378576551908,
			"height": 19.960871663247985,
			"seed": 1430448528,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717182802172,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "y2JZ7f0l",
				"focus": 1.2315449679956545,
				"gap": 4.776762495389619
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
					29.219307252649628,
					-16.69674700151404
				],
				[
					91.74378576551908,
					-19.960871663247985
				]
			]
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1293276016,
			"isDeleted": false,
			"id": "y2JZ7f0l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -498.21026201494385,
			"y": 796.2265107929824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 87.43901062011719,
			"height": 14.759438976790474,
			"seed": 755691888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tqG_KX1hW2sJ5iPaCFqGm",
					"type": "arrow"
				}
			],
			"updated": 1717182802124,
			"link": null,
			"locked": false,
			"fontSize": 11.807551181432379,
			"fontFamily": 1,
			"text": "hyperparameter",
			"rawText": "hyperparameter",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "hyperparameter",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 1784855952,
			"isDeleted": false,
			"id": "8rxyNbQC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -880.9837025633826,
			"y": 862.7466710279487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 480.5770263671875,
			"height": 20,
			"seed": 164867440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182829045,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the diffusion kernel is particularly useful for semi-supervised",
			"rawText": "the diffusion kernel is particularly useful for semi-supervised",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the diffusion kernel is particularly useful for semi-supervised",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 992625552,
			"isDeleted": false,
			"id": "H8UAm5cw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -863.7116688719764,
			"y": 892.7466710279487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 446.032958984375,
			"height": 20,
			"seed": 1889280400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717182835656,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "learning, or for unsupervised analyses such as clustering",
			"rawText": "learning, or for unsupervised analyses such as clustering",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "learning, or for unsupervised analyses such as clustering",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 108,
			"versionNonce": 1938749808,
			"isDeleted": false,
			"id": "sAiiC01CeLW0AlRBjVHzR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -820.7429376663084,
			"y": 922.7466714311741,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 359.519707657755,
			"height": 149.4898502208163,
			"seed": 1610260368,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
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
			"id": "JCLJfUpx",
			"type": "text",
			"x": -31.782707618659288,
			"y": -39.0329079735522,
			"width": 149.39231872558594,
			"height": 20,
			"angle": 0.5997107546648444,
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
			"seed": 859092847,
			"version": 62,
			"versionNonce": 518353665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719577437606,
			"link": null,
			"locked": false,
			"text": "Structured Output",
			"rawText": "Structured Output",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Structured Output",
			"lineHeight": 1.25
		},
		{
			"id": "rmKf0avm",
			"type": "text",
			"x": 1133.7816529414877,
			"y": 693.4887822972232,
			"width": 354.1321716308594,
			"height": 45,
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
			"seed": 1898408577,
			"version": 203,
			"versionNonce": 2011487649,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Structured Output ",
			"rawText": "Structured Output ",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Structured Output ",
			"lineHeight": 1.25
		},
		{
			"id": "hxMu7x3V",
			"type": "text",
			"x": 880.7242419928748,
			"y": 753.2181358016248,
			"width": 820.3590087890625,
			"height": 150,
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
			"seed": 1544125601,
			"version": 414,
			"versionNonce": 429556097,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "What is Structured output?\nUnlike classical machine learning concepts like classification and regression\nStructured output is the prediction and learning of complex structures that abide\nby certain rules like trees orderings and alignments\nto learn a structured prediction model, we train a function that scores the\ncompatibility between input 𝑥 and output 𝑦",
			"rawText": "What is Structured output?\nUnlike classical machine learning concepts like classification and regression\nStructured output is the prediction and learning of complex structures that abide\nby certain rules like trees orderings and alignments\nto learn a structured prediction model, we train a function that scores the\ncompatibility between input 𝑥 and output 𝑦",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is Structured output?\nUnlike classical machine learning concepts like classification and regression\nStructured output is the prediction and learning of complex structures that abide\nby certain rules like trees orderings and alignments\nto learn a structured prediction model, we train a function that scores the\ncompatibility between input 𝑥 and output 𝑦",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 244,
			"versionNonce": 92945953,
			"isDeleted": false,
			"id": "NDLXcOZ7KnV2Qp4aHmFmH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1379.4387512561143,
			"y": -263.1683526063099,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 874.9051434712972,
			"height": 893.8905434949543,
			"seed": 1485160481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1719586107546,
			"link": null,
			"locked": false
		},
		{
			"id": "UUx3La8k",
			"type": "text",
			"x": 1609.70447883743,
			"y": -251.4072267756218,
			"width": 414.3736877441406,
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
			"seed": 1395044193,
			"version": 192,
			"versionNonce": 1846987311,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719585951739,
			"link": null,
			"locked": false,
			"text": "SVMs for Binary classification",
			"rawText": "SVMs for Binary classification",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SVMs for Binary classification",
			"lineHeight": 1.25
		},
		{
			"id": "THUrIGVhA7yVac4soaqmG",
			"type": "image",
			"x": 1470.5313536592132,
			"y": -111.47667555707967,
			"width": 278.3462509399163,
			"height": 213.37756078918068,
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
			"seed": 2002605345,
			"version": 304,
			"versionNonce": 33502721,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586026255,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a6169de55e8e82aad150967864c656048502b2d6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "uhFquhvV",
			"type": "text",
			"x": 1408.0017967220128,
			"y": -206.80518105385187,
			"width": 817.779052734375,
			"height": 75,
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
			"seed": 1380978337,
			"version": 235,
			"versionNonce": 879466945,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719585983393,
			"link": null,
			"locked": false,
			"text": "We have a Dataset {xn, yn} with yn being either +1 or -1 according to the class\nwe want to find the model that correctly separates both classes while having the\nmaximum margin",
			"rawText": "We have a Dataset {xn, yn} with yn being either +1 or -1 according to the class\nwe want to find the model that correctly separates both classes while having the\nmaximum margin",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We have a Dataset {xn, yn} with yn being either +1 or -1 according to the class\nwe want to find the model that correctly separates both classes while having the\nmaximum margin",
			"lineHeight": 1.25
		},
		{
			"id": "yFThLlsVdPsmjZuPBKZ3U",
			"type": "image",
			"x": 1870.0848447089083,
			"y": -106.7871618932327,
			"width": 307.9866452484538,
			"height": 203.9985343988836,
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
			"seed": 2125154127,
			"version": 169,
			"versionNonce": 1415536655,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586021341,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "89d6dbae18990de98c7938f197565e12eab63015",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ljUz4gIV",
			"type": "text",
			"x": 1748.6150597631513,
			"y": 194.36697808972104,
			"width": 125.02052307128906,
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
			"seed": 1531414945,
			"version": 237,
			"versionNonce": 50537601,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586237536,
			"link": null,
			"locked": false,
			"text": "Objective",
			"rawText": "Objective",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Objective",
			"lineHeight": 1.25
		},
		{
			"id": "TA5Y3xDk",
			"type": "text",
			"x": 1770.9031603444894,
			"y": 297.3906828622393,
			"width": 80.44432067871094,
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
			"seed": 402498977,
			"version": 185,
			"versionNonce": 205509857,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586253280,
			"link": null,
			"locked": false,
			"text": "Primal",
			"rawText": "Primal",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Primal",
			"lineHeight": 1.25
		},
		{
			"id": "29Wk5MNG",
			"type": "text",
			"x": 1784.9991953921053,
			"y": 404.707955028009,
			"width": 63.78425598144531,
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
			"seed": 1681000655,
			"version": 159,
			"versionNonce": 306302479,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586293786,
			"link": null,
			"locked": false,
			"text": "Dual",
			"rawText": "Dual",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dual",
			"lineHeight": 1.25
		},
		{
			"id": "LCSdICp4",
			"type": "text",
			"x": 1395.3048327130314,
			"y": 101.90088524320265,
			"width": 859.0390625,
			"height": 75,
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
			"seed": 780346063,
			"version": 140,
			"versionNonce": 1618785551,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586228556,
			"link": null,
			"locked": false,
			"text": "But there is never a clear separation between classes, Training points are allowed to\nbe misclassified but with a penalty that increases linearly with the distance to\nthe decision boundary.",
			"rawText": "But there is never a clear separation between classes, Training points are allowed to\nbe misclassified but with a penalty that increases linearly with the distance to\nthe decision boundary.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But there is never a clear separation between classes, Training points are allowed to\nbe misclassified but with a penalty that increases linearly with the distance to\nthe decision boundary.",
			"lineHeight": 1.25
		},
		{
			"id": "JDP8A7jfDgA0l_OCiF43X",
			"type": "image",
			"x": 1527.5855888305514,
			"y": 231.5480011775337,
			"width": 567.0794649738709,
			"height": 48.51315654111728,
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
			"seed": 1855465327,
			"version": 93,
			"versionNonce": 1288269665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586251062,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ec7e85833abce9b32c0b6184f0dc99f73a083f6e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "MDnhx3xnXm5TqYlm5t703",
			"type": "image",
			"x": 1493.906011821842,
			"y": 344.23859656244576,
			"width": 645.970622339814,
			"height": 48.621444692244054,
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
			"seed": 39098479,
			"version": 103,
			"versionNonce": 1436145953,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586268833,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d64f54449b3de54304c661a4869b2e76934e4e94",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "7wYzgL_ULRyoEjA4j7AyI",
			"type": "image",
			"x": 1626.8169625192666,
			"y": 441.93989631108553,
			"width": 380.1487218009979,
			"height": 82.77431845666891,
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
			"seed": 1860348111,
			"version": 89,
			"versionNonce": 108793743,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586295058,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b91ca87702b1be4a00819345eb420f7a51f17874",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "OmaYbNsl",
			"type": "text",
			"x": 1750.629047402676,
			"y": 529.2405639176533,
			"width": 132.52455139160156,
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
			"seed": 811237615,
			"version": 26,
			"versionNonce": 321460015,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586296341,
			"link": null,
			"locked": false,
			"text": "Prediction",
			"rawText": "Prediction",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prediction",
			"lineHeight": 1.25
		},
		{
			"id": "arwrmiDslDGGlKH4ET0Vg",
			"type": "image",
			"x": 1705.0397876661998,
			"y": 568.7669131575011,
			"width": 223.70306977802355,
			"height": 46.19237429044734,
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
			"seed": 1482839919,
			"version": 43,
			"versionNonce": 1470470561,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719586307317,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6b2a9597ce543195856953dae5637ad10566b002",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "UfjnuBKJMZ2xs08uEvSfI",
			"type": "image",
			"x": 1149.0025835109232,
			"y": 917.9474899216025,
			"width": 283.8023261091711,
			"height": 83.86449893590067,
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
			"seed": 1410963855,
			"version": 179,
			"versionNonce": 1622190433,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ed329516302155e72701839a4807b8743e22c14a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "KIQXPFZRhyatspRpUJGBp",
			"type": "image",
			"x": 1149.0025837895103,
			"y": 1001.8119893657886,
			"width": 238.77416489316784,
			"height": 53.70604316746024,
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
			"seed": 1305241423,
			"version": 214,
			"versionNonce": 1450628417,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5461d55eb29b67a77717a9fac4187fb302f86f82",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8es9qafc",
			"type": "text",
			"x": 878.98858879356,
			"y": 1087.254950485423,
			"width": 801.1790771484375,
			"height": 125,
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
			"seed": 1983282209,
			"version": 423,
			"versionNonce": 776766753,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "2QWzRxFVSqC-ATRBqEh5W",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Idea:\nInstead of mapping x to a higher dimension, lets build a feature extractor that\nmaps x and y to higher dimensions that represents their features.\nThis leaves a design that is flexible and problem specific to combine properties\nof x and y.",
			"rawText": "Idea:\nInstead of mapping x to a higher dimension, lets build a feature extractor that\nmaps x and y to higher dimensions that represents their features.\nThis leaves a design that is flexible and problem specific to combine properties\nof x and y.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea:\nInstead of mapping x to a higher dimension, lets build a feature extractor that\nmaps x and y to higher dimensions that represents their features.\nThis leaves a design that is flexible and problem specific to combine properties\nof x and y.",
			"lineHeight": 1.25
		},
		{
			"id": "MCN8D8A-3YaFHp1YDsQWu",
			"type": "image",
			"x": 1188.1162958290154,
			"y": 1218.3551048387544,
			"width": 160.54674027933817,
			"height": 27.843899605641674,
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
			"seed": 289411041,
			"version": 261,
			"versionNonce": 1475637473,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "582779975618060c59ca423bf235266e315ed4f4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "DEvqyEMmqZHi8iCExfI23",
			"type": "image",
			"x": 1113.377463595833,
			"y": 1250.0920227257848,
			"width": 310.0244061858248,
			"height": 67.03230404017832,
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
			"seed": 1080856591,
			"version": 222,
			"versionNonce": 1356180673,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "IlYhwDWI3KV7DZ93w3VFn",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7013525b3adfe23d3b68d2afbc428b4f668602a8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZcT9ll8b",
			"type": "text",
			"x": 1790.3698180936594,
			"y": 1190.1042164315431,
			"width": 771.3591918945312,
			"height": 50,
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
			"seed": 119684033,
			"version": 328,
			"versionNonce": 785395841,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "2QWzRxFVSqC-ATRBqEh5W",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Problem:\nprediction requires brute-force exhaustive search over 𝒴 which is not feasible",
			"rawText": "Problem:\nprediction requires brute-force exhaustive search over 𝒴 which is not feasible",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nprediction requires brute-force exhaustive search over 𝒴 which is not feasible",
			"lineHeight": 1.25
		},
		{
			"id": "IupYcLtg",
			"type": "text",
			"x": 1777.1955289790826,
			"y": 1240.1042165494507,
			"width": 775.5791015625,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1756954977,
			"version": 420,
			"versionNonce": 256689217,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Solution:\nDecompose Y into non-overlapping parts/features such that their maps do not\nintersect or combine different parts.\nOur final solution combines the compatibilities that were computed on\neach part separately",
			"rawText": "Solution:\nDecompose Y into non-overlapping parts/features such that their maps do not\nintersect or combine different parts.\nOur final solution combines the compatibilities that were computed on\neach part separately",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Solution:\nDecompose Y into non-overlapping parts/features such that their maps do not\nintersect or combine different parts.\nOur final solution combines the compatibilities that were computed on\neach part separately",
			"lineHeight": 1.25
		},
		{
			"id": "2QWzRxFVSqC-ATRBqEh5W",
			"type": "arrow",
			"x": 1688.0226806912112,
			"y": 1132.8883529300356,
			"width": 483.153771856488,
			"height": 52.47092214493887,
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
			"roundness": {
				"type": 2
			},
			"seed": 1881326785,
			"version": 369,
			"versionNonce": 734138287,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1719587892090,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					433.1642083454524,
					1.116402598828472
				],
				[
					483.153771856488,
					52.47092214493887
				]
			],
			"lastCommittedPoint": [
				477.8203122985917,
				12.28042858711342
			],
			"startBinding": {
				"elementId": "8es9qafc",
				"focus": -0.2820494168682628,
				"gap": 7.855014749213751
			},
			"endBinding": {
				"elementId": "ZcT9ll8b",
				"focus": 0.058732923473004135,
				"gap": 4.744941356568688
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "uJbkonFP",
			"type": "text",
			"x": 2066.568952619979,
			"y": 1374.6790437715895,
			"width": 218.96092224121094,
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
			"seed": 1776737807,
			"version": 96,
			"versionNonce": 621242369,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Viterbi Algorithm",
			"rawText": "Viterbi Algorithm",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Viterbi Algorithm",
			"lineHeight": 1.25
		},
		{
			"id": "lp2_wAhyXIWZNyEC4iUqB",
			"type": "image",
			"x": 1897.4907296456324,
			"y": 1600.7691621487952,
			"width": 574.0504449815176,
			"height": 37.88732936878016,
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
			"seed": 1220207247,
			"version": 169,
			"versionNonce": 1790754785,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "39868d05aa368db198e299d6c51d2df2717c5602",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "gxya0ejh3Rf5xKhPahMK9",
			"type": "image",
			"x": 2056.6668176458866,
			"y": 1482.4030347333544,
			"width": 235.17824926969308,
			"height": 114.69080114032568,
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
			"seed": 593398561,
			"version": 152,
			"versionNonce": 599530433,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dc3b52b940d1f47041b24da2e8c05298aa0e0318",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "t7fMdZyy",
			"type": "text",
			"x": 1727.6651131727722,
			"y": 1425.9288950253494,
			"width": 837.4791259765625,
			"height": 50,
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
			"seed": 188613711,
			"version": 247,
			"versionNonce": 1613036449,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "The abstract idea is that we assume that Y decomposes into different independent\nparts with connections, thus we can perform the map on each of them seperately",
			"rawText": "The abstract idea is that we assume that Y decomposes into different independent\nparts with connections, thus we can perform the map on each of them seperately",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The abstract idea is that we assume that Y decomposes into different independent\nparts with connections, thus we can perform the map on each of them seperately",
			"lineHeight": 1.25
		},
		{
			"id": "bvikiDbkvoN5tQDFeHQ81",
			"type": "image",
			"x": 1964.266592426157,
			"y": 1642.3318182635123,
			"width": 423.5656438457208,
			"height": 53.62213145085199,
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
			"seed": 767225057,
			"version": 184,
			"versionNonce": 2547585,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e15ae2d507e7c8d161838abd5bd0d1b41d88d39",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "vJJZR1urcLdrDfQMFpjbT",
			"type": "arrow",
			"x": 2367.152721001633,
			"y": 1603.8633790078113,
			"width": 191.4063075470633,
			"height": 26.416851162669673,
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
			"roundness": {
				"type": 2
			},
			"seed": 1570907393,
			"version": 104,
			"versionNonce": 838944609,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					130.69389522583992,
					-26.416851162669673
				],
				[
					191.4063075470633,
					-6.951802937544699
				]
			],
			"lastCommittedPoint": [
				191.4063075470633,
				-6.951802937544699
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "2JyXMM8R",
			"type": "text",
			"x": 2484.802129283099,
			"y": 1614.4248213578471,
			"width": 318.064697265625,
			"height": 40,
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
			"seed": 148139279,
			"version": 137,
			"versionNonce": 805548865,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "While this is given as a sum\nit can also be given as a concatenation",
			"rawText": "While this is given as a sum\nit can also be given as a concatenation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "While this is given as a sum\nit can also be given as a concatenation",
			"lineHeight": 1.25
		},
		{
			"id": "A1dEPdJq",
			"type": "text",
			"x": 2011.1548342418948,
			"y": 1707.3598830436106,
			"width": 315.2646484375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 446363407,
			"version": 81,
			"versionNonce": 1049469729,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Linear instead of exponential complexity",
			"rawText": "Linear instead of exponential complexity",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear instead of exponential complexity",
			"lineHeight": 1.25
		},
		{
			"id": "IlYhwDWI3KV7DZ93w3VFn",
			"type": "arrow",
			"x": 1273.408803059998,
			"y": 1328.3232010306592,
			"width": 0.6911691384952974,
			"height": 135.469151145071,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1108287951,
			"version": 282,
			"versionNonce": 544681967,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587892091,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6911691384952974,
					135.469151145071
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "DEvqyEMmqZHi8iCExfI23",
				"focus": -0.033813416205186665,
				"gap": 11.198874264696201
			},
			"endBinding": {
				"elementId": "3DDqRtyz",
				"focus": -0.0012940954941853954,
				"gap": 11.161566739372347
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "3DDqRtyz",
			"type": "text",
			"x": 1159.8071572369327,
			"y": 1474.9539189151026,
			"width": 225.82095336914062,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 521779951,
			"version": 105,
			"versionNonce": 84283105,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "IlYhwDWI3KV7DZ93w3VFn",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Soft-Margin SVM",
			"rawText": "Soft-Margin SVM",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Soft-Margin SVM",
			"lineHeight": 1.25
		},
		{
			"id": "pqfCgaegflFIKhDNCI-hc",
			"type": "image",
			"x": 870.466761402439,
			"y": 1526.391905377806,
			"width": 713.2674187567534,
			"height": 97.89944963327987,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 117907631,
			"version": 236,
			"versionNonce": 1705413281,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "70be5d28c802bb42b8943299b2e6258ad889eda2",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "O7kGTcvn",
			"type": "text",
			"x": 1000.9116543047932,
			"y": 1633.6254739205292,
			"width": 546.4993896484375,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 273700591,
			"version": 181,
			"versionNonce": 480153217,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "9aj0psHP9ihwwsSS0s-YL",
					"type": "arrow"
				},
				{
					"id": "EM7Y7whgMdjzbu-f2_sDt",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "This enables us to quantify the mismatch between\n𝑦 and 𝑦𝑛 (incorrect predictions can vary in quality)\nWe want to give a bigger penalty for heavier violations",
			"rawText": "This enables us to quantify the mismatch between\n𝑦 and 𝑦𝑛 (incorrect predictions can vary in quality)\nWe want to give a bigger penalty for heavier violations",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This enables us to quantify the mismatch between\n𝑦 and 𝑦𝑛 (incorrect predictions can vary in quality)\nWe want to give a bigger penalty for heavier violations",
			"lineHeight": 1.25
		},
		{
			"id": "9aj0psHP9ihwwsSS0s-YL",
			"type": "arrow",
			"x": 1265.1452970800326,
			"y": 1725.5468719596533,
			"width": 361.8235193436781,
			"height": 208.84350403922508,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1292654799,
			"version": 316,
			"versionNonce": 1578188847,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1719587892091,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					51.5662972936359,
					114.30529233422612
				],
				[
					328.30542610281486,
					104.85147116372627
				],
				[
					361.8235193436781,
					208.84350403922508
				]
			],
			"lastCommittedPoint": [
				361.8235193436781,
				208.84350403922508
			],
			"startBinding": {
				"elementId": "O7kGTcvn",
				"focus": 0.11568186618300569,
				"gap": 16.921398039124142
			},
			"endBinding": {
				"elementId": "2CuenBTL",
				"focus": 0.08264363948092204,
				"gap": 8.594383223272644
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "2CuenBTL",
			"type": "text",
			"x": 1553.1677595162657,
			"y": 1942.984759222151,
			"width": 148.2798309326172,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1965587457,
			"version": 98,
			"versionNonce": 1639368193,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "9aj0psHP9ihwwsSS0s-YL",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Slack Rescaling",
			"rawText": "Slack Rescaling",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Slack Rescaling",
			"lineHeight": 1.25
		},
		{
			"id": "EM7Y7whgMdjzbu-f2_sDt",
			"type": "arrow",
			"x": 1268.5830502329418,
			"y": 1727.2657485361078,
			"width": 324.00823466167833,
			"height": 214.85957205681598,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1609721601,
			"version": 397,
			"versionNonce": 1142177903,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1719587892092,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-37.81528468199963,
					112.58641575777165
				],
				[
					-284.4740734032242,
					113.44585404599889
				],
				[
					-324.00823466167833,
					214.85957205681598
				]
			],
			"lastCommittedPoint": [
				-328.30542610281464,
				214.85957205681598
			],
			"startBinding": {
				"elementId": "O7kGTcvn",
				"focus": -0.04645164764347161,
				"gap": 18.64027461557862
			},
			"endBinding": {
				"elementId": "YQLM1vif",
				"focus": -0.09363648214047818,
				"gap": 7.734944594045373
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "YQLM1vif",
			"type": "text",
			"x": 865.2049043774157,
			"y": 1949.8602651869692,
			"width": 158.7398223876953,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1270545921,
			"version": 108,
			"versionNonce": 896080289,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "EM7Y7whgMdjzbu-f2_sDt",
					"type": "arrow"
				}
			],
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Margin Rescaling",
			"rawText": "Margin Rescaling",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Margin Rescaling",
			"lineHeight": 1.25
		},
		{
			"id": "xQt6gPF00mM6i4pl7AnkC",
			"type": "image",
			"x": 1543.8957590239986,
			"y": 2012.0236667295258,
			"width": 166.823831422341,
			"height": 139.5028069214117,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1184774817,
			"version": 151,
			"versionNonce": 2136335713,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "54268537edffdbf7d0d8cae83584e74138cc5ee2",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "OfOHdnwD",
			"type": "text",
			"x": 1472.7313351149553,
			"y": 1981.874297044314,
			"width": 309.1526794433594,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2027399233,
			"version": 146,
			"versionNonce": 1695846721,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Normally Our magrin would look like this",
			"rawText": "Normally Our magrin would look like this",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normally Our magrin would look like this",
			"lineHeight": 1.25
		},
		{
			"id": "LCqskSmc",
			"type": "text",
			"x": 1437.0033075829292,
			"y": 2161.6758437118347,
			"width": 380.6087341308594,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1011974145,
			"version": 157,
			"versionNonce": 433242401,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "But we want to reformulate our slack to scale\nwith the error of the prediction",
			"rawText": "But we want to reformulate our slack to scale\nwith the error of the prediction",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But we want to reformulate our slack to scale\nwith the error of the prediction",
			"lineHeight": 1.25
		},
		{
			"id": "FsW85oTvrgqsaf_XpBH5G",
			"type": "image",
			"x": 1513.2278140976703,
			"y": 2201.675843617796,
			"width": 228.15972168094345,
			"height": 191.30732007927085,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2057004993,
			"version": 245,
			"versionNonce": 452982017,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3d4e85bad13a376b03ed2d74920abbbe6dfa1e8f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "fEC21ng6KOQFfYRZ6LweK",
			"type": "image",
			"x": 1493.8755918540537,
			"y": 2396.4772028990337,
			"width": 266.8641659459126,
			"height": 81.99452426964108,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 922077217,
			"version": 168,
			"versionNonce": 203140321,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b096a6f7298dbd48d51124486e2c56a79ffcc2d0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8jaLwbwKkl1dK_GfVesIj",
			"type": "image",
			"x": 799.4494439504546,
			"y": 2031.4705724829546,
			"width": 296.9029228583735,
			"height": 250.5118411617526,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2047702657,
			"version": 66,
			"versionNonce": 1958045889,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "03c7edd2c76705d65be3d2a64b4094198dabcc2f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Yl2xAmQ2",
			"type": "text",
			"x": 809.0168710590732,
			"y": 1994.7489572122554,
			"width": 256.64056396484375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1760445921,
			"version": 98,
			"versionNonce": 1047308449,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Normally our margin is fixed at 1",
			"rawText": "Normally our margin is fixed at 1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normally our margin is fixed at 1",
			"lineHeight": 1.25
		},
		{
			"id": "6Hctkm1J",
			"type": "text",
			"x": 646.8141963086978,
			"y": 2281.9824135878616,
			"width": 595.521240234375,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 841062657,
			"version": 233,
			"versionNonce": 1928391809,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "But we want to have a bigger margin for higher loss so we focus\non separating them correctly and not such high margin on things we already\npredict correctly",
			"rawText": "But we want to have a bigger margin for higher loss so we focus\non separating them correctly and not such high margin on things we already\npredict correctly",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But we want to have a bigger margin for higher loss so we focus\non separating them correctly and not such high margin on things we already\npredict correctly",
			"lineHeight": 1.25
		},
		{
			"id": "SMKPfPAO6iMLM_FZnuhh6",
			"type": "image",
			"x": 820.210754275802,
			"y": 2352.2103093178403,
			"width": 255.38030244931437,
			"height": 208.62052876141175,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 364429121,
			"version": 153,
			"versionNonce": 973190241,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "20028bb1bbfa6a9b6b0ec015d9d89c6a3e7d9ddd",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ybt7KwyY1P9LQJ4rEcXX8",
			"type": "image",
			"x": 787.064064518022,
			"y": 2571.058734305651,
			"width": 321.6736803325265,
			"height": 80.82525863329924,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2098169697,
			"version": 157,
			"versionNonce": 393117761,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0fa5ec4d6a8f2600579dd429d2b71167a995c239",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "oeVhvLz0SQX5Xakmks5Rp",
			"type": "arrow",
			"x": 1080.1462954365397,
			"y": 1280.0009663339276,
			"width": 544.4659125949414,
			"height": 3.0769579199263717,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1625724705,
			"version": 183,
			"versionNonce": 1763102753,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-544.4659125949414,
					-3.0769579199263717
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "oyWrArz7",
			"type": "text",
			"x": 413.3157471969058,
			"y": 1253.982760782155,
			"width": 95.48040771484375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1020578689,
			"version": 206,
			"versionNonce": 619324417,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Kernels",
			"rawText": "Kernels",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernels",
			"lineHeight": 1.25
		},
		{
			"id": "OoO72mKi",
			"type": "text",
			"x": 195.73624870972293,
			"y": 1305.046617784309,
			"width": 530.639404296875,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 481641039,
			"version": 296,
			"versionNonce": 1458043873,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "We can use the Kernel trick in this situation as well\nto help simplify the computation of the mapping we do\nWe define the kernel as follows",
			"rawText": "We can use the Kernel trick in this situation as well\nto help simplify the computation of the mapping we do\nWe define the kernel as follows",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can use the Kernel trick in this situation as well\nto help simplify the computation of the mapping we do\nWe define the kernel as follows",
			"lineHeight": 1.25
		},
		{
			"id": "zmgv_a3tOJUWXgu1DcpAR",
			"type": "image",
			"x": 149.61459414095964,
			"y": 1434.4513661454198,
			"width": 658,
			"height": 31,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1133453473,
			"version": 169,
			"versionNonce": 1595922369,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f24a8b983915901d1baf1721a2aeb8c89fa467d8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "yj0BFc9NBqBEsvKFu-PSw",
			"type": "image",
			"x": 304.11459409686245,
			"y": 1393.7489921652357,
			"width": 349,
			"height": 27,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 8250511,
			"version": 115,
			"versionNonce": 1873885089,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4dc14161889ed7cb7093609d276c15072fbfef09",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "vhOM32hl",
			"type": "text",
			"x": 302.14816925816,
			"y": 1488.8705616578077,
			"width": 367.15960693359375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1315584001,
			"version": 100,
			"versionNonce": 1254857601,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "Which turns our dual formulation into",
			"rawText": "Which turns our dual formulation into",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which turns our dual formulation into",
			"lineHeight": 1.25
		},
		{
			"id": "Q1pq8ktIXc8L-Tk2oTZXh",
			"type": "image",
			"x": 134.67623094173285,
			"y": 1519.8561159774604,
			"width": 687.8767269066433,
			"height": 128.02991943526732,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1089867631,
			"version": 165,
			"versionNonce": 1085178721,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "86b2c9539d79d6db418cee0eff4c4cb15e54caf7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Iw6Kx7Th",
			"type": "text",
			"x": 115.50497512900688,
			"y": 1647.886035502702,
			"width": 726.21923828125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1931804033,
			"version": 250,
			"versionNonce": 1839820609,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"text": "But how do we construct a valid kernel for a feature map that involves\n2 parameters?\nKernels and combineable! Given 2 kernels we can use the following rules",
			"rawText": "But how do we construct a valid kernel for a feature map that involves\n2 parameters?\nKernels and combineable! Given 2 kernels we can use the following rules",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But how do we construct a valid kernel for a feature map that involves\n2 parameters?\nKernels and combineable! Given 2 kernels we can use the following rules",
			"lineHeight": 1.25
		},
		{
			"id": "-rYOQaBBs29S1KaXZ2d5o",
			"type": "image",
			"x": 282.0559513671871,
			"y": 1727.626974187917,
			"width": 358,
			"height": 320,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 477643169,
			"version": 120,
			"versionNonce": 941350689,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719587891496,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9ae2cb58b3d91eb3cf7f74e67ba7d550f83c5f4c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "lPVxnLX3",
			"type": "text",
			"x": -1615.7829258547422,
			"y": 1249.077029023211,
			"width": 322.380126953125,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 85439937,
			"version": 28,
			"versionNonce": 1342747631,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1719596166352,
			"link": null,
			"locked": false,
			"text": "Anomaly Detection",
			"rawText": "Anomaly Detection",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Anomaly Detection",
			"lineHeight": 1.25
		},
		{
			"id": "0y4B9Dwijnuoh5IVK4sF4",
			"type": "image",
			"x": -289.63634352587076,
			"y": 1483.2933420873435,
			"width": 789,
			"height": 56,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1237243727,
			"version": 95,
			"versionNonce": 1254547649,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719587738426,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "25d99f4a0af9790a93b3b92483bacb32dc484eeb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "RaNvPji2Kw4Fk1_hy2RgO",
			"type": "image",
			"x": 1644.7834728451166,
			"y": 233.0870422932872,
			"width": 337.4830335686903,
			"height": 49.15513749804837,
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
			"seed": 990362977,
			"version": 252,
			"versionNonce": 1827827617,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719586238494,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a0cdd42dbdac6aa5a153a294bb05f217d4af2621",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xTgRl8KBENZ1sMlEHdy6l",
			"type": "image",
			"x": 1635.4353171865787,
			"y": 319.18109798529196,
			"width": 356.1793438172811,
			"height": 44.168503684813864,
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
			"seed": 509854081,
			"version": 209,
			"versionNonce": 292806927,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719586238982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1d8df6f0254077e3bb3edbafbdd165141fd1da0a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "GZvPXWXMJYLE-yVt1sHG2",
			"type": "image",
			"x": 1637.2191119948682,
			"y": 412.3387684801567,
			"width": 352.61175493844246,
			"height": 71.74592490072409,
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
			"seed": 1569578177,
			"version": 202,
			"versionNonce": 114665281,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719586239531,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eb9c2b5007f15d9fdb0f8525e5b0534f9c59208d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "QldFbNKJ",
			"type": "text",
			"x": 1809.8912924741849,
			"y": 166.27691914116724,
			"width": 14.00006103515625,
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
			"seed": 1138183983,
			"version": 9,
			"versionNonce": 2092945921,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719586107547,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "NDLXcOZ7KnV2Qp4aHmFmH",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "iPTXTjtNYAmcTFVyNgZDb",
			"type": "image",
			"x": 1693.9426623415793,
			"y": 141.59039715894642,
			"width": 245.89732195425924,
			"height": 51.34119908935083,
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
			"seed": 1053341455,
			"version": 61,
			"versionNonce": 373560705,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719586089713,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f455f80c0c6cd6aefcd7d5ebd915d653fc3ba28c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "h7Wex1y6",
			"type": "text",
			"x": 1671.2357816186,
			"y": 1148.6692162329985,
			"width": 9.999984741210938,
			"height": 25,
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
			"seed": 1139267265,
			"version": 2,
			"versionNonce": 939241519,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719586903713,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "2QWzRxFVSqC-ATRBqEh5W",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "5ICykwhj",
			"type": "text",
			"x": 2047.8955088094094,
			"y": 1651.2803262871857,
			"width": 9.999984741210938,
			"height": 25,
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
			"seed": 1156135969,
			"version": 3,
			"versionNonce": 1656822209,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719587081989,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "vJJZR1urcLdrDfQMFpjbT",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "MkdaAHLh",
			"type": "text",
			"x": 1009.4259246176082,
			"y": 1909.9119386051761,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 850683855,
			"version": 2,
			"versionNonce": 652400705,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719587293357,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "9aj0psHP9ihwwsSS0s-YL",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "MmnfK4k0",
			"type": "text",
			"x": 662.5879467505649,
			"y": 1914.7405429582102,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 841468961,
			"version": 2,
			"versionNonce": 726566095,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1719587308718,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "EM7Y7whgMdjzbu-f2_sDt",
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
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 36,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 2537.2815961971182,
		"scrollY": -586.427858225062,
		"zoom": {
			"value": 0.651156678718982
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